[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/contexts/ServletActionContext.html.md)


    1   /*
    2    * $Id: ServletActionContext.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.contexts;
    22  
    23  import org.apache.commons.chain.web.servlet.ServletWebContext;
    24  import org.apache.struts.Globals;
    25  import org.apache.struts.action.ActionMessages;
    26  import org.apache.struts.action.ActionServlet;
    27  import org.apache.struts.chain.Constants;
    28  import org.apache.struts.config.ActionConfig;
    29  import org.apache.struts.util.MessageResources;
    30  
    31  import javax.servlet.ServletContext;
    32  import javax.servlet.http.HttpServletRequest;
    33  import javax.servlet.http.HttpServletResponse;
    34  
    35  /**
    36   * <p> Implement ActionContext interface while making Servlet API-specific
    37   * values available. </p>
    38   */
    39  public class ServletActionContext extends WebActionContext {
    40      /**
    41       * <p> Instantiate this composite by wrapping a ServletWebContext. </p>
    42       *
    43       * @param context The ServletWebContext to wrap
    44       */
    45      public ServletActionContext(ServletWebContext context) {
    46          super(context);
    47      }
    48  
    49      /**
    50       * <p> Instantiate this Context for a given ServletContext,
    51       * HttpServletRequest, and HttpServletResponse. </p>
    52       *
    53       * @param context  The instant ServletContext
    54       * @param request  The instant HttpServletRequest
    55       * @param response The instant HttpServletResponse
    56       */
    57      public ServletActionContext(ServletContext context,
    58          HttpServletRequest request, HttpServletResponse response) {
    59          this(new ServletWebContext(context, request, response));
    60      }
    61  
    62      /**
    63       * <p> Provide the ServletWebContext for this composite. </p>
    64       *
    65       * @return Our ServletWebContext
    66       */
    67      protected ServletWebContext servletWebContext() {
    68          return (ServletWebContext) this.getBaseContext();
    69      }
    70  
    71      public void release() {
    72          this.servletWebContext().release();
    73          super.release();
    74      }
    75  
    76      // -------------------------------
    77      // Servlet specific properties
    78      // -------------------------------
    79  
    80      /**
    81       * <p> Return the ServletContext for this context. </p>
    82       *
    83       * @return Our ServletContext
    84       */
    85      public ServletContext getContext() {
    86          return servletWebContext().getContext();
    87      }
    88  
    89      /**
    90       * <p> Return the HttpServletRequest for this context. </p>
    91       *
    92       * @return Our HttpServletRequest
    93       */
    94      public HttpServletRequest getRequest() {
    95          return servletWebContext().getRequest();
    96      }
    97  
    98      /**
    99       * <p> Return the HttpServletResponse for this context. </p>
    100      *
    101      * @return Our HttpServletResponse
    102      */
    103     public HttpServletResponse getResponse() {
    104         return servletWebContext().getResponse();
    105     }
    106 
    107     /**
    108      * <p> Return the ActionServlet for this context. </p>
    109      *
    110      * @return Our ActionServlet
    111      */
    112     public ActionServlet getActionServlet() {
    113         return (ActionServlet) this.get(Constants.ACTION_SERVLET_KEY);
    114     }
    115 
    116     /**
    117      * <p> Set the ActionServlet instance for this context. </p>
    118      *
    119      * @param servlet Our ActionServlet instance
    120      */
    121     public void setActionServlet(ActionServlet servlet) {
    122         this.put(Constants.ACTION_SERVLET_KEY, servlet);
    123     }
    124 
    125     // -------------------------------
    126     // Servlet specific modifications to base properties.
    127     // -------------------------------
    128     public void setActionConfig(ActionConfig actionConfig) {
    129         super.setActionConfig(actionConfig);
    130         this.getRequestScope().put(Globals.MAPPING_KEY, actionConfig);
    131 
    132         // ISSUE: Should we check this call to put?
    133     }
    134 
    135     public MessageResources getMessageResources() {
    136         return ((MessageResources) getRequest().getAttribute(Globals.MESSAGES_KEY));
    137     }
    138 
    139     // ISSUE: This method would probably be better handled by a "Struts"
    140     // object which encapsulated the servler (Application) scope.
    141     public MessageResources getMessageResources(String key) {
    142         // Identify the current module
    143         ServletContext context = getActionServlet().getServletContext();
    144 
    145         // Return the requested message resources instance
    146         return (MessageResources) context.getAttribute(key
    147             + getModuleConfig().getPrefix());
    148     }
    149 
    150     public void setMessageResources(MessageResources resources) {
    151         super.setMessageResources(resources);
    152         this.getRequest().setAttribute(Globals.MESSAGES_KEY, resources);
    153     }
    154 
    155     /**
    156      * <p> Store the mesasage resources for the current module under the given
    157      * request attribute key. </p>
    158      *
    159      * @param key       Request attribute key
    160      * @param resources Message resouces to store
    161      */
    162     public void setMessageResources(String key, MessageResources resources) {
    163         this.getRequest().setAttribute(key + getModuleConfig().getPrefix(),
    164             resources);
    165     }
    166 
    167     // -------------------------------
    168     // ActionMessage Processing
    169     // -------------------------------
    170     public void saveErrors(ActionMessages errors) {
    171         // Remove any error messages attribute if none are required
    172         if ((errors == null) || errors.isEmpty()) {
    173             getRequest().removeAttribute(Globals.ERROR_KEY);
    174 
    175             return;
    176         }
    177 
    178         // Save the error messages we need
    179         getRequest().setAttribute(Globals.ERROR_KEY, errors);
    180     }
    181 
    182     public void saveMessages(ActionMessages messages) {
    183         if ((messages == null) || messages.isEmpty()) {
    184             getRequest().removeAttribute(Globals.MESSAGE_KEY);
    185 
    186             return;
    187         }
    188 
    189         getRequest().setAttribute(Globals.MESSAGE_KEY, messages);
    190     }
    191 
    192     public void addMessages(ActionMessages messages) {
    193         if (messages == null) {
    194             return;
    195         }
    196 
    197         ActionMessages requestMessages = getMessages();
    198 
    199         if (requestMessages == null) {
    200             requestMessages = new ActionMessages();
    201         }
    202 
    203         requestMessages.add(messages);
    204         saveMessages(requestMessages);
    205     }
    206 
    207     public void addErrors(ActionMessages errors) {
    208         if (errors == null) {
    209             return;
    210         }
    211 
    212         ActionMessages requestErrors = getErrors();
    213 
    214         if (requestErrors == null) {
    215             requestErrors = new ActionMessages();
    216         }
    217 
    218         requestErrors.add(errors);
    219         saveErrors(requestErrors);
    220     }
    221 
    222     public ActionMessages getErrors() {
    223         return (ActionMessages) this.getRequest().getAttribute(Globals.ERROR_KEY);
    224     }
    225 
    226     public ActionMessages getMessages() {
    227         return (ActionMessages) this.getRequest().getAttribute(Globals.MESSAGE_KEY);
    228     }
    229 
    230     // -------------------------------
    231     // Token Processing
    232     // Implementing the servlet-aware versions by using the
    233     // TokenProcessor class
    234     // directly should ensure greater compatibility.
    235     // -------------------------------
    236     public void saveToken() {
    237         token.saveToken(getRequest());
    238     }
    239 
    240     public String generateToken() {
    241         return token.generateToken(getRequest());
    242     }
    243 
    244     public boolean isTokenValid(boolean reset) {
    245         return token.isTokenValid(getRequest(), reset);
    246     }
    247 
    248     public void resetToken() {
    249         token.resetToken(getRequest());
    250     }
    251 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
