[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/SaveRegistrationAction.html.md)


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
    35  import org.apache.struts.action.ActionMessage;
    36  import org.apache.struts.action.ActionErrors;
    37  import org.apache.struts.action.ActionForm;
    38  import org.apache.struts.action.ActionForward;
    39  import org.apache.struts.action.ActionMapping;
    40  
    41  
    42  /**
    43   * Implementation of <strong>Action</strong> that validates and creates or
    44   * updates the user registration information entered by the user.  If a new
    45   * registration is created, the user is also implicitly logged on.
    46   *
    47   * @author Craig R. McClanahan
    48   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    49   */
    50  
    51  public final class SaveRegistrationAction extends Action {
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
    89      HttpSession session = request.getSession();
    90      RegistrationForm regform = (RegistrationForm) form;
    91      String action = regform.getAction();
    92      if (action == null) {
    93          action = "Create";
    94          }
    95          UserDatabase database = (UserDatabase)
    96        servlet.getServletContext().getAttribute(Constants.DATABASE_KEY);
    97          if (log.isDebugEnabled()) {
    98              log.debug("SaveRegistrationAction:  Processing " + action +
    99                        " action");
    100         }
    101 
    102     // Is there a currently logged on user (unless creating)?
    103     User user = (User) session.getAttribute(Constants.USER_KEY);
    104     if (!"Create".equals(action) && (user == null)) {
    105             if (log.isTraceEnabled()) {
    106                 log.trace(" User is not logged on in session "
    107                           + session.getId());
    108             }
    109         return (mapping.findForward("logon"));
    110         }
    111 
    112     // Was this transaction cancelled?
    113     if (isCancelled(request)) {
    114             if (log.isTraceEnabled()) {
    115                 log.trace(" Transaction '" + action +
    116                           "' was cancelled");
    117             }
    118         session.removeAttribute(Constants.SUBSCRIPTION_KEY);
    119         return (mapping.findForward("failure"));
    120     }
    121 
    122         // Validate the transactional control token
    123     ActionErrors errors = new ActionErrors();
    124         if (log.isTraceEnabled()) {
    125             log.trace(" Checking transactional control token");
    126         }
    127         if (!isTokenValid(request)) {
    128             errors.add(ActionErrors.GLOBAL_MESSAGE,
    129                        new ActionMessage("error.transaction.token"));
    130         }
    131         resetToken(request);
    132 
    133     // Validate the request parameters specified by the user
    134         if (log.isTraceEnabled()) {
    135             log.trace(" Performing extra validations");
    136         }
    137     String value = null;
    138     value = regform.getUsername();
    139     if (("Create".equals(action)) &&
    140             (database.findUser(value) != null)) {
    141             errors.add("username",
    142                        new ActionMessage("error.username.unique",
    143                                        regform.getUsername()));
    144         }
    145     if ("Create".equals(action)) {
    146         value = regform.getPassword();
    147         if ((value == null) || (value.length() <1)) {
    148                 errors.add("password",
    149                            new ActionMessage("error.password.required"));
    150             }
    151         value = regform.getPassword2();
    152         if ((value == null) || (value.length() < 1)) {
    153                 errors.add("password2",
    154                            new ActionMessage("error.password2.required"));
    155             }
    156     }
    157 
    158     // Report any errors we have discovered back to the original form
    159     if (!errors.isEmpty()) {
    160         saveErrors(request, errors);
    161             saveToken(request);
    162             return (mapping.getInputForward());
    163     }
    164 
    165     // Update the user's persistent profile information
    166         try {
    167             if ("Create".equals(action)) {
    168                 user = database.createUser(regform.getUsername());
    169             }
    170             String oldPassword = user.getPassword();
    171             PropertyUtils.copyProperties(user, regform);
    172             if ((regform.getPassword() == null) ||
    173                 (regform.getPassword().length() < 1)) {
    174                 user.setPassword(oldPassword);
    175             }
    176         } catch (InvocationTargetException e) {
    177             Throwable t = e.getTargetException();
    178             if (t == null) {
    179                 t = e;
    180             }
    181             log.error("Registration.populate", t);
    182             throw new ServletException("Registration.populate", t);
    183         } catch (Throwable t) {
    184             log.error("Registration.populate", t);
    185             throw new ServletException("Subscription.populate", t);
    186         }
    187 
    188         try {
    189             database.save();
    190         } catch (Exception e) {
    191             log.error("Database save", e);
    192         }
    193 
    194         // Log the user in if appropriate
    195     if ("Create".equals(action)) {
    196         session.setAttribute(Constants.USER_KEY, user);
    197             if (log.isTraceEnabled()) {
    198                 log.trace(" User '" + user.getUsername() +
    199                           "' logged on in session " + session.getId());
    200             }
    201     }
    202 
    203     // Remove the obsolete form bean
    204     if (mapping.getAttribute() != null) {
    205             if ("request".equals(mapping.getScope()))
    206                 request.removeAttribute(mapping.getAttribute());
    207             else
    208                 session.removeAttribute(mapping.getAttribute());
    209         }
    210 
    211     // Forward control to the specified success URI
    212         if (log.isTraceEnabled()) {
    213             log.trace(" Forwarding to success page");
    214         }
    215     return (mapping.findForward("success"));
    216 
    217     }
    218 
    219 
    220 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
