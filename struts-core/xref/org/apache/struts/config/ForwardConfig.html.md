[View Javadoc](../../../../../apidocs/org/apache/struts/config/ForwardConfig.html.md)


    1   /*
    2    * $Id: ForwardConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.lang.reflect.InvocationTargetException;
    24  
    25  /**
    26   * <p>A JavaBean representing the configuration information of a
    27   * <code>&lt;forward&gt;</code> element from a Struts configuration file.</p>
    28   *
    29   * @version $Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005)
    30   *          $
    31   * @since Struts 1.1
    32   */
    33  public class ForwardConfig extends BaseConfig {
    34      // ------------------------------------------------------------- Properties
    35  
    36      /**
    37       * The name of the ForwardConfig that this object should inherit
    38       * properties from.
    39       */
    40      protected String inherit = null;
    41  
    42      /**
    43       * Have the inheritance values for this class been applied?
    44       */
    45      protected boolean extensionProcessed = false;
    46  
    47      /**
    48       * The unique identifier of this forward, which is used to reference it in
    49       * <code>Action</code> classes.
    50       */
    51      protected String name = null;
    52  
    53      /**
    54       * <p>The URL to which this <code>ForwardConfig</code> entry points, which
    55       * must start with a slash ("/") character.  It is interpreted according
    56       * to the following rules:</p>
    57       *
    58       * <ul>
    59       *
    60       * <li>If <code>contextRelative</code> property is <code>true</code>, the
    61       * path is considered to be context-relative within the current web
    62       * application (even if we are in a named module).  It will be prefixed by
    63       * the context path to create a server-relative URL.</li>
    64       *
    65       * <li>If the <code>contextRelative</code> property is false, the path is
    66       * considered to be the module-relative portion of the URL. It will be
    67       * used as the replacement for the <code>$P</code> marker in the
    68       * <code>forwardPattern</code> property defined on the {@link
    69       * ControllerConfig} element for our current module. For the default
    70       * <code>forwardPattern</code> value of <code>$C$M$P</code>, the resulting
    71       * server-relative URL will be the concatenation of the context path, the
    72       * module prefix, and the <code>path</code> from this
    73       * <code>ForwardConfig</code>.
    74       *
    75       * </li>
    76       *
    77       * </ul>
    78       */
    79      protected String path = null;
    80  
    81      /**
    82       * <p>The prefix of the module to which this <code>ForwardConfig</code>
    83       * entry points, which must start with a slash ("/") character.  </p>
    84       * <p>Usage note: If a forward config is used in a hyperlink, and a module
    85       * is specified, the path must lead to another action and not directly to
    86       * a page. This is in keeping with rule that in a modular application all
    87       * links must be to an action rather than a page. </p>
    88       */
    89      protected String module = null;
    90  
    91      /**
    92       * Should a redirect be used to transfer control to the specified path?
    93       */
    94      protected boolean redirect = false;
    95  
    96      /**
    97       * <p>The name of a <code>commons-chain</code> command which should be
    98       * looked up and executed before Struts dispatches control to the view
    99       * represented by this config.</p>
    100      */
    101     protected String command = null;
    102 
    103     /**
    104      * <p>The name of a <code>commons-chain</code> catalog in which
    105      * <code>command</code> should be looked up.  If this value is undefined,
    106      * then the command will be looked up in the "default" catalog.  This
    107      * value has no meaning except in the context of the <code>command</code>
    108      * property.</p>
    109      */
    110     protected String catalog = null;
    111 
    112     // ----------------------------------------------------------- Constructors
    113 
    114     /**
    115      * Construct a new instance with default values.
    116      */
    117     public ForwardConfig() {
    118         super();
    119     }
    120 
    121     /**
    122      * Construct a new instance with the specified values.
    123      *
    124      * @param name     Name of this forward
    125      * @param path     Path to which control should be forwarded or
    126      *                 redirected
    127      * @param redirect Should we do a redirect?
    128      */
    129     public ForwardConfig(String name, String path, boolean redirect) {
    130         super();
    131         setName(name);
    132         setPath(path);
    133         setRedirect(redirect);
    134     }
    135 
    136     /**
    137      * <p>Construct a new instance with the specified values.</p>
    138      *
    139      * @param name     Name of this forward
    140      * @param path     Path to which control should be forwarded or
    141      *                 redirected
    142      * @param redirect Should we do a redirect?
    143      * @param module   Module prefix, if any
    144      */
    145     public ForwardConfig(String name, String path, boolean redirect,
    146         String module) {
    147         super();
    148         setName(name);
    149         setPath(path);
    150         setRedirect(redirect);
    151         setModule(module);
    152     }
    153 
    154     /**
    155      * <p>Construct a new instance based on the values of another
    156      * ForwardConfig.</p>
    157      *
    158      * @param copyMe A ForwardConfig instance to copy
    159      * @since Struts 1.3.6
    160      */
    161     public ForwardConfig(ForwardConfig copyMe) {
    162         this(copyMe.getName(), copyMe.getPath(), copyMe.getRedirect(),
    163             copyMe.getModule());
    164     }
    165 
    166     public String getExtends() {
    167         return (this.inherit);
    168     }
    169 
    170     public void setExtends(String inherit) {
    171         if (configured) {
    172             throw new IllegalStateException("Configuration is frozen");
    173         }
    174 
    175         this.inherit = inherit;
    176     }
    177 
    178     public boolean isExtensionProcessed() {
    179         return extensionProcessed;
    180     }
    181 
    182     public String getName() {
    183         return (this.name);
    184     }
    185 
    186     public void setName(String name) {
    187         if (configured) {
    188             throw new IllegalStateException("Configuration is frozen");
    189         }
    190 
    191         this.name = name;
    192     }
    193 
    194     public String getPath() {
    195         return (this.path);
    196     }
    197 
    198     public void setPath(String path) {
    199         if (configured) {
    200             throw new IllegalStateException("Configuration is frozen");
    201         }
    202 
    203         this.path = path;
    204     }
    205 
    206     public String getModule() {
    207         return (this.module);
    208     }
    209 
    210     public void setModule(String module) {
    211         if (configured) {
    212             throw new IllegalStateException("Configuration is frozen");
    213         }
    214 
    215         this.module = module;
    216     }
    217 
    218     public boolean getRedirect() {
    219         return (this.redirect);
    220     }
    221 
    222     public void setRedirect(boolean redirect) {
    223         if (configured) {
    224             throw new IllegalStateException("Configuration is frozen");
    225         }
    226 
    227         this.redirect = redirect;
    228     }
    229 
    230     public String getCommand() {
    231         return (this.command);
    232     }
    233 
    234     public void setCommand(String command) {
    235         if (configured) {
    236             throw new IllegalStateException("Configuration is frozen");
    237         }
    238 
    239         this.command = command;
    240     }
    241 
    242     public String getCatalog() {
    243         return (this.catalog);
    244     }
    245 
    246     public void setCatalog(String catalog) {
    247         if (configured) {
    248             throw new IllegalStateException("Configuration is frozen");
    249         }
    250 
    251         this.catalog = catalog;
    252     }
    253 
    254     // ------------------------------------------------------ Protected Methods
    255 
    256     /**
    257      * <p>Traces the hierarchy of this object to check if any of the ancestors
    258      * are extending this instance.</p>
    259      *
    260      * @param moduleConfig The {@link ModuleConfig} that this config is from.
    261      * @param actionConfig The {@link ActionConfig} that this config is from,
    262      *                     if applicable.  This parameter must be null if this
    263      *                     forward config is a global forward.
    264      * @return true if circular inheritance was detected.
    265      */
    266     protected boolean checkCircularInheritance(ModuleConfig moduleConfig,
    267         ActionConfig actionConfig) {
    268         String ancestorName = getExtends();
    269 
    270         if (ancestorName == null) {
    271             return false;
    272         }
    273 
    274         // Find our ancestor
    275         ForwardConfig ancestor = null;
    276 
    277         // First check the action config
    278         if (actionConfig != null) {
    279             ancestor = actionConfig.findForwardConfig(ancestorName);
    280 
    281             // If we found *this*, set ancestor to null to check for a global def
    282             if (ancestor == this) {
    283                 ancestor = null;
    284             }
    285         }
    286 
    287         // Then check the global forwards
    288         if (ancestor == null) {
    289             ancestor = moduleConfig.findForwardConfig(ancestorName);
    290 
    291             if (ancestor != null) {
    292                 // If the ancestor is a global forward, set actionConfig
    293                 //  to null so further searches are only done among
    294                 //  global forwards.
    295                 actionConfig = null;
    296             }
    297         }
    298 
    299         while (ancestor != null) {
    300             // Check if an ancestor is extending *this*
    301             if (ancestor == this) {
    302                 return true;
    303             }
    304 
    305             // Get our ancestor's ancestor
    306             ancestorName = ancestor.getExtends();
    307 
    308             // check against ancestors extending same named ancestors
    309             if (ancestor.getName().equals(ancestorName)) {
    310                 // If the ancestor is extending a config with the same name
    311                 //  make sure we look for its ancestor in the global forwards.
    312                 //  If we're already at that level, we return false.
    313                 if (actionConfig == null) {
    314                     return false;
    315                 } else {
    316                     // Set actionConfig = null to force us to look for global
    317                     //  forwards
    318                     actionConfig = null;
    319                 }
    320             }
    321 
    322             ancestor = null;
    323 
    324             // First check the action config
    325             if (actionConfig != null) {
    326                 ancestor = actionConfig.findForwardConfig(ancestorName);
    327             }
    328 
    329             // Then check the global forwards
    330             if (ancestor == null) {
    331                 ancestor = moduleConfig.findForwardConfig(ancestorName);
    332 
    333                 if (ancestor != null) {
    334                     // Limit further checks to moduleConfig.
    335                     actionConfig = null;
    336                 }
    337             }
    338         }
    339 
    340         return false;
    341     }
    342 
    343     // --------------------------------------------------------- Public Methods
    344 
    345     /**
    346      * <p>Inherit values that have not been overridden from the provided
    347      * config object.  Subclasses overriding this method should verify that
    348      * the given parameter is of a class that contains a property it is trying
    349      * to inherit:</p>
    350      *
    351      * <pre>
    352      * if (config instanceof MyCustomConfig) {
    353      *     MyCustomConfig myConfig =
    354      *         (MyCustomConfig) config;
    355      *
    356      *     if (getMyCustomProp() == null) {
    357      *         setMyCustomProp(myConfig.getMyCustomProp());
    358      *     }
    359      * }
    360      * </pre>
    361      *
    362      * <p>If the given <code>config</code> is extending another object, those
    363      * extensions should be resolved before it's used as a parameter to this
    364      * method.</p>
    365      *
    366      * @param config The object that this instance will be inheriting its
    367      *               values from.
    368      * @see #processExtends(ModuleConfig, ActionConfig)
    369      */
    370     public void inheritFrom(ForwardConfig config)
    371         throws ClassNotFoundException, IllegalAccessException,
    372             InstantiationException, InvocationTargetException {
    373         if (configured) {
    374             throw new IllegalStateException("Configuration is frozen");
    375         }
    376 
    377         // Inherit values that have not been overridden
    378         if (getCatalog() == null) {
    379             setCatalog(config.getCatalog());
    380         }
    381 
    382         if (getCommand() == null) {
    383             setCommand(config.getCommand());
    384         }
    385 
    386         if (getModule() == null) {
    387             setModule(config.getModule());
    388         }
    389 
    390         if (getName() == null) {
    391             setName(config.getName());
    392         }
    393 
    394         if (getPath() == null) {
    395             setPath(config.getPath());
    396         }
    397 
    398         if (!getRedirect()) {
    399             setRedirect(config.getRedirect());
    400         }
    401 
    402         inheritProperties(config);
    403     }
    404 
    405     /**
    406      * <p>Inherit configuration information from the ForwardConfig that this
    407      * instance is extending.  This method verifies that any forward config
    408      * object that it inherits from has also had its processExtends() method
    409      * called.</p>
    410      *
    411      * @param moduleConfig The {@link ModuleConfig} that this config is from.
    412      * @param actionConfig The {@link ActionConfig} that this config is from,
    413      *                     if applicable.  This must be null for global
    414      *                     forwards.
    415      * @see #inheritFrom(ForwardConfig)
    416      */
    417     public void processExtends(ModuleConfig moduleConfig,
    418         ActionConfig actionConfig)
    419         throws ClassNotFoundException, IllegalAccessException,
    420             InstantiationException, InvocationTargetException {
    421         if (configured) {
    422             throw new IllegalStateException("Configuration is frozen");
    423         }
    424 
    425         String ancestorName = getExtends();
    426 
    427         if ((!extensionProcessed) && (ancestorName != null)) {
    428             ForwardConfig baseConfig = null;
    429 
    430             // We only check the action config if we're not a global forward
    431             boolean checkActionConfig =
    432                 (this != moduleConfig.findForwardConfig(getName()));
    433 
    434             // ... and the action config was provided
    435             checkActionConfig &= (actionConfig != null);
    436 
    437             // ... and we're not extending a config with the same name
    438             // (because if we are, that means we're an action-level forward
    439             //  extending a global forward).
    440             checkActionConfig &= !ancestorName.equals(getName());
    441 
    442             // We first check in the action config's forwards
    443             if (checkActionConfig) {
    444                 baseConfig = actionConfig.findForwardConfig(ancestorName);
    445             }
    446 
    447             // Then check the global forwards
    448             if (baseConfig == null) {
    449                 baseConfig = moduleConfig.findForwardConfig(ancestorName);
    450             }
    451 
    452             if (baseConfig == null) {
    453                 throw new NullPointerException("Unable to find " + "forward '"
    454                     + ancestorName + "' to extend.");
    455             }
    456 
    457             // Check for circular inheritance and make sure the base config's
    458             //  own extends have been processed already
    459             if (checkCircularInheritance(moduleConfig, actionConfig)) {
    460                 throw new IllegalArgumentException(
    461                     "Circular inheritance detected for forward " + getName());
    462             }
    463 
    464             if (!baseConfig.isExtensionProcessed()) {
    465                 baseConfig.processExtends(moduleConfig, actionConfig);
    466             }
    467 
    468             // copy values from the base config
    469             inheritFrom(baseConfig);
    470         }
    471 
    472         extensionProcessed = true;
    473     }
    474 
    475     /**
    476      * Return a String representation of this object.
    477      */
    478     public String toString() {
    479         StringBuffer sb = new StringBuffer("ForwardConfig[");
    480 
    481         sb.append("name=");
    482         sb.append(this.name);
    483         sb.append(",path=");
    484         sb.append(this.path);
    485         sb.append(",redirect=");
    486         sb.append(this.redirect);
    487         sb.append(",module=");
    488         sb.append(this.module);
    489         sb.append(",extends=");
    490         sb.append(this.inherit);
    491         sb.append(",catalog=");
    492         sb.append(this.catalog);
    493         sb.append(",command=");
    494         sb.append(this.command);
    495         sb.append("]");
    496 
    497         return (sb.toString());
    498     }
    499 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
