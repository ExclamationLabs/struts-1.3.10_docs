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

#### iPlanet Application Server 6.0

Service Pack 2 is recommended.

NOTE: At present, the Struts example application still uses a non-Serializable servlet context attribute, and will not run in an environment that requires them, like iPlanet Application Server.

#### iPlanet Web Server 4.2

Here are the issues I ran into while moving my struts based application from Tomcat (supports WebApps and WAR) to iWS 4.1 (does **NOT** support Webapps and WAR).

Webapps and WAR will be supported in iWS 5.0, as mentioned in iWS5.0 roadmap.

#### Classpath issues.

This s pretty straightforward. Since there is no notion of `WEB-INF/lib` and `WEB-INF/classes` the classpath has to be explicitly set in `$SERVER_ROOT/config/jvm12.conf` .

#### Context relative paths

All URLs should be visible from the document root. In my case I just created a symbolic link from `$DOCROOT/myapp` to `webapps/myapp` .

#### Extension mapping

The config file `$SERVER_ROOT/config/rules.properties` has a similar mechanism as in web.xml.

I have this in my `rules.properties` which forwards all urls ending with "do" to the servlet whose logical name is action.

    ####
                        @.*[.]do$=action
                        ####

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


