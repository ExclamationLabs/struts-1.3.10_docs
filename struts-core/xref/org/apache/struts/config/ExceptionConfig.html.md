[View Javadoc](../../../../../apidocs/org/apache/struts/config/ExceptionConfig.html.md)


    1   /*
    2    * $Id: ExceptionConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    26   * <p>A JavaBean representing the configuration information of an
    27   * <code>&lt;exception&gt;</code> element from a Struts configuration
    28   * file.</p>
    29   *
    30   * @version $Rev: 471754 $ $Date: 2005-08-06 18:03:30 -0400 (Sat, 06 Aug 2005)
    31   *          $
    32   * @since Struts 1.1
    33   */
    34  public class ExceptionConfig extends BaseConfig {
    35      // ------------------------------------------------------------- Properties
    36  
    37      /**
    38       * The servlet context attribute under which the message resources bundle
    39       * to be used for this exception is located.  If not set, the default
    40       * message resources for the current module is assumed.
    41       */
    42      protected String bundle = null;
    43  
    44      /**
    45       * The type of the ExceptionConfig that this object should inherit
    46       * properties from.
    47       */
    48      protected String inherit = null;
    49  
    50      /**
    51       * Have the inheritance values for this class been applied?
    52       */
    53      protected boolean extensionProcessed = false;
    54  
    55      /**
    56       * The fully qualified Java class name of the exception handler class
    57       * which should be instantiated to handle this exception.
    58       */
    59      protected String handler = "org.apache.struts.action.ExceptionHandler";
    60  
    61      /**
    62       * The message resources key specifying the error message associated with
    63       * this exception.
    64       */
    65      protected String key = null;
    66  
    67      /**
    68       * The module-relative path of the resource to forward to if this
    69       * exception occurs during an <code>Action</code>.
    70       */
    71      protected String path = null;
    72  
    73      /**
    74       * The scope in which we should expose the ActionMessage for this
    75       * exception handler.
    76       */
    77      protected String scope = "request";
    78  
    79      /**
    80       * The fully qualified Java class name of the exception that is to be
    81       * handled by this handler.
    82       */
    83      protected String type = null;
    84  
    85      public String getBundle() {
    86          return (this.bundle);
    87      }
    88  
    89      public void setBundle(String bundle) {
    90          if (configured) {
    91              throw new IllegalStateException("Configuration is frozen");
    92          }
    93  
    94          this.bundle = bundle;
    95      }
    96  
    97      public String getExtends() {
    98          return (this.inherit);
    99      }
    100 
    101     public void setExtends(String inherit) {
    102         if (configured) {
    103             throw new IllegalStateException("Configuration is frozen");
    104         }
    105 
    106         this.inherit = inherit;
    107     }
    108 
    109     public boolean isExtensionProcessed() {
    110         return extensionProcessed;
    111     }
    112 
    113     public String getHandler() {
    114         return (this.handler);
    115     }
    116 
    117     public void setHandler(String handler) {
    118         if (configured) {
    119             throw new IllegalStateException("Configuration is frozen");
    120         }
    121 
    122         this.handler = handler;
    123     }
    124 
    125     public String getKey() {
    126         return (this.key);
    127     }
    128 
    129     public void setKey(String key) {
    130         if (configured) {
    131             throw new IllegalStateException("Configuration is frozen");
    132         }
    133 
    134         this.key = key;
    135     }
    136 
    137     public String getPath() {
    138         return (this.path);
    139     }
    140 
    141     public void setPath(String path) {
    142         if (configured) {
    143             throw new IllegalStateException("Configuration is frozen");
    144         }
    145 
    146         this.path = path;
    147     }
    148 
    149     public String getScope() {
    150         return (this.scope);
    151     }
    152 
    153     public void setScope(String scope) {
    154         if (configured) {
    155             throw new IllegalStateException("Configuration is frozen");
    156         }
    157 
    158         this.scope = scope;
    159     }
    160 
    161     public String getType() {
    162         return (this.type);
    163     }
    164 
    165     public void setType(String type) {
    166         if (configured) {
    167             throw new IllegalStateException("Configuration is frozen");
    168         }
    169 
    170         this.type = type;
    171     }
    172 
    173     // ------------------------------------------------------ Protected Methods
    174 
    175     /**
    176      * <p>Traces the hierarchy of this object to check if any of the ancestors
    177      * are extending this instance.</p>
    178      *
    179      * @param moduleConfig The {@link ModuleConfig} that this config is from.
    180      * @param actionConfig The {@link ActionConfig} that this config is from,
    181      *                     if applicable.  This parameter must be null if this
    182      *                     is a global handler.
    183      * @return true if circular inheritance was detected.
    184      */
    185     protected boolean checkCircularInheritance(ModuleConfig moduleConfig,
    186         ActionConfig actionConfig) {
    187         String ancestorType = getExtends();
    188 
    189         if (ancestorType == null) {
    190             return false;
    191         }
    192 
    193         // Find our ancestor
    194         ExceptionConfig ancestor = null;
    195 
    196         // First check the action config
    197         if (actionConfig != null) {
    198             ancestor = actionConfig.findExceptionConfig(ancestorType);
    199 
    200             // If we found *this*, set ancestor to null to check for a global def
    201             if (ancestor == this) {
    202                 ancestor = null;
    203             }
    204         }
    205 
    206         // Then check the global handlers
    207         if (ancestor == null) {
    208             ancestor = moduleConfig.findExceptionConfig(ancestorType);
    209 
    210             if (ancestor != null) {
    211                 // If the ancestor is a global handler, set actionConfig
    212                 //  to null so further searches are only done among
    213                 //  global handlers.
    214                 actionConfig = null;
    215             }
    216         }
    217 
    218         while (ancestor != null) {
    219             // Check if an ancestor is extending *this*
    220             if (ancestor == this) {
    221                 return true;
    222             }
    223 
    224             // Get our ancestor's ancestor
    225             ancestorType = ancestor.getExtends();
    226 
    227             // check against ancestors extending same typed ancestors
    228             if (ancestor.getType().equals(ancestorType)) {
    229                 // If the ancestor is extending a config for the same type,
    230                 //  make sure we look for its ancestor in the global handlers.
    231                 //  If we're already at that level, we return false.
    232                 if (actionConfig == null) {
    233                     return false;
    234                 } else {
    235                     // Set actionConfig = null to force us to look for global
    236                     //  forwards
    237                     actionConfig = null;
    238                 }
    239             }
    240 
    241             ancestor = null;
    242 
    243             // First check the action config
    244             if (actionConfig != null) {
    245                 ancestor = actionConfig.findExceptionConfig(ancestorType);
    246             }
    247 
    248             // Then check the global handlers
    249             if (ancestor == null) {
    250                 ancestor = moduleConfig.findExceptionConfig(ancestorType);
    251 
    252                 if (ancestor != null) {
    253                     // Limit further checks to moduleConfig.
    254                     actionConfig = null;
    255                 }
    256             }
    257         }
    258 
    259         return false;
    260     }
    261 
    262     // --------------------------------------------------------- Public Methods
    263 
    264     /**
    265      * <p>Inherit values that have not been overridden from the provided
    266      * config object.  Subclasses overriding this method should verify that
    267      * the given parameter is of a class that contains a property it is trying
    268      * to inherit:</p>
    269      *
    270      * <pre>
    271      * if (config instanceof MyCustomConfig) {
    272      *     MyCustomConfig myConfig =
    273      *         (MyCustomConfig) config;
    274      *
    275      *     if (getMyCustomProp() == null) {
    276      *         setMyCustomProp(myConfig.getMyCustomProp());
    277      *     }
    278      * }
    279      * </pre>
    280      *
    281      * <p>If the given <code>config</code> is extending another object, those
    282      * extensions should be resolved before it's used as a parameter to this
    283      * method.</p>
    284      *
    285      * @param config The object that this instance will be inheriting its
    286      *               values from.
    287      * @see #processExtends(ModuleConfig, ActionConfig)
    288      */
    289     public void inheritFrom(ExceptionConfig config)
    290         throws ClassNotFoundException, IllegalAccessException,
    291             InstantiationException, InvocationTargetException {
    292         if (configured) {
    293             throw new IllegalStateException("Configuration is frozen");
    294         }
    295 
    296         // Inherit values that have not been overridden
    297         if (getBundle() == null) {
    298             setBundle(config.getBundle());
    299         }
    300 
    301         if (getHandler().equals("org.apache.struts.action.ExceptionHandler")) {
    302             setHandler(config.getHandler());
    303         }
    304 
    305         if (getKey() == null) {
    306             setKey(config.getKey());
    307         }
    308 
    309         if (getPath() == null) {
    310             setPath(config.getPath());
    311         }
    312 
    313         if (getScope().equals("request")) {
    314             setScope(config.getScope());
    315         }
    316 
    317         if (getType() == null) {
    318             setType(config.getType());
    319         }
    320 
    321         inheritProperties(config);
    322     }
    323 
    324     /**
    325      * <p>Inherit configuration information from the ExceptionConfig that this
    326      * instance is extending.  This method verifies that any exception config
    327      * object that it inherits from has also had its processExtends() method
    328      * called.</p>
    329      *
    330      * @param moduleConfig The {@link ModuleConfig} that this config is from.
    331      * @param actionConfig The {@link ActionConfig} that this config is from,
    332      *                     if applicable.  This must be null for global
    333      *                     forwards.
    334      * @see #inheritFrom(ExceptionConfig)
    335      */
    336     public void processExtends(ModuleConfig moduleConfig,
    337         ActionConfig actionConfig)
    338         throws ClassNotFoundException, IllegalAccessException,
    339             InstantiationException, InvocationTargetException {
    340         if (configured) {
    341             throw new IllegalStateException("Configuration is frozen");
    342         }
    343 
    344         String ancestorType = getExtends();
    345 
    346         if ((!extensionProcessed) && (ancestorType != null)) {
    347             ExceptionConfig baseConfig = null;
    348 
    349             // We only check the action config if we're not a global handler
    350             boolean checkActionConfig =
    351                 (this != moduleConfig.findExceptionConfig(getType()));
    352 
    353             // ... and the action config was provided
    354             checkActionConfig &= (actionConfig != null);
    355 
    356             // ... and we're not extending a config with the same type value
    357             // (because if we are, that means we're an action-level handler
    358             //  extending a global handler).
    359             checkActionConfig &= !ancestorType.equals(getType());
    360 
    361             // We first check in the action config's exception handlers
    362             if (checkActionConfig) {
    363                 baseConfig = actionConfig.findExceptionConfig(ancestorType);
    364             }
    365 
    366             // Then check the global exception handlers
    367             if (baseConfig == null) {
    368                 baseConfig = moduleConfig.findExceptionConfig(ancestorType);
    369             }
    370 
    371             if (baseConfig == null) {
    372                 throw new NullPointerException("Unable to find "
    373                     + "handler for '" + ancestorType + "' to extend.");
    374             }
    375 
    376             // Check for circular inheritance and make sure the base config's
    377             //  own inheritance has been processed already
    378             if (checkCircularInheritance(moduleConfig, actionConfig)) {
    379                 throw new IllegalArgumentException(
    380                     "Circular inheritance detected for forward " + getType());
    381             }
    382 
    383             if (!baseConfig.isExtensionProcessed()) {
    384                 baseConfig.processExtends(moduleConfig, actionConfig);
    385             }
    386 
    387             // copy values from the base config
    388             inheritFrom(baseConfig);
    389         }
    390 
    391         extensionProcessed = true;
    392     }
    393 
    394     /**
    395      * Return a String representation of this object.
    396      */
    397     public String toString() {
    398         StringBuffer sb = new StringBuffer("ExceptionConfig[");
    399 
    400         sb.append("type=");
    401         sb.append(this.type);
    402 
    403         if (this.bundle != null) {
    404             sb.append(",bundle=");
    405             sb.append(this.bundle);
    406         }
    407 
    408         if (this.inherit != null) {
    409             sb.append(",extends=");
    410             sb.append(this.inherit);
    411         }
    412 
    413         sb.append(",handler=");
    414         sb.append(this.handler);
    415         sb.append(",key=");
    416         sb.append(this.key);
    417         sb.append(",path=");
    418         sb.append(this.path);
    419         sb.append(",scope=");
    420         sb.append(this.scope);
    421         sb.append("]");
    422 
    423         return (sb.toString());
    424     }
    425 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
