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

<span id="a6.1_Release_Notes_-_Version_1.3.2"></span>6.1 Release Notes - Version 1.3.2
--------------------------------------------------------------------------------------

**SPECIAL NOTE ON UPGRADING - README FIRST!** - If you use the standard **CANCEL BUTTON** in your application and validate is set to true for that mapping, you **MUST** also specify "cancellable=true" in the mapping, otherwise, an InvalidCancelException will be thrown if the Cancel button is used. See the new [Opt-In Cancel Handling](release-notes-1_3_1.html.md#opt-in) feature for more.

                            <action path="/ActionThatCanBeCancelled"
                                    validate="true"
                                    cancellable="true"
                                    ...
                             </action>
                        

<span id="release_notes"></span>
### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place to the Struts 1 project, previously known as "Struts Classic" since [Version 1.3.1](release-notes-1_3_1.html.md). To keep up-to-date on all changes to Struts, subscribe to the (commits at struts.apache.org) list. To preview our plans for upcoming changes, please visit the [Roadmap page](../roadmap.html) .

**Notes on upgrading** are maintained in the [Wiki Upgrade pages](http://wiki.apache.org/struts/StrutsUpgrade) . The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter](installation.html.md) .

<span id="Highlight"></span>
### <span id="Highlights_of_Changes"></span>Highlights of Changes

The purpose of this section is to highlight the new features since the Version 1.3.1 release. For more detail, see the Project Info reports for each subproject, which include a complete changelog and list of external dependencies.

You can also access to the Apache Struts source repository and change logs directly through both [web browser](http://svn.apache.org/viewcvs.cgi/struts/action/trunk/?root=Apache-SVN) and [Subversion client](http://www.apache.org/dev/version-control.html.md) interfaces.

### Struts

Since Struts 1.3.1, we have moved the Struts 1 related subprojects back into the Struts 1 project, leaving Struts and Struts Shale the two remaining subprojects. The Struts 1.3.2 release contains the following seven components: Core, Applications, EL, Extras, Scripting, Taglibs, and Tiles.

The Struts, including the website, is being built with Maven 2. But, of course, you can continue to build your own projects any way you like!

### Dependency Changes

#### Specification Changes

The 1.3.x series of Struts has a minumum requirement of the following specification versions:

-   Java Servlet 2.3 and JavaServer Pages (JSP) 1.2
-   Java 2 Standard Platform Edition (J2SE) 1.4

#### Software Component Changes

A following software dependency change applies to this release:

-   Upgraded to Commons Validator 1.3 (previously 1.2) - see [Validator 1.3.0 Release Notes](http://jakarta.apache.org/commons/validator/changes-report.html.md) .

### Bug Fixes

-   [[STR-2822](http://issues.apache.org/struts/browse/STR-2822)] - Wildcard action matcher does not set module in forward
-   [[STR-2838](http://issues.apache.org/struts/browse/STR-2838)] - Add necessary reports to site build
-   [[STR-2840](http://issues.apache.org/struts/browse/STR-2840)] - Release should include site docs

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


