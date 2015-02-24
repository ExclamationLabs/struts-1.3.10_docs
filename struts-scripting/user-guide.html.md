<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Scripting

-   [Welcome](index.html.md)
-   **User Guide**
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

<span id="User_Guide"></span>User Guide
---------------------------------------

<span id="overview"></span>
The entire Struts Scripting component is only a few classes, since most of the heavy lifting is done by the [Bean Scripting Framework](http://jakarta.apache.org/bsf) and the scripting engines themselves. Therefore, there are only a few steps you'll need to take in order to sucessfully install and use Struts Scripting.

-   [Installation](#installation)
-   [Usage](#usage)

### <span id="Installation"></span>Installation

<span id="installation"></span>
After downloading the Struts Scripting distribution, copy the Struts Scripting jar, `struts-scripting-1.0.1.jar`, to your application's libraries directory. When deployed, this directory will be `WEB-INF/lib`.

Next, choose which scripting engine you want to use. BSF ships with knowledge about the following languages and script extensions:

**BSF-supported languages and extentions**
javascript (js)
jacl (jacl)
netrexx (nrx)
java (java)
javaclass (class)
bml (bml)
vbscript (vbs)
jscript (jss)
perlscript (pls)
perl (pl)
jpython (py)
jython (py)
lotusscript (lss)
xslt (xslt)
pnuts (pnut)
beanbasic (bb)
beanshell (bsh)
ruby (rb)
judoscript (judo, jud)
Once you have picked a language, you need to download its libraries and install it into your application, which usually means copying its jar files into the same location you copied the Struts Scripting jar. If you are not sure, we recommend Groovy which ships with the Struts Scripting Mailreader example, as it features a very similar Java-like syntax.

*Optional*: If you don't see your desired language that claims to support BSF, or their BSF engine has changed from what BSF expects, you can manually define BSF engines and have them loaded by Struts Scripting. Create a file called `struts-scripting.properties` and add two properties for each engine:

-   `struts-scripting.engine.ENGINE_NAME.class` - The class of the BSF engine where ENGINE\_NAME is the name you are calling the engine.
-   `struts-scripting.engine.ENGINE_NAME.extensions` - A comma-delimited list of file extensions that will be used to identify the engine to use to execute the script.

The `struts-scripting.properties` should then stored in a directory accessible to the classloader, usually `WEB-INF/classes`.

### <span id="Usage"></span>Usage

<span id="usage"></span>
To determine what script will be executed, the "parameter" attribute of the action mapping should contain the name of the script relative to the web application root directory (i.e. http://server/app). In the place of the traditional Action implementation, use the value `org.apache.struts.scripting.ScriptAction`. For example:

        <action    path="/logoff"
                   type="org.apache.struts.scripting.ScriptAction"
                   parameter="/WEB-INF/scripts/Logoff.bsh">
          <forward name="success"              path="/index.jsp"/>
        </action>

In addition to specifying the script file, the "parameter" attribute can also contain parameters that will be passed to the script in the form of pre-defined variables. The format follows the URL format:

        parameter="/path/file.bsh?PARAMETER_NAME=PARAMETER_VALUE[&amp;PARAMETER_NAME=PARAMETER_VALUE..]"

This ability to pass parameters can enable DispatchAction-type behavior where one script file can handle multiple action paths. If you are using Struts Action 1.3 or later, this feature isn't as useful since you can pass multiple values through ActionMapping using the `<set-property key="foo" value="bar">` syntax.

Before the script completes, the next ActionForward needs to be specified. This can be done one of two ways:

1.  Set `struts.forwardName` to the name of the forward
2.  Set `struts.forward` to the actual ActionForward object

A number of pre-defined variables are available to the script:

-   `request` - The HTTP request
-   `response` - The HTTP response
-   `session` - The session
-   `application` - The servlet context
-   `struts` - A grouping of all Struts-related objects
-   `log` - A logging instance

You can add your own variables by creating a BSFManagerFilter and configuring it in struts-scripting.properties:

-   `struts-scripting.filters.FILTER_NAME.class=FILTER_CLASS` - The class implementing BSFManagerFilter where FILTER\_NAME is the name you are calling the filter.
-   `struts-scripting.filters.FILTER_NAME.PROPERTY_NAME=PROPERTY_VALUE` - A property to be used by the filter.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


