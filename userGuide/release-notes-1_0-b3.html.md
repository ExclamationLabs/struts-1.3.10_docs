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

This document contains the release notes for **Version 1.0-beta-3** of the Struts Framework, and covers changes that have taken place since [Version 1.0-beta-2](release-notes-1_0-b2.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

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

**DEPRECATIONS** - The entire custom tag library that is documented in `struts-form.tld` has been deprecated because this library has been renamed `struts.html.md.tld` instead.

**DEPRECATIONS** - Several classes in the `org.apache.struts.util` package have been marked as deprecated in their entirety, because they will be replaced by versions from the Jakarta Commons project once those packages are released. These deprecated classes will **not** be removed until a release after Struts 1.1. In general, the only change required inside user code using these classes will be to update the `import` statement. The following classes are involved:

-   ArrayStack
-   BeanUtils
-   ConvertUtils
-   FastArrayList
-   FastHashMap
-   FastTreeMap
-   GenericConnection
-   GenericDataSource
-   PropertyUtils

The following new features have been added to the basic controller framework (package `org.apache.struts.action` ):

The following new features have been added to the utility classes (package `org.apache.struts.util` ):

-   `GenericDataSource` can now be configured with a "ping" type command (via the `pingCommand` and `pingQuery` properties) that will be executed before returning a connection from `getConnection()` . This can be used to detect stale connections due to timeouts or a database server restart. If the ping command fails, the corresponding connection will be thrown away, and a new one allocated.

The following new features have been added to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   It is now possible to use any object in the values and labels collections for the `.html.md:options>` tag.
-   Added the missing `tabindex` attribute to the `.html.md:radio>` tag.
-   On the `.html.md:img>` , `<html:link>` , and `<html:rewrite>` tags, you can now specify arbitrary object values in the `Map` used to include dynamic request attributes, as long as the `toString()` method renders the values appropriately.
-   In all cases where "minimized" attributes were being generated ( `checked` , `disabled` , `multiple` , `readonly` , and `selected` ), the generated attribute has a value (such as `selected="true"` ) for XML syntax compatibility.

The following new features have been added to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

The following new features have been added to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ):

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes have occurred in the configuration files related to Struts:

-   The DTD for `struts-config.xml` files had an incorrect ENTITY declaration for the `Location` element.
-   The DTD for version 2.3 web application deployment descriptors has been updated to the most recent (Proposed Final Draft 2) version.

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   The `FastArrayMap()` , `FastHashMap()` , and `FastTreeMap()` classes not correctly implement the `clone()` , `equals()` , and `hashCode()` methods consistent with the requirements of the Java standard Collections APIs.
-   `PropertyUtils` can now access public methods defined in nested interfaces.
-   A misleading error message returned by `BeanUtils` has been corrected.
-   Work around a problem compiling the `FastXxxxx` classes with the VAJ compiler, because the superclass already includes a private class named `Iterator` .
-   Remove a JDK 1.3 dependency that prevented compiling `BeanUtils` under JDK 1.2.
-   Generate "&amp;" instead of "&" in query strings that contain more than one name/value pair.

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   Restore the ability of the `.html.md:button>` tag to retrieve the button text from the nested body content (so that it can be easily internationalized).
-   If the property name used in the `labelProperty` attribute of an `.html.md:options>` tag is invalid, report the correct property name in the error message.

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   Fix a reference to an old Struts 0.5 tag in one of the User's Guide examples.
-   Fix the stylesheet used to transform XML into HTML documentation so that nested `<body>` tags are not created.
-   The DTD for Struts configuration files has been refined to highlight the fact that you should use `<set-property>` elements to configure your data source implementation.

The following changes and bug fixes to the Struts Example Application have occurred:

The following changes and bug fixes to the Struts Template Example Application have occurred:

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


