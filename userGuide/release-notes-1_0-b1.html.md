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

<span id="Introduction"></span>Introduction
-------------------------------------------

This document contains the release notes for **Version 1.0-beta-1** of the Struts Framework. The following sections cover [New Features](#New) and [Changes](#Changes) since the **Version 0.5** of Struts was made available.

One global new feature to take note of is that Struts 1.0 requires a Java2 (JDK 1.2 or later) platform on which to run.

<span id="Whats_New"></span>What's New?
---------------------------------------

The following major new features have been added to the controller servlet and associated classes (package `org.apache.struts.action` ):

-   A new configuration file format, including the [Document Type Definition (DTD)](../../dtds/struts-config_1_0.dtd) it is based on, is available for configuring the Struts controller servlet. Support for the previous format is still present, but will be phased out by the 1.0 release.
-   If enabled by setting the `locale` servlet initialization parameter to `true` , the controller servlet will now calculate a Locale for this user (based on the Locale returned by the servlet container, or by the HTTP headers included with the request) and store it in the user's session, unless the application has stored one there already.
-   Application `Action` instances now have lifecycle support. The controller servlet will call `setServlet()` with a non-null argument when the instance is first created, and call it with a `null` argument when the instance is being shut down.
-   The collection of "standard" Struts actions (in package `org.apache.struts.actions` ) is kicked off with a set of simple actions that allow on-the-fly changes in the form bean, forward, and mapping definitions registered with the controller servlet. These actions would normally be configured behind security constraints to prevent interference with the operation of your application but can be very useful during development.
-   A new representation of error messages ( `ActionError` and `ActionErrors` ) has been created that allows errors to be associated with individual fields, and stores parameter replacement values along with the messages keys.
-   The `ActionForm` interface has been converted to a base class, with default implementations of some useful functionality. In addition, the new class provides two `validate()` methods that take the current mapping and current request as arguments, in order to provide access to more context information than just the properties of this particular form bean.
-   The new `ActionForm` class also provides two `reset()` methods that take the current mapping and current request as arguments, in order to provide access to more context information (particularly important on multi-page forms so that the form bean knows which properties to reset). Among other things, use of the `reset()` methods can prevent problems with checkbox fields -- simply reset boolean fields to `false` and they will be set to `true` (during auto-population of the form bean properties) only if the checkbox was actually checked.
-   All servlet context attributes created by the Struts controller servlet itself (but not the Struts Example application) now implement `java.io.Serializable` .
-   The `Action` class now includes support for "transactional tokens", so that you can detect cases where the user submitted a form, then went back and resubmitted the form again.

The following major new features have been added to the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ):

-   A new custom tag, `<bean:page>` , is available to expose key items from the page context associated with the current page as scripting variables, and as page-scope beans. For example, you can use the following sequence to render the server information string returned by our servlet context:

                                <bean:page id="app" property="application"/>
                                <bean:write name="app" property="serverInfo"/>
                            

-   A new custom tag, `<bean:struts>` , is available to expose internal Struts configuration objects (form bean, forward, and mapping definitions) as scripting variables and page-scope beans. For example, you can use the following sequence to render the actual context-relative path of an `ActionForward` object:

                                <bean:struts id="link" forward="success"/>
                                <bean:write name="link" property="path"/>
                            

-   All of the tags in this library that accept a `name` attribute referring to a JSP bean now also accept an optional `scope` attribute to define the scope in which to search for that bean. If not specified, all scopes are searched.
-   The `<bean:size>` tag will create a bean that stores the number of elements of an array, Collection, or Map.

The *struts.html.md* custom tag library has been created (package `org.apache.struts.taglib.html` ), based on the old tags that were related to HTML form presentation. The following differences from the old tags are notable:

-   You must now reference the "struts.html.md.tld" TLD to access these tags.
-   All attribute names matching JavaScript event handlers are now all lower case (onClick --\> onclick) to conform to XHTML.
-   The `options1` tag has been eliminated since Struts is now based on Java2.
-   All tag implementation classes have had their `final` modifiers removed, and `private` instance variables changed to `protected` . This makes it possible to easily subclass these tags to provide specialized functionality.
-   The `.html.md:link>` tag has been enhanced to support a new `page` attribute that allows you to use context-relative URIs in a portable manner.
-   A new `.html.md:html>` tag has been created that renders an HTML `<html>` element with appropriate `lang` and `xml:lang` attributes, based on the locale stored for the user's session (if there is one).
-   A new `<rewrite>` tag has been created that renders a request URI, possibly encoded with a session identifier, based on exactly the same rules used by the `<link>` tag that generates hyperlinks. These constants can be useful when you are creating JavaScript code that needs to be aware of Struts addressing concepts.
-   The `options` tag now supports a new `collection` attribute, which can be used to specify a collection whose beans have properties that return the value (to be returned to the server) and the label (to be displayed to the user) from a single collection. The previous support for processing parallel collections is still available.
-   The `form` tag has been enhanced to look up the name of the form bean, it's Java class, and the scope in which the bean should be created or accessed, from the corresponding action mapping entry in the "struts-config.xml" file, if the `name` , `scope` , and `type` attributes are not specified. This removes the need to make changes in two places when these values are changed.
-   A new `<image>` tag has been added, to create HTML input tags of type "image".
-   The `form` tag has been enhanced to read its configuration from a corresponding action mapping entry in the "struts-config.xml" file, if the `name` , `scope` , and `type` attributes are not specified. It can look up the name of the form bean, its Java class, the scope in which the bean should be created or accessed, plus the path to which the form should be submitted. This removes the need to make changes in two places when these values are changed. It works for cases where the controller servlet is extension mapped or path mapped.
-   The `.html.md:img>` tag has been added, to render an HTML `<img>` tag.

