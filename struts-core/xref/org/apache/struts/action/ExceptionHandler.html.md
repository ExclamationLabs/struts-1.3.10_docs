[View Javadoc](../../../../../apidocs/org/apache/struts/action/ExceptionHandler.html.md)


    1   /*
    2    * $Id: ExceptionHandler.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.action;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.config.ExceptionConfig;
    27  import org.apache.struts.util.MessageResources;
    28  import org.apache.struts.util.ModuleException;
    29  
    30  import javax.servlet.RequestDispatcher;
    31  import javax.servlet.ServletException;
    32  import javax.servlet.http.HttpServletRequest;
    33  import javax.servlet.http.HttpServletResponse;
    34  
    35  import java.io.IOException;
    36  
    37  /**
    38   * <p>An <strong>ExceptionHandler</strong> is configured in the Struts
    39   * configuration file to handle a specific type of exception thrown by an
    40   * <code>Action.execute</code> method.</p>
    41   *
    42   * @since Struts 1.1
    43   */
    44  public class ExceptionHandler {
    45      /**
    46       * <p>The name of a configuration property which can be set to specify an
    47       * alternative path which should be used when the HttpServletResponse has
    48       * already been committed.</p> <p>To use this, in your
    49       * <code>struts-config.xml</code> specify the exception handler like
    50       * this:
    51       * <pre>
    52       *   &lt;exception
    53       *       key="GlobalExceptionHandler.default"
    54       *       type="java.lang.Exception"
    55       *       path="/ErrorPage.jsp"&gt;
    56       *       &lt;set-property key="INCLUDE_PATH" value="/error.jsp" /&gt;
    57       *   &lt;/exception&gt;
    58       *  </pre>
    59       * </p> <p>You would want to use this when your normal ExceptionHandler
    60       * path is a Tiles definition or otherwise unsuitable for use in an
    61       * <code>include</code> context.  If you do not use this, and you do not
    62       * specify "SILENT_IF_COMMITTED" then the ExceptionHandler will attempt to
    63       * forward to the same path which would be used in normal circumstances,
    64       * specified using the "path" attribute in the &lt;exception&gt;
    65       * element.</p>
    66       *
    67       * @since Struts 1.3
    68       */
    69      public static final String INCLUDE_PATH = "INCLUDE_PATH";
    70  
    71      /**
    72       * <p>The name of a configuration property which indicates that Struts
    73       * should do nothing if the response has already been committed.  This
    74       * suppresses the default behavior, which is to use an "include" rather
    75       * than a "forward" in this case in hopes of providing some meaningful
    76       * information to the browser.</p> <p>To use this, in your
    77       * <code>struts-config.xml</code> specify the exception handler like
    78       * this:
    79       * <pre>
    80       *   &lt;exception
    81       *       key="GlobalExceptionHandler.default"
    82       *       type="java.lang.Exception"
    83       *       path="/ErrorPage.jsp"&gt;
    84       *       &lt;set-property key="SILENT_IF_COMMITTED" value="true" /&gt;
    85       *   &lt;/exception&gt;
    86       *  </pre>
    87       * To be effective, this value must be defined to the literal String
    88       * "true". If it is not defined or defined to any other value, the default
    89       * behavior will be used. </p> <p>You only need to use this if you do not
    90       * want error information displayed in the browser when Struts intercepts
    91       * an exception after the response has been committed.</p>
    92       *
    93       * @since Struts 1.3
    94       */
    95      public static final String SILENT_IF_COMMITTED = "SILENT_IF_COMMITTED";
    96  
    97      /**
    98       * <p>Commons logging instance.</p>
    99       */
    100     private static final Log LOG = LogFactory.getLog(ExceptionHandler.class);
    101 
    102     /**
    103      * <p>The message resources for this package.</p>
    104      */
    105     private static MessageResources messages =
    106         MessageResources.getMessageResources(
    107             "org.apache.struts.action.LocalStrings");
    108 
    109     /**
    110      * <p> Handle the Exception. Return the ActionForward instance (if any)
    111      * returned by the called ExceptionHandler. </p>
    112      *
    113      * @param ex           The exception to handle
    114      * @param ae           The ExceptionConfig corresponding to the exception
    115      * @param mapping      The ActionMapping we are processing
    116      * @param formInstance The ActionForm we are processing
    117      * @param request      The servlet request we are processing
    118      * @param response     The servlet response we are creating
    119      * @return The <code>ActionForward</code> instance (if any) returned by
    120      *         the called <code>ExceptionHandler</code>.
    121      * @throws ServletException if a servlet exception occurs
    122      * @since Struts 1.1
    123      */
    124     public ActionForward execute(Exception ex, ExceptionConfig ae,
    125         ActionMapping mapping, ActionForm formInstance,
    126         HttpServletRequest request, HttpServletResponse response)
    127         throws ServletException {
    128         LOG.debug("ExceptionHandler executing for exception " + ex);
    129 
    130         ActionForward forward;
    131         ActionMessage error;
    132         String property;
    133 
    134         // Build the forward from the exception mapping if it exists
    135         // or from the form input
    136         if (ae.getPath() != null) {
    137             forward = new ActionForward(ae.getPath());
    138         } else {
    139             forward = mapping.getInputForward();
    140         }
    141 
    142         // Figure out the error
    143         if (ex instanceof ModuleException) {
    144             error = ((ModuleException) ex).getActionMessage();
    145             property = ((ModuleException) ex).getProperty();
    146         } else {
    147             error = new ActionMessage(ae.getKey(), ex.getMessage());
    148             property = error.getKey();
    149         }
    150 
    151         this.logException(ex);
    152 
    153         // Store the exception
    154         request.setAttribute(Globals.EXCEPTION_KEY, ex);
    155         this.storeException(request, property, error, forward, ae.getScope());
    156 
    157         if (!response.isCommitted()) {
    158             return forward;
    159         }
    160 
    161         LOG.debug("Response is already committed, so forwarding will not work."
    162             + " Attempt alternate handling.");
    163 
    164         if (!silent(ae)) {
    165             handleCommittedResponse(ex, ae, mapping, formInstance, request,
    166                 response, forward);
    167         } else {
    168             LOG.warn("ExceptionHandler configured with " + SILENT_IF_COMMITTED
    169                 + " and response is committed.", ex);
    170         }
    171 
    172         return null;
    173     }
    174 
    175     /**
    176      * <p>Attempt to give good information when the response has already been
    177      * committed when the exception was thrown. This happens often when Tiles
    178      * is used. Base implementation will see if the INCLUDE_PATH property has
    179      * been set, or if not, it will attempt to use the same path to which
    180      * control would have been forwarded.</p>
    181      *
    182      * @param ex            The exception to handle
    183      * @param config        The ExceptionConfig we are processing
    184      * @param mapping       The ActionMapping we are processing
    185      * @param formInstance  The ActionForm we are processing
    186      * @param request       The servlet request we are processing
    187      * @param response      The servlet response we are creating
    188      * @param actionForward The ActionForward we are processing
    189      * @since Struts 1.3
    190      */
    191     protected void handleCommittedResponse(Exception ex,
    192         ExceptionConfig config, ActionMapping mapping, ActionForm formInstance,
    193         HttpServletRequest request, HttpServletResponse response,
    194         ActionForward actionForward) {
    195         String includePath = determineIncludePath(config, actionForward);
    196 
    197         if (includePath != null) {
    198             if (includePath.startsWith("/")) {
    199                 LOG.debug("response committed, "
    200                     + "but attempt to include results "
    201                     + "of actionForward path");
    202 
    203                 RequestDispatcher requestDispatcher =
    204                     request.getRequestDispatcher(includePath);
    205 
    206                 try {
    207                     requestDispatcher.include(request, response);
    208 
    209                     return;
    210                 } catch (IOException e) {
    211                     LOG.error("IOException when trying to include "
    212                         + "the error page path " + includePath, e);
    213                 } catch (ServletException e) {
    214                     LOG.error("ServletException when trying to include "
    215                         + "the error page path " + includePath, e);
    216                 }
    217             } else {
    218                 LOG.warn("Suspicious includePath doesn't seem likely to work, "
    219                     + "so skipping it: " + includePath
    220                     + "; expected path to start with '/'");
    221             }
    222         }
    223 
    224         LOG.debug("Include not available or failed; "
    225             + "try writing to the response directly.");
    226 
    227         try {
    228             response.getWriter().println("Unexpected error: " + ex);
    229             response.getWriter().println("<!-- ");
    230             ex.printStackTrace(response.getWriter());
    231             response.getWriter().println("-->");
    232         } catch (IOException e) {
    233             LOG.error("Error giving minimal information about exception", e);
    234             LOG.error("Original exception: ", ex);
    235         }
    236     }
    237 
    238     /**
    239      * <p>Return a path to which an include should be attempted in the case
    240      * when the response was committed before the <code>ExceptionHandler</code>
    241      * was invoked.  </p> <p>If the <code>ExceptionConfig</code> has the
    242      * property <code>INCLUDE_PATH</code> defined, then the value of that
    243      * property will be returned. Otherwise, the ActionForward path is
    244      * returned. </p>
    245      *
    246      * @param config        Configuration element
    247      * @param actionForward Forward to use on error
    248      * @return Path of resource to include
    249      * @since Struts 1.3
    250      */
    251     protected String determineIncludePath(ExceptionConfig config,
    252         ActionForward actionForward) {
    253         String includePath = config.getProperty("INCLUDE_PATH");
    254 
    255         if (includePath == null) {
    256             includePath = actionForward.getPath();
    257         }
    258 
    259         return includePath;
    260     }
    261 
    262     /**
    263      * <p>Logs the <code>Exception</code> using commons-logging.</p>
    264      *
    265      * @param e The Exception to LOG.
    266      * @since Struts 1.2
    267      */
    268     protected void logException(Exception e) {
    269         LOG.debug(messages.getMessage("exception.LOG"), e);
    270     }
    271 
    272     /**
    273      * <p>Default implementation for handling an <code>ActionMessage</code>
    274      * generated from an <code>Exception</code> during <code>Action</code>
    275      * delegation. The default implementation is to set an attribute of the
    276      * request or session, as defined by the scope provided (the scope from
    277      * the exception mapping). An <code>ActionMessages</code> instance is
    278      * created, the error is added to the collection and the collection is set
    279      * under the <code>Globals.ERROR_KEY</code>.</p>
    280      *
    281      * @param request  The request we are handling
    282      * @param property The property name to use for this error
    283      * @param error    The error generated from the exception mapping
    284      * @param forward  The forward generated from the input path (from the
    285      *                 form or exception mapping)
    286      * @param scope    The scope of the exception mapping.
    287      * @since Struts 1.2
    288      */
    289     protected void storeException(HttpServletRequest request, String property,
    290         ActionMessage error, ActionForward forward, String scope) {
    291         ActionMessages errors = new ActionMessages();
    292 
    293         errors.add(property, error);
    294 
    295         if ("request".equals(scope)) {
    296             request.setAttribute(Globals.ERROR_KEY, errors);
    297         } else {
    298             request.getSession().setAttribute(Globals.ERROR_KEY, errors);
    299         }
    300     }
    301 
    302     /**
    303      * <p>Indicate whether this Handler has been configured to be silent.  In
    304      * the base implementation, this is done by specifying the value
    305      * <code>"true"</code> for the property "SILENT_IF_COMMITTED" in the
    306      * ExceptionConfig.</p>
    307      *
    308      * @param config The ExceptionConfiguration we are handling
    309      * @return True if Handler is silent
    310      * @since Struts 1.3
    311      */
    312     private boolean silent(ExceptionConfig config) {
    313         return "true".equals(config.getProperty(SILENT_IF_COMMITTED));
    314     }
    315 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
