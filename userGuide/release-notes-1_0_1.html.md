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

This document contains the release notes for **Version 1.0.1** of the Struts Framework, and covers changes that have taken place since [Version 1.0](release-notes-1_0.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

This version covers bug-fixes only; no new functionality.

<span id="Whats_Included"></span>What's Included?
-------------------------------------------------

The binary distribution of this release includes the following files relevant to Struts 1.0.1:

-   `INSTALL` - Brief installation instructions. See the `Struts Documentation Application` , or online at <http://jakarta.apache.org/struts/> for more information.
-   `LICENSE` - The Apache Software Foundation license that defines the terms under which you can use Struts (and other software licensed by Apache).
-   `README` - A brief introduction to Struts.
-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `struts.jar` - JAR file that contains the compiled Java classes for version 1.0 of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts-xxxxx.tld` - The tag library descriptor files for the Struts 1.0.1 tag libraries (bean,.html.md, logic, and template). You must place these files in the `/WEB-INF` directory of your web application, and reference them with appropriate `<taglib>` directives in your web.xml file.
    -   `jdbc2_0-stdext.jar` - The JDBC 2.0 Optional Package API classes (package `javax.sql` ). You will need to include this file in the `/WEB-INF/lib` directory of your application, if it is not already made visible to web applications by your servlet container.
    -   `struts-config_1_0.dtd` - The document type descriptor (DTD) for the Struts configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `web-app_2_2.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.2 specification. This copy is for reference purposes only.
    -   `web-app_2_3.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.3 specification. This copy is for reference purposes only.
-   `webapps/` - Web Application Archive (WAR) files for the web applications that are included with Struts.

The struts 0.5 milestone API release is no longer supported, and has been removed as of Struts 1.1.

<span id="Whats_New"></span>What's New?
---------------------------------------

The following new features have been added to the basic controller framework (package `org.apache.struts.action` ):

The following new features have been added to the utility classes (package `org.apache.struts.util` ):

-   LocalStrings: Correct message regarding replaceable parameter so that it does not append an extraneous character.
-   MessageResources: Escape any single quote characters that are included in the specified message string.
-   Allow a transaction token to be the only parameter in computeParameters().
-   Change RequestUtils to encode ampersands when building a query string.

The following new features have been added to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

The following new features have been added to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

The following new features have been added to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ):

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes have occurred in the configuration files related to Struts:

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

-   Modify ActionForm class to use ActionServletWrapper rather than expose ActionServlet.
-   Add ActionServletWrapper class. Used by ActionForm to prevent the Public String properties of ActionServlet from being changed via a query string.
-   Unconditionally pass the selected mapping as a request attribute under key Action.MAPPING\_KEY, even if no form bean is specified.
-   Avoid a NullPointerException in corner cases caused by failed initialization of ActionServlet.

The following changes and bug fixes have occurred in the file upload package (package `org.apache.struts.upload` ):

-   Fixed lost byte problem in BufferedMultipartInputStream
-   Fixed ArrayIndexOutOfBoundsException situations
-   Better reporting for premature closing of input streams while reading multipart requests.
-   Additional fix for file corruption problem with uploads and new line characters.

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   Modify RequestUtils class to use ActionServletWrapper rather than expose ActionServlet.
-   `ConvertUtils.convertCharacter()` will now detect empty strings and return the default value.

The following changes and bug fixes have occurred in the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ):

-   Correct the generated scripting variable type when the \<bean:cookie\>, \<bean:header\>, or \<bean:parameter\> tag is used with the "multiple" attribute.

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   Fixed FormTag to exclude query string when identifying action mapping name.
-   Correct MultiboxTagdoAfterBody() to return SKIP\_BODY instead of SKIP\_PAGE.
-   Added the 'align' attribute to the \.html.md:image\> tag.
-   On the Options tag, if the property specified by the "property" attribute returns null, it now throws an error message that indicates what the real problem is, rather than causing an NPE.
-   Added 'style' and 'styleClass' attributes for \.html.md:option\> and \<html:options\> tags.
-   Correctly URLEncode the query string parameter value on ImgTag, even if there is only a single parameter.

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   The `.html.md:errors>` when the property tag is specified, errors are no longer printed if the specified property has no errors. Previously errors were always printed! Future enhancements would include additional attributes to always turn off the header or footer.

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   Add installation notes for Jetty.
-   In the Tag Developers Guide, add more detail regarding file upload requirements.
-   In the Introduction, added references to basic background material.
-   In Building View Components, clarify that additional i18n support may be provided by the browser, and is outside the scope of the framework.
-   In Building Controller Components, document 'validating' init-param, add defaults for various parameters, clarify that some web.xml settings are not Struts-specific.
-   Correct the example page in the User's Guide (Building View Components) to reflect current practice.
-   Revised installation instructions for SilverStream and Resin.

The following changes and bug fixes to the Struts Example Application have occurred:

-   Remove references to saving database data from "tour" document, since this functionality was removed.

The following changes and bug fixes to the Struts Template Example Application have occurred:

The following changes and bug fixes to the Struts Exercise Taglib Example Application have occurred:

-   Added test case for \.html.md:select\> using \<html:options\> based on a collection saved in the page context.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


