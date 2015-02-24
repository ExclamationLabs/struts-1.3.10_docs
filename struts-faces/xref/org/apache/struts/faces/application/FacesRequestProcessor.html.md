[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/application/FacesRequestProcessor.html.md)


    1   /*
    2    * $Id: FacesRequestProcessor.java 473326 2006-11-10 12:58:06Z niallp $
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
    22  package org.apache.struts.faces.application;
    23  
    24  
    25  import java.io.IOException;
    26  import javax.faces.FactoryFinder;
    27  import javax.faces.application.ViewHandler;
    28  import javax.faces.component.UICommand;
    29  import javax.faces.component.UIComponent;
    30  import javax.faces.context.FacesContext;
    31  import javax.faces.context.FacesContextFactory;
    32  import javax.faces.event.ActionEvent;
    33  import javax.faces.lifecycle.Lifecycle;
    34  import javax.faces.lifecycle.LifecycleFactory;
    35  import javax.servlet.ServletException;
    36  import javax.servlet.http.HttpServletRequest;
    37  import javax.servlet.http.HttpServletResponse;
    38  import org.apache.commons.logging.Log;
    39  import org.apache.commons.logging.LogFactory;
    40  import org.apache.struts.Globals;
    41  import org.apache.struts.action.Action;
    42  import org.apache.struts.action.ActionForm;
    43  import org.apache.struts.action.ActionForward;
    44  import org.apache.struts.action.ActionMapping;
    45  import org.apache.struts.action.RequestProcessor;
    46  import org.apache.struts.action.InvalidCancelException;
    47  import org.apache.struts.config.FormBeanConfig;
    48  import org.apache.struts.config.ForwardConfig;
    49  import org.apache.struts.faces.Constants;
    50  import org.apache.struts.faces.component.FormComponent;
    51  
    52  
    53  
    54  /**
    55   * <p>Concrete implementation of <code>RequestProcessor</code> that
    56   * implements the standard Struts request processing lifecycle on a
    57   * request that was received as an <code>ActionEvent</code> by our
    58   * associated <code>ActionListener</code>.  It replaces the request processor
    59   * instance normally configured by Struts, so it must support non-Faces
    60   * requests as well.</p>
    61   *
    62   * @version $Rev: 473326 $ $Date: 2006-11-10 06:58:06 -0600 (Fri, 10 Nov 2006) $
    63   */
    64  
    65  public class FacesRequestProcessor extends RequestProcessor {
    66  
    67  
    68      // ------------------------------------------------------ Instance Variables
    69  
    70  
    71      /**
    72       * <p>The log instance for this class.</p>
    73       */
    74      protected static Log log = LogFactory.getLog(FacesRequestProcessor.class);
    75  
    76  
    77      /**
    78       * <p>The lifecycle id.</p>
    79       */
    80      public static final String LIFECYCLE_ID_ATTR = "javax.faces.LIFECYCLE_ID";
    81  
    82      // ------------------------------------------------------- Protected Methods
    83  
    84  
    85      /**
    86       * <p>Set up a Faces Request if we are not already processing one.  Next,
    87       * create a new view if the specified <code>uri</code> is different from
    88       * the current view identifier.  Finally, cause the new view to be
    89       * rendered, and call <code>FacesContext.responseComplete()</code> to
    90       * indicate that this has already been done.</p>
    91       *
    92       * @param uri Context-relative path to forward to
    93       * @param request Current page request
    94       * @param response Current page response
    95       *
    96       * @exception IOException if an input/output error occurs
    97       * @exception ServletException if a servlet error occurs
    98       */
    99      protected void doForward(String uri,
    100                              HttpServletRequest request,
    101                              HttpServletResponse response)
    102         throws IOException, ServletException {
    103 
    104         if (log.isDebugEnabled()) {
    105             log.debug("doForward(" + uri + ")");
    106         }
    107 
    108         // Remove the current ActionEvent (if any)
    109         request.removeAttribute(Constants.ACTION_EVENT_KEY);
    110 
    111         // Process a Struts controller request normally
    112         if (isStrutsRequest(uri)) {
    113             if (response.isCommitted()) {
    114                 if (log.isTraceEnabled()) {
    115                     log.trace("  super.doInclude(" + uri + ")");
    116                 }
    117                 super.doInclude(uri, request, response);
    118             } else {
    119                 if (log.isTraceEnabled()) {
    120                     log.trace("  super.doForward(" + uri + ")");
    121                 }
    122                 super.doForward(uri, request, response);
    123             }
    124             return;
    125         }
    126 
    127         // Create a FacesContext for this request if necessary
    128         LifecycleFactory lf = (LifecycleFactory)
    129             FactoryFinder.getFactory(FactoryFinder.LIFECYCLE_FACTORY);
    130         Lifecycle lifecycle = 
    131             lf.getLifecycle(getLifecycleId());
    132         boolean created = false;
    133         FacesContext context = FacesContext.getCurrentInstance();
    134         if (context == null) {
    135             if (log.isTraceEnabled()) {
    136                 log.trace("  Creating new FacesContext for '" + uri + "'");
    137             }
    138             created = true;
    139             FacesContextFactory fcf = (FacesContextFactory)
    140                 FactoryFinder.getFactory(FactoryFinder.FACES_CONTEXT_FACTORY);
    141             context = fcf.getFacesContext(servlet.getServletContext(),
    142                                           request, response, lifecycle);
    143         }
    144 
    145         // Create a new view root
    146         ViewHandler vh = context.getApplication().getViewHandler();
    147         if (log.isTraceEnabled()) {
    148             log.trace("  Creating new view for '" + uri + "'");
    149         }
    150         context.setViewRoot(vh.createView(context, uri));
    151 
    152         // Cause the view to be rendered
    153         if (log.isTraceEnabled()) {
    154             log.trace("  Rendering view for '" + uri + "'");
    155         }
    156         try {
    157             lifecycle.render(context);
    158         } finally {
    159             if (created) {
    160                 if (log.isTraceEnabled()) {
    161                     log.trace("  Releasing context for '" + uri + "'");
    162                 }
    163                 context.release();
    164             } else {
    165                 if (log.isTraceEnabled()) {
    166                     log.trace("  Rendering completed");
    167                 }
    168             }
    169         }
    170 
    171     }
    172 
    173 
    174     // Override default processing to provide logging
    175     protected Action processActionCreate(HttpServletRequest request,
    176                                          HttpServletResponse response,
    177                                          ActionMapping mapping)
    178         throws IOException {
    179 
    180         if (log.isTraceEnabled()) {
    181             log.trace("Performing standard action create");
    182         }
    183         Action result = super.processActionCreate(request, response, mapping);
    184         if (log.isDebugEnabled()) {
    185             log.debug("Standard action create returned " +
    186                       result.getClass().getName() + " instance");
    187         }
    188         return (result);
    189 
    190     }
    191 
    192 
    193     // Override default processing to provide logging
    194     protected ActionForm processActionForm(HttpServletRequest request,
    195                                            HttpServletResponse response,
    196                                            ActionMapping mapping) {
    197         if (log.isTraceEnabled()) {
    198             log.trace("Performing standard action form processing");
    199             String attribute = mapping.getAttribute();
    200             if (attribute != null) {
    201                 String name = mapping.getName();
    202                 FormBeanConfig fbc = moduleConfig.findFormBeanConfig(name);
    203                 if (fbc != null) {
    204                     if ("request".equals(mapping.getScope())) {
    205                         log.trace("  Bean in request scope = " +
    206                                   request.getAttribute(attribute));
    207                     } else {
    208                         log.trace("  Bean in session scope = " +
    209                                   request.getSession().getAttribute(attribute));
    210                     }
    211                 } else {
    212                     log.trace("  No FormBeanConfig for '" + name + "'");
    213                 }
    214             } else {
    215                 log.trace("  No form bean for this action");
    216             }
    217         }
    218         ActionForm result =
    219             super.processActionForm(request, response, mapping);
    220         if (log.isDebugEnabled()) {
    221             log.debug("Standard action form returned " +
    222                       result);
    223         }
    224         return (result);
    225 
    226 
    227     }
    228 
    229 
    230     // Override default processing to provide logging
    231     protected ActionForward processActionPerform(HttpServletRequest request,
    232                                                  HttpServletResponse response,
    233                                                  Action action,
    234                                                  ActionForm form,
    235                                                  ActionMapping mapping)
    236         throws IOException, ServletException {
    237 
    238         if (log.isTraceEnabled()) {
    239             log.trace("Performing standard action perform");
    240         }
    241         ActionForward result =
    242             super.processActionPerform(request, response, action,
    243                                        form, mapping);
    244         if (log.isDebugEnabled()) {
    245             log.debug("Standard action perform returned " +
    246                       (result == null ? "NULL" :
    247                       result.getPath()) + " forward path");
    248         }
    249         return (result);
    250 
    251     }
    252 
    253 
    254     // Override default processing to provide logging
    255     protected boolean processForward(HttpServletRequest request,
    256                                      HttpServletResponse response,
    257                                      ActionMapping mapping)
    258         throws IOException, ServletException {
    259 
    260         if (log.isTraceEnabled()) {
    261             log.trace("Performing standard forward handling");
    262         }
    263         boolean result = super.processForward
    264             (request, response, mapping);
    265         if (log.isDebugEnabled()) {
    266             log.debug("Standard forward handling returned " + result);
    267         }
    268         return (result);
    269 
    270     }
    271 
    272 
    273     // Override default processing to provide logging
    274     protected void processForwardConfig(HttpServletRequest request,
    275                                         HttpServletResponse response,
    276                                         ForwardConfig forward)
    277         throws IOException, ServletException {
    278 
    279         if (log.isTraceEnabled()) {
    280             log.trace("Performing standard forward config handling");
    281         }
    282         super.processForwardConfig(request, response, forward);
    283         if (log.isDebugEnabled()) {
    284             log.debug("Standard forward config handling completed");
    285         }
    286 
    287     }
    288 
    289 
    290     // Override default processing to provide logging
    291     protected boolean processInclude(HttpServletRequest request,
    292                                      HttpServletResponse response,
    293                                      ActionMapping mapping)
    294         throws IOException, ServletException {
    295 
    296         if (log.isTraceEnabled()) {
    297             log.trace("Performing standard include handling");
    298         }
    299         boolean result = super.processInclude
    300             (request, response, mapping);
    301         if (log.isDebugEnabled()) {
    302             log.debug("Standard include handling returned " + result);
    303         }
    304         return (result);
    305 
    306     }
    307 
    308 
    309     /**
    310      * <p>Identify and return the path component (from the request URI for a
    311      * non-Faces request, or from the form event for a Faces request)
    312      * that we will use to select an ActionMapping to dispatch with.
    313      * If no such path can be identified, create an error response and return
    314      * <code>null</code>.</p>
    315      *
    316      * @param request The servlet request we are processing
    317      * @param response The servlet response we are creating
    318      *
    319      * @exception IOException if an input/output error occurs
    320      */
    321     protected String processPath(HttpServletRequest request,
    322                                  HttpServletResponse response)
    323         throws IOException {
    324 
    325         // Are we processing a Faces request?
    326         ActionEvent event = (ActionEvent)
    327             request.getAttribute(Constants.ACTION_EVENT_KEY);
    328 
    329         // Handle non-Faces requests in the usual way
    330         if (event == null) {
    331             if (log.isTraceEnabled()) {
    332                 log.trace("Performing standard processPath() processing");
    333             }
    334             return (super.processPath(request, response));
    335         }
    336 
    337         // Calculate the path from the form name
    338         UIComponent component = event.getComponent();
    339         if (log.isTraceEnabled()) {
    340             log.trace("Locating form parent for command component " +
    341                       event.getComponent());
    342         }
    343         while (!(component instanceof FormComponent)) {
    344             component = component.getParent();
    345             if (component == null) {
    346                 log.warn("Command component was not nested in a Struts form!");
    347                 return (null);
    348             }
    349         }
    350         if (log.isDebugEnabled()) {
    351             log.debug("Returning selected path of '" +
    352                       ((FormComponent) component).getAction() + "'");
    353         }
    354         return (((FormComponent) component).getAction());
    355 
    356     }
    357 
    358 
    359     /**
    360      * <p>Populate the properties of the specified <code>ActionForm</code>
    361      * instance from the request parameters included with this request,
    362      * <strong>IF</strong> this is a non-Faces request.  For a Faces request,
    363      * this will have already been done by the <em>Update Model Values</em>
    364      * phase of the request processing lifecycle, so all we have to do is
    365      * recognize whether the request was cancelled or not.</p>
    366      *
    367      * @param request The servlet request we are processing
    368      * @param response The servlet response we are creating
    369      * @param form The ActionForm instance we are populating
    370      * @param mapping The ActionMapping we are using
    371      *
    372      * @exception ServletException if thrown by RequestUtils.populate()
    373      */
    374     protected void processPopulate(HttpServletRequest request,
    375                                    HttpServletResponse response,
    376                                    ActionForm form,
    377                                    ActionMapping mapping)
    378         throws ServletException {
    379 
    380         // Are we processing a Faces request?
    381         ActionEvent event = (ActionEvent)
    382             request.getAttribute(Constants.ACTION_EVENT_KEY);
    383 
    384         // Handle non-Faces requests in the usual way
    385         if (event == null) {
    386             if (log.isTraceEnabled()) {
    387                 log.trace("Performing standard processPopulate() processing");
    388             }
    389             super.processPopulate(request, response, form, mapping);
    390             return;
    391         }
    392 
    393         // Faces Requests require no processing for form bean population
    394         // so we need only check for the cancellation command name
    395         if (log.isTraceEnabled()) {
    396             log.trace("Faces request, so no processPopulate() processing");
    397         }
    398         UIComponent source = event.getComponent();
    399         if (source instanceof UICommand) {
    400             if ("cancel".equals(((UICommand) source).getId())) {
    401                 if (log.isTraceEnabled()) {
    402                     log.trace("Faces request with cancel button pressed");
    403                 }
    404                 request.setAttribute(Globals.CANCEL_KEY, Boolean.TRUE);
    405             }
    406         }
    407 
    408     }
    409 
    410 
    411     // Override default processing to provide logging
    412     protected boolean processValidate(HttpServletRequest request,
    413                                       HttpServletResponse response,
    414                                       ActionForm form,
    415                                       ActionMapping mapping)
    416         throws IOException, ServletException, InvalidCancelException {
    417 
    418         if (log.isTraceEnabled()) {
    419             log.trace("Performing standard validation");
    420         }
    421         boolean result = super.processValidate
    422             (request, response, form, mapping);
    423         if (log.isDebugEnabled()) {
    424             log.debug("Standard validation processing returned " + result);
    425         }
    426         return (result);
    427 
    428     }
    429 
    430 
    431     // --------------------------------------------------------- Private Methods
    432 
    433 
    434     /**
    435      * <p>Return the used Lifecycle ID (default or custom).</p>
    436      */
    437     private String getLifecycleId()
    438     {
    439         String lifecycleId = this.servlet.getServletContext().getInitParameter(LIFECYCLE_ID_ATTR);
    440         return lifecycleId != null ? lifecycleId : LifecycleFactory.DEFAULT_LIFECYCLE;
    441     }  
    442 
    443     /**
    444      * <p>Return <code>true</code> if the specified context-relative URI
    445      * specifies a request to be processed by the Struts controller servlet.</p>
    446      *
    447      * @param uri URI to be checked
    448      */
    449     private boolean isStrutsRequest(String uri) {
    450 
    451         int question = uri.indexOf("?");
    452         if (question >= 0) {
    453             uri = uri.substring(0, question);
    454         }
    455         String mapping = (String)
    456             servlet.getServletContext().getAttribute(Globals.SERVLET_KEY);
    457         if (mapping == null) {
    458             return (false);
    459         } else if (mapping.startsWith("*.")) {
    460             return (uri.endsWith(mapping.substring(1)));
    461         } else if (mapping.endsWith("/*")) {
    462             return (uri.startsWith(mapping.substring(0, mapping.length() - 2)));
    463         } else {
    464             return (false);
    465         }
    466 
    467     }
    468 
    469 
    470 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
