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

#### Jetty Java HTTP Servlet Server

Jetty is a small, pure-Java, open source HTTP server that supports the 2.3 Servlet spec and JSP 1.2. Jetty can be downloaded from <http://www.mortbay.com/jetty> .

Struts WAR files run nearly straight out of the box when placed underneath Jetty's webapps directory. The one additional step needed is to add an entry for each WAR file to the Jetty server configuration file in order to map the appropriate request paths to the added Struts web applications (using "\<Call name="addWebApplication"\>...").

So for example, if you have copied the WAR files that come with the Struts binary distribution into a subdirectory of the "%JETTY\_HOME%/webapps" called "%JETTY\_HOME%/webapps/struts" so that you have:

                        - %JETTY_HOME%/webapps/struts/struts-documentation.war
                        - %JETTY_HOME%/webapps/struts/struts-example.war
                        - %JETTY_HOME%/webapps/struts/struts-exercise-taglib.war
                        - %JETTY_HOME%/webapps/struts/struts-upload.war
                        - %JETTY_HOME%/webapps/struts/struts-blank.war
                    

And you want to run Jetty using the demo.xml configuration file that comes with Jetty, just add the following block to demo.xml, anywhere after the Listeners are declared.

                        <!-- Jetty config for Struts BEGIN -->

                        <Call name="addWebApplication">
                        <Arg>/struts/struts-documentation/*</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/webapps/struts/struts-documentation.war</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/etc/webdefault.xml</Arg>
                        <Arg type="boolean">false</Arg> <!-- if
                        true,
                        expand war in temp dir -->
                        </Call>

                        <Call name="addWebApplication">
                        <Arg>/struts/struts-example/*</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/webapps/struts/struts-example.war</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/etc/webdefault.xml</Arg>
                        <Arg type="boolean">true</Arg> <!-- if
                        true,
                        expand war in temp dir -->
                        </Call>

                        <Call name="addWebApplication">
                        <Arg>/struts/struts-exercise-taglib/*</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/webapps/struts/struts-exercise-taglib.war</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/etc/webdefault.xml</Arg>
                        <Arg type="boolean">false</Arg> <!-- if
                        true,
                        expand war in temp dir -->
                        </Call>

                        <Call name="addWebApplication">
                        <Arg>/struts/struts-upload/*</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/webapps/struts/struts-upload.war</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/etc/webdefault.xml</Arg>
                        <Arg type="boolean">true</Arg> <!-- if
                        true,
                        expand war in temp dir -->
                        </Call>

                        <Call name="addWebApplication">
                        <Arg>/struts/struts-blank/*</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/webapps/struts/struts-blank.war</Arg>
                        <Arg><SystemProperty name="jetty.home"
                        default="."/>/etc/webdefault.xml</Arg>
                        <Arg type="boolean">true</Arg> <!-- if
                        true,
                        expand war in temp dir -->
                        </Call>

                        <!-- Jetty config for Struts END -->
                    

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


