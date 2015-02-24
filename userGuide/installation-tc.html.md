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

#### Tomcat 3.2.1 With Apache

Note that the instructions for Tomcat 4 will be different than those for Tomcat 3, but the Tomcat 4.0 web connector is still under development. Versions of Tomcat prior to 3.2.1 are not recommend for use with Struts.

-   These instructions assume you have successfully integrated Tomcat with Apache according to the Tomcat documentation.
-   Copy "struts-documentation.war" and "struts-example.war" to your $TOMCAT\_HOME/webapps directory
-   Restart Tomcat if it is already running
-   Tomcat will generate a file "$TOMCAT\_HOME/conf/tomcat-apache.conf" that will be used by Apache. This file is regenerated every time you start Tomcat, so copy this file to a safe place (such as your Apache configuration directory; on Unix systems this is usually `/usr/local/apache/conf` .
-   If you are running Tomcat 3.1, Tomcat will not have generated the entries for your new applications. Add the following lines to the `tomcat-apache.conf` file that you have saved, replacing $TOMCAT\_HOME with the path to your Tomcat home directory:

<!-- -->

                        Alias /struts-documentation
                        "$TOMCAT_HOME/webapps/struts-documentation
                        <Directory "$TOMCAT_HOME/webapps/struts-documentation>
                        Options Indexes FollowSymLinks
                        </Directory>
                        ApJServMount /struts-documentation/servlet
                        /struts-documentation
                        <Location "/struts-documentation/WEB-INF/">
                        AllowOverride None
                        deny from all
                        </Location>
                        Alias /struts-example
                        "$TOMCAT_HOME/webapps/struts-example"
                        <Directory "$TOMCAT_HOME/webapps/struts-example>
                        Options Indexes FollowSymLinks
                        </Directory>
                        ApJServMount /struts-example/servlet /struts-example
                        <Location "/struts-example/WEB-INF/">
                        AllowOverride None
                        deny from all
                        </Location>
                    

-   The generated file above does not know anything about extension mappings defined in a web.xml file, so the "\*.do" URIs that go to the controller servlet will not be recognized. To fix this, add the following line to the saved version of "tomcat-apache.conf", after the corresponding line for the .jsp extension:
     `AddHandler jserv-servlet .do`
-   Ensure that the saved version of "tomcat-apache.conf" is referenced in your Apache "httpd.conf" configuration file. A typical use would have the following line at the bottom of "httpd.conf":
     `Include /usr/local/apache/conf/tomcat-apache.conf`
-   In order to recognize "index.jsp" as a default page for web applications, search in your "httpd.conf" for a "DirectoryIndex" directive. If you have one, add "index.jsp" to the end of the list, so that it might look like this:
     `DirectoryIndex index.html.md index.jsp`
     If you do not have such an entry, add one like this:
     `DirectoryIndex index.jsp`
-   Restart Apache to make it aware of the new applications. You should now be able to access the applications from a browser like this:
     `http://localhost/struts-documentation http://localhost/struts-example`

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


