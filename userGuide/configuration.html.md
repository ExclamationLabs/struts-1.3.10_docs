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

<span id="a5._Configuring_Applications"></span>5. Configuring Applications
--------------------------------------------------------------------------

> *"An author doesn't necessarily understand the meaning of his own story better than anyone else."*

<span id="config-overview"></span>
### <span id="a5.1_Overview"></span>5.1 Overview

Before you can build an application, you need to lay a solid foundation. There are several setup tasks you need to perform before deploying your application. These include components in the configuration file and in the Web Application Deployment Descriptor.

<span id="struts-config"></span>
### <span id="a5.2_The_configuration_file"></span>5.2 The configuration file

The [Writing Action Mappings](building_controller.html.md#4_8_Writing_Action_Mappings) section covered writing the `<form-bean>` and `<action-mapping>` portions of the configuration file. These elements usually play an important role in the development of an application. The other elements in a configuration file tend to be static: you set them once and leave them alone.

These "static" configuration elements are:

-   \<controller\>
-   \<message-resources\>
-   \<plug-in\>

<span id="controller_config"></span>
### <span id="a5.2.1_Controller_Configuration"></span>5.2.1 Controller Configuration

The `<controller>` element allows you to configure the ActionServlet. Many of the controller parameters were previously defined by servlet initialization parameters in your `web.xml` file but have been moved to this section of `struts-config.xml` in order to allow different modules in the same web application to be configured differently. For full details on available parameters see the [struts-config DTDDoc](../struts-core/dtddoc/struts-config_1_3.dtd.html.md) or the list below.

-   **bufferSize** - The size (in bytes) of the input buffer used when processing file uploads. [4096] (optional)
-   **catalog** - Name of the catalog to use when processing requests for this module. [struts]
-   **className** - Classname of configuration bean. [org.apache.struts.config.ControllerConfig] (optional)
-   **command** - Name of the command to execute to process a request. [servlet-standard]
-   **contentType** - Default content type (and optional character encoding) to be set on each response. May be overridden by the Action, JSP, or other resource to which the request is forwarded. [text.html.md] (optional)
-   **forwardPattern** - Replacement pattern defining how the "path" attribute of a `<forward>` element is mapped to a context-relative URL when it starts with a slash. This value may consist of any combination of the following:
    -   *$M* - Replaced by the module prefix of this module.
    -   *$P* - Replaced by the "path" attribute of the selected `<forward>` element.
    -   *$$* - Causes a literal dollar sign to be rendered.
    -   *$x* - (Where "x" is any character not defined above) Silently swallowed, reserved for future use.

    If not specified, the default forwardPattern is consistent with the previous behavior of forwards. [$M$P] (optional)
-   **inputForward** - Set to `true` if you want the `input` attribute of `<action>` elements to be the name of a local or global `ActionForward` , which will then be used to calculate the ultimate URL. Set to `false` to treat the `input` parameter of `<action>` elements as a module-relative path to the resource to be used as the input form. [false] (optional)
-   **locale** - Set to `true` if you want a `Locale` object stored in the user's session if not already present. [true] (optional)
-   **maxFileSize** - The maximum size (in bytes) of a file to be accepted as a file upload. Can be expressed as a number followed by a "K", "M", or "G", which are interpreted to mean kilobytes, megabytes, or gigabytes, respectively. [250M] (optional)
-   **memFileSize** - The maximum size (in bytes) of a file whose contents will be retained in memory after uploading. Files larger than this threshold will be written to some alternative storage medium, typically a hard disk. Can be expressed as a number followed by a "K", "M", or "G", which are interpreted to mean kilobytes, megabytes, or gigabytes, respectively. ["256K"]
-   **multipartClass** - The fully qualified Java class name of the multipart request handler class to be used with this module. [org.apache.struts.upload.CommonsMultipartRequestHandler] (optional)
-   **nocache** - Set to `true` if you want the controller to add HTTP headers for defeating caching to every response from this module. [false] (optional)
-   **pagePattern** - Replacement pattern defining how the `page` attribute of custom tags using it is mapped to a context-relative URL of the corresponding resource. This value may consist of any combination of the following:
    -   *$M* - Replaced by the module prefix of this module.
    -   *$P* - Replaced by the "path" attribute of the selected `<forward>` element.
    -   *$$* - Causes a literal dollar sign to be rendered.
    -   *$x* - (Where "x" is any character not defined above) Silently swallowed, reserved for future use.

    If not specified, the default pagePattern is consistent with the previous behavior of URL calculation. [$M$P] (optional)
-   **processorClass** - The fully qualified Java class name of the `RequestProcessor` subclass to be used with this module. [org.apache.struts.chain.ComposableRequestProcessor] (optional)
-   **tempDir** - Temporary working directory to use when processing file uploads. [{the directory provided by the servlet container}]

This example uses the default values for several controller parameters. If you only want default behavior you can omit the controller section altogether.

    <controller
        processorClass="org.apache.struts.action.RequestProcessor"
           contentType="text.html.md"/>;

<span id="resources_config"></span>
### <span id="a5.2.2_Message_Resources_Configuration"></span>5.2.2 Message Resources Configuration

The framework has built in support for internationalization (I18N). You can define one or more `<message-resources>` elements for your webapp; modules can define their own resource bundles. Different bundles can be used simultaneously in your application, the 'key' attribute is used to specify the desired bundle.

-   **className** - Classname of configuration bean. [org.apache.struts.config.MessageResourcesConfig] (optional)
-   **factory** - Classname of MessageResourcesFactory. [org.apache.struts.util.PropertyMessageResourcesFactory] (optional)
-   **key** - ServletContext attribute key to store this bundle. [org.apache.struts.action.MESSAGE] (optional)
-   **null** - Set to `false` to display missing resource keys in your application like ' *???keyname???* ' instead of `null` . [true] (optional)
-   **escape** - Set to `true` if *escape processing* should be performed on the error message string. [true] (optional)
-   **parameter** - Name of the resource bundle. (required)

Example configuration:

    <message-resources
        parameter="MyWebAppResources"
             null="false" />

This would set up a message resource bundle provided in the file `MyWebAppResources.properties` under the default key. Missing resource keys would be displayed as ' *???keyname???* '.

The default `PropertyMessageResources` implementation can operate in one of three modes:

-   **Default** - default, backwardly compatible, Struts behaviour (i.e. the way its always worked).
-   **JSTL** - compatible with how JSTL finds messages.
-   **Resource** - compatible with how Java's `PropertyResourceBundle` finds messages.

The *mode* can be configured in the struts-config.xml (for more details see `PropertyMessageResources` [JavaDoc](../apidocs/org/apache/struts/util/PropertyMessageResources.html.md)):.

    <message-resources parameter="MyWebAppResources">
        <set-property key="mode" value="JSTL"/>
    </message-resources>

<span id="plugin_config"></span>
### <span id="a5.2.3_PlugIn_Configuration"></span>5.2.3 PlugIn Configuration

Struts PlugIns are configured using the `<plug-in>` element within the configuration file. This element has only one valid attribute, 'className', which is the fully qualified name of the Java class which implements the `org.apache.struts.action.PlugIn` interface.

For PlugIns that require configuration themselves, the nested `<set-property>` element is available.

This is an example using the Tiles plugin:

    <plug-in className="org.apache.struts.tiles.TilesPlugin">
        <set-property
            property="definitions-config"
               value="/WEB-INF/tiles-defs.xml"/>
    </plug-in>

<span id="dd_config_modules"></span>
### <span id="a5.3_Configuring_Your_Application_for_Modules"></span>5.3 Configuring Your Application for Modules

Very little is required in order to start taking advantage of the module feature. Just go through the following steps:

1.  Prepare a configuration file for each module.
2.  Inform the controller of your module.
3.  Use Actions to refer to your pages.

<span id="module_config-files"></span>
### <span id="a5.3.1_Module_Configuration_Files"></span>5.3.1 Module Configuration Files

Back in version 1.0, a few "boot-strap" options were placed in the `web.xml` file, and the bulk of the configuration was done in a single `struts-config.xml` file. Obviously, this wasn't ideal for a team environment, since multiple users had to share the same configuration file.

Since version 1.1, you have two options: you can list [multiple struts-config files](#dd_config) as a comma-delimited list, or you can subdivide a larger application into modules.

With the advent of modules, a given module has its own configuration file. This means each team (each module would presumably be developed by a single team) has their own configuration file, and there should be a lot less contention when trying to modify it.

<span id="module_config-inform_controller"></span>
### <span id="a5.3.2_Informing_the_Controller"></span>5.3.2 Informing the Controller

Since version 1.0, you listed your configuration file as an initialization parameter to the action servlet in `web.xml.` This is still done since version 1.1, but the parameter can be extended. In order to tell the framework machinery about your different modules, you specify multiple 'config' initialization parameters, with a slight twist. You'll still use 'config' to tell the ActionServlet about your "default" module, however, for each additional module, you will list an initialization parameter named "config */module* ", where */module* is the prefix for your module (this gets used when determining which URIs fall under a given module, so choose something meaningful!). For example:

        ...
        <init-param>
            <param-name>config</param-name>
            <param-value>/WEB-INF/conf/struts-default.xml</param-value>
        </init-param>
        <init-param>
            <param-name>config/module1</param-name>
            <param-value>/WEB-INF/conf/struts-module1.xml</param-value>
        </init-param>
        ...

Here we have two modules. One happens to be the "default" module, identified by the param-name of "config", and the other will be using the module prefix "/module1" based on the param-name it was given ("config/module1"). The controller is configured to find the respective configuration files under `/WEB-INF/conf/` (which is the recommended place to put all configuration files). Pretty simple!

(The `struts-default.xml` would be equivalent to what most folks call `struts-config.xml.` I just like the symmetry of having all my module configuration files being named `struts- module.xml` )

If you'd like to vary where the pages for each module are stored, see the [forwardPattern](#controller_config) setting for the Controller.

<span id="module_config-switching"></span>
### <span id="a5.3.3_Switching_Modules"></span>5.3.3 Switching Modules

There are three approaches for switching from one module to another.

1.  You can use the `org.apache.struts.actions.SwitchAction` from the Extras JAR,
2.  you can use a `<forward>` (global or local) and specify the contextRelative attribute with a value of true,
3.  or you can specify the "module" parameter as part of any of the Struts JSP hyperlink tags (Include, Img, Link, Rewrite, or Forward).

You can use `org.apache.struts.actions.SwitchAction` like so:

        ...
        <action-mappings>
        <action path="/toModule"
        type="org.apache.struts.actions.SwitchAction"/>
        ...
        </action-mappings>
        ...

Now, to change to ModuleB, we would use a URI like this:

                        http://localhost:8080/toModule.do?prefix=/moduleB&page=/index.do
                    

If you are using the "default" module as well as "named" modules (like "/moduleB"), you can switch back to the "default" module with a URI like this:

                        http://localhost:8080/toModule.do?prefix=&page=/index.do
                    

Here's an example of a global forward:

    <global-forwards>
        <forward       name="toModuleB"
            contextRelative="true"
                       path="/moduleB/index.do"
                   redirect="true"/>
       ...
    </global-forwards>

You could do the same thing with a local forward declared in an ActionMapping:

       <action-mappings>
       <action ... >
           <forward       name="success"
               contextRelative="true"
                          path="/moduleB/index.do"
                      redirect="true"/>
       </action>
       ...
       </action-mappings>
       

Using the module parameter with a hyperlink tag is even simpler:

        .html.md:link module="/moduleB" path="/index.do"/>
        

That's all there is to it! Happy module-switching!

<span id="dd_config"></span>
### <span id="a5.4_The_Web_Application_Deployment_Descriptor"></span>5.4 The Web Application Deployment Descriptor

The final step in setting up the application is to configure the application deployment descriptor (stored in file `WEB-INF/web.xml` ) to include all the framework or Taglib components that are required. Using the deployment descriptor for the example application as a guide, we see that the following entries need to be created or modified.

<span id="dd_config_servlet"></span>
### <span id="a5.4.1_Configure_the_ActionServlet_Instance"></span>5.4.1 Configure the ActionServlet Instance

Add an entry defining the action servlet itself, along with the appropriate initialization parameters. Such an entry might look like this:

    <servlet>
        <servlet-name>action</servlet-name>
        <servlet-class>
            org.apache.struts.action.ActionServlet
        </servlet-class>
        <init-param>
            <param-name>config</param-name>
            <param-value>
             /WEB-INF/struts-config.xml
            </param-value>
        </init-param>
        <load-on-startup>1</load-on-startup>
    </servlet>

The initialization parameters supported by the action servlet are described below. (You can also find these details in the [Javadocs](../apidocs/org/apache/struts/action/ActionServlet.html.md) for the ActionServlet class.) Square brackets describe the default values that are assumed if you do not provide a value for that initialization parameter.

-   **chainConfig** - Comma-separated list of either context-relative or classloader path(s) to load commons-chain catalog definitions from. If none specified, the default catalog that is provided with the framework will be used. (Since version 1.3)
-   **config** - Context-relative path to the XML resource containing the configuration information for the default module. This may also be a comma-delimited list of configuration files. Each file is loaded in turn, and its objects are appended to the internal data structure. [/WEB-INF/struts-config.xml].
     **WARNING** - If you define an object of the same name in more than one configuration file, the last one loaded quietly wins.
     **WARNING** - Plugins are not designed to be loaded more than once in the same module. The set of configuration files for a module should load a plugin only once.
-   **config/${module}** - Context-relative path to the XML resource containing the configuration information for the application module that will use the specified prefix (/${module}). This can be repeated as many times as required for multiple application modules. (Since version 1.1)
-   **configFactory** - The Java class name of the ModuleConfigFactory used to create the implementation of the ModuleConfig interface. (Since version 1.3) [org.apache.struts.config.impl.DefaultModuleConfigFactory]
-   **convertNull** - Force simulation of the version 1.0 behavior when populating forms. If set to "true", the numeric Java wrapper class types (like `java.lang.Integer` ) will default to null (rather than 0). (Since version 1.1) [false]
-   **rulesets** - Comma-delimited list of fully qualified classnames of additional `org.apache.commons.digester.RuleSet` instances that should be added to the `Digester` that will be processing `struts-config.xml` files. By default, only the `RuleSet` for the standard configuration elements is loaded. (Since version 1.1)
-   **validating** - Should we use a validating XML parser to process the configuration file (strongly recommended)? [true]

**WARNING** - The framework will not operate correctly if you define more than one `<servlet>` element for a controller servlet, or a subclass of the standard controller servlet class. The controller servlet **MUST** be a web application wide singleton.

<span id="dd_config_mapping"></span>
### <span id="a5.4.2_Configure_the_ActionServlet_Mapping"></span>5.4.2 Configure the ActionServlet Mapping

**Note:** The material in this section is not specific to Struts. The configuration of servlet mappings is defined in the Java Servlet Specification. This section describes the most common means of configuring a application.

There are two common approaches to defining the URLs that will be processed by the controller servlet -- prefix matching and extension matching. An appropriate mapping entry for each approach will be described below.

Prefix matching means that you want all URLs that start (after the context path part) with a particular value to be passed to this servlet. Such an entry might look like this:

    <servlet-mapping>
        <servlet-name>action</servlet-name>
        <url-pattern>/do/*</url-pattern>
    </servlet-mapping>

which means that a request URI to match the `/logon` path described earlier might look like this:

                        http://www.mycompany.com/myapplication/do/logon

where `/myapplication` is the context path under which your application is deployed.

Extension mapping, on the other hand, matches request URIs to the action servlet based on the fact that the URI ends with a period followed by a defined set of characters. For example, the JSP processing servlet is mapped to the `*.jsp` pattern so that it is called to process every JSP page that is requested. To use the `*.do` extension (which implies "do something"), the mapping entry would look like this:

    <servlet-mapping>
        <servlet-name>action</servlet-name>
        <url-pattern>*.do</url-pattern>
    </servlet-mapping>

and a request URI to match the `/logon` path described earlier might look like this:

                        http://www.mycompany.com/myapplication/logon.do

**WARNING** - The framework will not operate correctly if you define more than one `<servlet-mapping>` element for the controller servlet.

**WARNING** - If you are using the new module support since version 1.1, you should be aware that **only** extension mapping is supported.

<span id="dd_config_taglib_uri"></span>
### <span id="a5.4.3.1_Configure_the_Struts_JSP_Tag_Libraries_Servlet_2.32.4"></span> 5.4.3.1 Configure the Struts JSP Tag Libraries (Servlet 2.3/2.4)

The Servlet 2.3 and 2.4 specifications simplify the deployment and configuration of tag libraries. All that's now required to install the Struts tag libraries is to copy `struts-taglib.jar` into your `/WEB-INF/lib` directory and reference the tags in your code like this:

                        <%@ taglib
                        uri="http://struts.apache.org/tags.html.md"
                        prefix=.html.md" %>
                    

Note that you **must use the full uri** defined in the various tlds (see the [example configuration](5_4_3_Configure_the_Struts_Tag_Libraries) for reference) so that the container knows where to find the tag's class files. You don't have to alter your `web.xml` file or copy tlds into any application directories.

Of course, the configuration techniques use for older containers do still work.

<span id="config_add"></span>
### <span id="a5.5_Add_Framework_Components_To_Your_Application"></span>5.5 Add Framework Components To Your Application

To use the framework, you must copy `struts-core-*.jar` (and all of the `commons-*.jar` files) into your `WEB-INF/lib` directory. To use Struts Taglib, you must also copy the `struts-taglib-*.jar.` Likewise, to use other optional components, like Extras, Tiles, or the Validator, copy the corresponding `struts-*.jar.`

#### Sidebar: Sharing JAR Files Across Web Applications

Many servlet containers and application servers provide facilities for sharing JAR files across multiple web applications that depend on them. For example, Tomcat 4.1 allows you to put JAR files into the `$CATALINA_HOME/shared/lib` or `$CATALINA_HOME/common/lib` directories, and the classes in those JAR files will be available in all applications, without the need to place them in every web application's `/WEB-INF/lib` directory. Usually, the sharing is accomplished by creating a separate class loader that is the parent of the class loader (created by your container) for each individual web application.

If you have multiple web applications based on the framework, it is tempting to consider taking advantage of this container feature, and placing `struts.jar` and the various `commons-*.jar` files in the shared directory, rather than in each web application. However, there are several potential, and actual, problems with this approach:

-   Classes loaded from the shared class loader cannot see classes in the web application's class loader, unless they are specifically programmed to use the Thread context class loader. For example, the framework dynamically loads your action and form bean classes, and normally would not be able to find those classes. The framework has been programmed to deal with this in *most* scenarios, but it has not been thoroughly audited to ensure that it works in *all* scenarios. The Commons libraries that the framework uses have **NOT** been audited to catch all possible scenarios where this might become a problem.
-   When a class is loaded from a shared class loader, static variables used within that class become global as well. This can cause inter-webapp conflicts when the underlying code assumes that the statics are global only within a particular web applicaiton (which would be true if the class was loaded from the webapp class loader). There are many cases where the framework, and the Commons libraries it relies on, use static variables to maintain information that is presumed to be visible only within a single web application. Sharing these JAR files can cause unwanted interactions, and probably cause incorrect behavior.
-   When JAR files are shared like this, it is not possible to update the JAR file versions employed by a single web application without updating all of them. In addition, because updating a Struts version normally requires recompilation of the applications that use it, you will have to recompile all of your applications as well, instead of being able to manage them independently.

In spite of these difficulties, it is possible that sharing the Struts and Commons JAR files *might* appear to work for you. However, this is **NOT** a supported configuration.

If you file a bug report for `ClassNotFoundException` or `NoClassDefFoundError` exceptions, or similar situations where it appears that the wrong version of a class is being loaded, the bug report will **NOT** be processed unless the problem exists with the JAR files in their recommended location, in the `/WEB-INF/lib` subdirectory of your webapp.

<span id="config_logging"></span>
### <span id="a5.6_Logging"></span>5.6 Logging

Since version 1.0, the logging functionality was fairly limited. You could set a debugging detail level with a servlet initialization parameter, and all log messages were written to wherever `ServletContext.log()` output is sent by your servlet container. With Struts 1.1, however, all logging messages written by the framework, as well as the commons libraries that it utilizes, flow through an abstract wrapper called [Commons Logging,](http://commons.apache.org/logging) which can be used as a wrapper around any logging implementation. The most common implementations used are simple logging to `System.err,` the [Apache Log4J](http://jakarta.apache.org/log4j/) package, or the built-in logging capabilities of JDK 1.4 or later in the [java.util.logging](http://java.sun.com/j2se/1.4/docs/api/java/util/logging/package-summary.html.md) package.

This section does not attempt to fully explain how Commons Logging is configured and used. Instead, it focuses on pertinent details of using Commons Logging in connection with the Struts Framework. For complete documentation on using Commons Logging, consult the documentation for the logging system you are using, plus the Commons Logging [Javadocs.](http://commons.apache.org/logging/commons-logging-1.0.3/docs/api/)

Commons Logging provides fine-grained control over the logging messages created by a `Log` instance. By convention, the `Log` instances for the framework (and the Commons packages in general) are named the fully qualified class name of the class whose messages are being logged. Therefore, log messages created by the `RequestProcessor` class are, naturally enough, directed to a logger named `org.apache.struts.action.RequestProcessor.`

The advantage of this approach is that you can configure the level of detail in the output you want from each class, individually. However, it would be a burden to be required to maintain such settings for every possible class, so the logging environment supports the notion of logging *hierarchies* as well. If a detail level configuration for a particular class has not been set, the logging system looks up the hierarchy until it finds a configuration setting to use, or else uses the default detail level if no configuration for any level of the hierarchy has been explicitly set. In the case of our messages from `RequestProcessor,` the logging system will look for explicit settings of the following loggers, in this order, until it finds one:

-   `org.apache.struts.action.RequestProcessor`
-   `org.apache.struts.action`
-   `org.apache.struts`
-   `org.apache`
-   `org`
-   The default logging detail level for your log implementation.

In a similar manner, the detail level for messages from `PropertyUtils` (from the Commons BeanUtils library) is set by a search for configuration settings for:

-   `org.apache.commons.beanutils.PropertyUtils`
-   `org.apache.commons.beanutils`
-   `org.apache.commons`
-   `org.apache`
-   `org`
-   The default logging detail level for your log implementation.

You can seamlessly integrate logging from your own components into the same logging implementation that the framework and the Commons libraries use, by following the instructions in [Section 4.11](building_controller.html.md#4_11_Commons_Logging_Interface) . If you do this, you are strongly encouraged to follow the same naming convention for loggers (based on the class name of the messages being logged) for maximum configuration flexibility.

For more about putting it all together, see the [Building Applications HowTo.](../faqs/apps.html.md)

Next: [Release Notes](./release-notes.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


