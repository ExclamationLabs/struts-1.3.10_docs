[View Javadoc](../../../../../apidocs/org/apache/struts/validator/BeanValidatorForm.html.md)


    1   /*
    2    * $Id: BeanValidatorForm.java 472728 2006-11-09 01:10:58Z niallp $
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
    21  package org.apache.struts.validator;
    22  
    23  import org.apache.commons.beanutils.ConvertUtils;
    24  import org.apache.commons.beanutils.DynaBean;
    25  import org.apache.commons.beanutils.DynaClass;
    26  import org.apache.commons.beanutils.WrapDynaBean;
    27  import org.apache.commons.logging.Log;
    28  import org.apache.commons.logging.LogFactory;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.config.FormBeanConfig;
    31  
    32  import javax.servlet.http.HttpServletRequest;
    33  
    34  import java.io.Serializable;
    35  
    36  import java.lang.reflect.Array;
    37  
    38  import java.util.List;
    39  import java.util.Map;
    40  
    41  /**
    42   * <p>Struts <i>validator</i> <code>ActionForm</code> backed by either a
    43   * <code>DynaBean</code> or POJO JavaBean.</p>
    44   *
    45   * <p>Passing a POJO JavaBean to the constructor will automatically create an
    46   * associated <code>WrapDynaBean</code>. One use for this would be to migrate
    47   * <i>view</i> objects from an existing system which, for the usual reasons,
    48   * can't be changed to extend <ActionForm</code>.</p>
    49   *
    50   * <p>This form is based on the standard struts <code>ValidatorForm</code> for
    51   * use with the <i>Validator</i> framework and validates either using the
    52   * <i>name</i> from the Struts <code>ActionMapping</code> or the
    53   * <code>ActionMapping</code>'s path depending on whether
    54   * <code>pathValidation</code> is <code>true</code> or
    55   * <code>false</code>.</p>
    56   *
    57   * <p><b>Note</b>: WrapDynaBean is NOT serializable.  If you use this class
    58   * with a WrapDynaBean (as described above), you should not store your form in
    59   * session scope.</p>
    60   */
    61  public class BeanValidatorForm extends ValidatorForm implements DynaBean,
    62      Serializable {
    63      /**
    64       * Commons Logging
    65       */
    66      protected static Log logger = LogFactory.getLog(BeanValidatorForm.class);
    67  
    68      /**
    69       * The <code>DynaBean</code> that this ActionForm is backed by.
    70       */
    71      protected DynaBean dynaBean;
    72  
    73      /**
    74       * Indicates whether the ActionMapping's path should be used for the
    75       * validation key.
    76       */
    77      protected boolean pathValidation = false;
    78  
    79      /**
    80       * The name used to identify the ActionForm in the struts-config.xml
    81       */
    82      private String strutsConfigFormName;
    83  
    84      // ------------------- Constructor ----------------------------------
    85  
    86      /**
    87       * Construct a new <code>BeanValidatorForm</code> with the specified
    88       * bean.
    89       */
    90      public BeanValidatorForm(Object bean) {
    91          if (bean instanceof DynaBean) {
    92              dynaBean = (DynaBean) bean;
    93          } else {
    94              dynaBean = new WrapDynaBean(bean);
    95          }
    96      }
    97  
    98      // ------------------- Protected Methods ----------------------------------
    99  
    100     /**
    101      * <p>Set whether this form should validate based on the
    102      * <code>ActionMapping</code>'s path.</p>
    103      */
    104     protected void setPathValidation(boolean pathValidation) {
    105         this.pathValidation = pathValidation;
    106     }
    107 
    108     /**
    109      * <p>Indicates whether this form should validate based on the
    110      * <code>ActionMapping</code>'s path.</p>
    111      */
    112     protected boolean isPathValidation() {
    113         return pathValidation;
    114     }
    115 
    116     // ------------------- Public Methods ----------------------------------
    117 
    118     /**
    119      * <p>Perform intialization of the ActionForm.</p>
    120      * <p>This method is called when the form is created.</p>
    121      *
    122      * @since Struts 1.3.6
    123      */
    124     public void initialize(FormBeanConfig formBeanConfig) {
    125         strutsConfigFormName = formBeanConfig.getName();
    126     }
    127 
    128     /**
    129      * Return name used to identify the ActionForm in the
    130      * struts-config.xml.
    131      *
    132      * @since Struts 1.3.6
    133      */
    134     public String getStrutsConfigFormName() {
    135         return strutsConfigFormName;
    136     }
    137 
    138     /**
    139      * <p>Return the <code>DynaBean</code> that this <code>ActionForm</code>
    140      * is backed by.</p>
    141      */
    142     public DynaBean getDynaBean() {
    143         return dynaBean;
    144     }
    145 
    146     /**
    147      * <p>Return the <code>Bean</code> that this <code>ActionForm</code> is
    148      * backed by.</p>
    149      *
    150      * <p>If the <code>DynaBean</code> is a <code>WrapDynaBean</code> type
    151      * then this method returns the 'Wrapped' POJO bean associated with it. If
    152      * you require the actual <code>WrapDynaBean</code> then use the
    153      * <code>getDynaBean()</code> method.</p>
    154      */
    155     public Object getInstance() {
    156         if (dynaBean instanceof WrapDynaBean) {
    157             return ((WrapDynaBean) dynaBean).getInstance();
    158         }
    159 
    160         return dynaBean;
    161     }
    162 
    163     /**
    164      * <p>Return the size of an indexed or mapped property.</p>
    165      */
    166     public int size(String name) {
    167         Object value = dynaBean.get(name);
    168 
    169         if (value == null) {
    170             return 0;
    171         }
    172 
    173         if (value instanceof Map) {
    174             return ((Map) value).size();
    175         }
    176 
    177         if (value instanceof List) {
    178             return ((List) value).size();
    179         }
    180 
    181         if ((value.getClass().isArray())) {
    182             return Array.getLength(value);
    183         }
    184 
    185         return 0;
    186     }
    187 
    188     // ------------------- ValidatorForm Methods ----------------------------------
    189 
    190     /**
    191      * Returns the Validation key
    192      *
    193      * @param mapping The mapping used to select this instance
    194      * @param request The servlet request we are processing
    195      * @return validation key to use
    196      */
    197     public String getValidationKey(ActionMapping mapping,
    198         HttpServletRequest request) {
    199         String validationKey = null;
    200 
    201         if (isPathValidation()) {
    202             // Get the path replacing any slashes by underscore
    203             validationKey = mapping.getPath();
    204 
    205             // Remove any leading slash
    206             if (validationKey.charAt(0) == '/') {
    207                 validationKey = validationKey.substring(1);
    208             }
    209 
    210             // Replace any slashes by underscore
    211             if (validationKey.indexOf("/") > 0) {
    212                 validationKey = validationKey.replace('/', '_');
    213             }
    214         } else {
    215             validationKey = mapping.getAttribute();
    216         }
    217 
    218         if (logger.isDebugEnabled()) {
    219             logger.debug("Validating ActionForm '" + mapping.getName()
    220                 + "' using key '" + validationKey + "' for mapping '"
    221                 + mapping.getPath() + "'");
    222         }
    223 
    224         return validationKey;
    225     }
    226 
    227     // ------------------- DynaBean Methods ----------------------------------
    228 
    229     /**
    230      * Return the <code>DynaClass</code> instance that describes the set of
    231      * properties available for this DynaBean.
    232      */
    233     public DynaClass getDynaClass() {
    234         return dynaBean.getDynaClass();
    235     }
    236 
    237     /**
    238      * Return the value of a simple property with the specified name.
    239      *
    240      * @param name Name of the property whose value is to be retrieved
    241      */
    242     public Object get(String name) {
    243         return dynaBean.get(name);
    244     }
    245 
    246     /**
    247      * Return the value of an indexed property with the specified name.
    248      *
    249      * @param name  Name of the property whose value is to be retrieved
    250      * @param index Index of the value to be retrieved
    251      */
    252     public Object get(String name, int index) {
    253         return dynaBean.get(name, index);
    254     }
    255 
    256     /**
    257      * Return the value of a mapped property with the specified name, or
    258      * <code>null</code> if there is no value for the specified key.
    259      *
    260      * @param name Name of the property whose value is to be retrieved
    261      * @param key  Key of the value to be retrieved
    262      */
    263     public Object get(String name, String key) {
    264         return dynaBean.get(name, key);
    265     }
    266 
    267     /**
    268      * Set the value of a simple property with the specified name.
    269      *
    270      * @param name  Name of the property whose value is to be set
    271      * @param value Value to which this property is to be set
    272      */
    273     public void set(String name, Object value) {
    274         // Set the page number (for validator)
    275         if ("page".equals(name)) {
    276             if (value == null) {
    277                 page = 0;
    278             } else if (value instanceof Integer) {
    279                 page = ((Integer) value).intValue();
    280             } else {
    281                 try {
    282                     page =
    283                         ((Integer) ConvertUtils.convert(value.toString(),
    284                             Integer.class)).intValue();
    285                 } catch (Exception ignore) {
    286                     page = 0;
    287                 }
    288             }
    289         }
    290 
    291         dynaBean.set(name, value);
    292     }
    293 
    294     /**
    295      * Set the value of an indexed property with the specified name.
    296      *
    297      * @param name  Name of the property whose value is to be set
    298      * @param index Index of the property to be set
    299      * @param value Value to which this property is to be set
    300      */
    301     public void set(String name, int index, Object value) {
    302         dynaBean.set(name, index, value);
    303     }
    304 
    305     /**
    306      * Set the value of a mapped property with the specified name.
    307      *
    308      * @param name  Name of the property whose value is to be set
    309      * @param key   Key of the property to be set
    310      * @param value Value to which this property is to be set
    311      */
    312     public void set(String name, String key, Object value) {
    313         dynaBean.set(name, key, value);
    314     }
    315 
    316     /**
    317      * Does the specified mapped property contain a value for the specified
    318      * key value?
    319      *
    320      * @param name Name of the property to check
    321      * @param key  Name of the key to check
    322      */
    323     public boolean contains(String name, String key) {
    324         return dynaBean.contains(name, key);
    325     }
    326 
    327     /**
    328      * Remove any existing value for the specified key on the specified mapped
    329      * property.
    330      *
    331      * @param name Name of the property for which a value is to be removed
    332      * @param key  Key of the value to be removed
    333      */
    334     public void remove(String name, String key) {
    335         dynaBean.remove(name, key);
    336     }
    337 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
