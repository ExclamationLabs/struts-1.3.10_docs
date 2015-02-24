[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/SaveSubscriptionAction.html.md)


    1   /*
    2    * $Id: SaveSubscriptionAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import java.lang.reflect.InvocationTargetException;
    27  import javax.servlet.ServletException;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.http.HttpSession;
    31  import org.apache.commons.beanutils.PropertyUtils;
    32  import org.apache.commons.logging.Log;
    33  import org.apache.commons.logging.LogFactory;
    34  import org.apache.struts.action.Action;
    35  import org.apache.struts.action.ActionForm;
    36  import org.apache.struts.action.ActionForward;
    37  import org.apache.struts.action.ActionMapping;
    38  import org.apache.struts.util.MessageResources;
    39  
    40  
    41  /**
    42   * Implementation of <strong>Action</strong> that validates and creates or
    43   * updates the mail subscription entered by the user.
    44   *
    45   * @author Craig R. McClanahan
    46   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    47   */
    48  
    49  public final class SaveSubscriptionAction extends Action {
    50  
    51  
    52      // ----------------------------------------------------- Instance Variables
    53  
    54  
    55      /**
    56       * The <code>Log</code> instance for this application.
    57       */
    58      private Log log =
    59          LogFactory.getLog("org.apache.struts.webapp.Example");
    60  
    61  
    62      // --------------------------------------------------------- Public Methods
    63  
    64  
    65      /**
    66       * Process the specified HTTP request, and create the corresponding HTTP
    67       * response (or forward to another web component that will create it).
    68       * Return an <code>ActionForward</code> instance describing where and how
    69       * control should be forwarded, or <code>null</code> if the response has
    70       * already been completed.
    71       *
    72       * @param mapping The ActionMapping used to select this instance
    73       * @param form The optional ActionForm bean for this request (if any)
    74       * @param request The HTTP request we are processing
    75       * @param response The HTTP response we are creating
    76       *
    77       * @exception Exception if the application business logic throws
    78       *  an exception
    79       */
    80      public ActionForward execute(ActionMapping mapping,
    81                   ActionForm form,
    82                   HttpServletRequest request,
    83                   HttpServletResponse response)
    84      throws Exception {
    85  
    86      // Extract attributes and parameters we will need
    87      MessageResources messages = getResources(request);
    88      HttpSession session = request.getSession();
    89      SubscriptionForm subform = (SubscriptionForm) form;
    90      String action = subform.getAction();
    91      if (action == null) {
    92          action = "?";
    93          }
    94          if (log.isDebugEnabled()) {
    95              log.debug("SaveSubscriptionAction:  Processing " + action +
    96                        " action");
    97          }
    98  
    99      // Is there a currently logged on user?
    100     User user = (User) session.getAttribute(Constants.USER_KEY);
    101     if (user == null) {
    102             if (log.isTraceEnabled()) {
    103                 log.trace(" User is not logged on in session "
    104                           + session.getId());
    105             }
    106         return (mapping.findForward("logon"));
    107         }
    108 
    109     // Was this transaction cancelled?
    110     if (isCancelled(request)) {
    111             if (log.isTraceEnabled()) {
    112                 log.trace(" Transaction '" + action +
    113                           "' was cancelled");
    114             }
    115             session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    116         return (mapping.findForward("success"));
    117     }
    118 
    119     // Is there a related Subscription object?
    120     Subscription subscription =
    121       (Subscription) session.getAttribute(Constants.SUBSCRIPTION_KEY);
    122         if ("Create".equals(action)) {
    123             if (log.isTraceEnabled()) {
    124                 log.trace(" Creating subscription for mail server '" +
    125                           subform.getHost() + "'");
    126             }
    127             subscription =
    128                 user.createSubscription(subform.getHost());
    129         }
    130     if (subscription == null) {
    131             if (log.isTraceEnabled()) {
    132                 log.trace(" Missing subscription for user '" +
    133                           user.getUsername() + "'");
    134             }
    135         response.sendError(HttpServletResponse.SC_BAD_REQUEST,
    136                            messages.getMessage("error.noSubscription"));
    137         return (null);
    138     }
    139 
    140     // Was this transaction a Delete?
    141     if (action.equals("Delete")) {
    142             if (log.isTraceEnabled()) {
    143                 log.trace(" Deleting mail server '" +
    144                           subscription.getHost() + "' for user '" +
    145                           user.getUsername() + "'");
    146             }
    147             user.removeSubscription(subscription);
    148         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    149             try {
    150                 UserDatabase database = (UserDatabase)
    151                     servlet.getServletContext().
    152                     getAttribute(Constants.DATABASE_KEY);
    153                 database.save();
    154             } catch (Exception e) {
    155                 log.error("Database save", e);
    156             }
    157         return (mapping.findForward("success"));
    158     }
    159 
    160     // All required validations were done by the form itself
    161 
    162     // Update the persistent subscription information
    163         if (log.isTraceEnabled()) {
    164             log.trace(" Populating database from form bean");
    165         }
    166         try {
    167             PropertyUtils.copyProperties(subscription, subform);
    168         } catch (InvocationTargetException e) {
    169             Throwable t = e.getTargetException();
    170             if (t == null)
    171                 t = e;
    172             log.error("Subscription.populate", t);
    173             throw new ServletException("Subscription.populate", t);
    174         } catch (Throwable t) {
    175             log.error("Subscription.populate", t);
    176             throw new ServletException("Subscription.populate", t);
    177         }
    178 
    179         try {
    180             UserDatabase database = (UserDatabase)
    181                 servlet.getServletContext().
    182                 getAttribute(Constants.DATABASE_KEY);
    183             database.save();
    184         } catch (Exception e) {
    185             log.error("Database save", e);
    186         }
    187 
    188     // Remove the obsolete form bean and current subscription
    189     if (mapping.getAttribute() != null) {
    190             if ("request".equals(mapping.getScope()))
    191                 request.removeAttribute(mapping.getAttribute());
    192             else
    193                 session.removeAttribute(mapping.getAttribute());
    194         }
    195     session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    196 
    197     // Forward control to the specified success URI
    198         if (log.isTraceEnabled()) {
    199             log.trace(" Forwarding to success page");
    200         }
    201     return (mapping.findForward("success"));
    202 
    203     }
    204 
    205 
    206 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
