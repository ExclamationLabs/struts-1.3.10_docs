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

#### Bluestone Universal Business Server 7.2

-   You need UBS version 7.2 to run war file applications. The UBS 7.2.2 evaluation is located [here](http://www.bluestone.com/SaISAPI.dll/SaServletEngine.class/products/downloads.jsp) . If you're using version 7.2.1, you need to download the WAR file patch, located in the product enhancement section of Bluestone's website [here](http://www.bluestone.com/SaISAPI.dll/SaServletEngine.class/products/wfe.jsp)
-   After installation of the correct version and/or patch of UBS 7.2, you need to modify your apserver.txt file to point to the correct directory for your war file applications. Look for the section that says something similar to the following:

                                    [SaServletEngine.class]
                                    session_affinity=1
                                    type=1
                                    program=/SaServletEngine.class
                                    file_path=f:\webapps
                                    host=localhost:20000
                                

-   Use the directory specified by the "file\_path" variable, or modify it to point to your own custom webapp directory. Copy the "struts-documention.war" and "struts-example.war" files into that webapp directory, and start the UBS (read documentation distributed with UBS for information on how to start it if necessary). Your webapps are now accessible from the following URL: http://localhost/\<PLUGIN\>/SaServletEngine.class/struts-example/
     http://localhost/\<PLUGIN\>/SaServletEngine.class/struts-documentation/
-   Note: "\<PLUGIN\>" represents the plugin you are using for your specific webserver. For Apache on Windows, it might be "cgi-bin/SaCGI.exe", for IIS on Windows, it might be "scripts/SaCGI.exe" or "scripts/ISAPI.dll". Consult the UBS documentation for more information.

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


