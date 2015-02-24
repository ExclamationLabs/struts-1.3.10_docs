[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/EditRegistrationAction.html.md)


    1   /*
    2    * $Id: EditRegistrationAction.java 471754 2006-11-06 14:55:09Z husted $
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
    42   * <code>RegistrationForm</code> from the profile of the currently logged on
    43   * User (if any).
    44   *
    45   * @author Craig R. McClanahan
    46   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    47   */
    48  
    49  public final class EditRegistrationAction extends Action {
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
    86      // Extract attributes we will need
    87      HttpSession session = request.getSession();
    88      String action = request.getParameter("action");
    89      if (action == null)
    90          action = "Create";
    91          if (log.isDebugEnabled()) {
    92              log.debug("EditRegistrationAction:  Processing " + action +
    93                          " action");
    94          }
    95  
    96      // Is there a currently logged on user?
    97      User user = null;
    98      if (!"Create".equals(action)) {
    99          user = (User) session.getAttribute(Constants.USER_KEY);
    100         if (user == null) {
    101                 if (log.isDebugEnabled()) {
    102                     log.debug(" User is not logged on in session "
    103                               + session.getId());
    104                 }
    105         return (mapping.findForward("logon"));
    106         }
    107     }
    108 
    109     // Populate the user registration form
    110     if (form == null) {
    111             if (log.isTraceEnabled()) {
    112                 log.trace(" Creating new RegistrationForm bean under key "
    113                           + mapping.getAttribute());
    114             }
    115         form = new RegistrationForm();
    116             if ("request".equals(mapping.getScope()))
    117                 request.setAttribute(mapping.getAttribute(), form);
    118             else
    119                 session.setAttribute(mapping.getAttribute(), form);
    120     }
    121     RegistrationForm regform = (RegistrationForm) form;
    122     if (user != null) {
    123             if (log.isTraceEnabled()) {
    124                 log.trace(" Populating form from " + user);
    125             }
    126             try {
    127                 PropertyUtils.copyProperties(regform, user);
    128                 regform.setAction(action);
    129                 regform.setPassword(null);
    130                 regform.setPassword2(null);
    131             } catch (InvocationTargetException e) {
    132                 Throwable t = e.getTargetException();
    133                 if (t == null)
    134                     t = e;
    135                 log.error("RegistrationForm.populate", t);
    136                 throw new ServletException("RegistrationForm.populate", t);
    137             } catch (Throwable t) {
    138                 log.error("RegistrationForm.populate", t);
    139                 throw new ServletException("RegistrationForm.populate", t);
    140             }
    141     }
    142 
    143         // Set a transactional control token to prevent double posting
    144         if (log.isTraceEnabled()) {
    145             log.trace(" Setting transactional control token");
    146         }
    147         saveToken(request);
    148 
    149     // Forward control to the edit user registration page
    150         if (log.isTraceEnabled()) {
    151             log.trace(" Forwarding to 'success' page");
    152         }
    153         if ("Create".equals(action)) {
    154             return (mapping.findForward("register"));
    155         } else {
    156             return (mapping.findForward("success"));
    157         }
    158 
    159     }
    160 
    161 
    162 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
