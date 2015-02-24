[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/SaveRegistrationAction.html.md)


    1   /*
    2    * $Id: SaveRegistrationAction.java 471754 2006-11-06 14:55:09Z husted $
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
    37  import org.apache.struts.action.ActionMessage;
    38  import org.apache.struts.action.ActionMessages;
    39  import org.apache.struts.action.ActionForm;
    40  import org.apache.struts.action.ActionForward;
    41  import org.apache.struts.action.ActionMapping;
    42  
    43  
    44  /**
    45   * Implementation of <strong>Action</strong> that validates and creates or
    46   * updates the user registration information entered by the user.  If a new
    47   * registration is created, the user is also implicitly logged on.
    48   *
    49   * @author Craig R. McClanahan
    50   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    51   */
    52  
    53  public final class SaveRegistrationAction extends Action {
    54  
    55  
    56      // ----------------------------------------------------- Instance Variables
    57  
    58  
    59      /**
    60       * The <code>Log</code> instance for this application.
    61       */
    62      private Log log =
    63          LogFactory.getLog("org.apache.struts.webapp.Example");
    64  
    65  
    66      // --------------------------------------------------------- Public Methods
    67  
    68  
    69      /**
    70       * Process the specified HTTP request, and create the corresponding HTTP
    71       * response (or forward to another web component that will create it).
    72       * Return an <code>ActionForward</code> instance describing where and how
    73       * control should be forwarded, or <code>null</code> if the response has
    74       * already been completed.
    75       *
    76       * @param mapping The ActionMapping used to select this instance
    77       * @param form The optional ActionForm bean for this request (if any)
    78       * @param request The HTTP request we are processing
    79       * @param response The HTTP response we are creating
    80       *
    81       * @exception Exception if the application business logic throws
    82       *  an exception
    83       */
    84      public ActionForward execute(ActionMapping mapping,
    85                   ActionForm form,
    86                   HttpServletRequest request,
    87                   HttpServletResponse response)
    88      throws Exception {
    89  
    90      // Extract attributes and parameters we will need
    91      HttpSession session = request.getSession();
    92      RegistrationForm regform = (RegistrationForm) form;
    93      String action = regform.getAction();
    94      if (action == null) {
    95          action = "Create";
    96          }
    97          UserDatabase database = (UserDatabase)
    98        servlet.getServletContext().getAttribute(Constants.DATABASE_KEY);
    99          if (log.isDebugEnabled()) {
    100             log.debug("SaveRegistrationAction:  Processing " + action +
    101                       " action");
    102         }
    103 
    104     // Is there a currently logged on user (unless creating)?
    105     User user = (User) session.getAttribute(Constants.USER_KEY);
    106     if (!"Create".equals(action) && (user == null)) {
    107             if (log.isTraceEnabled()) {
    108                 log.trace(" User is not logged on in session "
    109                           + session.getId());
    110             }
    111         return (mapping.findForward("logon"));
    112         }
    113 
    114     // Was this transaction cancelled?
    115     if (isCancelled(request)) {
    116             if (log.isTraceEnabled()) {
    117                 log.trace(" Transaction '" + action +
    118                           "' was cancelled");
    119             }
    120         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    121         return (mapping.findForward("failure"));
    122     }
    123 
    124         // Validate the transactional control token
    125     ActionMessages errors = new ActionMessages();
    126         if (log.isTraceEnabled()) {
    127             log.trace(" Checking transactional control token");
    128         }
    129         if (!isTokenValid(request)) {
    130             errors.add(ActionMessages.GLOBAL_MESSAGE,
    131                        new ActionMessage("error.transaction.token"));
    132         }
    133         resetToken(request);
    134 
    135     // Validate the request parameters specified by the user
    136         if (log.isTraceEnabled()) {
    137             log.trace(" Performing extra validations");
    138         }
    139     String value = null;
    140     value = regform.getUsername();
    141     if (("Create".equals(action)) &&
    142             (database.findUser(value) != null)) {
    143             errors.add("username",
    144                        new ActionMessage("error.username.unique",
    145                                        regform.getUsername()));
    146         }
    147     if ("Create".equals(action)) {
    148         value = regform.getPassword();
    149         if ((value == null) || (value.length() <1)) {
    150                 errors.add("password",
    151                            new ActionMessage("error.password.required"));
    152             }
    153         value = regform.getPassword2();
    154         if ((value == null) || (value.length() < 1)) {
    155                 errors.add("password2",
    156                            new ActionMessage("error.password2.required"));
    157             }
    158     }
    159 
    160     // Report any errors we have discovered back to the original form
    161     if (!errors.isEmpty()) {
    162         saveErrors(request, errors);
    163             saveToken(request);
    164             return (mapping.getInputForward());
    165     }
    166 
    167     // Update the user's persistent profile information
    168         try {
    169             if ("Create".equals(action)) {
    170                 user = database.createUser(regform.getUsername());
    171             }
    172             String oldPassword = user.getPassword();
    173             PropertyUtils.copyProperties(user, regform);
    174             if ((regform.getPassword() == null) ||
    175                 (regform.getPassword().length() < 1)) {
    176                 user.setPassword(oldPassword);
    177             }
    178         } catch (InvocationTargetException e) {
    179             Throwable t = e.getTargetException();
    180             if (t == null) {
    181                 t = e;
    182             }
    183             log.error("Registration.populate", t);
    184             throw new ServletException("Registration.populate", t);
    185         } catch (Throwable t) {
    186             log.error("Registration.populate", t);
    187             throw new ServletException("Subscription.populate", t);
    188         }
    189 
    190         try {
    191             database.save();
    192         } catch (Exception e) {
    193             log.error("Database save", e);
    194         }
    195 
    196         // Log the user in if appropriate
    197     if ("Create".equals(action)) {
    198         session.setAttribute(Constants.USER_KEY, user);
    199             if (log.isTraceEnabled()) {
    200                 log.trace(" User '" + user.getUsername() +
    201                           "' logged on in session " + session.getId());
    202             }
    203     }
    204 
    205     // Remove the obsolete form bean
    206     if (mapping.getAttribute() != null) {
    207             if ("request".equals(mapping.getScope()))
    208                 request.removeAttribute(mapping.getAttribute());
    209             else
    210                 session.removeAttribute(mapping.getAttribute());
    211         }
    212 
    213     // Forward control to the specified success URI
    214         if (log.isTraceEnabled()) {
    215             log.trace(" Forwarding to success page");
    216         }
    217     return (mapping.findForward("success"));
    218 
    219     }
    220 
    221 
    222 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
