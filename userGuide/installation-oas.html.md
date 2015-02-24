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

#### Orion Application Server

In the steps below, `$ORION_HOME` refers to the directory in which you have installed Orion, and `$STRUTS_HOME` is the directory in which you unpacked the Struts binary distribution.

-   Modify the file `$ORION_HOME/config/application.xml` to define the two new applications, by adding the following declarations, immediately following the `web-module` directive for the default web application:

<!-- -->

    <web-module id="strutsDoc"
                        path="$STRUTS_HOME/webapps/struts-documentation.war"/>
                        <web-module id="strutsExample"
                        path="$STRUTS_HOME/webapps/struts-example.war"/>
                    

-   Modify the file `$ORION_HOME/config/default-web-site.xml` (or the configuration file for any other Orion website) to include the following declarations, after the declaration for the \<default-web-app\> if any:

<!-- -->

    <web-app application="default" name="strutsDoc"
                        root="/struts-documentation"/>
                        <web-app application="default" name="strutsExample"
                        root="/struts-example"/>
                    

-   After you start Orion, you should now be able to access these applications (assuming you haven't changed the port number from the default of 80) at:

<!-- -->

    http://localhost/struts-documentation
                        http://localhost/struts-example
                    

-   Versions of Orion up to at least 1.0.3 have a bug related to ServletContext.getResource() calls that prevent the Struts example application from working out of the box. This manifests itself as a JSP error when you try to access the example application, with the following message:
     `javax.servlet.jsp.JspException: Missing resources attributeorg.apache.struts.action.MESSAGE`
     followed by an error traceback. There will also be an initialization error message in the `ORION_HOME/log/global-application.log` log file. To work around this problem, you can take the following steps:
    -   Go to the `$STRUTS_HOME/webapps` directory, where you will note that Orion has automatically expanded each web application into an unpacked directory structure.
    -   Go to the `$STRUTS_HOME/webapps/struts-example/WEB-INF` directory, and copy the file `struts-config.xml` one directory up (that is, into `$STRUTS_HOME/webapps/struts-example` .
    -   Modify the `$STRUTS_HOME/webapps/struts-example/WEB-INF/web.xm` file, changing the value of the "config" initialization parameter (for the action servlet) from `/WEB-INF/struts-config.xml` to `/action.xml` .
    -   Restart Orion, and you should be able to access the example application.
    -   Note that this workaround has a negative security-related side effect: your `struts-conifig.xml` file can now be retrieved by remote clients at the following URL:
         `http://localhost/struts-example/struts-config.xml`
         Therefore, you should be sure you do not store sensitive information (such as database passwords) in this file.

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


