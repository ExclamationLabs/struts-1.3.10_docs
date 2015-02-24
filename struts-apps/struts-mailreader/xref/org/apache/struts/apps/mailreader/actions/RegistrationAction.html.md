[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/mailreader/actions/RegistrationAction.html.md)


    1   /*
    2    * Licensed to the Apache Software Foundation (ASF) under one or more
    3    * contributor license agreements.  See the NOTICE file distributed with
    4    * this work for additional information regarding copyright ownership.
    5    * The ASF licenses this file to You under the Apache License, Version 2.0
    6    * (the "License"); you may not use this file except in compliance with
    7    * the License.  You may obtain a copy of the License at
    8    *
    9    *      http://www.apache.org/licenses/LICENSE-2.0
    10   *
    11   * Unless required by applicable law or agreed to in writing, software
    12   * distributed under the License is distributed on an "AS IS" BASIS,
    13   * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    14   * See the License for the specific language governing permissions and
    15   * limitations under the License.
    16   */
    17  package org.apache.struts.apps.mailreader.actions;
    18  
    19  import org.apache.commons.beanutils.PropertyUtils;
    20  import org.apache.struts.action.ActionForm;
    21  import org.apache.struts.action.ActionForward;
    22  import org.apache.struts.action.ActionMapping;
    23  import org.apache.struts.action.ActionMessage;
    24  import org.apache.struts.action.ActionMessages;
    25  import org.apache.struts.action.DynaActionForm;
    26  import org.apache.struts.apps.mailreader.Constants;
    27  import org.apache.struts.apps.mailreader.dao.ExpiredPasswordException;
    28  import org.apache.struts.apps.mailreader.dao.User;
    29  import org.apache.struts.apps.mailreader.dao.UserDatabase;
    30  
    31  import javax.servlet.ServletException;
    32  import javax.servlet.http.HttpServletRequest;
    33  import javax.servlet.http.HttpServletResponse;
    34  import javax.servlet.http.HttpSession;
    35  import java.lang.reflect.InvocationTargetException;
    36  
    37  /**
    38   * <p>
    39   * Provide an Edit method for retrieving an existing user,
    40   * and a Save method for updating or inserting a user.
    41   * </p><p>
    42   * Both methods utilize a RegistrationForm to obtain or expose User details.
    43   * If Save is used to create a user,
    44   * additional validations ensure input is nominal.
    45   * When a user is created,
    46   * Save also handles the initial logon.
    47   * </p>
    48   */
    49  public final class RegistrationAction extends BaseAction {
    50  
    51      // --- Public Constants --
    52  
    53      /**
    54       * <p>
    55       * Name of fromAddress field ["fromAddress"].
    56       * </p>
    57       */
    58      public final static String FROM_ADDRESS = "fromAddress";
    59  
    60      /**
    61       * <p>
    62       * Name of fullName field ["fullName"].
    63       * </p>
    64       */
    65      public final static String FULL_NAME = "fullName";
    66  
    67      /**
    68       * <p>
    69       * Name of password confirmation field ["password2"].
    70       * </p>
    71       */
    72      public final static String PASSWORD2 = "password2";
    73  
    74      /**
    75       * <p>
    76       * Name of replyToAddress field ["replyToAddress"].
    77       * </p>
    78       */
    79      public final static String REPLY_TO_ADDRESS = "replyToAddress";
    80  
    81      // ---- Private Methods ----
    82  
    83      /**
    84       * <p>
    85       * The message prefix to use when populating a Registration Form.
    86       * </p>
    87       */
    88      final String LOG_REGISTRATION_POPULATE = "RegistrationForm.populate";
    89  
    90      /**
    91       * <p>
    92       * Helper method to post error message when user already exists.
    93       * </p>
    94       *
    95       * @param username Existing username
    96       * @param errors   Our ActionMessages collection
    97       */
    98      private void errorUsernameUnique(String username,
    99                                       ActionMessages errors) {
    100         errors.add(
    101                 USERNAME,
    102                 new org.apache.struts.action.ActionMessage(
    103                         "error.username.unique", username));
    104     }
    105 
    106     /**
    107      * <p>
    108      * Verify input for creating a new user,
    109      * create the user, and process the login.
    110      * </p>
    111      *
    112      * @param form    The input form
    113      * @param request The HttpRequest being served
    114      * @param errors  The ActionMessages collection for any errors
    115      * @return A new User and empty Errors if create succeeds,
    116      *         or null and Errors if create fails
    117      */
    118     private User doCreateUser(
    119             ActionForm form,
    120             HttpServletRequest request,
    121             ActionMessages errors) {
    122 
    123         if (log.isTraceEnabled()) {
    124             log.trace(" Perform additional validations on Create");
    125         }
    126 
    127         UserDatabase database = doGetUserDatabase();
    128         String username = doGet(form, USERNAME);
    129         try {
    130             if (database.findUser(username) != null) {
    131                 errorUsernameUnique(username, errors);
    132             }
    133         }
    134         catch (ExpiredPasswordException e) {
    135             errorUsernameUnique(username, errors);
    136             errors.add("errors.literal", new ActionMessage(e.getMessage()));
    137         }
    138 
    139         String password = doGet(form, PASSWORD);
    140         if ((password == null) || (password.length() < 1)) {
    141             errors.add(PASSWORD, new ActionMessage("error.password.required"));
    142 
    143             String password2 = doGet(form, PASSWORD2);
    144             if ((password2 == null) || (password2.length() < 1)) {
    145                 errors.add(
    146                         PASSWORD2,
    147                         new ActionMessage("error.password2.required"));
    148             }
    149         }
    150 
    151         if (!errors.isEmpty()) {
    152             return null;
    153         }
    154 
    155         User user = database.createUser(username);
    156 
    157         // Log the user in
    158         HttpSession session = request.getSession();
    159         session.setAttribute(Constants.USER_KEY, user);
    160         if (log.isTraceEnabled()) {
    161             log.trace(
    162                     " User: '"
    163                             + user.getUsername()
    164                             + "' logged on in session: "
    165                             + session.getId());
    166         }
    167 
    168         return user;
    169     }
    170 
    171     /**
    172      * <p>
    173      * Helper method to populate the input form from the User object.
    174      * </p>
    175      *
    176      * @param form Form with incoming values
    177      * @param user User object to populate
    178      * @throws ServletException On any error
    179      */
    180     private void doPopulate(ActionForm form, User user)
    181             throws ServletException {
    182 
    183         final String title = Constants.EDIT;
    184 
    185         if (log.isTraceEnabled()) {
    186             log.trace(Constants.LOG_POPULATE_FORM + user);
    187         }
    188 
    189         try {
    190             PropertyUtils.copyProperties(form, user);
    191             DynaActionForm dyna = (DynaActionForm) form;
    192             dyna.set(TASK, title);
    193             dyna.set(PASSWORD, null);
    194             dyna.set(PASSWORD2, null);
    195         } catch (InvocationTargetException e) {
    196             Throwable t = e.getTargetException();
    197             if (t == null) {
    198                 t = e;
    199             }
    200             log.error(LOG_REGISTRATION_POPULATE, t);
    201             throw new ServletException(LOG_REGISTRATION_POPULATE, t);
    202         } catch (Throwable t) {
    203             log.error(LOG_REGISTRATION_POPULATE, t);
    204             throw new ServletException(LOG_REGISTRATION_POPULATE, t);
    205         }
    206     }
    207 
    208     /**
    209      * <p>
    210      * Helper method to populate the User object from the input form.
    211      * </p>
    212      *
    213      * @param user User object to populate
    214      * @param form Form with incoming values
    215      * @throws ServletException On any error
    216      */
    217     private void doPopulate(User user, ActionForm form)
    218             throws ServletException {
    219 
    220         if (log.isTraceEnabled()) {
    221             log.trace(Constants.LOG_POPULATE_USER + user);
    222         }
    223 
    224         try {
    225             String oldPassword = user.getPassword();
    226             PropertyUtils.copyProperties(user, form);
    227             String password = doGet(form, PASSWORD);
    228             if ((password == null)
    229                     || (password.length() < 1)) {
    230 
    231                 user.setPassword(oldPassword);
    232             }
    233 
    234         } catch (InvocationTargetException e) {
    235             Throwable t = e.getTargetException();
    236             if (t == null) {
    237                 t = e;
    238             }
    239 
    240             log.error(LOG_REGISTRATION_POPULATE, t);
    241             throw new ServletException(LOG_REGISTRATION_POPULATE, t);
    242 
    243         } catch (Throwable t) {
    244             log.error(LOG_REGISTRATION_POPULATE, t);
    245             throw new ServletException(LOG_REGISTRATION_POPULATE, t);
    246         }
    247     }
    248 
    249     /**
    250      * <p>
    251      * Validate and clear the transactional token,
    252      * creating logging statements as needed.
    253      * </p>
    254      *
    255      * @param request Our HttpServletRequest
    256      * @param errors  ActionErrors to transfer any messages
    257      */
    258     private void doValidateToken(HttpServletRequest request,
    259                                  ActionMessages errors) {
    260 
    261         if (log.isTraceEnabled()) {
    262             log.trace(Constants.LOG_TOKEN_CHECK);
    263         }
    264 
    265         if (!isTokenValid(request)) {
    266             errors.add(
    267                     ActionMessages.GLOBAL_MESSAGE,
    268                     new ActionMessage(Constants.MSG_TRANSACTION_TOKEN));
    269         }
    270 
    271         resetToken(request);
    272     }
    273 
    274     // ----- Public Methods ----
    275 
    276     /**
    277      * <p>
    278      * Retrieve the User object to edit or null if the User does not exist,
    279      * and set an transactional token to later detect multiple Save commands.
    280      * </p>
    281      *
    282      * @param mapping  Our ActionMapping
    283      * @param form     Our ActionForm
    284      * @param request  Our HttpServletRequest
    285      * @param response Our HttpServletResponse
    286      * @return The "Success" result for this mapping
    287      * @throws Exception on any error
    288      */
    289     public ActionForward Edit(
    290             ActionMapping mapping,
    291             ActionForm form,
    292             HttpServletRequest request,
    293             HttpServletResponse response)
    294             throws Exception {
    295 
    296         final String method = Constants.EDIT;
    297         doLogProcess(mapping, method);
    298 
    299         HttpSession session = request.getSession();
    300         User user = doGetUser(session);
    301         boolean updating = (user != null);
    302         if (updating) {
    303             doPopulate(form, user);
    304         }
    305 
    306         doSaveToken(request);
    307         return doFindSuccess(mapping);
    308     }
    309 
    310     /**
    311      * <p>
    312      * Insert or update a User object to the persistent store.
    313      * </p><p>
    314      * If a User is not logged in,
    315      * then a new User is created and automatically logged in.
    316      * Otherwise, the existing User is updated.
    317      * </p>
    318      *
    319      * @param mapping  Our ActionMapping
    320      * @param form     Our ActionForm
    321      * @param request  Our HttpServletRequest
    322      * @param response Our HttpServletResponse
    323      * @return The "Success" result for this mapping
    324      * @throws Exception on any error
    325      */
    326     public ActionForward Save(
    327             ActionMapping mapping,
    328             ActionForm form,
    329             HttpServletRequest request,
    330             HttpServletResponse response)
    331             throws Exception {
    332 
    333         final String method = Constants.SAVE;
    334         doLogProcess(mapping, method);
    335 
    336         HttpSession session = request.getSession();
    337         if (isCancelled(request)) {
    338             doCancel(session, method, Constants.SUBSCRIPTION_KEY);
    339             return doFindSuccess(mapping);
    340         }
    341 
    342         ActionMessages errors = new ActionMessages();
    343         doValidateToken(request, errors);
    344 
    345         if (!errors.isEmpty()) {
    346             return doInputForward(mapping, request, errors);
    347         }
    348 
    349         User user = doGetUser(session);
    350         if (user == null) {
    351             user = doCreateUser(form, request, errors);
    352             if (!errors.isEmpty()) {
    353                 return doInputForward(mapping, request, errors);
    354             }
    355         }
    356 
    357         doPopulate(user, form);
    358         doSaveUser(user);
    359 
    360         return doFindSuccess(mapping);
    361     }
    362 
    363 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
