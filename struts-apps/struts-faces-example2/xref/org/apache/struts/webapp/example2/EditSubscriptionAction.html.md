[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/EditSubscriptionAction.html.md)


    1   /*
    2    * $Id: EditSubscriptionAction.java 471754 2006-11-06 14:55:09Z husted $
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
    38  
    39  
    40  /**
    41   * Implementation of <strong>Action</strong> that populates an instance of
    42   * <code>SubscriptionForm</code> from the currently specified subscription.
    43   *
    44   * @author Craig R. McClanahan
    45   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    46   */
    47  
    48  public final class EditSubscriptionAction extends Action {
    49  
    50  
    51      // ----------------------------------------------------- Instance Variables
    52  
    53  
    54      /**
    55       * The <code>Log</code> instance for this application.
    56       */
    57      private Log log =
    58          LogFactory.getLog("org.apache.struts.webapp.Example");
    59  
    60  
    61      // --------------------------------------------------------- Public Methods
    62  
    63  
    64      /**
    65       * Process the specified HTTP request, and create the corresponding HTTP
    66       * response (or forward to another web component that will create it).
    67       * Return an <code>ActionForward</code> instance describing where and how
    68       * control should be forwarded, or <code>null</code> if the response has
    69       * already been completed.
    70       *
    71       * @param mapping The ActionMapping used to select this instance
    72       * @param form The optional ActionForm bean for this request (if any)
    73       * @param request The HTTP request we are processing
    74       * @param response The HTTP response we are creating
    75       *
    76       * @exception Exception if the application business logic throws
    77       *  an exception
    78       */
    79      public ActionForward execute(ActionMapping mapping,
    80                   ActionForm form,
    81                   HttpServletRequest request,
    82                   HttpServletResponse response)
    83      throws Exception {
    84  
    85      // Extract attributes we will need
    86      HttpSession session = request.getSession();
    87      String action = request.getParameter("action");
    88      if (action == null) {
    89          action = "Create";
    90          }
    91      String host = request.getParameter("host");
    92          if (log.isDebugEnabled()) {
    93              log.debug("EditSubscriptionAction:  Processing " + action +
    94                        " action");
    95          }
    96  
    97      // Is there a currently logged on user?
    98      User user = (User) session.getAttribute(Constants.USER_KEY);
    99      if (user == null) {
    100             if (log.isTraceEnabled()) {
    101                 log.trace(" User is not logged on in session "
    102                           + session.getId());
    103             }
    104         return (mapping.findForward("logon"));
    105     }
    106 
    107     // Identify the relevant subscription
    108     Subscription subscription =
    109             user.findSubscription(request.getParameter("host"));
    110     if ((subscription == null) && !action.equals("Create")) {
    111             if (log.isTraceEnabled()) {
    112                 log.trace(" No subscription for user " +
    113                           user.getUsername() + " and host " + host);
    114             }
    115         return (mapping.findForward("failure"));
    116     }
    117         if (subscription != null) {
    118             session.setAttribute(Constants.SUBSCRIPTION_KEY, subscription);
    119         }
    120 
    121     // Populate the subscription form
    122     if (form == null) {
    123             if (log.isTraceEnabled()) {
    124                 log.trace(" Creating new SubscriptionForm bean under key "
    125                           + mapping.getAttribute());
    126             }
    127         form = new SubscriptionForm();
    128             if ("request".equals(mapping.getScope())) {
    129                 request.setAttribute(mapping.getAttribute(), form);
    130             } else {
    131                 session.setAttribute(mapping.getAttribute(), form);
    132             }
    133     }
    134     SubscriptionForm subform = (SubscriptionForm) form;
    135     subform.setAction(action);
    136         if (!action.equals("Create")) {
    137             if (log.isTraceEnabled()) {
    138                 log.trace(" Populating form from " + subscription);
    139             }
    140             try {
    141                 PropertyUtils.copyProperties(subform, subscription);
    142                 subform.setAction(action);
    143             } catch (InvocationTargetException e) {
    144                 Throwable t = e.getTargetException();
    145                 if (t == null)
    146                     t = e;
    147                 log.error("SubscriptionForm.populate", t);
    148                 throw new ServletException("SubscriptionForm.populate", t);
    149             } catch (Throwable t) {
    150                 log.error("SubscriptionForm.populate", t);
    151                 throw new ServletException("SubscriptionForm.populate", t);
    152             }
    153         }
    154 
    155     // Forward control to the edit subscription page
    156         if (log.isTraceEnabled()) {
    157             log.trace(" Forwarding to 'success' page");
    158         }
    159     return (mapping.findForward("success"));
    160 
    161     }
    162 
    163 
    164 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
