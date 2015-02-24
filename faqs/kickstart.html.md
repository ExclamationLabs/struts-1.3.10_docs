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

<span id="top"></span>Kickstart FAQ
-----------------------------------

1.  [Why do we need Struts?"](#why)
2.  [How does Struts work?](#how)
3.  [Is Struts compatible with other Java technologies?](#compat)
4.  [Who wrote Struts?](#who)
5.  [Was Struts the first web application framework for Java?](#first)
6.  [Is Struts the most popular web application framework for Java?](#popular)
7.  [Where can I get a copy of Struts Framework?](#where)
8.  [How do I install Struts?](#install)
9.  [When do I need the Struts JARs on my classpath?](#jar)
10. [Does Struts include its own unit tests?](#tests)

<span id="why"></span>Why do we need Struts?"  
Java technologies give developers a serious boost when creating and maintaining applications to meet the demands of today's public Web sites and enterprise intranets. Struts combines standard Java technologies into a unified framework.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="how"></span>How does Struts work?  
Java Servlets are designed to handle requests made by Web browsers. Server pages are designed to create dynamic web pages that can turn billboard sites into interactive applications. Struts uses a special Servlet as a switchboard to route requests from Web browsers to the appropriate server page. Along the way, a special Java class, called an Action, can interact with a data access framework or business logic classes. A layered architecture makes enterprise-grade web applications easier to create and maintain. (For more detail, see the longer version of ["How Does Struts Work?".](works.html.md))

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="compat"></span>Is Struts compatible with other Java technologies?  
Yes. The Apache Struts Project is committed to supporting industry standards. Struts acts as an integrator of Java technologies so that they can be used in the "real world".

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="who"></span>Who wrote Struts?  
There are several [active committers](http://struts.apache.org/volunteers.html.md) to the Apache Struts project, working cooperatively from around the globe. Dozens of individual developers and committers contributed to the Struts 1.x codebase. All interested developers and wordsmiths are invited to [contribute to the project](http://struts.apache.org/helping.html#contribute) .

The initial Struts codebase (Struts 0.5) was created by Craig R. McClanahan in May 2000 and donated to The Apache Software Foundation in May 2000. Craig was the primary developer of both Struts 1.x and [Tomcat 4](http://jakarta.apache.org/tomcat/index.html.md) . Tomcat 4 was the basis for the official reference implementation for a servlet 2.3 and JSP 1.2 container.

After serving as the co-lead of the JSR 127 specification (JavaServerFaces), Craig created another rendition of Struts based on JavaServer Faces, called Shale. The new framework began as an Apache Struts subproject, but later Shale graduated to a top-level Apache project in its own right. [Apache Shale](http://shale.apache.org/) is an excellent choice for teams creating complex applications that utilize JSF as a foundation technology.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="first"></span>Was Struts the first web application framework for Java?  
No, not by a long shot. When Struts 1.0 shipped in June 2001, there were already several other web application frameworks available, including Barracuda, Expresso, Maverick, Tapestry, and Turbine, to name a few. Struts did not enter a "greenfield". Back in the day, there were lively comparisons between the available frameworks, just as there are today.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="popular"></span>Is Struts the most popular web application framework for Java?  
Yes. By any objective measure, Struts continues to be the most popular web application framework for Java.

As of 2006, the vast majority of job offerings for Java developers cite Struts as prerequisite. According to OnJava magazine between their reader surveys for 2005 and 2004 the popularity of Struts remained steady. Likewise, the number of Struts articles published in all online journals also remained constant between 2004 and 2005. (For a complete list, see the [Struts Central website](http://www.StrutsCentral.net/).) New and updated books about Struts continue to be published regularly.

While some people characterize the space of Java web application framework as being "fragmented", the truth is that **more web developers use Struts than all other alternatives combined.** This observation is as true in 2006 as it was in 2005, as it was in 2004. It's probably been true since Struts released its 1.0 version in 2001.

Of course, some developers are finding that JavaServer Faces can be a faster way to write new applications, especially modest intranet applications. And that's great! More than anything else, every Struts committer wants every developer to get more out of every work day. (We're developers too!) As these new JSF applications grow in complexity, we're glad that [Apache Shale](http://shale.apache.org/) is ready to do for *JSF* developers what Struts has been doing for *JSP* developers, year after year after year.

Meanwhile, enterprise web developers who have standardized on Struts can be assured that new releases of Struts 1 will continue, even as we break new ground with Struts 2.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="where"></span>Where can I get a copy of Struts Framework?  
The best place to download Apache Struts products is at [struts.apache.org](http://struts.apache.org/)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="install"></span>How do I install Struts?  
To develop applications with Struts, you can usually just add the Struts JAR file to your Java development environment. You can then start using the Struts classes as part of your own application. A blank Struts application (in the `webapps` directory, open `struts-blank.war` ) is provided, which you can just copy to get a quick-start on your own brainchild.

Aside from the Struts jar, the blank application includes the other Struts Library JARs and dependencies. All dependencies are compatible with the Apache License.

Since the full source code for Struts is available, we also provide [instructions](http://struts.apache.org/downloads.html.md#Building) for compiling your own Struts JAR from scratch. (With Maven, building Struts is easy!)

Your Struts application can usually be deployed using a standard WAR file. In most cases, you simply deposit the WAR file on your application server, and it is installed automatically. If not, step-by-step installation instructions for [various servlet containers](../userGuide/installation.html.md#Containers) are available.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="jar"></span>When do I need the Struts JARs on my classpath?  
When you are compiling an application that uses the Struts classes, you must have the Struts JARs on the classpath your **compiler** sees -- it does not *have* to be on your CLASSPATH environment variable.

Why is that an important distinction? Because if you are using a servlet container on your development machine to test your application, the Struts JARs **must not** be on your CLASSPATH environment variable when running the container. (This is because each Web application must also have their own copy of the Struts classes, and the container will become confused if it is on the environment path as well.)

There are several general approaches to this issue:

-   **Use Ant or Maven** for building your projects -- it can easily assemble classpaths for the compiler.
-   **Use an IDE** where you can configure the "class path" used for compilation independent of the CLASSPATH environment variable.
-   **Use a shell script** that temporarily adds struts-action.jar to the classpath just for compilation, for example
     *javac -classpath /path/to/struts-action.jar:$CLASSPATH $@*

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="tests"></span>Does Struts include its own unit tests?  
Struts currently has two testing environments, to reflect the fact that some things can be tested statically, and some really need to be done in the environment of a running servlet container.

For static unit tests, we use the [JUnit framework](http://www.junit.org) . The sources for these tests are in the "src/test" hierarchy in the source repository, and are executed via the "test.junit" target in the top-level build.xml file. Such tests are focused on the low-level functionality of individual methods, are particularly suitable for the static methods in the org.apache.struts.util utility classes. In the test hierarchy, there are also some "mock object" classes (in the org.apache.struts.mock package) so that you can package up things that look like servlet API and Struts API objects to pass in as arguments to such tests.

Another valuable tool is [Struts TestCase](http://sourceforge.net/projects/strutstestcase/) which provides a useful harness for Action classes that can be used with JUnit or [Cactus](http://jakarta.apache.org/cactus).

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


