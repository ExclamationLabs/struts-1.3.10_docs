<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Scripting

-   **Welcome**
-   [User Guide](user-guide.html.md)
-   [Source Guide](source-guide.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Welcome_to_Struts_Scripting"></span>Welcome to Struts Scripting
-------------------------------------------------------------------------

<span id="overview"></span>
This component allows Struts Actions to be written in the scripting language of one's choice rather than as Java classes. It uses the [Bean Scripting Framework](http://jakarta.apache.org/bsf) to allow scripts to be written in any language BSF supports like Perl, Python, Ruby, JavaScript, Groovy, and even VBScript.

Struts Scripting allows an application to be developed rapidly with the quick development cycle (edit file -\> refresh browser) that one would expect in a scripting environment. Furthermore, it enables other non-Java trained members of a development group, such as web designers who may have a scripting background, to be more involved, leaving the Java developers to create the reusable services the Struts actions will interact with. Finally, when used with Java-like languages such as [Groovy](http://groovy.codehaus.org), applications can quickly be stood up, then later the Struts action scripts can be migrated to Java for better performance.

### <span id="Features"></span>Features

<span id="features"></span>
-   Implement Actions with JavaScript, Groovy, etc.
-   Supports all BSF languages
-   Scripts cached in memory on first use
-   Ability to pass parameters to script through Struts config

### <span id="Documentation"></span>Documentation

<span id="documentation"></span>
-   [User Guide](user-guide.html.md) - Covers installation and usage
-   [Source Code Guide](source-guide.html.md) - Covers the source layout and how to build Struts Scripting
-   [Javadocs](apidocs/index.html.md) - Includes [`struts`](apidocs/org/apache/struts/scripting/StrutsInfo.html) variable and [Filter](apidocs/org/apache/struts/scripting/BSFManagerFilter.html) API's.
-   [Struts Mailreader](http://svn.apache.org/viewvc/struts/action/trunk/apps/scripting-mailreader/src/main/) - A rewrite of the Struts Mailreader example application using Struts Scripting and [Groovy](http://groovy.codehaus.org)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


