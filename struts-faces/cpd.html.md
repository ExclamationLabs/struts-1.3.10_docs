<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Faces

-   [Welcome](index.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)
    -   [Checkstyle](checkstyle.html.md)
    -   **CPD Report**
    -   [JavaDocs](apidocs/index.html.md)
    -   [PMD Report](pmd.html.md)
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)
    -   [Taglibdoc documentation](tlddoc/index.html.md)
    -   [Tag library validation](taglibvalidation.html.md)
    -   [Tag reference](tagreference.html.md)
    -   [Test JavaDocs](testapidocs/index.html.md)
    -   [Test Source Xref](xref-test/index.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

CPD Results
-----------

The following document contains the results of PMD's [CPD](http://pmd.sourceforge.net/cpd.html.md) 4.2.2.

Duplications
------------

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------

File
Line
org\\apache\\struts\\faces\\application\\FacesRequestProcessor.java
[171](./xref/org/apache/struts/faces/application/FacesRequestProcessor.html.md#171)
org\\apache\\struts\\faces\\application\\FacesTilesRequestProcessor.java
[185](./xref/org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md#185)
        }


        // Override default processing to provide logging
        protected Action processActionCreate(HttpServletRequest request,
                                             HttpServletResponse response,
                                             ActionMapping mapping)
            throws IOException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard action create");
            }
            Action result = super.processActionCreate(request, response, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard action create returned " +
                          result.getClass().getName() + " instance");
            }
            return (result);

        }


        // Override default processing to provide logging
        protected ActionForm processActionForm(HttpServletRequest request,
                                               HttpServletResponse response,
                                               ActionMapping mapping) {
            if (log.isTraceEnabled()) {
                log.trace("Performing standard action form processing");
                String attribute = mapping.getAttribute();
                if (attribute != null) {
                    String name = mapping.getName();
                    FormBeanConfig fbc = moduleConfig.findFormBeanConfig(name);
                    if (fbc != null) {
                        if ("request".equals(mapping.getScope())) {
                            log.trace("  Bean in request scope = " +
                                      request.getAttribute(attribute));
                        } else {
                            log.trace("  Bean in session scope = " +
                                      request.getSession().getAttribute(attribute));
                        }
                    } else {
                        log.trace("  No FormBeanConfig for '" + name + "'");
                    }
                } else {
                    log.trace("  No form bean for this action");
                }
            }
            ActionForm result =
                super.processActionForm(request, response, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard action form returned " +
                          result);
            }
            return (result);


        }


        // Override default processing to provide logging
        protected ActionForward processActionPerform(HttpServletRequest request,
                                                     HttpServletResponse response,
                                                     Action action,
                                                     ActionForm form,
                                                     ActionMapping mapping)
            throws IOException, ServletException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard action perform");
            }
            ActionForward result =
                super.processActionPerform(request, response, action,
                                           form, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard action perform returned " +
                          (result == null ? "NULL" :
                          result.getPath()) + " forward path");
            }
            return (result);

        }


        // Override default processing to provide logging
        protected boolean processForward(HttpServletRequest request,
                                         HttpServletResponse response,
                                         ActionMapping mapping)
            throws IOException, ServletException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard forward handling");
            }
            boolean result = super.processForward
                (request, response, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard forward handling returned " + result);
            }
            return (result);

        }


        // Override default processing to provide logging
        protected void processForwardConfig(HttpServletRequest request,
                                            HttpServletResponse response,
                                            ForwardConfig forward)
            throws IOException, ServletException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard forward config handling");
            }
            super.processForwardConfig(request, response, forward);
            if (log.isDebugEnabled()) {
                log.debug("Standard forward config handling completed");
            }

        }


        // Override default processing to provide logging
        protected boolean processInclude(HttpServletRequest request,
                                         HttpServletResponse response,
                                         ActionMapping mapping)
            throws IOException, ServletException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard include handling");
            }
            boolean result = super.processInclude
                (request, response, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard include handling returned " + result);
            }
            return (result);

        }


        /**
         * <p>Identify and return the path component (from the request URI for a
         * non-Faces request, or from the form event for a Faces request)
         * that we will use to select an ActionMapping to dispatch with.
         * If no such path can be identified, create an error response and return
         * <code>null</code>.</p>
         *
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception IOException if an input/output error occurs
         */
        protected String processPath(HttpServletRequest request,
                                     HttpServletResponse response)
            throws IOException {

            // Are we processing a Faces request?
            ActionEvent event = (ActionEvent)
                request.getAttribute(Constants.ACTION_EVENT_KEY);

            // Handle non-Faces requests in the usual way
            if (event == null) {
                if (log.isTraceEnabled()) {
                    log.trace("Performing standard processPath() processing");
                }
                return (super.processPath(request, response));
            }

            // Calculate the path from the form name
            UIComponent component = event.getComponent();
            if (log.isTraceEnabled()) {
                log.trace("Locating form parent for command component " +
                          event.getComponent());
            }
            while (!(component instanceof FormComponent)) {
                component = component.getParent();
                if (component == null) {
                    log.warn("Command component was not nested in a Struts form!");
                    return (null);
                }
            }
            if (log.isTraceEnabled()) {

File
Line
org\\apache\\struts\\faces\\application\\FacesRequestProcessor.java
[352](./xref/org/apache/struts/faces/application/FacesRequestProcessor.html.md#352)
org\\apache\\struts\\faces\\application\\FacesTilesRequestProcessor.java
[366](./xref/org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md#366)
                          ((FormComponent) component).getAction());
            }
            return (((FormComponent) component).getAction());

        }


        /**
         * <p>Populate the properties of the specified <code>ActionForm</code>
         * instance from the request parameters included with this request,
         * <strong>IF</strong> this is a non-Faces request.  For a Faces request,
         * this will have already been done by the <em>Update Model Values</em>
         * phase of the request processing lifecycle, so all we have to do is
         * recognize whether the request was cancelled or not.</p>
         *
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         * @param form The ActionForm instance we are populating
         * @param mapping The ActionMapping we are using
         *
         * @exception ServletException if thrown by RequestUtils.populate()
         */
        protected void processPopulate(HttpServletRequest request,
                                       HttpServletResponse response,
                                       ActionForm form,
                                       ActionMapping mapping)
            throws ServletException {

            // Are we processing a Faces request?
            ActionEvent event = (ActionEvent)
                request.getAttribute(Constants.ACTION_EVENT_KEY);

            // Handle non-Faces requests in the usual way
            if (event == null) {
                if (log.isTraceEnabled()) {
                    log.trace("Performing standard processPopulate() processing");
                }
                super.processPopulate(request, response, form, mapping);
                return;
            }

            // Faces Requests require no processing for form bean population
            // so we need only check for the cancellation command name
            if (log.isTraceEnabled()) {
                log.trace("Faces request, so no processPopulate() processing");
            }
            UIComponent source = event.getComponent();
            if (source instanceof UICommand) {
                if ("cancel".equals(((UICommand) source).getId())) {
                    if (log.isTraceEnabled()) {
                        log.trace("Faces request with cancel button pressed");
                    }
                    request.setAttribute(Globals.CANCEL_KEY, Boolean.TRUE);
                }
            }

        }


        // Override default processing to provide logging
        protected boolean processValidate(HttpServletRequest request,
                                          HttpServletResponse response,
                                          ActionForm form,
                                          ActionMapping mapping)
            throws IOException, ServletException, InvalidCancelException {

            if (log.isTraceEnabled()) {
                log.trace("Performing standard validation");
            }
            boolean result = super.processValidate
                (request, response, form, mapping);
            if (log.isDebugEnabled()) {
                log.debug("Standard validation processing returned " + result);
            }
            return (result);

        }


        // --------------------------------------------------------- Private Methods


        /**
         * <p>Return the used Lifecycle ID (default or custom).</p>
         */
        private String getLifecycleId()
        {
            String lifecycleId = this.servlet.getServletContext().getInitParameter(LIFECYCLE_ID_ATTR);
            return lifecycleId != null ? lifecycleId : LifecycleFactory.DEFAULT_LIFECYCLE;
        }  

        /**
         * <p>Return <code>true</code> if the specified context-relative URI
         * specifies a request to be processed by the Struts controller servlet.</p>
         *
         * @param uri URI to be checked
         */
        private boolean isStrutsRequest(String uri) {

            int question = uri.indexOf("?");
            if (question >= 0) {
                uri = uri.substring(0, question);
            }
            String mapping = (String)
                servlet.getServletContext().getAttribute(Globals.SERVLET_KEY);
            if (mapping == null) {
                return (false);
            } else if (mapping.startsWith("*.")) {
                return (uri.endsWith(mapping.substring(1)));
            } else if (mapping.endsWith("/*")) {
                return (uri.startsWith(mapping.substring(0, mapping.length() - 2)));
            } else {
                return (false);
            }

        }


    }

