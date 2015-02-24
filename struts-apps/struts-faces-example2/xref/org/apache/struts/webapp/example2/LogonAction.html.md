[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/LogonAction.html.md)


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
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.http.HttpServletResponse;
    28  import javax.servlet.http.HttpSession;
    29  import org.apache.commons.beanutils.PropertyUtils;
    30  import org.apache.commons.logging.Log;
    31  import org.apache.commons.logging.LogFactory;
    32  import org.apache.struts.action.Action;
    33  import org.apache.struts.action.ActionMessage;
    34  import org.apache.struts.action.ActionErrors;
    35  import org.apache.struts.action.ActionForm;
    36  import org.apache.struts.action.ActionForward;
    37  import org.apache.struts.action.ActionMapping;
    38  import org.apache.struts.util.ModuleException;
    39  
    40  
    41  /**
    42   * Implementation of <strong>Action</strong> that validates a user logon.
    43   *
    44   * @author Craig R. McClanahan
    45   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    46   */
    47  
    48  public final class LogonAction extends Action {
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
    76       * @exception Exception if business logic throws an exception
    77       */
    78      public ActionForward execute(ActionMapping mapping,
    79                   ActionForm form,
    80                   HttpServletRequest request,
    81                   HttpServletResponse response)
    82      throws Exception {
    83  
    84      // Extract attributes we will need
    85      User user = null;
    86  
    87      // Validate the request parameters specified by the user
    88      ActionErrors errors = new ActionErrors();
    89      String username = (String)
    90              PropertyUtils.getSimpleProperty(form, "username");
    91          String password = (String)
    92              PropertyUtils.getSimpleProperty(form, "password");
    93      UserDatabase database = (UserDatabase)
    94        servlet.getServletContext().getAttribute(Constants.DATABASE_KEY);
    95      if (database == null)
    96              errors.add(ActionErrors.GLOBAL_MESSAGE,
    97                         new ActionMessage("error.database.missing"));
    98      else {
    99          user = getUser(database, username);
    100         if ((user != null) && !user.getPassword().equals(password))
    101         user = null;
    102         if (user == null)
    103                 errors.add(ActionErrors.GLOBAL_MESSAGE,
    104                            new ActionMessage("error.password.mismatch"));
    105     }
    106 
    107     // Report any errors we have discovered back to the original form
    108     if (!errors.isEmpty()) {
    109         saveErrors(request, errors);
    110             return (mapping.getInputForward());
    111     }
    112 
    113     // Save our logged-in user in the session
    114     HttpSession session = request.getSession();
    115     session.setAttribute(Constants.USER_KEY, user);
    116         if (log.isDebugEnabled()) {
    117             log.debug("LogonAction: User '" + user.getUsername() +
    118                       "' logged on in session " + session.getId());
    119         }
    120 
    121         // Remove the obsolete form bean
    122     if (mapping.getAttribute() != null) {
    123             if ("request".equals(mapping.getScope()))
    124                 request.removeAttribute(mapping.getAttribute());
    125             else
    126                 session.removeAttribute(mapping.getAttribute());
    127         }
    128 
    129     // Forward control to the specified success URI
    130     return (mapping.findForward("success"));
    131 
    132     }
    133 
    134 
    135     // ------------------------------------------------------ Protected Methods
    136 
    137 
    138     /**
    139      * Look up the user, throwing an exception to simulate business logic
    140      * rule exceptions.
    141      *
    142      * @param database Database in which to look up the user
    143      * @param username Username specified on the logon form
    144      *
    145      * @exception AppException if a business logic rule is violated
    146      */
    147     public User getUser(UserDatabase database, String username)
    148         throws ModuleException {
    149 
    150         // Force an ArithmeticException which can be handled explicitly
    151         if ("arithmetic".equals(username)) {
    152             throw new ArithmeticException();
    153         }
    154 
    155         // Force an application-specific exception which can be handled
    156         if ("expired".equals(username)) {
    157             throw new ExpiredPasswordException(username);
    158         }
    159 
    160         // Look up and return the specified user
    161         return (database.findUser(username));
    162 
    163     }
    164 
    165 
    166 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
