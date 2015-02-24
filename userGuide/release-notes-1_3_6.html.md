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

<span id="a6.1_Release_Notes_-_Version_1.3.6"></span>6.1 Release Notes - Version 1.3.6
--------------------------------------------------------------------------------------

> *"I've had nothing yet, so I can't take more."*
>
> *"You mean you can't take less. It's very easy to take more than nothing."*

<span id="release_notes"></span>
### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place to Struts, since the [Version 1.3.5](release-notes-1_3_5.html.md) distribution. To keep up-to-date on all changes to the framework, subscribe to the (commits at struts.apache.org) list. To preview our plans for upcoming changes, please visit the [Roadmap page.](../roadmap.html)

-   **Notes on upgrading** are maintained in the [Wiki Upgrade pages.](http://wiki.apache.org/struts/StrutsUpgrade) The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter.](installation.html.md)

<span id="dependencies"></span>
### <span id="Dependencies"></span>Dependencies

The following dependencies have changed:

-   **Validator 1.3.1** - [Commons Validator](http://jakarta.apache.org/commons/validator/) has been upgraded to [Version 1.3.1](http://jakarta.apache.org/commons/validator/changes-report.html.md) - as well as a number of bugfixes, compressed versions of the JavaScript routines are provided which can be configured using the new `validator-rules-compressed.xml` config file.
-   **Digester 1.8** - [Commons Digester](http://jakarta.apache.org/commons/digester/) has been upgraded to [Version 1.8](http://jakarta.apache.org/commons/digester/commons-digester-1.8/RELEASE-NOTES.txt) to fix issue [DIGESTER-29](http://issues.apache.org/jira/browse/DIGESTER-29).

<span id="Highlight"></span>
### <span id="Highlights_of_Changes"></span>Highlights of Changes

The purpose of this section is to highlight the new features since the [Version 1.3.5 distribution.](release-notes-1_3_5.html.md) For more detail, see the Project Info reports for each component, which include a list of external dependencies.

You can also access to the Apache Struts source repository and change logs directly through both [web browser](http://svn.apache.org/viewcvs.cgi/struts/struts1/trunk/?root=Apache-SVN) and [Subversion client](http://www.apache.org/dev/version-control.html.md) interfaces.

#### Action ID

An action mapping may now may be given an identifier by the new `actionId` property which uniquely identifies the mapping within a module:

    <action path="/person/view" type="..." input="...">
        <set-property property="actionId" value="viewPersonAction" />
        <forward name="success" path="person.jsp" />
    </action>

Just as the `TilesRequestProcessor` could recognize a tile definition and resolve it to the intended JSP, so does Struts now have built-in recognition for URIs that begin with an `actionId` and will automatically translate forwards. Both these forwards below will be resolved internally to `/person/view.do` (with parameters included):

    <forward name="success" path="viewPersonAction" />
    <forward name="success" path="viewPersonAction?fruit=banana&color=yellow" />

You can effectively eliminate all URI management throughout the Struts configuration files **and** within JSP. The tag libraries are also updated to recognize the `actionId`:

    .html.md:form action="savePersonAction">...</html:form>
    .html.md:link action="viewPersonAction">...</html:link>

Note: It is good practice to name the `actionId` as *entityAction* to distinguish the identifier from, perhaps, a Tiles definition named *entityPage*.

#### Internationalization (I18N) Tag Properties

Struts tag libraries now include the HTML I18N properties. This allows sites that specialize in internationalization to specify both bi-directional text and language at the tag level:

    .html.md:link action="viewPersonAction" dir="ltor" lang="es"/>vea a persona</html:link>

#### Dynamic Link Parameters

The Struts `.html.md:link>`, `<html:frame>`, `<html:rewrite>` tag libaries now allow their bodies to nest the new `<html:param>` tag. This is useful when it is awkward (or inappropriate) to pass in existing parameters as a `Map`, which is still supported and will be appened to any present `<html:param>` tags:

    .html.md:link action="viewPersonAction">
        View Profile of A Struts Developer
        .html.md:param name="id" value="1" />
        .html.md:param name="name" value="Ted Husted" />
    <.html.md:link>

#### Property MessageResources Modes

`PropertyMessageResources` now has a *compatibility mode* option which allows it to be configured to operate in modes compatible with either *JSTL* or `PropertyResourceBundle` (as well as the *backwardly compatible* default mode). To use the new modes configure the the message resources in the `struts-config.xml` in the following way (**note** the use of the **key** attribute in `<set-property>`):

    <message-resources parameter="....">
        <set-property key="mode" value="JSTL"/>     // JSTL mode
    </message-resources>

    <message-resources parameter="....">
        <set-property key="mode" value="resource"/> // PropertyResourceBundle mode
    </message-resources>

### Issue Tracking

#### Bug

-   [[STR-2894](http://issues.apache.org/struts/browse/STR-2894)] - The \<form-bean\> type attribute should be optional
-   [[STR-2903](http://issues.apache.org/struts/browse/STR-2903)] - MappingDispatchAction throws an error when mapping.getParameter returns null
-   [[STR-2916](http://issues.apache.org/struts/browse/STR-2916)] - Arbitrary properties don't get copied when creating ActionRedirect objects based on an existing ForwardConfig
-   [[STR-2917](http://issues.apache.org/struts/browse/STR-2917)] - ForwardConfig inheritance doesn't work when trying to inherit global forwards
-   [[STR-2920](http://issues.apache.org/struts/browse/STR-2920)] - Broken link to "MessageResources" in user guide
-   [[STR-2922](http://issues.apache.org/struts/browse/STR-2922)] - Broken Link in User Guide
-   [[STR-2932](http://issues.apache.org/struts/browse/STR-2932)] -.html.md:option tag does not apply any filtering to escape HTML-sensitive characters
-   [[STR-2935](http://issues.apache.org/struts/browse/STR-2935)] - Tiles resource chain-config.xml missing RemovedCachedMessages and SetOriginalURI
-   [[STR-2936](http://issues.apache.org/struts/browse/STR-2936)] - Incorrect validator name floatRange used in maxlength error
-   [[STR-2955](http://issues.apache.org/struts/browse/STR-2955)] - extending action does not pick up the correct validate attribute
-   [[STR-2966](http://issues.apache.org/struts/browse/STR-2966)] - s:commandLink doesn't work with Apache Trinidad or Oracle's ADF Faces
-   [[STR-2967](http://issues.apache.org/struts/browse/STR-2967)] -.html.md:image takes a "module-aware" path but does not allow module to be specified
-   [[STR-2971](http://issues.apache.org/struts/browse/STR-2971)] - one of validator.Resources.getActionMessage method does not respect message's "bundle" attribute
-   [[STR-2972](http://issues.apache.org/struts/browse/STR-2972)] - LazyValidatorForm cannot be saved in the session
-   [[STR-2973](http://issues.apache.org/struts/browse/STR-2973)] - multiple lifecycle (FIXME in code)
-   [[STR-2977](http://issues.apache.org/struts/browse/STR-2977)] - ELFormTagBeanInfo wrongly references ELTextTag
-   [[STR-2985](http://issues.apache.org/struts/browse/STR-2985)] - Validate language and country according to RFC2616 in HtmlTag
-   [[STR-2987](http://issues.apache.org/struts/browse/STR-2987)] - Scripting Mailreader: cannot log out

#### Improvement

-   [[STR-2077](http://issues.apache.org/struts/browse/STR-2077)] - Provide a `PropertyResourceBundle` compatibility option for PropertyMessageResources
-   [[STR-2925](http://issues.apache.org/struts/browse/STR-2925)] - Provide a *JSTL* compatibility option for PropertyMessageResources
-   [[STR-2839](http://issues.apache.org/struts/browse/STR-2839)] - Create aggregated Javadocs
-   [[STR-2951](http://issues.apache.org/struts/browse/STR-2951)] - Various documentation improvements
-   [[STR-2952](http://issues.apache.org/struts/browse/STR-2952)] - Maven build and infrastructure improvements
-   [[STR-2958](http://issues.apache.org/struts/browse/STR-2958)] - ClassNotFoundExceptions are swallowed by FormPropertyConfig
-   [[STR-2980](http://issues.apache.org/struts/browse/STR-2980)] - Typo in documentation: "indefinately"
-   [[STR-2981](http://issues.apache.org/struts/browse/STR-2981)] - Adjust AbstractAuthorizeAction to allow custom code to throw its own UnauthorizedActionException
-   [[STR-2982](http://issues.apache.org/struts/browse/STR-2982)] - Complete JavaDoc package summaries

#### New Feature

-   [[STR-746](http://issues.apache.org/struts/browse/STR-746)] - Add \.html.md:param\> for multiple parameters
-   [[STR-1559](http://issues.apache.org/struts/browse/STR-1559)] - Need Bidirectional support for RtoL languages in.html.md:html tag
-   [[STR-2864](http://issues.apache.org/struts/browse/STR-2864)] - Add actionId attribute to action mapping
-   [[STR-2983](http://issues.apache.org/struts/browse/STR-2983)] - Provide a new *compressed* version of the validator-rules.xml (requires [Commons Validator 1.3.1](http://jakarta.apache.org/commons/validator/))

#### Task

-   [[STR-2942](http://issues.apache.org/struts/browse/STR-2942)] - Use the DTDDoc plugin to generate HTML formatted DTD documentation
-   [[STR-2944](http://issues.apache.org/struts/browse/STR-2944)] - Update the dtds whenever the top-level site is published
-   [[STR-2968](http://issues.apache.org/struts/browse/STR-2968)] - ASF Source Header and Copyright Notice Policy
-   [[STR-2978](http://issues.apache.org/struts/browse/STR-2978)] - Struts 1.3.6 omnibus

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


