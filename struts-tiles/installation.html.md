<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Tiles

-   [Welcome](index.html.md)
-   [FAQ](faq.html.md)
-   **Installation**
-   [User Guide](userGuide.html.md)
-   [Creating Templates](examples.html.md)
-   [Taglib Reference](tagreference.html.md)

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

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Quick_Install"></span>Quick Install
---------------------------------------------

-   Create a new web application based on the Struts Blank example.
-   Edit the struts-config and uncomment the section that refers to the "Tiles PlugIn".
-   Create one or more Tiles Definitions XML files in the /WEB-INF directory of the new application.
-   Deploy the new application.

<span id="Configuring_the_Plugin"></span>Configuring the Plugin
---------------------------------------------------------------

Here's how to use Tiles in your own application:

-   Ensure that a `struts-tiles.jar` is available in the `WEB-INF/lib` directory of your web application.
-   Add this `init-param` to the Action Servlet definition in web.xml:
            <init-param>
                <param-name>chainConfig</param-name>
                <param-value>org/apache/struts/tiles/chain-config.xml</param-value>
            </init-param>
            

-   Configure the Tiles Plugin to load your definitions.
            <plug-in className="org.apache.struts.tiles.TilesPlugin">
            <set-property
                property="definitions-config"
                   value="/WEB-INF/tiles-defs.xml"/>
            </plug-in>
            

-   At the top of each JSP page that will use the Tiles custom tags, add a line that declares the Tiles custom tag library.
            <%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>
            

<span id="Avoiding_ClassNotFoundExceptions"></span>Avoiding ClassNotFoundExceptions
-----------------------------------------------------------------------------------

**WARNING** - Do **NOT** add `tiles.jar` to the classpath of your servlet container in an attempt to avoid placing it in the `/WEB-INF/lib` directory of each individual web app! Doing so will cause problems with `ClassNotFoundException` exceptions.

For most containers, you need only to:

-   Copy the WAR files in your Tiles `/webapp` directory to your containers `webapps` directory.
-   In some cases, you may need to restart your container if it is running.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


