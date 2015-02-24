[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/dispatch/ActionDispatcherExample.html.md)


    1   /*
    2    * $Id: ActionDispatcherExample.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.webapp.dispatch;
    22  
    23  import javax.servlet.http.HttpServletRequest;
    24  import javax.servlet.http.HttpServletResponse;
    25  import org.apache.struts.actions.ActionDispatcher;
    26  import org.apache.struts.action.Action;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionForward;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.action.ActionMessage;
    31  import org.apache.struts.action.ActionMessages;
    32  
    33  /**
    34   * Example DispatchAction.
    35   *
    36   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    37   */
    38  public class ActionDispatcherExample extends Action {
    39  
    40      private ActionDispatcher dispatcher
    41                      = new ActionDispatcher(this,
    42                                  ActionDispatcher.DISPATCH_FLAVOR);
    43  
    44      private int fooCount;
    45      private int barCount;
    46  
    47      /**
    48       * Execute method.
    49       *
    50       * @param mapping The ActionMapping used to select this instance
    51       * @param form The optional ActionForm bean for this request
    52       * @param request The servlet request we are processing
    53       * @param response The servlet response we are creating
    54       *
    55       * @exception Exception if business logic throws an exception
    56       */
    57      public ActionForward execute(ActionMapping mapping,
    58                                   ActionForm form,
    59                                   HttpServletRequest request,
    60                                   HttpServletResponse response)
    61          throws Exception {
    62  
    63          return dispatcher.execute(mapping, form, request, response);
    64  
    65      }
    66  
    67      /**
    68       * Example "foo" method.
    69       *
    70       * @param mapping The ActionMapping used to select this instance
    71       * @param form The optional ActionForm bean for this request
    72       * @param request The servlet request we are processing
    73       * @param response The servlet response we are creating
    74       *
    75       * @exception Exception if business logic throws an exception
    76       */
    77      public ActionForward doFoo(ActionMapping mapping,
    78                                 ActionForm form,
    79                                 HttpServletRequest request,
    80                                 HttpServletResponse response)
    81          throws Exception {
    82  
    83          fooCount++;
    84  
    85          ActionMessages messages = new ActionMessages();
    86          messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
    87          saveMessages(request, messages);
    88  
    89          return (mapping.findForward("success"));
    90  
    91      }
    92  
    93      /**
    94       * Example "bar" method.
    95       *
    96       * @param mapping The ActionMapping used to select this instance
    97       * @param form The optional ActionForm bean for this request
    98       * @param request The servlet request we are processing
    99       * @param response The servlet response we are creating
    100      *
    101      * @exception Exception if business logic throws an exception
    102      */
    103     public ActionForward doBar(ActionMapping mapping,
    104                                ActionForm form,
    105                                HttpServletRequest request,
    106                                HttpServletResponse response)
    107         throws Exception {
    108         barCount++;
    109 
    110         ActionMessages messages = new ActionMessages();
    111         messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
    112         saveMessages(request, messages);
    113 
    114         return (mapping.findForward("success"));
    115 
    116     }
    117 
    118 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
