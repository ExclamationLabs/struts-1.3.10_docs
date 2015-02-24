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

#### <span id="ipas13"></span>iPortal Application Server 1.3

**Tested with: Windows 2000**
#### Important Note:

At the moment, iPAS 1.3 is not fully compliant with the JSP 1.1/1.2 specification.

Specifically, the automatic type conversions for custom tag parameters specified in "Issue 7" of the JSP 1.1 Errata and in the JSP 1.2 Proposed Final Draft have not yet been implemented.

As it stands, JSP pages that make use of Struts taglibs whose parameters require conversion (such as booleans) will not compile under JRun. This includes the Struts Example Application. Attempting to run the example application will result in an exception similar to the following being thrown:

                        /struts-example/index.jsp:

                        Compilation failed [IT_Builder:1000]
                        at
                        com.iona.j2ee.builder.JavaBuilder.build(JavaBuilder.java:84)
                        at
                        com.iona.j2ee.builder.JspBuilder.build(JspBuilder.java:51)
                        at
                        com.iona.j2ee.builder.WarBuilder.build(WarBuilder.java:111)
                        at
                        com.iona.j2ee.builder.EarBuilder.build(EarBuilder.java:99)
                        at
                        com.iona.j2ee.builder.EarBuilder.main(EarBuilder.java:223)
                        at iportal.build.main(build.java:14)
                        ocale(boolean) in org.apache.struts.taglib.html.md.HtmlTag
                        cannot be applied to (java.lang.String)
                        _x0.setLocale("true");
                        ^
                        1 error
                    

(For more details see refer to:
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg01860.html.md> )

The following instructions describe how to install the Struts Example Application under iPAS 1.3. A subsequent section describes how the Struts Example Application can be patched to work with Struts.

The following instructions assume the following:

-   iPortal Application Server 1.3 has been installed.
-   Both the Strut and XML Parser libraries are in your classpath.

#### Installing the struts example application

-   Start iPAS Services by clicking on the [Start iPAS Services] menu item.
-   Start the iPortal Application Server by clicking on the [iPortal Application Server] menu item.
-   Start a command shell. Change to the `$INSTALLDIR\IONA` and run the setenvs.bat file.
-   Create a directory called jars.

Now run the EARSCO tool. Type `java iportal.earsco` and at the prompts do:

-   Next
-   Type in the application name of `struts-example` then click next.
-   In step three click the check box and enter the name of the WAR `struts-example` .Then click next.
-   Click on Finish.

Now you must copy the contents of the struts-example war into the EARSCO directory structure as follows:

Under `$INSTALLDIR\IONA\jars\struts-examples\src\struts-example.war` you copy contents into the following directories: etc, lib, src and web.

-   Copy all files in the root directory
     `$INSTALLDIR\jakarta-tomcat-3.2.1\webapps\struts-example\WEB-INF`
     into the earsco directory
     `$INSTALLDIR\IONA\jars\struts-examples\src\struts-example.war\etc`
     Do not copy in the classes or lib directories.
-   Copy the directory
     `$INSTALLDIR\jakarta-tomcat-3.2.1\webapps\struts-example\WEB-INF\lib`
     into the earsco directory
     `$INSTALLDIR\IONA\jars\struts-examples\src\struts-example.war\lib`
-   Copy the directory
     `$INSTALLDIR\jakarta-tomcat-3.2.1\webapps\struts-example\WEB-INF\classes`
     into the earsco directory
     `$INSTALLDIR\IONA\jars\struts-examples\src\struts-example.war\src`
-   Copy the directory
     `$INSTALLDIR\jakarta-tomcat-3.2.1\webapps\struts-example`
     into the earsco directory
     `$INSTALLDIR\IONA\jars\struts-examples\src\struts-example.war\web`
-   Next modify the application.xml in the
     `$INSTALLDIR\IONA\jars\struts-examples\etc` directory to this:

<!-- -->

                        <application>

                        <!-- Add display name -->
                        <display-name>Struts Example</display-name>
                        .......
                    

-   Last update the cc.xml in the
     `$INSTALLDIR\IONA\jars\struts-examples directory as follows:`

<!-- -->

                        <configuration>
                        <web-app>
                        <context-root>struts-example</context-root>
                        </web-app>
                        </configuration>
                    

Now you are ready to compile and deploy the struts-example.

To compile the source from the $INSTALLDIR\\IONA\\jars\\struts-examples type

`java iportal.build`

Next, type

`java iportal.deploy`

The first time you deploy you will be prompted by a Deploy wizard and asked to supply both locations of the struts-example.ear file and of the cc.xml file. Once both elements have been satisfied continue until the finish button and click it. The EAR file should deploy successfully.

Test the sample application by using the following URL in the browser:

`http://hostname:9000/struts-example/index.jsp`

The `struts-documentation.war` can be installed using the same procedure.

#### Patching the struts example application

As mentioned at the beginning of these notes, the Struts Example Application will not run under iPAS 1.3 without modification. The following changes will need to be made:

-   index.jsp, logon.jsp: Change \.html.md:html locale="true"\> to
     \.html.md:html locale=\<%= true %\>\>
-   registration.jsp, subscription.jsp: Change all instances of filter="true" to
     filter=\<%= true %\>

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