A new package of Actions and associated classes for handling file uploads has been created (package `org.apache.struts.upload` ):

-   The basic package of file upload handling actions has been created.
-   An example application illustrating the use of the new features has been added ( `webapps/struts-upload.war` ).

The following major new features have been added to the utility classes library (package `org.apache.struts.util` ):

-   Initial implementation of a JDBC data source that implements the `javax.sql.DataSource` interface from the JDBC 2.0 Standard Extensions API. This implementation may be configured based on new extensions to the Struts configuration file DTD, and the configured data sources / connection pools are made available to application components as a servlet context attribute (i.e. an application scope bean).
-   The previous implementation of `MessageResources` , which was ultimately based on `java.util.ResourceBundle` , has been completely replaced and re-implemented. The primary features of the new implementation are:
    -   All components stored as servlet context attributes now implement the `java.io.Serializable` interface, to better integrate with application servers that prefer this.
    -   The `MessageResources` and `MessageResourcesFactory` classes have been abstracted so that you can easily create your own implementations that derive their message strings from resources other than property files.
-   Property gets and sets made through `PropertyUtils` can now use a new syntax for indexed and nested properties.
-   Conversion to and from numeric types now support a configurable default value to use when conversion fails.

The following major new features have been added to the *Struts Example Application* :

-   The form beans used in the example application now use request scope rather than session scope. This is the preferred approach for single page forms that contain *all* of your relevant properties, because there is no need to maintain such form beans across requests. Note that the action classes have been coded so that they work with either request scope or session scope beans.
-   The Struts Example Application has been updated to utilize the new (separated) custom tag libraries, rather than the old combined one, as well as the latest features of the tags being used.
-   A "Walking Tour of the Struts Example Application" has been added, to highlight features for newcomers to Struts.

The following major new documentation updates have been added to Struts:

-   All documentation is generated from XML input files, using a standard stylesheet to create a common look and feel.
-   Developer Guides for the Java classes in the `org.apache.struts.digester` and `org.apache.struts.util` packages.
-   Developer Guides for the following Struts custom tag libraries have been added: `struts-bean` , `struts.html.md` , `struts-logic` , and `struts-template` .
-   The Struts Users Guide has been brought up to date with respect to all of the changes since Struts 0.5, and separated into multiple HTML pages for easy reading.
-   Installation information has been updated to include platform-specific notes, issues, and workarounds.
-   A new resources page now points at external information and resources related to Struts.
-   A new example application, `struts-blank` , is included as a quick starting point for new application development.

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes to the controller servlet and associated classes (package `org.apache.struts.action` ) have occurred:

-   The `ActionMapping` interface has been converted to a base class instead, to reduce the impact of future enhancements. Anyone who has extended the `ActionMappingBase` convenience base class (which has been deprecated) should extend `ActionMapping` instead.
-   In conjunction with the new configuration file format mentioned above, the properties of `ActionMapping` have been substantially updated. See the ActionMapping API Documentation for more information
-   The `Action` interface has been converted to a base class instead, to reduce the impact of future enhancements. Anyone who has extended the `ActionBase` convenience base class (which has been deprecated) should extend `Action` instead.
-   In conjunction with the above change, the `servlet` argument has been removed from the parameter list for the `perform()` method, because it is now redundant -- the associated servlet is set via the `setServlet()` method when the `Action` instance is first created.
-   Responsibility for creating `Action` instances has been moved from `ActionMapping` to the controller servlet, so that instance lifecycle management can be performed. As a side effect of this change, if you had two actions that used the same Action class name, there will now be only one (shared) instance of the Action class, rather than two.
-   New `log(String, int)` method that logs the associated message only if you have configured the debugging detail level for the servlet to an equal or higher value.
-   In `ActionServlet` , the functionality to populate form bean parameters from a request, and the functionality to validate the form bean's contents, has been separated into two methods that can be overridden individually if required.
-   The `ActionServlet` functionality to call the `validate()` method of a form bean is skipped if the user pressed the Cancel key (i.e. the submit button created by the `.html.md:cancel>` custom tag), or if the selected mapping does not define an input form to return control to.
-   The controller servlet may now be used as the target of a `RequestDispatcher.include()` or `<jsp:include/>` call. Previously, it would mistakenly use the original request URI, rather than the included path, to calculate which action class to execute.
-   The `ActionMappings.getUnknown()` method now takes the current request as an parameter, so that context-sensitive decisions can be made.
-   When the controller servlet processes an `ActionForward` that has the `redirect` property set, it now performs URL rewriting to maintain session state even if cookies are not being used.
-   The `ActionErrors` class now includes a method that will return an Iterator over the error messages related to a particular input field.

