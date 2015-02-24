[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/SaveSubscriptionAction.html.md)


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
    23  package org.apache.struts.webapp.example;
    24  
    25  
    26  import java.lang.reflect.InvocationTargetException;
    27  
    28  import javax.servlet.ServletException;
    29  import javax.servlet.http.HttpServletRequest;
    30  import javax.servlet.http.HttpServletResponse;
    31  import javax.servlet.http.HttpSession;
    32  
    33  import org.apache.commons.beanutils.PropertyUtils;
    34  import org.apache.commons.logging.Log;
    35  import org.apache.commons.logging.LogFactory;
    36  import org.apache.struts.action.Action;
    37  import org.apache.struts.action.ActionForm;
    38  import org.apache.struts.action.ActionForward;
    39  import org.apache.struts.action.ActionMapping;
    40  import org.apache.struts.util.MessageResources;
    41  
    42  
    43  /**
    44   * Implementation of <strong>Action</strong> that validates and creates or
    45   * updates the mail subscription entered by the user.
    46   *
    47   * @author Craig R. McClanahan
    48   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    49   */
    50  
    51  public final class SaveSubscriptionAction extends Action {
    52  
    53  
    54      // ----------------------------------------------------- Instance Variables
    55  
    56  
    57      /**
    58       * The <code>Log</code> instance for this application.
    59       */
    60      private Log log =
    61          LogFactory.getLog("org.apache.struts.webapp.Example");
    62  
    63  
    64      // --------------------------------------------------------- Public Methods
    65  
    66  
    67      /**
    68       * Process the specified HTTP request, and create the corresponding HTTP
    69       * response (or forward to another web component that will create it).
    70       * Return an <code>ActionForward</code> instance describing where and how
    71       * control should be forwarded, or <code>null</code> if the response has
    72       * already been completed.
    73       *
    74       * @param mapping The ActionMapping used to select this instance
    75       * @param form The optional ActionForm bean for this request (if any)
    76       * @param request The HTTP request we are processing
    77       * @param response The HTTP response we are creating
    78       *
    79       * @exception Exception if the application business logic throws
    80       *  an exception
    81       */
    82      public ActionForward execute(ActionMapping mapping,
    83                   ActionForm form,
    84                   HttpServletRequest request,
    85                   HttpServletResponse response)
    86      throws Exception {
    87  
    88      // Extract attributes and parameters we will need
    89      MessageResources messages = getResources(request);
    90      HttpSession session = request.getSession();
    91      SubscriptionForm subform = (SubscriptionForm) form;
    92      String action = subform.getAction();
    93      if (action == null) {
    94          action = "?";
    95          }
    96          if (log.isDebugEnabled()) {
    97              log.debug("SaveSubscriptionAction:  Processing " + action +
    98                        " action");
    99          }
    100 
    101     // Is there a currently logged on user?
    102     User user = (User) session.getAttribute(Constants.USER_KEY);
    103     if (user == null) {
    104             if (log.isTraceEnabled()) {
    105                 log.trace(" User is not logged on in session "
    106                           + session.getId());
    107             }
    108         return (mapping.findForward("logon"));
    109         }
    110 
    111     // Was this transaction cancelled?
    112     if (isCancelled(request)) {
    113             if (log.isTraceEnabled()) {
    114                 log.trace(" Transaction '" + action +
    115                           "' was cancelled");
    116             }
    117             session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    118         return (mapping.findForward("success"));
    119     }
    120 
    121     // Is there a related Subscription object?
    122     Subscription subscription =
    123       (Subscription) session.getAttribute(Constants.SUBSCRIPTION_KEY);
    124         if ("Create".equals(action)) {
    125             if (log.isTraceEnabled()) {
    126                 log.trace(" Creating subscription for mail server '" +
    127                           subform.getHost() + "'");
    128             }
    129             subscription =
    130                 user.createSubscription(subform.getHost());
    131         }
    132     if (subscription == null) {
    133             if (log.isTraceEnabled()) {
    134                 log.trace(" Missing subscription for user '" +
    135                           user.getUsername() + "'");
    136             }
    137         response.sendError(HttpServletResponse.SC_BAD_REQUEST,
    138                            messages.getMessage("error.noSubscription"));
    139         return (null);
    140     }
    141 
    142     // Was this transaction a Delete?
    143     if (action.equals("Delete")) {
    144             if (log.isTraceEnabled()) {
    145                 log.trace(" Deleting mail server '" +
    146                           subscription.getHost() + "' for user '" +
    147                           user.getUsername() + "'");
    148             }
    149             user.removeSubscription(subscription);
    150         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    151             try {
    152                 UserDatabase database = (UserDatabase)
    153                     servlet.getServletContext().
    154                     getAttribute(Constants.DATABASE_KEY);
    155                 database.save();
    156             } catch (Exception e) {
    157                 log.error("Database save", e);
    158             }
    159         return (mapping.findForward("success"));
    160     }
    161 
    162     // All required validations were done by the form itself
    163 
    164     // Update the persistent subscription information
    165         if (log.isTraceEnabled()) {
    166             log.trace(" Populating database from form bean");
    167         }
    168         try {
    169             PropertyUtils.copyProperties(subscription, subform);
    170         } catch (InvocationTargetException e) {
    171             Throwable t = e.getTargetException();
    172             if (t == null)
    173                 t = e;
    174             log.error("Subscription.populate", t);
    175             throw new ServletException("Subscription.populate", t);
    176         } catch (Throwable t) {
    177             log.error("Subscription.populate", t);
    178             throw new ServletException("Subscription.populate", t);
    179         }
    180 
    181         try {
    182             UserDatabase database = (UserDatabase)
    183                 servlet.getServletContext().
    184                 getAttribute(Constants.DATABASE_KEY);
    185             database.save();
    186         } catch (Exception e) {
    187             log.error("Database save", e);
    188         }
    189 
    190     // Remove the obsolete form bean and current subscription
    191     if (mapping.getAttribute() != null) {
    192             if ("request".equals(mapping.getScope()))
    193                 request.removeAttribute(mapping.getAttribute());
    194             else
    195                 session.removeAttribute(mapping.getAttribute());
    196         }
    197     session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    198 
    199     // Forward control to the specified success URI
    200         if (log.isTraceEnabled()) {
    201             log.trace(" Forwarding to success page");
    202         }
    203     return (mapping.findForward("success"));
    204 
    205     }
    206 
    207 
    208 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
