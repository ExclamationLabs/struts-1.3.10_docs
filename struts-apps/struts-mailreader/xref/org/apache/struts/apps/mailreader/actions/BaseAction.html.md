[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/mailreader/actions/BaseAction.html.md)


    1   /*
    2    * $Id: BaseAction.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.apps.mailreader.actions;
    23  
    24  import org.apache.commons.beanutils.PropertyUtils;
    25  import org.apache.commons.logging.Log;
    26  import org.apache.commons.logging.LogFactory;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionForward;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.action.ActionMessage;
    31  import org.apache.struts.action.ActionMessages;
    32  import org.apache.struts.action.DynaActionForm;
    33  import org.apache.struts.actions.MappingDispatchAction;
    34  import org.apache.struts.apps.mailreader.Constants;
    35  import org.apache.struts.apps.mailreader.dao.ExpiredPasswordException;
    36  import org.apache.struts.apps.mailreader.dao.Subscription;
    37  import org.apache.struts.apps.mailreader.dao.User;
    38  import org.apache.struts.apps.mailreader.dao.UserDatabase;
    39  
    40  import javax.servlet.ServletException;
    41  import javax.servlet.http.HttpServletRequest;
    42  import javax.servlet.http.HttpSession;
    43  
    44  /**
    45   * <p>
    46   * Base Action for MailReader application.
    47   * </p><p>
    48   * All the BaseAction helper methods are prefixed with "do"
    49   * so that they can be easily distinguished from Struts and Servlet API methods.
    50   * BaseAction subclasses may also have prive "do" helpers of their own.
    51   * </p><p>
    52   * Methods are kept in alphabetical order, to make them easier to find.
    53   * </p>
    54   *
    55   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    56   */
    57  public abstract class BaseAction extends MappingDispatchAction {
    58  
    59      // ---- Fields ----
    60  
    61      /**
    62       * <p>
    63       * Name of username field ["username"].
    64       * </p>
    65       */
    66      public static String USERNAME = "username";
    67  
    68      /**
    69       * <p>
    70       * Name of password field ["password"].
    71       * </p>
    72       */
    73      public static String PASSWORD = "password";
    74  
    75      /**
    76       * <p>
    77       * Name of task field ["task"].
    78       * </p>
    79       */
    80      public final static String TASK = "task";
    81  
    82      // ---- Protected Variables ----
    83  
    84      /**
    85       * <p>
    86       * The <code>Log</code> instance for this application.
    87       * </p>
    88       */
    89      protected Log log = LogFactory.getLog(Constants.PACKAGE);
    90  
    91      // ---- Protected Methods ----
    92  
    93      /**
    94       * <p>
    95       * Store User object in client session.
    96       * If user object is null, any existing user object is removed.
    97       * </p>
    98       *
    99       * @param request The request we are processing
    100      * @param user    The user object returned from the database
    101      */
    102     void doCacheUser(HttpServletRequest request, User user) {
    103 
    104         HttpSession session = request.getSession();
    105         session.setAttribute(Constants.USER_KEY, user);
    106         if (log.isDebugEnabled()) {
    107             log.debug(
    108                     "LogonAction: User '"
    109                             + user.getUsername()
    110                             + "' logged on in session "
    111                             + session.getId());
    112         }
    113     }
    114 
    115     /**
    116      * <p>
    117      * Helper method to log event and cancel transaction.
    118      * </p>
    119      *
    120      * @param session Our HttpSession
    121      * @param method  Method being processed
    122      * @param key     Attrkibute to remove from session, if any
    123      */
    124     protected void doCancel(HttpSession session, String method, String key) {
    125         if (log.isTraceEnabled()) {
    126             StringBuffer sb = new StringBuffer(128);
    127             sb.append(Constants.LOG_CANCEL);
    128             sb.append(method);
    129             log.trace(sb.toString());
    130         }
    131         if (key != null) {
    132             session.removeAttribute(key);
    133         }
    134     }
    135 
    136     /**
    137      * <p>
    138      * Return the local or global forward named "failure"
    139      * or null if there is no such forward.
    140      * </p>
    141      *
    142      * @param mapping Our ActionMapping
    143      * @return Return the mapping named "failure" or null if there is no such mapping.
    144      */
    145     protected ActionForward doFindFailure(ActionMapping mapping) {
    146         if (log.isTraceEnabled()) {
    147             log.trace(Constants.LOG_FAILURE);
    148         }
    149         return mapping.findForward(Constants.FAILURE);
    150     }
    151 
    152     /**
    153      * <p>
    154      * Return the local or global forward named "logon"
    155      * or null if there is no such forward.
    156      * </p>
    157      *
    158      * @param mapping Our ActionMapping
    159      * @return Return the mapping named "logon" or null if there is no such mapping.
    160      */
    161     protected ActionForward doFindLogon(ActionMapping mapping) {
    162         if (log.isTraceEnabled()) {
    163             log.trace(Constants.LOG_LOGON);
    164         }
    165         return mapping.findForward(Constants.LOGON);
    166     }
    167 
    168     /**
    169      * <p>
    170      * Return the mapping labeled "success"
    171      * or null if there is no such mapping.
    172      * </p>
    173      *
    174      * @param mapping Our ActionMapping
    175      * @return Return the mapping named "success" or null if there is no such
    176      *         mapping.
    177      */
    178     protected ActionForward doFindSuccess(ActionMapping mapping) {
    179         if (log.isTraceEnabled()) {
    180             log.trace(Constants.LOG_SUCCESS);
    181         }
    182         return mapping.findForward(Constants.SUCCESS);
    183     }
    184 
    185     /**
    186      * <p>
    187      * Helper method to fetch a String property from a DynaActionForm.
    188      * </p>
    189      * <p>
    190      * Values are returned trimmed of leading and trailing whitespace.
    191      * Zero-length strings are returned as null.
    192      * </p>
    193      *
    194      * @param form     Our DynaActionForm
    195      * @param property The name of the property
    196      * @return The value or null if an error occurs
    197      */
    198     protected String doGet(ActionForm form, String property) {
    199         String initial;
    200         try {
    201             initial = (String) PropertyUtils.getSimpleProperty(form, property);
    202         } catch (Throwable t) {
    203             initial = null;
    204         }
    205         String value = null;
    206         if ((initial != null) && (initial.length() > 0)) {
    207             value = initial.trim();
    208             if (value.length() == 0) {
    209                 value = null;
    210             }
    211         }
    212         return value;
    213     }
    214 
    215     /**
    216      * <p>
    217      * Obtain the cached Subscription object, if any.
    218      * </p>
    219      *
    220      * @param session Our HttpSession
    221      * @return Cached Subscription object or null
    222      */
    223     protected Subscription doGetSubscription(HttpSession session) {
    224         return (Subscription) session.getAttribute(Constants.SUBSCRIPTION_KEY);
    225     }
    226 
    227     /**
    228      * <p>
    229      * Obtain the cached Subscription object, if any.
    230      * </p>
    231      *
    232      * @param request Our HttpServletRequest
    233      * @return Cached Subscription object or null
    234      */
    235     protected Subscription doGetSubscription(HttpServletRequest request) {
    236         HttpSession session = request.getSession();
    237         return doGetSubscription(session);
    238     }
    239 
    240     /**
    241      * <p>
    242      * Confirm user credentials. Post any errors and return User object
    243      * (or null).
    244      * </p>
    245      *
    246      * @param database Database in which to look up the user
    247      * @param username Username specified on the logon form
    248      * @param password Password specified on the logon form
    249      * @param errors   ActionMessages queue to passback errors
    250      * @return Validated User object or null
    251      * @throws org.apache.struts.apps.mailreader.dao.ExpiredPasswordException
    252      *          to be handled by Struts exception
    253      *          processor via the action-mapping
    254      */
    255     User doGetUser(UserDatabase database, String username,
    256                    String password, ActionMessages errors)
    257             throws ExpiredPasswordException {
    258 
    259         User user = null;
    260         if (database == null) {
    261             errors.add(
    262                     ActionMessages.GLOBAL_MESSAGE,
    263                     new ActionMessage("error.database.missing"));
    264         } else {
    265 
    266             if (username.equals("Hermes")) {
    267                 throw new ExpiredPasswordException("Hermes");
    268             }
    269 
    270             user = database.findUser(username);
    271             if ((user != null) && !user.getPassword().equals(password)) {
    272                 user = null;
    273             }
    274             if (user == null) {
    275                 errors.add(
    276                         ActionMessages.GLOBAL_MESSAGE,
    277                         new ActionMessage("error.password.mismatch"));
    278             }
    279         }
    280 
    281         return user;
    282     }
    283 
    284     /**
    285      * <p>
    286      * Confirm user credentials. Post any errors and return User object
    287      * (or null).
    288      * </p>
    289      *
    290      * @param username Username specified on the logon form
    291      * @param password Password specified on the logon form
    292      * @param errors   ActionMessages queue to passback errors
    293      * @return Validated User object or null
    294      * @throws org.apache.struts.apps.mailreader.dao.ExpiredPasswordException
    295      *          to be handled by Struts exception
    296      *          processor via the action-mapping
    297      */
    298     User doGetUser(String username,
    299                    String password, ActionMessages errors)
    300             throws ExpiredPasswordException {
    301 
    302         return doGetUser(doGetUserDatabase(), username, password, errors);
    303     }
    304 
    305     /**
    306      * <p>
    307      * Return a reference to the UserDatabase
    308      * or null if the database is not available.
    309      * </p>
    310      *
    311      * @return a reference to the UserDatabase or null if the database is not
    312      *         available
    313      */
    314     protected UserDatabase doGetUserDatabase() {
    315         return (UserDatabase) servlet.getServletContext().getAttribute(
    316                 Constants.DATABASE_KEY);
    317     }
    318 
    319     /**
    320      * <p>
    321      * Helper method to obtain User form session (if any).
    322      * </p>
    323      *
    324      * @param session Our HttpSession
    325      * @return User object, or null if there is no user.
    326      */
    327     protected User doGetUser(HttpSession session) {
    328         return (User) session.getAttribute(Constants.USER_KEY);
    329     }
    330 
    331     /**
    332      * <p>
    333      * Helper method to obtain User form session (if any).
    334      * </p>
    335      *
    336      * @param request Our HttpServletRequest
    337      * @return User object, or null if there is no user.
    338      */
    339     protected User doGetUser(HttpServletRequest request) {
    340         HttpSession session = request.getSession();
    341         return (User) session.getAttribute(Constants.USER_KEY);
    342     }
    343 
    344     /**
    345      * <p>
    346      * Save any errors and the transactioonal token, and forward to the
    347      * InputForard result.
    348      * </p>
    349      *
    350      * @param mapping Our ActionMapping
    351      * @param request Our HttpServletRequest
    352      * @param errors  Our ActionMessages collectoin
    353      * @return The InputForward for this mappintg
    354      */
    355     protected ActionForward doInputForward(ActionMapping mapping,
    356                                            HttpServletRequest request,
    357                                            ActionMessages errors) {
    358         this.saveErrors(request, errors);
    359         this.saveToken(request);
    360         return (mapping.getInputForward());
    361     }
    362 
    363     /**
    364      * <p>
    365      * Log a "processing" message for an Action.
    366      * </p>
    367      *
    368      * @param mapping Our ActionMapping
    369      * @param method  Name of method being processed
    370      */
    371     protected void doLogProcess(ActionMapping mapping, String method) {
    372         if (log.isDebugEnabled()) {
    373             StringBuffer sb = new StringBuffer(128);
    374             sb.append(" ");
    375             sb.append(mapping.getPath());
    376             sb.append(":");
    377             sb.append(Constants.LOG_PROCESSING);
    378             sb.append(method);
    379             log.debug(sb.toString());
    380         }
    381     }
    382 
    383     /**
    384      * <p>
    385      * Helper method to log event and save token.
    386      * </p>
    387      *
    388      * @param request Our HttpServletRequest
    389      */
    390     protected void doSaveToken(HttpServletRequest request) {
    391         if (log.isTraceEnabled()) {
    392             log.trace(Constants.LOG_TOKEN);
    393         }
    394         saveToken(request);
    395     }
    396 
    397     /**
    398      * <p>
    399      * Persist the User object, including subscriptions, to the database.
    400      * </p>
    401      *
    402      * @param user Our User object
    403      * @throws javax.servlet.ServletException On any error
    404      */
    405     protected void doSaveUser(User user) throws ServletException {
    406 
    407         final String LOG_DATABASE_SAVE_ERROR =
    408                 " Unexpected error when saving User: ";
    409 
    410         try {
    411             UserDatabase database = doGetUserDatabase();
    412             database.save();
    413         } catch (Exception e) {
    414             String message = LOG_DATABASE_SAVE_ERROR + user.getUsername();
    415             log.error(message, e);
    416             throw new ServletException(message, e);
    417         }
    418     }
    419 
    420     /**
    421      * <p>
    422      * Helper method to inject a String property into a DynaActionForm.
    423      * </p>
    424      *
    425      * @param form     Our DynaActionForm
    426      * @param property The name of the property
    427      * @param value    The value for the property
    428      * @return True if the assignment succeeds
    429      */
    430     protected boolean doSet(ActionForm form, String property, String value) {
    431         try {
    432             DynaActionForm dyna = (DynaActionForm) form;
    433             dyna.set(property, value);
    434         } catch (Throwable t) {
    435             return false;
    436         }
    437         return true;
    438     }
    439 
    440 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
