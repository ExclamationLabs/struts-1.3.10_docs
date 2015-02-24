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

#### SilverStream Application Server 3.7.1 and later

-   Start the SilverStream application server.
-   Create an XML deployment plan for the " `struts-example.war` " application. Call the file " `struts-example-depl-plan.xml` ". You can use the following contents for the file

------------------------------------------------------------------------

----- cut here -----

                        <?xml version="1.0" encoding="UTF-8"?>
                        <!DOCTYPE warJarOptions PUBLIC
                        "-//SilverStream Software, Inc.//DTD J2EE WAR
                        Deployment Plan//EN"
                        "deploy_war.dtd">
                        <warJarOptions>
                        <warJar>
                        <warJarName>struts-example.war</warJarName>
                        <isEnabled>true</isEnabled>
                        <urls><el>struts-example</el></urls>
                        </warJar>
                        </warJarOptions>
                    

----- cut here -----

------------------------------------------------------------------------

Create an XML deployment plan for the " `struts-documentation.war` " application. Call the file "struts-documentation-depl-plan.xml". You can use the following contents for the file:

------------------------------------------------------------------------

----- cut here -----

                        <?xml version="1.0" encoding="UTF-8"?>
                        <!DOCTYPE warJarOptions PUBLIC
                        "-//SilverStream Software, Inc.//DTD J2EE WAR
                        Deployment Plan//EN"
                        "deploy_war.dtd">
                        <warJarOptions>
                        <warJar>
                        <warJarName>struts-documentation.war</warJarName>
                        <isEnabled>true</isEnabled>
                        <urls><el>struts-documentation</el></urls>
                        </warJar>
                        </warJarOptions>
                    

----- cut here -----

------------------------------------------------------------------------

Run the following " `SilverCmd DeployWAR` " commands to deploy the applications. You can change 'localhost' to whatever server you are deploying to. You can change 'Silvermaster' to whatever database you are deploying to.

-   SilverCmd DeployWar localhost Silvermaster struts-example.war -f struts-example-depl-plan.xml
-   SilverCmd DeployWar localhost Silvermaster struts-documentation.war -f struts-documentation-depl-plan.xml

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


