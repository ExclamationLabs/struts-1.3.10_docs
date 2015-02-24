[View Javadoc](../../../../../apidocs/org/apache/struts/config/FormBeanConfig.html.md)


    1   /*
    2    * $Id: FormBeanConfig.java 472728 2006-11-09 01:10:58Z niallp $
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
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.commons.beanutils.DynaBean;
    25  import org.apache.commons.beanutils.MutableDynaClass;
    26  import org.apache.commons.logging.Log;
    27  import org.apache.commons.logging.LogFactory;
    28  import org.apache.struts.action.ActionForm;
    29  import org.apache.struts.action.ActionServlet;
    30  import org.apache.struts.action.DynaActionForm;
    31  import org.apache.struts.action.DynaActionFormClass;
    32  import org.apache.struts.chain.commands.util.ClassUtils;
    33  import org.apache.struts.chain.contexts.ActionContext;
    34  import org.apache.struts.chain.contexts.ServletActionContext;
    35  import org.apache.struts.util.RequestUtils;
    36  import org.apache.struts.validator.BeanValidatorForm;
    37  
    38  import java.lang.reflect.InvocationTargetException;
    39  
    40  import java.util.HashMap;
    41  
    42  /**
    43   * <p>A JavaBean representing the configuration information of a
    44   * <code>&lt;form-bean&gt;</code> element in a Struts configuration file.<p>
    45   *
    46   * @version $Rev: 472728 $ $Date: 2006-01-17 07:26:20 -0500 (Tue, 17 Jan 2006)
    47   *          $
    48   * @since Struts 1.1
    49   */
    50  public class FormBeanConfig extends BaseConfig {
    51      private static final Log log = LogFactory.getLog(FormBeanConfig.class);
    52  
    53      // ----------------------------------------------------- Instance Variables
    54  
    55      /**
    56       * The set of FormProperty elements defining dynamic form properties for
    57       * this form bean, keyed by property name.
    58       */
    59      protected HashMap formProperties = new HashMap();
    60  
    61      /**
    62       * <p>The lockable object we can synchronize on when creating
    63       * DynaActionFormClass.</p>
    64       */
    65      protected String lock = "";
    66  
    67      // ------------------------------------------------------------- Properties
    68  
    69      /**
    70       * The DynaActionFormClass associated with a DynaActionForm.
    71       */
    72      protected transient DynaActionFormClass dynaActionFormClass;
    73  
    74      /**
    75       * Is the form bean class an instance of DynaActionForm with dynamic
    76       * properties?
    77       */
    78      protected boolean dynamic = false;
    79  
    80      /**
    81       * The name of the FormBeanConfig that this config inherits configuration
    82       * information from.
    83       */
    84      protected String inherit = null;
    85  
    86      /**
    87       * Have the inheritance values for this class been applied?
    88       */
    89      protected boolean extensionProcessed = false;
    90  
    91      /**
    92       * The unique identifier of this form bean, which is used to reference
    93       * this bean in <code>ActionMapping</code> instances as well as for the
    94       * name of the request or session attribute under which the corresponding
    95       * form bean instance is created or accessed.
    96       */
    97      protected String name = null;
    98  
    99      /**
    100      * The fully qualified Java class name of the implementation class to be
    101      * used or generated.
    102      */
    103     protected String type = null;
    104 
    105     /**
    106      * Is this DynaClass currently restricted (for DynaBeans with a
    107      * MutableDynaClass).
    108      */
    109     protected boolean restricted = false;
    110 
    111     /**
    112      * <p>Return the DynaActionFormClass associated with a
    113      * DynaActionForm.</p>
    114      *
    115      * @throws IllegalArgumentException if the ActionForm is not dynamic
    116      */
    117     public DynaActionFormClass getDynaActionFormClass() {
    118         if (dynamic == false) {
    119             throw new IllegalArgumentException("ActionForm is not dynamic");
    120         }
    121 
    122         synchronized (lock) {
    123             if (dynaActionFormClass == null) {
    124                 dynaActionFormClass = new DynaActionFormClass(this);
    125             }
    126         }
    127 
    128         return dynaActionFormClass;
    129     }
    130 
    131     public boolean getDynamic() {
    132         return (this.dynamic);
    133     }
    134 
    135     public String getExtends() {
    136         return (this.inherit);
    137     }
    138 
    139     public void setExtends(String extend) {
    140         throwIfConfigured();
    141         this.inherit = extend;
    142     }
    143 
    144     public boolean isExtensionProcessed() {
    145         return extensionProcessed;
    146     }
    147 
    148     public String getName() {
    149         return (this.name);
    150     }
    151 
    152     public void setName(String name) {
    153         throwIfConfigured();
    154         this.name = name;
    155     }
    156 
    157     public String getType() {
    158         return (this.type);
    159     }
    160 
    161     public void setType(String type) {
    162         throwIfConfigured();
    163         this.type = type;
    164 
    165         Class dynaBeanClass = DynaActionForm.class;
    166         Class formBeanClass = formBeanClass();
    167 
    168         if (formBeanClass != null) {
    169             if (dynaBeanClass.isAssignableFrom(formBeanClass)) {
    170                 this.dynamic = true;
    171             } else {
    172                 this.dynamic = false;
    173             }
    174         } else {
    175             this.dynamic = false;
    176         }
    177     }
    178 
    179     /**
    180      * <p>Indicates whether a MutableDynaClass is currently restricted.</p>
    181      * <p>If so, no changes to the existing registration of property names,
    182      * data types, readability, or writeability are allowed.</p>
    183      */
    184     public boolean isRestricted() {
    185         return restricted;
    186     }
    187 
    188     /**
    189      * <p>Set whether a MutableDynaClass is currently restricted.</p> <p>If
    190      * so, no changes to the existing registration of property names, data
    191      * types, readability, or writeability are allowed.</p>
    192      */
    193     public void setRestricted(boolean restricted) {
    194         this.restricted = restricted;
    195     }
    196 
    197     // ------------------------------------------------------ Protected Methods
    198 
    199     /**
    200      * <p>Traces the hierarchy of this object to check if any of the ancestors
    201      * is extending this instance.</p>
    202      *
    203      * @param moduleConfig The configuration for the module being configured.
    204      * @return true if circular inheritance was detected.
    205      */
    206     protected boolean checkCircularInheritance(ModuleConfig moduleConfig) {
    207         String ancestorName = getExtends();
    208 
    209         while (ancestorName != null) {
    210             // check if we have the same name as an ancestor
    211             if (getName().equals(ancestorName)) {
    212                 return true;
    213             }
    214 
    215             // get our ancestor's ancestor
    216             FormBeanConfig ancestor =
    217                 moduleConfig.findFormBeanConfig(ancestorName);
    218 
    219             ancestorName = ancestor.getExtends();
    220         }
    221 
    222         return false;
    223     }
    224 
    225     /**
    226      * <p>Compare the form properties of this bean with that of the given and
    227      * copy those that are not present.</p>
    228      *
    229      * @param config The form bean config to copy properties from.
    230      * @see #inheritFrom(FormBeanConfig)
    231      */
    232     protected void inheritFormProperties(FormBeanConfig config)
    233         throws ClassNotFoundException, IllegalAccessException,
    234             InstantiationException, InvocationTargetException {
    235         throwIfConfigured();
    236 
    237         // Inherit form property configs
    238         FormPropertyConfig[] baseFpcs = config.findFormPropertyConfigs();
    239 
    240         for (int i = 0; i < baseFpcs.length; i++) {
    241             FormPropertyConfig baseFpc = baseFpcs[i];
    242 
    243             // Do we have this prop?
    244             FormPropertyConfig prop =
    245                 this.findFormPropertyConfig(baseFpc.getName());
    246 
    247             if (prop == null) {
    248                 // We don't have this, so let's copy it
    249                 prop =
    250                     (FormPropertyConfig) RequestUtils.applicationInstance(baseFpc.getClass()
    251                                                                                  .getName());
    252 
    253                 BeanUtils.copyProperties(prop, baseFpc);
    254                 this.addFormPropertyConfig(prop);
    255                 prop.setProperties(baseFpc.copyProperties());
    256             }
    257         }
    258     }
    259 
    260     // --------------------------------------------------------- Public Methods
    261 
    262     /**
    263      * <p>Create and return an <code>ActionForm</code> instance appropriate to
    264      * the information in this <code>FormBeanConfig</code>.</p>
    265      *
    266      * <p>Although this method is not formally deprecated yet, where possible,
    267      * the form which accepts an <code>ActionContext</code> as an argument is
    268      * preferred, to help sever direct dependencies on the Servlet API.  As
    269      * the ActionContext becomes more familiar in Struts, this method will
    270      * almost certainly be deprecated.</p>
    271      *
    272      * @param servlet The action servlet
    273      * @return ActionForm instance
    274      * @throws IllegalAccessException if the Class or the appropriate
    275      *                                constructor is not accessible
    276      * @throws InstantiationException if this Class represents an abstract
    277      *                                class, an array class, a primitive type,
    278      *                                or void; or if instantiation fails for
    279      *                                some other reason
    280      */
    281     public ActionForm createActionForm(ActionServlet servlet)
    282         throws IllegalAccessException, InstantiationException {
    283         Object obj = null;
    284 
    285         // Create a new form bean instance
    286         if (getDynamic()) {
    287             obj = getDynaActionFormClass().newInstance();
    288         } else {
    289             obj = formBeanClass().newInstance();
    290         }
    291 
    292         ActionForm form = null;
    293 
    294         if (obj instanceof ActionForm) {
    295             form = (ActionForm) obj;
    296         } else {
    297             form = new BeanValidatorForm(obj);
    298         }
    299 
    300         form.setServlet(servlet);
    301 
    302         if (form instanceof DynaBean
    303             && ((DynaBean) form).getDynaClass() instanceof MutableDynaClass) {
    304             DynaBean dynaBean = (DynaBean) form;
    305             MutableDynaClass dynaClass =
    306                 (MutableDynaClass) dynaBean.getDynaClass();
    307 
    308             // Add properties
    309             dynaClass.setRestricted(false);
    310 
    311             FormPropertyConfig[] props = findFormPropertyConfigs();
    312 
    313             for (int i = 0; i < props.length; i++) {
    314                 dynaClass.add(props[i].getName(), props[i].getTypeClass());
    315                 dynaBean.set(props[i].getName(), props[i].initial());
    316             }
    317 
    318             dynaClass.setRestricted(isRestricted());
    319         }
    320 
    321         if (form instanceof BeanValidatorForm) {
    322             ((BeanValidatorForm)form).initialize(this);
    323         }
    324 
    325         return form;
    326     }
    327 
    328     /**
    329      * <p>Create and return an <code>ActionForm</code> instance appropriate to
    330      * the information in this <code>FormBeanConfig</code>.</p>
    331      * <p><b>NOTE:</b> If the given <code>ActionContext</code> is not of type
    332      * <code>ServletActionContext</code> (or a subclass), then the form which
    333      * is returned will have a null <code>servlet</code> property.  Some of
    334      * the subclasses of <code>ActionForm</code> included in Struts will later
    335      * throw a <code>NullPointerException</code> in this case. </p> <p>TODO:
    336      * Find a way to control this direct dependency on the Servlet API.</p>
    337      *
    338      * @param context The ActionContext.
    339      * @return ActionForm instance
    340      * @throws IllegalAccessException if the Class or the appropriate
    341      *                                constructor is not accessible
    342      * @throws InstantiationException if this Class represents an abstract
    343      *                                class, an array class, a primitive type,
    344      *                                or void; or if instantiation fails for
    345      *                                some other reason
    346      */
    347     public ActionForm createActionForm(ActionContext context)
    348         throws IllegalAccessException, InstantiationException {
    349         ActionServlet actionServlet = null;
    350 
    351         if (context instanceof ServletActionContext) {
    352             ServletActionContext saContext = (ServletActionContext) context;
    353 
    354             actionServlet = saContext.getActionServlet();
    355         }
    356 
    357         return createActionForm(actionServlet);
    358     }
    359 
    360     /**
    361      * <p>Checks if the given <code>ActionForm</code> instance is suitable for
    362      * use as an alternative to calling this <code>FormBeanConfig</code>
    363      * instance's <code>createActionForm</code> method.</p>
    364      *
    365      * @param form an existing form instance that may be reused.
    366      * @return true if the given form can be reused as the form for this
    367      *         config.
    368      */
    369     public boolean canReuse(ActionForm form) {
    370         if (form != null) {
    371             if (this.getDynamic()) {
    372                 String className = ((DynaBean) form).getDynaClass().getName();
    373 
    374                 if (className.equals(this.getName())) {
    375                     log.debug("Can reuse existing instance (dynamic)");
    376 
    377                     return (true);
    378                 }
    379             } else {
    380                 try {
    381                     // check if the form's class is compatible with the class
    382                     //      we're configured for
    383                     Class formClass = form.getClass();
    384 
    385                     if (form instanceof BeanValidatorForm) {
    386                         BeanValidatorForm beanValidatorForm =
    387                             (BeanValidatorForm) form;
    388 
    389                         if (beanValidatorForm.getInstance() instanceof DynaBean) {
    390                             String formName = beanValidatorForm.getStrutsConfigFormName();
    391                             if (getName().equals(formName)) {
    392                                 log.debug("Can reuse existing instance (BeanValidatorForm)");
    393                                 return true;
    394                             } else {
    395                                 return false;
    396                             }
    397                         }
    398                         formClass = beanValidatorForm.getInstance().getClass();
    399                     }
    400 
    401                     Class configClass =
    402                         ClassUtils.getApplicationClass(this.getType());
    403 
    404                     if (configClass.isAssignableFrom(formClass)) {
    405                         log.debug("Can reuse existing instance (non-dynamic)");
    406 
    407                         return (true);
    408                     }
    409                 } catch (Exception e) {
    410                     log.debug("Error testing existing instance for reusability; just create a new instance",
    411                         e);
    412                 }
    413             }
    414         }
    415 
    416         return false;
    417     }
    418 
    419     /**
    420      * Add a new <code>FormPropertyConfig</code> instance to the set
    421      * associated with this module.
    422      *
    423      * @param config The new configuration instance to be added
    424      * @throws IllegalArgumentException if this property name has already been
    425      *                                  defined
    426      */
    427     public void addFormPropertyConfig(FormPropertyConfig config) {
    428         throwIfConfigured();
    429 
    430         if (formProperties.containsKey(config.getName())) {
    431             throw new IllegalArgumentException("Property " + config.getName()
    432                 + " already defined");
    433         }
    434 
    435         formProperties.put(config.getName(), config);
    436     }
    437 
    438     /**
    439      * Return the form property configuration for the specified property name,
    440      * if any; otherwise return <code>null</code>.
    441      *
    442      * @param name Form property name to find a configuration for
    443      */
    444     public FormPropertyConfig findFormPropertyConfig(String name) {
    445         return ((FormPropertyConfig) formProperties.get(name));
    446     }
    447 
    448     /**
    449      * Return the form property configurations for this module.  If there are
    450      * none, a zero-length array is returned.
    451      */
    452     public FormPropertyConfig[] findFormPropertyConfigs() {
    453         FormPropertyConfig[] results =
    454             new FormPropertyConfig[formProperties.size()];
    455 
    456         return ((FormPropertyConfig[]) formProperties.values().toArray(results));
    457     }
    458 
    459     /**
    460      * Freeze the configuration of this component.
    461      */
    462     public void freeze() {
    463         super.freeze();
    464 
    465         FormPropertyConfig[] fpconfigs = findFormPropertyConfigs();
    466 
    467         for (int i = 0; i < fpconfigs.length; i++) {
    468             fpconfigs[i].freeze();
    469         }
    470     }
    471 
    472     /**
    473      * <p>Inherit values that have not been overridden from the provided
    474      * config object.  Subclasses overriding this method should verify that
    475      * the given parameter is of a class that contains a property it is trying
    476      * to inherit:</p>
    477      *
    478      * <pre>
    479      * if (config instanceof MyCustomConfig) {
    480      *     MyCustomConfig myConfig =
    481      *         (MyCustomConfig) config;
    482      *
    483      *     if (getMyCustomProp() == null) {
    484      *         setMyCustomProp(myConfig.getMyCustomProp());
    485      *     }
    486      * }
    487      * </pre>
    488      *
    489      * <p>If the given <code>config</code> is extending another object, those
    490      * extensions should be resolved before it's used as a parameter to this
    491      * method.</p>
    492      *
    493      * @param config The object that this instance will be inheriting its
    494      *               values from.
    495      * @see #processExtends(ModuleConfig)
    496      */
    497     public void inheritFrom(FormBeanConfig config)
    498         throws ClassNotFoundException, IllegalAccessException,
    499             InstantiationException, InvocationTargetException {
    500         throwIfConfigured();
    501 
    502         // Inherit values that have not been overridden
    503         if (getName() == null) {
    504             setName(config.getName());
    505         }
    506 
    507         if (!isRestricted()) {
    508             setRestricted(config.isRestricted());
    509         }
    510 
    511         if (getType() == null) {
    512             setType(config.getType());
    513         }
    514 
    515         inheritFormProperties(config);
    516         inheritProperties(config);
    517     }
    518 
    519     /**
    520      * <p>Inherit configuration information from the FormBeanConfig that this
    521      * instance is extending.  This method verifies that any form bean config
    522      * object that it inherits from has also had its processExtends() method
    523      * called.</p>
    524      *
    525      * @param moduleConfig The {@link ModuleConfig} that this bean is from.
    526      * @see #inheritFrom(FormBeanConfig)
    527      */
    528     public void processExtends(ModuleConfig moduleConfig)
    529         throws ClassNotFoundException, IllegalAccessException,
    530             InstantiationException, InvocationTargetException {
    531         if (configured) {
    532             throw new IllegalStateException("Configuration is frozen");
    533         }
    534 
    535         String ancestor = getExtends();
    536 
    537         if ((!extensionProcessed) && (ancestor != null)) {
    538             FormBeanConfig baseConfig =
    539                 moduleConfig.findFormBeanConfig(ancestor);
    540 
    541             if (baseConfig == null) {
    542                 throw new NullPointerException("Unable to find "
    543                     + "form bean '" + ancestor + "' to extend.");
    544             }
    545 
    546             // Check against circule inheritance and make sure the base config's
    547             //  own extends have been processed already
    548             if (checkCircularInheritance(moduleConfig)) {
    549                 throw new IllegalArgumentException(
    550                     "Circular inheritance detected for form bean " + getName());
    551             }
    552 
    553             // Make sure the ancestor's own extension has been processed.
    554             if (!baseConfig.isExtensionProcessed()) {
    555                 baseConfig.processExtends(moduleConfig);
    556             }
    557 
    558             // Copy values from the base config
    559             inheritFrom(baseConfig);
    560         }
    561 
    562         extensionProcessed = true;
    563     }
    564 
    565     /**
    566      * Remove the specified form property configuration instance.
    567      *
    568      * @param config FormPropertyConfig instance to be removed
    569      */
    570     public void removeFormPropertyConfig(FormPropertyConfig config) {
    571         if (configured) {
    572             throw new IllegalStateException("Configuration is frozen");
    573         }
    574 
    575         formProperties.remove(config.getName());
    576     }
    577 
    578     /**
    579      * Return a String representation of this object.
    580      */
    581     public String toString() {
    582         StringBuffer sb = new StringBuffer("FormBeanConfig[");
    583 
    584         sb.append("name=");
    585         sb.append(this.name);
    586         sb.append(",type=");
    587         sb.append(this.type);
    588         sb.append(",extends=");
    589         sb.append(this.inherit);
    590         sb.append("]");
    591 
    592         return (sb.toString());
    593     }
    594 
    595     // ------------------------------------------------------ Protected Methods
    596 
    597     /**
    598      * Return the <code>Class</code> instance for the form bean implementation
    599      * configured by this <code>FormBeanConfig</code> instance.  This method
    600      * uses the same algorithm as <code>RequestUtils.applicationClass()</code>
    601      * but is reproduced to avoid a runtime dependence.
    602      */
    603     protected Class formBeanClass() {
    604         ClassLoader classLoader =
    605             Thread.currentThread().getContextClassLoader();
    606 
    607         if (classLoader == null) {
    608             classLoader = this.getClass().getClassLoader();
    609         }
    610 
    611         try {
    612             return (classLoader.loadClass(getType()));
    613         } catch (Exception e) {
    614             return (null);
    615         }
    616     }
    617 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
