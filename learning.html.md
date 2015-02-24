<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](index.html.md)
-   **Learning**
-   [Roadmap](roadmap.html.md)
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

<span id="Docs"></span>
<span id="Learning_About_Struts"></span>Learning About Struts
-------------------------------------------------------------

The **official documentation** for the framework is provided online and may be built locally from the source code distribution using [Apache Maven 2](http://maven.apache.org/). To build the documentation, change to the subproject's folder and run

$ mvn site

For more help with building the website, visit the [Struts Maintenance - Website](http://wiki.apache.org/struts/StrutsMaintenanceWebsite) page.

Our documentation includes a [User Guide,](userGuide/index.html.md)[FAQs and Howto Guides,](./faqs/index.html) along with this top-level introduction.

The [Javadocs](apidocs/index.html.md) and [source code](http://svn.apache.org/viewcvs.cgi/struts/struts1/trunk/) can also be browsed.

<span id="Versions"></span>
### <span id="Documentation_Versions"></span>Documentation Versions

You are invited to preview the documentation online, and then install the documentation bundle locally for closer study.

**NOTE:** If you are previewing the documentation on the website, most of the links in this section will refer to the **Nightly Build.** When learning about the framework, **be sure to refer to the documentation for the version you are actually using.**

<span id="userGuide"></span>
### <span id="User_Guide"></span>User Guide

Our concise [**User Guide**](userGuide/index.html.md) introduces the Model-View-Controller architecture, and how it relates to the major components of the framework. If you want to find out "How it works", this is the place to start. Along with an architectural overview, the User Guide also includes detailed installation instructions and release notes for each version of the framework.

<span id="faqs"></span>
### <span id="FAQS_and_HOWTOs"></span>FAQS and HOWTOs

Our **FAQs** and **HOWTOs** are designed to fill in any gaps left by the Javadocs or User Guide.

-   Our [Kickstart FAQ](faqs/kickstart.html.md) answers the most common non-technical questions people first ask about the framework.
-   Our [Newbie FAQ](faqs/newbie.html.md) answers the most common technical questions asked developers using the framework for the first-time.

The **HOWTO Guides** are designed to help you get started with some of the optional extensions and components available for the framework. These include topics like using the Secure Socket Layer (SSL) protocol and how to unit test your applications.

If you have any comments on the pages you see here, they can be posted to the Wiki by following the link on the bottom of any page.

Of course, the only true documentation is the code itself. If you have any questions about how the framework actually works, do not hesitate to *use the source.* For the complete, buildable source code, see the "src" folder in your **source distribution.**

<span id="Javadocs"></span>
### <span id="Javadocs"></span>Javadocs

For more detail about a specific class or package, our [**Javadocs**](apidocs/index.html.md) are **surprisingly comprehensive and carefully maintained.** It is *strongly* recommended that you refer to the [Javadocs](apidocs/index.html) for each class as you begin to use it. This will help ensure that important features and options are not overlooked. *What you don't know, can't help you.*

<span id="Examples"></span>
### <span id="Struts_by_Example"></span>Struts by Example

To help you see how it all fits together, several example applications are bundled in the "webapp" folder in the distribution that demonstrate using the framework.

-   Blank - A simple template for starting new applications.
-   Cookbook - See various techniques in action and view the source code in place.
-   Examples - Various demonstration applications combined as separate modules:
    -   Exercise - A set of test pages that also demonstrate use of the custom tags.
    -   Upload - Demonstrates using the file upload facilities. (Based on Commons Upload.)
    -   Validator - Demonstrates using the Validator extension.
-   Faces - Demonstrates the Struts-Faces integration tag library.
-   [MailReader](http://opensource2.atlassian.com/confluence/oss/display/STRUTS/MailReader) - The original Struts example application. *Try me first!*

There are also many third-party example applications available for study, including these three:

-   [AppFuse](http://raibledesigns.com/wiki/Wiki.jsp?page=AppFuse) - Demonstrates using XDoclet with the framework, along with different security packages and Hibernate for database persistence.
-   [JPetStore](http://ibatis.apache.org/petstore.html.md) - A streamlined version of the Java Petstore application implemented with Struts and iBATIS database layer.
-   [LogWeb](http://www.codeczar.com/products/logweb/index.html.md) - A Struts webapp for configuring Log4J at runtime within a servlet container.

Other open source applications built using the framework include:

-   [Roller](http://rollerweblogger.org/page/project) - open source blog server.
-   [XPlanner](http://www.xplanner.org/) - project planning and tracking tool for eXtreme Programming (XP) teams.

<span id="More"></span>
### <span id="Learning_More_About_Struts"></span>Learning More About Struts

The Apache Struts [Mailing Lists](http://struts.apache.org/mail.html.md) are a treasure trove of useful, interactive information. The user list tends to carry a high volume, so always check the published documentation and one of the [**MAILING LIST ARCHIVES**](http://struts.apache.org/mail.html#Archives) before [posting a new question.](http://www.catb.org/~esr/faqs/smart-questions.html) Like as not, it's already been asked and answered.

If you really can't find the answer to your question in the [FAQs](#faqs) or one of the [list archives,](http://struts.apache.org/mail.html.md#Archives) you can post your query to the Apache Struts User list -- **BUT YOU MUST SUBSCRIBE TO THE [USER LIST](mailto:user-subscribe@struts.apache.org) OR THE [USER LIST DIGEST](mailto:user-digest-subscribe@struts.apache.org) BEFORE POSTING.**

The Apache Struts [**Wiki**](http://wiki.apache.org/struts) is a relatively new addition to our documentation team. Any Struts user (that means you!) is invited to post new material to the Wiki. However, the Wiki is not the place to ask incidental questions. **All support questions should be directed to the [Struts User list](http://struts.apache.org/mail.html.md) or other support forum.**

The [**Roadmap**](roadmap.html.md) page outlines our tentative plans for future development.

<span id="resources"></span>
### <span id="Community_Resources"></span>Community Resources

The framework has attracted a large and robust community of developers, which have created a vast number of Struts related resources. Several pages on our wiki are devoted to listing [Apache Struts resources.](http://wiki.apache.org/struts/StrutsResources)

For a comprehensive listing of all resources related to Apache Struts, including articles, books, and third-party extensions, for both Struts 1 and Struts 2, visit [Struts Central.](http://www.StrutsCentral.net/)

<span id="books"></span>
### <span id="Books_about_Struts"></span>Books about Struts

The Apache Software Foundation does not provide printed manuals, but several third-party books about Struts are available. Visit [Struts Central](http://www.StrutsCentral.net/Resources/Action/books.html.md) or the [Apache Bookstore](http://opensource.atlassian.com/confluence/oss/display/BOOKS/Books+about+Struts) for complete listings.

Next: [Roadmap](roadmap.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


