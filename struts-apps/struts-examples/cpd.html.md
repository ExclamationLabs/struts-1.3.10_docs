<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](../../images/struts.gif)](../../)</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](../2.x/) | [Struts 1](../1.x/) | [Apache](http://www.apache.org) | [Struts 1](../../1.x/) | [Struts 2](../../2.x/)

------------------------------------------------------------------------

##### Struts Apps

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

-   [Apache Struts Home](../../)
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
org\\apache\\struts\\webapp\\dispatch\\ActionDispatcherExample.java
[42](./xref/org/apache/struts/webapp/dispatch/ActionDispatcherExample.html.md#42)
org\\apache\\struts\\webapp\\dispatch\\EventActionDispatcherExample.java
[42](./xref/org/apache/struts/webapp/dispatch/EventActionDispatcherExample.html.md#42)
                                     = new EventActionDispatcher(this);

        private int fooCount;
        private int barCount;

        /**
         * Execute method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward execute(ActionMapping mapping,
                                     ActionForm form,
                                     HttpServletRequest request,
                                     HttpServletResponse response)
            throws Exception {

            return dispatcher.execute(mapping, form, request, response);

        }

        /**
         * Example "foo" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doFoo(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {

            fooCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

        /**
         * Example "bar" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doBar(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {
            barCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

    }

File
Line
org\\apache\\struts\\webapp\\dispatch\\DispatchExampleAction.java
[37](./xref/org/apache/struts/webapp/dispatch/DispatchExampleAction.html.md#37)
org\\apache\\struts\\webapp\\dispatch\\EventDispatchActionExample.java
[37](./xref/org/apache/struts/webapp/dispatch/EventDispatchActionExample.html.md#37)
    public class MappingDispatchExampleAction extends MappingDispatchAction {

        private int fooCount;
        private int barCount;

        /**
         * Example "foo" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doFoo(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {

            fooCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

        /**
         * Example "bar" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doBar(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {
            barCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

    }

File
Line
org\\apache\\struts\\webapp\\dispatch\\ActionDispatcherExample.java
[63](./xref/org/apache/struts/webapp/dispatch/ActionDispatcherExample.html.md#63)
org\\apache\\struts\\webapp\\dispatch\\LookupDispatchExampleAction.java
[50](./xref/org/apache/struts/webapp/dispatch/LookupDispatchExampleAction.html.md#50)
            keyMethodMap.put("button.bar.label", "doBar");
        }

        /**
         * Example "foo" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doFoo(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {

            fooCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

        /**
         * Example "bar" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doBar(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {
            barCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

File
Line
org\\apache\\struts\\webapp\\dispatch\\ActionDispatcherExample.java
[77](./xref/org/apache/struts/webapp/dispatch/ActionDispatcherExample.html.md#77)
org\\apache\\struts\\webapp\\dispatch\\MappingDispatchExampleAction.java
[52](./xref/org/apache/struts/webapp/dispatch/MappingDispatchExampleAction.html.md#52)
        public ActionForward doFoo(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {

            fooCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

        /**
         * Example "bar" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doBar(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {
            barCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

    }

File
Line
org\\apache\\struts\\webapp\\dispatch\\DispatchExampleAction.java
[52](./xref/org/apache/struts/webapp/dispatch/DispatchExampleAction.html.md#52)
org\\apache\\struts\\webapp\\dispatch\\LookupDispatchExampleAction.java
[63](./xref/org/apache/struts/webapp/dispatch/LookupDispatchExampleAction.html.md#63)
        public ActionForward doFoo(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {

            fooCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("foo", new ActionMessage("count.foo.message", fooCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }

        /**
         * Example "bar" method.
         *
         * @param mapping The ActionMapping used to select this instance
         * @param form The optional ActionForm bean for this request
         * @param request The servlet request we are processing
         * @param response The servlet response we are creating
         *
         * @exception Exception if business logic throws an exception
         */
        public ActionForward doBar(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
            throws Exception {
            barCount++;

            ActionMessages messages = new ActionMessages();
            messages.add("bar", new ActionMessage("count.bar.message", barCount+""));
            saveMessages(request, messages);

            return (mapping.findForward("success"));

        }


