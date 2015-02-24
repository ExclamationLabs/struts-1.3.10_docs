[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md)


    1   /*
    2    * $Id: FacesTilesRequestProcessor.java 473326 2006-11-10 12:58:06Z niallp $
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
    45  import org.apache.struts.action.InvalidCancelException;
    46  import org.apache.struts.config.FormBeanConfig;
    47  import org.apache.struts.config.ForwardConfig;
    48  import org.apache.struts.faces.Constants;
    49  import org.apache.struts.faces.component.FormComponent;
    50  import org.apache.struts.tiles.TilesRequestProcessor;
    51  
    52  
    53  /**
    54   * <p>Concrete implementation of <code>RequestProcessor</code> that
    55   * implements the standard Struts request processing lifecycle on a
    56   * request that was received as an <code>ActionEvent</code> by our
    57   * associated <code>ActionListener</code>.  It replaces the request processor
    58   * instance normally configured by Struts+Tiles, so it must support non-Faces
    59   * requests as well.</p>
    60   *
    61   * @version $Rev: 473326 $ $Date: 2006-11-10 06:58:06 -0600 (Fri, 10 Nov 2006) $
    62   */
    63  
    64  public class FacesTilesRequestProcessor extends TilesRequestProcessor {
    65  
    66  
    67      // ------------------------------------------------------ Instance Variables
    68  
    69  
    70      /**
    71       * <p>The log instance for this class.</p>
    72       */
    73      protected static Log log =
    74          LogFactory.getLog(FacesTilesRequestProcessor.class);
    75  
    76      /**
    77       * <p>The lifecycle id.</p>
    78       */
    79      public static final String LIFECYCLE_ID_ATTR = "javax.faces.LIFECYCLE_ID";
    80  
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
    175     protected void internalModuleRelativeForward
    176         (String uri, HttpServletRequest request, HttpServletResponse response)
    177         throws IOException, ServletException {
    178 
    179         if (log.isTraceEnabled()) {
    180             log.trace("Performing internal module relative forward to '" +
    181                       uri + "'");
    182         }
    183         super.internalModuleRelativeForward(uri, request, response);
    184 
    185     }
    186 
    187 
    188     // Override default processing to provide logging
    189     protected Action processActionCreate(HttpServletRequest request,
    190                                          HttpServletResponse response,
    191                                          ActionMapping mapping)
    192         throws IOException {
    193 
    194         if (log.isTraceEnabled()) {
    195             log.trace("Performing standard action create");
    196         }
    197         Action result = super.processActionCreate(request, response, mapping);
    198         if (log.isDebugEnabled()) {
    199             log.debug("Standard action create returned " +
    200                       result.getClass().getName() + " instance");
    201         }
    202         return (result);
    203 
    204     }
    205 
    206 
    207     // Override default processing to provide logging
    208     protected ActionForm processActionForm(HttpServletRequest request,
    209                                            HttpServletResponse response,
    210                                            ActionMapping mapping) {
    211         if (log.isTraceEnabled()) {
    212             log.trace("Performing standard action form processing");
    213             String attribute = mapping.getAttribute();
    214             if (attribute != null) {
    215                 String name = mapping.getName();
    216                 FormBeanConfig fbc = moduleConfig.findFormBeanConfig(name);
    217                 if (fbc != null) {
    218                     if ("request".equals(mapping.getScope())) {
    219                         log.trace("  Bean in request scope = " +
    220                                   request.getAttribute(attribute));
    221                     } else {
    222                         log.trace("  Bean in session scope = " +
    223                                   request.getSession().getAttribute(attribute));
    224                     }
    225                 } else {
    226                     log.trace("  No FormBeanConfig for '" + name + "'");
    227                 }
    228             } else {
    229                 log.trace("  No form bean for this action");
    230             }
    231         }
    232         ActionForm result =
    233             super.processActionForm(request, response, mapping);
    234         if (log.isDebugEnabled()) {
    235             log.debug("Standard action form returned " +
    236                       result);
    237         }
    238         return (result);
    239 
    240 
    241     }
    242 
    243 
    244     // Override default processing to provide logging
    245     protected ActionForward processActionPerform(HttpServletRequest request,
    246                                                  HttpServletResponse response,
    247                                                  Action action,
    248                                                  ActionForm form,
    249                                                  ActionMapping mapping)
    250         throws IOException, ServletException {
    251 
    252         if (log.isTraceEnabled()) {
    253             log.trace("Performing standard action perform");
    254         }
    255         ActionForward result =
    256             super.processActionPerform(request, response, action,
    257                                        form, mapping);
    258         if (log.isDebugEnabled()) {
    259             log.debug("Standard action perform returned " +
    260                       (result == null ? "NULL" :
    261                       result.getPath()) + " forward path");
    262         }
    263         return (result);
    264 
    265     }
    266 
    267 
    268     // Override default processing to provide logging
    269     protected boolean processForward(HttpServletRequest request,
    270                                      HttpServletResponse response,
    271                                      ActionMapping mapping)
    272         throws IOException, ServletException {
    273 
    274         if (log.isTraceEnabled()) {
    275             log.trace("Performing standard forward handling");
    276         }
    277         boolean result = super.processForward
    278             (request, response, mapping);
    279         if (log.isDebugEnabled()) {
    280             log.debug("Standard forward handling returned " + result);
    281         }
    282         return (result);
    283 
    284     }
    285 
    286 
    287     // Override default processing to provide logging
    288     protected void processForwardConfig(HttpServletRequest request,
    289                                         HttpServletResponse response,
    290                                         ForwardConfig forward)
    291         throws IOException, ServletException {
    292 
    293         if (log.isTraceEnabled()) {
    294             log.trace("Performing standard forward config handling");
    295         }
    296         super.processForwardConfig(request, response, forward);
    297         if (log.isDebugEnabled()) {
    298             log.debug("Standard forward config handling completed");
    299         }
    300 
    301     }
    302 
    303 
    304     // Override default processing to provide logging
    305     protected boolean processInclude(HttpServletRequest request,
    306                                      HttpServletResponse response,
    307                                      ActionMapping mapping)
    308         throws IOException, ServletException {
    309 
    310         if (log.isTraceEnabled()) {
    311             log.trace("Performing standard include handling");
    312         }
    313         boolean result = super.processInclude
    314             (request, response, mapping);
    315         if (log.isDebugEnabled()) {
    316             log.debug("Standard include handling returned " + result);
    317         }
    318         return (result);
    319 
    320     }
    321 
    322 
    323     /**
    324      * <p>Identify and return the path component (from the request URI for a
    325      * non-Faces request, or from the form event for a Faces request)
    326      * that we will use to select an ActionMapping to dispatch with.
    327      * If no such path can be identified, create an error response and return
    328      * <code>null</code>.</p>
    329      *
    330      * @param request The servlet request we are processing
    331      * @param response The servlet response we are creating
    332      *
    333      * @exception IOException if an input/output error occurs
    334      */
    335     protected String processPath(HttpServletRequest request,
    336                                  HttpServletResponse response)
    337         throws IOException {
    338 
    339         // Are we processing a Faces request?
    340         ActionEvent event = (ActionEvent)
    341             request.getAttribute(Constants.ACTION_EVENT_KEY);
    342 
    343         // Handle non-Faces requests in the usual way
    344         if (event == null) {
    345             if (log.isTraceEnabled()) {
    346                 log.trace("Performing standard processPath() processing");
    347             }
    348             return (super.processPath(request, response));
    349         }
    350 
    351         // Calculate the path from the form name
    352         UIComponent component = event.getComponent();
    353         if (log.isTraceEnabled()) {
    354             log.trace("Locating form parent for command component " +
    355                       event.getComponent());
    356         }
    357         while (!(component instanceof FormComponent)) {
    358             component = component.getParent();
    359             if (component == null) {
    360                 log.warn("Command component was not nested in a Struts form!");
    361                 return (null);
    362             }
    363         }
    364         if (log.isTraceEnabled()) {
    365             log.trace("Returning selected path of " +
    366                       ((FormComponent) component).getAction());
    367         }
    368         return (((FormComponent) component).getAction());
    369 
    370     }
    371 
    372 
    373     /**
    374      * <p>Populate the properties of the specified <code>ActionForm</code>
    375      * instance from the request parameters included with this request,
    376      * <strong>IF</strong> this is a non-Faces request.  For a Faces request,
    377      * this will have already been done by the <em>Update Model Values</em>
    378      * phase of the request processing lifecycle, so all we have to do is
    379      * recognize whether the request was cancelled or not.</p>
    380      *
    381      * @param request The servlet request we are processing
    382      * @param response The servlet response we are creating
    383      * @param form The ActionForm instance we are populating
    384      * @param mapping The ActionMapping we are using
    385      *
    386      * @exception ServletException if thrown by RequestUtils.populate()
    387      */
    388     protected void processPopulate(HttpServletRequest request,
    389                                    HttpServletResponse response,
    390                                    ActionForm form,
    391                                    ActionMapping mapping)
    392         throws ServletException {
    393 
    394         // Are we processing a Faces request?
    395         ActionEvent event = (ActionEvent)
    396             request.getAttribute(Constants.ACTION_EVENT_KEY);
    397 
    398         // Handle non-Faces requests in the usual way
    399         if (event == null) {
    400             if (log.isTraceEnabled()) {
    401                 log.trace("Performing standard processPopulate() processing");
    402             }
    403             super.processPopulate(request, response, form, mapping);
    404             return;
    405         }
    406 
    407         // Faces Requests require no processing for form bean population
    408         // so we need only check for the cancellation command name
    409         if (log.isTraceEnabled()) {
    410             log.trace("Faces request, so no processPopulate() processing");
    411         }
    412         UIComponent source = event.getComponent();
    413         if (source instanceof UICommand) {
    414             if ("cancel".equals(((UICommand) source).getId())) {
    415                 if (log.isTraceEnabled()) {
    416                     log.trace("Faces request with cancel button pressed");
    417                 }
    418                 request.setAttribute(Globals.CANCEL_KEY, Boolean.TRUE);
    419             }
    420         }
    421 
    422     }
    423 
    424 
    425     // Override default processing to provide logging
    426     protected boolean processValidate(HttpServletRequest request,
    427                                       HttpServletResponse response,
    428                                       ActionForm form,
    429                                       ActionMapping mapping)
    430         throws IOException, ServletException, InvalidCancelException {
    431 
    432         if (log.isTraceEnabled()) {
    433             log.trace("Performing standard validation");
    434         }
    435         boolean result = super.processValidate
    436             (request, response, form, mapping);
    437         if (log.isDebugEnabled()) {
    438             log.debug("Standard validation processing returned " + result);
    439         }
    440         return (result);
    441 
    442     }
    443 
    444 
    445     // --------------------------------------------------------- Private Methods
    446 
    447 
    448     /**
    449      * <p>Return the used Lifecycle ID (default or custom).</p>
    450      */
    451     private String getLifecycleId()
    452     {
    453         String lifecycleId = this.servlet.getServletContext().getInitParameter(LIFECYCLE_ID_ATTR);
    454         return lifecycleId != null ? lifecycleId : LifecycleFactory.DEFAULT_LIFECYCLE;
    455     }  
    456 
    457     /**
    458      * <p>Return <code>true</code> if the specified context-relative URI
    459      * specifies a request to be processed by the Struts controller servlet.</p>
    460      *
    461      * @param uri URI to be checked
    462      */
    463     private boolean isStrutsRequest(String uri) {
    464 
    465         int question = uri.indexOf("?");
    466         if (question >= 0) {
    467             uri = uri.substring(0, question);
    468         }
    469         String mapping = (String)
    470             servlet.getServletContext().getAttribute(Globals.SERVLET_KEY);
    471         if (mapping == null) {
    472             return (false);
    473         } else if (mapping.startsWith("*.")) {
    474             return (uri.endsWith(mapping.substring(1)));
    475         } else if (mapping.endsWith("/*")) {
    476             return (uri.startsWith(mapping.substring(0, mapping.length() - 2)));
    477         } else {
    478             return (false);
    479         }
    480 
    481     }
    482 
    483 
    484 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
