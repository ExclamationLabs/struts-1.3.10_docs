[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/mailreader/actions/SubscriptionAction.html.md)


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
    23  import org.apache.struts.apps.mailreader.Constants;
    24  import org.apache.struts.apps.mailreader.dao.Subscription;
    25  import org.apache.struts.apps.mailreader.dao.User;
    26  
    27  import javax.servlet.ServletException;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.http.HttpSession;
    31  import java.lang.reflect.InvocationTargetException;
    32  
    33  /**
    34   * <p>
    35   * Provide an Edit method for retrieving an existing subscription,
    36   * and a Save method for updating or inserting a subscription.
    37   * </p>
    38   */
    39  public final class SubscriptionAction extends BaseAction {
    40  
    41      // --- Public Constants --
    42  
    43      /**
    44       * <p>
    45       * Name of autoConnect field ["autoConnect"].
    46       * </p>
    47       */
    48      public final static String AUTO_CONNECT = "autoConnect";
    49  
    50      /**
    51       * <p>
    52       * Name of host field ["host"].
    53       * </p>
    54       */
    55      public final static String HOST = "host";
    56  
    57      /**
    58       * <p>
    59       * Name of type field ["type"].
    60       * </p>
    61       */
    62      public final static String TYPE = "type";
    63  
    64      // ---- Private Methods ----
    65  
    66      final String LOG_SUBSCRIPTION_POPULATE = "SubscriptionForm.populate";
    67  
    68      /**
    69       * <p>
    70       * Obtain subscription matching host for the given User,
    71       * or return null if not found.
    72       * </p>
    73       *
    74       * @param user Our User object
    75       * @param host The name of the mail server host
    76       * @return The matching Subscription or null
    77       */
    78      private Subscription doFindSubscription(User user, String host) {
    79  
    80          Subscription subscription;
    81  
    82          try {
    83              subscription = user.findSubscription(host);
    84          }
    85          catch (NullPointerException e) {
    86              subscription = null;
    87          }
    88  
    89          if ((subscription == null) && (log.isTraceEnabled())) {
    90              log.trace(
    91                      " No subscription for user "
    92                              + user.getUsername()
    93                              + " and host "
    94                              + host);
    95          }
    96  
    97          return subscription;
    98      }
    99  
    100     /**
    101      * <p>
    102      * Helper method to populate the Subscription object from the input form.
    103      * </p>
    104      *
    105      * @param subscription User object to populate
    106      * @param form         Form with incoming values
    107      * @throws ServletException On any error
    108      */
    109     private void doPopulate(Subscription subscription, ActionForm form)
    110             throws ServletException {
    111 
    112         if (log.isTraceEnabled()) {
    113             log.trace(Constants.LOG_POPULATE_SUBSCRIPTION + subscription);
    114         }
    115 
    116         try {
    117             PropertyUtils.copyProperties(subscription, form);
    118         } catch (InvocationTargetException e) {
    119             Throwable t = e.getTargetException();
    120             if (t == null) {
    121                 t = e;
    122             }
    123             log.error(LOG_SUBSCRIPTION_POPULATE, t);
    124             throw new ServletException(LOG_SUBSCRIPTION_POPULATE, t);
    125         } catch (Throwable t) {
    126             log.error(LOG_SUBSCRIPTION_POPULATE, t);
    127             throw new ServletException(LOG_SUBSCRIPTION_POPULATE, t);
    128         }
    129     }
    130 
    131     /**
    132      * <p>
    133      * Helper method to populate the input form from the Subscription object.
    134      * </p>
    135      *
    136      * @param subscription User object to populate
    137      * @param form         Form with incoming values
    138      * @throws ServletException On any error
    139      */
    140     private void doPopulate(ActionForm form, Subscription subscription)
    141             throws ServletException {
    142 
    143         final String title = Constants.EDIT;
    144 
    145         if (log.isTraceEnabled()) {
    146             log.trace(Constants.LOG_POPULATE_FORM + subscription.getHost());
    147         }
    148 
    149         try {
    150             PropertyUtils.copyProperties(form, subscription);
    151             doSet(form, TASK, title);
    152         } catch (InvocationTargetException e) {
    153             Throwable t = e.getTargetException();
    154             if (t == null) {
    155                 t = e;
    156             }
    157             log.error(LOG_SUBSCRIPTION_POPULATE, t);
    158             throw new ServletException(LOG_SUBSCRIPTION_POPULATE, t);
    159         } catch (Throwable t) {
    160             log.error(LOG_SUBSCRIPTION_POPULATE, t);
    161             throw new ServletException(LOG_SUBSCRIPTION_POPULATE, t);
    162         }
    163     }
    164 
    165     /**
    166      * <p>
    167      * Remove the given subscription for this user.
    168      * </p>
    169      *
    170      * @param mapping      Our ActionMapping
    171      * @param session      Our HttpSession
    172      * @param user         Our User
    173      * @param subscription Subscription to delete
    174      * @return "Success" if delete is nominal, "Logon" if attributes are
    175      *         missing
    176      * @throws ServletException if updates fails
    177      */
    178     private ActionForward doRemoveSubscription(
    179             ActionMapping mapping,
    180             HttpSession session,
    181             User user,
    182             Subscription subscription)
    183             throws ServletException {
    184 
    185         final String method = Constants.DELETE;
    186         doLogProcess(mapping, method);
    187 
    188         if (log.isTraceEnabled()) {
    189             log.trace(
    190                     " Deleting subscription to mail server '"
    191                             + subscription.getHost()
    192                             + "' for user '"
    193                             + user.getUsername()
    194                             + "'");
    195         }
    196 
    197         boolean missingAttributes = ((user == null) || (subscription == null));
    198         if (missingAttributes) {
    199             return doFindLogon(mapping);
    200         }
    201 
    202         user.removeSubscription(subscription);
    203         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    204         doSaveUser(user);
    205 
    206         return doFindSuccess(mapping);
    207     }
    208 
    209     // ----- Public Methods ----
    210 
    211     /**
    212      * <p>
    213      * Prepare for a Delete operation by populating the form
    214      * and seting the action to Delete.
    215      * </p>
    216      *
    217      * @param mapping  Our ActionMapping
    218      * @param form     Our ActionForm
    219      * @param request  Our HttpServletRequest
    220      * @param response Our HttpServletResponse
    221      * @return The "Success" result for this mapping
    222      * @throws Exception on any error
    223      */
    224     public ActionForward Delete(
    225             ActionMapping mapping,
    226             ActionForm form,
    227             HttpServletRequest request,
    228             HttpServletResponse response)
    229             throws Exception {
    230 
    231         final String method = Constants.DELETE;
    232         doLogProcess(mapping, method);
    233 
    234         ActionForward result = Edit(mapping, form, request, response);
    235 
    236         doSet(form, TASK, method);
    237         return result;
    238     }
    239 
    240     /**
    241      * <p>
    242      * Retrieve the Subscription object to edit
    243      * or null if the Subscription does not exist.
    244      * </p><p>
    245      * The Subscription object is bound to the User,
    246      * and so if the User is not logged in,
    247      * control is forwarded to the Logon result.
    248      * </p>
    249      *
    250      * @param mapping  Our ActionMapping
    251      * @param form     Our ActionForm
    252      * @param request  Our HttpServletRequest
    253      * @param response Our HttpServletResponse
    254      * @return The "Success" result for this mapping
    255      * @throws Exception on any error
    256      */
    257     public ActionForward Edit(
    258             ActionMapping mapping,
    259             ActionForm form,
    260             HttpServletRequest request,
    261             HttpServletResponse response)
    262             throws Exception {
    263 
    264         final String method = Constants.EDIT;
    265         doLogProcess(mapping, method);
    266 
    267         HttpSession session = request.getSession();
    268         User user = doGetUser(session);
    269         if (user == null) {
    270             return doFindLogon(mapping);
    271         }
    272 
    273         // Retrieve the subscription, if there is one
    274         Subscription subscription;
    275         String host = doGet(form, HOST);
    276         boolean updating = (host != null);
    277         if (updating) {
    278             subscription = doFindSubscription(user, host);
    279             if (subscription == null) {
    280                 return doFindFailure(mapping);
    281             }
    282             session.setAttribute(Constants.SUBSCRIPTION_KEY, subscription);
    283             doPopulate(form, subscription);
    284             doSet(form, TASK, method);
    285         }
    286 
    287         return doFindSuccess(mapping);
    288     }
    289 
    290     /**
    291      * <p>
    292      * Insert or update a Subscription object to the persistent store.
    293      * </p>
    294      *
    295      * @param mapping  Our ActionMapping
    296      * @param form     Our ActionForm
    297      * @param request  Our HttpServletRequest
    298      * @param response Our HttpServletResponse
    299      * @return The "Success" result for this mapping
    300      * @throws Exception on any error
    301      */
    302     public ActionForward Save(
    303             ActionMapping mapping,
    304             ActionForm form,
    305             HttpServletRequest request,
    306             HttpServletResponse response)
    307             throws Exception {
    308 
    309         final String method = Constants.SAVE;
    310         doLogProcess(mapping, method);
    311 
    312         User user = doGetUser(request);
    313         if (user == null) {
    314             return doFindLogon(mapping);
    315         }
    316 
    317         HttpSession session = request.getSession();
    318         if (isCancelled(request)) {
    319             doCancel(session, method, Constants.SUBSCRIPTION_KEY);
    320             return doFindSuccess(mapping);
    321         }
    322 
    323         String action = doGet(form, TASK);
    324         Subscription subscription = doGetSubscription(request);
    325         boolean isDelete = action.equals(Constants.DELETE);
    326         if (isDelete) {
    327             return doRemoveSubscription(mapping, session, user, subscription);
    328         }
    329 
    330         if (subscription == null) {
    331             subscription = user.createSubscription(doGet(form, HOST));
    332             session.setAttribute(Constants.SUBSCRIPTION_KEY, subscription);
    333         }
    334 
    335         doPopulate(subscription, form);
    336         doSaveUser(user);
    337         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    338 
    339         return doFindSuccess(mapping);
    340     }
    341 
    342 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
