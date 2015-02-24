[View Javadoc](../../../../../apidocs/org/apache/struts/action/DynaActionFormClass.html.md)


    1   /*
    2    * $Id: DynaActionFormClass.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.beanutils.DynaBean;
    24  import org.apache.commons.beanutils.DynaClass;
    25  import org.apache.commons.beanutils.DynaProperty;
    26  import org.apache.struts.config.FormBeanConfig;
    27  import org.apache.struts.config.FormPropertyConfig;
    28  import org.apache.struts.util.RequestUtils;
    29  
    30  import java.io.Serializable;
    31  
    32  import java.util.HashMap;
    33  
    34  /**
    35   * <p>Implementation of <code>DynaClass</code> for <code>DynaActionForm</code>
    36   * classes that allow developers to define ActionForms without having to
    37   * individually code all of the classes. <strong>NOTE</strong> - This class is
    38   * only used in the internal implementation of dynamic action form beans.
    39   * Application developers never need to consult this documentation.</p>
    40   *
    41   * @version $Rev: 471754 $ $Date: 2006-01-17 07:26:20 -0500 (Tue, 17 Jan 2006)
    42   *          $
    43   * @since Struts 1.1
    44   */
    45  public class DynaActionFormClass implements DynaClass, Serializable {
    46      // ----------------------------------------------------- Instance Variables
    47  
    48      /**
    49       * <p>The <code>DynaActionForm</code> implementation <code>Class</code>
    50       * which we will use to create new bean instances.</p>
    51       */
    52      protected transient Class beanClass = null;
    53  
    54      /**
    55       * <p>The form bean configuration information for this class.</p>
    56       */
    57      protected FormBeanConfig config = null;
    58  
    59      /**
    60       * <p>The "dynamic class name" for this <code>DynaClass</code>.</p>
    61       */
    62      protected String name = null;
    63  
    64      /**
    65       * <p>The set of dynamic properties that are part of this DynaClass.</p>
    66       */
    67      protected DynaProperty[] properties = null;
    68  
    69      /**
    70       * <p>The set of dynamic properties that are part of this
    71       * <code>DynaClass</code>, keyed by the property name.  Individual
    72       * descriptor instances will be the same instances as those in the
    73       * <code>properties</code> list.
    74       */
    75      protected HashMap propertiesMap = new HashMap();
    76  
    77      // ----------------------------------------------------------- Constructors
    78  
    79      /**
    80       * <p>Construct a new <code>DynaActionFormClass</code> for the specified
    81       * form bean configuration.  This constructor is private;
    82       * <code>DynaActionFormClass</code> instances will be created as needed
    83       * via calls to the static <code>createDynaActionFormClass()</code>
    84       * method.</p>
    85       *
    86       * @param config The FormBeanConfig instance describing the properties of
    87       *               the bean to be created
    88       * @throws IllegalArgumentException if the bean implementation class
    89       *                                  specified in the configuration is not
    90       *                                  DynaActionForm (or a subclass of
    91       *                                  DynaActionForm)
    92       */
    93      public DynaActionFormClass(FormBeanConfig config) {
    94          introspect(config);
    95      }
    96  
    97      // ------------------------------------------------------ DynaClass Methods
    98  
    99      /**
    100      * <p>Return the name of this <code>DynaClass</code> (analogous to the
    101      * <code>getName()</code> method of <code>java.lang.Class</code>, which
    102      * allows the same <code>DynaClass</code> implementation class to support
    103      * different dynamic classes, with different sets of properties.
    104      *
    105      * @return The name of this <code>DynaClass</code>.
    106      */
    107     public String getName() {
    108         return (this.name);
    109     }
    110 
    111     /**
    112      * <p>Return a property descriptor for the specified property, if it
    113      * exists; otherwise, return <code>null</code>.</p>
    114      *
    115      * @param name Name of the dynamic property for which a descriptor is
    116      *             requested
    117      * @return A property descriptor for the specified property.
    118      * @throws IllegalArgumentException if no property name is specified
    119      */
    120     public DynaProperty getDynaProperty(String name) {
    121         if (name == null) {
    122             throw new IllegalArgumentException("No property name specified");
    123         }
    124 
    125         return ((DynaProperty) propertiesMap.get(name));
    126     }
    127 
    128     /**
    129      * <p>Return an array of <code>DynaProperty</code>s for the properties
    130      * currently defined in this <code>DynaClass</code>.  If no properties are
    131      * defined, a zero-length array will be returned.</p>
    132      *
    133      * @return An array of property instances for this class.
    134      */
    135     public DynaProperty[] getDynaProperties() {
    136         return (properties);
    137 
    138         // :FIXME: Should we really be implementing
    139         // getBeanInfo instead, which returns property descriptors
    140         // and a bunch of other stuff?
    141     }
    142 
    143     /**
    144      * <p>Instantiate and return a new {@link DynaActionForm} instance,
    145      * associated with this <code>DynaActionFormClass</code>.  The properties
    146      * of the returned {@link DynaActionForm} will have been initialized to
    147      * the default values specified in the form bean configuration
    148      * information.</p>
    149      *
    150      * @return A new {@link DynaActionForm} instance.
    151      * @throws IllegalAccessException if the Class or the appropriate
    152      *                                constructor is not accessible
    153      * @throws InstantiationException if this Class represents an abstract
    154      *                                class, an array class, a primitive type,
    155      *                                or void; or if instantiation fails for
    156      *                                some other reason
    157      */
    158     public DynaBean newInstance()
    159         throws IllegalAccessException, InstantiationException {
    160         DynaActionForm dynaBean = (DynaActionForm) getBeanClass().newInstance();
    161 
    162         dynaBean.setDynaActionFormClass(this);
    163 
    164         FormPropertyConfig[] props = config.findFormPropertyConfigs();
    165 
    166         for (int i = 0; i < props.length; i++) {
    167             dynaBean.set(props[i].getName(), props[i].initial());
    168         }
    169 
    170         return (dynaBean);
    171     }
    172 
    173     // --------------------------------------------------------- Public Methods
    174 
    175     /**
    176      * <p>Render a <code>String</code> representation of this object.</p>
    177      *
    178      * @return The string representation of this instance.
    179      */
    180     public String toString() {
    181         StringBuffer sb = new StringBuffer("DynaActionFormBean[name=");
    182 
    183         sb.append(name);
    184 
    185         DynaProperty[] props = getDynaProperties();
    186 
    187         if (props == null) {
    188             props = new DynaProperty[0];
    189         }
    190 
    191         for (int i = 0; i < props.length; i++) {
    192             sb.append(',');
    193             sb.append(props[i].getName());
    194             sb.append('/');
    195             sb.append(props[i].getType());
    196         }
    197 
    198         sb.append("]");
    199 
    200         return (sb.toString());
    201     }
    202 
    203     // --------------------------------------------------------- Static Methods
    204 
    205     /**
    206      * Return the <code>DynaActionFormClass</code> instance for the specified
    207      * form bean configuration instance.
    208      *
    209      * @param config The config for which the class should be created.
    210      * @return The instance for the specified form bean config.
    211      */
    212     public static DynaActionFormClass createDynaActionFormClass(
    213         FormBeanConfig config) {
    214         return config.getDynaActionFormClass();
    215     }
    216 
    217     // ------------------------------------------------------ Protected Methods
    218 
    219     /**
    220      * <p>Return the implementation class we are using to construct new
    221      * instances, re-introspecting our {@link FormBeanConfig} if necessary
    222      * (that is, after being deserialized, since <code>beanClass</code> is
    223      * marked transient).</p>
    224      *
    225      * @return The implementation class used to construct new instances.
    226      */
    227     protected Class getBeanClass() {
    228         if (beanClass == null) {
    229             introspect(config);
    230         }
    231 
    232         return (beanClass);
    233     }
    234 
    235     /**
    236      * <p>Introspect our form bean configuration to identify the supported
    237      * properties.</p>
    238      *
    239      * @param config The FormBeanConfig instance describing the properties of
    240      *               the bean to be created
    241      * @throws IllegalArgumentException if the bean implementation class
    242      *                                  specified in the configuration is not
    243      *                                  DynaActionForm (or a subclass of
    244      *                                  DynaActionForm)
    245      */
    246     protected void introspect(FormBeanConfig config) {
    247         this.config = config;
    248 
    249         // Validate the ActionFormBean implementation class
    250         try {
    251             beanClass = RequestUtils.applicationClass(config.getType());
    252         } catch (Throwable t) {
    253             throw new IllegalArgumentException(
    254                 "Cannot instantiate ActionFormBean class '" + config.getType()
    255                 + "': " + t);
    256         }
    257 
    258         if (!DynaActionForm.class.isAssignableFrom(beanClass)) {
    259             throw new IllegalArgumentException("Class '" + config.getType()
    260                 + "' is not a subclass of "
    261                 + "'org.apache.struts.action.DynaActionForm'");
    262         }
    263 
    264         // Set the name we will know ourselves by from the form bean name
    265         this.name = config.getName();
    266 
    267         // Look up the property descriptors for this bean class
    268         FormPropertyConfig[] descriptors = config.findFormPropertyConfigs();
    269 
    270         if (descriptors == null) {
    271             descriptors = new FormPropertyConfig[0];
    272         }
    273 
    274         // Create corresponding dynamic property definitions
    275         properties = new DynaProperty[descriptors.length];
    276 
    277         for (int i = 0; i < descriptors.length; i++) {
    278             properties[i] =
    279                 new DynaProperty(descriptors[i].getName(),
    280                     descriptors[i].getTypeClass());
    281             propertiesMap.put(properties[i].getName(), properties[i]);
    282         }
    283     }
    284 
    285     // -------------------------------------------------------- Private Methods
    286 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
