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
-   **Release Notes**
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

<span id="a6.1_Release_Notes_-_Version_1.3.10"></span>6.1 Release Notes - Version 1.3.10
----------------------------------------------------------------------------------------

<span id="release_notes"></span>
### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place to Struts, since the [Version 1.3.9](release-notes-1_3_9.html.md) distribution. To keep up-to-date on all changes to the framework, subscribe to the (commits at struts.apache.org) list. To preview our plans for upcoming changes, please visit the [Roadmap page.](../roadmap.html)

-   **Notes on upgrading** are maintained in the [Wiki Upgrade pages.](http://wiki.apache.org/struts/StrutsUpgrade) The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter.](installation.html.md)

<span id="Highlight"></span>
### <span id="Issue_Tracking"></span>Issue Tracking

#### Bug

-   [[STR-2630](https://issues.apache.org/struts/browse/STR-2630)] - Taglib documentation does not render embedded HTML
-   [[STR-2802](https://issues.apache.org/struts/browse/STR-2802)] - Validator validwhen cannot test between two different indices in array
-   [[STR-3026](https://issues.apache.org/struts/browse/STR-3026)] - Linked examples hosted by "Planet Struts" nonexistant
-   [[STR-3052](https://issues.apache.org/struts/browse/STR-3052)] - ImgTag missing actionId support
-   [[STR-3054](https://issues.apache.org/struts/browse/STR-3054)] - EL-Example errors
-   [[STR-3070](https://issues.apache.org/struts/browse/STR-3070)] - Postback forms cause NPE with classic RequestProcessor
-   [[STR-3076](https://issues.apache.org/struts/browse/STR-3076)] - PasswordTag doesn't define the attribute onselect
-   [[STR-3080](https://issues.apache.org/struts/browse/STR-3080)] - XLST instead of XSLT
-   [[STR-3081](https://issues.apache.org/struts/browse/STR-3081)] - Uploading a File using LazyDynaBean causes ClassCastException
-   [[STR-3082](https://issues.apache.org/struts/browse/STR-3082)] - Incomplete error message when failing to create a form bean
-   [[STR-3084](https://issues.apache.org/struts/browse/STR-3084)] - Error on Tiles examples page
-   [[STR-3088](https://issues.apache.org/struts/browse/STR-3088)] - N-length empty strings not treated as \*null\* by validwhen
-   [[STR-3093](https://issues.apache.org/struts/browse/STR-3093)] - Taglibs TLD do not match tag implementations
-   [[STR-3097](https://issues.apache.org/struts/browse/STR-3097)] - Generating site fails
-   [[STR-3110](https://issues.apache.org/struts/browse/STR-3110)] - PropertyUtils.clearDescriptors() call in ActionServlet.destroy() method is causing appliction classloader memory leak on Weblogic Portal
-   [[STR-3112](https://issues.apache.org/struts/browse/STR-3112)] - Generated javascript is wrong to set focus on control that is of array
-   [[STR-3143](https://issues.apache.org/struts/browse/STR-3143)] - Struts jar remains "in-use" preventing dynamic redeployment
-   [[STR-3144](https://issues.apache.org/struts/browse/STR-3144)] - Bean Taglib Documentation Has Been Unreadable FOR YEARS...
-   [[STR-3146](https://issues.apache.org/struts/browse/STR-3146)] - TLD reports contain broken hyperlinks
-   [[STR-3161](https://issues.apache.org/struts/browse/STR-3161)] - Servlet not injected into newly created action in higly concurrent env

#### Improvement

-   [[STR-1496](https://issues.apache.org/struts/browse/STR-1496)] -.html.md:form focus and focusIndex problem
-   [[STR-1709](https://issues.apache.org/struts/browse/STR-1709)] - FormTag: Add check for nonexistent form field in focus javascript
-   [[STR-2810](https://issues.apache.org/struts/browse/STR-2810)] - autocomplete attribute

#### Task

-   [[STR-3055](https://issues.apache.org/struts/browse/STR-3055)] - Figure out the 'disabled="${!empty pageScope}" in EL-Example
-   [[STR-3134](https://issues.apache.org/struts/browse/STR-3134)] - Upgrade JSTL from 1.0.2 to latest 1.0.6
-   [[STR-3150](https://issues.apache.org/struts/browse/STR-3150)] - Upgrade Commons Chain to 1.2
-   [[STR-3163](https://issues.apache.org/struts/browse/STR-3163)] - Upgrade Commons BeanUtils
-   [[STR-3171](https://issues.apache.org/struts/browse/STR-3171)] - Lock down Maven plugin dependencies
-   [[STR-3172](https://issues.apache.org/struts/browse/STR-3172)] - Require Tomcat 5.5 for integration testing

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


