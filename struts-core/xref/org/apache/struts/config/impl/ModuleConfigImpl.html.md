[View Javadoc](../../../../../../apidocs/org/apache/struts/config/impl/ModuleConfigImpl.html.md)


    1   /*
    2    * $Id: ModuleConfigImpl.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.config.impl;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.config.ActionConfig;
    26  import org.apache.struts.config.ActionConfigMatcher;
    27  import org.apache.struts.config.BaseConfig;
    28  import org.apache.struts.config.ControllerConfig;
    29  import org.apache.struts.config.ExceptionConfig;
    30  import org.apache.struts.config.FormBeanConfig;
    31  import org.apache.struts.config.ForwardConfig;
    32  import org.apache.struts.config.MessageResourcesConfig;
    33  import org.apache.struts.config.ModuleConfig;
    34  import org.apache.struts.config.PlugInConfig;
    35  
    36  import java.io.Serializable;
    37  
    38  import java.util.ArrayList;
    39  import java.util.HashMap;
    40  import java.util.List;
    41  
    42  /**
    43   * <p>The collection of static configuration information that describes a
    44   * Struts-based module.  Multiple modules are identified by a <em>prefix</em>
    45   * at the beginning of the context relative portion of the request URI.  If no
    46   * module prefix can be matched, the default configuration (with a prefix
    47   * equal to a zero-length string) is selected, which is elegantly backwards
    48   * compatible with the previous Struts behavior that only supported one
    49   * module.</p>
    50   *
    51   * @version $Rev: 471754 $ $Date: 2005-12-31 03:57:16 -0500 (Sat, 31 Dec 2005)
    52   *          $
    53   * @since Struts 1.1
    54   */
    55  public class ModuleConfigImpl extends BaseConfig implements Serializable,
    56      ModuleConfig {
    57      /**
    58       * <p>Commons Logging instance. </p>
    59       */
    60      protected static Log log = LogFactory.getLog(ModuleConfigImpl.class);
    61  
    62      // ----------------------------------------------------- Instance Variables
    63      // Instance Variables at end to make comparing Interface and implementation easier.
    64  
    65      /**
    66       * <p>The set of action configurations for this module, if any, keyed by
    67       * the <code>path</code> property.</p>
    68       */
    69      protected HashMap actionConfigs = null;
    70  
    71      /**
    72       * <p>The set of action configuration for this module, if any, keyed by
    73       * the <code>actionId</code> property.</p>
    74       */
    75      protected HashMap actionConfigIds = null;
    76  
    77      /**
    78       * <p>The set of action configurations for this module, if any, listed in
    79       * the order in which they are added.</p>
    80       */
    81      protected List actionConfigList = null;
    82  
    83      /**
    84       * <p>The set of exception handling configurations for this module, if
    85       * any, keyed by the <code>type</code> property.</p>
    86       */
    87      protected HashMap exceptions = null;
    88  
    89      /**
    90       * <p>The set of form bean configurations for this module, if any, keyed
    91       * by the <code>name</code> property.</p>
    92       */
    93      protected HashMap formBeans = null;
    94  
    95      /**
    96       * <p>The set of global forward configurations for this module, if any,
    97       * keyed by the <code>name</code> property.</p>
    98       */
    99      protected HashMap forwards = null;
    100 
    101     /**
    102      * <p>The set of message resources configurations for this module, if any,
    103      * keyed by the <code>key</code> property.</p>
    104      */
    105     protected HashMap messageResources = null;
    106 
    107     /**
    108      * <p>The set of configured plug-in Actions for this module, if any, in
    109      * the order they were declared and configured.</p>
    110      */
    111     protected ArrayList plugIns = null;
    112 
    113     /**
    114      * <p>The controller configuration object for this module.</p>
    115      */
    116     protected ControllerConfig controllerConfig = null;
    117 
    118     /**
    119      * <p>The prefix of the context-relative portion of the request URI, used
    120      * to select this configuration versus others supported by the controller
    121      * servlet.  A configuration with a prefix of a zero-length String is the
    122      * default configuration for this web module.</p>
    123      */
    124     protected String prefix = null;
    125 
    126     /**
    127      * <p>The default class name to be used when creating action form bean
    128      * instances.</p>
    129      */
    130     protected String actionFormBeanClass =
    131         "org.apache.struts.action.ActionFormBean";
    132 
    133     /**
    134      * The default class name to be used when creating action mapping
    135      * instances.
    136      */
    137     protected String actionMappingClass =
    138         "org.apache.struts.action.ActionMapping";
    139 
    140     /**
    141      * The default class name to be used when creating action forward
    142      * instances.
    143      */
    144     protected String actionForwardClass =
    145         "org.apache.struts.action.ActionForward";
    146 
    147     /**
    148      * <p>Matches action config paths against compiled wildcard patterns</p>
    149      */
    150     protected ActionConfigMatcher matcher = null;
    151 
    152     /**
    153      * <p>Constructor for ModuleConfigImpl.  Assumes default
    154      * configuration.</p>
    155      *
    156      * @since Struts 1.2.8
    157      */
    158     public ModuleConfigImpl() {
    159         this("");
    160     }
    161 
    162     /**
    163      * <p>Construct an ModuleConfigImpl object according to the specified
    164      * parameter values.</p>
    165      *
    166      * @param prefix Context-relative URI prefix for this module
    167      */
    168     public ModuleConfigImpl(String prefix) {
    169         super();
    170         this.prefix = prefix;
    171         this.actionConfigs = new HashMap();
    172         this.actionConfigIds = new HashMap();
    173         this.actionConfigList = new ArrayList();
    174         this.actionFormBeanClass = "org.apache.struts.action.ActionFormBean";
    175         this.actionMappingClass = "org.apache.struts.action.ActionMapping";
    176         this.actionForwardClass = "org.apache.struts.action.ActionForward";
    177         this.configured = false;
    178         this.controllerConfig = null;
    179         this.exceptions = new HashMap();
    180         this.formBeans = new HashMap();
    181         this.forwards = new HashMap();
    182         this.messageResources = new HashMap();
    183         this.plugIns = new ArrayList();
    184     }
    185 
    186     // --------------------------------------------------------- Public Methods
    187 
    188     /**
    189      * </p> Has this module been completely configured yet.  Once this flag
    190      * has been set, any attempt to modify the configuration will return an
    191      * IllegalStateException.</p>
    192      */
    193     public boolean getConfigured() {
    194         return (this.configured);
    195     }
    196 
    197     /**
    198      * <p>The controller configuration object for this module.</p>
    199      */
    200     public ControllerConfig getControllerConfig() {
    201         if (this.controllerConfig == null) {
    202             this.controllerConfig = new ControllerConfig();
    203         }
    204 
    205         return (this.controllerConfig);
    206     }
    207 
    208     /**
    209      * <p>The controller configuration object for this module.</p>
    210      *
    211      * @param cc The controller configuration object for this module.
    212      */
    213     public void setControllerConfig(ControllerConfig cc) {
    214         throwIfConfigured();
    215         this.controllerConfig = cc;
    216     }
    217 
    218     /**
    219      * <p>The prefix of the context-relative portion of the request URI, used
    220      * to select this configuration versus others supported by the controller
    221      * servlet.  A configuration with a prefix of a zero-length String is the
    222      * default configuration for this web module.</p>
    223      */
    224     public String getPrefix() {
    225         return (this.prefix);
    226     }
    227 
    228     /**
    229      * <p>The prefix of the context-relative portion of the request URI, used
    230      * to select this configuration versus others supported by the controller
    231      * servlet.  A configuration with a prefix of a zero-length String is the
    232      * default configuration for this web module.</p>
    233      */
    234     public void setPrefix(String prefix) {
    235         throwIfConfigured();
    236         this.prefix = prefix;
    237     }
    238 
    239     /**
    240      * <p>The default class name to be used when creating action form bean
    241      * instances.</p>
    242      */
    243     public String getActionFormBeanClass() {
    244         return this.actionFormBeanClass;
    245     }
    246 
    247     /**
    248      * <p>The default class name to be used when creating action form bean
    249      * instances.</p>
    250      *
    251      * @param actionFormBeanClass default class name to be used when creating
    252      *                            action form bean instances.
    253      */
    254     public void setActionFormBeanClass(String actionFormBeanClass) {
    255         this.actionFormBeanClass = actionFormBeanClass;
    256     }
    257 
    258     /**
    259      * <p>The default class name to be used when creating action mapping
    260      * instances.</p>
    261      */
    262     public String getActionMappingClass() {
    263         return this.actionMappingClass;
    264     }
    265 
    266     /**
    267      * <p> The default class name to be used when creating action mapping
    268      * instances. </p>
    269      *
    270      * @param actionMappingClass default class name to be used when creating
    271      *                           action mapping instances.
    272      */
    273     public void setActionMappingClass(String actionMappingClass) {
    274         this.actionMappingClass = actionMappingClass;
    275     }
    276 
    277     /**
    278      * </p> Ad   d a new <code>ActionConfig</code> instance to the set
    279      * associated with this module. </p>
    280      *
    281      * @param config The new configuration instance to be added
    282      * @throws IllegalStateException if this module configuration has been
    283      *                               frozen
    284      */
    285     public void addActionConfig(ActionConfig config) {
    286         throwIfConfigured();
    287         config.setModuleConfig(this);
    288 
    289         String path = config.getPath();
    290         if (actionConfigs.containsKey(path)) {
    291             log.warn("Overriding ActionConfig of path " + path);
    292         }
    293 
    294         String actionId = config.getActionId();
    295         if ((actionId != null) && !actionId.equals("")) {
    296             if (actionConfigIds.containsKey(actionId)) {
    297                 if (log.isWarnEnabled()) {
    298                     ActionConfig otherConfig = (ActionConfig) actionConfigIds.get(actionId);
    299                     StringBuffer msg = new StringBuffer("Overriding actionId[");
    300                     msg.append(actionId);
    301                     msg.append("] for path[");
    302                     msg.append(otherConfig.getPath());
    303                     msg.append("] with path[");
    304                     msg.append(path);
    305                     msg.append("]");
    306                     log.warn(msg);
    307                 }
    308             }
    309             actionConfigIds.put(actionId, config);
    310         }
    311 
    312         actionConfigs.put(path, config);
    313         actionConfigList.add(config);
    314     }
    315 
    316     /**
    317      * <p> Add a new <code>ExceptionConfig</code> instance to the set
    318      * associated with this module. </p>
    319      *
    320      * @param config The new configuration instance to be added
    321      * @throws IllegalStateException if this module configuration has been
    322      *                               frozen
    323      */
    324     public void addExceptionConfig(ExceptionConfig config) {
    325         throwIfConfigured();
    326 
    327         String key = config.getType();
    328 
    329         if (exceptions.containsKey(key)) {
    330             log.warn("Overriding ExceptionConfig of type " + key);
    331         }
    332 
    333         exceptions.put(key, config);
    334     }
    335 
    336     /**
    337      * <p> Add a new <code>FormBeanConfig</code> instance to the set
    338      * associated with this module. </p>
    339      *
    340      * @param config The new configuration instance to be added
    341      * @throws IllegalStateException if this module configuration has been
    342      *                               frozen
    343      */
    344     public void addFormBeanConfig(FormBeanConfig config) {
    345         throwIfConfigured();
    346 
    347         String key = config.getName();
    348 
    349         if (formBeans.containsKey(key)) {
    350             log.warn("Overriding ActionForm of name " + key);
    351         }
    352 
    353         formBeans.put(key, config);
    354     }
    355 
    356     /**
    357      * <p> The default class name to be used when creating action forward
    358      * instances. </p>
    359      */
    360     public String getActionForwardClass() {
    361         return this.actionForwardClass;
    362     }
    363 
    364     /**
    365      * <p> The default class name to be used when creating action forward
    366      * instances. </p>
    367      *
    368      * @param actionForwardClass default class name to be used when creating
    369      *                           action forward instances.
    370      */
    371     public void setActionForwardClass(String actionForwardClass) {
    372         this.actionForwardClass = actionForwardClass;
    373     }
    374 
    375     /**
    376      * <p> Add a new <code>ForwardConfig</code> instance to the set of global
    377      * forwards associated with this module. </p>
    378      *
    379      * @param config The new configuration instance to be added
    380      * @throws IllegalStateException if this module configuration has been
    381      *                               frozen
    382      */
    383     public void addForwardConfig(ForwardConfig config) {
    384         throwIfConfigured();
    385 
    386         String key = config.getName();
    387 
    388         if (forwards.containsKey(key)) {
    389             log.warn("Overriding global ActionForward of name " + key);
    390         }
    391 
    392         forwards.put(key, config);
    393     }
    394 
    395     /**
    396      * <p> Add a new <code>MessageResourcesConfig</code> instance to the set
    397      * associated with this module. </p>
    398      *
    399      * @param config The new configuration instance to be added
    400      * @throws IllegalStateException if this module configuration has been
    401      *                               frozen
    402      */
    403     public void addMessageResourcesConfig(MessageResourcesConfig config) {
    404         throwIfConfigured();
    405 
    406         String key = config.getKey();
    407 
    408         if (messageResources.containsKey(key)) {
    409             log.warn("Overriding MessageResources bundle of key " + key);
    410         }
    411 
    412         messageResources.put(key, config);
    413     }
    414 
    415     /**
    416      * <p> Add a newly configured {@link org.apache.struts.config.PlugInConfig}
    417      * instance to the set of plug-in Actions for this module. </p>
    418      *
    419      * @param plugInConfig The new configuration instance to be added
    420      */
    421     public void addPlugInConfig(PlugInConfig plugInConfig) {
    422         throwIfConfigured();
    423         plugIns.add(plugInConfig);
    424     }
    425 
    426     /**
    427      * <p> Return the action configuration for the specified path, first
    428      * looking a direct match, then if none found, a wildcard pattern match;
    429      * otherwise return <code>null</code>. </p>
    430      *
    431      * @param path Path of the action configuration to return
    432      */
    433     public ActionConfig findActionConfig(String path) {
    434         ActionConfig config = (ActionConfig) actionConfigs.get(path);
    435 
    436         // If a direct match cannot be found, try to match action configs
    437         // containing wildcard patterns only if a matcher exists.
    438         if ((config == null) && (matcher != null)) {
    439             config = matcher.match(path);
    440         }
    441 
    442         return config;
    443     }
    444 
    445     /**
    446      * <p>Returns the action configuration for the specifed action
    447      * action identifier.</p>
    448      *
    449      * @param actionId the action identifier
    450      * @return the action config if found; otherwise <code>null</code>
    451      * @see ActionConfig#getActionId()
    452      * @since Struts 1.3.6
    453      */
    454     public ActionConfig findActionConfigId(String actionId) {
    455         if (actionId != null) {
    456             return (ActionConfig) this.actionConfigIds.get(actionId);
    457         }
    458         return null;
    459     }
    460 
    461     /**
    462      * <p> Return the action configurations for this module.  If there are
    463      * none, a zero-length array is returned. </p>
    464      */
    465     public ActionConfig[] findActionConfigs() {
    466         ActionConfig[] results = new ActionConfig[actionConfigList.size()];
    467 
    468         return ((ActionConfig[]) actionConfigList.toArray(results));
    469     }
    470 
    471     /**
    472      * <p> Return the exception configuration for the specified type, if any;
    473      * otherwise return <code>null</code>. </p>
    474      *
    475      * @param type Exception class name to find a configuration for
    476      */
    477     public ExceptionConfig findExceptionConfig(String type) {
    478         return ((ExceptionConfig) exceptions.get(type));
    479     }
    480 
    481     /**
    482      * <p>Find and return the <code>ExceptionConfig</code> instance defining
    483      * how <code>Exceptions</code> of the specified type should be handled.
    484      *
    485      * <p>In original Struts usage, this was only available in
    486      * <code>ActionConfig</code>, but there are cases when an exception could
    487      * be thrown before an <code>ActionConfig</code> has been identified,
    488      * where global exception handlers may still be pertinent.</p>
    489      *
    490      * <p>TODO: Look for a way to share this logic with
    491      * <code>ActionConfig</code>, although there are subtle differences, and
    492      * it certainly doesn't seem like it should be done with inheritance.</p>
    493      *
    494      * @param type Exception class for which to find a handler
    495      * @since Struts 1.3.0
    496      */
    497     public ExceptionConfig findException(Class type) {
    498         // Check through the entire superclass hierarchy as needed
    499         ExceptionConfig config = null;
    500 
    501         while (true) {
    502             // Check for a locally defined handler
    503             String name = type.getName();
    504 
    505             log.debug("findException: look locally for " + name);
    506             config = findExceptionConfig(name);
    507 
    508             if (config != null) {
    509                 return (config);
    510             }
    511 
    512             // Loop again for our superclass (if any)
    513             type = type.getSuperclass();
    514 
    515             if (type == null) {
    516                 break;
    517             }
    518         }
    519 
    520         return (null); // No handler has been configured
    521     }
    522 
    523     /**
    524      * <p> Return the exception configurations for this module.  If there are
    525      * none, a zero-length array is returned. </p>
    526      */
    527     public ExceptionConfig[] findExceptionConfigs() {
    528         ExceptionConfig[] results = new ExceptionConfig[exceptions.size()];
    529 
    530         return ((ExceptionConfig[]) exceptions.values().toArray(results));
    531     }
    532 
    533     /**
    534      * <p> Return the form bean configuration for the specified key, if any;
    535      * otherwise return <code>null</code>. </p>
    536      *
    537      * @param name Name of the form bean configuration to return
    538      */
    539     public FormBeanConfig findFormBeanConfig(String name) {
    540         return ((FormBeanConfig) formBeans.get(name));
    541     }
    542 
    543     /**
    544      * <p> Return the form bean configurations for this module.  If there are
    545      * none, a zero-length array is returned. </p>
    546      */
    547     public FormBeanConfig[] findFormBeanConfigs() {
    548         FormBeanConfig[] results = new FormBeanConfig[formBeans.size()];
    549 
    550         return ((FormBeanConfig[]) formBeans.values().toArray(results));
    551     }
    552 
    553     /**
    554      * <p> Return the forward configuration for the specified key, if any;
    555      * otherwise return <code>null</code>. </p>
    556      *
    557      * @param name Name of the forward configuration to return
    558      */
    559     public ForwardConfig findForwardConfig(String name) {
    560         return ((ForwardConfig) forwards.get(name));
    561     }
    562 
    563     /**
    564      * <p> Return the form bean configurations for this module.  If there are
    565      * none, a zero-length array is returned. </p>
    566      */
    567     public ForwardConfig[] findForwardConfigs() {
    568         ForwardConfig[] results = new ForwardConfig[forwards.size()];
    569 
    570         return ((ForwardConfig[]) forwards.values().toArray(results));
    571     }
    572 
    573     /**
    574      * <p> Return the message resources configuration for the specified key,
    575      * if any; otherwise return <code>null</code>. </p>
    576      *
    577      * @param key Key of the data source configuration to return
    578      */
    579     public MessageResourcesConfig findMessageResourcesConfig(String key) {
    580         return ((MessageResourcesConfig) messageResources.get(key));
    581     }
    582 
    583     /**
    584      * <p> Return the message resources configurations for this module. If
    585      * there are none, a zero-length array is returned. </p>
    586      */
    587     public MessageResourcesConfig[] findMessageResourcesConfigs() {
    588         MessageResourcesConfig[] results =
    589             new MessageResourcesConfig[messageResources.size()];
    590 
    591         return ((MessageResourcesConfig[]) messageResources.values().toArray(results));
    592     }
    593 
    594     /**
    595      * <p> Return the configured plug-in actions for this module.  If there
    596      * are none, a zero-length array is returned. </p>
    597      */
    598     public PlugInConfig[] findPlugInConfigs() {
    599         PlugInConfig[] results = new PlugInConfig[plugIns.size()];
    600 
    601         return ((PlugInConfig[]) plugIns.toArray(results));
    602     }
    603 
    604     /**
    605      * <p> Freeze the configuration of this module.  After this method
    606      * returns, any attempt to modify the configuration will return an
    607      * IllegalStateException. </p>
    608      */
    609     public void freeze() {
    610         super.freeze();
    611 
    612         ActionConfig[] aconfigs = findActionConfigs();
    613 
    614         for (int i = 0; i < aconfigs.length; i++) {
    615             aconfigs[i].freeze();
    616         }
    617 
    618         matcher = new ActionConfigMatcher(aconfigs);
    619 
    620         getControllerConfig().freeze();
    621 
    622         ExceptionConfig[] econfigs = findExceptionConfigs();
    623 
    624         for (int i = 0; i < econfigs.length; i++) {
    625             econfigs[i].freeze();
    626         }
    627 
    628         FormBeanConfig[] fbconfigs = findFormBeanConfigs();
    629 
    630         for (int i = 0; i < fbconfigs.length; i++) {
    631             fbconfigs[i].freeze();
    632         }
    633 
    634         ForwardConfig[] fconfigs = findForwardConfigs();
    635 
    636         for (int i = 0; i < fconfigs.length; i++) {
    637             fconfigs[i].freeze();
    638         }
    639 
    640         MessageResourcesConfig[] mrconfigs = findMessageResourcesConfigs();
    641 
    642         for (int i = 0; i < mrconfigs.length; i++) {
    643             mrconfigs[i].freeze();
    644         }
    645 
    646         PlugInConfig[] piconfigs = findPlugInConfigs();
    647 
    648         for (int i = 0; i < piconfigs.length; i++) {
    649             piconfigs[i].freeze();
    650         }
    651     }
    652 
    653     /**
    654      * <p> Remove the specified action configuration instance. </p>
    655      *
    656      * @param config ActionConfig instance to be removed
    657      * @throws IllegalStateException if this module configuration has been
    658      *                               frozen
    659      */
    660     public void removeActionConfig(ActionConfig config) {
    661         throwIfConfigured();
    662         config.setModuleConfig(null);
    663         actionConfigs.remove(config.getPath());
    664         actionConfigList.remove(config);
    665     }
    666 
    667     /**
    668      * <p> Remove the specified exception configuration instance. </p>
    669      *
    670      * @param config ActionConfig instance to be removed
    671      * @throws IllegalStateException if this module configuration has been
    672      *                               frozen
    673      */
    674     public void removeExceptionConfig(ExceptionConfig config) {
    675         throwIfConfigured();
    676         exceptions.remove(config.getType());
    677     }
    678 
    679     /**
    680      * <p> Remove the specified form bean configuration instance. </p>
    681      *
    682      * @param config FormBeanConfig instance to be removed
    683      * @throws IllegalStateException if this module configuration has been
    684      *                               frozen
    685      */
    686     public void removeFormBeanConfig(FormBeanConfig config) {
    687         throwIfConfigured();
    688         formBeans.remove(config.getName());
    689     }
    690 
    691     /**
    692      * <p> Remove the specified forward configuration instance. </p>
    693      *
    694      * @param config ForwardConfig instance to be removed
    695      * @throws IllegalStateException if this module configuration has been
    696      *                               frozen
    697      */
    698     public void removeForwardConfig(ForwardConfig config) {
    699         throwIfConfigured();
    700         forwards.remove(config.getName());
    701     }
    702 
    703     /**
    704      * <p> Remove the specified message resources configuration instance.
    705      * </p>
    706      *
    707      * @param config MessageResourcesConfig instance to be removed
    708      * @throws IllegalStateException if this module configuration has been
    709      *                               frozen
    710      */
    711     public void removeMessageResourcesConfig(MessageResourcesConfig config) {
    712         throwIfConfigured();
    713         messageResources.remove(config.getKey());
    714     }
    715 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
