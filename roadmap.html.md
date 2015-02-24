<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](index.html.md)
-   [Learning](learning.html.md)
-   **Roadmap**
-   [Releases](downloads.html.md)

##### Documentation

-   [User Guide](userGuide/index.html.md)
-   [FAQs and HOWTOs](faqs/index.html.md)
-   [Release Notes](userGuide/release-notes.html.md)
-   [Javadoc](apidocs/index.html.md)
-   [DTDDoc](dtddoc/index.html.md)

##### Support

-   [User Mailing List](mail.html.md)
-   [Issue Tracker (JIRA)](http://issues.apache.org/struts/)
-   [Wiki Pages](http://wiki.apache.org/struts/)

##### Components

-   [Struts Apps](struts-apps/index.html.md)
-   [Struts EL](struts-el/index.html.md)
-   [Struts Extras](struts-extras/index.html.md)
-   [Struts Faces](struts-faces/index.html.md)
-   [Struts Scripting](struts-scripting/index.html.md)
-   [Struts Taglib](struts-taglib/index.html.md)
-   [Struts Tiles](struts-tiles/index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Development_Roadmap"></span>Development Roadmap
---------------------------------------------------------

<span id="roadmap"></span>
This document outlines some of changes we expect to see in future releases of Struts 1.

This document is provided for discussion purposes only. All releases and changes to the codebase are subject to [a vote](http://struts.apache.org/bylaws.html.md) of the [Apache Struts PMC.](http://struts.apache.org/volunteers.html#pmc)

<span id="JIRA"></span>
### <span id="JIRA_Queries"></span>JIRA Queries

The Apache Struts Projects uses the [JIRA issuer tracker](http://issues.apache.org/struts/) to manage problem reports and enhancement suggestions. For your convenience, here are some common JIRA queries:

-   [Open Issues (Struts 1)](http://issues.apache.org/struts/browse/STR?report=com.atlassian.jira.plugin.system.project:openissues-panel)
-   [Open Issues (Struts 2)](http://issues.apache.org/struts/browse/WW?report=com.atlassian.jira.plugin.system.project:openissues-panel)
-   [Open Issues (Sandbox)](http://issues.apache.org/struts/browse/SB?report=com.atlassian.jira.plugin.system.project:openissues-panel)

<span id="Struts_1_x"></span>
### <span id="Struts_1.x"></span>Struts 1.x

Releases in the 1.x series will focus on refactoring of existing functionality, with a continued emphasis on backward compatibility.

New features are being added to the 1.x series, but only if backward compatability with the prior release can be retained. The framework's API is evolving through a strict deprecate/replace/remove protocol. Developers are encouraged to stay current with the "best available" release and to observe deprecation warnings. Features are deprecated before removal, and deprecated features are removed in a subsequent release.

Throughout the 1.x series, there will be a continued emphasis on expanding unit test coverage. Bug reports should include a failing test case when possible. Proposals for new features should include a working test suite. (Creating features through Test Driven Development is encouraged.)

Enhancement requests are logged in JIRA as they are suggested. **The listing of an enhancement in JIRA does not imply that it is being "planned",** merely that someone has suggested it, and the idea hasn't been ruled out (yet).

Future release [milestones](#milestones) are provided for enhancements which are being actively planned or developed but may not be ready for the current release. If a report has not been tagged for a specific milestone by a working developer, then **it may never be implemented** . When developers (including non-Committers) are actually working on an enhancement, they should re-tag it for a specific release milestone, such as "1.4.1" or "1.4.2".

If an enhancement has not been tagged for a specific target, feel free to start working on it yourself. Many of our best features have been contributed by developers, just like you. If you are working on an enhancement, post a note on the ticket that you are working on an enhancement and then post a patch as soon as possible. If the development effort doesn't succeed, post a note to the ticket explaining what problem you had creating the enhancement, so that other developers can explore alternatives.

### <span id="Development_Milestones"></span>Development Milestones

<span id="milestones"></span>
These are milestones of where we have been, where we are, and possibly where we are going.

<span id="struts_1_0"></span>
### <span id="Release_1.0.x_complete"></span>Release 1.0.x (complete)

Major refactoring of framework internals to provide support for modules and a new "config" object series. Bundles Struts Tiles and Struts Validator into main distribution. The initial release of Struts EL is provided as an optional package.

<span id="struts_1_1"></span>
### <span id="Release_1.1.x_complete"></span>Release 1.1.x (complete)

Split internal libraries into their own projects in Jakarta Commons. Added support for modules and plugins.

<span id="struts_1_2"></span>
### <span id="Release_1.2.x_complete"></span>Release 1.2.x (complete)

Added support for wildcard mappings, internal project restructuring, removed deprecations, other minor enhancements.

<span id="struts_1_3_x"></span>
### <span id="Release_1.3.x_pending"></span>Release 1.3.x (pending)

Evolutionary enhancements to product base, based on existing features or codebases.

-   Divided distribution into components with individual JARs
-   Support for Maven 2 builds
-   Moved action to "Struts Chain" Request Processor
-   Enhanced all configs to extend one configuration element from another, as is done with Tiles Definitions

Next: [User Guide](userGuide/index.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


