<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Scripting

-   [Welcome](index.html.md)
-   [User Guide](user-guide.html.md)
-   **Source Guide**

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

<span id="Source_Code_Guide"></span>Source Code Guide
-----------------------------------------------------

<span id="overview"></span>
The Struts Scripting component, for the most part, follows Apache Struts build and source code layout, so if you are familiar with another Struts component, you'll be at home here. If not, this guide first walks you though what is where and why. Next, it gives help on how to build common artifacts.

Again, since the heavy lifting is done by the [Bean Scripting Framework](http://jakarta.apache.org/bsf) and the scripting engines themselves, there isn't much code to this project itself.

-   [Source code layout](#layout)
-   [Build instructions](#build)

### <span id="Source_code_layout"></span>Source code layout

<span id="layout"></span>
When you unzip the latest release of Struts or check it out from Subversion (more help on Subversion at the Struts [source code](http://struts.apache.org/downloads.html.md#Source_Code)), you'll be confronted with a directory structure that includes:

-   `/apps/scripting-mailreader` - A modified version of the classic Struts Mailreader example application. This rendition replaces Java-coded Struts Actions with [Groovy](http://groovy.codehaus.org) scripts.
-   `/scripting/src` - All other scripting source code can be found here
-   `/scripting/src/main/java` - The source code for the Struts Scripting framework itself

<!-- -->

-   `/scripting/src/site/xdocs` - The XML source code for all documentation, including this guide.
-   `/scripting/target` - Maven puts all compiled files into this temporary directory.

Next, we'll look at how to build both Struts Scripting library and the Mailreader example application.

### <span id="Build_Instructions"></span>Build Instructions

<span id="build"></span>
Struts Scripting uses [Apache Maven 2](http://maven.apache.org) to build its JAR, example application, documentation, and distribution files. Maven is used throughout Struts for building subprojects, providing a consistent build environment to Struts users. To follow these build instructions, you will need to have [Apache Maven 2](http://maven.apache.org) installed and its `mvn` executable available in your command path.

Since there are a bunch of build targets, we will break the build down into tasks that you might want to accomplish and show the best way to complete them.

-   **Build the Struts Scripting JAR** - Run '`mvn jar:jar`' which will create the JAR as `/scripting/target/struts-scripting-VERSION.jar`.
-   **Build the Mailreader example** - Change to `/apps/scripting-mailreader` and run '`mvn install`' to create `/apps/scripting-mailreadertarget/scripting-mailreader.war`.
-   **Build the documentation** - Run '`mvn site`' to create the Struts Scripting website at `/scripting/target/docs`.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


