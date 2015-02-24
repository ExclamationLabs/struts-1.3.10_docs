[View Javadoc](../../../../../../../apidocs/org/apache/struts/chain/commands/servlet/PerformForward.html.md)


    1   /*
    2    * $Id: PerformForward.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands.servlet;
    22  
    23  import java.io.IOException;
    24  
    25  import org.apache.commons.logging.Log;
    26  import org.apache.commons.logging.LogFactory;
    27  import org.apache.struts.action.ActionServlet;
    28  import org.apache.struts.chain.commands.AbstractPerformForward;
    29  import org.apache.struts.chain.contexts.ActionContext;
    30  import org.apache.struts.chain.contexts.ServletActionContext;
    31  import org.apache.struts.config.ForwardConfig;
    32  import org.apache.struts.config.ModuleConfig;
    33  import org.apache.struts.util.MessageResources;
    34  import org.apache.struts.util.RequestUtils;
    35  import org.apache.struts.util.ModuleUtils;
    36  
    37  import javax.servlet.RequestDispatcher;
    38  import javax.servlet.ServletContext;
    39  import javax.servlet.ServletException;
    40  import javax.servlet.http.HttpServletRequest;
    41  import javax.servlet.http.HttpServletResponse;
    42  
    43  /**
    44   * <p>Perform forwarding or redirection based on the specified
    45   * <code>ForwardConfig</code> (if any).</p>
    46   *
    47   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    48   */
    49  public class PerformForward extends AbstractPerformForward {
    50      private static final Log LOG = LogFactory.getLog(PerformForward.class);
    51  
    52      // ------------------------------------------------------- Protected Methods
    53  
    54      /**
    55       * <p>Perform the appropriate processing on the specified
    56       * <code>ForwardConfig</code>.</p>
    57       *
    58       * @param context       The context for this request
    59       * @param forwardConfig The forward to be performed
    60       */
    61      protected void perform(ActionContext context, ForwardConfig forwardConfig)
    62          throws Exception {
    63          ServletActionContext sacontext = (ServletActionContext) context;
    64          String uri = forwardConfig.getPath();
    65  
    66          if (uri == null) {
    67              ActionServlet servlet = sacontext.getActionServlet();
    68              MessageResources resources = servlet.getInternal();
    69  
    70              throw new IllegalArgumentException(resources.getMessage("forwardPathNull"));
    71          }
    72  
    73          HttpServletRequest request = sacontext.getRequest();
    74          ServletContext servletContext = sacontext.getContext();
    75          HttpServletResponse response = sacontext.getResponse();
    76  
    77          // If the forward can be unaliased into an action, then use the path of the action
    78          String actionIdPath = RequestUtils.actionIdURL(forwardConfig, sacontext.getRequest(), sacontext.getActionServlet());
    79          if (actionIdPath != null) {
    80              uri = actionIdPath;
    81              ForwardConfig actionIdForwardConfig = new ForwardConfig(forwardConfig);
    82              actionIdForwardConfig.setPath(actionIdPath);
    83              forwardConfig = actionIdForwardConfig;
    84          }
    85  
    86          if (uri.startsWith("/")) {
    87              uri = resolveModuleRelativePath(forwardConfig, servletContext, request);
    88          }
    89  
    90  
    91          if (response.isCommitted() && !forwardConfig.getRedirect()) {
    92              handleAsInclude(uri, servletContext, request, response);
    93          } else if (forwardConfig.getRedirect()) {
    94              handleAsRedirect(uri, request, response);
    95          } else {
    96              handleAsForward(uri, servletContext, request, response);
    97          }
    98      }
    99  
    100     private String resolveModuleRelativePath(ForwardConfig forwardConfig, ServletContext servletContext, HttpServletRequest request) {
    101         String prefix = forwardConfig.getModule();
    102         ModuleConfig moduleConfig = ModuleUtils.getInstance().getModuleConfig(prefix, request, servletContext);
    103         return RequestUtils.forwardURL(request,forwardConfig, moduleConfig);
    104     }
    105 
    106     private void handleAsForward(String uri, ServletContext servletContext, HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    107         RequestDispatcher rd = servletContext.getRequestDispatcher(uri);
    108 
    109         if (LOG.isDebugEnabled()) {
    110             LOG.debug("Forwarding to " + uri);
    111         }
    112 
    113         rd.forward(request, response);
    114     }
    115 
    116     private void handleAsRedirect(String uri, HttpServletRequest request, HttpServletResponse response) throws IOException {
    117         if (uri.startsWith("/")) {
    118             uri = request.getContextPath() + uri;
    119         }
    120 
    121         if (LOG.isDebugEnabled()) {
    122             LOG.debug("Redirecting to " + uri);
    123         }
    124 
    125         response.sendRedirect(response.encodeRedirectURL(uri));
    126     }
    127 
    128     private void handleAsInclude(String uri, ServletContext servletContext, HttpServletRequest request, HttpServletResponse response) throws IOException, ServletException {
    129         RequestDispatcher rd = servletContext.getRequestDispatcher(uri);
    130 
    131         if (rd == null) {
    132             response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    133                 "Error getting RequestDispatcher for " + uri);
    134             return;
    135         }
    136 
    137         if (LOG.isDebugEnabled()) {
    138             LOG.debug("Including " + uri);
    139         }
    140 
    141         rd.include(request, response);
    142     }
    143 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
