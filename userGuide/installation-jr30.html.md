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

#### JRUN 3.0 SP2A, VERSION 3.02A.11614

**Tested with: Microsoft IIS 5.0, Windows 2000**
#### Important Note:

At the moment, JRun is not fully compliant with the JSP 1.1/1.2 specification.

Specifically, the automatic type conversions for custom tag parameters specified in "Issue 7" of the JSP 1.1 Errata and in the JSP 1.2 Proposed Final Draft have not yet been implemented.

As it stands, JSP pages that make use of Struts taglibs whose parameters require conversion (such as booleans) will not compile under JRun. This includes the Struts Example Application. Attempting to run the example application will result in an exception similar to the following being thrown:

                        /struts-example/index.jsp:

                        javax.servlet.ServletException: Compilation error
                        occurred:

                        allaire.jrun.scripting.DefaultCFE:

                        Errors reported by compiler:
                        c:/JRun/servers/default/Struts
                        Example/WEB-INF/jsp/jrun__index2ejspa.java:41:1:41:27:

                        Error: No match was found for method
                        "setLocale(java.lang.String)".
                    

(For more details see refer to:
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg01860.html.md> )

The following instructions describe how to install the Struts Example Application under JRun. A subsequent section describes how the Struts Example Application can be patched to work with Struts

The following instructions assume the following:

-   JRun has been installed and integrated with the web server of choice.
-   $APP\_SERVER\_NAME is the name of the application server used to host the application. (When JRun is first installed, it creates an application server called JRun Default Server).
-   $APP\_SERVER\_DIR is the directory used to hold applications hosted by $APP\_SERVER\_NAME. For the JRun Default Server, the directory is $JRUN\_HOME/servers/default where $JRUN\_HOME is the directory where JRun is installed.

#### Installing the struts example application

-   Login to the JRun Management Console.
-   On the left pane, select $APP\_SERVER\_NAME. A page showing the current server status will be shown on the right pane.
-   On the right pane, click on the WAR Deployment link. A page containing a list of the currently deployed web applications will be shown.
-   On the right pane, click on Deploy an Application. Complete the Web Application Information form as follows:
    -   Servlet War File or Directory: Enter the full path where struts-example.war is found or click on Browse to select the path.
    -   JRun Server Name: $APP\_SERVER\_NAME
    -   Application Name: Struts Example
    -   Application Hosts: All Hosts
    -   Application URL: /struts-example
    -   Application Deploy Directory: will default to $APP\_SERVER\_NAME/Struts Example (or the name as specified for Application Name).
-   Once the form is complete, click on the Deploy button.
-   If deployment is successful, restart the application server by clicking on `$APP_SERVER_NAME` on the left pane. A page showing the current server status will be shown on the right pane. Click the Restart Server button to restart the application server.
-   Test the sample application by using the following URL in the browser:
     `http://hostname/struts-example/index.jsp`
     The struts-documentation.war can be installed using the same procedure.

#### Installing unpacked web applications

The above steps should be followed for applications deployed as `*.war` files.

For unpacked web applications, configuration involves the following steps:

-   From the JRun Management Console, select `$APP_SERVER_NAME` (on the left pane) and click on WAR Deployment (on the right pane).
-   On the right pane, click on Create an Application and complete the Web Application Information form as follows:
-   JRun Server Name: $APP\_SERVER\_NAME
    -   Application Name: myApplication
    -   Application Hosts: All Hosts
    -   Application URL: /myApplication
    -   Application Deploy Directory: will default to
         `$APP_SERVER_NAME/myApplication`
-   Click on Create to submit the form.
-   Once the web application is created, install and configure the struts components (struts.jar, struts\*.tld, etc) for the web application under `$APP_SERVER_NAME/myApplication/WEB-INF`
-   Install the remaining components of the application: .class files, JSP pages,.properties files etc as required.
-   To configure the extension mapping of the request URI (ie \*.do) to the action servlet, expand `$APP_SERVER_NAME` on the left pane, expand the Web Applications branch and click on myApplication. The right pane will display the configuration options for myApplication. Click on Servlet URL Mappings. A list of existing mappings will be shown. Click the Edit button and create the following entry:
    -   Virtual Path/Extension: \*.do
    -   Servlet Invoked: action
-   Click on the Update button to save the changes.
-   Restart the application server.
-   The application should now be accessible from the browser.

The JRun application server will need to be restarted each time one of the following changes are made to the web application:

-   `.class` or `.jar` files are modified
-   `.properties` files are modified
-   `.xml` files are modified

#### Patching the struts example application

As mentioned at the beginning of these notes, the Struts Example Application will not run under JRun without modification. The following changes will need to be made:

-   index.jsp, logon.jsp: Change \.html.md:html locale="true"\> to
     \.html.md:html locale=\<%= true %\>\>
-   logon.jsp: Change \.html.md:html redisplay="true"\> to
     \.html.md:html redisplay=\<%= true %\>\>
-   registration.jsp, subscription.jsp: Change all instances of filter="true" to
     filter=\<%= true %\>

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


