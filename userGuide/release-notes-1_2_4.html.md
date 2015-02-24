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

<span id="a6.1_Release_Notes_-_Version_1.2.4"></span>6.1 Release Notes - Version 1.2.4
--------------------------------------------------------------------------------------

### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place since [Version 1.1](release-notes-1_1.html.md) was released.

### <span id="Whats_Included"></span>What's Included?

The binary distribution of this release includes the following files relevant to Struts:

-   `INSTALL.txt` - Brief installation instructions. For more detail, see the `Struts User Guide` , either through the Struts Documentation application or online at <http://struts.apache.org/> .
-   `LICENSE.txt` - The Apache Software Foundation license that defines the terms under which you can use Struts (and other software licensed by Apache).
-   `contrib/` - Additional libraries developed by the Struts team which are not yet part of the core distribution.
-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `antlr-#.#.jar` - ANTLR, ANother Tool for Language Recognition, a public domain library made available by [antlr.org](http://www.antlr.org/) .
    -   `commons-*-#.#.jar` - Various packages from the [Jakarta Commons Project](http://jakarta.apache.org/commons/) that Struts relies on. You are welcome to use these classes in your own applications. These JAR files should be copied into the `/WEB-INF/lib` directory of your web application.
    -   `jakarta-oro-#.#.jar` - JAR file containing the Jakarta ORO package, utilitied by the Struts Valdiator. You must place this file in the `/WEB-INF/lib` directory of your web application to use the Struts Validator package.
    -   `struts-#.#.jar` - JAR file that contains the compiled Java classes of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts-*.tld` - The tag library descriptor files for the Struts tag libraries (bean,.html.md, logic, and nested). When these taglibs are used, you must place these files in the `/WEB-INF` directory of your web application and reference them with appropriate `<taglib>` directives in your web.xml file.
    -   `struts-config_1_2.dtd` - The Document Type Definition (DTD) for the Struts 1.2 configuration file (which is typically named `/WEB-INF/struts-config.xml` ). Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `struts-config_1_1.dtd` - The Document Type Definition (DTD) for the Struts 1.1 configuration file (which is typically named `/WEB-INF/struts-config.xml` ). Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `struts-config_1_0.dtd` - The Document Type Definition (DTD) for the Struts 1.0 configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `web-app_2_2.dtd` - The Document Type Definition (DTD) for web.xml files conforming to the Servlet 2.2 specification. This copy is for reference purposes only.
    -   `web-app_2_3.dtd` - The Document Type Definition (DTD) for web.xml files conforming to the Servlet 2.3 specification. This copy is for reference purposes only.
-   `webapps/` - Web Application Archive (WAR) files for the web applications that are included with Struts.

For the version requirements of each library, see the [Installation chapter](installation.html.md) .

### <span id="Whats_new"></span>What's new?

This section highlights new features added and critical changes made since the last release. Other interesting changes are listed in the [What Changed?](#Changes) section. Subscribers to the [struts-dev mailing list](../using.html.md#Lists) , receive reports of all changes as they are made.

**Deprecations** - Many constructs were deprecated for the Struts 1.1 release, most of which have now been removed. Before moving to this release, you should clean-compile your application with deprecation warnings enabled. Alternatives should be available for all decprecated constructs. **You are strongly advised** to resolve all Struts 1.1. deprecations before moving to this release. Removed constructs most likely to affect developers are:

-   `org.apache.struts.Action` statics: Use `org.apache.struts.Global` statics instead.
-   `Action.perform` : Use `Action.execute` instead.

Although not removed or deprecated, in many cases **you should replace** the `ActionErrors` with the preferred `ActionMessages` to ensure correct operation.

**TagUtils and ModuleUtils** - Many utility methods previously found in `org.apache.struts.utils.RequestUtils` have been moved to `org.apache.struts.taglibs.TagUtils` or `org.apache.struts.utils.ModuleUtils` .

**GenericDataSource / GenericConnection implementations removed** - The datasources manager is still supported, but our own datasource *implementation* is not. You are welcome to plug in your own DataSource implementation, but we do not have the resources to maintain one of our own. If your container does not supply a DataSource implementation, the DBCP package from the Jakarta Commons is suggested.

**Validator enhancements**

-   ValidWhen - The Struts Validator now supports a ValidWhen rule, so that one validation can be dependant on another. [Details ...](../faqs/validator.html.md#validWhen)
-   IntRange now checks select-one and radio fields. Example: This allows populating combo boxes with valid choices plus one additional choice with a caption something like "Choose one" and a value 0f "-1". Then when the user attempts to submit the form, you can look for the value of "-1" and advise if nothing was selected.
-   You can now force the clientside Javascript validation to check all constraints, instead of stopping at the first error. By setting a new property, `stopOnFirstError` , on the Validator PlugIn to false. [Details ...](dev_validator.html.md#stopOnFirstError)
-   The "required" validation can now handle checkboxes, radio,select-one, and select-multiple field types. See the updated Validator example application to see these new features in action.
-   A standard `validateUrl` rule lets you check if a property contains a well-formed URL.

**DigestingPlugIn** - A new standard PlugIn that helps you create your own object graph in application scope. This is handy way to create business objects for Actions to call. Check the latest MailReader eaxmple application to see the DigestingPlugin in action.

**ModuleConfigVerifier** - While not exactly new, a standard class for verifying module configurations is also available in the PlugIn packages. As it stands, the `ModuleConfigVerifier` mainly confirms that various components of the Struts object graph were loaded. However, ambitious developers could extend this class with additional checks to ensure the Struts configuration is internally consistent.

**Maven project files** - While still under development, significant progress has been made toward putting the Struts build process under [Maven](http://maven.apache.org) . The core JAR and TLDs can be built using Maven, leveraging the shared Maven repository for our many dependencies. You can find the current maven.xml and project.xml in the root directory of the Struts source distribution. However, at this time, the original Ant build files are still the official mechanism for building Struts.

**New Configuration DTD** - The `struts-config_1_2.dtd` is preferred to the deprecated Struts Configuration 1.1 DTD. The new DTD adds two new elements \<display-name\> and \<description\> to the struts-config element. These elements are for use by struts config file tools and document generation. In the Struts 1.2.x series, existing Struts configuration files can be loaded using either DTD version.

**New Taglib URIs** - The URIs for the tag libraries have been changed to reflect the move of Struts from Jakarta to an Apache top level project. For compatibility purposes, TLDs with the old URIs are still available, but users are encouraged to update their usage accordingly.

**New Committers** - We are pleased to welcome Steve Raeburn, Don Brown, Joe Germuska and Niall Pemberton to the team of Struts Committers.

**Struts-Chain** - Still experimental, this new "contrib" package utilizes the new Chain of Responsibilty package in the Jakarta Sandbox to create a new breed of RequestProcessor. Look for this to become the default implementation in a future release.

**MappingDispatchAction** - A new standard Action that dispatches to a method named by the ActionMapping parameter.

**Cancel handlers** - DispatchAction, LookupDispatchAction, and MappingDispatchAction - Now provide default cancel handler that can be overridden. It also also possible to specify the default handler name.

**Session-scoped ActionMessages** - You can now save ActionMessages in the session and have them cleaned up after the first use. There is now an alternate form of Action.saveMessages() that stores messages in the session. ActionMessages.isAccessed() returns true after the messages have been retrieved one time. RequestProcessor.processCachedMessages() queries isAccessed() to determine if it should remove the messages from the session.

**JA Mailreader** - The Struts Mailreader Example application now includes a Japanese resource file.

**Tiles EL** - The Tiles tags are now avaiable through the Struts EL taglib, which is based on JSTL.

**Wildcard Mappings** - You can now use wildcards in your action-mappings. For details see [Using Wildcards in ActionMappings](building_controller.html.md#action_mapping_wildcards) as well as the Struts Mailreader Example application.

**Action attributes** - An Action attribute has been added to the.html.md img tag, to match what's available on the html link tag now.

**Module attribute** - A new "module" attribute is available on the forward element as well as several of the core tags. This attribute allows you to specify another module by name (or "prefix") to create direct links between modules. The new module attribute is preferered to the `contextRelative` attribute and can often be used in lieu of a "SwitchAction".

### <span id="What_Changed"></span>What Changed?

This section highlights some of the changes that have taken place since the last release. Subscribers to the [struts-dev mailing list](../using.html.md#Lists) , receive reports of all changes as they are made.

**General Changes**

-   2004-09-02 - URI for Struts DTD changed to reflect move to an Apache top level project.

<!-- -->

-   2004-08-31 - Code changes to re-enable building with JDK 1.3.

<!-- -->

-   2003-03-14 - Move license on all source code files to ASL 2.0.

<!-- -->

-   2003-12-30 - Add inital STATUS LOG.

**Build Changes**

-   2004-07-09: struts.xsl: Give each "src" variable a distinct name to follow XSL rules.
-   2004-07-08: build.properties.sample.lib: Add a simplified build.properties file for use by developers who are not actively involved in Jakarta development. This template assumes the developer is using JARS from our "lib" distribution.

<!-- -->

-   2004-04-14 - project.properties: Adjust properties to use alternate repo for nightly builds.

<!-- -->

-   2003-08-09 - build.xml: Adjust loading order of properties files to go from most local (current directory) to most global (${user.home}/build.properties).
-   2003-08-08 - maven.xml,project.xml - Maven build files.

**Configuration Changes** [ `/conf/shared` ]

-   2003-08-09 - Add two new elements \<description-short%gt; and \<description-long\> for use by struts config file tools and document generation.

<!-- -->

-   2003-07-04 - struts-config\_1\_2.dtd: Added 1.2 struts-config.dtd. This is a copy of the 1.1 DTD except that the \<data-source\> "type" attribute is now required because Struts does not supply a default DataSource implementation.

**Project-wide Changes**

-   2004-01-14 - Update License format to please Maven Checkstyle reports.
-   2004-01-10 - Removed @author javadoc tags from all classes; updated volunteers.xml to list missing people.

**Default Package Changes** [ `org.apache.struts` ]

-   2003-07-04 - Globals: Removed deprecated APPLICATION\_KEY.
-   2003-07-03 - Globals,ActionServlet,RequestUtils: Moved initialization of module prefix list to the new ActionServlet.initModulePrefixes() method from RequestUtils.getModulePrefixes() because of a potential race condition documented in PR\# 21091. This also required a move of the RequestUtils.PREFIXES constant to Globals.MODULE\_PREFIXES\_KEY.

**Action Package Changes** [ `org.apache.struts.action` ]

-   2004-09-10 - Corrected Japanese translation of message resources.
-   2004-09-07 - Action: Use ActionMessages instead of ActionErrors.
-   2004-09-03 - ActionServlet: Eliminate performance bottleneck in obtaining request processor.
-   2004-09-03 - ActionForward: New copy constructor that takes module parameter; deprecate copy constructor missing this parameter.
-   2004-09-02 - Correct javadoc for ActionErrors.

<!-- -->

-   2004-08-10 - DynaActionForm: Change Map's key from String to Object in toString().

<!-- -->

-   2004-07-01 - TestDynaActionFormClass: Correct operation of static method calls.

<!-- -->

-   2004-06-26 - Action: Add getErrors, getMessages, addErrors, and AddMessages methods, to better manage error handling.

<!-- -->

-   2004-04-01 - ActionConfigMatcher: Added support for multiple wildcard replacements.

<!-- -->

-   2004-03-16 - ActionForward: Add "copy constructor".

<!-- -->

-   2004-01-24 - DynaActionForm: Enhance so that it can be initialized using a FormBeanConfig object. Add corresponding method to RequestUtils to create an ActionForm by passing only a FormBeanConfig and an ActionServlet object.
-   2004-01-19 - ActionMapping, ActionConfig: Push "findException" from ActionMapping up to ActionConfig so that everyone can take advantage of the superclass search logic.

<!-- -->

-   2003-09-29 - RequestProcessor,ActionMappingMatcher,WildcardHelper: Added optional wildcard support for action mappings.
-   2003-09-11 - Action,ActionMessages,RequestProcessor: Added ability to save ActionMessages in the session and have them cleaned up after the first use.

<!-- -->

-   2003-08-23 - Action: Deprecate saveErrors(HttpServletRequest, ActionErrors) in favor of saveErrors(HttpServletRequest, ActionMessages).
-   2003-08-23 - RequestProcessor: Replaced ActionErrors reference with ActionMessages.
-   2003-08-23 - ActionMessages, ActionErrors: Deprecated ActionErrors.GLOBAL\_ERROR in favor of ActionMessages.GLOBAL\_MESSAGE.
-   2003-08-16 - ExceptionHandler: Added storeException() method that takes an ActionMessage instead of ActionError.
-   2003-08-13 - ActionError: Deprecate ActionError in favor of ActionMessage
-   2003-08-08 - ActionServlet,ActionFormBeans,ActionForwards,ActionMappings.java v 1.13 : Removed references to ActionMappings, ActionFormBeans, and ActionForwards.

<!-- -->

-   2003-07-26 - Action: getLocale() now calls RequestUtils.getUserLocale() to prevent session creation.
-   2003-07-04 - Action,ActionException: Removed deprecated getResources() method.
-   2003-07-04 - Action: Removed deprecated perform() methods.
-   2003-07-03 - ActionServlet: Removed support for some of the deprecated servlet init parameters.
-   2003-07-03 - Globals,ActionServlet,RequestUtils: Moved initialization of module prefix list to the new ActionServlet.initModulePrefixes() method from RequestUtils.getModulePrefixes() because of a potential race condition documented in PR\# 21091. This also required a move of the RequestUtils.PREFIXES constant to Globals.MODULE\_PREFIXES\_KEY.
-   2003-07-02 - RequestProcessor: Deprecated log() methods in favor of commons-logging.
-   2003-07-02 - ActionSerlvet: Removed deprecated method.
-   2003-07-02 - ActionServlet: Removed references to deprecated ApplicationConfig class.
-   2003-07-02 - ActionServlet,NoOpAction: Removed deprecated ActionServlet debug level and logging methods.
-   2003-07-02 - RequestProcessor: Changed processRoles() to send a 403 Forbidden response if the role check fails. Also removed deprecated methods.
-   2003-07-01 - Action: Removed deprecated constants and toHex() method.

**Actions Package Changes** [ `org.apache.struts.actions` ]

-   2004-06-24 - RedeployableActionServlet: Provides support for WebLogi hot-deploy.

<!-- -->

-   2003-12-22 - DispatchAction: Add detection of recursive calls.

<!-- -->

-   2003-08-13 - DispatchAction,LookupDispatchAction: Add 'default' and a 'cancel' handlers to DispatchAction and LookupDispatchAction.
-   2003-08-12 - MappingDispatchAction: Addition of MappingDispatchAction that dispatches to a method named by the ActionMapping parameter.

<!-- -->

-   2003-07-11 - DispatchAction,ForwardAction,IncludeAction,SwitchAction: Throw exceptions from execute() method instead of sending a failure response to the client. This allows the exception handling mechanism to respond to the error gracefully.
-   2003-07-03 - LookupDispatchAction: Fixed synchronization problem (PR\# 21224). Also refactored some code into a new initLookupMap() method.

**Config Package** [ `org.apache.struts.config` ]

-   2004-07-31 - Enhance support for "lazy" dynabeans or POJO beans. "Lazy" DynaBeans will hopefully soon be released with Beanutils 1.7.0. These changes will make it easier to plug either a regular JavaBean or a "lazy" DynaBean into struts as an ActionForm. \* FormBeanConfig now sets up the properties of DynaBeans which use a MutableDynaClass. \* FormBeanConfig now handles POJO beans by wrapping the specified bean using WrapDynaBean and the new BeanValidatorForm. \* RequestUtils has been changed so that properties starting with "org.apache.struts" are not attempted to be populated in the ActionForm.

<!-- -->

-   2004-04-14 - ModuleConfig.java: Local, as well as global, ActionForwards now observe pluggable classes.
-   2004-04-08 - ModuleConfigImpl: Added a list to store ActionConfigs to ensure when enumerated, they are in the order in which they were added.

<!-- -->

-   2004-02-17 - Undeprecate and Restore the functionality for the 'type' attribute on form-beans and global-forwards elements in the config file.
-   2004-02-13 - Add module property to ForwardConfig to support direct cross-linking between modules.

<!-- -->

-   2004-01-10 - Changed WildcardHelper methods from statics to instance methods to allow subclasses to override and customize behavior. Changed WildcardHelper.match() to accept a generic Map parameter rather than HashMap.

<!-- -->

-   2003-08-08 - ConfigHelper,ConfigHelperInterface: Removed references to ActionMappings, ActionFormBeans, and ActionForwards.

<!-- -->

-   2003-07-27 - ConfigHelper: Deprecate methods() since they return objects that have been deprecated. The ModuleConfig object should be used to lookup these items.
-   2003-07-16 - ModuleConfigFactory: Catch only relevant exceptions instead of Throwable and made LOG final.
-   2003-07-04 - struts-config\_1\_2.dtd, ControllerConfig.java: Removed deprecated debug controller attribute.
-   2003-07-04 - ActionConfig: Removed deprecated perform() methods.
-   ApplicationConfig: removed in favor of ModuleConfig.

**Contrib Packages** [ `/contrib` ]

-   2004-06-29 - struts-chain: Wrap HttpServletRequest to ensure correct handling of URIs.

<!-- -->

-   2004-02-29 - struts-chain: Fix problem with large uploads being deleted if validation failed.

<!-- -->

-   2004-01-15 - struts-chain: Add Tiles support. Add null check for type, to support forward actions; also add commons loggging
-   2004-01-14 - struts-chain: Add support for 'unknown' actions.

<!-- -->

-   2004-07-07 - struts-faces: correct operation of \<s:base\> tag and add portlet specific version.
-   2004-03-08 - struts-faces: updated for JSF 1.0 final release.
-   2003-12-31 - struts-faces: Initial support for Tiles; partial "Tilesization" of example app; \*not\* ready for prime time but comments definately welcome.
-   2003-12-29 - struts-faces: Various updates regarding the JSF Final Draft and to prepare for Tiles support.
-   2003-12-17 - struts-jericho: Whiteboard directory for Struts-Jericho, a working proposal for Struts 2.x.

<!-- -->

-   2003-09-07 - strutsel.taglib.tiles: Addition of "tiles-el" library

<!-- -->

-   2004-08-10 - TilesUtilImpl: Remove "static" modifier from doInclude() method.

<!-- -->

-   2003-08-11 - struts-chain: Initial check-in of an experimental library that decomposes the Struts 1.1 request procoessor, using the newly checked in Commons Sandbox project called "chain" supporting the Chain of Responsibility pattern.
-   2003-08-10 - strutsel: Added action attribute added in base class
-   2003-08-10 - strutsel: Removed deprecated FormTag attributes: name, scope, type.
-   2003-08-10 - struts-legacy: Removed package (GenericDataSource and GenericConnection).

<!-- -->

-   2003-07-26 - strutsel: Updated tags to match recent attribute changes to tags in base library.

**Plugins Package** [ `org.apache.struts.plugins` ]

-   2003-08-07 - DigestingPlugIn.java: Added DigestingPlugIn.

**Taglib Package Changes** [ `org.apache.struts.taglib` ]

-   2004-06-26 - EmptyTag: Add support for arrays.

<!-- -->

-   2004-02-24 - createDynamicJavascript: Move test for null validator form inside "createDynamicJavascript" so that those who use the tag to generate static javascript don't get a JspException.

<!-- -->

-   2003-09-09 - TagUtils: Log error message when keys or bundles are missing.

<!-- -->

-   2003-08-23 - TagUtils: Deprecated getActionErrors() in favor of getActionMessages().
-   2003-08-16 - TagUtils: Replaced ActionError with ActionMessage.
-   2003-08-02 - LocalStrings.properties,TagUtils: Move message resources from util package.

<!-- -->

-   2003-07-26 - TagUtils,RequestUtils: Added TagUtils class for taglibs to use instead of RequestUtils. We should migrate any method in RequestUtils that takes a PageContext parameter and/or throws JspException. A clean separation will help keep RequestUtils smaller and allow the taglibs to be easily split off of the core Struts distribution.

**Bean Taglib Package Changes** [ `org.apache.struts.taglib.bean` ]

-   2004-01-14 - WriteTag: Use client locale when applying date format.
-   2004-01-01 - WriteTag: Add notes regarding discovering localized notations.

<!-- -->

-   2003-08-28 - IncludeTag: Rename setCookie to addCookie since it isn't a bean setter

<!-- -->

-   2003-07-13 - MessageTag: Simplified args[] creation, deprecated unused defaultLocale variable.

**HTML Taglib Package Changes** [ `org.apache.struts.taglib.html.md` ]:

-   2004-08-24 - ImgTag: Correct usage in a module environment.

<!-- -->

-   2004-07-21 - Add accept-charset attribute to the FormTag.
-   2004-07-01 - JavascriptValidatorTag - Correct naming of JS methods when multiple forms are used.

<!-- -->

-   2004-05-17 - OptionsCollectionTag,OptionsTag: Filter values as well as labels.

<!-- -->

-   2004-03-08 - JavascriptValidatorTag - Allow multiple forms to be on the same page by generating a unique variable name based on form name.

<!-- -->

-   2004-02-14 - Substitute "-" for "/" in JavaScript function name when form is subclass of ValidatorActionForm.
-   2004-02-07 - Add "module" attribute to IncludeTag, ImgTag, LinkTag, and RewriteTag, as well as to Forward. This permits a module to be referenced by name (or "prefix) for direct cross-linking between modules.
-   2004-02-04 - Run validator messages through a routine to escape quote marks so that the emitted JavaScript is syntactically correct.
-   2004-02-04 - Throw JspException when no form is found in the ValidatorResources under the specified 'name'.

<!-- -->

-   2004-01-18 - Add "action" attribute to img tag.
-   2004-01-09 - Add disabled element to TLD.
-   2004-01-03 - Add 10 new tests that cover "some" of the functionality provided by.html.md:options. More to come.
-   2004-01-01 - In link-related tags, allow LocalCharacterEncoding to be specified conditionally.

<!-- -->

-   2003-11-28 - JavascriptValidatorTag - Removed getNextVar() and replaceChar() methods and use a simpler javascript identifier naming scheme. All variables with be named a0, a1, etc. to prevent using reserved words as variable names.

<!-- -->

-   2003-08-19 - Remove "request scope" references from messages tag. The messages are searched for in all scopes.
-   2003-08-10 - struts.html.md.xml,RewriteTag.java: Added action attribute to rewrite tag.
-   2003-08-10 - Removed deprecated FormTag attributes: name, scope, type.

<!-- -->

-   2003-07-08 - struts.html.md.xml,FormTag,JavascriptValidatorTag: Added scriptLanguage property to the form and javascript tags for PR\# 17234. This property is ignored in XHTML mode but allows developers to turn off the "language" attribute of \<script\> tags in HTML.
-   2003-07-03 - FormTag: Added disabled check to focus JavaScript
-   2003-07-02 - HtmlTag: Removed deprecated method.
-   2003-07-02 - BaseHandlerTag: Use RequestUtils.is.html.md() instead of duplicating logic.
-   2003-07-02 - ErrorsTag: Don't render new lines

**Logic Taglib Package Changes** [ `org.apache.struts.taglib.logic` ]:

-   2004-01-16 - logic:redirect - Add action attribute.

<!-- -->

-   2003-07-31 - PresentTag,RedirectTag: Replace depricated method calls with non-deprecated ones.

**Nested Taglib Package Changes** [ `org.apache.struts.taglib.nested` ]:

-   2004-03-22 - Add missing filter attribute to nested:options and nested:optionsCollection.

<!-- -->

-   2004-01-01 - Correct operation of NestedMessage\* tags by implementing NestedPropertySupport rather than NestedNameSupport.

<!-- -->

-   2003-08-10 - Removed deprecated FormTag attributes: name, scope, type.

<!-- -->

-   2003-07-03 - struts-nested.xml: Added styleId to nested:hidden

**Tiles Taglib Package Changes** [ `org.apache.struts.taglib.tiles` ]:

-   2004-05-17 - PutTag: Manage tag body content more carefully to ensure pooled tags do not display old content with empty tiles.

<!-- -->

-   2003-09-07 - ImportAttributeTag,UseAttributeTag: Removing "final" from class declaration, to allow class to be extended in "tiles-el" (or other classes).

<!-- -->

-   2003-07-27 - xmlDefinition/XmlParser: Remove deprecated/non functional digester logging method.
-   2003-07-10 - TagUtils: Deprecated getProperty() because it provided no value over calling PropertyUtils.getProperty() directly.
-   2003-07-08 - TilesServlet,ActionComponentServlet: Formatted code, removed deprecated constant.
-   2003-07-04 - ActionController: Call Action.execute() instead of perform().

**Tiles Package Changes** [ `org.apache.struts.tiles` ]:

-   2003-09-13 - Controller: Added execute() method to Tiles Controller interface.

<!-- -->

-   2003-08-16 - portal.UserMenuAction: Replaced hardcoded debugging with commons logging.

<!-- -->

-   2003-07-31 - xmlDefinition/I18nFactorySet: Replace deprecated constant reference with it's base interface equal.
-   2003-07-31 - actions/DefinitionDispatcherAction: Replace deprecated method with current one. Still one method DefinitionUtil.setActionDefinition that doesn't have a replacement. It's a simple method but I don't know where a good place to move it would be.
-   2003-07-31 - actions/ReloadDefinitionsAction: Use TilesUtil.createDefinitionsFactory(request,context) instead of deprecated method().
-   2003-07-21 - struts-\*config.xml: Remove the use of the deprecated action NoOpAction. Replace by ForwardAction.
-   2003-07-21 - \*Action: Replace the deprecated perform(..) method by the new execute(...) method.
-   2003-07-12 - DefinitionDispatcherAction: Use commons-logging to record error messages instead of printing them to the response.
-   2003-07-10 - TilesAction: Removed deprecated perform() method.
-   2003-07-09 - Removed deprecated TilesUtil.applicationClass() method.
-   2003-07-08 - DefinitionsUtil.java: Deprecated debug level constants, removed some deprecated methods.
-   2003-07-08 - ChannelFactorySet: Use commons-logging instead of printing to stdout.
-   2003-07-07 - InsertTag: Fixed exception handling. Instead of swallowing exceptions or printing the stack trace on the page, the exceptions are logged and rethrown as JspException for the page error handling mechanism to deal with.
-   2003-07-07 - InsertTag: More code cleanup, removed deprecated method, deprecated ROLE\_DELIMITER because it is only used internally to this class
-   2003-07-04 - ComponentContext: Removed deprecated constructor
-   2003-07-02 - Changed UntyppedAttribute class name to UntypedAttribute (spelling error).

**Upload Package Changes** [ `org.apache.struts.upload` ]:

-   2004-04-08 - CommonsMultipartRequestHandler: Made CommonsFormFile serializable since it gets put into the session

<!-- -->

-   2004-03-22 - Allow MultipartPost with latin1 characters over Linux.

<!-- -->

-   2004-01-21 - Add support for an "EncodingFilter" to handle multibyte file names.

<!-- -->

-   2003-11-26 - DiskMultipartRequestHandler: Deprecate DiskMultipartRequestHandler and friends, which is the buggy old upload implementation, no longer used as the default as of Struts 1.1. This will be removed after 1.2 (meaning as of 1.3/2.0).

<!-- -->

-   2003-07-31 - MultipartElement: Remove deprecated methods.

**Utility Package Changes** [ `org.apache.struts.util` ]:

-   2004-07-21 - ModuleUtil: Add module support to the bundle attribute. 2004-07-07 - TokenProcessor: Ensure that tokens returned differ even if called quickly by tracking last value used.

<!-- -->

-   2004-04-08 - RequestUtils: Fixed inappropriate serialization of ModuleConfig when a DynaActionForm was put in the session.

<!-- -->

-   2003-09-22 - LabelValueBean: Implement Comparable interface.

<!-- -->

-   2003-08-16 - ModuleException: Added getActionMessage() to replace the getError() method.
-   2003-08-02 - LocalStrings.properties: Move message resources to taglib TagUtil package.
-   2003-08-02 - ModuleUtils.java,RequestUtils.java: Moved module related methods to new ModuleUtils class.

<!-- -->

-   2003-07-26 - TagUtils,RequestUtils: Added TagUtils class for taglibs to use instead of RequestUtils. We should migrate any method in RequestUtils that takes a PageContext parameter and/or throws JspException. A clean separation will help keep RequestUtils smaller and allow the taglibs to be easily split off of the core Struts distribution.
-   2003-07-25 - RequestUtils: Backwards compatibility fix. Changed ModuleConfig lookups to use getModuleConfig so that default module config is returned if one is not already present in the request
-   2003-07-16 - RequestUtils: Make retrieveMessageResources() module-aware by adding the module prefix to the bundle name when retrieving from application context.
-   2003-07-03 - LabelValueBean: Added equals and hashCode() methods.
-   2003-07-03 - Globals,ActionServlet,RequestUtils: Moved initialization of module prefix list to the new ActionServlet.initModulePrefixes() method from RequestUtils.getModulePrefixes() because of a potential race condition documented in PR\# 21091. This also required a move of the RequestUtils.PREFIXES constant to Globals.MODULE\_PREFIXES\_KEY.
-   2003-07-02 - RequestUtils,TestRequestUtils: Removed deprecated "application" methods in favor of "module" methods.
-   2003-07-02 - LabelValueBean: Added default constructor.

**Validator Package Changes** [ `org.apache.struts.validator` ]

-   2004-09-03 - ValidWhen: Added new test cases.
-   2004-09-03 - ValidWhen: Correct parsing of integer values.

<!-- -->

-   2004-06-24 - ValidWhen: "allow '\_' (underscore) in identifiers.

<!-- -->

-   2004-04-16 - FieldChecks: Add optional variables to configure various aspects of URL validation.
-   2004-04-03 - ValidatorPlugIn: Modify Validator PlugIn to validate XML file and errros now throw an exception to loudly flag an error. Remove deprecated classes, now in Commons Validator.
-   2004-04-02 - Add a getValidationKey method to make it eaiser for subclasses to use different rules for finding the Validator form.

<!-- -->

-   2004-02-20 - Changed FieldCheck so that it examines all indexed fields and does not stop on the first failure.

<!-- -->

-   2004-01-17 - Changed initValidator() to accept an ActionMessages object instead of ActionErrors; changed ACTION\_ERRORS\_PARAM name to ACTION\_MESSAGES\_PARAM.
-   2004-01-17 - Add section to Validator User Guide listing standard validations.

<!-- -->

-   2003-12-21 - Add rest of form to fr.CA formset to correct operation; Use action form of.html.md:link;

<!-- -->

-   2003-10-06 - FieldChecks - Add validateUrl. Remove deprecated validateRange.

<!-- -->

-   2003-09-26 - FieldChecks,ValidWhen: Changed validator signatures to use ActionMessages rather than ActionErrors, was breaking validations.
-   2003-09-26 - validator-rules.xml: Modify JavaScript to honor datePattern option.
-   2003-09-24 - validator-rules.xml: Add ability of required to handle checkboxes, radio,select-one, and select-multiple field types.

<!-- -->

-   2003-07-30 - validator-rules.xml: Remove deprecated range() method. Use intRange() instead.
-   2003-07-30 - validator-rules.xml: Allow intRange validation of select-one and radio fields. In some form combo boxes you might have the combo boxes populated with valid choices plus one additional choice with a caption something like "Choose one" and a value 0f "-1". Then when the user attempts to submit the form, you can look for the value of "-1" and yell at them if they failed to pick something.
-   2003-07-28 - JavascriptValidatorTag.java,ValidatorPlugIn.java: Enhancement to allow checking of all constraints instead of aborting. The default is same as struts 1.1.
-   2003-07-26 - Resources: Deprecated Resources.getLocale() because it created sessions. Use RequestUtils.getUserLocale() instead.
-   2003-07-02 - Resources: Rewrote getArgs() method to use arrays and loops, which removes limitation of 4 args.
-   2003-07-02 - Resources: Remove deprecated methods
-   2003-07-02 - Validator,ValdiatorUtils: Changed processRoles() to send a 403 Forbidden response if the role check fails. Also removed deprecated methods.
-   2003-07-01 - Add validwhen validation to package.

**Documentation Application Changes** [ `struts-documentation.war` ]:

-   2004-08-31 - Added a Struts download page, reflecting the move to an Apache top level project.
-   2004-08-24 - Fix build script errors on Eclipse HOW-TO page.

<!-- -->

-   2004-07-11 - Add links to development releases.
-   2004-07-07 - Rename "status.xml" to "roadmap.xml" to avoid confusion with STATUS.txt file.
-   2004-07-07 - Extend prior draft of bylaws page with additional material from Jakarta site and link to main menu.

<!-- -->

-   2004-03-28 - Added Trifork server to Installing Struts on Various Containers section.
-   2004-03-24 - Document new exception-throwing behavior in.html.md:javascript when dynamicJavascript is true but no form can be identified.

<!-- -->

-   2003-11-27 - resource: Move resource area to [Struts SourceForge site](http://struts.sf.net/) .

**MailReader Example Application Changes** [ `struts-example.war` ]:

-   2004-03-07 - Various refactorings to JSP pages, welcome and login action.

<!-- -->

-   2004-01-08 - Use (new) DigestingPlugIn to create the menu of server types.

<!-- -->

-   2003-12-21 - Change to use typical welcome.do - welcome.jsp approach; Use "name" rather than "attribute" in configuration, per documented and common practice; Use action form of.html.md:link
-   2003-10-25 - Updated to include the usage of wildcards in action mappings.

<!-- -->

-   2003-08-30 - AlternateApplicationResources\_ja.properties,ApplicationResources\_ja.properties: Provide Japanese resources.
-   2003-08-16 - Changed ActionError to ActionMessage.

**Combined Examples Application** [ `struts-examples.war` ]

-   2004-09-07 - Fix problems with running the application while not connected to the internet.
-   2004-09-03 - Change Commons Validator DTD to version 1.1.3.

<!-- -->

-   2004-01-17 - Add tests to to hmlt:link page for forwards, actions, and pages.
-   2004-01-16 - exercises: Add test pages for.html.md:img and logic:forward,redirect. Add test pages for html:img and logic:forward,redirect tags
-   2004-01-08 - Convert Taglib-Exercises, Upload, and Validator example applications into modules of a combined examples application.

**Exercise module Changes** :

-   2004-01-09 - Enable inputForward.
-   2004-01-01 - Add several tests to bean:write: localized numbers; date format pattern; localization.

<!-- -->

-   2003-07-23 -.html.md-messages.jsp: Updated to reference Globals constants.

**Upload Example module Changes**

-   2004-01-09 - Enable inputForward; use message tags for validation errors; refine markup on display page.
-   2004-01-08 - Convert to Upload example application to module under the "examples" application.

<!-- -->

-   2003-08-16 - Changed ActionError to ActionMessage.

**Validator Example module Changes**

-   2004-06-25 - Update arg elements to use new dynamic feature, that does not requiring numbering.

<!-- -->

-   2004-03-25 - Modify example to test proper behaviour is a property is named 'name'.

<!-- -->

-   2004-01-09 - Enable inputForward.
-   2004-01-08 - Convert to Validator Example application to module under the "examples" application.

<!-- -->

-   2003-12-21 - Add rest of form to fr.CA formset to correct operation.
-   2003-09-24 - Modify Validator example to show use of 'required' for checkboxes, radio,select-one, and select-multiple field types.

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


