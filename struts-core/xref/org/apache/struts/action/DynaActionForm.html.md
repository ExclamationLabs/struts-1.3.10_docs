[View Javadoc](../../../../../apidocs/org/apache/struts/action/DynaActionForm.html.md)


    1   /*
    2    * $Id: DynaActionForm.java 471754 2006-11-06 14:55:09Z husted $
    3    *
    4    * Licensed to the Apache Software Foundation (ASF) under one
    5    * or more contributor license agreements.  See the NOTICE file
    6    * distributed with this work for additional information
    7    * regarding copyright ownership.  The ASF licenses this file
    8    * to you under the Apache License, Version 2.0 (the
    9    * "License"); you may not use this file except in compliance
    10   * with the License.  You may obtain a copy of the License at
    11   *
    12   *  http://www.apache.org/licenses/LICENSE-2.0
    13   *
    14   * Unless required by applicable law or agreed to in writing,
    15   * software distributed under the License is distributed on an
    16   * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    17   * KIND, either express or implied.  See the License for the
    18   * specific language governing permissions and limitations
    19   * under the License.
    20   */
    21  package org.apache.struts.action;
    22  
    23  import org.apache.commons.beanutils.ConversionException;
    24  import org.apache.commons.beanutils.DynaBean;
    25  import org.apache.commons.beanutils.DynaClass;
    26  import org.apache.commons.beanutils.DynaProperty;
    27  import org.apache.struts.config.FormBeanConfig;
    28  import org.apache.struts.config.FormPropertyConfig;
    29  
    30  import javax.servlet.ServletRequest;
    31  import javax.servlet.http.HttpServletRequest;
    32  
    33  import java.lang.reflect.Array;
    34  
    35  import java.util.HashMap;
    36  import java.util.Iterator;
    37  import java.util.List;
    38  import java.util.Map;
    39  import java.util.StringTokenizer;
    40  
    41  /**
    42   * <p>Specialized subclass of <code>ActionForm</code> that allows the creation
    43   * of form beans with dynamic sets of properties, without requiring the
    44   * developer to create a Java class for each type of form bean.</p>
    45   *
    46   * <p><strong>USAGE NOTE</strong> - Since Struts 1.1, the <code>reset</code>
    47   * method no longer initializes property values to those specified in
    48   * <code>&lt;form-property&gt;</code> elements in the Struts module
    49   * configuration file.  If you wish to utilize that behavior, the simplest
    50   * solution is to subclass <code>DynaActionForm</code> and call the
    51   * <code>initialize</code> method inside it.</p>
    52   *
    53   * @version $Rev: 471754 $ $Date: 2005-11-12 11:52:08 -0500 (Sat, 12 Nov 2005)
    54   *          $
    55   * @since Struts 1.1
    56   */
    57  public class DynaActionForm extends ActionForm implements DynaBean {
    58      // ----------------------------------------------------- Instance Variables
    59  
    60      /**
    61       * <p>The <code>DynaActionFormClass</code> with which we are associated.
    62       * </p>
    63       */
    64      protected DynaActionFormClass dynaClass = null;
    65  
    66      /**
    67       * <p>The set of property values for this <code>DynaActionForm</code>,
    68       * keyed by property name.</p>
    69       */
    70      protected HashMap dynaValues = new HashMap();
    71  
    72      // ----------------------------------------------------- ActionForm Methods
    73  
    74      /**
    75       * <p>Initialize all bean properties to their initial values, as specified
    76       * in the {@link FormPropertyConfig} elements associated with the
    77       * definition of this <code>DynaActionForm</code>.</p>
    78       *
    79       * @param mapping The mapping used to select this instance
    80       */
    81      public void initialize(ActionMapping mapping) {
    82          String name = mapping.getName();
    83  
    84          if (name == null) {
    85              return;
    86          }
    87  
    88          FormBeanConfig config =
    89              mapping.getModuleConfig().findFormBeanConfig(name);
    90  
    91          if (config == null) {
    92              return;
    93          }
    94  
    95          initialize(config);
    96      }
    97  
    98      /**
    99       * <p>Initialize the specified form bean.</p>
    100      *
    101      * @param config The configuration for the form bean to initialize.
    102      */
    103     public void initialize(FormBeanConfig config) {
    104         FormPropertyConfig[] props = config.findFormPropertyConfigs();
    105 
    106         for (int i = 0; i < props.length; i++) {
    107             set(props[i].getName(), props[i].initial());
    108         }
    109     }
    110 
    111     // :FIXME: Is there any point in retaining these reset methods
    112     // since they now simply replicate the superclass behavior?
    113 
    114     /**
    115      * <p>Reset bean properties to their default state, as needed. This method
    116      * is called before the properties are repopulated by the controller.</p>
    117      *
    118      * <p>The default implementation attempts to forward to the HTTP version
    119      * of this method.</p>
    120      *
    121      * @param mapping The mapping used to select this instance
    122      * @param request The servlet request we are processing
    123      */
    124     public void reset(ActionMapping mapping, ServletRequest request) {
    125         super.reset(mapping, request);
    126     }
    127 
    128     /**
    129      * <p>Reset the properties to their <code>initial</code> value if their
    130      * <code>reset</code> configuration is set to true or if
    131      * <code>reset</code> is set to a list of HTTP request methods that
    132      * includes the method of given <code>request</code> object.</p>
    133      *
    134      * @param mapping The mapping used to select this instance
    135      * @param request The servlet request we are processing
    136      */
    137     public void reset(ActionMapping mapping, HttpServletRequest request) {
    138         String name = getDynaClass().getName();
    139 
    140         if (name == null) {
    141             return;
    142         }
    143 
    144         FormBeanConfig config =
    145             mapping.getModuleConfig().findFormBeanConfig(name);
    146 
    147         if (config == null) {
    148             return;
    149         }
    150 
    151         // look for properties we should reset
    152         FormPropertyConfig[] props = config.findFormPropertyConfigs();
    153 
    154         for (int i = 0; i < props.length; i++) {
    155             String resetValue = props[i].getReset();
    156 
    157             // skip this property if there's no reset value
    158             if ((resetValue == null) || (resetValue.length() <= 0)) {
    159                 continue;
    160             }
    161 
    162             boolean reset = Boolean.valueOf(resetValue).booleanValue();
    163 
    164             if (!reset) {
    165                 // check for the request method
    166                 // use a StringTokenizer with the default delimiters + a comma
    167                 StringTokenizer st =
    168                     new StringTokenizer(resetValue, ", \t\n\r\f");
    169 
    170                 while (st.hasMoreTokens()) {
    171                     String token = st.nextToken();
    172 
    173                     if (token.equalsIgnoreCase(request.getMethod())) {
    174                         reset = true;
    175 
    176                         break;
    177                     }
    178                 }
    179             }
    180 
    181             if (reset) {
    182                 set(props[i].getName(), props[i].initial());
    183             }
    184         }
    185     }
    186 
    187     // ------------------------------------------------------- DynaBean Methods
    188 
    189     /**
    190      * <p>Indicates if the specified mapped property contain a value for the
    191      * specified key value.</p>
    192      *
    193      * @param name Name of the property to check
    194      * @param key  Name of the key to check
    195      * @return <code>true</code> if the specified mapped property contains a
    196      *         value for the specified key value; <code>true</code>
    197      *         otherwise.
    198      * @throws NullPointerException     if there is no property of the
    199      *                                  specified name
    200      * @throws IllegalArgumentException if there is no mapped property of the
    201      *                                  specified name
    202      */
    203     public boolean contains(String name, String key) {
    204         Object value = dynaValues.get(name);
    205 
    206         if (value == null) {
    207             throw new NullPointerException("No mapped value for '" + name + "("
    208                 + key + ")'");
    209         } else if (value instanceof Map) {
    210             return (((Map) value).containsKey(key));
    211         } else {
    212             throw new IllegalArgumentException("Non-mapped property for '"
    213                 + name + "(" + key + ")'");
    214         }
    215     }
    216 
    217     /**
    218      * <p>Return the value of a simple property with the specified name.</p>
    219      *
    220      * @param name Name of the property whose value is to be retrieved
    221      * @return The value of a simple property with the specified name.
    222      * @throws IllegalArgumentException if there is no property of the
    223      *                                  specified name
    224      * @throws NullPointerException     if the type specified for the property
    225      *                                  is invalid
    226      */
    227     public Object get(String name) {
    228         // Return any non-null value for the specified property
    229         Object value = dynaValues.get(name);
    230 
    231         if (value != null) {
    232             return (value);
    233         }
    234 
    235         // Return a null value for a non-primitive property
    236         Class type = getDynaProperty(name).getType();
    237 
    238         if (type == null) {
    239             throw new NullPointerException("The type for property " + name
    240                 + " is invalid");
    241         }
    242 
    243         if (!type.isPrimitive()) {
    244             return (value);
    245         }
    246 
    247         // Manufacture default values for primitive properties
    248         if (type == Boolean.TYPE) {
    249             return (Boolean.FALSE);
    250         } else if (type == Byte.TYPE) {
    251             return (new Byte((byte) 0));
    252         } else if (type == Character.TYPE) {
    253             return (new Character((char) 0));
    254         } else if (type == Double.TYPE) {
    255             return (new Double(0.0));
    256         } else if (type == Float.TYPE) {
    257             return (new Float((float) 0.0));
    258         } else if (type == Integer.TYPE) {
    259             return (new Integer(0));
    260         } else if (type == Long.TYPE) {
    261             return (new Long(0));
    262         } else if (type == Short.TYPE) {
    263             return (new Short((short) 0));
    264         } else {
    265             return (null);
    266         }
    267     }
    268 
    269     /**
    270      * <p>Return the value of an indexed property with the specified name.
    271      * </p>
    272      *
    273      * @param name  Name of the property whose value is to be retrieved
    274      * @param index Index of the value to be retrieved
    275      * @return The value of an indexed property with the specified name.
    276      * @throws IllegalArgumentException if there is no property of the
    277      *                                  specified name
    278      * @throws IllegalArgumentException if the specified property exists, but
    279      *                                  is not indexed
    280      * @throws NullPointerException     if no array or List has been
    281      *                                  initialized for this property
    282      */
    283     public Object get(String name, int index) {
    284         Object value = dynaValues.get(name);
    285 
    286         if (value == null) {
    287             throw new NullPointerException("No indexed value for '" + name
    288                 + "[" + index + "]'");
    289         } else if (value.getClass().isArray()) {
    290             return (Array.get(value, index));
    291         } else if (value instanceof List) {
    292             return ((List) value).get(index);
    293         } else {
    294             throw new IllegalArgumentException("Non-indexed property for '"
    295                 + name + "[" + index + "]'");
    296         }
    297     }
    298 
    299     /**
    300      * <p>Return the value of a mapped property with the specified name, or
    301      * <code>null</code> if there is no value for the specified key. </p>
    302      *
    303      * @param name Name of the property whose value is to be retrieved
    304      * @param key  Key of the value to be retrieved
    305      * @return The value of a mapped property with the specified name, or
    306      *         <code>null</code> if there is no value for the specified key.
    307      * @throws NullPointerException     if there is no property of the
    308      *                                  specified name
    309      * @throws IllegalArgumentException if the specified property exists, but
    310      *                                  is not mapped
    311      */
    312     public Object get(String name, String key) {
    313         Object value = dynaValues.get(name);
    314 
    315         if (value == null) {
    316             throw new NullPointerException("No mapped value for '" + name + "("
    317                 + key + ")'");
    318         } else if (value instanceof Map) {
    319             return (((Map) value).get(key));
    320         } else {
    321             throw new IllegalArgumentException("Non-mapped property for '"
    322                 + name + "(" + key + ")'");
    323         }
    324     }
    325 
    326     /**
    327      * <p>Return the value of a <code>String</code> property with the
    328      * specified name. This is equivalent to calling <code>(String)
    329      * dynaForm.get(name)</code>.</p>
    330      *
    331      * @param name Name of the property whose value is to be retrieved.
    332      * @return The value of a <code>String</code> property with the specified
    333      *         name.
    334      * @throws IllegalArgumentException if there is no property of the
    335      *                                  specified name
    336      * @throws NullPointerException     if the type specified for the property
    337      *                                  is invalid
    338      * @throws ClassCastException       if the property is not a String.
    339      * @since Struts 1.2
    340      */
    341     public String getString(String name) {
    342         return (String) this.get(name);
    343     }
    344 
    345     /**
    346      * <p>Return the value of a <code>String[]</code> property with the
    347      * specified name. This is equivalent to calling <code>(String[])
    348      * dynaForm.get(name)</code>.</p>
    349      *
    350      * @param name Name of the property whose value is to be retrieved.
    351      * @return The value of a <code>String[]</code> property with the
    352      *         specified name.
    353      * @throws IllegalArgumentException if there is no property of the
    354      *                                  specified name
    355      * @throws NullPointerException     if the type specified for the property
    356      *                                  is invalid
    357      * @throws ClassCastException       if the property is not a String[].
    358      * @since Struts 1.2
    359      */
    360     public String[] getStrings(String name) {
    361         return (String[]) this.get(name);
    362     }
    363 
    364     /**
    365      * <p>Return the <code>DynaClass</code> instance that describes the set of
    366      * properties available for this <code>DynaBean</code>.</p>
    367      *
    368      * @return The <code>DynaClass</code> instance that describes the set of
    369      *         properties available for this <code>DynaBean</code>.
    370      */
    371     public DynaClass getDynaClass() {
    372         return (this.dynaClass);
    373     }
    374 
    375     /**
    376      * <p>Returns the <code>Map</code> containing the property values. This is
    377      * done mostly to facilitate accessing the <code>DynaActionForm</code>
    378      * through JavaBeans accessors, in order to use the JavaServer Pages
    379      * Standard Tag Library (JSTL).</p>
    380      *
    381      * <p>For instance, the normal JSTL EL syntax for accessing an
    382      * <code>ActionForm</code> would be something like this:
    383      * <pre>
    384      *  ${formbean.prop}</pre>
    385      * The JSTL EL syntax for accessing a <code>DynaActionForm</code> looks
    386      * something like this (because of the presence of this
    387      * <code>getMap()</code> method):
    388      * <pre>
    389      *  ${dynabean.map.prop}</pre>
    390      * </p>
    391      *
    392      * @return The <code>Map</code> containing the property values.
    393      */
    394     public Map getMap() {
    395         return (dynaValues);
    396     }
    397 
    398     /**
    399      * <p>Remove any existing value for the specified key on the specified
    400      * mapped property.</p>
    401      *
    402      * @param name Name of the property for which a value is to be removed
    403      * @param key  Key of the value to be removed
    404      * @throws NullPointerException     if there is no property of the
    405      *                                  specified name
    406      * @throws IllegalArgumentException if there is no mapped property of the
    407      *                                  specified name
    408      */
    409     public void remove(String name, String key) {
    410         Object value = dynaValues.get(name);
    411 
    412         if (value == null) {
    413             throw new NullPointerException("No mapped value for '" + name + "("
    414                 + key + ")'");
    415         } else if (value instanceof Map) {
    416             ((Map) value).remove(key);
    417         } else {
    418             throw new IllegalArgumentException("Non-mapped property for '"
    419                 + name + "(" + key + ")'");
    420         }
    421     }
    422 
    423     /**
    424      * <p>Set the value of a simple property with the specified name.</p>
    425      *
    426      * @param name  Name of the property whose value is to be set
    427      * @param value Value to which this property is to be set
    428      * @throws ConversionException      if the specified value cannot be
    429      *                                  converted to the type required for
    430      *                                  this property
    431      * @throws IllegalArgumentException if there is no property of the
    432      *                                  specified name
    433      * @throws NullPointerException     if the type specified for the property
    434      *                                  is invalid
    435      * @throws NullPointerException     if an attempt is made to set a
    436      *                                  primitive property to null
    437      */
    438     public void set(String name, Object value) {
    439         DynaProperty descriptor = getDynaProperty(name);
    440 
    441         if (descriptor.getType() == null) {
    442             throw new NullPointerException("The type for property " + name
    443                 + " is invalid");
    444         }
    445 
    446         if (value == null) {
    447             if (descriptor.getType().isPrimitive()) {
    448                 throw new NullPointerException("Primitive value for '" + name
    449                     + "'");
    450             }
    451         } else if (!isDynaAssignable(descriptor.getType(), value.getClass())) {
    452             throw new ConversionException("Cannot assign value of type '"
    453                 + value.getClass().getName() + "' to property '" + name
    454                 + "' of type '" + descriptor.getType().getName() + "'");
    455         }
    456 
    457         dynaValues.put(name, value);
    458     }
    459 
    460     /**
    461      * <p>Set the value of an indexed property with the specified name.</p>
    462      *
    463      * @param name  Name of the property whose value is to be set
    464      * @param index Index of the property to be set
    465      * @param value Value to which this property is to be set
    466      * @throws ConversionException       if the specified value cannot be
    467      *                                   converted to the type required for
    468      *                                   this property
    469      * @throws NullPointerException      if there is no property of the
    470      *                                   specified name
    471      * @throws IllegalArgumentException  if the specified property exists, but
    472      *                                   is not indexed
    473      * @throws IndexOutOfBoundsException if the specified index is outside the
    474      *                                   range of the underlying property
    475      */
    476     public void set(String name, int index, Object value) {
    477         Object prop = dynaValues.get(name);
    478 
    479         if (prop == null) {
    480             throw new NullPointerException("No indexed value for '" + name
    481                 + "[" + index + "]'");
    482         } else if (prop.getClass().isArray()) {
    483             Array.set(prop, index, value);
    484         } else if (prop instanceof List) {
    485             try {
    486                 ((List) prop).set(index, value);
    487             } catch (ClassCastException e) {
    488                 throw new ConversionException(e.getMessage());
    489             }
    490         } else {
    491             throw new IllegalArgumentException("Non-indexed property for '"
    492                 + name + "[" + index + "]'");
    493         }
    494     }
    495 
    496     /**
    497      * <p>Set the value of a mapped property with the specified name.</p>
    498      *
    499      * @param name  Name of the property whose value is to be set
    500      * @param key   Key of the property to be set
    501      * @param value Value to which this property is to be set
    502      * @throws NullPointerException     if there is no property of the
    503      *                                  specified name
    504      * @throws IllegalArgumentException if the specified property exists, but
    505      *                                  is not mapped
    506      */
    507     public void set(String name, String key, Object value) {
    508         Object prop = dynaValues.get(name);
    509 
    510         if (prop == null) {
    511             throw new NullPointerException("No mapped value for '" + name + "("
    512                 + key + ")'");
    513         } else if (prop instanceof Map) {
    514             ((Map) prop).put(key, value);
    515         } else {
    516             throw new IllegalArgumentException("Non-mapped property for '"
    517                 + name + "(" + key + ")'");
    518         }
    519     }
    520 
    521     // --------------------------------------------------------- Public Methods
    522 
    523     /**
    524      * <p>Render a String representation of this object.</p>
    525      *
    526      * @return A string representation of this object.
    527      */
    528     public String toString() {
    529         StringBuffer sb = new StringBuffer("DynaActionForm[dynaClass=");
    530         DynaClass dynaClass = getDynaClass();
    531 
    532         if (dynaClass == null) {
    533             return sb.append("null]").toString();
    534         }
    535 
    536         sb.append(dynaClass.getName());
    537 
    538         DynaProperty[] props = dynaClass.getDynaProperties();
    539 
    540         if (props == null) {
    541             props = new DynaProperty[0];
    542         }
    543 
    544         for (int i = 0; i < props.length; i++) {
    545             sb.append(',');
    546             sb.append(props[i].getName());
    547             sb.append('=');
    548 
    549             Object value = get(props[i].getName());
    550 
    551             if (value == null) {
    552                 sb.append("<NULL>");
    553             } else if (value.getClass().isArray()) {
    554                 int n = Array.getLength(value);
    555 
    556                 sb.append("{");
    557 
    558                 for (int j = 0; j < n; j++) {
    559                     if (j > 0) {
    560                         sb.append(',');
    561                     }
    562 
    563                     sb.append(Array.get(value, j));
    564                 }
    565 
    566                 sb.append("}");
    567             } else if (value instanceof List) {
    568                 int n = ((List) value).size();
    569 
    570                 sb.append("{");
    571 
    572                 for (int j = 0; j < n; j++) {
    573                     if (j > 0) {
    574                         sb.append(',');
    575                     }
    576 
    577                     sb.append(((List) value).get(j));
    578                 }
    579 
    580                 sb.append("}");
    581             } else if (value instanceof Map) {
    582                 int n = 0;
    583                 Iterator keys = ((Map) value).keySet().iterator();
    584 
    585                 sb.append("{");
    586 
    587                 while (keys.hasNext()) {
    588                     if (n > 0) {
    589                         sb.append(',');
    590                     }
    591 
    592                     n++;
    593 
    594                     Object key = keys.next();
    595 
    596                     sb.append(key);
    597                     sb.append('=');
    598                     sb.append(((Map) value).get(key));
    599                 }
    600 
    601                 sb.append("}");
    602             } else {
    603                 sb.append(value);
    604             }
    605         }
    606 
    607         sb.append("]");
    608 
    609         return (sb.toString());
    610     }
    611 
    612     // -------------------------------------------------------- Package Methods
    613 
    614     /**
    615      * <p>Set the <code>DynaActionFormClass</code> instance with which we are
    616      * associated.</p>
    617      *
    618      * @param dynaClass The DynaActionFormClass instance for this bean
    619      */
    620     void setDynaActionFormClass(DynaActionFormClass dynaClass) {
    621         this.dynaClass = dynaClass;
    622     }
    623 
    624     // ------------------------------------------------------ Protected Methods
    625 
    626     /**
    627      * <p>Return the property descriptor for the specified property name.</p>
    628      *
    629      * @param name Name of the property for which to retrieve the descriptor
    630      * @return The property descriptor for the specified property name.
    631      * @throws IllegalArgumentException if this is not a valid property name
    632      *                                  for our DynaClass
    633      */
    634     protected DynaProperty getDynaProperty(String name) {
    635         DynaProperty descriptor = getDynaClass().getDynaProperty(name);
    636 
    637         if (descriptor == null) {
    638             throw new IllegalArgumentException("Invalid property name '" + name
    639                 + "'");
    640         }
    641 
    642         return (descriptor);
    643     }
    644 
    645     /**
    646      * <p>Indicates if an object of the source class is assignable to the
    647      * destination class.</p>
    648      *
    649      * @param dest   Destination class
    650      * @param source Source class
    651      * @return <code>true</code> if the source is assignable to the
    652      *         destination; <code>false</code> otherwise.
    653      */
    654     protected boolean isDynaAssignable(Class dest, Class source) {
    655         if (dest.isAssignableFrom(source)
    656             || ((dest == Boolean.TYPE) && (source == Boolean.class))
    657             || ((dest == Byte.TYPE) && (source == Byte.class))
    658             || ((dest == Character.TYPE) && (source == Character.class))
    659             || ((dest == Double.TYPE) && (source == Double.class))
    660             || ((dest == Float.TYPE) && (source == Float.class))
    661             || ((dest == Integer.TYPE) && (source == Integer.class))
    662             || ((dest == Long.TYPE) && (source == Long.class))
    663             || ((dest == Short.TYPE) && (source == Short.class))) {
    664             return (true);
    665         } else {
    666             return (false);
    667         }
    668     }
    669 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
