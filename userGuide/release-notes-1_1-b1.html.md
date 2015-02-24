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

This document contains the release notes for **Version 1.1 Beta 1** of the Struts Framework, and covers changes that have taken place since [Version 1.0.1](release-notes-1_0_1.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

<span id="Whats_Included"></span>What's Included?
-------------------------------------------------

The binary distribution of this release includes the following files relevant to Struts:

-   `INSTALL` - Brief installation instructions. See the `Struts Documentation Application` , or online at <http://jakarta.apache.org/struts/> for more information.
-   `LICENSE` - The Apache Software Foundation license that defines the terms under which you can use Struts (and other software licensed by Apache).
-   `README` - A brief introduction to Struts.
-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `commons-*.jar` - Release packages from the [Jakarta Commons Project](http://jakarta.apache.org/commons/) that Struts relies on. You are welcome to use these classes in your own applications. These JAR files should be copied into the `/WEB-INF/lib` directory of your web application.
    -   `struts.jar` - JAR file that contains the compiled Java classes of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts-xxxxx.tld` - The tag library descriptor files for the Struts 1.0 tag libraries (bean,.html.md, logic, and template). You must place these files in the `/WEB-INF` directory of your web application, and reference them with appropriate `<taglib>` directives in your web.xml file. **NOTE** - The struts-form.tld file is deprecated; you should use the struts-html.tld file instead.
    -   `jdbc2_0-stdext.jar` - The JDBC 2.0 Optional Package API classes (package `javax.sql` ). You will need to include this file in the `/WEB-INF/lib` directory of your application, if it is not already made visible to web applications by your servlet container.
    -   `struts-config_1_1.dtd` - The document type descriptor (DTD) for the Struts configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `web-app_2_2.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.2 specification. This copy is for reference purposes only.
    -   `web-app_2_3.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.3 specification. This copy is for reference purposes only.
-   `webapps/` - Web Application Archive (WAR) files for the web applications that are included with Struts.

<span id="Whats_New"></span>What's New?
---------------------------------------

**DEPRECATIONS** :

-   `struts-config.dtd` in favor of `struts-config_1_1.dtd` .

**COMMONS PACKAGES** : Several components of Struts 1.0 have been found to be useful in general Java development (and not just useful for building Struts-based web applications), and have been migrated into the [Jakarta Commons Project](http://jakarta.apache.org/commons/) . As a result, the current development version of Struts has been modified to rely on the Commons packages containing these classes, rather than the Struts internal versions. In nearly every case, this involved changing only the `import` statements at the top of your classes. Any applications that utilize these classes will need to be modified in the same way. The following Commons packages contain the replacements for the corresponding Struts 1.0 classes:

-   **BeanUtils Package** (org.apache.commons.beanutils) - `org.apache.struts.utils.BeanUtils` , `org.apache.struts.utils.ConvertUtils` , and `org.apache.struts.utils.PropertyUtils` .
-   **Collections Package** (org.apache.commons.collections) - `org.apache.struts.util.ArrayStack` , `org.apache.struts.util.FastArrayList` , `org.apache.struts.util.FastHashMap` , `org.apache.struts.util.FastTreeMap` .
-   **Digester Package** - (org.apache.commons.digester) - `org.apache.struts.digester.*` .

**XML PARSER PREREQUISITE UPDATED** : Struts now depends on an XML parser that conforms to the JAXP/1.1 (rather than JAXP/1.0) APIs. Parser known to work include the JAXP/1.1 reference implementation, and Xerces 1.3.1.

**CONTRIB Directory** : A new directory ( `contrib` ) in the CVS source repository has been added to accumulate Struts add-on extensions that are generally useful but have not yet been integrated into the standard code base.

-   ValidatorForm - Client and Server-side validation library.
-   Tiles - Advanced templating library (see Struts-Tiles.war).
-   Service Manager - Add custom services without subclassing controller.

**UNIT TESTING SUPPORT** : Support for running unit tests on Struts components and custom tags is being added, utilizing the [Jakarta Cactus](http://jakarta.apache.org/cactus/) product.

The following new features have been added to the basic controller framework (package `org.apache.struts.action` ):

-   The new `ActionMessages` class will support a superset of the capabilities of `ActionErrors` , and will be useful as a collection of general purpose messages, not just errors.

The following new features have been added to the utility classes (package `org.apache.struts.util` ):

-   LocalStrings: Correct message regarding replaceable parameter so that it does not append an extraneous character.
-   Add LabelValueBean class. This defines a collection of name/value pairs that can be used with the \.html.md:options\> tag, and elsewhere.
-   MessageResources: Escape any single quote characters that are included in the specified message string.
-   Allow a transaction token to be the only parameter in computeParameters().
-   Change RequestUtils to encode ampersands when building a query string.

The following new features have been added to the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ):

-   Add format, locale and bundle attributes to bean:write to support values formatting according to current user locale, format string from attribute or format string from string resources.
-   Correct the generated scripting variable type when the \<bean:cookie\>, \<bean:header\>, or \<bean:parameter\> tag is used with the "multiple" attribute.
-   Added `name` , `property` , and `scope` attributes to the `<bean:message>` tag, so that the message source key can be obtained dynamically from a bean or bean property.

The following new features have been added to the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   On the Options tag, if the property specified by the "property" attribute returns null, it now throws an error message that indicates what the real problem is, rather than causing an NPE.
-   Added 'style' and 'styleClass' attributes for \.html.md:option\> and \<html:options\> tags.
-   Added 'name', 'property' and 'scope' attributes to `<bean:message>` so that the message resource key can be obtained dynamically from a bean.
-   Added a new `.html.md:messages>` tag to iterate through a message collection in the new `ActionMessages` class.
-   `ActionForm` will now call `reset()` if it instantiates the ActionForm bean.
-   Added indexed property to the SubmitTag, SelectTag, LinkTag.java, CheckboxTag, ButtonTag, ImageTag, RadioTag, and TextArea.Tag.

The following new features have been added to the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   Added `<logic:empty>` and `<logic:notEmpty>` tags, which are similar to `<logic:present>` and `<logic:notPresent>` except for the treatment of empty strings.

The following new features have been added to the *struts-template* custom tag library (package `org.apache.struts.taglib.template` ):

-   None.

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

-   Move Tag Library documentation into User's Guide.
-   Added Kickstart FAQ.
-   Added Reference copy of 1.0 JavaDoc.
-   Revised the example page in the User's Guide (Building View Components) to reflect current practice.
-   Revised installation instructions for SilverStream and Resin.

<span id="Changes_and_Bug_Fixes"></span>Changes and Bug Fixes
-------------------------------------------------------------

The following changes and bug fixes have occurred in the configuration files related to Struts:

-   Remove deprecated support for the old (Struts 0.5) configuration file format.

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

-   Add InvokeAction and CreateActionForm methods to allow direct chaining of Actions.
-   Add ContextHelper to expose framework elements to alternate presentation layers.
-   ActionForms and related classes now use a StringBuffer when responding a toString request in order to conserve resources.
-   Add standard LookupDispatchAction to help select between internationalized buttons.
-   Modify ActionForm class to use ActionServletWrapper rather than expose ActionServlet.
-   Add ActionServletWrapper class. Used by ActionForm to prevent the Public String properties of ActionServlet from being changed via a query string.
-   Unconditionally pass the selected mapping as a request attribute under key Action.MAPPING\_KEY, even if no form bean is specified.
-   Avoid a NullPointerException in corner cases caused by failed initialization of ActionServlet.
-   The `ActionForm` class is now truly serializable, because the two non-serializable instance variables (servlet and multipartRequestHandler) have been made transient. However, if you actually do serialize and deserialize such instances, it is your responsibility to reset these two properties.
-   Removed deprecated Struts 0.5 methods, and support for the Struts 0.5 configuration file format.
-   The initial order a property/key is added in is now maintained by ActionMessages class.

The following changes and bug fixes have occurred in the file upload package (package `org.apache.struts.upload` ):

-   Correct MultiboxTagdoAfterBody() to return SKIP\_BODY instead of SKIP\_PAGE.
-   Fixed lost byte problem in BufferedMultipartInputStream
-   Fixed ArrayIndexOutOfBoundsException situations
-   Better reporting for premature closing of input streams while reading multipart requests.
-   Additional fix for file corruption problem with uploads and new line characters.

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   Modify RequestUtils class to use ActionServletWrapper rather than expose ActionServlet.
-   Added error message for the getActionErrors and getActionMessages method.
-   Added a getActionErrors and getActionMessages methods to generate the correct corresponding object based on the object retrieved from request scope based on the key passed in.
-   The logic for creating an ActionErrors or ActionMessages object has been moved to a utility method in RequestUtils. The JspException message is also generated in RequestUtils.
-   `ConvertUtils.convertCharacter()` will now detect empty strings and return the default value.

The following changes and bug fixes have occurred in the *struts-bean* custom tag library (package `org.apache.struts.taglib.bean` ):

-   The `.html.md:errors>` when the property tag is specified, errors are no longer printed if the specified property has no errors. Previously errors were always printed ! Future enhancements would include additional attributes to always turn off the header or footer.
-   Made the remaining helper methods "protected" rather than "private".

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   Fixed FormTag to exclude query string when identifying action mapping name.
-   Added the 'align' attribute to the \.html.md:image\> tag.
-   Added indexed attribute to ImageTag, RadioTag, and TextAreaTag.
-   Added MessagesTag.
-   Correctly URLEncode the query string parameter value on ImgTag, even if there is only a single parameter.

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   None.

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   In the HTML tag documentation, expand to cover using indexed properties with iterate.
-   Add installation notes for Jetty.
-   In the Tag Developers Guide, add more detail regarding file upload requirements.
-   In the Introduction, added references to basic background material.
-   In Building View Components, clarify that additional i18n support may be provided by the browser, and is outside the scope of the framework.
-   In Building Controller Components, document 'validating' init-param, add defaults for various parameters, clarify that some web.xml settings are not Struts-specific.
-   Reorganized to separate 1.0 material from nightly build material.
-   Expanded Resources section.
-   Various updates regarding other release notes.

The following changes and bug fixes to the Struts Example Application have occurred:

-   Add Russian and Japanese translations of the application resources and set the character set for the example JSP pages to "UTF-8" so that it can display either English or Japanese.
-   Exchange "name" for "attribute" properties for Edit mappings in Struts configuration file.
-   Remove references to saving database data from "tour" document, since this functionality was removed.

The following changes and bug fixes to the Struts Template Example Application have occurred:

-   None.

The following changes and bug fixes to the Struts Exercise Taglib Example Application have occurred:

-   Added test case for \.html.md:select\> using \<html:options\> based on a collection saved in the page context.

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


