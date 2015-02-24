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

<span id="How_to_Access_a_Database"></span>How to Access a Database
-------------------------------------------------------------------

Most developers would consider accessing a database part of the "business end" of an application. Most often, we don't access a database for the sake of accessing a database. We use the database as part of a larger business transaction. So lets start with accessing business logic from the framework.

The best thing is to use the Action as a thin adaptor between the web/presentation-tier and your business classes (including those that access a database).

So you first design a business API that uses plain Java classes. The best thing is to use objects that take ordinary Java types and return a JavaBean or collection of JavaBeans. The Action then calls these objects and passes the result back to the web/presentation tier.

A common approach is to create an Action class for each of business transaction, or use case, in your application. A simple "CRUD" application might have a CreateAction, a RetrieveAction, an UpdateAction, and a DeleteAction. To complete each transaction, the Action can make whatever calls are needed to your business API classes.

Ideally, all the database access code should be encapsulated behind the business API classes, so the framework doesn't know what persistent layer you are using (or even if there is a persistence layer). It just passes a key or search String and gets back a bean or collection of beans. This lets you use the same business API classes in other environments, and also to run unit tests against your business API outside of a web environment.

The Struts MailReader shows how this is usually done. MailReader uses the DAO (Data Access Object) pattern to separate the persistence layer from the (Struts) control layer. MailReader defines a DAO interface that the Actions can call, it then defines a implementation that uses a database stored in main memory. Other implementations could be defined and used instead, without changing any of the Struts classes.

To get started, it's simplest to setup a 1:1 correspondence between the Actions and your application's use cases. Each use case may make one or more calls to your business API, but from the user's perspective, each use case is a single transaction.

As you gain experience, you will find ways to combine your Action classes, say by using the DispatchAction. It's even possible to use a single "framework" Action to call all of your business classes, as is done with Scaffold ProcessAction in the Sandbox subproject.

Using fewer Actions does require a deeper understanding of how Struts and MVC frameworks operate. Don't hesitate to err on the side of creating more Action classes at first. The configuration file makes it easy to refactor your Actions later, since you can change the Action type without changing anything else in the application.

<span id="Using_DataSources"></span>Using DataSources
-----------------------------------------------------

When you use the DAO approach, all of the database access details are hidden behind the business interface. The implementation of the business classes handle all the gritty details, like using a `DataSource` to pool connections to the database.

As a rule, you should always use a connection pool to access a database. The `DataSource` interface is the preferred way to implement a connection pool today. Many containers and database systems now bundle a DataSource implmentation that you can use. Most often, the DataSource is made available through JNDI. The JNDI approach makes it easy for your business classes to access the DataSource without worrying about who set it up.

<span id="Persistence_Franeworks"></span>Persistence Franeworks
---------------------------------------------------------------

There are many useful and mature persistence layer frameworks available. Before using raw JDBC or "rolling your own" solution, you should carefully review one or more of these packages. Here's a short list of packages most often mentioned on the Struts User list:

-   [Hibernate](http://www.hibernate.org/)
-   [iBATIS](http://sourceforge.net/projects/ibatisdb)
-   [Object Relational Bridge](http://db.apache.org/ojb/)
-   [Torque / Peers](http://db.apache.org/torque/index.html.md)

For more, see the [Struts Community Resources area](http://struts.sourceforge.net/community/models.html.md) on SourceForge.

<span id="See_Also"></span>See Also
-----------------------------------

<http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24621.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24709.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24626.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24331.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24102.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23501.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23455.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23375.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23321.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23098.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg22713.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg21974.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg21026.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg19338.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg18323.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg14975.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg14914.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg14435.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg01562.html.md>

Transformation/Data Transfer
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24480.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg23623.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg10195.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg10205.html.md>

<span id="Rendering_a_dynamic_result_set"></span>Rendering a dynamic result set
-------------------------------------------------------------------------------

The result of most queries will map to the ActionForms you are already using, and so you can render the ResultSet as a collection of ActionForms. But sometimes there are columns in a ResultSet that are not properties of an ActionForm, or even known in advance.

Happily, the Struts JSP tags don't care what type of bean you use with them. You could even output a ResultSet directly. But a ResultSet retains a connection to the database, and passing "all that" directly to a JSP gets messy. So what's a developer to do?

Since version 1.1, the simplest option is to use a [ResultSetDynaClass](http://commons.apache.org/beanutils/api/org/apache/commons/beanutils/ResultSetDynaClass.html.md) to transfer the ResultSet into an ArrayList of DynaBeans. The Struts custom tags can use DynaBean properties as easily as they use conventional JavaBean properties. (See [DynaActionForm classes](../userGuide/building_controller.html#dyna_action_form_classes) in the Struts User Guide for details.)

Since these classes are in the BeanUtils JAR, you already have it on board, and just need to implement the transfer routine (see the ResultSetDynaClass link).

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


