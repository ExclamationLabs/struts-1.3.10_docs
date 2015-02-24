[View Javadoc](../../../../../apidocs/org/apache/struts/config/ActionConfig.html.md)


    1   /*
    2    * $Id: ActionConfig.java 480593 2006-11-29 15:17:52Z niallp $
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
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.util.RequestUtils;
    27  
    28  import java.lang.reflect.InvocationTargetException;
    29  
    30  import java.util.ArrayList;
    31  import java.util.HashMap;
    32  
    33  /**
    34   * <p>A JavaBean representing the configuration information of an
    35   * <code>&lt;action&gt;</code> element from a Struts module configuration
    36   * file.</p>
    37   *
    38   * @version $Rev: 480593 $ $Date: 2006-11-29 09:17:52 -0600 (Wed, 29 Nov 2006) $
    39   * @since Struts 1.1
    40   */
    41  public class ActionConfig extends BaseConfig {
    42      private static final Log log = LogFactory.getLog(ActionConfig.class);
    43  
    44      // ----------------------------------------------------- Instance Variables
    45  
    46      /**
    47       * <p> The set of exception handling configurations for this action, if
    48       * any, keyed by the <code>type</code> property. </p>
    49       */
    50      protected HashMap exceptions = new HashMap();
    51  
    52      /**
    53       * <p> The set of local forward configurations for this action, if any,
    54       * keyed by the <code>name</code> property. </p>
    55       */
    56      protected HashMap forwards = new HashMap();
    57  
    58      // ------------------------------------------------------------- Properties
    59  
    60      /**
    61       * <p> The module configuration with which we are associated. </p>
    62       */
    63      protected ModuleConfig moduleConfig = null;
    64  
    65      /**
    66       * <p> The request-scope or session-scope attribute name under which our
    67       * form bean is accessed, if it is different from the form bean's
    68       * specified <code>name</code>. </p>
    69       */
    70      protected String attribute = null;
    71  
    72      /**
    73       * <p>The internal identification of this action mapping. Identifications are
    74       * not inheritable and must be unique within a module.</p>
    75       *
    76       * @since Struts 1.3.6
    77       */
    78      protected String actionId = null;
    79  
    80      /**
    81       * <p>The path of the ActionConfig that this object should inherit
    82       * properties from.</p> </p>
    83       */
    84      protected String inherit = null;
    85  
    86      /**
    87       * Indicates whether the "cancellable " property has been set or not.
    88       */
    89      private boolean cancellableSet = false;
    90  
    91      /**
    92       * <p>Can this Action be cancelled? [false]</p> <p> By default, when an
    93       * Action is cancelled, validation is bypassed and the Action should not
    94       * execute the business operation. If a request tries to cancel an Action
    95       * when cancellable is not set, a "InvalidCancelException" is thrown.
    96       * </p>
    97       */
    98      protected boolean cancellable = false;
    99  
    100     /**
    101      * <p> Have the inheritance values for this class been applied?</p>
    102      */
    103     protected boolean extensionProcessed = false;
    104 
    105     /**
    106      * <p> Context-relative path of the web application resource that will
    107      * process this request via RequestDispatcher.forward(), instead of
    108      * instantiating and calling the <code>Action</code> class specified by
    109      * "type". Exactly one of <code>forward</code>, <code>include</code>, or
    110      * <code>type</code> must be specified. </p>
    111      */
    112     protected String forward = null;
    113 
    114     /**
    115      * <p> Context-relative path of the web application resource that will
    116      * process this request via RequestDispatcher.include(), instead of
    117      * instantiating and calling the <code>Action</code> class specified by
    118      * "type". Exactly one of <code>forward</code>, <code>include</code>, or
    119      * <code>type</code> must be specified. </p>
    120      */
    121     protected String include = null;
    122 
    123     /**
    124      * <p> Context-relative path of the input form to which control should be
    125      * returned if a validation error is encountered.  Required if "name" is
    126      * specified and the input bean returns validation errors. </p>
    127      */
    128     protected String input = null;
    129 
    130     /**
    131      * <p> Fully qualified Java class name of the <code>MultipartRequestHandler</code>
    132      * implementation class used to process multi-part request data for this
    133      * Action. </p>
    134      */
    135     protected String multipartClass = null;
    136 
    137     /**
    138      * <p> Name of the form bean, if any, associated with this Action. </p>
    139      */
    140     protected String name = null;
    141 
    142     /**
    143      * <p> General purpose configuration parameter that can be used to pass
    144      * extra information to the Action instance selected by this Action.
    145      * Struts does not itself use this value in any way. </p>
    146      */
    147     protected String parameter = null;
    148 
    149     /**
    150      * <p> Context-relative path of the submitted request, starting with a
    151      * slash ("/") character, and omitting any filename extension if extension
    152      * mapping is being used. </p>
    153      */
    154     protected String path = null;
    155 
    156     /**
    157      * <p> Prefix used to match request parameter names to form bean property
    158      * names, if any. </p>
    159      */
    160     protected String prefix = null;
    161 
    162     /**
    163      * <p> Comma-delimited list of security role names allowed to request this
    164      * Action. </p>
    165      */
    166     protected String roles = null;
    167 
    168     /**
    169      * <p> The set of security role names used to authorize access to this
    170      * Action, as an array for faster access. </p>
    171      */
    172     protected String[] roleNames = new String[0];
    173 
    174     /**
    175      * <p> Identifier of the scope ("request" or "session") within which our
    176      * form bean is accessed, if any. </p>
    177      */
    178     protected String scope = "session";
    179 
    180     /**
    181      * <p> Suffix used to match request parameter names to form bean property
    182      * names, if any. </p>
    183      */
    184     protected String suffix = null;
    185 
    186     /**
    187      * <p> Fully qualified Java class name of the <code>Action</code> class to
    188      * be used to process requests for this mapping if the
    189      * <code>forward</code> and <code>include</code> properties are not set.
    190      * Exactly one of <code>forward</code>, <code>include</code>, or
    191      * <code>type</code> must be specified.
    192      */
    193     protected String type = null;
    194 
    195     /**
    196      * <p> Indicates Action be configured as the default one for this module,
    197      * when true.
    198      */
    199     protected boolean unknown = false;
    200 
    201     /**
    202      * Indicates whether the "validate" property has been set or not.
    203      */
    204     private boolean validateSet = false;
    205 
    206     /**
    207      * <p> Should the <code>validate()</code> method of the form bean
    208      * associated with this action be called?
    209      */
    210     protected boolean validate = true;
    211 
    212     /**
    213      * <p> The name of a <code>commons-chain</code> command which should be
    214      * executed as part of the processing of this action.
    215      *
    216      * @since Struts 1.3.0
    217      */
    218     protected String command = null;
    219 
    220     /**
    221      * <p> The name of a <code>commons-chain</code> catalog in which
    222      * <code>command</code> should be sought.  If a <code>command</code> is
    223      * defined and this property is undefined, the "default" catalog will be
    224      * used. This is likely to be infrequently used after a future release of
    225      * <code>commons-chain</code> supports a one-string expression of a
    226      * catalog/chain combination.
    227      *
    228      * @since Struts 1.3.0
    229      */
    230     protected String catalog = null;
    231 
    232     /**
    233      * <p>The internal name of this action mapping. If an action has a name, it may be used
    234      * as a shortcut in a URI. For example, an action with an identification of "editPerson"
    235      * may be internally forwarded as "editPerson?id=1" which will then resolve to the
    236      * real URI path at execution time.</p>
    237      *
    238      * @return the actionId
    239      * @since Struts 1.3.6
    240      */
    241     public String getActionId() {
    242         return this.actionId;
    243     }
    244 
    245     /**
    246      * <p>The internal name of this action mapping. The name is not inheritable,
    247      * may not contain a forward slash, and must be unique within a module. </p>
    248      *
    249      * @param actionId the action identifier
    250      * @since Struts 1.3.6
    251      * @throws IllegalStateException if the configuration is frozen
    252      * @throws IllegalArgumentException if the identifier contains a forward slash
    253      */
    254     public void setActionId(String actionId) {
    255         if (configured) {
    256             throw new IllegalStateException("Configuration is frozen");
    257         }
    258         
    259         if ((actionId != null) && (actionId.indexOf("/") > -1)) {
    260             throw new IllegalArgumentException("actionId '" + actionId + "' may not contain a forward slash");
    261         }
    262 
    263         this.actionId = actionId;
    264     }
    265 
    266     /**
    267      * <p> The module configuration with which we are associated.
    268      */
    269     public ModuleConfig getModuleConfig() {
    270         return (this.moduleConfig);
    271     }
    272 
    273     /**
    274      * <p> The module configuration with which we are associated.
    275      */
    276     public void setModuleConfig(ModuleConfig moduleConfig) {
    277         if (configured) {
    278             throw new IllegalStateException("Configuration is frozen");
    279         }
    280 
    281         this.moduleConfig = moduleConfig;
    282     }
    283 
    284     /**
    285      * <p> Returns the request-scope or session-scope attribute name under
    286      * which our form bean is accessed, if it is different from the form
    287      * bean's specified <code>name</code>.
    288      *
    289      * @return attribute name under which our form bean is accessed.
    290      */
    291     public String getAttribute() {
    292         if (this.attribute == null) {
    293             return (this.name);
    294         } else {
    295             return (this.attribute);
    296         }
    297     }
    298 
    299     /**
    300      * <p> Set the request-scope or session-scope attribute name under which
    301      * our form bean is accessed, if it is different from the form bean's
    302      * specified <code>name</code>.
    303      *
    304      * @param attribute the request-scope or session-scope attribute name
    305      *                  under which our form bean is access.
    306      */
    307     public void setAttribute(String attribute) {
    308         if (configured) {
    309             throw new IllegalStateException("Configuration is frozen");
    310         }
    311 
    312         this.attribute = attribute;
    313     }
    314 
    315     /**
    316      * <p>Accessor for cancellable property</p>
    317      *
    318      * @return True if Action can be cancelled
    319      */
    320     public boolean getCancellable() {
    321         return (this.cancellable);
    322     }
    323 
    324     /**
    325      * <p>Mutator for for cancellable property</p>
    326      *
    327      * @param cancellable
    328      */
    329     public void setCancellable(boolean cancellable) {
    330         if (configured) {
    331             throw new IllegalStateException("Configuration is frozen");
    332         }
    333 
    334         this.cancellable = cancellable;
    335         this.cancellableSet = true;
    336     }
    337 
    338     /**
    339      * <p>Returns the path of the ActionConfig that this object should inherit
    340      * properties from.</p>
    341      *
    342      * @return the path of the ActionConfig that this object should inherit
    343      *         properties from.
    344      */
    345     public String getExtends() {
    346         return (this.inherit);
    347     }
    348 
    349     /**
    350      * <p>Set the path of the ActionConfig that this object should inherit
    351      * properties from.</p>
    352      *
    353      * @param inherit the path of the ActionConfig that this object should
    354      *                inherit properties from.
    355      */
    356     public void setExtends(String inherit) {
    357         if (configured) {
    358             throw new IllegalStateException("Configuration is frozen");
    359         }
    360 
    361         this.inherit = inherit;
    362     }
    363 
    364     public boolean isExtensionProcessed() {
    365         return extensionProcessed;
    366     }
    367 
    368     /**
    369      * <p> Returns context-relative path of the web application resource that
    370      * will process this request.
    371      *
    372      * @return context-relative path of the web application resource that will
    373      *         process this request.
    374      */
    375     public String getForward() {
    376         return (this.forward);
    377     }
    378 
    379     /**
    380      * <p> Set the context-relative path of the web application resource that
    381      * will process this request. Exactly one of <code>forward</code>,
    382      * <code>include</code>, or <code>type</code> must be specified.
    383      *
    384      * @param forward context-relative path of the web application resource
    385      *                that will process this request.
    386      */
    387     public void setForward(String forward) {
    388         if (configured) {
    389             throw new IllegalStateException("Configuration is frozen");
    390         }
    391 
    392         this.forward = forward;
    393     }
    394 
    395     /**
    396      * <p> Context-relative path of the web application resource that will
    397      * process this request.
    398      *
    399      * @return Context-relative path of the web application resource that will
    400      *         process this request.
    401      */
    402     public String getInclude() {
    403         return (this.include);
    404     }
    405 
    406     /**
    407      * <p> Set context-relative path of the web application resource that will
    408      * process this request. Exactly one of <code>forward</code>,
    409      * <code>include</code>, or <code>type</code> must be specified.
    410      *
    411      * @param include context-relative path of the web application resource
    412      *                that will process this request.
    413      */
    414     public void setInclude(String include) {
    415         if (configured) {
    416             throw new IllegalStateException("Configuration is frozen");
    417         }
    418 
    419         this.include = include;
    420     }
    421 
    422     /**
    423      * <p> Get the context-relative path of the input form to which control
    424      * should be returned if a validation error is encountered.
    425      *
    426      * @return context-relative path of the input form to which control should
    427      *         be returned if a validation error is encountered.
    428      */
    429     public String getInput() {
    430         return (this.input);
    431     }
    432 
    433     /**
    434      * <p> Set the context-relative path of the input form to which control
    435      * should be returned if a validation error is encountered.  Required if
    436      * "name" is specified and the input bean returns validation errors.
    437      *
    438      * @param input context-relative path of the input form to which control
    439      *              should be returned if a validation error is encountered.
    440      */
    441     public void setInput(String input) {
    442         if (configured) {
    443             throw new IllegalStateException("Configuration is frozen");
    444         }
    445 
    446         this.input = input;
    447     }
    448 
    449     /**
    450      * <p> Return the fully qualified Java class name of the
    451      * <code>MultipartRequestHandler</code> implementation class used to
    452      * process multi-part request data for this Action.
    453      */
    454     public String getMultipartClass() {
    455         return (this.multipartClass);
    456     }
    457 
    458     /**
    459      * <p> Set the fully qualified Java class name of the
    460      * <code>MultipartRequestHandler</code> implementation class used to
    461      * process multi-part request data for this Action.
    462      *
    463      * @param multipartClass fully qualified class name of the
    464      *                       <code>MultipartRequestHandler</code>
    465      *                       implementation class.
    466      */
    467     public void setMultipartClass(String multipartClass) {
    468         if (configured) {
    469             throw new IllegalStateException("Configuration is frozen");
    470         }
    471 
    472         this.multipartClass = multipartClass;
    473     }
    474 
    475     /**
    476      * <p> Return name of the form bean, if any, associated with this Action.
    477      */
    478     public String getName() {
    479         return (this.name);
    480     }
    481 
    482     /**
    483      * @param name name of the form bean associated with this Action.
    484      */
    485     public void setName(String name) {
    486         if (configured) {
    487             throw new IllegalStateException("Configuration is frozen");
    488         }
    489 
    490         this.name = name;
    491     }
    492 
    493     /**
    494      * <p> Return general purpose configuration parameter that can be used to
    495      * pass extra information to the Action instance selected by this Action.
    496      * Struts does not itself use this value in any way.
    497      */
    498     public String getParameter() {
    499         return (this.parameter);
    500     }
    501 
    502     /**
    503      * <p> General purpose configuration parameter that can be used to pass
    504      * extra information to the Action instance selected by this Action.
    505      * Struts does not itself use this value in any way.
    506      *
    507      * @param parameter General purpose configuration parameter.
    508      */
    509     public void setParameter(String parameter) {
    510         if (configured) {
    511             throw new IllegalStateException("Configuration is frozen");
    512         }
    513 
    514         this.parameter = parameter;
    515     }
    516 
    517     /**
    518      * <p> Return context-relative path of the submitted request, starting
    519      * with a slash ("/") character, and omitting any filename extension if
    520      * extension mapping is being used.
    521      */
    522     public String getPath() {
    523         return (this.path);
    524     }
    525 
    526     /**
    527      * <p> Set context-relative path of the submitted request, starting with a
    528      * slash ("/") character, and omitting any filename extension if extension
    529      * mapping is being used.
    530      *
    531      * @param path context-relative path of the submitted request.
    532      */
    533     public void setPath(String path) {
    534         if (configured) {
    535             throw new IllegalStateException("Configuration is frozen");
    536         }
    537 
    538         this.path = path;
    539     }
    540 
    541     /**
    542      * <p> Retruns prefix used to match request parameter names to form bean
    543      * property names, if any.
    544      */
    545     public String getPrefix() {
    546         return (this.prefix);
    547     }
    548 
    549     /**
    550      * @param prefix Prefix used to match request parameter names to form bean
    551      *               property names, if any.
    552      */
    553     public void setPrefix(String prefix) {
    554         if (configured) {
    555             throw new IllegalStateException("Configuration is frozen");
    556         }
    557 
    558         this.prefix = prefix;
    559     }
    560 
    561     public String getRoles() {
    562         return (this.roles);
    563     }
    564 
    565     public void setRoles(String roles) {
    566         if (configured) {
    567             throw new IllegalStateException("Configuration is frozen");
    568         }
    569 
    570         this.roles = roles;
    571 
    572         if (roles == null) {
    573             roleNames = new String[0];
    574 
    575             return;
    576         }
    577 
    578         ArrayList list = new ArrayList();
    579 
    580         while (true) {
    581             int comma = roles.indexOf(',');
    582 
    583             if (comma < 0) {
    584                 break;
    585             }
    586 
    587             list.add(roles.substring(0, comma).trim());
    588             roles = roles.substring(comma + 1);
    589         }
    590 
    591         roles = roles.trim();
    592 
    593         if (roles.length() > 0) {
    594             list.add(roles);
    595         }
    596 
    597         roleNames = (String[]) list.toArray(new String[list.size()]);
    598     }
    599 
    600     /**
    601      * <p> Get array of security role names used to authorize access to this
    602      * Action.
    603      */
    604     public String[] getRoleNames() {
    605         return (this.roleNames);
    606     }
    607 
    608     /**
    609      * <p> Get the scope ("request" or "session") within which our form bean
    610      * is accessed, if any.
    611      */
    612     public String getScope() {
    613         return (this.scope);
    614     }
    615 
    616     /**
    617      * @param scope scope ("request" or "session") within which our form bean
    618      *              is accessed, if any.
    619      */
    620     public void setScope(String scope) {
    621         if (configured) {
    622             throw new IllegalStateException("Configuration is frozen");
    623         }
    624 
    625         this.scope = scope;
    626     }
    627 
    628     /**
    629      * <p> Return suffix used to match request parameter names to form bean
    630      * property names, if any. </p>
    631      */
    632     public String getSuffix() {
    633         return (this.suffix);
    634     }
    635 
    636     /**
    637      * @param suffix Suffix used to match request parameter names to form bean
    638      *               property names, if any.
    639      */
    640     public void setSuffix(String suffix) {
    641         if (configured) {
    642             throw new IllegalStateException("Configuration is frozen");
    643         }
    644 
    645         this.suffix = suffix;
    646     }
    647 
    648     public String getType() {
    649         return (this.type);
    650     }
    651 
    652     public void setType(String type) {
    653         if (configured) {
    654             throw new IllegalStateException("Configuration is frozen");
    655         }
    656 
    657         this.type = type;
    658     }
    659 
    660     /**
    661      * <p> Determine whether Action is configured as the default one for this
    662      * module. </p>
    663      */
    664     public boolean getUnknown() {
    665         return (this.unknown);
    666     }
    667 
    668     /**
    669      * @param unknown Indicates Action is configured as the default one for
    670      *                this module, when true.
    671      */
    672     public void setUnknown(boolean unknown) {
    673         if (configured) {
    674             throw new IllegalStateException("Configuration is frozen");
    675         }
    676 
    677         this.unknown = unknown;
    678     }
    679 
    680     public boolean getValidate() {
    681         return (this.validate);
    682     }
    683 
    684     public void setValidate(boolean validate) {
    685         if (configured) {
    686             throw new IllegalStateException("Configuration is frozen");
    687         }
    688 
    689         this.validate = validate;
    690         this.validateSet = true;
    691     }
    692 
    693     /**
    694      * <p> Get the name of a <code>commons-chain</code> command which should
    695      * be executed as part of the processing of this action. </p>
    696      *
    697      * @return name of a <code>commons-chain</code> command which should be
    698      *         executed as part of the processing of this action.
    699      * @since Struts 1.3.0
    700      */
    701     public String getCommand() {
    702         return (this.command);
    703     }
    704 
    705     /**
    706      * <p> Get the name of a <code>commons-chain</code> catalog in which a
    707      * specified command should be sought.  This is likely to be infrequently
    708      * used after a future release of <code>commons-chain</code> supports a
    709      * one-string expression of a catalog/chain combination. </p>
    710      *
    711      * @return name of a <code>commons-chain</code> catalog in which a
    712      *         specified command should be sought.
    713      * @since Struts 1.3.0
    714      */
    715     public String getCatalog() {
    716         return (this.catalog);
    717     }
    718 
    719     /**
    720      * <p> Set the name of a <code>commons-chain</code> command which should
    721      * be executed as part of the processing of this action. </p>
    722      *
    723      * @param command name of a <code>commons-chain</code> command which
    724      *                should be executed as part of the processing of this
    725      *                action.
    726      * @since Struts 1.3.0
    727      */
    728     public void setCommand(String command) {
    729         if (configured) {
    730             throw new IllegalStateException("Configuration is frozen");
    731         }
    732 
    733         this.command = command;
    734     }
    735 
    736     /**
    737      * <p> Set the name of a <code>commons-chain</code> catalog in which a
    738      * specified command should be sought. This is likely to be infrequently
    739      * used after a future release of <code>commons-chain</code> supports a
    740      * one-string expression of a catalog/chain combination. </p>
    741      *
    742      * @param catalog name of a <code>commons-chain</code> catalog in which a
    743      *                specified command should be sought.
    744      * @since Struts 1.3.0
    745      */
    746     public void setCatalog(String catalog) {
    747         if (configured) {
    748             throw new IllegalStateException("Configuration is frozen");
    749         }
    750 
    751         this.catalog = catalog;
    752     }
    753 
    754     // ------------------------------------------------------ Protected Methods
    755 
    756     /**
    757      * <p>Traces the hierarchy of this object to check if any of the ancestors
    758      * is extending this instance.</p>
    759      *
    760      * @param moduleConfig The configuration for the module being configured.
    761      * @return true if circular inheritance was detected.
    762      */
    763     protected boolean checkCircularInheritance(ModuleConfig moduleConfig) {
    764         String ancestorPath = getExtends();
    765 
    766         while (ancestorPath != null) {
    767             // check if we have the same path as an ancestor
    768             if (getPath().equals(ancestorPath)) {
    769                 return true;
    770             }
    771 
    772             // get our ancestor's ancestor
    773             ActionConfig ancestor = moduleConfig.findActionConfig(ancestorPath);
    774 
    775             if (ancestor != null) {
    776                 ancestorPath = ancestor.getExtends();
    777             } else {
    778                 ancestorPath = null;
    779             }
    780         }
    781 
    782         return false;
    783     }
    784 
    785     /**
    786      * <p>Compare the exception handlers of this action with that of the given
    787      * and copy those that are not present.</p>
    788      *
    789      * @param baseConfig The action config to copy handlers from.
    790      * @see #inheritFrom(ActionConfig)
    791      */
    792     protected void inheritExceptionHandlers(ActionConfig baseConfig)
    793         throws ClassNotFoundException, IllegalAccessException,
    794             InstantiationException, InvocationTargetException {
    795         if (configured) {
    796             throw new IllegalStateException("Configuration is frozen");
    797         }
    798 
    799         // Inherit exception handler configs
    800         ExceptionConfig[] baseHandlers = baseConfig.findExceptionConfigs();
    801 
    802         for (int i = 0; i < baseHandlers.length; i++) {
    803             ExceptionConfig baseHandler = baseHandlers[i];
    804 
    805             // Do we have this handler?
    806             ExceptionConfig copy =
    807                 this.findExceptionConfig(baseHandler.getType());
    808 
    809             if (copy == null) {
    810                 // We don't have this, so let's copy it
    811                 copy =
    812                     (ExceptionConfig) RequestUtils.applicationInstance(baseHandler.getClass()
    813                                                                                   .getName());
    814 
    815                 BeanUtils.copyProperties(copy, baseHandler);
    816                 this.addExceptionConfig(copy);
    817                 copy.setProperties(baseHandler.copyProperties());
    818             } else {
    819                 // process any extension that this config might have
    820                 copy.processExtends(getModuleConfig(), this);
    821             }
    822         }
    823     }
    824 
    825     /**
    826      * <p>Compare the forwards of this action with that of the given and copy
    827      * those that are not present.</p>
    828      *
    829      * @param baseConfig The action config to copy forwards from.
    830      * @see #inheritFrom(ActionConfig)
    831      */
    832     protected void inheritForwards(ActionConfig baseConfig)
    833         throws ClassNotFoundException, IllegalAccessException,
    834             InstantiationException, InvocationTargetException {
    835         if (configured) {
    836             throw new IllegalStateException("Configuration is frozen");
    837         }
    838 
    839         // Inherit forward configs
    840         ForwardConfig[] baseForwards = baseConfig.findForwardConfigs();
    841 
    842         for (int i = 0; i < baseForwards.length; i++) {
    843             ForwardConfig baseForward = baseForwards[i];
    844 
    845             // Do we have this forward?
    846             ForwardConfig copy = this.findForwardConfig(baseForward.getName());
    847 
    848             if (copy == null) {
    849                 // We don't have this, so let's copy it
    850                 copy =
    851                     (ForwardConfig) RequestUtils.applicationInstance(baseForward.getClass()
    852                                                                                 .getName());
    853                 BeanUtils.copyProperties(copy, baseForward);
    854 
    855                 this.addForwardConfig(copy);
    856                 copy.setProperties(baseForward.copyProperties());
    857             } else {
    858                 // process any extension for this forward
    859                 copy.processExtends(getModuleConfig(), this);
    860             }
    861         }
    862     }
    863 
    864     // --------------------------------------------------------- Public Methods
    865 
    866     /**
    867      * <p> Add a new <code>ExceptionConfig</code> instance to the set
    868      * associated with this action. </p>
    869      *
    870      * @param config The new configuration instance to be added
    871      * @throws IllegalStateException if this module configuration has been
    872      *                               frozen
    873      */
    874     public void addExceptionConfig(ExceptionConfig config) {
    875         if (configured) {
    876             throw new IllegalStateException("Configuration is frozen");
    877         }
    878 
    879         exceptions.put(config.getType(), config);
    880     }
    881 
    882     /**
    883      * <p> Add a new <code>ForwardConfig</code> instance to the set of global
    884      * forwards associated with this action. </p>
    885      *
    886      * @param config The new configuration instance to be added
    887      * @throws IllegalStateException if this module configuration has been
    888      *                               frozen
    889      */
    890     public void addForwardConfig(ForwardConfig config) {
    891         if (configured) {
    892             throw new IllegalStateException("Configuration is frozen");
    893         }
    894 
    895         forwards.put(config.getName(), config);
    896     }
    897 
    898     /**
    899      * <p> Return the exception configuration for the specified type, if any;
    900      * otherwise return <code>null</code>. </p>
    901      *
    902      * @param type Exception class name to find a configuration for
    903      */
    904     public ExceptionConfig findExceptionConfig(String type) {
    905         return ((ExceptionConfig) exceptions.get(type));
    906     }
    907 
    908     /**
    909      * <p> Return the exception configurations for this action.  If there are
    910      * none, a zero-length array is returned. </p>
    911      */
    912     public ExceptionConfig[] findExceptionConfigs() {
    913         ExceptionConfig[] results = new ExceptionConfig[exceptions.size()];
    914 
    915         return ((ExceptionConfig[]) exceptions.values().toArray(results));
    916     }
    917 
    918     /**
    919      * <p>Find and return the <code>ExceptionConfig</code> instance defining
    920      * how <code>Exceptions</code> of the specified type should be handled.
    921      * This is performed by checking local and then global configurations for
    922      * the specified exception's class, and then looking up the superclass
    923      * chain (again checking local and then global configurations). If no
    924      * handler configuration can be found, return <code>null</code>.</p>
    925      *
    926      * <p>Introduced in <code>ActionMapping</code> in Struts 1.1, but pushed
    927      * up to <code>ActionConfig</code> in Struts 1.2.0.</p>
    928      *
    929      * @param type Exception class for which to find a handler
    930      * @since Struts 1.2.0
    931      */
    932     public ExceptionConfig findException(Class type) {
    933         // Check through the entire superclass hierarchy as needed
    934         ExceptionConfig config;
    935 
    936         while (true) {
    937             // Check for a locally defined handler
    938             String name = type.getName();
    939 
    940             log.debug("findException: look locally for " + name);
    941             config = findExceptionConfig(name);
    942 
    943             if (config != null) {
    944                 return (config);
    945             }
    946 
    947             // Check for a globally defined handler
    948             log.debug("findException: look globally for " + name);
    949             config = getModuleConfig().findExceptionConfig(name);
    950 
    951             if (config != null) {
    952                 return (config);
    953             }
    954 
    955             // Loop again for our superclass (if any)
    956             type = type.getSuperclass();
    957 
    958             if (type == null) {
    959                 break;
    960             }
    961         }
    962 
    963         return (null); // No handler has been configured
    964     }
    965 
    966     /**
    967      * <p> Return the forward configuration for the specified key, if any;
    968      * otherwise return <code>null</code>. </p>
    969      *
    970      * @param name Name of the forward configuration to return
    971      */
    972     public ForwardConfig findForwardConfig(String name) {
    973         return ((ForwardConfig) forwards.get(name));
    974     }
    975 
    976     /**
    977      * <p> Return all forward configurations for this module.  If there are
    978      * none, a zero-length array is returned. </p>
    979      */
    980     public ForwardConfig[] findForwardConfigs() {
    981         ForwardConfig[] results = new ForwardConfig[forwards.size()];
    982 
    983         return ((ForwardConfig[]) forwards.values().toArray(results));
    984     }
    985 
    986     /**
    987      * <p> Freeze the configuration of this action. </p>
    988      */
    989     public void freeze() {
    990         super.freeze();
    991 
    992         ExceptionConfig[] econfigs = findExceptionConfigs();
    993 
    994         for (int i = 0; i < econfigs.length; i++) {
    995             econfigs[i].freeze();
    996         }
    997 
    998         ForwardConfig[] fconfigs = findForwardConfigs();
    999 
    1000         for (int i = 0; i < fconfigs.length; i++) {
    1001             fconfigs[i].freeze();
    1002         }
    1003     }
    1004 
    1005     /**
    1006      * <p>Inherit values that have not been overridden from the provided
    1007      * config object.  Subclasses overriding this method should verify that
    1008      * the given parameter is of a class that contains a property it is trying
    1009      * to inherit:</p>
    1010      *
    1011      * <pre>
    1012      * if (config instanceof MyCustomConfig) {
    1013      *     MyCustomConfig myConfig =
    1014      *         (MyCustomConfig) config;
    1015      *
    1016      *     if (getMyCustomProp() == null) {
    1017      *         setMyCustomProp(myConfig.getMyCustomProp());
    1018      *     }
    1019      * }
    1020      * </pre>
    1021      *
    1022      * <p>If the given <code>config</code> is extending another object, those
    1023      * extensions should be resolved before it's used as a parameter to this
    1024      * method.</p>
    1025      *
    1026      * @param config The object that this instance will be inheriting its
    1027      *               values from.
    1028      * @see #processExtends(ModuleConfig)
    1029      */
    1030     public void inheritFrom(ActionConfig config)
    1031         throws ClassNotFoundException, IllegalAccessException,
    1032             InstantiationException, InvocationTargetException {
    1033         if (configured) {
    1034             throw new IllegalStateException("Configuration is frozen");
    1035         }
    1036 
    1037         // Inherit values that have not been overridden
    1038         if (getAttribute() == null) {
    1039             setAttribute(config.getAttribute());
    1040         }
    1041 
    1042         if (!cancellableSet) {
    1043             setCancellable(config.getCancellable());
    1044         }
    1045 
    1046         if (getCatalog() == null) {
    1047             setCatalog(config.getCatalog());
    1048         }
    1049 
    1050         if (getCommand() == null) {
    1051             setCommand(config.getCommand());
    1052         }
    1053 
    1054         if (getForward() == null) {
    1055             setForward(config.getForward());
    1056         }
    1057 
    1058         if (getInclude() == null) {
    1059             setInclude(config.getInclude());
    1060         }
    1061 
    1062         if (getInput() == null) {
    1063             setInput(config.getInput());
    1064         }
    1065 
    1066         if (getMultipartClass() == null) {
    1067             setMultipartClass(config.getMultipartClass());
    1068         }
    1069 
    1070         if (getName() == null) {
    1071             setName(config.getName());
    1072         }
    1073 
    1074         if (getParameter() == null) {
    1075             setParameter(config.getParameter());
    1076         }
    1077 
    1078         if (getPath() == null) {
    1079             setPath(config.getPath());
    1080         }
    1081 
    1082         if (getPrefix() == null) {
    1083             setPrefix(config.getPrefix());
    1084         }
    1085 
    1086         if (getRoles() == null) {
    1087             setRoles(config.getRoles());
    1088         }
    1089 
    1090         if (getScope().equals("session")) {
    1091             setScope(config.getScope());
    1092         }
    1093 
    1094         if (getSuffix() == null) {
    1095             setSuffix(config.getSuffix());
    1096         }
    1097 
    1098         if (getType() == null) {
    1099             setType(config.getType());
    1100         }
    1101 
    1102         if (!getUnknown()) {
    1103             setUnknown(config.getUnknown());
    1104         }
    1105 
    1106         if (!validateSet) {
    1107             setValidate(config.getValidate());
    1108         }
    1109 
    1110         inheritExceptionHandlers(config);
    1111         inheritForwards(config);
    1112         inheritProperties(config);
    1113     }
    1114 
    1115     /**
    1116      * <p>Inherit configuration information from the ActionConfig that this
    1117      * instance is extending.  This method verifies that any action config
    1118      * object that it inherits from has also had its processExtends() method
    1119      * called.</p>
    1120      *
    1121      * @param moduleConfig The {@link ModuleConfig} that this bean is from.
    1122      * @see #inheritFrom(ActionConfig)
    1123      */
    1124     public void processExtends(ModuleConfig moduleConfig)
    1125         throws ClassNotFoundException, IllegalAccessException,
    1126             InstantiationException, InvocationTargetException {
    1127         if (configured) {
    1128             throw new IllegalStateException("Configuration is frozen");
    1129         }
    1130 
    1131         String ancestorPath = getExtends();
    1132 
    1133         if ((!extensionProcessed) && (ancestorPath != null)) {
    1134             ActionConfig baseConfig =
    1135                 moduleConfig.findActionConfig(ancestorPath);
    1136 
    1137             if (baseConfig == null) {
    1138                 throw new NullPointerException("Unable to find "
    1139                     + "action for '" + ancestorPath + "' to extend.");
    1140             }
    1141 
    1142             // Check against circular inheritance and make sure the base
    1143             //  config's own extends has been processed already
    1144             if (checkCircularInheritance(moduleConfig)) {
    1145                 throw new IllegalArgumentException(
    1146                     "Circular inheritance detected for action " + getPath());
    1147             }
    1148 
    1149             // Make sure the ancestor's own extension has been processed.
    1150             if (!baseConfig.isExtensionProcessed()) {
    1151                 baseConfig.processExtends(moduleConfig);
    1152             }
    1153 
    1154             // Copy values from the base config
    1155             inheritFrom(baseConfig);
    1156         }
    1157 
    1158         extensionProcessed = true;
    1159     }
    1160 
    1161     /**
    1162      * <p> Remove the specified exception configuration instance. </p>
    1163      *
    1164      * @param config ExceptionConfig instance to be removed
    1165      * @throws IllegalStateException if this module configuration has been
    1166      *                               frozen
    1167      */
    1168     public void removeExceptionConfig(ExceptionConfig config) {
    1169         if (configured) {
    1170             throw new IllegalStateException("Configuration is frozen");
    1171         }
    1172 
    1173         exceptions.remove(config.getType());
    1174     }
    1175 
    1176     /**
    1177      * <p> Remove the specified forward configuration instance. </p>
    1178      *
    1179      * @param config ForwardConfig instance to be removed
    1180      * @throws IllegalStateException if this module configuration has been
    1181      *                               frozen
    1182      */
    1183     public void removeForwardConfig(ForwardConfig config) {
    1184         if (configured) {
    1185             throw new IllegalStateException("Configuration is frozen");
    1186         }
    1187 
    1188         forwards.remove(config.getName());
    1189     }
    1190 
    1191     /**
    1192      * <p> Return a String representation of this object. </p>
    1193      */
    1194     public String toString() {
    1195         StringBuffer sb = new StringBuffer("ActionConfig[");
    1196 
    1197         sb.append("cancellable=");
    1198         sb.append(cancellable);
    1199 
    1200         sb.append(",path=");
    1201         sb.append(path);
    1202 
    1203         sb.append(",validate=");
    1204         sb.append(validate);
    1205 
    1206         if (actionId != null) {
    1207             sb.append(",actionId=");
    1208             sb.append(actionId);
    1209         }
    1210 
    1211         if (attribute != null) {
    1212             sb.append(",attribute=");
    1213             sb.append(attribute);
    1214         }
    1215 
    1216         if (catalog != null) {
    1217             sb.append(",catalog=");
    1218             sb.append(catalog);
    1219         }
    1220 
    1221         if (command != null) {
    1222             sb.append(",command=");
    1223             sb.append(command);
    1224         }
    1225 
    1226         if (inherit != null) {
    1227             sb.append(",extends=");
    1228             sb.append(inherit);
    1229         }
    1230 
    1231         if (forward != null) {
    1232             sb.append(",forward=");
    1233             sb.append(forward);
    1234         }
    1235 
    1236         if (include != null) {
    1237             sb.append(",include=");
    1238             sb.append(include);
    1239         }
    1240 
    1241         if (input != null) {
    1242             sb.append(",input=");
    1243             sb.append(input);
    1244         }
    1245 
    1246         if (multipartClass != null) {
    1247             sb.append(",multipartClass=");
    1248             sb.append(multipartClass);
    1249         }
    1250 
    1251         if (name != null) {
    1252             sb.append(",name=");
    1253             sb.append(name);
    1254         }
    1255 
    1256         if (parameter != null) {
    1257             sb.append(",parameter=");
    1258             sb.append(parameter);
    1259         }
    1260 
    1261         if (prefix != null) {
    1262             sb.append(",prefix=");
    1263             sb.append(prefix);
    1264         }
    1265 
    1266         if (roles != null) {
    1267             sb.append(",roles=");
    1268             sb.append(roles);
    1269         }
    1270 
    1271         if (scope != null) {
    1272             sb.append(",scope=");
    1273             sb.append(scope);
    1274         }
    1275 
    1276         if (suffix != null) {
    1277             sb.append(",suffix=");
    1278             sb.append(suffix);
    1279         }
    1280 
    1281         if (type != null) {
    1282             sb.append(",type=");
    1283             sb.append(type);
    1284         }
    1285 
    1286         return (sb.toString());
    1287     }
    1288 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
