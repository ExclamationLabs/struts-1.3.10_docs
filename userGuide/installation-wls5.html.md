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

#### Weblogic 5.1 (service pack 8)

-   Obtain and install the Xerces XML parser (problems have been reported with the Sun reference implementation). Put xerces.jar in your WebLogic system path.
-   Obtain and unpack the Struts binary distribution (this procedure assumes it was extracted to `c:\jakarta-struts` ).
-   Add an entry to weblogic.properties for each of the Struts web applications that you would like to configure. For example, to make the struts-example application available, add the following line to weblogic.properties:
     `weblogic.httpd.webApp.strutsexample= c:/jakarta-struts/webapps/struts-example.war`
-   You do not need to include struts.jar or any of the application specific classes in the WebLogic classpath, since this will be done automatically (unless deploying an unpacked web archive- see below).
-   Start WebLogic server and point your web browser to the struts application. For example, to connect to the example application added in step 3:
     `http://localhost:7001/strutsexample`
-   This example application depends on the Struts specific resource file ApplicationResources.properties to be present on the classpath. However, WebLogic only extracts \*.class files from the archive so this file will not be found, resulting in an error the first time it is needed- something similar to: javax.servlet.ServletException: runtime failure in custom tag 'message'. Steps 6 & 7 will need to be performed for this application, and any other that relies on ApplicationResources.properties.
-   Extract ApplicationResources.properties from the \*.war file, and manually copy it to the respective package in the \_tmp\_war\_ directory WebLogic created for this application. Again referring to the struts-example application, this would be:
     `c:\jakarta-struts\webapps\WEB-INF\_tmp_war_strutsexample`
-   Restart WebLogic. You will now be able to run the application:
     `http://localhost:7001/strutsexample`

The above steps should be followed for applications deployed as \*.war files. For unpacked web applications, configuration involves adding both `struts.jar` and `/WEB-INF/classes` to the WebLogic classpath. For this reason, I would suggest deploying applications as war files to WebLogic. However, the same example application can be successfully deployed in extracted format by modifying weblogic.properties (assuming the war was extracted to directory webapps/struts-example):

`weblogic.httpd.webApp.strutsexample= c:/jakarta-struts/webapps/struts-example/`

And starting WebLogic with the updated WebLogic classpath. For example:

`c:\jdk1.3\bin\java -ms16m -mx64m -classpath c:\weblogic\lib\weblogic510sp8boot.jar;`

------------------------------------------------------------------------

#### Additional Recommendations

-   Servlet and JSP-Reloading should be turned off. First, you pay a performance penalty. Depending on the number of JSPs, the number of requests and the configured checking interval, the server will slow down. Second, with JSP- and Servlet reloading, one opens the door for various Weblogic classloader problems, that are difficult to diagnose, difficult to handle and often lead to lost HTTP-sessions.
-   Set the name of the `sessionid` to `JSESSIONID` , if cookies are used for session tracking and to jsessionid, if sessions are URL-based. (There are additional problems related to URL-based sessions, caused from BEA's way to encode the session id (J2EE-incompatible) as query-param. Especially \<bean:include\> will not work with URL-based sessions yet. However, using the correct session name solves at least some problems.)
-   Configure the JSP-Servlet registration in `weblogic.properties` for maximum J2EE-compliance and/or for maximum performance.

The JSP-Servlet supports some initialization parameters that can be customized to get best performance, maximum compliance or (as shown below) easier debugging:

                        weblogic.httpd.initArgs.*.jsp=\
                        pageCheckSeconds=-1,\
                        setEmptyStrings=false,\
                        compileCommand=./_jspCompiler_.cmd,\
                        workingDir=/weblogic/myserver/tmp_classfiles,\
                        keepgenerated=true,\
                        debug=true,\
                        verbose=true
                    

In the above example, the batch file ( `_jspCompiler_.cmd` ) invokes jikes which results dramatically reduced startup times (jikes is about three times faster than javac.) The batchfile contains only a single line:

    @jikes -g -nowarn %*

The next configuration could be used when all tests have been done and speed is the major concern ...

                        weblogic.httpd.initArgs.*.jsp=\
                        pageCheckSeconds=-1,\
                        setEmptyStrings=false,\
                        compileCommand=./_jspCompiler_.cmd,\
                        workingDir=/weblogic/myserver/tmp_classfiles,\
                        keepgenerated=false,\
                        debug=false,\
                        verbose=false
                    

... together with ...

    @jikes -O -nowarn %*

Weblogic supports similar settings through `<context-params>` in `web.xml` (Please read the latest documentation at the BEA website for details.)

For additional issues, see also [More fixes for WLS 5.1 SP8](http://www.mail-archive.com/struts-dev@jakarta.apache.org/msg00284.html.md) from the Struts Developer mailing list

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


