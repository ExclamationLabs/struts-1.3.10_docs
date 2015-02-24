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

<span id="a6.1_Release_Notes_-_Version_1.3.5"></span>6.1 Release Notes - Version 1.3.5
--------------------------------------------------------------------------------------

> *"I've had nothing yet, so I can't take more."*
>
> *"You mean you can't take less. It's very easy to take more than nothing."*

**SPECIAL NOTE ON UPGRADING - README FIRST!** - If you use the standard **CANCEL BUTTON** in your application and validate is set to true for that mapping, you **MUST** also specify "cancellable=true" in the mapping, otherwise, an InvalidCancelException will be thrown if the Cancel button is used. See the new [Opt-In Cancel Handling](release-notes-1_3_1.html.md#opt-in) feature for more.

                            <action path="/ActionThatCanBeCancelled"
                                    validate="true"
                                    cancellable="true"
                                    ...
                             </action>
                        

<span id="release_notes"></span>
### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place to Struts, since the [Version 1.3.3](release-notes-1_3_3.html.md) distribution. To keep up-to-date on all changes to the framework, subscribe to the (commits at struts.apache.org) list. To preview our plans for upcoming changes, please visit the [Roadmap page](../roadmap.html) .

-   **Notes on upgrading** are maintained in the [Wiki Upgrade pages.](http://wiki.apache.org/struts/StrutsUpgrade) The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter.](installation.html.md)

<span id="Highlight"></span>
### <span id="Highlights_of_Changes"></span>Highlights of Changes

The purpose of this section is to highlight the new features since the [Version 1.3.3 distribution](release-notes-1_3_3.html.md). For more detail, see the Project Info reports for each component, which include a list of external dependencies.

You can also access to the Apache Struts source repository and change logs directly through both [web browser](http://svn.apache.org/viewcvs.cgi/struts/struts1/trunk/?root=Apache-SVN) and [Subversion client](http://www.apache.org/dev/version-control.html.md) interfaces.

### Components

The Struts 1.3.5 distribution contains the eight components: Core, Applications, EL, Extras, Faces, Scripting, Taglib, and Tiles.

The entire Struts distribution, including the website, is being built with Maven 2. But, of course, you can continue to build your own projects any way you like!

#### Specification Changes

The 1.3.x series of Struts has a minimum requirement of the following specification versions:

-   Java Servlet 2.3 and JavaServer Pages (JSP) 1.2
-   Java 2 Standard Platform Edition (J2SE) 1.4

#### Dependency Changes

A following software dependency change applies to this distribution:

-   Upgraded to Commons Validator 1.3 (previously 1.2) - see [Validator 1.3.0 Change Report.](http://jakarta.apache.org/commons/validator/changes-report.html.md)

### Resolved Issues

The following issues have been resolved since the 1.3.3 test build:

#### Bugs

-   [[STR-2901](http://issues.apache.org/struts/browse/STR-2901)] - Map-backed forms won't work with ')' characters in keys
-   [[STR-2890](http://issues.apache.org/struts/browse/STR-2890)] - DEFINE tag causes compilation issues
-   [[STR-2887](http://issues.apache.org/struts/browse/STR-2887)] - TagUtils.instance is private final. Please allow to change the instance with a custom one! Maybe put it protected only!
-   [[STR-2883](http://issues.apache.org/struts/browse/STR-2883)] - The command/action corresponding to RequestProcessor.processCachedMessages() method appears to be missing in 1.3
-   [[STR-2881](http://issues.apache.org/struts/browse/STR-2881)] - PerformForward command not honoring "module" property of ForwardConfig
-   [[STR-2879](http://issues.apache.org/struts/browse/STR-2879)] - when used in modules, TilesPreProcessor not backwards compatible with 1.2.x
-   [[STR-2877](http://issues.apache.org/struts/browse/STR-2877)] - TestModuleConfig fails when run offline
-   [[STR-2876](http://issues.apache.org/struts/browse/STR-2876)] - Tiles 1.1 DTD registration is missing from XmlParser
-   [[STR-2872](http://issues.apache.org/struts/browse/STR-2872)] - Section "4.3.3 Map-backed ActionForms" of User's Manual contains a dead link
-   [[STR-2870](http://issues.apache.org/struts/browse/STR-2870)] - The Specification-Title in the jar file manifests is corrupted
-   [[STR-2866](http://issues.apache.org/struts/browse/STR-2866)] - Struts Tiles jar is missing dtd, tld and chain config files
-   [[STR-2862](http://issues.apache.org/struts/browse/STR-2862)] - Cannot load a validator resource from '/WEB-INF/validator-rules.xml
-   [[STR-2859](http://issues.apache.org/struts/browse/STR-2859)] - When using \.html.md:html xhtml="true"\> the form name is not used but the id, and the client validation using javascript fails
-   [[STR-2795](http://issues.apache.org/struts/browse/STR-2795)] - Postback Forms - Caching and Modules
-   [[STR-2527](http://issues.apache.org/struts/browse/STR-2527)] - Attributes with \<rtexprvalue\>false\</rtexprvalue\> in TLD prevent EL evaluation
-   [[STR-2496](http://issues.apache.org/struts/browse/STR-2496)] - [struts-faces] Example applications don't work?!
-   [[STR-2493](http://issues.apache.org/struts/browse/STR-2493)] - [struts-faces] ErrorsRenderer assumes ActionErrors
-   [[STR-1892](http://issues.apache.org/struts/browse/STR-1892)] - timezone support for bean:write tag

#### Tasks

-   [[STR-2898](http://issues.apache.org/struts/browse/STR-2898)] - Rename Struts Action 1 to Struts 1
-   [[STR-2892](http://issues.apache.org/struts/browse/STR-2892)] - Remove old cactus config
-   [[STR-2871](http://issues.apache.org/struts/browse/STR-2871)] - Rename the release notes so that the filename contains a single period
-   [[STR-2853](http://issues.apache.org/struts/browse/STR-2853)] - Configure the CheckStyle plugin to use the struts\_checks.xml file

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


