<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](../images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](../2.x/) | [Struts 1](../1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](../index.html.md)
-   [Learning](../learning.html.md)
-   [Roadmap](../roadmap.html.md)
-   [Releases](../downloads.html.md)

##### Documentation

-   [User Guide](../userGuide/index.html.md)
-   [FAQs and HOWTOs](../faqs/index.html.md)
-   [Release Notes](../userGuide/release-notes.html.md)
-   [Javadoc](../apidocs/index.html.md)
-   [DTDDoc](../dtddoc/index.html.md)

##### Support

-   [User Mailing List](../mail.html.md)
-   [Issue Tracker (JIRA)](http://issues.apache.org/struts/)
-   [Wiki Pages](http://wiki.apache.org/struts/)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Project Documentation

-   [Project Information](../project-info.html.md)
-   [Project Reports](../project-reports.html.md)

[![Built by Maven](../images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="How_does_Struts_work"></span>How does Struts work?
------------------------------------------------------------

> [From the [Kickstart FAQ](kickstart.html.md#how)]
>  *"Java Servlets are designed to handle requests made by Web browsers. Server pages are designed to create dynamic Web pages that can turn billboard sites into interactive applications. Struts uses a special Servlet as a switchboard to route requests from Web browsers to the appropriate server page. This makes Web applications much easier to design, create, and maintain."*

That's a good high-level description, but let's describe the mechanisms and dependencies of the framework in more detail.

-   The web application that you develop has a deployment descriptor `(WEB-INF/web.xml)` which you must write. This file describes the configuration of your web application, including welcome pages (the file that is shown in a directory when none is specified by the request), mappings to servlets (path or extension name), and parameters to those servlets.

    In the `web.xml` file, you configure the framework [`ActionServlet`](../apidocs/org/apache/struts/action/ActionServlet.html.md) as the servlet that will handle all requests for a given mapping (usually the extension `.do` is used). The ActionServlet is the "switchboard" mentioned in the opening paragraph.

    Also in the `web.xml,` you configure the `ActionServlet` to use one or more configuration files for Struts itself.

    For now, let's say we are installing the web application on the server using `/myapp` as a location, and we are using the simplest possible configuration from there.

    If you need more details on deployment descriptors, read the relevant Servlet Specification available from Sun Microsystem's [Java site.](http://java.sun.com)

-   In the framework configuration file(s), you associate paths with the controller components of your application, known as [`Action`](../apidocs/org/apache/struts/action/Action.html.md) classes (i.e. "login" ==\> LoginAction class). This tells the `ActionServlet` that for the incoming request `http://myhost/myapp/login.do` it should invoke your controller component, `LoginAction.`

    Note the extension `.do` in this URL. The extension causes your container (i.e. Tomcat) to call the `ActionServlet,` which sees the word "login" as the thing you want to do. The configuration is referenced, and your `LoginAction` is executed.

-   For each `Action,` you also configure the framework with the names of the resulting page(s) that can be shown as a result of that action. There can be more than one view as the result of an action (often, there are at least two: one for "success", and one for "failure").

    Your `Action` (the controller component you write) is based on these *logical* result mapping names. It reports back to the `ActionServlet` using words like "success", "failure", "ready", "ok", "UserError", et cetera. The framework (through the configuration that you wrote) knows how to forward to the proper *specific* page. This has the added advantage of reconfiguration of the view layer by simply editing the XML configuration file.

    At this point, the framework knows how to delegate to your controller components, and what to show as a result of your controller processing. The "model" part of the application is completely up to you, and is called from within your controller components.

-   You may also associate a JavaBean with an action (or set of actions) in the framework's configuration file. The JavaBean is used as a repository for form or display data that can be communicated between the view and controller layer.

    These Beans are automatically made visible to your controller components (like the `LoginAction` class) and any view page that is associated with that controller.

    These Beans can also be validated with the help of the framework to help insure that the user is putting good data in the form. They can be carried along with a session, allowing forms to span multiple pages of the view, and Actions in the controller.

    **Note:** You must be using some sort of server-side technology (JSP, Velocity, XSLT) for the view layer (going *to* the client) to see this data (plain HTML won't work). The framework works on the server side, so the client's view has to be composed there.

    The client feeds the data back through normal form submission (POST/GET) methods, and the framework updates that data in the Bean before calling your controller components.

-   Within your web application will be pages that represent the view your users will see. These can be JSP pages, Velocity Templates, XSLT pages, and so forth. Sets of JSP and JSTL tags are available for the framework so that you can get started right away, but any standard presentation technology can be used with the framework.

    Even plain HTML files can be used within your application, although they will not take full advantage of all of the dynamic features.

    Following the example of the Struts JSP taglibs, several other packages are available to make the framework easy to use with your favorite presentation technology. For Velocity templates, there are the [Velocity](http://jakarta.apache.org/velocity/) ViewTools for Struts. If you want to use XSLT in you application, you can choose between [stxx](http://www.openroad.ca/opencode/) and [StrutsCX.](http://it.cappuccinonet.com/strutscx/)

    These packages make the standard Struts framework elements look and feel like a seamless part of the original presentation technology. Struts also makes it easy to mix and match. If need be, you can use JSP, Velocity templates, and XSLT all in the same application!

    Since Struts relies on standard Servlet technologies, you should be able to use any Java presentation technology with Struts.

-   While the focus of the Struts framework is on the controller, the presentation layer is a significant part of any application. The Struts JSP taglibs include a number of generic and Struts-specific tags to help you use dynamic data in your view.

    The custom JSP tags account for a good deal of the Struts code base. It is educational to note that as of version 1.1b3 the Java code for the core of Struts was about 28,000 lines, and the Java code for the tag libraries (including tiles) was about 41,000 lines.

    These tags help you glue your view layer to the controller layer without having to embed a lot of Java in the JSP. This gives the page an XML look, and can be easier for web designers to deal with than a plain JSP. It also helps minimize dependencies between the controller and view.

    The custom tags are used to create forms (and invisibly interact with the Bean mentioned previously), logically forward to other pages, and invoke other actions of the web application.

    There are also tags that help you with internationalization, error messages, etc.

    All of these abilities depend in some way on the configuration files you supplied to Struts.

It is important for you to remember that the mechanism described here is only in effect when the `ActionServlet` is handling the request.

Since this only happens when a request is submitted that causes your container (i.e. Tomcat, WebSphere, whatever) to call `ActionServlet` , you must be sure that any page that relies on Struts is done through a request that will map to the `ActionServlet` (i.e. it has a `.do` extension).

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


