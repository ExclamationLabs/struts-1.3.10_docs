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

#### WebSphere Application Server 3.5 and the Example Application

Server: Windows 2000 Server with WebSphere 3.5.3 Advanced

1.  Start up the adminserver.
2.  Start up Admin Console.
3.  Use the Convert War file task to convert the struts-example.war from the struts-b1 distrib as-is.
4.  Convert to the default\_server, default servlet engine and standard install directory (c:\\websphere\\appserver\\hosts\\default\_host).
5.  Create a WEB-INF directory in the servlets dir and copy struts-config.xml, database.xml AND web.xml into it (Keep WEB-INF with all the TLD's under web - both WEB-INF directories must be present).
6.  Copy jaxp 1.0.1's (NOT 1.1.1's) jaxp.jar and parser.jar to the servlets directory of the strut-example webapp.
7.  In the servlets directory, open struts.jar with WinZip. Extract the three DTD's (struts-config\_1\_0.dtd, web-app\_2\_2.dtd and web-app\_2\_3.dtd) into the servlets directory making sure you use folder names (so the files extract to servlets/org/apache/struts/resources).
8.  Click on struts-example in the Admin Console under Default Server/Default Servlet Engine and click the advanced tab on the right hand side of the screen.
9.  Down where it says Default Error Page, enter /ErrorReporter and then click Apply.
10. Start the Default Server via the Admin Console. You should see a whole bunch of ActionServlet messages in the default\_host\_stdout.log file with no exceptions.
11. Via a browser accessed the app using http://localhost/struts-example/index.jsp.
12. If it returns "Application not Available" then go back to the Admin Console, right-click on struts-example and select Restart WebApp.
13. Once it reports success, go back to the URL above and try again - it should work flawlessly.

For whatever reason, some installations do not like XML files that reference PUBLIC DTD's - if in looking at the default\_host\_stdout.log file you see errors about invalid public URL references during DTD registrations, or if your pages say "cannot find //logon or //saveRegistration (ie. action mappings) then do the following:

1.  Stop Default Server
2.  Go to servlets\\WEB-INF\\ and edit web.xml and struts\_config.xml.
3.  In the DOCTYPE declaration, change the word PUBLIC to SYSTEM and completely remove the line that reads "-//Sun Microsystems, Inc.//DTD Web Application 2.2//EN" from web.xml and remove "-//Apache Software Foundation//DTD Struts Configuration 1.0//EN" from struts-config.xml.
4.  Save these changes and go back to step 10 above.

Just as a troubleshooting guide -

If you are getting errors like "Cannot find ActionMappings, etc..." or "Cannot find key org.apache.struts.MESSAGE" then your application is most likely still bombing on the struts-config issue that Richard discovered. The above steps SHOULD correct that leaving nothing out. If you are getting 404 errors about //logon or something not found, then you are still having XML config troubles and it is not initializing the Action servlet properly. Follow the steps above in regards to DTD's and it should work.

As a final thought, I obviously haven't gotten to test too much but I don't believe that there are ANY coding changes that need to be made to the actual struts source. Everything about getting it to work in WebSphere has been a WebSphere configuration issue thus far (and I don't think I'll be having any more).

If changing the DTD's to SYSTEM, do so ONLY AFTER using the Convert a War util. Ant doesn't seem to like it the other way! :)

------------------------------------------------------------------------

Back to [Installation](installation.html.md#Containers)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


