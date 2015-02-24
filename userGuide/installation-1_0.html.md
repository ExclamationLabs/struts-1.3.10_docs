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

<span id="Prerequisite_Software"></span>Prerequisite Software
-------------------------------------------------------------

The Struts binary distribution needs three other software packages installed to operate. You may already have these installed on your system. To build Struts from source you may need to acquire and install several others. The complete list is as follows:

-   **Java Development Kit** - You **must** download and install a Java2 (version 1.2 or later) Java Development Kit implementation for your operating system platform. A good starting point for locating Java Development Kit distributions is <http://java.sun.com/j2se> .
-   **Servlet Container** - You **must** download and install a servlet container that is compatible with the Servlet API Specification, version 2.2 or later, and the JavaServer Pages (JSP) Specification, version 1.1 or later. One popular choice is to download Apache's [Tomcat](http://jakarta.apache.org/tomcat) (version 3.1 or later required, version 3.2 or later recommended).
-   **XML Parser** - Struts **requires** the presence of an XML parser that is compatible with the Java API for XML Parsing (JAXP) specification, 1.0 or later. You can download and install the JAXP [reference implementation](http://java.sun.com/xml) , which is required for building the Struts source distribution. In Struts-based web applications, you may replace the reference implementation classes with any other JAXP compliant parser, such as [Xerces](http://xml.apache.org/xerces-j) . See detailed instructions related to the parser in the instructions for [building](#Building) and [installing](#Installing) Struts, below.
-   **Ant Build System** - If you are building Struts from the source distribution, you must download and install version 1.3 or later of the [Ant](http://jakarta.apache.org/ant) build system. This package is also strongly recommended for use in developing your own web applications based on Struts.
    -   If you are using the release version of Ant version 1.3, you will also need to download the "optional.jar" file that contains the implementation of Ant's `<style>` command.
    -   Make sure that the "ant" and "ant.bat" scripts are executable, by adding the $ANT\_HOME/bin directory to your PATH environment variable.
-   **JDBC 2.0 Optional Package Classes** - Struts supports an optional implementation of `javax.sql.DataSource` , so it requires the API classes to be compiled. They can be downloaded from <http://java.sun.com/products/jdbc/download.html.md> .
-   **Xalan XSLT Processor** - If you are building Struts from the source distribution, you must download and install version 1.2 (problems have been reported with current versions of Xalan 2.0) of the [Xalan](http://xml.apache.org/xalan) XSLT processor (which also includes the Xerces XML parser), or use the version of Xalan included in the JAXP 1.1 release. This processor is used to convert the Struts documentation from its internal XML-based format into the HTML that is presented in the Struts documentation application.

<span id="Install_A_Struts_Binary_Distribution"></span>Install A Struts Binary Distribution
-------------------------------------------------------------------------------------------

First, download a binary distribution of Struts by following the instructions [here](../acquiring.html.md) . Then, make sure you have downloaded and installed the [prerequisite](#Prerequisites) software packages described above.

Unpack the Struts binary distribution into a convenient directory. (If you [build Struts from the source distribution](#Building) , the result of the build will already be an unpacked binary distribution for you). The distribution consists of the following contents:

-   **lib/struts.jar** - This JAR file contains all of the Java classes included in Struts. It should be copied into the `WEB-INF/lib` directory of your web application. *WARNING* - If you are going to be hosting multiple Struts based applications on the same servlet container, you will be tempted to place the `struts.jar` file into the shared repository supported by your container. Be advised that this will like cause you to encounter ClassNotFoundException problems unless *all* of your application classes are stored in the shared repository.
-   **lib/struts\*.tld** - These are the "tag library descriptor" files that describe the custom tags in the various Struts tag libraries. They should be copied into the `WEB-INF` directory of your web application.
-   **webapps/struts-blank.war** - This is a simple "web application archive" file containing a basic starting point for building your own Struts-based applications.
-   **webapps/struts-documentation.war** - This is a "web application archive" file containing all of the Struts documentation found on the [Struts web site](http://jakarta.apache.org/struts) (including these pages). You can install this web application on any servlet container compatible with Servlet API 2.2 or later.
-   **webapps/struts-example.war** - This is an example web application that uses a large percentage of Struts features. You can install this web application on any servlet container compatible with the Servlet 2.2 (or later) and JSP 1.1 (or later) specifications. If an XML parser is not made available to web applications by your container, you will need to add one to the WEB-INF/lib directory of this web application.
-   **webapps/struts-exercise-taglib.war** - This web application contains test pages for the various custom tags supported by Struts. It is primarily of use to developers who are enhancing the Struts custom tag libraries, but may also be useful as simple examples of the usage of various Struts tags.
-   **webapps/struts-template.war** - This web application both introduces and demonstrates the Struts template tags.
-   **webapps/struts-upload.war** - This web application is a quick example of uploading files using the Struts framework.

To use Struts in your own application, you will need to follow these steps:

-   Copy the file `lib/struts.jar` from the Struts distribution into the `WEB-INF/lib` directory of your web application.
-   Copy the all of the files that match `lib/struts*.tld` from the Struts distribution into the `WEB-INF` directory of your web application.
-   Modify the `WEB-INF/web.xml` file for your web application to include a `<servlet>` element to define the controller servlet, and a `<servlet-mapping>` element to establish which request URIs are mapped to this servlet. Use the `WEB-INF/web.xml` file from the Struts example application for a detailed example of the required syntax.
-   Modify the `WEB-INF/web.xml` file of your web application to include the following tag library declarations:

<!-- -->

    <taglib>
                    <taglib-uri>/WEB-INF/struts-bean.tld</taglib-uri>
                    <taglib-location>/WEB-INF/struts-bean.tld</taglib-location>
                    </taglib>

                    <taglib>
                    <taglib-uri>/WEB-INF/struts.html.md.tld</taglib-uri>
                    <taglib-location>/WEB-INF/struts.html.md.tld</taglib-location>
                    </taglib>

                    <taglib>
                    <taglib-uri>/WEB-INF/struts-logic.tld</taglib-uri>
                    <taglib-location>/WEB-INF/struts-logic.tld</taglib-location>
                    </taglib>

                    <taglib>
                    <taglib-uri>/WEB-INF/struts-template.tld</taglib-uri>
                    <taglib-location>/WEB-INF/struts-template.tld</taglib-location>
                    </taglib>
                

-   Create a file `WEB-INF/struts-config.xml` that defines the action mappings and other characteristics of your specific application. You can use the `struts-config.xml` file from the Struts example application for a detailed example of the required syntax.
-   At the top of each JSP page that will use the Struts custom tags, add line(s) declaring the Struts custom tag libraries used on this particular page, like this:

<!-- -->

    <%@ taglib uri="/WEB-INF/struts-bean.tld" prefix="bean" %>
                    <%@ taglib uri="/WEB-INF/struts.html.md.tld" prefix="html" %>
                    <%@ taglib uri="/WEB-INF/struts-logic.tld" prefix="logic" %>
                    <%@ taglib uri="/WEB-INF/struts-template.tld"
                    prefix="template" %>
                

-   When compiling the Java classes that comprise your application, be sure to include the `struts.jar` file (copied earlier) on the CLASSPATH that is submitted to the compiler.

<span id="Installing_Struts_with_your_servlet_container"></span>Installing Struts with your servlet container
-------------------------------------------------------------------------------------------------------------

**WARNING** - Do **NOT** add `struts.jar` to the classpath of your servlet container in an attempt to avoid placing it in the `/WEB-INF/lib` directory of each individual web app! Doing so will cause problems with `ClassNotFoundException` exceptions.

For most containers, you need only to:

-   Copy the WAR files in your Struts `/webapp` directory to your containers `webapps` directory.
-   In some cases, you may need to restart your container if it is running.

#### Status of various containers

-   Bluestone Universal Business Server - [Additional steps required.](installation-ubs72.html.md)
-   Borland Application Server 4.5 -No additional steps required.
-   iPlanet Application Server - Service Pack 2 is recommended. Note that the database object in the Struts-Example application is not compatible with this container.
-   iPlanet Web Server - [Additional steps required.](installation-ip.html.md)
-   iPortal Application Server - [Additional steps required.](installation-ipas.html.md)
-   Jetty - [Additional steps required.](installation-jetty.html.md)
-   JRun - [Additional steps required.](installation-jr30.html.md)
-   Orion Application Server - [Additional steps required.](installation-oas.html.md)
-   Resin 1.2+ "standalone" - No additional steps required.
-   SilverStream 3.7.1 and later - [Additional steps required.](installation-sas.html.md)
-   Tomcat 3.1 and prior - Not recommended. Use Tomcat 3.2.1 or later.
-   Tomcat 3.2.1 with Apache - [Additional steps required.](installation-tc.html.md)
-   Tomcat 3.2.1+ "standalone" - No additional steps required.
-   Tomcat 4.0 - No additional steps required.
-   Weblogic - [Additional steps required.](installation-wls5.html.md)
-   WebLogic 6.0+ - No additional steps required.
-   WebSphere - [Additional steps required.](installation-was352.html.md)
-   WebSphere - [Steps for the Example Application.](installation-was352-x.html.md)

<span id="Building_Struts_From_Source"></span>Building Struts From Source
-------------------------------------------------------------------------

First, download a source distribution of Struts by following the instructions [here](../acquiring.html.md) . Then, make sure you have downloaded and installed **all** of the [prerequisite](#Prerequisites) software packages described above.

To build Struts, you will need to customize the build process to the details of your development environment as follows:

-   The Struts source distribution uses a file named `build.properties` (in the top-level directory of the distribution) to identify the location of external components that Struts depends on.
-   There is no `build.properties` file included with the source distribution. However, there is an example file named `build.properties.example` that you can copy to `build.properties` and then customize.
-   The properties you must configure in `build.properties` are:
    -   **catalina.home** - Pathname to the directory of your binary distribution of Tomcat 4.0 (required only if you wish to use the `deploy.catalina` target).
    -   **servletapi.home** - Pathname to the directory of your binary distribution of the Servlet API classes.
    -   **tomcat.home** - Pathname to the directory of your binary distribution of Tomcat 3.2 (required only if you wish to use the `deploy.tomcat` target).
    -   **xerces.home** - Pathname to the directory of your binary distribution of the Xerces parser, version 1.2 or 1.3 (required only if you wish to use the `deploy.catalina` target).
-   If you are a Struts developer with write access to the CVS repository, be sure that you do **NOT** check in a copy of the `build.properties` file, since it will be different for each individual developer.

To build a "distribution" version of Struts, first change your current directory to the directory in which you have unpacked the Struts source distribution, and (if necessary) create or customize the `build.properties` file as described above. Then, type:

                    ant dist
                

This command will create a binary distribution of Struts, in a directory named `dist` (relative to where you are compiling from). This directory contains an exact replica of the files included in a binary distribution of Struts, as described in the [preceding section](#Installing) .

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


