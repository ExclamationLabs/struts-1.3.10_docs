[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/application/PropertyResolverImpl.html.md)


    1   /*
    2    * $Id: PropertyResolverImpl.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.faces.application;
    23  
    24  
    25  import java.util.Map;
    26  
    27  import javax.faces.el.PropertyNotFoundException;
    28  import javax.faces.el.PropertyResolver;
    29  
    30  import org.apache.commons.beanutils.DynaBean;
    31  import org.apache.commons.beanutils.DynaProperty;
    32  import org.apache.commons.logging.Log;
    33  import org.apache.commons.logging.LogFactory;
    34  import org.apache.struts.action.DynaActionForm;
    35  
    36  
    37  
    38  /**
    39   * <p>Custom <code>PropertyResolver</code> implementation that adds support
    40   * for <code>DynaBean</code> property access to the facilities of the default
    41   * <code>PropertyResolver</code> provided by JavaServer Faces.</p>
    42   *
    43   * <p>This class implements the following specific rules:</p>
    44   * <ul>
    45   * <li>Indexed variants of each call are directly passed through to the
    46   *     <code>PropertyResolver</code> instance that we are wrapping.</li>
    47   * <li>If the specified base object is an instance of
    48   *     <code>DynaActionForm</code>, and the requested property name is
    49   *     <code>map</code>, maintain compatibility with the way that JSP and
    50   *     JSTL expressions can access this property:
    51   *     <ul>
    52   *     <li><code>getValue()</code> will return the result of calling
    53   *         <code>getMap()</code> on the base object.</li>
    54   *     <li><code>setValue()</code> will throw an exception, because the
    55   *         map of property values is a read-only property of the
    56   *         <code>DynaActionForm</code> class.</li>
    57   *     <li><code>isReadOnly()</code> returns <code>true</code>.</li>
    58   *     <li><code>getType()</code> returns the <code>Class</code> object
    59   *         for <code>java.util.Map</code>.</li>
    60   *     </ul></li>
    61   * <li>If the specified base object is an instance of
    62   *     <code>DynaBean</code>, provide access to its named properties
    63   *     as follows:
    64   *     <ul>
    65   *     <li><code>getValue()</code> will return the result of calling
    66   *         <code>get()</code> on the base object.</li>
    67   *     <li><code>setValue()</code> will call <code>set()</code>
    68   *         on the base object.</li>
    69   *     <li><code>isReadOnly()</code> returns <code>false</code> (because
    70   *         the DynaBean APIs provide no mechanism to make this determination,
    71   *         but most implementations will provide mutable properties).</li>
    72   *     <li><code>getType()</code> returns the <code>Class</code> object
    73   *         for the underlying dynamic property.</li>
    74   *     </ul></li>
    75   * <li>Named variant calls with any other type of base object are
    76   *     passed through to the <code>PropertyResolver</code> that we
    77   *     are wrapping.</li>
    78   * </ul>
    79   *
    80   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    81   */
    82  
    83  public class PropertyResolverImpl extends PropertyResolver {
    84  
    85  
    86      // ------------------------------------------------------------ Constructor
    87  
    88  
    89      /**
    90       * <p>Construct a new <code>PropertyResolver</code> instance, wrapping the
    91       * specified instance using the Decorator pattern such that this class need
    92       * implement only the new functionality it supports, and not need to
    93       * re-implement the basic facilities.
    94       *
    95       * @param resolver The original resolver to be wrapped
    96       *
    97       * @exception NullPointerException if <code>resolver</code>
    98       *  is <code>null</code>
    99       */
    100     public PropertyResolverImpl(PropertyResolver resolver) {
    101 
    102         if (resolver == null) {
    103             throw new NullPointerException();
    104         }
    105         if (log.isDebugEnabled()) {
    106             log.debug("Creating new instance, wrapping resolver " +
    107                       resolver);
    108         }
    109         this.resolver = resolver;
    110 
    111     }
    112 
    113 
    114     // ----------------------------------------------------- Instance Variables
    115 
    116 
    117     /**
    118      * <p>The <code>Log</code> instance for this class.</p>
    119      */
    120     private static final Log log =
    121         LogFactory.getLog(PropertyResolverImpl.class);
    122 
    123 
    124     /**
    125      * <p>The <code>PropertyResolver</code> instance that we are wrapping,
    126      * which will be used to perform operations on beans that are not
    127      * recognized by this class.</p>
    128      */
    129     private PropertyResolver resolver = null;
    130 
    131 
    132     // ----------------------------------------------- PropertyResolver Methods
    133 
    134 
    135     /**
    136      * <p>Return the value of the property with the specified name from
    137      * the specified base object.</p>
    138      *
    139      * @param base The base object whose property value is to be returned
    140      * @param name Name of the property to be returned
    141      *
    142      * @exception NullPointerException if <code>base</code> or
    143      *  <code>name</code> is <code>null</code>
    144      * @exception PropertyNotFoundException if the specified property name
    145      *  does not exist, or is not readable
    146      */
    147     public Object getValue(Object base, Object name)
    148         throws PropertyNotFoundException {
    149 
    150         if ((base == null) || (name == null)) {
    151             throw new NullPointerException();
    152         } else if ((base instanceof DynaActionForm) &&
    153                    ("map".equals(name))) {
    154             if (log.isTraceEnabled()) {
    155                 log.trace("Returning property map for DynaActionForm " + base
    156                           + "'");
    157             }
    158             return (((DynaActionForm) base).getMap());
    159         } else if (base instanceof DynaBean) {
    160             if (getDynaProperty((DynaBean) base, name.toString()) == null) {
    161                 throw new PropertyNotFoundException(name.toString());
    162             }
    163             Object value = ((DynaBean) base).get(name.toString());
    164             if (log.isTraceEnabled()) {
    165                 log.trace("Returning dynamic property '" + name +
    166                           "' for DynaBean '" + base + "' value '" +
    167                           value + "'");
    168             }
    169             return (value);
    170         } else {
    171             Object value = resolver.getValue(base, name);
    172             if (log.isTraceEnabled()) {
    173                 log.trace("Delegating get of property '" + name +
    174                           "' for bean '" + base + "' value '" +
    175                           value + "'");
    176             }
    177             return (value);
    178         }
    179 
    180     }
    181 
    182 
    183     /**
    184      * <p>Return the value at the specified index of the specified
    185      * base object.</p>
    186      *
    187      * @param base The base object whose property value is to be returned
    188      * @param index Index of the value to return
    189      *
    190      * @exception IndexOutOfBoundsException if thrown by the underlying
    191      *  access to the base object
    192      * @exception NullPointerException if <code>base</code>
    193      *  is <code>null</code>
    194      * @exception PropertyNotFoundException if some other exception occurs
    195      */
    196     public Object getValue(Object base, int index)
    197         throws PropertyNotFoundException {
    198 
    199         return (resolver.getValue(base, index));
    200 
    201     }
    202 
    203 
    204     /**
    205      * <p>Set the specified value of the property with the specified name on
    206      * the specified base object.</p>
    207      *
    208      * @param base The base object whose property value is to be set
    209      * @param name Name of the property to be set
    210      * @param value Value of the property to be set
    211      *
    212      * @exception NullPointerException if <code>base</code> or
    213      *  <code>name</code> is <code>null</code>
    214      * @exception PropertyNotFoundException if the specified property name
    215      *  does not exist, or is not writeable
    216      */
    217     public void setValue(Object base, Object name, Object value)
    218         throws PropertyNotFoundException {
    219 
    220         if ((base == null) || (name == null)) {
    221             throw new NullPointerException();
    222         } else if ((base instanceof DynaActionForm) &&
    223                    ("map".equals(name))) {
    224             throw new PropertyNotFoundException(name.toString());
    225         } else if (base instanceof DynaBean) {
    226             if (log.isTraceEnabled()) {
    227                 log.trace("setting dynamic property '" + name +
    228                           "' for DynaBean '" + base +
    229                           "' to '" + value + "'");
    230             }
    231             if (getDynaProperty((DynaBean) base, name.toString()) == null) {
    232                 throw new PropertyNotFoundException(name.toString());
    233             }
    234             ((DynaBean) base).set(name.toString(), value);
    235         } else {
    236             if (log.isTraceEnabled()) {
    237                 log.trace("Delegating set of property '" + name +
    238                           "' for bean '" + base + "' to value '" +
    239                           value + "'");
    240             }
    241             resolver.setValue(base, name, value);
    242         }
    243 
    244     }
    245 
    246 
    247     /**
    248      * <p>Set the value at the specified index of the specified
    249      * base object.</p>
    250      *
    251      * @param base The base object whose property value is to be set
    252      * @param index Index of the value to set
    253      * @param value Value to be set
    254      *
    255      * @exception IndexOutOfBoundsException if thrown by the underlying
    256      *  access to the base object
    257      * @exception NullPointerException if <code>base</code>
    258      *  is <code>null</code>
    259      * @exception PropertyNotFoundException if some other exception occurs
    260      */
    261     public void setValue(Object base, int index, Object value)
    262         throws PropertyNotFoundException {
    263 
    264         resolver.setValue(base, index, value);
    265 
    266     }
    267 
    268 
    269     /**
    270      * <p>Return <code>true</code> if the specified property of the specified
    271      * base object is known to be immutable; otherwise, return
    272      * <code>false</code>.</p>
    273      *
    274      * @param base The base object whose property is to analyzed
    275      * @param name Name of the property to be analyzed
    276      *
    277      * @exception NullPointerException if <code>base</code> or
    278      *  <code>name</code> is <code>null</code>
    279      * @exception PropertyNotFoundException if the specified property name
    280      *  does not exist
    281      */
    282     public boolean isReadOnly(Object base, Object name)
    283         throws PropertyNotFoundException {
    284 
    285         if ((base == null) || (name == null)) {
    286             throw new NullPointerException();
    287         } else if ((base instanceof DynaActionForm) &&
    288                    ("map".equals(name))) {
    289             return (true);
    290         } else if (base instanceof DynaBean) {
    291             if (getDynaProperty((DynaBean) base, name.toString()) == null) {
    292                 throw new PropertyNotFoundException(name.toString());
    293             }
    294             return (false);
    295         } else {
    296             return (resolver.isReadOnly(base, name.toString()));
    297         }
    298 
    299     }
    300 
    301 
    302     /**
    303      * <p>Return <code>true</code> if the value at the specified index of
    304      * the specified base object is known to be immutable; otherwise,
    305      * return <code>false</code>.</p>
    306      *
    307      * @param base The base object whose property is to analyzed
    308      * @param index Index of the value whose type is to be returned
    309      *
    310      * @exception IndexOutOfBoundsException if thrown by the underlying
    311      *  accessed to the indexed property
    312      * @exception NullPointerException if <code>base</code>
    313      *  is <code>null</code>
    314      * @exception PropertyNotFoundException if some other exception occurs
    315      */
    316     public boolean isReadOnly(Object base, int index)
    317         throws PropertyNotFoundException {
    318 
    319         return (resolver.isReadOnly(base, index));
    320 
    321     }
    322 
    323 
    324     /**
    325      * <p>Return the <code>java.lang.Class</code> representing the type of
    326      * the specified property of the specified base object, if it can be
    327      * determined; otherwise return <code>null</code>.</p>
    328      *
    329      * @param base The base object whose property is to analyzed
    330      * @param name Name of the property to be analyzed
    331      *
    332      * @exception NullPointerException if <code>base</code> or
    333      *  <code>name</code> is <code>null</code>
    334      * @exception PropertyNotFoundException if the specified property name
    335      *  does not exist
    336      */
    337     public Class getType(Object base, Object name)
    338         throws PropertyNotFoundException {
    339 
    340         if ((base == null) || (name == null)) {
    341             throw new NullPointerException();
    342         } else if ((base instanceof DynaActionForm) &&
    343                    ("map".equals(name))) {
    344             return (Map.class);
    345         } else if (base instanceof DynaBean) {
    346             DynaProperty dynaProperty =
    347                 getDynaProperty((DynaBean) base, name.toString());
    348             if (dynaProperty != null) {
    349                 return (dynaProperty.getType());
    350             } else {
    351                 throw new PropertyNotFoundException(name.toString());
    352             }
    353         } else {
    354             return (resolver.getType(base, name));
    355         }
    356     }
    357 
    358 
    359     /**
    360      * <p>Return the <code>java.lang.Class</code> representing the type of
    361      * value at the specified index of the specified base object, or
    362      * <code>null</code> if this value is <code>null</code>.</p>
    363      *
    364      * @param base The base object whose property is to analyzed
    365      * @param index Index of the value whose type is to be returned
    366      *
    367      * @exception IndexOutOfBoundsException if thrown by the underlying
    368      *  accessed to the indexed property
    369      * @exception NullPointerException if <code>base</code>
    370      *  is <code>null</code>
    371      * @exception PropertyNotFoundException if some other exception occurs
    372      */
    373     public Class getType(Object base, int index)
    374         throws PropertyNotFoundException {
    375 
    376         return (resolver.getType(base, index));
    377 
    378     }
    379 
    380 
    381     // -------------------------------------------------------- Private Methods
    382 
    383 
    384     /**
    385      * <p>Return the <code>DynaProperty</code> describing the specified
    386      * property of the specified <code>DynaBean</code>, or <code>null</code>
    387      * if there is no such property defined on the underlying
    388      * <code>DynaClass</code>.</p>
    389      *
    390      * @param bean <code>DynaBean</code> to be checked
    391      * @param name Name of the property to be checked
    392      */
    393     private DynaProperty getDynaProperty(DynaBean bean, String name)
    394         throws PropertyNotFoundException {
    395 
    396         DynaProperty dynaProperty = null;
    397         try {
    398             dynaProperty = bean.getDynaClass().getDynaProperty(name);
    399         } catch (IllegalArgumentException e) {
    400             ;
    401         }
    402         return (dynaProperty);
    403 
    404     }
    405 
    406 
    407 
    408 
    409 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
