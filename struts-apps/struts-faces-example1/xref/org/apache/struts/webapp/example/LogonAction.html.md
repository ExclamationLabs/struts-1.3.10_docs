[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/LogonAction.html.md)


    1   /*
    2    * $Id: LogonAction.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.http.HttpSession;
    28  import javax.servlet.http.HttpServletResponse;
    29  import org.apache.commons.logging.Log;
    30  import org.apache.commons.logging.LogFactory;
    31  import org.apache.struts.action.Action;
    32  import org.apache.struts.action.ActionMessage;
    33  import org.apache.struts.action.ActionMessages;
    34  import org.apache.struts.action.ActionForm;
    35  import org.apache.struts.action.ActionForward;
    36  import org.apache.struts.action.ActionMapping;
    37  
    38  import org.apache.struts.util.ModuleException;
    39  import org.apache.commons.beanutils.PropertyUtils;
    40  
    41  
    42  /**
    43   * Implementation of <strong>Action</strong> that validates a user logon.
    44   *
    45   * @author Craig R. McClanahan
    46   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    47   */
    48  
    49  public final class LogonAction extends Action {
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
    77       * @exception Exception if business logic throws an exception
    78       */
    79      public ActionForward execute(ActionMapping mapping,
    80                   ActionForm form,
    81                   HttpServletRequest request,
    82                   HttpServletResponse response)
    83      throws Exception {
    84  
    85      // Extract attributes we will need
    86      User user = null;
    87  
    88      // Validate the request parameters specified by the user
    89      ActionMessages errors = new ActionMessages();
    90      String username = (String)
    91              PropertyUtils.getSimpleProperty(form, "username");
    92          String password = (String)
    93              PropertyUtils.getSimpleProperty(form, "password");
    94      UserDatabase database = (UserDatabase)
    95        servlet.getServletContext().getAttribute(Constants.DATABASE_KEY);
    96      if (database == null)
    97              errors.add(ActionMessages.GLOBAL_MESSAGE,
    98                         new ActionMessage("error.database.missing"));
    99      else {
    100         user = getUser(database, username);
    101         if ((user != null) && !user.getPassword().equals(password))
    102         user = null;
    103         if (user == null)
    104                 errors.add(ActionMessages.GLOBAL_MESSAGE,
    105                            new ActionMessage("error.password.mismatch"));
    106     }
    107 
    108     // Report any errors we have discovered back to the original form
    109     if (!errors.isEmpty()) {
    110         saveErrors(request, errors);
    111             return (mapping.getInputForward());
    112     }
    113 
    114     // Save our logged-in user in the session
    115     HttpSession session = request.getSession();
    116     session.setAttribute(Constants.USER_KEY, user);
    117         if (log.isDebugEnabled()) {
    118             log.debug("LogonAction: User '" + user.getUsername() +
    119                       "' logged on in session " + session.getId());
    120         }
    121 
    122         // Remove the obsolete form bean
    123     if (mapping.getAttribute() != null) {
    124             if ("request".equals(mapping.getScope()))
    125                 request.removeAttribute(mapping.getAttribute());
    126             else
    127                 session.removeAttribute(mapping.getAttribute());
    128         }
    129 
    130     // Forward control to the specified success URI
    131     return (mapping.findForward("success"));
    132 
    133     }
    134 
    135 
    136     // ------------------------------------------------------ Protected Methods
    137 
    138 
    139     /**
    140      * Look up the user, throwing an exception to simulate business logic
    141      * rule exceptions.
    142      *
    143      * @param database Database in which to look up the user
    144      * @param username Username specified on the logon form
    145      *
    146      * @exception AppException if a business logic rule is violated
    147      */
    148     public User getUser(UserDatabase database, String username)
    149         throws ModuleException {
    150 
    151         // Force an ArithmeticException which can be handled explicitly
    152         if ("arithmetic".equals(username)) {
    153             throw new ArithmeticException();
    154         }
    155 
    156         // Force an application-specific exception which can be handled
    157         if ("expired".equals(username)) {
    158             throw new ExpiredPasswordException(username);
    159         }
    160 
    161         // Look up and return the specified user
    162         return (database.findUser(username));
    163 
    164     }
    165 
    166 
    167 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
