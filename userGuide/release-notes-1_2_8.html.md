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

<span id="a6.1_Release_Notes_-_Version_1.2.8"></span>6.1 Release Notes - Version 1.2.8
--------------------------------------------------------------------------------------

### <span id="Introduction"></span>Introduction

The main motivation for releasing Struts 1.2.8 is to fix a *Cross Site Scripting* (XSS) vulnerability which has been identified by Hacktics.com. More details available on the [Wiki](http://wiki.apache.org/struts/StrutsXssVulnerability) .

This section contains release notes for changes that have taken place since [Version 1.2.7](release-notes-1_2_7.html.md) . To keep up-to-date on all changes to Struts, subscribe to the dev@ list.

**Notes on upgrading** are maintained in the [Wiki Upgrade pages](http://wiki.apache.org/struts/StrutsUpgrade) . The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter](installation.html.md) .

### Version 1.2.8

After [Version 1.2.6 was tagged](http://svn.apache.org/viewcvs.cgi/struts/core/tags/STRUTS_1_2_6/) the [1.2 Branch](http://svn.apache.org/viewcvs.cgi/struts/core/branches/STRUTS_1_2_BRANCH/) was created and work started on the next version ( *1.3.x series* ). Work has continued on both versions and *Revision* numbers shown in brackets are where a change has been ported from the current development version into the *1.2 Branch* .

| Modification | Revision                                                                                                                                                                                        | Bugzilla                                                         | Description                                                                                            |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| 2005-11-07   | [331261](http://svn.apache.org/viewcvs?rev=331261&view=rev) ( [331265](http://svn.apache.org/viewcvs.cgi?rev=331265&view=rev) )                                                                 | [37131](http://issues.apache.org/bugzilla/show_bug.cgi?id=37131) | Escape newlines in Validator variables.                                                                |
| 2005-11-05   | [191272](http://svn.apache.org/viewcvs?rev=191272&view=rev) and [192949](http://svn.apache.org/viewcvs?rev=192949&view=rev) ( [331056](http://svn.apache.org/viewcvs.cgi?rev=331056&view=rev) ) | [35127](http://issues.apache.org/bugzilla/show_bug.cgi?id=35127) | Changing rendering of the form name to use the 'id' attribute when in XHTML strict mode.               |
| 2005-11-05   | [331060](http://svn.apache.org/viewcvs?rev=331060&view=rev) ( [331055](http://svn.apache.org/viewcvs.cgi?rev=331055&view=rev) )                                                                 | *n/a*                                                            | Fix for Struts XSS Vulnerability - remove uri from error messages.                                     |
| 2005-08-31   | [265661](http://svn.apache.org/viewcvs?rev=265661&view=rev) ( [265658](http://svn.apache.org/viewcvs.cgi?rev=265658&view=rev) )                                                                 | *n/a*                                                            | Remove I18nFactorySet copied code.                                                                     |
| 2005-08-29   | [264694](http://svn.apache.org/viewcvs?rev=264694&view=rev) ( [264684](http://svn.apache.org/viewcvs.cgi?rev=264684&view=rev) )                                                                 | [32584](http://issues.apache.org/bugzilla/show_bug.cgi?id=32584) | Provide config option to turn off MessageResources escape processing.                                  |
| 2005-08-29   | [226545](http://svn.apache.org/viewcvs?rev=226545&view=rev) ( [264662](http://svn.apache.org/viewcvs.cgi?rev=264662&view=rev) )                                                                 | [35833](http://issues.apache.org/bugzilla/show_bug.cgi?id=35833) | Fix bug where non-resource action messages only work for the first message in the messages list.       |
| 2005-06-20   | [191474](http://svn.apache.org/viewcvs?rev=191474&view=rev) ( [191475](http://svn.apache.org/viewcvs.cgi?rev=191475&view=rev) )                                                                 | [35421](http://issues.apache.org/bugzilla/show_bug.cgi?id=35421) | Correct link on the acquiring page to the maven generated nightly builds.                              |
| 2005-06-17   | [190794](http://svn.apache.org/viewcvs?rev=190794&view=rev) ( [191170](http://svn.apache.org/viewcvs.cgi?rev=191170&view=rev) )                                                                 | *n/a*                                                            | Update TagUtils to provide a more specific error message where properties on a formbean are not found. |
| 2005-06-16   | [191011](http://svn.apache.org/viewcvs.cgi?rev=191011&view=rev)                                                                                                                                 | [34460](http://issues.apache.org/bugzilla/show_bug.cgi?id=34460) | Update to the HTML tag library docs.                                                                   |
| 2005-06-16   | [191001](http://svn.apache.org/viewcvs?rev=191001&view=rev) ( [191002](http://svn.apache.org/viewcvs.cgi?rev=191002&view=rev) )                                                                 | [32313](http://issues.apache.org/bugzilla/show_bug.cgi?id=32313) | Update tag library configuration docs for Servlet 2.4.                                                 |
| 2005-06-15   | [190634](http://svn.apache.org/viewcvs?rev=190634&view=rev) ( [190779](http://svn.apache.org/viewcvs.cgi?rev=190779&view=rev) )                                                                 | [23864](http://issues.apache.org/bugzilla/show_bug.cgi?id=23864) | Filter.html.md sensitive characters in the \<html:radio\> tag's value.                                    |
| 2005-06-15   | [190804](http://svn.apache.org/viewcvs?rev=190804&view=rev) ( [190807](http://svn.apache.org/viewcvs.cgi?rev=190807&view=rev) )                                                                 | [3202](http://issues.apache.org/bugzilla/show_bug.cgi?id=3202)   | \.html.md:options\> tag logic updated to be more efficient with use of iterators.                         |
| 2005-06-15   | [190631](http://svn.apache.org/viewcvs?rev=190631&view=rev) ( [190780](http://svn.apache.org/viewcvs.cgi?rev=190780&view=rev) )                                                                 | [27861](http://issues.apache.org/bugzilla/show_bug.cgi?id=27861) | Add better error reporting to \<bean:define\> tag.                                                     |
| 2005-06-04   | [180002](http://svn.apache.org/viewcvs?rev=180002&view=rev) ( [180001](http://svn.apache.org/viewcvs.cgi?rev=180001&view=rev) )                                                                 | *n/a*                                                            | Add warning to ActionMapping.findForward() method if not found.                                        |
| 2005-05-27   | [178799](http://svn.apache.org/viewcvs.cgi?rev=178799&view=rev)                                                                                                                                 | [35108](http://issues.apache.org/bugzilla/show_bug.cgi?id=35108) | Add comment regarding jdbc20ext.jar and JDK to build.properties.sample.                                |
| 2005-05-18   | [170859](http://svn.apache.org/viewcvs?rev=170859&view=rev) ( [170858](http://svn.apache.org/viewcvs.cgi?rev=170858&view=rev) )                                                                 | [34949](http://issues.apache.org/bugzilla/show_bug.cgi?id=34949) | Add no-arg constructor to ModuleConfigImpl.                                                            |

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


