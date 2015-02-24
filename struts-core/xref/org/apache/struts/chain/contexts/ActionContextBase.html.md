[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/contexts/ActionContextBase.html.md)


    1   /*
    2    * $Id: ActionContextBase.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.contexts;
    22  
    23  import org.apache.commons.chain.Context;
    24  import org.apache.commons.chain.impl.ContextBase;
    25  import org.apache.commons.logging.Log;
    26  import org.apache.commons.logging.LogFactory;
    27  import org.apache.struts.action.Action;
    28  import org.apache.struts.action.ActionForm;
    29  import org.apache.struts.action.ActionMessages;
    30  import org.apache.struts.chain.Constants;
    31  import org.apache.struts.config.ActionConfig;
    32  import org.apache.struts.config.FormBeanConfig;
    33  import org.apache.struts.config.ForwardConfig;
    34  import org.apache.struts.config.ModuleConfig;
    35  import org.apache.struts.util.MessageResources;
    36  import org.apache.struts.util.TokenProcessor;
    37  
    38  import java.util.Locale;
    39  import java.util.Map;
    40  
    41  /**
    42   * <p> Provide an abstract but semi-complete implementation of ActionContext
    43   * to serve as the base for concrete implementations. </p> <p> The abstract
    44   * methods to implement are the accessors for the named states,
    45   * <code>getApplicationScope</code>, <code>getRequestScope</code>, and
    46   * <code>getSessionScope</code>. </p>
    47   */
    48  public abstract class ActionContextBase extends ContextWrapper
    49      implements ActionContext {
    50      /**
    51       * @see Constants.ACTION_KEY
    52       */
    53      public static final String ACTION_KEY = Constants.ACTION_KEY;
    54  
    55      /**
    56       * @see
    57       */
    58      public static final String ACTION_CONFIG_KEY = Constants.ACTION_CONFIG_KEY;
    59  
    60      /**
    61       * @see Constants.ACTION_FORM_KEY
    62       */
    63      public static final String ACTION_FORM_KEY = Constants.ACTION_FORM_KEY;
    64  
    65      /**
    66       * @see Constants.FORWARD_CONFIG_KEY
    67       */
    68      public static final String FORWARD_CONFIG_KEY =
    69          Constants.FORWARD_CONFIG_KEY;
    70  
    71      /**
    72       * @see Constants.MODULE_CONFIG_KEY
    73       */
    74      public static final String MODULE_CONFIG_KEY = Constants.MODULE_CONFIG_KEY;
    75  
    76      /**
    77       * @see Constants.EXCEPTION_KEY
    78       */
    79      public static final String EXCEPTION_KEY = Constants.EXCEPTION_KEY;
    80  
    81      /**
    82       * <p> Provide the default context attribute under which to store the
    83       * ActionMessage cache for errors. </p>
    84       */
    85      public static final String ERROR_ACTION_MESSAGES_KEY = "errors";
    86  
    87      /**
    88       * <p> Provide the default context attribute under which to store the
    89       * ActionMessage cache. </p>
    90       */
    91      public static final String MESSAGE_ACTION_MESSAGES_KEY = "messages";
    92  
    93      /**
    94       * @see Constants.MESSAGE_RESOURCES_KEY
    95       */
    96      public static final String MESSAGE_RESOURCES_KEY =
    97          Constants.MESSAGE_RESOURCES_KEY;
    98  
    99      /**
    100      * @see Constants.INCLUDE_KEY
    101      */
    102     public static final String INCLUDE_KEY = Constants.INCLUDE_KEY;
    103 
    104     /**
    105      * @see Constants.LOCALE_KEY
    106      */
    107     public static final String LOCALE_KEY = Constants.LOCALE_KEY;
    108 
    109     /**
    110      * @see Constants.CANCEL_KEY
    111      */
    112     public static final String CANCEL_KEY = Constants.CANCEL_KEY;
    113 
    114     /**
    115      * @see Constants.VALID_KEY
    116      */
    117     public static final String VALID_KEY = Constants.VALID_KEY;
    118 
    119     /**
    120      * Provide the default context attribute under which to store the
    121      * transaction token key.
    122      */
    123     public static final String TRANSACTION_TOKEN_KEY = "TRANSACTION_TOKEN_KEY";
    124 
    125     /**
    126      * Provide the default context attribute under which to store the token
    127      * key.
    128      */
    129     public static final String TOKEN_KEY = "TOKEN_KEY";
    130 
    131     /**
    132      * Store the TokenProcessor instance for this Context.
    133      */
    134     protected TokenProcessor token = null;
    135 
    136     /**
    137      * Store the Log instance for this Context.
    138      */
    139     private Log logger = null;
    140 
    141     /**
    142      * Instantiate ActionContextBase, wrapping the given Context.
    143      *
    144      * @param context Context to wrap
    145      */
    146     public ActionContextBase(Context context) {
    147         super(context);
    148         token = TokenProcessor.getInstance();
    149         logger = LogFactory.getLog(this.getClass());
    150     }
    151 
    152     /**
    153      * Instantiate ActionContextBase, wrapping a default ContextBase
    154      * instance.
    155      */
    156     public ActionContextBase() {
    157         this(new ContextBase());
    158     }
    159 
    160     // -------------------------------
    161     // General Application Support
    162     // -------------------------------
    163     public void release() {
    164         this.token = null;
    165     }
    166 
    167     public abstract Map getApplicationScope();
    168 
    169     public abstract Map getRequestScope();
    170 
    171     public abstract Map getSessionScope();
    172 
    173     public Map getScope(String scopeName) {
    174         if (REQUEST_SCOPE.equals(scopeName)) {
    175             return this.getRequestScope();
    176         }
    177 
    178         if (SESSION_SCOPE.equals(scopeName)) {
    179             return this.getSessionScope();
    180         }
    181 
    182         if (APPLICATION_SCOPE.equals(scopeName)) {
    183             return this.getApplicationScope();
    184         }
    185 
    186         throw new IllegalArgumentException("Invalid scope: " + scopeName);
    187     }
    188 
    189     // -------------------------------
    190     // General Struts properties
    191     // -------------------------------
    192     public void setAction(Action action) {
    193         this.put(ACTION_KEY, action);
    194     }
    195 
    196     public Action getAction() {
    197         return (Action) this.get(ACTION_KEY);
    198     }
    199 
    200     public void setActionForm(ActionForm form) {
    201         this.put(ACTION_FORM_KEY, form);
    202     }
    203 
    204     public ActionForm getActionForm() {
    205         return (ActionForm) this.get(ACTION_FORM_KEY);
    206     }
    207 
    208     public void setActionConfig(ActionConfig config) {
    209         this.put(ACTION_CONFIG_KEY, config);
    210     }
    211 
    212     public ActionConfig getActionConfig() {
    213         return (ActionConfig) this.get(ACTION_CONFIG_KEY);
    214     }
    215 
    216     public void setForwardConfig(ForwardConfig forward) {
    217         this.put(FORWARD_CONFIG_KEY, forward);
    218     }
    219 
    220     public ForwardConfig getForwardConfig() {
    221         return (ForwardConfig) this.get(FORWARD_CONFIG_KEY);
    222     }
    223 
    224     public void setInclude(String include) {
    225         this.put(INCLUDE_KEY, include);
    226     }
    227 
    228     public String getInclude() {
    229         return (String) this.get(INCLUDE_KEY);
    230     }
    231 
    232     public Boolean getFormValid() {
    233         return (Boolean) this.get(VALID_KEY);
    234     }
    235 
    236     public void setFormValid(Boolean valid) {
    237         this.put(VALID_KEY, valid);
    238     }
    239 
    240     public ModuleConfig getModuleConfig() {
    241         return (ModuleConfig) this.get(MODULE_CONFIG_KEY);
    242     }
    243 
    244     public void setModuleConfig(ModuleConfig config) {
    245         this.put(MODULE_CONFIG_KEY, config);
    246     }
    247 
    248     public Exception getException() {
    249         return (Exception) this.get(EXCEPTION_KEY);
    250     }
    251 
    252     public void setException(Exception e) {
    253         this.put(EXCEPTION_KEY, e);
    254     }
    255 
    256     // -------------------------------
    257     // ActionMessage Processing
    258     // -------------------------------
    259     public void addMessages(ActionMessages messages) {
    260         this.addActionMessages(MESSAGE_ACTION_MESSAGES_KEY, messages);
    261     }
    262 
    263     public void addErrors(ActionMessages errors) {
    264         this.addActionMessages(ERROR_ACTION_MESSAGES_KEY, errors);
    265     }
    266 
    267     public ActionMessages getErrors() {
    268         return (ActionMessages) this.get(ERROR_ACTION_MESSAGES_KEY);
    269     }
    270 
    271     public ActionMessages getMessages() {
    272         return (ActionMessages) this.get(MESSAGE_ACTION_MESSAGES_KEY);
    273     }
    274 
    275     public void saveErrors(ActionMessages errors) {
    276         this.saveActionMessages(ERROR_ACTION_MESSAGES_KEY, errors);
    277     }
    278 
    279     public void saveMessages(ActionMessages messages) {
    280         this.saveActionMessages(MESSAGE_ACTION_MESSAGES_KEY, messages);
    281     }
    282 
    283     // ISSUE: do we want to add this to the public API?
    284 
    285     /**
    286      * <p> Add the given messages to a cache stored in this Context, under
    287      * key. </p>
    288      *
    289      * @param key      The attribute name for the message cache
    290      * @param messages The ActionMessages to add
    291      */
    292     public void addActionMessages(String key, ActionMessages messages) {
    293         if (messages == null) {
    294             // bad programmer! *slap*
    295             return;
    296         }
    297 
    298         // get any existing messages from the request, or make a new one
    299         ActionMessages requestMessages = (ActionMessages) this.get(key);
    300 
    301         if (requestMessages == null) {
    302             requestMessages = new ActionMessages();
    303         }
    304 
    305         // add incoming messages
    306         requestMessages.add(messages);
    307 
    308         // if still empty, just wipe it out from the request
    309         this.remove(key);
    310 
    311         // save the messages
    312         this.saveActionMessages(key, requestMessages);
    313     }
    314 
    315     // ISSUE: do we want to add this to the public API?
    316 
    317     /**
    318      * <p> Save the given ActionMessages into the request scope under the
    319      * given key, clearing the attribute if the messages are empty or null.
    320      * </p>
    321      *
    322      * @param key      The attribute name for the message cache
    323      * @param messages The ActionMessages to add
    324      */
    325     public void saveActionMessages(String key, ActionMessages messages) {
    326         this.saveActionMessages(REQUEST_SCOPE, key, messages);
    327     }
    328 
    329     /**
    330      * <p>Save the given <code>messages</code> into the map identified by the
    331      * given <code>scopeId</code> under the given <code>key</code>.</p>
    332      *
    333      * @param scopeId
    334      * @param key
    335      * @param messages
    336      */
    337     public void saveActionMessages(String scopeId, String key,
    338         ActionMessages messages) {
    339         Map scope = getScope(scopeId);
    340 
    341         if ((messages == null) || messages.isEmpty()) {
    342             scope.remove(key);
    343 
    344             return;
    345         }
    346 
    347         scope.put(key, messages);
    348     }
    349 
    350     // ISSUE: Should we deprecate this method, since it is misleading?
    351     // Do we need it for backward compatibility?
    352 
    353     /**
    354      * <p> Adapt a legacy form of SaveMessages to the ActionContext API by
    355      * storing the ActoinMessages under the default scope.
    356      *
    357      * @param scope    The scope for the internal cache
    358      * @param messages ActionMesssages to cache
    359      */
    360     public void saveMessages(String scope, ActionMessages messages) {
    361         this.saveMessages(messages);
    362     }
    363 
    364     // -------------------------------
    365     // Token Processing
    366     // -------------------------------
    367     // ISSUE: Should there be a getToken method?
    368     // Is there a problem trying to map this method from Action
    369     // to ActionContext when we aren't necessarily sure how token
    370     // processing maps into a context with an ill-defined "session"?
    371     // There's no getToken() method, but maybe there should be. *
    372     public void saveToken() {
    373         String token = this.generateToken();
    374 
    375         this.put(TRANSACTION_TOKEN_KEY, token);
    376     }
    377 
    378     public String generateToken() {
    379         return token.generateToken(getTokenGeneratorId());
    380     }
    381 
    382     // ISSUE: The original implementation was based on the HttpSession
    383     // identifier; what would be a way to do that without depending on the
    384     // Servlet API?
    385     // REPLY: uuid's
    386     // http://java.sun.com/products/jini/2.0/doc/specs/api/net/jini/id/Uuid.html.md
    387     protected String getTokenGeneratorId() {
    388         return "";
    389     }
    390 
    391     public boolean isTokenValid() {
    392         return this.isTokenValid(false);
    393     }
    394 
    395     public boolean isTokenValid(boolean reset) {
    396         // Retrieve the transaction token from this session, and
    397         // reset it if requested
    398         String saved = (String) this.get(TRANSACTION_TOKEN_KEY);
    399 
    400         if (saved == null) {
    401             return false;
    402         }
    403 
    404         if (reset) {
    405             this.resetToken();
    406         }
    407 
    408         // Retrieve the transaction token included in this request
    409         String token = (String) this.get(TOKEN_KEY);
    410 
    411         if (token == null) {
    412             return false;
    413         }
    414 
    415         return saved.equals(token);
    416     }
    417 
    418     public void resetToken() {
    419         this.remove(TRANSACTION_TOKEN_KEY);
    420     }
    421 
    422     // -------------------------------
    423     // Cancel Processing
    424     // -------------------------------
    425     public Boolean getCancelled() {
    426         return (Boolean) this.get(CANCEL_KEY);
    427     }
    428 
    429     public void setCancelled(Boolean cancelled) {
    430         this.put(CANCEL_KEY, cancelled);
    431     }
    432 
    433     // -------------------------------
    434     // MessageResources Processing
    435     // -------------------------------
    436     public void setMessageResources(MessageResources messageResources) {
    437         this.put(MESSAGE_RESOURCES_KEY, messageResources);
    438     }
    439 
    440     public MessageResources getMessageResources() {
    441         return (MessageResources) this.get(MESSAGE_RESOURCES_KEY);
    442     }
    443 
    444     public MessageResources getMessageResources(String key) {
    445         return (MessageResources) this.get(key);
    446     }
    447 
    448     // -------------------------------
    449     // Locale Processing
    450     // -------------------------------
    451     public void setLocale(Locale locale) {
    452         this.put(LOCALE_KEY, locale);
    453     }
    454 
    455     public Locale getLocale() {
    456         return (Locale) this.get(LOCALE_KEY);
    457     }
    458 
    459     // -------------------------------
    460     // Convenience Methods: these are not part of the formal ActionContext API,
    461     // but are likely to be commonly useful.
    462     // -------------------------------
    463 
    464     /**
    465      * <p> Provide the currently configured commons-logging <code>Log</code>
    466      * instance. </p>
    467      *
    468      * @return Log instance for this context
    469      */
    470     public Log getLogger() {
    471         return this.logger;
    472     }
    473 
    474     /**
    475      * <p> Set the commons-logging <code>Log</code> instance which should be
    476      * used to LOG messages. This is initialized at instantiation time but may
    477      * be overridden. Be advised not to set the value to null, as
    478      * <code>ActionContextBase</code> uses the logger for some of its own
    479      * operations. </p>
    480      */
    481     public void setLogger(Log logger) {
    482         this.logger = logger;
    483     }
    484 
    485     /**
    486      * <p> Using this <code>ActionContext</code>'s default
    487      * <code>ModuleConfig</code>, return an existing <code>ActionForm</code>
    488      * in the specified scope, or create a new one and add it to the specified
    489      * scope. </p>
    490      *
    491      * @param formName  The name attribute of our ActionForm
    492      * @param scopeName The scope identier (request, session)
    493      * @return The ActionForm for this request
    494      * @throws IllegalAccessException If object cannot be created
    495      * @throws InstantiationException If object cannot be created
    496      * @see this.findOrCreateActionForm(String, String, ModuleConfig)
    497      */
    498     public ActionForm findOrCreateActionForm(String formName, String scopeName)
    499         throws IllegalAccessException, InstantiationException {
    500         return this.findOrCreateActionForm(formName, scopeName,
    501             this.getModuleConfig());
    502     }
    503 
    504     /**
    505      * <p> In the context of the given <code>ModuleConfig</code> and this
    506      * <code>ActionContext</code>, look for an existing
    507      * <code>ActionForm</code> in the specified scope. If one is found, return
    508      * it; otherwise, create a new instance, add it to that scope, and then
    509      * return it. </p>
    510      *
    511      * @param formName  The name attribute of our ActionForm
    512      * @param scopeName The scope identier (request, session)
    513      * @return The ActionForm for this request
    514      * @throws IllegalAccessException   If object cannot be created
    515      * @throws InstantiationException   If object cannot be created
    516      * @throws IllegalArgumentException If form config is missing from module
    517      *                                  or scopeName is invalid
    518      */
    519     public ActionForm findOrCreateActionForm(String formName, String scopeName,
    520         ModuleConfig moduleConfig)
    521         throws IllegalAccessException, InstantiationException {
    522         Map scope = this.getScope(scopeName);
    523 
    524         ActionForm instance;
    525         FormBeanConfig formBeanConfig =
    526             moduleConfig.findFormBeanConfig(formName);
    527 
    528         if (formBeanConfig == null) {
    529             throw new IllegalArgumentException("No form config found under "
    530                 + formName + " in module " + moduleConfig.getPrefix());
    531         }
    532 
    533         instance = (ActionForm) scope.get(formName);
    534 
    535         // ISSUE: Can we recycle the existing instance (if any)?
    536         if (instance != null) {
    537             getLogger().trace("Found an instance in scope " + scopeName
    538                 + "; test for reusability");
    539 
    540             if (formBeanConfig.canReuse(instance)) {
    541                 return instance;
    542             }
    543         }
    544 
    545         ActionForm form = formBeanConfig.createActionForm(this);
    546 
    547         // ISSUE: Should we check this call to put?
    548         scope.put(formName, form);
    549 
    550         return form;
    551     }
    552 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
