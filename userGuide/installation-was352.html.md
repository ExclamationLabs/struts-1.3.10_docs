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

<span id="a6.2_Installation"></span>6.2 Installation
----------------------------------------------------

### <span id="Installing_Struts_with_your_servlet_container"></span>Installing Struts with your servlet container

#### WebSphere Application Server 3.5 FixPack 2

-   In the steps below, `$WAS_HOME` refers to the directory in which you have installed WebSphere Application Server, and `$STRUTS_HOME` is the directory in which you unpacked the Struts binary distribution.
-   WebSphere before 3.5.2 did not support JSP 1.1 and Servlet 2.2, which made it difficult to get Struts functioning without massive code changes. Please upgrade to 3.5.2 (3.5 with FixPack 2) before attempting to use Struts. See <http://www.ibm.com/software/webservers/appserv/efix.html.md> for download and install instructions on FixPack 2 for WebSphere 3.5
-   Warning: Struts will not work with WebSphere 3.5.2 out of the box. Fixes expected to be in WebSphere 3.5.3 (not released at time of writing) should correct this. However, you can successfully get WebSphere 3.5.2 working with Struts.
-   Make sure the WebSphere Application Server is started. Under Windows NT/2000, it's the "IBM WS AdminServer" service.
-   Start the WebSphere Administrative Console.
-   Once it's started, select "Convert a War File" from the tasks toolbar option, or from the Console-\>Tasks menu. This will cause a "Convert War File" Wizard dialog to appear.
-   Select a Servlet Engine to host the web application that will result from converting the War file, e.g. "Default Servlet Engine", by expanding the tree control under Nodes. Press the Next button.
-   Select a Virtual Host to associate the resulting web application with, e.g. "default host". Press the Next button.
-   Press the Browse button and choose the `$STRUTS_HOME/webapps/struts-example.war` . Press the Next button
-   Select a destination directory for the resulting web application, e.g. `$WAS_HOME/hosts/default_host` . Press the Next button
-   Enter a "Web Application Web Path", e.g. struts-example, and a "Web Application Name", e.g. struts-example. Press the Finish button.
-   You should, after a lengthy pause, get a message box with the text Command "convert war file" completed successfully. Press Ok.
-   You now need to add jaxp.jar and a jaxp compatible parser, e.g. parser.jar from JAXP 1.0.1 to the struts-example web application's servlets directory, e.g. `$WAS_HOME/AppServer/hosts/default_host/struts-example/servlets`
-   At this point, if WAS 3.5.2 correctly implemented Servlet 2.2, all would be fine. However, WAS 3.5.2 returns null for calls to `ServletContext.getResource(String)` or `ServletContext.getResourceAsStream(String)` . This manifests itself as an exception in the application server stdout log, e.g. `default_server_stdout.log.`
-   Warning: Don't be fooled by the fact that the web application starts successfully from the Admin Console. It actually doesn't. The Admin Console is lying. If you try to access the webapp e.g. `http://localhost/struts-example/` it will fail.
-   At this point, you need to patch the Struts source. There are three places `getResourceAsStream` is called:

<!-- -->

                        ResourceTag.doStartTag()
                        ActionServlet.initMapping()
                        PropertyMessageResources.loadLocale(String)
                    

of these, `ActionServlet` is the most important.

-   Change the source from

<!-- -->

                        // Acquire an input stream to our configuration resource
                        InputStream input =
                        getServletContext().getResourceAsStream(config);
                    

to

                        // Acquire an input stream to our configuration resource
                        InputStream input = new
                        java.io.FileInputStream(getServletContext().getRealPath(config));
                    

-   Make similar changes to the other classes if necessary.
-   Recompile ActionServlet and copy the `.class` file to
     `$WAS_HOME/AppServer/hosts/default_host/struts-example/servlets/ org/apache/struts/action/ActionServlet.class`
-   Another bug with WAS 3.5.2's classloaders is that Class.getResource() wont load a resource from a jar, so you must copy
     `$STRUTS_HOME/lib/struts-config_1_0.dtd`
     to
     `$WAS_HOME/AppServer/hosts/default_host/struts-example/servlets/org/apache/struts/resources/struts-config_1_0.dtd`
     or be connected to the Internet to fetch the dtd from the Jakarta website.
-   Start your webapp in the Admin Console
-   Test the example application by loading the following URL in your browser of choice: [http://localhost/struts-example/" \>http://localhost/struts-example/](http://localhost/struts-example/)

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


