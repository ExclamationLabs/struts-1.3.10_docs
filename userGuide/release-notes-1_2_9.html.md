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

<span id="a6.1_Release_Notes_-_Version_1.2.9"></span>6.1 Release Notes - Version 1.2.9
--------------------------------------------------------------------------------------

### <span id="Introduction"></span>Introduction

The main motivation for releasing Struts 1.2.9 is to fix three security issues which have been identified:

-   [Bug 38374](http://issues.apache.org/bugzilla/show_bug.cgi?id=38374) - Validation always skipped with Globals.CANCEL\_KEY.
-   [Bug 38534](http://issues.apache.org/bugzilla/show_bug.cgi?id=38534) - DOS attack, application hack.
-   [Bug 38749](http://issues.apache.org/bugzilla/show_bug.cgi?id=38749) - XSS vulnerability in LookupDispatchAction.

This section contains release notes for changes that have taken place since [Version 1.2.8](release-notes-1_2_8.html.md). To keep up-to-date on all changes to Struts, subscribe to the dev@ list.

**Notes on upgrading** are maintained in the [Wiki Upgrade pages](http://wiki.apache.org/struts/StrutsUpgrade). The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter](installation.html.md).

### Version 1.2.9

After [Version 1.2.6 was tagged](http://svn.apache.org/viewcvs.cgi/struts/core/tags/STRUTS_1_2_6/) the [1.2 Branch](http://svn.apache.org/viewcvs.cgi/struts/core/branches/STRUTS_1_2_BRANCH/) was created and work started on the next version (*1.3.x series*). Work has continued on both versions and *Revision* numbers shown in brackets are where a change has been ported from the current development version into the *1.2 Branch*.

| Modification | Revision                                                                                                                      | Bugzilla                                                         | Description                                                                               |
|--------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 2006-03-08   | [384234](http://svn.apache.org/viewcvs.cgi?rev=384234&view=rev) ([384235](http://svn.apache.org/viewcvs?rev=384235&view=rev)) | [37817](http://issues.apache.org/bugzilla/show_bug.cgi?id=37817) | TagUtils doesn't create XHTML compliant URLs using forwards defined with redirect="true". |
| 2006-03-08   | [384090](http://svn.apache.org/viewcvs.cgi?rev=384090&view=rev) ([384092](http://svn.apache.org/viewcvs?rev=384092&view=rev)) | [38343](http://issues.apache.org/bugzilla/show_bug.cgi?id=38343) | Add EventDispatchAction and EventActionDispatcher.                                        |
| 2006-03-07   | [383907](http://svn.apache.org/viewcvs.cgi?rev=383907&view=rev) ([383908](http://svn.apache.org/viewcvs?rev=383908&view=rev)) | [37685](http://issues.apache.org/bugzilla/show_bug.cgi?id=37685) | Javascript tag does not work on Mozilla.                                                  |
| 2006-03-07   | [383718](http://svn.apache.org/viewcvs.cgi?rev=383718&view=rev) ([383720](http://svn.apache.org/viewcvs?rev=383720&view=rev)) | [38749](http://issues.apache.org/bugzilla/show_bug.cgi?id=38749) | XSS vulnerability in LookupDispatchAction.                                                |
| 2006-02-15   | [379661](http://svn.apache.org/viewcvs.cgi?rev=379661&view=rev) ([377929](http://svn.apache.org/viewcvs?rev=377929&view=rev)) | [38534](http://issues.apache.org/bugzilla/show_bug.cgi?id=38534) | DOS attack, application hack.                                                             |
| 2006-02-14   | [377562](http://svn.apache.org/viewcvs.cgi?rev=377562&view=rev) ([377805](http://svn.apache.org/viewcvs?rev=377805&view=rev)) | [38374](http://issues.apache.org/bugzilla/show_bug.cgi?id=38374) | Validation always skipped with Globals.CANCEL\_KEY.                                       |
| 2006-01-31   | [373798](http://svn.apache.org/viewcvs.cgi?rev=373798&view=rev) ([373801](http://svn.apache.org/viewcvs?rev=373801&view=rev)) | [38461](http://issues.apache.org/bugzilla/show_bug.cgi?id=38461) | struts-el.html.md tag library errorKey not using documented default value.                   |

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


