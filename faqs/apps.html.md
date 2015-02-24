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

<span id="How_to_Build_Applications"></span>How to Build Applications
---------------------------------------------------------------------

This document outlines one possible sequence of development steps that can be followed to create a Struts application. It is not intended as a complete description of each referenced development activity. More detailed documentation is available elsewhere and is referenced by "(more...)" links where possible.

For those who are short on time and/or patience, you can get a Struts application up and running in a matter of minutes thanks to Maven's archetype feature.

NOTE - as of the time of this writing (10/16/2006), the specified version in this example has not been released. Once this has been released, this note can be removed and the archetype will work fine.

                               $ cd ~/projects
                               
                                               $ mvn archetype:create                                \
                                                     -DarchetypeGroupId=org.apache.struts            \
                                                     -DarchetypeArtifactId=struts-archetype-blank    \
                                                     -DarchetypeVersion=1.3.5                        \
                                                     -DgroupId=com.example                           \
                                                     -DpackageName=com.example.projectname           \
                                                     -DartifactId=my-webapp
                                                     
                               $ cd my-webapp
                               
                               $ mvn install
                               
                               $ mvn jetty:run
                        

### <span id="Caveats"></span>Caveats

1.  Requirements development and design are outside of the scope of this document.
2.  For help installing the framework, see the [Getting Started](../userGuide/installation.html.md) chapter.
3.  There are many other ways to approach development with the framework and there are many other features available besides the ones discussed below. This document outlines only one way to get started.
4.  This document focuses on form/data centric applications, but may also work with other types of applications.
5.  This material was originally written for Struts 1.1 (beta 2), and reviewed for the 1.3.5 distribution.

### <span id="Overview"></span>Overview

1.  Implement data entry forms as JSP files.
2.  Implement one or more `ActionForm` descendents to buffer data between JSPs and Actions.
3.  Create an XML document that defines the validation rules for your application.
4.  Implement one or more `Action` descendents to respond form submissions.
5.  Create `struts-config.xml` to associate forms with actions.
6.  Create or update `web.xml` to reference `ActionServlet.`
7.  Parallel Tasks
    1.  Building
    2.  Unit Testing
    3.  Deployment

### <span id="Details"></span>Details

1.  Implement data entry forms as JSP files.
    1.  Use elements from the .html.md` taglib to define the form elements. [(more...)](../struts-taglib/tagreference.html#struts-html.tld)
    2.  Use `message` and other elements from the `bean` taglib to define the labels and other static text of the form. [(more...)](../struts-taglib/tagreference.html.md#struts-bean.tld)
        1.  Create and maintain a properties file of the text elements to be displayed. [(more...)](../userGuide/preface.html.md#0_6_Properties_Files_and_ResourceBundles)

    3.  Use `property` attributes to link form fields to `ActionForm` instance variables.

2.  Implement one or more `ActionForm` descendents to buffer data between JSPs and Actions.
    1.  Create get/set pairs that correspond to the property names in your related JSP form. Example:

            .html.md:text property="city" />

        needs:

            getCity() and setCity(String c)

    2.  When needed, create a `reset` method that sets the fields of the `ActionForm` to their default values. Most ActionForms do not need to do this.

3.  Create an XML document that defines the validation rules for your application.
4.  Implement one or more `Action` descendents to respond to form submissions.
    1.  Descend from DispatchAction or LookupDispatchAction if you want one class to handle more than one kind of event (example: one Action to handle 'insert', 'update' and 'delete' events, using a different "surrogate" execute method for each). [(more...)](http://husted.com/struts/tips/002.html.md)
    2.  Use the `execute` method (or its surrogates) of your Action class to interface with objects in your application responsible for database interaction, such as EJBs, etc.
    3.  Use the return value of the `execute` method (or its surrogates) direct the user interface to the appropriate next page.

5.  Create `struts-config.xml` to associate forms with actions. The file minimally needs:
6.  Create or update `web.xml` to reference `ActionServlet` [(more...)](../userGuide/configuration.html.md#5_4_The_Web_Application_Deployment_Descriptor)
7.  Parallel Tasks
    1.  Building
        1.  Use Ant. It can compile, create WAR file, perform XSLT transformations, run unit tests, interact with version control systems, clean up, etc. [(more...)](http://ant.apache.org)
        2.  Create and use build script incrementally, as you create files that need to be copied, compiled, etc.

    2.  Unit Testing
        1.  Unit test normal JavaBeans with JUnit. [(more...)](http://www.junit.org)
        2.  Unit test JSP, taglibs, and conventional servlet components with Cactus. [(more...)](http://jakarta.apache.org/cactus)
        3.  Unit test Action servlets with StrutsTestCase. [(more...)](http://strutstestcase.sourceforge.net)
        4.  Add all unit tests to the build script as a separate target. This target should use the `junit` tag to launch each TestCase descendent. [(more...)](http://ant.apache.org/manual/OptionalTasks/junit.html.md)

    3.  Deployment
        1.  Build script should create a WAR file containing the files developed above, along with files that make up the framework.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


