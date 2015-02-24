[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/LogonForm.html.md)


    1   /*
    2    * $Id: LogonForm.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import org.apache.struts.action.ActionErrors;
    28  import org.apache.struts.action.ActionMessage;
    29  import org.apache.struts.action.ActionForm;
    30  import org.apache.struts.action.ActionMapping;
    31  
    32  
    33  /**
    34   * Form bean for the user profile page.  This form has the following fields,
    35   * with default values in square brackets:
    36   * <ul>
    37   * <li><b>password</b> - Entered password value
    38   * <li><b>username</b> - Entered username value
    39   * </ul>
    40   *
    41   * @author Craig R. McClanahan
    42   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    43   */
    44  
    45  public final class LogonForm extends ActionForm {
    46  
    47  
    48      // --------------------------------------------------- Instance Variables
    49  
    50  
    51      /**
    52       * The password.
    53       */
    54      private String password = null;
    55  
    56  
    57      /**
    58       * The username.
    59       */
    60      private String username = null;
    61  
    62  
    63      // ----------------------------------------------------------- Properties
    64  
    65  
    66      /**
    67       * Return the password.
    68       */
    69      public String getPassword() {
    70  
    71      return (this.password);
    72  
    73      }
    74  
    75  
    76      /**
    77       * Set the password.
    78       *
    79       * @param password The new password
    80       */
    81      public void setPassword(String password) {
    82  
    83          this.password = password;
    84  
    85      }
    86  
    87  
    88      /**
    89       * Return the username.
    90       */
    91      public String getUsername() {
    92  
    93      return (this.username);
    94  
    95      }
    96  
    97  
    98      /**
    99       * Set the username.
    100      *
    101      * @param username The new username
    102      */
    103     public void setUsername(String username) {
    104 
    105         this.username = username;
    106 
    107     }
    108 
    109 
    110     // --------------------------------------------------------- Public Methods
    111 
    112 
    113     /**
    114      * Reset all properties to their default values.
    115      *
    116      * @param mapping The mapping used to select this instance
    117      * @param request The servlet request we are processing
    118      */
    119     public void reset(ActionMapping mapping, HttpServletRequest request) {
    120 
    121         this.password = null;
    122         this.username = null;
    123 
    124     }
    125 
    126 
    127     /**
    128      * Validate the properties that have been set from this HTTP request,
    129      * and return an <code>ActionMessages</code> object that encapsulates any
    130      * validation errors that have been found.  If no errors are found, return
    131      * <code>null</code> or an <code>ActionMessages</code> object with no
    132      * recorded error messages.
    133      *
    134      * @param mapping The mapping used to select this instance
    135      * @param request The servlet request we are processing
    136      */
    137     public ActionErrors validate(ActionMapping mapping,
    138                                  HttpServletRequest request) {
    139 
    140         ActionErrors errors = new ActionErrors();
    141         if ((username == null) || (username.length() < 1))
    142             errors.add("username", new ActionMessage("error.username.required"));
    143         if ((password == null) || (password.length() < 1))
    144             errors.add("password", new ActionMessage("error.password.required"));
    145 
    146         return errors;
    147 
    148     }
    149 
    150 
    151 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
