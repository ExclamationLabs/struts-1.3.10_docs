<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Extras

-   [Welcome](index.html.md)

##### FAQs and HOWTOs

-   [Dispatching And Validating](dispatchValidator.html.md)

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
org\\apache\\struts\\actions\\ActionDispatcher.java
[175](./xref/org/apache/struts/actions/ActionDispatcher.html.md#175)
org\\apache\\struts\\actions\\DispatchAction.java
[123](./xref/org/apache/struts/actions/DispatchAction.html.md#123)
            };

        // --------------------------------------------------------- Public Methods

        /**
         * Process the specified HTTP request, and create the corresponding HTTP
         * response (or forward to another web component that will create it).
         * Return an <code>ActionForward</code> instance describing where and how
         * control should be forwarded, or <code>null</code> if the response has
         * already been completed.
         *
         * @param mapping  The ActionMapping used to select this instance
         * @param form     The optional ActionForm bean for this request (if any)
         * @param request  The HTTP request we are processing
         * @param response The HTTP response we are creating
         * @return The forward to which control should be transferred, or
         *         <code>null</code> if the response has been completed.
         * @throws Exception if an exception occurs
         */
        public ActionForward execute(ActionMapping mapping, ActionForm form,
            HttpServletRequest request, HttpServletResponse response)
            throws Exception {
            if (isCancelled(request)) {
                ActionForward af = cancelled(mapping, form, request, response);

                if (af != null) {
                    return af;
                }
            }

            // Get the parameter. This could be overridden in subclasses.
            String parameter = getParameter(mapping, form, request, response);

            // Get the method's name. This could be overridden in subclasses.
            String name =
                getMethodName(mapping, form, request, response, parameter);

            // Prevent recursive calls
            if ("execute".equals(name) || "perform".equals(name)) {
                String message =
                    messages.getMessage("dispatch.recursive", mapping.getPath());

                log.error(message);
                throw new ServletException(message);
            }

            // Invoke the named method, and return the result
            return dispatchMethod(mapping, form, request, response, name);
        }

        /**
         * Method which is dispatched to when there is no value for specified
         * request parameter included in the request.  Subclasses of
         * <code>DispatchAction</code> should override this method if they wish to
         * provide default behavior different than throwing a ServletException.
         *
         * @param mapping  The ActionMapping used to select this instance
         * @param form     The optional ActionForm bean for this request (if any)
         * @param request  The non-HTTP request we are processing
         * @param response The non-HTTP response we are creating
         * @return The forward to which control should be transferred, or
         *         <code>null</code> if the response has been completed.
         * @throws Exception if the application business logic throws an
         *                   exception.
         */
        protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
            HttpServletRequest request, HttpServletResponse response)
            throws Exception {
            String message =

File
Line
org\\apache\\struts\\actions\\EventActionDispatcher.java
[157](./xref/org/apache/struts/actions/EventActionDispatcher.html.md#157)
org\\apache\\struts\\actions\\EventDispatchAction.java
[116](./xref/org/apache/struts/actions/EventDispatchAction.html.md#116)
            throw new ServletException(message);
        }

        /**
         * Returns the method name, given a parameter's value.
         *
         * @param mapping   The ActionMapping used to select this instance
         * @param form      The optional ActionForm bean for this request (if
         *                  any)
         * @param request   The HTTP request we are processing
         * @param response  The HTTP response we are creating
         * @param parameter The <code>ActionMapping</code> parameter's name
         * @return The method's name.
         * @throws Exception if an error occurs.
         */
        protected String getMethodName(ActionMapping mapping, ActionForm form,
                HttpServletRequest request, HttpServletResponse response,
                String parameter) throws Exception {

            StringTokenizer st = new StringTokenizer(parameter, ",");
            String defaultMethodName = null;

            while (st.hasMoreTokens()) {
                String methodKey = st.nextToken().trim();
                String methodName = methodKey;

                // The key can either be a direct method name or an alias
                // to a method as indicated by a "key=value" signature
                int equals = methodKey.indexOf('=');
                if (equals > -1) {
                    methodName = methodKey.substring(equals + 1).trim();
                    methodKey = methodKey.substring(0, equals).trim();
                }

                // Set the default if it passes by
                if (methodKey.equals(DEFAULT_METHOD_KEY)) {
                    defaultMethodName = methodName;
                }

                // If the method key exists as a standalone parameter or with
                // the image suffixes (.x/.y), the method name has been found.
                if ((request.getParameter(methodKey) != null)
                      || (request.getParameter(methodKey + ".x") != null)) {
                    return methodName;
                }
            }

            return defaultMethodName;
        }
    }

File
Line
org\\apache\\struts\\actions\\ActionDispatcher.java
[362](./xref/org/apache/struts/actions/ActionDispatcher.html.md#362)
org\\apache\\struts\\actions\\DispatchAction.java
[269](./xref/org/apache/struts/actions/DispatchAction.html.md#269)
                forward = (ActionForward) method.invoke(this, args);
            } catch (ClassCastException e) {
                String message =
                    messages.getMessage("dispatch.return", mapping.getPath(), name);

                log.error(message, e);
                throw e;
            } catch (IllegalAccessException e) {
                String message =
                    messages.getMessage("dispatch.error", mapping.getPath(), name);

                log.error(message, e);
                throw e;
            } catch (InvocationTargetException e) {
                // Rethrow the target exception if possible so that the
                // exception handling machinery can deal with it
                Throwable t = e.getTargetException();

                if (t instanceof Exception) {
                    throw ((Exception) t);
                } else {
                    String message =
                        messages.getMessage("dispatch.error", mapping.getPath(),
                            name);

                    log.error(message, e);
                    throw new ServletException(t);
                }
            }

            // Return the returned ActionForward instance
            return (forward);
        }

        /**
         * <p>Returns the parameter value.</p>
         *
         * @param mapping  The ActionMapping used to select this instance
         * @param form     The optional ActionForm bean for this request (if any)
         * @param request  The HTTP request we are processing
         * @param response The HTTP response we are creating
         * @return The <code>ActionMapping</code> parameter's value
         * @throws Exception if the parameter is missing.
         */
        protected String getParameter(ActionMapping mapping, ActionForm form,

File
Line
org\\apache\\struts\\actions\\ActionDispatcher.java
[293](./xref/org/apache/struts/actions/ActionDispatcher.html.md#293)
org\\apache\\struts\\actions\\DispatchAction.java
[220](./xref/org/apache/struts/actions/DispatchAction.html.md#220)
        }

        // ----------------------------------------------------- Protected Methods

        /**
         * Dispatch to the specified method.
         *
         * @param mapping  The ActionMapping used to select this instance
         * @param form     The optional ActionForm bean for this request (if any)
         * @param request  The non-HTTP request we are processing
         * @param response The non-HTTP response we are creating
         * @param name     The name of the method to invoke
         * @return The forward to which control should be transferred, or
         *         <code>null</code> if the response has been completed.
         * @throws Exception if the application business logic throws an
         *                   exception.
         * @since Struts 1.1
         */
        protected ActionForward dispatchMethod(ActionMapping mapping,
            ActionForm form, HttpServletRequest request,
            HttpServletResponse response, String name)
            throws Exception {
            // Make sure we have a valid method name to call.
            // This may be null if the user hacks the query string.
            if (name == null) {
                return this.unspecified(mapping, form, request, response);
            }

            // Identify the method object to be dispatched to
            Method method = null;

            try {
                method = getMethod(name);
            } catch (NoSuchMethodException e) {
                String message =
                    messages.getMessage("dispatch.method", mapping.getPath(), name);

                log.error(message, e);

                String userMsg =
                    messages.getMessage("dispatch.method.user", mapping.getPath());
                throw new NoSuchMethodException(userMsg);
            }


