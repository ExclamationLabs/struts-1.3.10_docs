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

<span id="a6.1_Release_Notes"></span>6.1 Release Notes
------------------------------------------------------

### <span id="Beta_Notes"></span>Beta Notes

This section contains the release notes for **nightly build** of the Struts Framework, for changes that have taken place since [Version 1.1 beta 2](release-notes-1_1-b2.html.md) was released. For a complete list of changes since the last production release, see the [Introduction](#Introduction)

### <span id="Beta_Fixes"></span>Beta Fixes

**ApplicationConfig:** In Struts 1.1. beta 3, the ApplicationConfig class is renamed to ModuleConfig, to conform with the venacular.

**Dyna\*Form:** In Struts 1.1. beta 3, the reset method was changed so that it conforms to the original ActionForm implementation.

**Blank application:** Fixed configuration problem with Struts Blank application.

### <span id="Introduction"></span>Introduction

The remainder of this document contains the release notes for **nightly build** of the Struts Framework, and covers changes that have taken place since [Version 1.0.2](release-notes-1_0_2.html.md) was released. The following sections cover [New Features](#New) and [Changes](#Changes) to Struts.

### <span id="Whats_Included"></span>What's Included?

The binary distribution of this release includes the following files relevant to Struts:

-   `INSTALL` - Brief installation instructions. See the `Struts Documentation Application` , or online at <http://jakarta.apache.org/struts/> for more information.
-   `LICENSE` - The Apache Software Foundation license that defines the terms under which you can use Struts (and other software licensed by Apache).
-   `README` - A brief introduction to Struts.
-   `lib/` - Directory containing files you will need in your own applications. The individual files of interest are:
    -   `commons-*.jar` - Release packages from the [Jakarta Commons Project](http://jakarta.apache.org/commons/) that Struts relies on. You are welcome to use these classes in your own applications. These JAR files should be copied into the `/WEB-INF/lib` directory of your web application.
    -   `struts.jar` - JAR file that contains the compiled Java classes of Struts. You must place this file in the `/WEB-INF/lib` directory of your web application.
    -   `struts-xxxxx.tld` - The tag library descriptor files for the Struts 1.1 tag libraries (bean,.html.md, logic, and template). You must place these files in the `/WEB-INF` directory of your web application, and reference them with appropriate `<taglib>` directives in your web.xml file.
    -   `jdbc2_0-stdext.jar` - The JDBC 2.0 Optional Package API classes (package `javax.sql` ). You will need to include this file in the `/WEB-INF/lib` directory of your application, if it is not already made visible to web applications by your servlet container.
    -   `struts-config_1_1.dtd` - The document type descriptor (DTD) for the Struts 1.1 configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `struts-config_1_0.dtd` - The document type descriptor (DTD) for the Struts 1.0 configuration file (which is typically named `/WEB-INF/struts-config.xml` . Your configuration file will be validated against an internal copy of this DTD -- this copy is available for reference purposes only.
    -   `web-app_2_2.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.2 specification. This copy is for reference purposes only.
    -   `web-app_2_3.dtd` - The document type descriptor (DTD) for web.xml files conforming to the Servlet 2.3 specification. This copy is for reference purposes only.
-   `webapps/` - Web Application Archive (WAR) files for the web applications that are included with Struts.

### <span id="Whats_New"></span>What's New?

Following are highlights of the new features. In the next section, we provide links to the JavaDocs for the affected classes.

**New Configuration DTD**

The Struts Configuration 1.0 DTD has been deprecated in favor of the `struts-config_1_1.dtd` . In the Struts 1.1 release, existing Struts configuration files can be loaded using either DTD version.

**New Dependencies on Commons packages**

Several components of Struts 1.0 have been found to be useful in general Java development (and not just useful for building Struts-based web applications), and have been migrated into the [Jakarta Commons Project](http://jakarta.apache.org/commons/) . As a result, the current development version of Struts has been modified to rely on the Commons packages containing these classes, rather than the Struts internal versions. In nearly every case, this involved changing only the `import` statements at the top of your classes. Any applications that utilize these classes will need to be modified in the same way.

The following Commons packages contain the replacements for the corresponding Struts 1.0 classes:

-   **BeanUtils Package** [ [`org.apache.commons.beanutils`](http://jakarta.apache.org/commons/beanutils.html.md) ] - `org.apache.struts.utils.BeanUtils` , `org.apache.struts.utils.ConvertUtils` , and `org.apache.struts.utils.PropertyUtils` .
-   **Collections Package** [ [`org.apache.commons.collections`](http://jakarta.apache.org/commons/collections.html.md) ] - `org.apache.struts.util.ArrayStack` , `org.apache.struts.util.FastArrayList` , `org.apache.struts.util.FastHashMap` , `org.apache.struts.util.FastTreeMap` .
-   **Digester Package** - [ [`org.apache.commons.digester`](http://jakarta.apache.org/commons/digester.html.md) ] - `org.apache.struts.digester.*` .

The following Commons packages are also now used by various components of the Struts framework:

-   **Database Connection Pool Package** [ [`org.apache.commons.dbpc`](http://jakarta.apache.org/commons/dbcp.html.md) ]
-   **FileUpload Package** [ [`org.apache.commons.fileupload`](http://cvs.apache.org/viewcvs/jakarta-commons-sandbox/fileupload/) ]
-   **Logging Package** [ [`org.apache.commons.logging`](http://jakarta.apache.org/commons/logging.html.md) ]
-   **Pool Package** [ [`org.apache.commons.pool`](http://jakarta.apache.org/commons/pool/index.html.md) ]
-   **Validator Package** [ [`org.apache.commons.validator`](http://cvs.apache.org/viewcvs/jakarta-commons/validator/) ]

**NOTE! XML Parser Prerequisite Updated**

Struts now depends on an XML parser that conforms to the JAXP/1.1 (rather than JAXP/1.0) APIs. Parsers known to work include the JAXP/1.1 reference implementation, and Xerces 1.3.1.

**SOURCE DEVELOPERS NOTE! Ant Prerequisite Updated**

To build Struts from source Ant 1.4 or later is now required. This does not affect developers that use Struts from the binary distribution.

**Struts Validator Integration**

The new Commons-Validator is now integrated with Struts and exposed through the new Validator package.

**Tiles - An advanced templating taglib**

The Tiles JSP assembly framework has been integrated with Struts.

**Nested - An very cool taglib extension**

The Nested taglib is bundled with Struts and enhances the functionality of the existing Struts tags.

**New Example Applications**

New example applications for the Validator and Tiles are now part of the Struts distribution.

**New Contrib directory for optional components**

A new directory ( `contrib` ) in the CVS source repository has been added to accumulate Struts add-on extensions that are generally useful but have not yet been integrated into the standard code base.

-   Scaffold - An extension of the Commons Scaffold toolkit of reusable classes for building web applications.
-   Struts-el - The optional Struts-el taglib makes it easy to use Struts with JSTL (container with servlet 2.3 support required).

The source for these components is available in the Struts source distribution. Binary distributions may also be made available with the Struts download area. As optional components, these products have their own release cycles.

**Action Package Additions**

The following new features have been added to the basic controller framework [ `org.apache.struts.action` ]:

-   The ActionServlet now provides support for modular Struts applications and sports several new extension points.
-   The new `ActionMessages` class will support a superset of the capabilities of `ActionErrors` , and will be useful as a collection of general purpose messages, not just errors.

**Upload Package Additions**

The following new features have been added to the file upload classes [ `org.apache.struts.upload` ]:

-   `CommonsMultipartRequestHandler:` New class that implements file upload using the Jakarta Commons FileUpload package.

**Util Package Additions**

The following new features have been added to the utility classes [ `org.apache.struts.util` ]:

-   `LocalStrings:` Correct message regarding replaceable parameter so that it does not append an extraneous character.
-   `LabelValueBean:` New class that defines a collection of name/value pairs that can be used with the \.html.md:options\> tag, and elsewhere.
-   `MessageResources:` Escape any single quote characters that are included in the specified message string.
-   `computeParameters:` Allow a transaction token to be the only parameter in .
-   `RequestUtils:` Change to encode ampersands when building a query string.

**Bean Taglib Package Additions**

The following new features have been added to the *struts-bean* custom tag library [ `org.apache.struts.taglib.bean` ]:

-   `<bean:write>` : Add format, locale and bundle attributes to support formatting values according to current user locale, format string from attribute or format string from string resources.
-   `<bean:cookie>, <bean:header>, or <bean:parameter>:` Correct the generated scripting variable type when tag is used with the "multiple" attribute.
-   `<bean:message>:` Added `name` , `property` , and `scope` attributes to the tag, so that the message source key can be obtained dynamically from a bean or bean property.

**HTML Taglib Package Additions**

The following new features have been added to the *struts.html.md* custom tag library [ `org.apache.struts.taglib.html` ]:

-   `.html.md:link>:` Added 'action' attribute.
-   `.html.md:options>:` If the property specified by the 'property' attribute returns null, tag now throws an error message that indicates what the real problem is, rather than causing an NPE.
-   `.html.md:option> and <html:options>:` Added 'style' and 'styleClass' attributes.
-   `.html.md:optionsCollection>:` New tag providing a cleaner way of populating HTML options from a collection.
-   `<bean:message>:` Added 'name', 'property' and 'scope' attributes so that the message resource key can be obtained dynamically from a bean.
-   `.html.md:messages>:` New tag to iterate through a message collection in the new `ActionMessages` class.
-   `ActionForm:` Tag will now call `reset()` if it instantiates the ActionForm bean. This also requires that the bean instantiated by the tag to be an `ActionForm` subclass.
-   `.html.md:image>:` Added the 'align' attribute.
-   `.html.md:img>:` Added the mouse event attributes ('onclick', 'ondblclick', 'onmousedown', 'onmouseup', 'onmouseover', 'onmousemove', 'onmouseout').
-   `SubmitTag, SelectTag, LinkTag.java, CheckboxTag, ButtonTag, ImageTag, RadioTag, and TextArea tags:` Added indexed property.

**Logic Taglib Package Additions**

The following new features have been added to the *struts-logic* custom tag library [ `org.apache.struts.taglib.logic` ]:

-   `<logic:empty>` and `<logic:notEmpty>` : New tags that are similar to `<logic:present>` and `<logic:notPresent>` except for the treatment of empty strings.

**Template Taglib Package Additions**

The following new features have been added to the *struts-template* custom tag library [ `org.apache.struts.taglib.template` ]:

-   None.

**Documentation Additions**

The following new features have been added to the Struts Documentation application (and corresponding contents on the Struts web site):

-   Version Differences: New section in Release Notes to link to the JavaDocs for all Struts classes and members added or changed between versions.
-   FAQ/HowTos: New documentation category organizes our FAQs and example-driven howTos. New HowTos include "Building Applications", "Using SSL", and using Struts with Eclipse or NetBeans.
-   User Guide Preface: New section to overview the enabling technologies behind Struts.
-   Developer Guides: Added "cover page" to guides. These then link to the Package Descriptions and the API guides.
-   HTML tag documentation: expanded to cover using indexed properties with iterate.
-   Site Menu: Removed separate links to taglib documentation, since these are now in the Developer Guide.
-   Newbie FAQ: The questions most likely to be asked by new developers using Struts. Still under development.
-   Kickstart FAQ: The questions most likely to be asked when selecting Struts.
-   1.0 JavaDoc: Added archival copy to web site for future reference.
-   The UserGuide "Building" pages: General revisions to reflect new features and current practices.
-   Installation: Updated instructions for SilverStream and Resin. Add installation notes for Jetty. Added RexIP to list of nominal containers.
-   JavaDocs: New `@since Struts 1.1` tag to indicate new packages, classes, and members added after the Struts 1.0.x version

### <span id="Operational_Changes_and_Bug_Fixes"></span>Operational Changes and Bug Fixes

**Struts Configuration Changes**

The following changes and bug fixes have occurred in the configuration files related to Struts:

-   Deprecated (Struts 0.5) configuration file format: Remove support.
-   Deprecated (Struts 0.5) methods: Remove from codebase.

**Added Config Package**

-   ControllerConfig: Added inputForward property to indicate that ActionMapping.input is a forward rather than a URI.
-   ControllerConfig: Added forwardPattern and inputPattern to help manage page directories in application modules.
-   Added package to provide more flexibility in configuring the controller and to provide support for modular applications

**Action Package Changes**

The following changes and bug fixes have occurred in the basic controller framework (package `org.apache.struts.action` ):

-   ActionMapping: input property may now refer to an ActionForward rather than a module-relative path if inputForward is set to true on the module's ControllerConfig bean [org.apache.struts.config.ControllerConfig.
-   ActionServlet: Added convertNull parameter to simulate the Struts 1.0 behavior when populating forms. If set to true, the numeric Java wrapper class types (like java.lang.Integer) will default to null (rather than 0).
-   ActionServlet: Added "config/$foo" parameter and deprecated several others in favor of components in the new config package.
-   ActionForms and related classes: now use a StringBuffer when responding a toString request in order to conserve resources.
-   LookupDispatchAction: Added standard Action to help select between internationalized buttons.
-   ActionForm class: Modified to use ActionServletWrapper rather than expose ActionServlet.
-   ActionServletWrapper class: Added for use by ActionForm to prevent the Public String properties of ActionServlet from being changed via a query string.
-   Action.MAPPING\_KEY request attribute: Unconditionally pass the selected mapping as a request attribute ("org.apache.struts.action.mapping.instance") even if no form bean is specified.
-   ActionServlet: Avoid a NullPointerException in corner cases caused by failed initialization of servlet.
-   ActionForm class: Now truly serializable, because the two non-serializable instance variables (servlet and multipartRequestHandler) have been made transient. However, if you actually do serialize and deserialize such instances, it is your responsibility to reset these two properties.
-   ActionMessages and ActionErrors: The initial order a property/key is added in is now retained.

**Upload Package Changes**

The following changes and bug fixes have occurred in the file upload package (package `org.apache.struts.upload` ):

-   CommonsMultipartRequestHandler: New implementation of file upload based on the Jakarta Commons FileUpload package. This new implementation is now the default.
-   BufferedMultipartInputStream: Fixed lost byte problem.
-   ArrayIndexOutOfBoundsException: Fixed situations where this was known to occur.
-   Multipart requests: Better reporting for premature closing of input streams while reading multipart requests.
-   New line characters: Additional fix for file corruption problem with uploads and new line characters.

**Utility Package Changes**

The following changes and bug fixes have occurred in the utilities (package `org.apache.struts.util` ):

-   RequestUtils: Added support for forwardPattern, pagePattern, and inputForward properties on ControllerConfig.
-   GenericDataSource: Deprecated and modified to act as a thin wrapper around [ `org.apache.commons.dbpc.BasicDataSource` ]. Replaced by direct use of BasicDataSource or other compatible component.
-   RequestUtils class: Modify to use ActionServletWrapper rather than expose ActionServlet.
-   Added error message for the getActionErrors and getActionMessages method.
-   getActionErrors and getActionMessages: Added methods to generate the correct corresponding object based on the object retrieved from request scope based on the key passed in.
-   ActionErrors or ActionMessages: The logic for creating one of these objects has been moved to a utility method in RequestUtils.
-   JspException message: Now generated in RequestUtils.
-   ConvertUtils.convertCharacter(): Will now detect empty strings and return the default value.

**Bean Taglib Package Changes**

The following changes and bug fixes have occurred in the *struts-bean* custom tag library [ `org.apache.struts.taglib.bean` ]:

-   \.html.md:errors\>: When the property tag is specified, errors are no longer printed if the specified property has no errors. Previously errors were always printed ! Future enhancements would include additional attributes to always turn off the header or footer.
-   Made the remaining helper methods "protected" rather than "private".

**HTML Taglib Package Changes**

The following changes and bug fixes have occurred in the *struts.html.md* custom tag library (package `org.apache.struts.taglib.html` ):

-   FormTag: Fixed to exclude query string when identifying action mapping name.
-   ImgTag: Correctly URLEncode the query string parameter value even if there is only a single parameter.
-   MultiboxTag.doAfterBody(): Corrected to return SKIP\_BODY instead of SKIP\_PAGE.

**Logic Taglib Package Changes**

The following changes and bug fixes have occurred in the *struts-logic* custom tag library (package `org.apache.struts.taglib.logic` ):

-   None.

**Documentation Application Changes**

The following changes and bug fixes to the Struts Documentation application (and corresponding contents on the Struts web site) have occurred:

-   Reorganized Resources into separate pages..
-   In the Tag Developers Guide, add more detail regarding file upload requirements.
-   In Building View Components, clarify that additional i18n support may be provided by the browser, and is outside the scope of the framework.
-   In Building Controller Components, document 'validating' init-param, add defaults for various parameters, clarify that some web.xml settings are not Struts-specific.
-   Tag library documentation: Moved under User's Guide.
-   Reorganized to separate 1.0 material from nightly build material.

**MailReader Example Application Changes**

The following changes and bug fixes to the Struts MailReader Example Application have occurred:

-   Add Russian and Japanese translations of the application resources and set the character set for the example JSP pages to "UTF-8" so that it can display either English or Japanese.
-   Exchange "name" for "attribute" properties for Edit mappings in Struts configuration file.
-   Remove references to saving database data from "tour" document, since this functionality was removed.

**Template Example Application Changes**

The following changes and bug fixes to the Struts Template Example Application have occurred:

-   None.

**Exercise Taglib Example Application Changes**

The following changes and bug fixes to the Struts Exercise Taglib Example Application have occurred:

-   Added test case for \.html.md:link\> using "action" attribute.
-   Added test case for \.html.md:select\> using \<html:options\> based on a collection saved in the page context.

### <span id="Whats_different"></span>What's different?

This section provides links to the Struts JavaDoc for any classes that have been added or deprecated since the Struts 1.0 release.

**Previously deprecated classes and packages removed in Struts 1.1**

-   Removed: `org.apache.struts.utils.BeanUtils` , `org.apache.struts.utils.ConvertUtils` , and `org.apache.struts.utils.PropertyUtils` - replaced by [`org.apache.commons.beanutils`](http://jakarta.apache.org/commons/beanutils.html.md)
-   Removed: `org.apache.struts.util.ArrayStack` , `org.apache.struts.util.FastArrayList` , `org.apache.struts.util.FastHashMap` , `org.apache.struts.util.FastTreeMap` - replaced by [`org.apache.commons.collections`](http://jakarta.apache.org/commons/collections.html.md)
-   Removed: `org.apache.struts.digester.*` - replaced by [`org.apache.commons.digester`](http://jakarta.apache.org/commons/digester.html.md)
-   Removed: The `struts-config.dtd` - Replaced by [`struts-config_1_1.dtd`](http://jakarta.apache.org/struts/dtds/struts-config_1_1.dtd) .
-   Removed: The omnibus "struts" taglib and its associated TLD - replaced by separate bean, logic, and.html.md taglibs.
-   Removed: The "form" taglib and its associated TLD - replaced by (renamed as) the.html.md taglib.

**Packages added in Struts 1.1**

-   [config](http://jakarta.apache.org/struts/api/org/apache/struts/config/package-summary.html.md)
-   [taglib.nested](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/nested/package-summary.html.md)
-   [taglib.nested.bean](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/nested/bean/package-summary.html.md)
-   [taglib.nested.html.md](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/nested/html/package-summary.html)
-   [taglib.nested.logic](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/nested/logic/package-summary.html.md)
-   [validator](http://jakarta.apache.org/struts/api/org/apache/struts/validator/package-frame.html.md)

**Classes added in Struts 1.1**

action

-   [ActionMessage](http://jakarta.apache.org/struts/api/org/apache/struts/action/ActionMessage.html.md)
-   [ActionMessages](http://jakarta.apache.org/struts/api/org/apache/struts/action/ActionMessages.html.md)
-   [DynaActionForm](http://jakarta.apache.org/struts/api/org/apache/struts/action/DynaActionForm.html.md)
-   [DynaActionFormClass](http://jakarta.apache.org/struts/api/org/apache/struts/action/DynaActionFormClass.html.md)
-   [ExceptionHandler](http://jakarta.apache.org/struts/api/org/apache/struts/action/ExceptionHandler.html.md)
-   [RequestProcessor](http://jakarta.apache.org/struts/api/org/apache/struts/action/RequestProcessor.html.md)

actions

-   [LookupDispatchAction](http://jakarta.apache.org/struts/api/org/apache/struts/actions/LookupDispatchAction.html.md)

taglib.html.md

-   [FrameTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib.html.md/FrameTag.html)
-   [JavascriptValidatorTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib.html.md/JavascriptValidatorTag.html)
-   [MessagesTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib.html.md/MessagesTag.html)
-   [OptionsCollectionTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib.html.md/OptionsCollectionTag.html)

taglib.logic

-   [EmptyTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/logic/EmptyTag.html.md)
-   [MessagesNotPresentTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/logic/MessagesNotPresentTag.html.md)
-   [MessagesPresentTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/logic/MessagesPresentTag.html.md)

upload

-   [CommonsMultipartRequestHandler](http://jakarta.apache.org/struts/api/org/apache/struts/upload/CommonsMultipartRequestHandler.html.md)

util

-   [LabelValueBean](http://jakarta.apache.org/struts/api/org/apache/struts/util/LabelValueBean.html.md)

**Classes with members added in Struts 1.1**

[action.Action](http://jakarta.apache.org/struts/api/org/apache/struts/action/Action.html.md)

-   ACTION\_SERVLET\_KEY
-   APPLICATION\_KEY
-   MESSAGE\_KEY
-   PLUG\_INS\_KEY
-   REQUEST\_PROCESSOR\_KEY
-   execute
-   getResources(javax.servlet.http.HttpServletRequest)
-   saveMessages

[action.A](http://jakarta.apache.org/struts/api/org/apache/struts/action/ActionServlet.html.md) [ctionServlet](http://jakarta.apache.org/struts/api/org/apache/struts/action/ActionServlet.html)

-   configDigester
-   convertHack
-   log
-   processor
-   getInternal
-   destroyApplications
-   destroyConfigDigester
-   getApplicationConfig
-   getRequestProcessor
-   initApplicationConfig
-   initApplicationDataSources
-   initApplicationPlugIns
-   initApplicationMessageResources
-   initConfigDigester
-   methods created for backward-compatiblity only
    -   defaultControllerConfig
    -   defaultFormBeansConfig
    -   defaultForwardsConfig
    -   defaultMappingsConfig
    -   defaultMessageResourcesConfig

[taglib.html.md.BaseHandlerTag](http://jakarta.apache.org/struts/api/org/apache/struts/taglib/html/BaseHandlerTag.html)

-   indexed
-   setIndexed
-   getIndexed

**Classes deprecated between Struts 1.0 and Struts 1.1**

action

-   ActionException
-   ActionFormBeans
-   ActionForwards
-   ActionMappings

**Classes with members deprecated between Struts 1.0 and Struts 1.1**

[action.Action](http://jakarta.apache.org/struts/api/org/apache/struts/action/Action.html.md)

-   FORM\_BEANS\_KEY
-   FORWARDS\_KEY
-   MAPPINGS\_KEY
-   getResources()
-   perform

[ActionServlet](http://jakarta.apache.org/struts/api/org/apache/struts/action/ActionServlet.html.md)

-   findDataSource
-   findFormBean
-   findForward
-   findMapping
-   initDataSources
-   methods created for backward-compatiblity only
    -   defaultControllerConfig
    -   defaultFormBeansConfig
    -   defaultForwardsConfig
    -   defaultMappingsConfig
    -   defaultMessageResourcesConfig

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


