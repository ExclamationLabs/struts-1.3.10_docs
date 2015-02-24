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

> *"Would you tell me, please, which way I ought to go from here?"*
>
> *"That depends a good deal on where you want to get to."*
>
> *"I don't much care where"*
>
> *"Then it doesn't much matter which way you go."*
>
> *"so long as I get somewhere."*
>
> *"Oh, you're sure to do that, if only you walk long enough."*

### <span id="Prerequisite_Software"></span>Prerequisite Software

The framework's binary distribution needs three other software packages installed to operate. You may already have these installed on your system. To build the framework from source you may need to acquire and install several others. The complete list is as follows:

-   **Java Development Kit** - You **must** download and install a Java Development Kit (version 1.4 or later) implementation for your operating system platform. A good starting point for locating Java Development Kit distributions is [http://java.sun.com/j2se.](http://java.sun.com/j2se) To build the framework, Java 1.4.2 (the latest production JDK) is suggested and required if you use our Maven build system.
-   **Servlet Container** - You **must** download and install a servlet container that is compatible with the Servlet API Specification, version 2.3 or later, and the JavaServer Pages (JSP) Specification, version 1.2 or later. One popular choice is to download Apache's [Tomcat](http://jakarta.apache.org/tomcat/) , but any compliant container should work well with the framework.
-   **Maven Build System** - (optional) If you are building the framework from the source distribution, you must download and install the [Apache Maven 2](http://maven.apache.org/) build system (2.0.4 or later).

### <span id="Install_a_Library_Distribution"></span>Install a Library Distribution

First, download a binary distribution of Struts by following the instructions [here,](http://struts.apache.org/downloads.html.md) Then, make sure you have downloaded and installed the [prerequisite](#Prerequisites) software packages described above.

Unpack the Library distribution into a convenient directory. (If you are [building from the source distribution,](http://struts.apache.org/downloads.html.md#Building) the result of the build will already be an unpacked binary distribution for you). The distribution consists of the following contents:

-   **lib/\*.jar** - The struts-\*.jars contains Java classes distributed by Apache Struts. The other JAR files contain packages from other projects that are imported by the framework. When you launch a your application, these JARs need to be available to your application, usually by copying them to the application's `WEB-INF/lib` directory.
     *WARNING* - If you are going to be hosting multiple applications on the same servlet container, you will be tempted to place the `struts-core.jar` file into the shared repository supported by your container. Be advised that this may cause ClassNotFoundException problems unless *all* of your application classes are stored in the shared repository.

To use Struts Library in your own application, you will need to follow these steps:

-   Copy the `lib/*.jar` files from the Library distribution into the `WEB-INF/lib` directory of your web application.
-   Modify the `WEB-INF/web.xml` file for your web application to include a `<servlet>` element to define the controller servlet, and a `<servlet-mapping>` element to establish which request URIs are mapped to this servlet. Use the `WEB-INF/web.xml` file from the Struts Mailreader application for a detailed example of the required syntax.
-   Create a file `WEB-INF/struts-config.xml` that defines the action mappings and other characteristics of your specific application. You can use the `struts-config.xml` file from the Struts Blank application for examples of the required syntax.
-   At the top of each JSP page that will use JSP tags, add line(s) declaring the JSP tag libraries used on this particular page, like this:

<!-- -->

                        <%@ taglib uri="http://struts.apache.org/tags-bean" prefix="bean" %>
                        <%@ taglib uri="http://struts.apache.org/tags.html.md" prefix="html" %>
                        <%@ taglib uri="http://struts.apache.org/tags-logic" prefix="logic" %>
                    

-   When compiling the Java classes that comprise your application, be sure to include the JAR files (copied earlier) on the CLASSPATH that is submitted to the compiler.

### <span id="Installing_The_Framework_With_Your_Servlet_Container"></span>Installing The Framework With Your Servlet Container

For most containers, you need only to:

-   Copy the WAR files in your `/webapps` directory to your containers `webapps` directory.
-   In some cases, you may need to restart your container if it is running.

#### Running Applications Under A Security Manager

Many application servers execute web applications under the control of a Java security manager, with restricted permissions on what classes in the web application can do. If you utilize form beans with mapped properties, you may encounter security exceptions unless you add the following permission to the set of permissions granted to your application's codebase:

                        permission java.lang.RuntimePermission
                        "accessDeclaredMembers";
                    

Consult the documentation on your application server for more information about how to configure additional security manager permissions.

#### Installing on Various Containers

-   Bluestone Universal Business Server 7.2 - [Additional steps required.](installation-ubs72.html.md)
-   Borland Application Server 4.5 -No additional steps required.
-   iPlanet Application Server - Service Pack 2 is recommended. Note that the database object in the Struts MailReader application is not compatible with this container.
-   iPlanet Web Server - [Additional steps required.](installation-ip.html.md)
-   iPortal Application Server - [Additional steps required.](installation-ipas.html.md)
-   Jetty - [Additional steps required.](installation-jetty.html.md)
-   JRun - [Additional steps required.](installation-jr30.html.md)
-   Novell ExteNd Application Server 4.0+ - [Additional steps required.](installation-novell.html.md)
-   Orion Application Server - [Additional steps required.](installation-oas.html.md)
-   Resin 1.2+ "standalone" - No additional steps required.
-   RexIP - No additional steps required.
-   SilverStream 3.7.1 and later - [Additional steps required.](installation-sas.html.md)
-   Tomcat 3.1 and prior - Not recommended. Use Tomcat 3.2.1 or later.
-   Tomcat 3.2.1 with Apache - [Additional steps required.](installation-tc.html.md)
-   Tomcat 3.2.1+ "standalone" - No additional steps required.
-   Tomcat 4.0 - No additional steps required.
-   Trifork Enterprise Application Server 3.3.x - No additional steps required.
-   Weblogic 5.1 sp8 - [Additional steps required.](installation-wls5.html.md)
-   WebLogic 6.0+ - No additional steps required.
-   WebSphere - [Additional steps required.](installation-was352.html.md)
-   WebSphere - [Steps for the Example Application.](installation-was352-x.html.md)

Next: [FAQs and HowTos](../faqs/index.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


