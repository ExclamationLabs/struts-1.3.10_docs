[View Javadoc](../../../../../apidocs/org/apache/struts/action/RequestProcessor.html.md)


    1   /*
    2    * $Id: RequestProcessor.java 680350 2008-07-28 13:32:29Z niallp $
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
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.config.ActionConfig;
    27  import org.apache.struts.config.ExceptionConfig;
    28  import org.apache.struts.config.ForwardConfig;
    29  import org.apache.struts.config.ModuleConfig;
    30  import org.apache.struts.upload.MultipartRequestWrapper;
    31  import org.apache.struts.util.MessageResources;
    32  import org.apache.struts.util.RequestUtils;
    33  
    34  import javax.servlet.RequestDispatcher;
    35  import javax.servlet.ServletContext;
    36  import javax.servlet.ServletException;
    37  import javax.servlet.http.HttpServletRequest;
    38  import javax.servlet.http.HttpServletResponse;
    39  import javax.servlet.http.HttpSession;
    40  
    41  import java.io.IOException;
    42  
    43  import java.util.HashMap;
    44  import java.util.Iterator;
    45  import java.util.Locale;
    46  
    47  /**
    48   * <p><strong>RequestProcessor</strong> contains the processing logic that the
    49   * {@link ActionServlet} performs as it receives each servlet request from the
    50   * container. You can customize the request processing behavior by subclassing
    51   * this class and overriding the method(s) whose behavior you are interested
    52   * in changing.</p>
    53   *
    54   * @version $Rev: 680350 $ $Date: 2008-07-28 08:32:29 -0500 (Mon, 28 Jul 2008) $
    55   * @since Struts 1.1
    56   */
    57  public class RequestProcessor {
    58      // ----------------------------------------------------- Manifest Constants
    59  
    60      /**
    61       * <p>The request attribute under which the path information is stored for
    62       * processing during a <code>RequestDispatcher.include</code> call.</p>
    63       */
    64      public static final String INCLUDE_PATH_INFO =
    65          "javax.servlet.include.path_info";
    66  
    67      /**
    68       * <p>The request attribute under which the servlet path information is
    69       * stored for processing during a <code>RequestDispatcher.include</code>
    70       * call.</p>
    71       */
    72      public static final String INCLUDE_SERVLET_PATH =
    73          "javax.servlet.include.servlet_path";
    74  
    75      /**
    76       * <p>Commons Logging instance.</p>
    77       */
    78      protected static Log log = LogFactory.getLog(RequestProcessor.class);
    79  
    80      // ----------------------------------------------------- Instance Variables
    81  
    82      /**
    83       * <p>The set of <code>Action</code> instances that have been created and
    84       * initialized, keyed by the fully qualified Java class name of the
    85       * <code>Action</code> class.</p>
    86       */
    87      protected HashMap actions = new HashMap();
    88  
    89      /**
    90       * <p>The <code>ModuleConfiguration</code> with which we are
    91       * associated.</p>
    92       */
    93      protected ModuleConfig moduleConfig = null;
    94  
    95      /**
    96       * <p>The servlet with which we are associated.</p>
    97       */
    98      protected ActionServlet servlet = null;
    99  
    100     // --------------------------------------------------------- Public Methods
    101 
    102     /**
    103      * <p>Clean up in preparation for a shutdown of this application.</p>
    104      */
    105     public void destroy() {
    106         synchronized (this.actions) {
    107             Iterator actions = this.actions.values().iterator();
    108 
    109             while (actions.hasNext()) {
    110                 Action action = (Action) actions.next();
    111 
    112                 action.setServlet(null);
    113             }
    114 
    115             this.actions.clear();
    116         }
    117 
    118         this.servlet = null;
    119     }
    120 
    121     /**
    122      * <p>Initialize this request processor instance.</p>
    123      *
    124      * @param servlet      The ActionServlet we are associated with
    125      * @param moduleConfig The ModuleConfig we are associated with.
    126      * @throws ServletException If an error occor during initialization
    127      */
    128     public void init(ActionServlet servlet, ModuleConfig moduleConfig)
    129         throws ServletException {
    130         synchronized (actions) {
    131             actions.clear();
    132         }
    133 
    134         this.servlet = servlet;
    135         this.moduleConfig = moduleConfig;
    136     }
    137 
    138     /**
    139      * <p>Process an <code>HttpServletRequest</code> and create the
    140      * corresponding <code>HttpServletResponse</code> or dispatch to another
    141      * resource.</p>
    142      *
    143      * @param request  The servlet request we are processing
    144      * @param response The servlet response we are creating
    145      * @throws IOException      if an input/output error occurs
    146      * @throws ServletException if a processing exception occurs
    147      */
    148     public void process(HttpServletRequest request, HttpServletResponse response)
    149         throws IOException, ServletException {
    150         // Wrap multipart requests with a special wrapper
    151         request = processMultipart(request);
    152 
    153         // Identify the path component we will use to select a mapping
    154         String path = processPath(request, response);
    155 
    156         if (path == null) {
    157             return;
    158         }
    159 
    160         if (log.isDebugEnabled()) {
    161             log.debug("Processing a '" + request.getMethod() + "' for path '"
    162                 + path + "'");
    163         }
    164 
    165         // Select a Locale for the current user if requested
    166         processLocale(request, response);
    167 
    168         // Set the content type and no-caching headers if requested
    169         processContent(request, response);
    170         processNoCache(request, response);
    171 
    172         // General purpose preprocessing hook
    173         if (!processPreprocess(request, response)) {
    174             return;
    175         }
    176 
    177         this.processCachedMessages(request, response);
    178 
    179         // Identify the mapping for this request
    180         ActionMapping mapping = processMapping(request, response, path);
    181 
    182         if (mapping == null) {
    183             return;
    184         }
    185 
    186         // Check for any role required to perform this action
    187         if (!processRoles(request, response, mapping)) {
    188             return;
    189         }
    190 
    191         // Process any ActionForm bean related to this request
    192         ActionForm form = processActionForm(request, response, mapping);
    193 
    194         processPopulate(request, response, form, mapping);
    195 
    196         // Validate any fields of the ActionForm bean, if applicable
    197         try {
    198             if (!processValidate(request, response, form, mapping)) {
    199                 return;
    200             }
    201         } catch (InvalidCancelException e) {
    202             ActionForward forward = processException(request, response, e, form, mapping);
    203             processForwardConfig(request, response, forward);
    204             return;
    205         } catch (IOException e) {
    206             throw e;
    207         } catch (ServletException e) {
    208             throw e;
    209         }
    210 
    211         // Process a forward or include specified by this mapping
    212         if (!processForward(request, response, mapping)) {
    213             return;
    214         }
    215 
    216         if (!processInclude(request, response, mapping)) {
    217             return;
    218         }
    219 
    220         // Create or acquire the Action instance to process this request
    221         Action action = processActionCreate(request, response, mapping);
    222 
    223         if (action == null) {
    224             return;
    225         }
    226 
    227         // Call the Action instance itself
    228         ActionForward forward =
    229             processActionPerform(request, response, action, form, mapping);
    230 
    231         // Process the returned ActionForward instance
    232         processForwardConfig(request, response, forward);
    233     }
    234 
    235     // ----------------------------------------------------- Processing Methods
    236 
    237     /**
    238      * <p>Return an <code>Action</code> instance that will be used to process
    239      * the current request, creating a new one if necessary.</p>
    240      *
    241      * @param request  The servlet request we are processing
    242      * @param response The servlet response we are creating
    243      * @param mapping  The mapping we are using
    244      * @return An <code>Action</code> instance that will be used to process
    245      *         the current request.
    246      * @throws IOException if an input/output error occurs
    247      */
    248     protected Action processActionCreate(HttpServletRequest request,
    249         HttpServletResponse response, ActionMapping mapping)
    250         throws IOException {
    251         // Acquire the Action instance we will be using (if there is one)
    252         String className = mapping.getType();
    253 
    254         if (log.isDebugEnabled()) {
    255             log.debug(" Looking for Action instance for class " + className);
    256         }
    257 
    258         // If there were a mapping property indicating whether
    259         // an Action were a singleton or not ([true]),
    260         // could we just instantiate and return a new instance here?
    261         Action instance;
    262 
    263         synchronized (actions) {
    264             // Return any existing Action instance of this class
    265             instance = (Action) actions.get(className);
    266 
    267             if (instance != null) {
    268                 if (log.isTraceEnabled()) {
    269                     log.trace("  Returning existing Action instance");
    270                 }
    271 
    272                 return (instance);
    273             }
    274 
    275             // Create and return a new Action instance
    276             if (log.isTraceEnabled()) {
    277                 log.trace("  Creating new Action instance");
    278             }
    279 
    280             try {
    281                 instance = (Action) RequestUtils.applicationInstance(className);
    282 
    283                 // Maybe we should propagate this exception
    284                 // instead of returning null.
    285             } catch (Exception e) {
    286                 log.error(getInternal().getMessage("actionCreate",
    287                         mapping.getPath()), e);
    288 
    289                 response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    290                     getInternal().getMessage("actionCreate", mapping.getPath()));
    291 
    292                 return (null);
    293             }
    294 
    295             actions.put(className, instance);
    296 
    297             if (instance.getServlet() == null) {
    298                 instance.setServlet(this.servlet);
    299             }
    300         }
    301 
    302         return (instance);
    303     }
    304 
    305     /**
    306      * <p>Retrieve and return the <code>ActionForm</code> associated with this
    307      * mapping, creating and retaining one if necessary. If there is no
    308      * <code>ActionForm</code> associated with this mapping, return
    309      * <code>null</code>.</p>
    310      *
    311      * @param request  The servlet request we are processing
    312      * @param response The servlet response we are creating
    313      * @param mapping  The mapping we are using
    314      * @return The <code>ActionForm</code> associated with this mapping.
    315      */
    316     protected ActionForm processActionForm(HttpServletRequest request,
    317         HttpServletResponse response, ActionMapping mapping) {
    318         // Create (if necessary) a form bean to use
    319         ActionForm instance =
    320             RequestUtils.createActionForm(request, mapping, moduleConfig,
    321                 servlet);
    322 
    323         if (instance == null) {
    324             return (null);
    325         }
    326 
    327         // Store the new instance in the appropriate scope
    328         if (log.isDebugEnabled()) {
    329             log.debug(" Storing ActionForm bean instance in scope '"
    330                 + mapping.getScope() + "' under attribute key '"
    331                 + mapping.getAttribute() + "'");
    332         }
    333 
    334         if ("request".equals(mapping.getScope())) {
    335             request.setAttribute(mapping.getAttribute(), instance);
    336         } else {
    337             HttpSession session = request.getSession();
    338 
    339             session.setAttribute(mapping.getAttribute(), instance);
    340         }
    341 
    342         return (instance);
    343     }
    344 
    345     /**
    346      * <p>Forward or redirect to the specified destination, by the specified
    347      * mechanism.  This method uses a <code>ForwardConfig</code> object
    348      * instead an <code>ActionForward</code>.</p>
    349      *
    350      * @param request  The servlet request we are processing
    351      * @param response The servlet response we are creating
    352      * @param forward  The ForwardConfig controlling where we go next
    353      * @throws IOException      if an input/output error occurs
    354      * @throws ServletException if a servlet exception occurs
    355      */
    356     protected void processForwardConfig(HttpServletRequest request,
    357         HttpServletResponse response, ForwardConfig forward)
    358         throws IOException, ServletException {
    359         if (forward == null) {
    360             return;
    361         }
    362 
    363         if (log.isDebugEnabled()) {
    364             log.debug("processForwardConfig(" + forward + ")");
    365         }
    366 
    367         String forwardPath = forward.getPath();
    368         String uri;
    369 
    370         // If the forward can be unaliased into an action, then use the path of the action
    371         String actionIdPath = RequestUtils.actionIdURL(forward, request, servlet);
    372         if (actionIdPath != null) {
    373             forwardPath = actionIdPath;
    374             ForwardConfig actionIdForward = new ForwardConfig(forward);
    375             actionIdForward.setPath(actionIdPath);
    376             forward = actionIdForward;
    377         }
    378 
    379         // paths not starting with / should be passed through without any
    380         // processing (ie. they're absolute)
    381         if (forwardPath.startsWith("/")) {
    382             // get module relative uri
    383             uri = RequestUtils.forwardURL(request, forward, null);
    384         } else {
    385             uri = forwardPath;
    386         }
    387 
    388         if (forward.getRedirect()) {
    389             // only prepend context path for relative uri
    390             if (uri.startsWith("/")) {
    391                 uri = request.getContextPath() + uri;
    392             }
    393 
    394             response.sendRedirect(response.encodeRedirectURL(uri));
    395         } else {
    396             doForward(uri, request, response);
    397         }
    398     }
    399 
    400     // :FIXME: if Action.execute throws Exception, and Action.process has been
    401     // removed, should the process* methods still throw IOException,
    402     // ServletException?
    403 
    404     /**
    405      * <P>Ask the specified <code>Action</code> instance to handle this
    406      * request. Return the <code>ActionForward</code> instance (if any)
    407      * returned by the called <code>Action</code> for further processing.
    408      * </P>
    409      *
    410      * @param request  The servlet request we are processing
    411      * @param response The servlet response we are creating
    412      * @param action   The Action instance to be used
    413      * @param form     The ActionForm instance to pass to this Action
    414      * @param mapping  The ActionMapping instance to pass to this Action
    415      * @return The <code>ActionForward</code> instance (if any) returned by
    416      *         the called <code>Action</code>.
    417      * @throws IOException      if an input/output error occurs
    418      * @throws ServletException if a servlet exception occurs
    419      */
    420     protected ActionForward processActionPerform(HttpServletRequest request,
    421         HttpServletResponse response, Action action, ActionForm form,
    422         ActionMapping mapping)
    423         throws IOException, ServletException {
    424         try {
    425             return (action.execute(mapping, form, request, response));
    426         } catch (Exception e) {
    427             return (processException(request, response, e, form, mapping));
    428         }
    429     }
    430 
    431     /**
    432      * <p>Removes any <code>ActionMessages</code> object stored in the session
    433      * under <code>Globals.MESSAGE_KEY</code> and <code>Globals.ERROR_KEY</code>
    434      * if the messages' <code>isAccessed</code> method returns true.  This
    435      * allows messages to be stored in the session, display one time, and be
    436      * released here.</p>
    437      *
    438      * @param request  The servlet request we are processing.
    439      * @param response The servlet response we are creating.
    440      * @since Struts 1.2
    441      */
    442     protected void processCachedMessages(HttpServletRequest request,
    443         HttpServletResponse response) {
    444         HttpSession session = request.getSession(false);
    445 
    446         if (session == null) {
    447             return;
    448         }
    449 
    450         // Remove messages as needed
    451         ActionMessages messages =
    452             (ActionMessages) session.getAttribute(Globals.MESSAGE_KEY);
    453 
    454         if (messages != null) {
    455             if (messages.isAccessed()) {
    456                 session.removeAttribute(Globals.MESSAGE_KEY);
    457             }
    458         }
    459 
    460         // Remove error messages as needed
    461         messages = (ActionMessages) session.getAttribute(Globals.ERROR_KEY);
    462 
    463         if (messages != null) {
    464             if (messages.isAccessed()) {
    465                 session.removeAttribute(Globals.ERROR_KEY);
    466             }
    467         }
    468     }
    469 
    470     /**
    471      * <p>Set the default content type (with optional character encoding) for
    472      * all responses if requested.  <strong>NOTE</strong> - This header will
    473      * be overridden automatically if a <code>RequestDispatcher.forward</code>
    474      * call is ultimately invoked.</p>
    475      *
    476      * @param request  The servlet request we are processing
    477      * @param response The servlet response we are creating
    478      */
    479     protected void processContent(HttpServletRequest request,
    480         HttpServletResponse response) {
    481         String contentType =
    482             moduleConfig.getControllerConfig().getContentType();
    483 
    484         if (contentType != null) {
    485             response.setContentType(contentType);
    486         }
    487     }
    488 
    489     /**
    490      * <p>Ask our exception handler to handle the exception. Return the
    491      * <code>ActionForward</code> instance (if any) returned by the called
    492      * <code>ExceptionHandler</code>.</p>
    493      *
    494      * @param request   The servlet request we are processing
    495      * @param response  The servlet response we are processing
    496      * @param exception The exception being handled
    497      * @param form      The ActionForm we are processing
    498      * @param mapping   The ActionMapping we are using
    499      * @return The <code>ActionForward</code> instance (if any) returned by
    500      *         the called <code>ExceptionHandler</code>.
    501      * @throws IOException      if an input/output error occurs
    502      * @throws ServletException if a servlet exception occurs
    503      */
    504     protected ActionForward processException(HttpServletRequest request,
    505         HttpServletResponse response, Exception exception, ActionForm form,
    506         ActionMapping mapping)
    507         throws IOException, ServletException {
    508         // Is there a defined handler for this exception?
    509         ExceptionConfig config = mapping.findException(exception.getClass());
    510 
    511         if (config == null) {
    512             log.warn(getInternal().getMessage("unhandledException",
    513                     exception.getClass()));
    514 
    515             if (exception instanceof IOException) {
    516                 throw (IOException) exception;
    517             } else if (exception instanceof ServletException) {
    518                 throw (ServletException) exception;
    519             } else {
    520                 throw new ServletException(exception);
    521             }
    522         }
    523 
    524         // Use the configured exception handling
    525         try {
    526             ExceptionHandler handler =
    527                 (ExceptionHandler) RequestUtils.applicationInstance(config
    528                     .getHandler());
    529 
    530             return (handler.execute(exception, config, mapping, form, request,
    531                 response));
    532         } catch (Exception e) {
    533             throw new ServletException(e);
    534         }
    535     }
    536 
    537     /**
    538      * <p>Process a forward requested by this mapping (if any). Return
    539      * <code>true</code> if standard processing should continue, or
    540      * <code>false</code> if we have already handled this request.</p>
    541      *
    542      * @param request  The servlet request we are processing
    543      * @param response The servlet response we are creating
    544      * @param mapping  The ActionMapping we are using
    545      * @return <code>true</code> to continue normal processing;
    546      *         <code>false</code> if a response has been created.
    547      * @throws IOException      if an input/output error occurs
    548      * @throws ServletException if a servlet exception occurs
    549      */
    550     protected boolean processForward(HttpServletRequest request,
    551         HttpServletResponse response, ActionMapping mapping)
    552         throws IOException, ServletException {
    553         // Are we going to processing this request?
    554         String forward = mapping.getForward();
    555 
    556         if (forward == null) {
    557             return (true);
    558         }
    559 
    560         // If the forward can be unaliased into an action, then use the path of the action
    561         String actionIdPath = RequestUtils.actionIdURL(forward, this.moduleConfig, this.servlet);
    562         if (actionIdPath != null) {
    563             forward = actionIdPath;
    564         }
    565 
    566         internalModuleRelativeForward(forward, request, response);
    567 
    568         return (false);
    569     }
    570 
    571     /**
    572      * <p>Process an include requested by this mapping (if any). Return
    573      * <code>true</code> if standard processing should continue, or
    574      * <code>false</code> if we have already handled this request.</p>
    575      *
    576      * @param request  The servlet request we are processing
    577      * @param response The servlet response we are creating
    578      * @param mapping  The ActionMapping we are using
    579      * @return <code>true</code> to continue normal processing;
    580      *         <code>false</code> if a response has been created.
    581      * @throws IOException      if an input/output error occurs
    582      * @throws ServletException if thrown by invoked methods
    583      */
    584     protected boolean processInclude(HttpServletRequest request,
    585         HttpServletResponse response, ActionMapping mapping)
    586         throws IOException, ServletException {
    587         // Are we going to processing this request?
    588         String include = mapping.getInclude();
    589 
    590         if (include == null) {
    591             return (true);
    592         }
    593 
    594         // If the forward can be unaliased into an action, then use the path of the action
    595         String actionIdPath = RequestUtils.actionIdURL(include, this.moduleConfig, this.servlet);
    596         if (actionIdPath != null) {
    597             include = actionIdPath;
    598         }
    599 
    600         internalModuleRelativeInclude(include, request, response);
    601 
    602         return (false);
    603     }
    604 
    605     /**
    606      * <p>Automatically select a <code>Locale</code> for the current user, if
    607      * requested. <strong>NOTE</strong> - configuring Locale selection will
    608      * trigger the creation of a new <code>HttpSession</code> if
    609      * necessary.</p>
    610      *
    611      * @param request  The servlet request we are processing
    612      * @param response The servlet response we are creating
    613      */
    614     protected void processLocale(HttpServletRequest request,
    615         HttpServletResponse response) {
    616         // Are we configured to select the Locale automatically?
    617         if (!moduleConfig.getControllerConfig().getLocale()) {
    618             return;
    619         }
    620 
    621         // Has a Locale already been selected?
    622         HttpSession session = request.getSession();
    623 
    624         if (session.getAttribute(Globals.LOCALE_KEY) != null) {
    625             return;
    626         }
    627 
    628         // Use the Locale returned by the servlet container (if any)
    629         Locale locale = request.getLocale();
    630 
    631         if (locale != null) {
    632             if (log.isDebugEnabled()) {
    633                 log.debug(" Setting user locale '" + locale + "'");
    634             }
    635 
    636             session.setAttribute(Globals.LOCALE_KEY, locale);
    637         }
    638     }
    639 
    640     /**
    641      * <p>Select the mapping used to process the selection path for this
    642      * request. If no mapping can be identified, create an error response and
    643      * return <code>null</code>.</p>
    644      *
    645      * @param request  The servlet request we are processing
    646      * @param response The servlet response we are creating
    647      * @param path     The portion of the request URI for selecting a mapping
    648      * @return The mapping used to process the selection path for this
    649      *         request.
    650      * @throws IOException if an input/output error occurs
    651      */
    652     protected ActionMapping processMapping(HttpServletRequest request,
    653         HttpServletResponse response, String path)
    654         throws IOException {
    655         // Is there a mapping for this path?
    656         ActionMapping mapping =
    657             (ActionMapping) moduleConfig.findActionConfig(path);
    658 
    659         // If a mapping is found, put it in the request and return it
    660         if (mapping != null) {
    661             request.setAttribute(Globals.MAPPING_KEY, mapping);
    662 
    663             return (mapping);
    664         }
    665 
    666         // Locate the mapping for unknown paths (if any)
    667         ActionConfig[] configs = moduleConfig.findActionConfigs();
    668 
    669         for (int i = 0; i < configs.length; i++) {
    670             if (configs[i].getUnknown()) {
    671                 mapping = (ActionMapping) configs[i];
    672                 request.setAttribute(Globals.MAPPING_KEY, mapping);
    673 
    674                 return (mapping);
    675             }
    676         }
    677 
    678         // No mapping can be found to process this request
    679         String msg = getInternal().getMessage("processInvalid");
    680 
    681         log.error(msg + " " + path);
    682         response.sendError(HttpServletResponse.SC_NOT_FOUND, msg);
    683 
    684         return null;
    685     }
    686 
    687     /**
    688      * <p>If this is a multipart request, wrap it with a special wrapper.
    689      * Otherwise, return the request unchanged.</p>
    690      *
    691      * @param request The HttpServletRequest we are processing
    692      * @return A wrapped request, if the request is multipart; otherwise the
    693      *         original request.
    694      */
    695     protected HttpServletRequest processMultipart(HttpServletRequest request) {
    696         if (!"POST".equalsIgnoreCase(request.getMethod())) {
    697             return (request);
    698         }
    699 
    700         String contentType = request.getContentType();
    701 
    702         if ((contentType != null)
    703             && contentType.startsWith("multipart/form-data")) {
    704             return (new MultipartRequestWrapper(request));
    705         } else {
    706             return (request);
    707         }
    708     }
    709 
    710     /**
    711      * <p>Set the no-cache headers for all responses, if requested.
    712      * <strong>NOTE</strong> - This header will be overridden automatically if
    713      * a <code>RequestDispatcher.forward</code> call is ultimately
    714      * invoked.</p>
    715      *
    716      * @param request  The servlet request we are processing
    717      * @param response The servlet response we are creating
    718      */
    719     protected void processNoCache(HttpServletRequest request,
    720         HttpServletResponse response) {
    721         if (moduleConfig.getControllerConfig().getNocache()) {
    722             response.setHeader("Pragma", "No-cache");
    723             response.setHeader("Cache-Control", "no-cache,no-store,max-age=0");
    724             response.setDateHeader("Expires", 1);
    725         }
    726     }
    727 
    728     /**
    729      * <p>Identify and return the path component (from the request URI) that
    730      * we will use to select an <code>ActionMapping</code> with which to
    731      * dispatch. If no such path can be identified, create an error response
    732      * and return <code>null</code>.</p>
    733      *
    734      * @param request  The servlet request we are processing
    735      * @param response The servlet response we are creating
    736      * @return The path that will be used to select an action mapping.
    737      * @throws IOException if an input/output error occurs
    738      */
    739     protected String processPath(HttpServletRequest request,
    740         HttpServletResponse response)
    741         throws IOException {
    742         String path;
    743 
    744         // Set per request the original path for postback forms
    745         if (request.getAttribute(Globals.ORIGINAL_URI_KEY) == null) {
    746             request.setAttribute(Globals.ORIGINAL_URI_KEY, request.getServletPath());
    747         }
    748 
    749         // For prefix matching, match on the path info (if any)
    750         path = (String) request.getAttribute(INCLUDE_PATH_INFO);
    751 
    752         if (path == null) {
    753             path = request.getPathInfo();
    754         }
    755 
    756         if ((path != null) && (path.length() > 0)) {
    757             return (path);
    758         }
    759 
    760         // For extension matching, strip the module prefix and extension
    761         path = (String) request.getAttribute(INCLUDE_SERVLET_PATH);
    762 
    763         if (path == null) {
    764             path = request.getServletPath();
    765         }
    766 
    767         String prefix = moduleConfig.getPrefix();
    768 
    769         if (!path.startsWith(prefix)) {
    770             String msg = getInternal().getMessage("processPath");
    771 
    772             log.error(msg + " " + request.getRequestURI());
    773             response.sendError(HttpServletResponse.SC_BAD_REQUEST, msg);
    774 
    775             return null;
    776         }
    777 
    778         path = path.substring(prefix.length());
    779 
    780         int slash = path.lastIndexOf("/");
    781         int period = path.lastIndexOf(".");
    782 
    783         if ((period >= 0) && (period > slash)) {
    784             path = path.substring(0, period);
    785         }
    786 
    787         return (path);
    788     }
    789 
    790     /**
    791      * <p>Populate the properties of the specified <code>ActionForm</code>
    792      * instance from the request parameters included with this request.  In
    793      * addition, request attribute <code>Globals.CANCEL_KEY</code> will be set
    794      * if the request was submitted with a button created by
    795      * <code>CancelTag</code>.</p>
    796      *
    797      * @param request  The servlet request we are processing
    798      * @param response The servlet response we are creating
    799      * @param form     The ActionForm instance we are populating
    800      * @param mapping  The ActionMapping we are using
    801      * @throws ServletException if thrown by RequestUtils.populate()
    802      */
    803     protected void processPopulate(HttpServletRequest request,
    804         HttpServletResponse response, ActionForm form, ActionMapping mapping)
    805         throws ServletException {
    806         if (form == null) {
    807             return;
    808         }
    809 
    810         // Populate the bean properties of this ActionForm instance
    811         if (log.isDebugEnabled()) {
    812             log.debug(" Populating bean properties from this request");
    813         }
    814 
    815         form.setServlet(this.servlet);
    816         form.reset(mapping, request);
    817 
    818         if (mapping.getMultipartClass() != null) {
    819             request.setAttribute(Globals.MULTIPART_KEY,
    820                 mapping.getMultipartClass());
    821         }
    822 
    823         RequestUtils.populate(form, mapping.getPrefix(), mapping.getSuffix(),
    824             request);
    825 
    826         // Set the cancellation request attribute if appropriate
    827         if ((request.getParameter(Globals.CANCEL_PROPERTY) != null)
    828             || (request.getParameter(Globals.CANCEL_PROPERTY_X) != null)) {
    829             request.setAttribute(Globals.CANCEL_KEY, Boolean.TRUE);
    830         }
    831     }
    832 
    833     /**
    834      * <p>General-purpose preprocessing hook that can be overridden as
    835      * required by subclasses. Return <code>true</code> if you want standard
    836      * processing to continue, or <code>false</code> if the response has
    837      * already been completed. The default implementation does nothing.</p>
    838      *
    839      * @param request  The servlet request we are processing
    840      * @param response The servlet response we are creating
    841      * @return <code>true</code> to continue normal processing;
    842      *         <code>false</code> if a response has been created.
    843      */
    844     protected boolean processPreprocess(HttpServletRequest request,
    845         HttpServletResponse response) {
    846         return (true);
    847     }
    848 
    849     /**
    850      * <p>If this action is protected by security roles, make sure that the
    851      * current user possesses at least one of them.  Return <code>true</code>
    852      * to continue normal processing, or <code>false</code> if an appropriate
    853      * response has been created and processing should terminate.</p>
    854      *
    855      * @param request  The servlet request we are processing
    856      * @param response The servlet response we are creating
    857      * @param mapping  The mapping we are using
    858      * @return <code>true</code> to continue normal processing;
    859      *         <code>false</code> if a response has been created.
    860      * @throws IOException      if an input/output error occurs
    861      * @throws ServletException if a servlet exception occurs
    862      */
    863     protected boolean processRoles(HttpServletRequest request,
    864         HttpServletResponse response, ActionMapping mapping)
    865         throws IOException, ServletException {
    866         // Is this action protected by role requirements?
    867         String[] roles = mapping.getRoleNames();
    868 
    869         if ((roles == null) || (roles.length < 1)) {
    870             return (true);
    871         }
    872 
    873         // Check the current user against the list of required roles
    874         for (int i = 0; i < roles.length; i++) {
    875             if (request.isUserInRole(roles[i])) {
    876                 if (log.isDebugEnabled()) {
    877                     log.debug(" User '" + request.getRemoteUser()
    878                         + "' has role '" + roles[i] + "', granting access");
    879                 }
    880 
    881                 return (true);
    882             }
    883         }
    884 
    885         // The current user is not authorized for this action
    886         if (log.isDebugEnabled()) {
    887             log.debug(" User '" + request.getRemoteUser()
    888                 + "' does not have any required role, denying access");
    889         }
    890 
    891         response.sendError(HttpServletResponse.SC_FORBIDDEN,
    892             getInternal().getMessage("notAuthorized", mapping.getPath()));
    893 
    894         return (false);
    895     }
    896 
    897     /**
    898      * <p>If this request was not cancelled, and the request's {@link
    899      * ActionMapping} has not disabled validation, call the
    900      * <code>validate</code> method of the specified {@link ActionForm}, and
    901      * forward to the input path if there were any errors. Return
    902      * <code>true</code> if we should continue processing, or
    903      * <code>false</code> if we have already forwarded control back to the
    904      * input form.</p>
    905      *
    906      * @param request  The servlet request we are processing
    907      * @param response The servlet response we are creating
    908      * @param form     The ActionForm instance we are populating
    909      * @param mapping  The ActionMapping we are using
    910      * @return <code>true</code> to continue normal processing;
    911      *         <code>false</code> if a response has been created.
    912      * @throws IOException      if an input/output error occurs
    913      * @throws ServletException if a servlet exception occurs
    914      * @throws InvalidCancelException if a cancellation is attempted
    915      *         without the proper action configuration.
    916      */
    917     protected boolean processValidate(HttpServletRequest request,
    918         HttpServletResponse response, ActionForm form, ActionMapping mapping)
    919         throws IOException, ServletException, InvalidCancelException {
    920         if (form == null) {
    921             return (true);
    922         }
    923 
    924         // Has validation been turned off for this mapping?
    925         if (!mapping.getValidate()) {
    926             return (true);
    927         }
    928 
    929         // Was this request cancelled? If it has been, the mapping also
    930         // needs to state whether the cancellation is permissable; otherwise
    931         // the cancellation is considered to be a symptom of a programmer
    932         // error or a spoof.
    933         if (request.getAttribute(Globals.CANCEL_KEY) != null) {
    934             if (mapping.getCancellable()) {
    935                 if (log.isDebugEnabled()) {
    936                     log.debug(" Cancelled transaction, skipping validation");
    937                 }
    938                 return (true);
    939             } else {
    940                 request.removeAttribute(Globals.CANCEL_KEY);
    941                 throw new InvalidCancelException();
    942             }
    943         }
    944 
    945         // Call the form bean's validation method
    946         if (log.isDebugEnabled()) {
    947             log.debug(" Validating input form properties");
    948         }
    949 
    950         ActionMessages errors = form.validate(mapping, request);
    951 
    952         if ((errors == null) || errors.isEmpty()) {
    953             if (log.isTraceEnabled()) {
    954                 log.trace("  No errors detected, accepting input");
    955             }
    956 
    957             return (true);
    958         }
    959 
    960         // Special handling for multipart request
    961         if (form.getMultipartRequestHandler() != null) {
    962             if (log.isTraceEnabled()) {
    963                 log.trace("  Rolling back multipart request");
    964             }
    965 
    966             form.getMultipartRequestHandler().rollback();
    967         }
    968 
    969         // Was an input path (or forward) specified for this mapping?
    970         String input = mapping.getInput();
    971 
    972         if (input == null) {
    973             if (log.isTraceEnabled()) {
    974                 log.trace("  Validation failed but no input form available");
    975             }
    976 
    977             response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    978                 getInternal().getMessage("noInput", mapping.getPath()));
    979 
    980             return (false);
    981         }
    982 
    983         // Save our error messages and return to the input form if possible
    984         if (log.isDebugEnabled()) {
    985             log.debug(" Validation failed, returning to '" + input + "'");
    986         }
    987 
    988         request.setAttribute(Globals.ERROR_KEY, errors);
    989 
    990         if (moduleConfig.getControllerConfig().getInputForward()) {
    991             ForwardConfig forward = mapping.findForward(input);
    992 
    993             processForwardConfig(request, response, forward);
    994         } else {
    995             internalModuleRelativeForward(input, request, response);
    996         }
    997 
    998         return (false);
    999     }
    1000 
    1001     /**
    1002      * <p>Do a module relative forward to specified URI using request
    1003      * dispatcher. URI is relative to the current module. The real URI is
    1004      * compute by prefixing the module name.</p> <p>This method is used
    1005      * internally and is not part of the public API. It is advised to not use
    1006      * it in subclasses. </p>
    1007      *
    1008      * @param uri      Module-relative URI to forward to
    1009      * @param request  Current page request
    1010      * @param response Current page response
    1011      * @throws IOException      if an input/output error occurs
    1012      * @throws ServletException if a servlet exception occurs
    1013      * @since Struts 1.1
    1014      */
    1015     protected void internalModuleRelativeForward(String uri,
    1016         HttpServletRequest request, HttpServletResponse response)
    1017         throws IOException, ServletException {
    1018         // Construct a request dispatcher for the specified path
    1019         uri = moduleConfig.getPrefix() + uri;
    1020 
    1021         // Delegate the processing of this request
    1022         // :FIXME: - exception handling?
    1023         if (log.isDebugEnabled()) {
    1024             log.debug(" Delegating via forward to '" + uri + "'");
    1025         }
    1026 
    1027         doForward(uri, request, response);
    1028     }
    1029 
    1030     /**
    1031      * <p>Do a module relative include to specified URI using request
    1032      * dispatcher. URI is relative to the current module. The real URI is
    1033      * compute by prefixing the module name.</p> <p>This method is used
    1034      * internally and is not part of the public API. It is advised to not use
    1035      * it in subclasses.</p>
    1036      *
    1037      * @param uri      Module-relative URI to include
    1038      * @param request  Current page request
    1039      * @param response Current page response
    1040      * @throws IOException      if an input/output error occurs
    1041      * @throws ServletException if a servlet exception occurs
    1042      * @since Struts 1.1
    1043      */
    1044     protected void internalModuleRelativeInclude(String uri,
    1045         HttpServletRequest request, HttpServletResponse response)
    1046         throws IOException, ServletException {
    1047         // Construct a request dispatcher for the specified path
    1048         uri = moduleConfig.getPrefix() + uri;
    1049 
    1050         // Delegate the processing of this request
    1051         // FIXME - exception handling?
    1052         if (log.isDebugEnabled()) {
    1053             log.debug(" Delegating via include to '" + uri + "'");
    1054         }
    1055 
    1056         doInclude(uri, request, response);
    1057     }
    1058 
    1059     /**
    1060      * <p>Do a forward to specified URI using a <code>RequestDispatcher</code>.
    1061      * This method is used by all internal method needing to do a
    1062      * forward.</p>
    1063      *
    1064      * @param uri      Context-relative URI to forward to
    1065      * @param request  Current page request
    1066      * @param response Current page response
    1067      * @throws IOException      if an input/output error occurs
    1068      * @throws ServletException if a servlet exception occurs
    1069      * @since Struts 1.1
    1070      */
    1071     protected void doForward(String uri, HttpServletRequest request,
    1072         HttpServletResponse response)
    1073         throws IOException, ServletException {
    1074         RequestDispatcher rd = getServletContext().getRequestDispatcher(uri);
    1075 
    1076         if (rd == null) {
    1077             response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    1078                 getInternal().getMessage("requestDispatcher", uri));
    1079 
    1080             return;
    1081         }
    1082 
    1083         rd.forward(request, response);
    1084     }
    1085 
    1086     /**
    1087      * <p>Do an include of specified URI using a <code>RequestDispatcher</code>.
    1088      * This method is used by all internal method needing to do an
    1089      * include.</p>
    1090      *
    1091      * @param uri      Context-relative URI to include
    1092      * @param request  Current page request
    1093      * @param response Current page response
    1094      * @throws IOException      if an input/output error occurs
    1095      * @throws ServletException if a servlet exception occurs
    1096      * @since Struts 1.1
    1097      */
    1098     protected void doInclude(String uri, HttpServletRequest request,
    1099         HttpServletResponse response)
    1100         throws IOException, ServletException {
    1101         RequestDispatcher rd = getServletContext().getRequestDispatcher(uri);
    1102 
    1103         if (rd == null) {
    1104             response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    1105                 getInternal().getMessage("requestDispatcher", uri));
    1106 
    1107             return;
    1108         }
    1109 
    1110         rd.include(request, response);
    1111     }
    1112 
    1113     // -------------------------------------------------------- Support Methods
    1114 
    1115     /**
    1116      * <p>Return the <code>MessageResources</code> instance containing our
    1117      * internal message strings.</p>
    1118      *
    1119      * @return The <code>MessageResources</code> instance containing our
    1120      *         internal message strings.
    1121      */
    1122     protected MessageResources getInternal() {
    1123         return (servlet.getInternal());
    1124     }
    1125 
    1126     /**
    1127      * <p>Return the <code>ServletContext</code> for the web application in
    1128      * which we are running.</p>
    1129      *
    1130      * @return The <code>ServletContext</code> for the web application.
    1131      */
    1132     protected ServletContext getServletContext() {
    1133         return (servlet.getServletContext());
    1134     }
    1135 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
