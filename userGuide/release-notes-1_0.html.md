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

This document contains the release notes for **Version 1.0** of the Struts Framework, and covers changes that have taken place since [Version 1.0-beta-3](release-notes-1_0-b3.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

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

The following new features have been added to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   The `.html.md:link>` tag now supports the optional `title` attribute, that causes some browsers to display alternate text when the mouse is hovered over a hyperlink.

The following new features have been added to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   The `<logic:iterate>` tag now supports a new attribute, `indexId` . This attribute names a page scope attribute (and corresponding scripting variable) that will be exposed in the nested body of the iteration, which will contain the current loop index as a java.lang.Integer.

The following new features have been added to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ):

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes have occurred in the configuration files related to Struts:

-   The documentation about configuring a data source element in the `struts-config.xml` file has been updated to emphasize the use of `<set-property>` elements nested inside the `<data-source>` element. No further additional attributes will be added to the `<data-source>` element in the DTD to support custom properties of particular data source implementations.

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

-   Several issues introduced with the internal wrapping of multipart requests have been fixed.
-   The instance variables in the `ActionForm` base class are now transient, so that `ActionForm` instances can actually be serialized. **WARNING** - If you deserialize such an `ActionForm` instance and attempt to use it within the Struts framework, be sure to call `setServlet()` (and `setMultipartRequestHander()` if appropriate) first.

The following changes and bug fixes have occurred in the file upload package (package `org.apache.struts.upload` ):

-   Fixed a bug that could cause corruption in the uploaded file, by converting sequences of \\r\\n\\n into \\r\\n\\r\\n.

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   Corrected a cut-and-paste typo that caused NullPointerException on attempts to use the new `pingQuery` property that was added in Struts 1.0-b3.
-   Fix operation ordering so that `RequestUtils.lookup()` will throw a JspException when the specified bean is missing, in accordance with its JavaDoc documentation.
-   Digester calls to `Rule.body()` methods will now trim leading and trailing whitespace first, consistent with the behavior of other body processing performed within the rules.
-   Correct the calculation of an absolute URL from a context-relative path in `RequestUtils.absoluteURL()` .

The following changes and bug fixes have occurred in the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ):

-   The `<bean:include>` tag will now pass a session identifier on to the included request (assuming that it is part of the same web application), even if the current request is maintaining session identity with cookies. Previously, this only worked if you were using URL rewriting.

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   For all tags where Struts generates attributes that are allowed to be minimized in the HTML specification (i.e. checked, disabled, multiple, readonly, and selected), generate attribute values equal to the attribute name, as required by HTML 4.01, section 3.3.4. For example, generate `checked="checked"` instead of `checked="true"` for the "checked" attribute.
-   Correctly generate a `<a name="my name"><>` element when the `linkName` attribute is used on the `.html.md:link>` tag.

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   Update the processing performed by the `<logic:present>` and `<logic:notPresent>` tags to reflect the changed behavior of `RequestUtils.lookup()` .

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   Links to subscribe and unsubscribe from the STRUTS-DEV and STRUTS-USER mailing lists have been added to the home page.
-   Miscellaneous corrections to typos and hyperlinks.
-   Cleaned up problems in the stylesheets used to create documentation pages that formerly emitted `<project>` tags in the generated HTML, and generated incorrect references to link colors in the navigation bar.
-   Added a "Who We Are" page to the documentation.

The following changes and bug fixes to the Struts Example Application have occurred:

-   The `name` and `page` attributes of the `<app:checkLogon>` tag now accept runtime expressions.

The following changes and bug fixes to the Struts Template Example Application have occurred:

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