File
Line
org\\apache\\struts\\faces\\application\\FacesRequestProcessor.java
[74](./xref/org/apache/struts/faces/application/FacesRequestProcessor.html.md#74)
org\\apache\\struts\\faces\\application\\FacesTilesRequestProcessor.java
[74](./xref/org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md#74)
            LogFactory.getLog(FacesTilesRequestProcessor.class);

        /**
         * <p>The lifecycle id.</p>
         */
        public static final String LIFECYCLE_ID_ATTR = "javax.faces.LIFECYCLE_ID";


        // ------------------------------------------------------- Protected Methods


        /**
         * <p>Set up a Faces Request if we are not already processing one.  Next,
         * create a new view if the specified <code>uri</code> is different from
         * the current view identifier.  Finally, cause the new view to be
         * rendered, and call <code>FacesContext.responseComplete()</code> to
         * indicate that this has already been done.</p>
         *
         * @param uri Context-relative path to forward to
         * @param request Current page request
         * @param response Current page response
         *
         * @exception IOException if an input/output error occurs
         * @exception ServletException if a servlet error occurs
         */
        protected void doForward(String uri,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
            throws IOException, ServletException {

            if (log.isDebugEnabled()) {
                log.debug("doForward(" + uri + ")");
            }

            // Remove the current ActionEvent (if any)
            request.removeAttribute(Constants.ACTION_EVENT_KEY);

            // Process a Struts controller request normally
            if (isStrutsRequest(uri)) {
                if (response.isCommitted()) {
                    if (log.isTraceEnabled()) {
                        log.trace("  super.doInclude(" + uri + ")");
                    }
                    super.doInclude(uri, request, response);
                } else {
                    if (log.isTraceEnabled()) {
                        log.trace("  super.doForward(" + uri + ")");
                    }
                    super.doForward(uri, request, response);
                }
                return;
            }

            // Create a FacesContext for this request if necessary
            LifecycleFactory lf = (LifecycleFactory)
                FactoryFinder.getFactory(FactoryFinder.LIFECYCLE_FACTORY);
            Lifecycle lifecycle = 
                lf.getLifecycle(getLifecycleId());
            boolean created = false;
            FacesContext context = FacesContext.getCurrentInstance();
            if (context == null) {
                if (log.isTraceEnabled()) {
                    log.trace("  Creating new FacesContext for '" + uri + "'");
                }
                created = true;
                FacesContextFactory fcf = (FacesContextFactory)
                    FactoryFinder.getFactory(FactoryFinder.FACES_CONTEXT_FACTORY);
                context = fcf.getFacesContext(servlet.getServletContext(),
                                              request, response, lifecycle);
            }

            // Create a new view root
            ViewHandler vh = context.getApplication().getViewHandler();
            if (log.isTraceEnabled()) {
                log.trace("  Creating new view for '" + uri + "'");
            }
            context.setViewRoot(vh.createView(context, uri));

            // Cause the view to be rendered
            if (log.isTraceEnabled()) {
                log.trace("  Rendering view for '" + uri + "'");
            }
            try {
                lifecycle.render(context);
            } finally {
                if (created) {
                    if (log.isTraceEnabled()) {
                        log.trace("  Releasing context for '" + uri + "'");
                    }
                    context.release();
                } else {
                    if (log.isTraceEnabled()) {
                        log.trace("  Rendering completed");
                    }
                }
            }

        }


        // Override default processing to provide logging
        protected void internalModuleRelativeForward

File
Line
org\\apache\\struts\\faces\\component\\MessageComponent.java
[185](./xref/org/apache/struts/faces/component/MessageComponent.html.md#185)
org\\apache\\struts\\faces\\component\\WriteComponent.java
[119](./xref/org/apache/struts/faces/component/WriteComponent.html.md#119)
        }


        /**
         * <p>Return the CSS style(s) to be rendered for this component.</p>
         */
        public String getStyle() {

            ValueBinding vb = getValueBinding("style");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return style;
            }

        }


        /**
         * <p>Set the CSS style(s) to be rendered for this component.</p>
         *
         * @param style The new CSS style(s)
         */
        public void setStyle(String style) {

            this.style = style;

        }


        /**
         * <p>Return the CSS style class(es) to be rendered for this component.</p>
         */
        public String getStyleClass() {

            ValueBinding vb = getValueBinding("styleClass");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return styleClass;
            }

        }


        /**
         * <p>Set the CSS style class(es) to be rendered for this component.</p>
         *
         * @param styleClass The new CSS style class(es)
         */
        public void setStyleClass(String styleClass) {

            this.styleClass = styleClass;

        }


        // ---------------------------------------------------- StateManager Methods


        /**
         * <p>Restore the state of this component.</p>
         *
         * @param context <code>FacesContext</code> for the current request
         * @param state State object from which to restore our state
         */
        public void restoreState(FacesContext context, Object state) {

            Object values[] = (Object[]) state;
            super.restoreState(context, values[0]);

File
Line
org\\apache\\struts\\faces\\component\\CommandLinkComponent.java
[361](./xref/org/apache/struts/faces/component/CommandLinkComponent.html.md#361)
org\\apache\\struts\\faces\\component\\FormComponent.java
[267](./xref/org/apache/struts/faces/component/FormComponent.html.md#267)
        }


        /**
         * <p>Return the CSS style(s) to be rendered for this component.</p>
         */
        public String getStyle() {

            ValueBinding vb = getValueBinding("style");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return style;
            }

        }


        /**
         * <p>Set the CSS style(s) to be rendered for this component.</p>
         *
         * @param style The new CSS style(s)
         */
        public void setStyle(String style) {

            this.style = style;

        }


        /**
         * <p>Return the CSS style class(es) to be rendered for this component.</p>
         */
        public String getStyleClass() {

            ValueBinding vb = getValueBinding("styleClass");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return styleClass;
            }

        }


        /**
         * <p>Set the CSS style class(es) to be rendered for this component.</p>
         *
         * @param styleClass The new CSS style class(es)
         */
        public void setStyleClass(String styleClass) {

            this.styleClass = styleClass;

        }


        /**
         * <p>Return the target frame for the response to this form submit.</p>
         */
        public String getTarget() {

File
Line
org\\apache\\struts\\faces\\component\\CommandLinkComponent.java
[361](./xref/org/apache/struts/faces/component/CommandLinkComponent.html.md#361)
org\\apache\\struts\\faces\\component\\MessageComponent.java
[185](./xref/org/apache/struts/faces/component/MessageComponent.html.md#185)
        }


        /**
         * <p>Return the CSS style(s) to be rendered for this component.</p>
         */
        public String getStyle() {

            ValueBinding vb = getValueBinding("style");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return style;
            }

        }


        /**
         * <p>Set the CSS style(s) to be rendered for this component.</p>
         *
         * @param style The new CSS style(s)
         */
        public void setStyle(String style) {

            this.style = style;

        }


        /**
         * <p>Return the CSS style class(es) to be rendered for this component.</p>
         */
        public String getStyleClass() {

            ValueBinding vb = getValueBinding("styleClass");
            if (vb != null) {
                return (String) vb.getValue(getFacesContext());
            } else {
                return styleClass;
            }

        }


        /**
         * <p>Set the CSS style class(es) to be rendered for this component.</p>
         *
         * @param styleClass The new CSS style class(es)
         */
        public void setStyleClass(String styleClass) {

            this.styleClass = styleClass;

        }


        // ---------------------------------------------------- StateManager Methods


        /**
         * <p>Restore the state of this component.</p>
         *
         * @param context <code>FacesContext</code> for the current request
         * @param state State object from which to restore our state
         */
        public void restoreState(FacesContext context, Object state) {

File
Line
org\\apache\\struts\\faces\\component\\CommandLinkComponent.java
[60](./xref/org/apache/struts/faces/component/CommandLinkComponent.html.md#60)
org\\apache\\struts\\faces\\taglib\\CommandLinkTag.java
[51](./xref/org/apache/struts/faces/taglib/CommandLinkTag.html.md#51)
        private String immediate = null;
        private String lang = null;
        private String onblur = null;
        private String onclick = null;
        private String ondblclick = null;
        private String onfocus = null;
        private String onkeydown = null;
        private String onkeypress = null;
        private String onkeyup = null;
        private String onmousedown = null;
        private String onmousemove = null;
        private String onmouseout = null;
        private String onmouseover = null;
        private String onmouseup = null;
        private String rel = null;
        private String rev = null;
        private String style = null;
        private String styleClass = null;
        private String tabindex = null;
        private String target = null;
        private String title = null;
        private String type = null;


        // ---------------------------------------------------------- Tag Attributes


        public void setAccesskey(String accesskey) {


