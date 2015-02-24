[View Javadoc](../../../../../apidocs/org/apache/struts/config/FormPropertyConfig.html.md)


    1   /*
    2    * $Id: FormPropertyConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.config;
    22  
    23  import org.apache.commons.beanutils.ConvertUtils;
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  
    27  import java.lang.reflect.Array;
    28  import java.lang.reflect.InvocationTargetException;
    29  
    30  /**
    31   * <p>A JavaBean representing the configuration information of a
    32   * <code>&lt;form-property&gt;</code> element in a Struts configuration
    33   * file.<p>
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-11-12 11:52:08 -0500 (Sat, 12 Nov 2005)$
    36   * @since Struts 1.1
    37   */
    38  public class FormPropertyConfig extends BaseConfig {
    39      /**
    40       * The logging instance
    41       */
    42      private static final Log log = LogFactory.getLog(FormPropertyConfig.class);
    43  
    44      // ----------------------------------------------------- Instance Variables
    45      // ------------------------------------------------------------- Properties
    46  
    47      /**
    48       * String representation of the initial value for this property.
    49       */
    50      protected String initial = null;
    51  
    52      /**
    53       * The JavaBean property name of the property described by this element.
    54       */
    55      protected String name = null;
    56  
    57      /**
    58       * <p>The conditions under which the property described by this element
    59       * should be reset to its <code>initial</code> value when the form's
    60       * <code>reset</code> method is called.</p> <p>This may be set to true (to
    61       * always reset the property) or a comma-separated list of HTTP request
    62       * methods.</p>
    63       *
    64       * @since Struts 1.3
    65       */
    66      protected String reset = null;
    67  
    68      /**
    69       * <p>The size of the array to be created if this property is an array
    70       * type and there is no specified <code>initial</code> value.  This value
    71       * must be non-negative.</p>
    72       *
    73       * @since Struts 1.1
    74       */
    75      protected int size = 0;
    76  
    77      /**
    78       * The fully qualified Java class name of the implementation class of this
    79       * bean property, optionally followed by <code>[]</code> to indicate that
    80       * the property is indexed.
    81       */
    82      protected String type = null;
    83  
    84      // ----------------------------------------------------------- Constructors
    85  
    86      /**
    87       * Standard no-arguments constructor for dynamic instantiation.
    88       */
    89      public FormPropertyConfig() {
    90          super();
    91      }
    92  
    93      /**
    94       * Constructor that preconfigures the relevant properties.
    95       *
    96       * @param name    Name of this property
    97       * @param type    Fully qualified class name of this property
    98       * @param initial Initial value of this property (if any)
    99       */
    100     public FormPropertyConfig(String name, String type, String initial) {
    101         this(name, type, initial, 0);
    102     }
    103 
    104     /**
    105      * Constructor that preconfigures the relevant properties.
    106      *
    107      * @param name    Name of this property
    108      * @param type    Fully qualified class name of this property
    109      * @param initial Initial value of this property (if any)
    110      * @param reset   The conditions under which this property will be reset
    111      *                to its initial value.
    112      */
    113     public FormPropertyConfig(String name, String type, String initial,
    114         String reset) {
    115         this(name, type, initial, reset, 0);
    116     }
    117 
    118     /**
    119      * Constructor that preconfigures the relevant properties.
    120      *
    121      * @param name    Name of this property
    122      * @param type    Fully qualified class name of this property
    123      * @param initial Initial value of this property (if any)
    124      * @param size    Size of the array to be created if this property is an
    125      *                array with no defined initial value
    126      */
    127     public FormPropertyConfig(String name, String type, String initial, int size) {
    128         this(name, type, initial, null, size);
    129     }
    130 
    131     /**
    132      * Constructor that preconfigures the relevant properties.
    133      *
    134      * @param name    Name of this property
    135      * @param type    Fully qualified class name of this property
    136      * @param initial Initial value of this property (if any)
    137      * @param size    Size of the array to be created if this property is an
    138      *                array with no defined initial value
    139      * @param reset   The conditions under which this property will be reset
    140      *                to its initial value.
    141      */
    142     public FormPropertyConfig(String name, String type, String initial,
    143         String reset, int size) {
    144         super();
    145         setName(name);
    146         setType(type);
    147         setInitial(initial);
    148         setReset(reset);
    149         setSize(size);
    150     }
    151 
    152     public String getInitial() {
    153         return (this.initial);
    154     }
    155 
    156     public void setInitial(String initial) {
    157         if (configured) {
    158             throw new IllegalStateException("Configuration is frozen");
    159         }
    160 
    161         this.initial = initial;
    162     }
    163 
    164     public String getName() {
    165         return (this.name);
    166     }
    167 
    168     public void setName(String name) {
    169         if (configured) {
    170             throw new IllegalStateException("Configuration is frozen");
    171         }
    172 
    173         this.name = name;
    174     }
    175 
    176     public String getReset() {
    177         return (this.reset);
    178     }
    179 
    180     public void setReset(String reset) {
    181         if (configured) {
    182             throw new IllegalStateException("Configuration is frozen");
    183         }
    184 
    185         this.reset = reset;
    186     }
    187 
    188     public int getSize() {
    189         return (this.size);
    190     }
    191 
    192     public void setSize(int size) {
    193         if (configured) {
    194             throw new IllegalStateException("Configuration is frozen");
    195         }
    196 
    197         if (size < 0) {
    198             throw new IllegalArgumentException("size < 0");
    199         }
    200 
    201         this.size = size;
    202     }
    203 
    204     public String getType() {
    205         return (this.type);
    206     }
    207 
    208     public void setType(String type) {
    209         if (configured) {
    210             throw new IllegalStateException("Configuration is frozen");
    211         }
    212 
    213         this.type = type;
    214     }
    215 
    216     /**
    217      * Return a Class corresponds to the value specified for the
    218      * <code>type</code> property, taking into account the trailing "[]" for
    219      * arrays (as well as the ability to specify primitive Java types).
    220      */
    221     public Class getTypeClass() {
    222         // Identify the base class (in case an array was specified)
    223         String baseType = getType();
    224         boolean indexed = false;
    225 
    226         if (baseType.endsWith("[]")) {
    227             baseType = baseType.substring(0, baseType.length() - 2);
    228             indexed = true;
    229         }
    230 
    231         // Construct an appropriate Class instance for the base class
    232         Class baseClass = null;
    233 
    234         if ("boolean".equals(baseType)) {
    235             baseClass = Boolean.TYPE;
    236         } else if ("byte".equals(baseType)) {
    237             baseClass = Byte.TYPE;
    238         } else if ("char".equals(baseType)) {
    239             baseClass = Character.TYPE;
    240         } else if ("double".equals(baseType)) {
    241             baseClass = Double.TYPE;
    242         } else if ("float".equals(baseType)) {
    243             baseClass = Float.TYPE;
    244         } else if ("int".equals(baseType)) {
    245             baseClass = Integer.TYPE;
    246         } else if ("long".equals(baseType)) {
    247             baseClass = Long.TYPE;
    248         } else if ("short".equals(baseType)) {
    249             baseClass = Short.TYPE;
    250         } else {
    251             ClassLoader classLoader =
    252                 Thread.currentThread().getContextClassLoader();
    253 
    254             if (classLoader == null) {
    255                 classLoader = this.getClass().getClassLoader();
    256             }
    257 
    258             try {
    259                 baseClass = classLoader.loadClass(baseType);
    260             } catch (ClassNotFoundException ex) {
    261                 log.error("Class '" + baseType +
    262                           "' not found for property '" + name + "'");
    263                 baseClass = null;
    264             }
    265         }
    266 
    267         // Return the base class or an array appropriately
    268         if (indexed) {
    269             return (Array.newInstance(baseClass, 0).getClass());
    270         } else {
    271             return (baseClass);
    272         }
    273     }
    274 
    275     // --------------------------------------------------------- Public Methods
    276 
    277     /**
    278      * <p>Return an object representing the initial value of this property.
    279      * This is calculated according to the following algorithm:</p>
    280      *
    281      * <ul>
    282      *
    283      * <li>If the value you have specified for the <code>type</code> property
    284      * represents an array (i.e. it ends with "[]"):
    285      *
    286      * <ul>
    287      *
    288      * <li>If you have specified a value for the <code>initial</code>
    289      * property, <code>ConvertUtils.convert</code> will be called to convert
    290      * it into an instance of the specified array type.</li>
    291      *
    292      * <li>If you have not specified a value for the <code>initial</code>
    293      * property, an array of the length specified by the <code>size</code>
    294      * property will be created. Each element of the array will be
    295      * instantiated via the zero-args constructor on the specified class (if
    296      * any). Otherwise, <code>null</code> will be returned.</li>
    297      *
    298      * </ul></li>
    299      *
    300      * <li>If the value you have specified for the <code>type</code> property
    301      * does not represent an array:
    302      *
    303      * <ul>
    304      *
    305      * <li>If you have specified a value for the <code>initial</code>
    306      * property, <code>ConvertUtils.convert</code> will be called to convert
    307      * it into an object instance.</li>
    308      *
    309      * <li>If you have not specified a value for the <code>initial</code>
    310      * attribute, Struts will instantiate an instance via the zero-args
    311      * constructor on the specified class (if any). Otherwise,
    312      * <code>null</code> will be returned.</li>
    313      *
    314      * </ul></li>
    315      *
    316      * </ul>
    317      */
    318     public Object initial() {
    319         Object initialValue = null;
    320 
    321         try {
    322             Class clazz = getTypeClass();
    323 
    324             if (clazz.isArray()) {
    325                 if (initial != null) {
    326                     initialValue = ConvertUtils.convert(initial, clazz);
    327                 } else {
    328                     initialValue =
    329                         Array.newInstance(clazz.getComponentType(), size);
    330 
    331                     if (!(clazz.getComponentType().isPrimitive())) {
    332                         for (int i = 0; i < size; i++) {
    333                             try {
    334                                 Array.set(initialValue, i,
    335                                     clazz.getComponentType().newInstance());
    336                             } catch (Throwable t) {
    337                                 log.error("Unable to create instance of "
    338                                     + clazz.getName() + " for property=" + name
    339                                     + ", type=" + type + ", initial=" + initial
    340                                     + ", size=" + size + ".");
    341 
    342                                 //FIXME: Should we just dump the entire application/module ?
    343                             }
    344                         }
    345                     }
    346                 }
    347             } else {
    348                 if (initial != null) {
    349                     initialValue = ConvertUtils.convert(initial, clazz);
    350                 } else {
    351                     initialValue = clazz.newInstance();
    352                 }
    353             }
    354         } catch (Throwable t) {
    355             initialValue = null;
    356         }
    357 
    358         return (initialValue);
    359     }
    360 
    361     /**
    362      * <p>Inherit values that have not been overridden from the provided
    363      * config object.  Subclasses overriding this method should verify that
    364      * the given parameter is of a class that contains a property it is trying
    365      * to inherit:</p>
    366      * <pre>
    367      * if (config instanceof MyCustomFormPropertyConfig) {
    368      *     MyCustomFormPropertyConfig myConfig =
    369      *         (MyCustomFormPropertyConfig) config;
    370      *
    371      *     if (getMyCustomProp() == null) {
    372      *         setMyCustomProp(myConfig.getMyCustomProp());
    373      *     }
    374      * }
    375      * </pre>
    376      *
    377      * @param config The object that this instance will be inheriting its
    378      *               values from.
    379      */
    380     public void inheritFrom(FormPropertyConfig config)
    381         throws IllegalAccessException, InvocationTargetException,
    382             InstantiationException, ClassNotFoundException {
    383         if (configured) {
    384             throw new IllegalStateException("Configuration is frozen");
    385         }
    386 
    387         if (getInitial() == null) {
    388             setInitial(config.getInitial());
    389         }
    390 
    391         if (getName() == null) {
    392             setName(config.getName());
    393         }
    394 
    395         if (getSize() == 0) {
    396             setSize(config.getSize());
    397         }
    398 
    399         if (getType() == null) {
    400             setType(config.getType());
    401         }
    402 
    403         inheritProperties(config);
    404     }
    405 
    406     /**
    407      * Return a String representation of this object.
    408      */
    409     public String toString() {
    410         StringBuffer sb = new StringBuffer("FormPropertyConfig[");
    411 
    412         sb.append("name=");
    413         sb.append(this.name);
    414         sb.append(",type=");
    415         sb.append(this.type);
    416         sb.append(",initial=");
    417         sb.append(this.initial);
    418         sb.append(",reset=");
    419         sb.append(this.reset);
    420         sb.append("]");
    421 
    422         return (sb.toString());
    423     }
    424 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
