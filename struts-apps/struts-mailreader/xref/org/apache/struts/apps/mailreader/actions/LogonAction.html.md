[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/mailreader/actions/LogonAction.html.md)


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
    21  package org.apache.struts.apps.mailreader.actions;
    22  
    23  import org.apache.struts.action.ActionForm;
    24  import org.apache.struts.action.ActionForward;
    25  import org.apache.struts.action.ActionMapping;
    26  import org.apache.struts.action.ActionMessages;
    27  import org.apache.struts.apps.mailreader.dao.User;
    28  
    29  import javax.servlet.http.HttpServletRequest;
    30  import javax.servlet.http.HttpServletResponse;
    31  
    32  /**
    33   * <p>
    34   * Validate a user logon.
    35   * </p>
    36   *
    37   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    38   */
    39  public final class LogonAction extends BaseAction {
    40  
    41      /**
    42       * <p>
    43       * Use "username" and "password" fields from ActionForm to retrieve a User
    44       * object from the database. If credentials are not valid, or database
    45       * has disappeared, post error messages and forward to input.
    46       * </p>
    47       *
    48       * @param mapping  The ActionMapping used to select this instance
    49       * @param form     The optional ActionForm bean for this request (if any)
    50       * @param request  The HTTP request we are processing
    51       * @param response The HTTP response we are creating
    52       * @throws Exception if the application business logic throws
    53       *                   an exception
    54       */
    55      public ActionForward execute(
    56              ActionMapping mapping,
    57              ActionForm form,
    58              HttpServletRequest request,
    59              HttpServletResponse response)
    60              throws Exception {
    61  
    62          // Retrieve user
    63          String username = doGet(form, USERNAME);
    64          String password = doGet(form, PASSWORD);
    65          ActionMessages errors = new ActionMessages();
    66          User user = doGetUser(username, password, errors);
    67  
    68          // Report back any errors, and exit if any
    69          if (!errors.isEmpty()) {
    70              this.saveErrors(request, errors);
    71              return (mapping.getInputForward());
    72          }
    73  
    74          // Cache user object in session to signify logon
    75          doCacheUser(request, user);
    76  
    77          // Done
    78          return doFindSuccess(mapping);
    79  
    80      }
    81  
    82  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)