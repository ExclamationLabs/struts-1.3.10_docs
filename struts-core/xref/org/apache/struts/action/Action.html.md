[View Javadoc](../../../../../apidocs/org/apache/struts/action/Action.html.md)


    1   /*
    2    * $Id: Action.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.config.ModuleConfig;
    25  import org.apache.struts.util.MessageResources;
    26  import org.apache.struts.util.ModuleUtils;
    27  import org.apache.struts.util.RequestUtils;
    28  import org.apache.struts.util.TokenProcessor;
    29  
    30  import javax.servlet.ServletContext;
    31  import javax.servlet.ServletRequest;
    32  import javax.servlet.ServletResponse;
    33  import javax.servlet.http.HttpServletRequest;
    34  import javax.servlet.http.HttpServletResponse;
    35  import javax.servlet.http.HttpSession;
    36  
    37  import java.util.Locale;
    38  
    39  /**
    40   * <p>An <strong>Action</strong> is an adapter between the contents of an
    41   * incoming HTTP request and the corresponding business logic that should be
    42   * executed to process this request. The controller (RequestProcessor) will
    43   * select an appropriate Action for each request, create an instance (if
    44   * necessary), and call the <code>execute</code> method.</p>
    45   *
    46   * <p>Actions must be programmed in a thread-safe manner, because the
    47   * controller will share the same instance for multiple simultaneous requests.
    48   * This means you should design with the following items in mind: </p>
    49   *
    50   * <ul>
    51   *
    52   * <li>Instance and static variables MUST NOT be used to store information
    53   * related to the state of a particular request. They MAY be used to share
    54   * global resources across requests for the same action.</li>
    55   *
    56   * <li>Access to other resources (JavaBeans, session variables, etc.) MUST be
    57   * synchronized if those resources require protection. (Generally, however,
    58   * resource classes should be designed to provide their own protection where
    59   * necessary.</li>
    60   *
    61   * </ul>
    62   *
    63   * <p>When an <code>Action</code> instance is first created, the controller
    64   * will call <code>setServlet</code> with a non-null argument to identify the
    65   * servlet instance to which this Action is attached. When the servlet is to
    66   * be shut down (or restarted), the <code>setServlet</code> method will be
    67   * called with a <code>null</code> argument, which can be used to clean up any
    68   * allocated resources in use by this Action.</p>
    69   *
    70   * @version $Rev: 471754 $ $Date: 2005-08-26 21:58:39 -0400 (Fri, 26 Aug 2005)
    71   *          $
    72   */
    73  public class Action {
    74      /**
    75       * <p>An instance of <code>TokenProcessor</code> to use for token
    76       * functionality.</p>
    77       */
    78      private static TokenProcessor token = TokenProcessor.getInstance();
    79  
    80      // NOTE: We can make the tken  variable protected and remove Action's
    81      // token methods or leave it private and allow the token methods to
    82      // delegate their calls.
    83      // ----------------------------------------------------- Instance Variables
    84  
    85      /**
    86       * <p>The servlet to which we are attached.</p>
    87       */
    88      protected transient ActionServlet servlet = null;
    89  
    90      // ------------------------------------------------------------- Properties
    91  
    92      /**
    93       * <p>Return the servlet instance to which we are attached.</p>
    94       *
    95       * @return The servlet instance to which we are attached.
    96       */
    97      public ActionServlet getServlet() {
    98          return (this.servlet);
    99      }
    100 
    101     /**
    102      * <p>Set the servlet instance to which we are attached (if
    103      * <code>servlet</code> is non-null), or release any allocated resources
    104      * (if <code>servlet</code> is null).</p>
    105      *
    106      * @param servlet The new controller servlet, if any
    107      */
    108     public void setServlet(ActionServlet servlet) {
    109         this.servlet = servlet;
    110 
    111         // :FIXME: Is this suppose to release resources?
    112     }
    113 
    114     // --------------------------------------------------------- Public Methods
    115 
    116     /**
    117      * <p>Process the specified non-HTTP request, and create the corresponding
    118      * non-HTTP response (or forward to another web component that will create
    119      * it), with provision for handling exceptions thrown by the business
    120      * logic. Return an {@link ActionForward} instance describing where and
    121      * how control should be forwarded, or <code>null</code> if the response
    122      * has already been completed.</p>
    123      *
    124      * <p>The default implementation attempts to forward to the HTTP version
    125      * of this method.</p>
    126      *
    127      * @param mapping  The ActionMapping used to select this instance
    128      * @param form     The optional ActionForm bean for this request (if any)
    129      * @param request  The non-HTTP request we are processing
    130      * @param response The non-HTTP response we are creating
    131      * @return The forward to which control should be transferred, or
    132      *         <code>null</code> if the response has been completed.
    133      * @throws Exception if the application business logic throws an
    134      *                   exception.
    135      * @since Struts 1.1
    136      */
    137     public ActionForward execute(ActionMapping mapping, ActionForm form,
    138         ServletRequest request, ServletResponse response)
    139         throws Exception {
    140         try {
    141             return execute(mapping, form, (HttpServletRequest) request,
    142                 (HttpServletResponse) response);
    143         } catch (ClassCastException e) {
    144             return null;
    145         }
    146     }
    147 
    148     /**
    149      * <p>Process the specified HTTP request, and create the corresponding
    150      * HTTP response (or forward to another web component that will create
    151      * it), with provision for handling exceptions thrown by the business
    152      * logic. Return an {@link ActionForward} instance describing where and
    153      * how control should be forwarded, or <code>null</code> if the response
    154      * has already been completed.</p>
    155      *
    156      * @param mapping  The ActionMapping used to select this instance
    157      * @param form     The optional ActionForm bean for this request (if any)
    158      * @param request  The HTTP request we are processing
    159      * @param response The HTTP response we are creating
    160      * @return The forward to which control should be transferred, or
    161      *         <code>null</code> if the response has been completed.
    162      * @throws Exception if the application business logic throws an
    163      *                   exception
    164      * @since Struts 1.1
    165      */
    166     public ActionForward execute(ActionMapping mapping, ActionForm form,
    167         HttpServletRequest request, HttpServletResponse response)
    168         throws Exception {
    169         return null;
    170     }
    171 
    172     // ---------------------------------------------------- Protected Methods
    173 
    174     /**
    175      * Adds the specified messages keys into the appropriate request attribute
    176      * for use by the &lt.html.md:messages&gt; tag (if messages="true" is set),
    177      * if any messages are required. Initialize the attribute if it has not
    178      * already been. Otherwise, ensure that the request attribute is not set.
    179      *
    180      * @param request  The servlet request we are processing
    181      * @param messages Messages object
    182      * @since Struts 1.2.1
    183      */
    184     protected void addMessages(HttpServletRequest request,
    185         ActionMessages messages) {
    186         if (messages == null) {
    187             //  bad programmer! *slap*
    188             return;
    189         }
    190 
    191         // get any existing messages from the request, or make a new one
    192         ActionMessages requestMessages =
    193             (ActionMessages) request.getAttribute(Globals.MESSAGE_KEY);
    194 
    195         if (requestMessages == null) {
    196             requestMessages = new ActionMessages();
    197         }
    198 
    199         // add incoming messages
    200         requestMessages.add(messages);
    201 
    202         // if still empty, just wipe it out from the request
    203         if (requestMessages.isEmpty()) {
    204             request.removeAttribute(Globals.MESSAGE_KEY);
    205 
    206             return;
    207         }
    208 
    209         // Save the messages
    210         request.setAttribute(Globals.MESSAGE_KEY, requestMessages);
    211     }
    212 
    213     /**
    214      * Adds the specified errors keys into the appropriate request attribute
    215      * for use by the &lt.html.md:errors&gt; tag, if any messages are required.
    216      * Initialize the attribute if it has not already been. Otherwise, ensure
    217      * that the request attribute is not set.
    218      *
    219      * @param request The servlet request we are processing
    220      * @param errors  Errors object
    221      * @since Struts 1.2.1
    222      */
    223     protected void addErrors(HttpServletRequest request, ActionMessages errors) {
    224         if (errors == null) {
    225             //  bad programmer! *slap*
    226             return;
    227         }
    228 
    229         // get any existing errors from the request, or make a new one
    230         ActionMessages requestErrors =
    231             (ActionMessages) request.getAttribute(Globals.ERROR_KEY);
    232 
    233         if (requestErrors == null) {
    234             requestErrors = new ActionMessages();
    235         }
    236 
    237         // add incoming errors
    238         requestErrors.add(errors);
    239 
    240         // if still empty, just wipe it out from the request
    241         if (requestErrors.isEmpty()) {
    242             request.removeAttribute(Globals.ERROR_KEY);
    243 
    244             return;
    245         }
    246 
    247         // Save the errors
    248         request.setAttribute(Globals.ERROR_KEY, requestErrors);
    249     }
    250 
    251     /**
    252      * <p>Generate a new transaction token, to be used for enforcing a single
    253      * request for a particular transaction.</p>
    254      *
    255      * @param request The request we are processing
    256      * @return The new transaction token.
    257      */
    258     protected String generateToken(HttpServletRequest request) {
    259         return token.generateToken(request);
    260     }
    261 
    262     /**
    263      * Retrieves any existing errors placed in the request by previous
    264      * actions. This method could be called instead of creating a <code>new
    265      * ActionMessages()</code> at the beginning of an <code>Action</code>.
    266      * This will prevent saveErrors() from wiping out any existing Errors
    267      *
    268      * @param request The servlet request we are processing
    269      * @return the Errors that already exist in the request, or a new
    270      *         ActionMessages object if empty.
    271      * @since Struts 1.2.1
    272      */
    273     protected ActionMessages getErrors(HttpServletRequest request) {
    274         ActionMessages errors =
    275             (ActionMessages) request.getAttribute(Globals.ERROR_KEY);
    276 
    277         if (errors == null) {
    278             errors = new ActionMessages();
    279         }
    280 
    281         return errors;
    282     }
    283 
    284     /**
    285      * <p>Return the user's currently selected Locale.</p>
    286      *
    287      * @param request The request we are processing
    288      * @return The user's currently selected Locale.
    289      */
    290     protected Locale getLocale(HttpServletRequest request) {
    291         return RequestUtils.getUserLocale(request, null);
    292     }
    293 
    294     /**
    295      * <p> Retrieves any existing messages placed in the request by previous
    296      * actions. This method could be called instead of creating a <code>new
    297      * ActionMessages()</code> at the beginning of an <code>Action</code> This
    298      * will prevent saveMessages() from wiping out any existing Messages </p>
    299      *
    300      * @param request The servlet request we are processing
    301      * @return the Messages that already exist in the request, or a new
    302      *         ActionMessages object if empty.
    303      * @since Struts 1.2.1
    304      */
    305     protected ActionMessages getMessages(HttpServletRequest request) {
    306         ActionMessages messages =
    307             (ActionMessages) request.getAttribute(Globals.MESSAGE_KEY);
    308 
    309         if (messages == null) {
    310             messages = new ActionMessages();
    311         }
    312 
    313         return messages;
    314     }
    315 
    316     /**
    317      * <p>Return the default message resources for the current module.</p>
    318      *
    319      * @param request The servlet request we are processing
    320      * @return The default message resources for the current module.
    321      * @since Struts 1.1
    322      */
    323     protected MessageResources getResources(HttpServletRequest request) {
    324         return ((MessageResources) request.getAttribute(Globals.MESSAGES_KEY));
    325     }
    326 
    327     /**
    328      * <p>Return the specified message resources for the current module.</p>
    329      *
    330      * @param request The servlet request we are processing
    331      * @param key     The key specified in the message-resources element for
    332      *                the requested bundle.
    333      * @return The specified message resource for the current module.
    334      * @since Struts 1.1
    335      */
    336     protected MessageResources getResources(HttpServletRequest request,
    337         String key) {
    338         // Identify the current module
    339         ServletContext context = getServlet().getServletContext();
    340         ModuleConfig moduleConfig =
    341             ModuleUtils.getInstance().getModuleConfig(request, context);
    342 
    343         // Return the requested message resources instance
    344         return (MessageResources) context.getAttribute(key
    345             + moduleConfig.getPrefix());
    346     }
    347 
    348     /**
    349      * <p>Returns <code>true</code> if the current form's cancel button was
    350      * pressed. This method will check if the <code>Globals.CANCEL_KEY</code>
    351      * request attribute has been set, which normally occurs if the cancel
    352      * button generated by <strong>CancelTag</strong> was pressed by the user
    353      * in the current request. If <code>true</code>, validation performed by
    354      * an <strong>ActionForm</strong>'s <code>validate()</code> method will
    355      * have been skipped by the controller servlet.</p>
    356      *
    357      * <p> Since Action 1.3.0, the mapping for a cancellable Action must also have
    358      * the new "cancellable" property set to true. If "cancellable" is not set, and
    359      * the magic Cancel token is found in the request, the standard Composable
    360      * Request Processor will throw an InvalidCancelException. </p>
    361      *
    362      * @param request The servlet request we are processing
    363      * @return <code>true</code> if the cancel button was pressed;
    364      *         <code>false</code> otherwise.
    365      */
    366     protected boolean isCancelled(HttpServletRequest request) {
    367         return (request.getAttribute(Globals.CANCEL_KEY) != null);
    368     }
    369 
    370     /**
    371      * <p>Return <code>true</code> if there is a transaction token stored in
    372      * the user's current session, and the value submitted as a request
    373      * parameter with this action matches it. Returns <code>false</code> under
    374      * any of the following circumstances:</p>
    375      *
    376      * <ul>
    377      *
    378      * <li>No session associated with this request</li>
    379      *
    380      * <li>No transaction token saved in the session</li>
    381      *
    382      * <li>No transaction token included as a request parameter</li>
    383      *
    384      * <li>The included transaction token value does not match the transaction
    385      * token in the user's session</li>
    386      *
    387      * </ul>
    388      *
    389      * @param request The servlet request we are processing
    390      * @return <code>true</code> if there is a transaction token and it is
    391      *         valid; <code>false</code> otherwise.
    392      */
    393     protected boolean isTokenValid(HttpServletRequest request) {
    394         return token.isTokenValid(request, false);
    395     }
    396 
    397     /**
    398      * <p>Return <code>true</code> if there is a transaction token stored in
    399      * the user's current session, and the value submitted as a request
    400      * parameter with this action matches it. Returns <code>false</code> under
    401      * any of the following circumstances:</p>
    402      *
    403      * <ul>
    404      *
    405      * <li>No session associated with this request</li> <li>No transaction
    406      * token saved in the session</li>
    407      *
    408      * <li>No transaction token included as a request parameter</li>
    409      *
    410      * <li>The included transaction token value does not match the transaction
    411      * token in the user's session</li>
    412      *
    413      * </ul>
    414      *
    415      * @param request The servlet request we are processing
    416      * @param reset   Should we reset the token after checking it?
    417      * @return <code>true</code> if there is a transaction token and it is
    418      *         valid; <code>false</code> otherwise.
    419      */
    420     protected boolean isTokenValid(HttpServletRequest request, boolean reset) {
    421         return token.isTokenValid(request, reset);
    422     }
    423 
    424     /**
    425      * <p>Reset the saved transaction token in the user's session. This
    426      * indicates that transactional token checking will not be needed on the
    427      * next request that is submitted.</p>
    428      *
    429      * @param request The servlet request we are processing
    430      */
    431     protected void resetToken(HttpServletRequest request) {
    432         token.resetToken(request);
    433     }
    434 
    435     /**
    436      * <p>Save the specified error messages keys into the appropriate request
    437      * attribute for use by the &lt.html.md:errors&gt; tag, if any messages are
    438      * required. Otherwise, ensure that the request attribute is not
    439      * created.</p>
    440      *
    441      * @param request The servlet request we are processing
    442      * @param errors  Error messages object
    443      * @since Struts 1.2
    444      */
    445     protected void saveErrors(HttpServletRequest request, ActionMessages errors) {
    446         // Remove any error messages attribute if none are required
    447         if ((errors == null) || errors.isEmpty()) {
    448             request.removeAttribute(Globals.ERROR_KEY);
    449 
    450             return;
    451         }
    452 
    453         // Save the error messages we need
    454         request.setAttribute(Globals.ERROR_KEY, errors);
    455     }
    456 
    457     /**
    458      * <p>Save the specified messages keys into the appropriate request
    459      * attribute for use by the &lt.html.md:messages&gt; tag (if messages="true"
    460      * is set), if any messages are required. Otherwise, ensure that the
    461      * request attribute is not created.</p>
    462      *
    463      * @param request  The servlet request we are processing.
    464      * @param messages The messages to save. <code>null</code> or empty
    465      *                 messages removes any existing ActionMessages in the
    466      *                 request.
    467      * @since Struts 1.1
    468      */
    469     protected void saveMessages(HttpServletRequest request,
    470         ActionMessages messages) {
    471         // Remove any messages attribute if none are required
    472         if ((messages == null) || messages.isEmpty()) {
    473             request.removeAttribute(Globals.MESSAGE_KEY);
    474 
    475             return;
    476         }
    477 
    478         // Save the messages we need
    479         request.setAttribute(Globals.MESSAGE_KEY, messages);
    480     }
    481 
    482     /**
    483      * <p>Save the specified messages keys into the appropriate session
    484      * attribute for use by the &lt.html.md:messages&gt; tag (if messages="true"
    485      * is set), if any messages are required. Otherwise, ensure that the
    486      * session attribute is not created.</p>
    487      *
    488      * @param session  The session to save the messages in.
    489      * @param messages The messages to save. <code>null</code> or empty
    490      *                 messages removes any existing ActionMessages in the
    491      *                 session.
    492      * @since Struts 1.2
    493      */
    494     protected void saveMessages(HttpSession session, ActionMessages messages) {
    495         // Remove any messages attribute if none are required
    496         if ((messages == null) || messages.isEmpty()) {
    497             session.removeAttribute(Globals.MESSAGE_KEY);
    498 
    499             return;
    500         }
    501 
    502         // Save the messages we need
    503         session.setAttribute(Globals.MESSAGE_KEY, messages);
    504     }
    505 
    506     /**
    507      * <p>Save the specified error messages keys into the appropriate session
    508      * attribute for use by the &lt.html.md:messages&gt; tag (if
    509      * messages="false") or &lt.html.md:errors&gt;, if any error messages are
    510      * required. Otherwise, ensure that the session attribute is empty.</p>
    511      *
    512      * @param session The session to save the error messages in.
    513      * @param errors  The error messages to save. <code>null</code> or empty
    514      *                messages removes any existing error ActionMessages in
    515      *                the session.
    516      * @since Struts 1.3
    517      */
    518     protected void saveErrors(HttpSession session, ActionMessages errors) {
    519         // Remove the error attribute if none are required
    520         if ((errors == null) || errors.isEmpty()) {
    521             session.removeAttribute(Globals.ERROR_KEY);
    522 
    523             return;
    524         }
    525 
    526         // Save the errors we need
    527         session.setAttribute(Globals.ERROR_KEY, errors);
    528     }
    529 
    530     /**
    531      * <p>Save a new transaction token in the user's current session, creating
    532      * a new session if necessary.</p>
    533      *
    534      * @param request The servlet request we are processing
    535      */
    536     protected void saveToken(HttpServletRequest request) {
    537         token.saveToken(request);
    538     }
    539 
    540     /**
    541      * <p>Set the user's currently selected <code>Locale</code> into their
    542      * <code>HttpSession</code>.</p>
    543      *
    544      * @param request The request we are processing
    545      * @param locale  The user's selected Locale to be set, or null to select
    546      *                the server's default Locale
    547      */
    548     protected void setLocale(HttpServletRequest request, Locale locale) {
    549         HttpSession session = request.getSession();
    550 
    551         if (locale == null) {
    552             locale = Locale.getDefault();
    553         }
    554 
    555         session.setAttribute(Globals.LOCALE_KEY, locale);
    556     }
    557 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
