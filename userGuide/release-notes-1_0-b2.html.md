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

This document contains the release notes for **Version 1.0-beta-2** of the Struts Framework, and covers changes that have taken place since [Version 1.0-beta-1](release-notes-1_0-b1.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

<span id="Whats_Included"></span>What's Included?
-------------------------------------------------

The binary distribution of this release includes the following files relevant to Struts 1.0:

-   `INSTALL` - Brief installation instructions. See the `Struts Documentation Application` , or online at <http://jakarta.apache.org/struts/> for more information.
-   `LICENSE` - The Apache Software Foundation license that defines the terms under which you can use Struts (and other software licensed by Apache).
-   `README` - A brief introduction to Struts.
-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `struts.jar` - JAR file that contains the compiled Java classes for both version 0.5 and 1.0 of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts-xxxxx.tld` - The tag library descriptor files for the Struts 1.0 tag libraries (bean,.html.md, logic, and template). You must place these files in the `/WEB-INF` directory of your web application, and reference them with appropriate `<taglib>` directives in your web.xml file. **NOTE** - The struts-form.tld file is deprecated; you should use the struts-html.tld file instead.
    -   `jdbc2_0-stdext.jar` - The JDBC 2.0 Optional Package API classes (package `javax.sql` ). You will need to include this file in the `/WEB-INF/lib` directory of your application, if it is not already made visible to web applications by your servlet container.
    -   `struts-config_1_0.dtd` - The document type descriptor (DTD) for the Struts configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `web-app_2_2.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.2 specification. This copy is for reference purposes only.
    -   `web-app_2_3.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.3 specification. This copy is for reference purposes only.
-   `webapps/` - Web Application Archive (WAR) files for the web applications that are included with Struts.

For backwards compatibility only, the binary distribution also includes the following files that conform to the Struts 0.5 milestone release APIs. Usage of these files and APIs is deprecated, and they will be removed from releases after Struts 1.0:

-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `struts.jar` - JAR file that contains the compiled Java classes for both version 0.5 and 1.0 of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts.tld` - The tag library descriptor file for the 0.5 version of the Struts tags. You must place this file in the `/WEB-INF` directory of your web application, and reference it with appropriate `<taglib>` directives in your web.xml file.

<span id="Whats_New"></span>What's New?
---------------------------------------

**DEPRECATIONS** - The entire custom tag library that is documented in `struts.tld` has been deprecated. These tags correspond to the Struts 0.5 functionality that is also deprecated, and have been replaced (and considerably enhanced) in the various individual tag libraries.

The build procedure for compiling the Struts source distribution has been revised, and now depends on having **Ant 1.2** (or later) installed, with the `$ANT_HOME/bin` directory on your path. Further information can be found in the [Installation](installation.html.md) documentation.

The following new features have been added to the basic controller framework (package `org.apache.struts.action` ):

-   You can now specify that an `<action>` element should invoke an existing servlet or JSP page resource, rather than calling an `Action` class, by using the `include` attribute rather than the `type` attribute. The standard form bean processing provided by the controller is still performed first, if you have configured it, so the included resource can benefit from this processing if it wishes to.
-   The `initDataSources()` method can now throw a `ServletException` to report that an initialization error has occurred. Previously, such errors were logged but otherwise ignored.
-   It is now possible to integrate business logic that is already encapsulated as a servlet or JSP page, via use of two new standard actions: `org.apache.struts.actions.ForwardAction` and `org.apache.struts.actions.IncludeAction` . These actions let you take advantage of the standard processing performed by the controller servlet (including form bean population and calling the `validate()` method), but not have to write Java code to perform (or wrap) the required business logic.
-   A wrapper class has been added around the standard `HttpServletRequest` for handling multipart requests as identically as possible to standard requests, including processing request parameters, populating form beans, transaction tokens, and checking for cancellations.

The following new features have been added to the utility classes (package `org.apache.struts.util` ):

-   `PropertyUtils` can now correctly locate public methods defined in a nested interface that is implemented by a bean.
-   `PropertyUtils` methods now throw `IllegalArgumentException` when you pass a null `bean` reference or property `name` .
-   **DEPRECATIONS** - The following classes have been deprecated in their entirety, because they will be replaced by corresponding classes (with identical functionality) from the [Jakarta Commons Project](http://jakarta.apache.org/commons) at some point after Struts 1.0 final release. The only change that will ultimately be required in user code is to change the package names on the `import` clauses:
    -   `org.apache.struts.util.FastArrayList`
    -   `org.apache.struts.util.FastHashMap`
    -   `org.apache.struts.util.FastTreeMap`
    -   `org.apache.struts.util.BeanUtils`
    -   `org.apache.struts.util.ConvertUtils`
    -   `org.apache.struts.util.PropertyUtils`

The following new features have been added to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   The `.html.md:link>` tag now accepts an optional `anchor` attribute, to allow the inclusion of a (possibly calculated) anchor ("\#xxx") in the generated hyperlink.
-   The `.html.md:base>` tag now accepts an optional `target` attribute.
-   The `.html.md:image>` tag now accepts an optional `border` attribute, to define the border with around this image.
-   You can now request that the `.html.md:link>` tag include any current transaction control token in the generated hyperlink, by specifying the `transaction` attribute with a value of `true` .
-   The `.html.md:options>` tag now supports Enumeration for the `collection` property.
-   The `.html.md:form>` tag now creates attributes for the tag itself, and the form bean, in request scope instead of page scope. Among other benefits, this allows you to nest the fields of a form inside a separate page that is accessed via a template or a `<jsp:include>` tag.
-   The `styleId` attribute has been added to all of the tags where the corresponding `id` tag is relevant, to identify a specific tag for the purposes of stylesheet references.
-   The `.html.md:file>` tag now supports the `size` attribute to set the size of the file list field.

The following new features have been added to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   The `<logic:iterate>` tag now supports Enumeration for the `collection` property.
-   The `<logic:iterate>` tag now exposes the current iteration index to nested tags, through a call to the `getIndex()` method.

The following new features have been added to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ):

-   Attribute getter methods have been added to all of the custom tag implementation classes to facilitate reuse.
-   The `<template:get>` tag now has an optional "flush" attribute that causes the response to be committed prior to performing the include, if set to "true". This allows working around problems on broken servlet containers.

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

-   Platform specific installation notes for a wide variety of application server and servlet container environments have been accumulated and published.

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

-   `DiskMultipartRequestHandler` now tries to retrieve the temporary directory provided by the servlet container before all other possible temporary directories.

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   The `computeURL()` method now returns a `MalformedURLException` if a URL cannot be created. Previously, this case returned `null` with no error message, making some problems difficult to track down.

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   The `.html.md:image>` tag now correctly generates a closing double quote on the `name` attribute.
-   The `.html.md:form>` tag now generates a hyperlink that includes any query parameters that were included in the original hyperlink value.
-   The `.html.md:link>` tag now correctly places any specified anchor ("\#xxx") in the generated hyperlink.
-   The JavaScript code generated to implement the `focus` attribute of the `.html.md:form>` tag now works even when you use nested or indexed property expressions. Previously, this would generate an invalid JavaScript reference to the field.
-   The `.html.md:checkbox>` tag now conforms to its documentation, and sends the specified `value` to the server if this checkbox is checked at submit time. In addition, a default value of `on` is sent if no value attribute is specified.
-   The hyperlinks created by the `.html.md:link>` and `<html:redirect>` tags now properly omit the port number if it is the default port for the current request scheme (80 for http, or 443 for https). Among other things, this corrects session management behavior on the standard port numbers.
-   The `focus` attribute of the `.html.md:form>` tag now works when the corresponding input field is a radio button, or is otherwise indexed.
-   The `disabled` and `readonly` attributes have been added to all HTML-rendering tags where they are relevant.

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   Hyperlink processing in the `<logic:forward>` tag is now identical to that performed by the Struts Controller Servlet when it processes an `ActionForward` that is returned by an `Action` .

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   The Java types of collections (and arrays) over which the `<logic:iterate>` tag can run are now documented.
-   The `<bean:define>` documentation now mentions the JSP 1.1 Specification restriction on using more than one `id` attribute with the same value in the same page.

The following changes and bug fixes to the Struts Example Application have occurred:

-   The Java source code of these applications is now included in the corresponding WAR files, in subdirectory `WEB-INF/src` .
-   Excessive filter() calls in `LinkSubscriptionTag` have been eliminated.
-   Calls to the deprecated `BeanUtils.filter()` have been replaced by calls to `ResponseUtils.filter()` .
-   Removed any attempt to save the pseudo-database at application shutdown, because there is no portable mechanism to accomplish this task.

The following changes and bug fixes to the Struts Template Example Application have occurred:

-   Refactored the example pages to eliminate the creation of redundant `.html.md>` , `<head>` , and `<body>` tags.
-   If `<template:get>` or `<template:insert>` throws an exception, do not overwrite any "real" exception that has already been saved.
-   The text of the various pages in the example has been updated so that they are not identical.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


