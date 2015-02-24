[View Javadoc](../../../../../apidocs/org/apache/struts/actions/SwitchAction.html.md)


    1   /*
    2    * $Id: SwitchAction.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.actions;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.action.ActionForm;
    27  import org.apache.struts.action.ActionForward;
    28  import org.apache.struts.action.ActionMapping;
    29  import org.apache.struts.util.ModuleUtils;
    30  
    31  import javax.servlet.ServletException;
    32  import javax.servlet.http.HttpServletRequest;
    33  import javax.servlet.http.HttpServletResponse;
    34  
    35  /**
    36   * <p>A standard <strong>Action</strong> that switches to a new module and
    37   * then forwards control to a URI (specified in a number of possible ways)
    38   * within the new module.</p>
    39   *
    40   * <p>Valid request parameters for this Action are:</p>
    41   *
    42   * <ul>
    43   *
    44   * <li><strong>page</strong> - Module-relative URI (beginning with "/") to
    45   * which control should be forwarded after switching.</li>
    46   *
    47   * <li><strong>prefix</strong> - The module prefix (beginning with "/") of the
    48   * module to which control should be switched.  Use a zero-length string for
    49   * the default module.  The appropriate <code>ModuleConfig</code> object will
    50   * be stored as a request attribute, so any subsequent logic will assume the
    51   * new module.</li>
    52   *
    53   * </ul>
    54   *
    55   * @version $Rev: 471754 $ $Date: 2005-05-14 21:27:02 -0400 (Sat, 14 May 2005)
    56   *          $
    57   * @since Struts 1.1
    58   */
    59  public class SwitchAction extends BaseAction {
    60      // ----------------------------------------------------- Instance Variables
    61  
    62      /**
    63       * Commons Logging instance.
    64       */
    65      protected static Log log = LogFactory.getLog(SwitchAction.class);
    66  
    67      /**
    68       * Process the specified HTTP request, and create the corresponding HTTP
    69       * response (or forward to another web component that will create it).
    70       * Return an <code>ActionForward</code> instance describing where and how
    71       * control should be forwarded, or <code>null</code> if the response has
    72       * already been completed.
    73       *
    74       * @param mapping  The ActionMapping used to select this instance
    75       * @param form     The optional ActionForm bean for this request (if any)
    76       * @param request  The HTTP request we are processing
    77       * @param response The HTTP response we are creating
    78       * @return Return an <code>ActionForward</code> instance describing where
    79       *         and how control should be forwarded, or <code>null</code> if
    80       *         the response has already been completed.
    81       * @throws Exception if an exception occurs
    82       */
    83      public ActionForward execute(ActionMapping mapping, ActionForm form,
    84          HttpServletRequest request, HttpServletResponse response)
    85          throws Exception {
    86          // Identify the request parameters controlling our actions
    87          String page = request.getParameter("page");
    88          String prefix = request.getParameter("prefix");
    89  
    90          if ((page == null) || (prefix == null)) {
    91              String message = messages.getMessage("switch.required");
    92  
    93              log.error(message);
    94              throw new ServletException(message);
    95          }
    96  
    97          // Switch to the requested module
    98          ModuleUtils.getInstance().selectModule(prefix, request,
    99              getServlet().getServletContext());
    100 
    101         if (request.getAttribute(Globals.MODULE_KEY) == null) {
    102             String message = messages.getMessage("switch.prefix", prefix);
    103 
    104             log.error(message);
    105             throw new ServletException(message);
    106         }
    107 
    108         // Forward control to the specified module-relative URI
    109         return (new ActionForward(page));
    110     }
    111 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