The following changes and bug fixes to the Digester module (package `org.apache.struts.digester` ) have occurred:

-   The `Digester.resolveEntity()` method has been enhanced to correctly handle local URIs so that it works with resources loaded via `Class.getResource()` .
-   The input source handed to the Digester is now closed, even if a parsing exception is throw.

The following changes and bug fixes to the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ) have occurred:

-   By default, the `<bean:write>` tag will filter output for characters sensitive to HTML. You can turn this off by adding a `filter="false"` attribute.
-   When performing a `<bean:include>` in a page that is part of a session, pass the session identifier along on the generated request so that it will be part of the same session.
-   The `<bean:define>` tag can now create beans directly from the `value` attribute, if desired.
-   The `<bean:define>` tag now accepts an optional `toScope` attribute, to declare which scope the new bean should be created in. The default remains `page` scope.
-   Default values can now be specified on `<bean:cookie>` , `<bean:header>` , and `<bean:parameter>` tags, which are used when the corresponding value is not present in the current request.

The following changes and bug fixes to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ) have occurred:

-   **WARNING** - When the Struts 0.5 tag library was originally split into separate libraries, this library was named *struts-form* , to reflect the fact that the majority of tags related to creating input forms. It has been renamed to *struts.html.md* to reflect the fact that all of the tags in this library are relevant only when building HTML-based user interfaces.
-   The `.html.md:html>` tag now supports a `locale="true"` attribute that requests the same Locale negotiation (based on the presence of an `Accept-Language` header) that is performed by the controller servlet.
-   The `.html.md:link>` tag now supports the ability to add a single request parameter (based on a bean property) in addition to the ability to add request parameters from a Map.
-   The `.html.md:errors>` tag lets you select only the error messages related to a particular input field, or all errors.
-   The `.html.md:password>` tag now optionally redisplays the previous value of the input field.
-   The value returned by a `.html.md:multibox>` tag can now be specified in the body of the tag, as well as via the `value` attribute.

The following changes and bug fixes to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ) have occurred:

-   The `<logic:present>` and `<logic:notPresent>` tags now accept a `role` attribute that allows you to detect whether the currently authenticated user does, or does not, possess a particular security role.

The following changes and bug fixes to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ) have occurred:

-   The `<template:put>` tag now accepts a `direct` attribute that causes the content being put to be rendered directly, rather than being included.

The following changes and bug fixes to the Utilities package (package `org.apache.struts.util` ) have occurred:

-   Fixed `PropertyUtils.getPropertyType()` to correctly return the underlying element type even if there was a non-indexed property getter method.
-   Added a missing "return" statement to `PropertyUtils.setIndexedProperty()` .
-   Functionality in `BeanUtils` that previously duplicated functionality that was earlier moved to `PropertyUtils` has been removed.
-   Fixed `PropertyUtils.copyProperties()` to skip cases where the origin bean has a getter method but the destination bean does not have a setter method.
-   Added `BeanUtils.cloneBean()` to create a new instance of an existing bean, and copy all known properties, even if the bean class does not implement `Cloneable` .
-   The `BeanUtils` class has been refactored so that it, and the associated `ConvertUtils` and `PropertyUtils` classes, can easily be used without having to have the servlet API classes available on the classpath.
-   Property introspection is now smarter, so that you can access public methods declared in an implemented interface, even if the class itself is not public.

The following changes and bug fixes to the Struts Example Application (package `org.apache.struts.example` and the corresponding web components) have occurred:

-   Used the `reset()` methods defined by the `ActionForm` interface to reset form bean properties to default values. This is particularly important to make boolean properties (represented visually by checkboxes) work correctly.
-   Eliminate the special-case handling of null String values in the form beans. Such handling is not necessary because the custom tags correctly deal with null String values.
-   Use the `PropertyUtils.copyProperties()` method to initially populate form beans from underlying data objects, and to update date objects when a transaction is successfully completed. Note that using this approach dramatically lessens an action class's dependence on the specific properties of the form bean and corresponding data object in many use cases.
-   Added an `autoConnect` boolean property to the Subscription data object, primarily to illustrate that representing a boolean property with a checkbox now works correctly if you set the property to `false` in the `reset()` method of your form beans.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


