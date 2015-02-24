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

<span id="a2._Building_Model_Components"></span>2. Building Model Components
----------------------------------------------------------------------------

> *"If I had a world of my own, everything would be nonsense. Nothing would be what it is, because everything would be what it isn't. And contrary wise, what is, it wouldn't be. And what it wouldn't be, it would. You see?"*

<span id="overview"></span>
### <span id="a2.1_Overview"></span>2.1 Overview

Many requirements documents used for building web applications focus on the *View.* However, you should ensure that the processing required for each submitted request is also clearly defined from the *Model's* perspective. In general, the developer of the *Model* components will be focusing on the creation of JavaBeans classes that support all of the functional requirements. The precise nature of the beans required by a particular application will vary widely depending on those requirements, but they can generally be classified into several categories discussed below. However, a brief review of the concept of "scope" as it relates to beans and JSP is useful first.

<span id="javabeans"></span>
### <span id="a2.2_JavaBeans_and_Scope"></span>2.2 JavaBeans and Scope

Within a web-based application, JavaBeans can be stored in (and accessed from) a number of different collections of "attributes". Each collection has different rules for the lifetime of that collection, and the visibility of the beans stored there. Together, the rules defining lifetime and visibility are called the *scope* of those beans. The JavaServer Pages (JSP) Specification defines scope choices using the following terms (with the equivalent servlet API concept defined in parentheses):

-   **page** - Beans that are visible within a single JSP page, for the lifetime of the current request. (Local variables of the `service` method)
-   **request** - Beans that are visible within a single JSP page, as well as to any page or servlet that is included in this page, or forwarded to by this page. (Request attributes)
-   **session** - Beans that are visible to all JSP pages and servlets that participate in a particular user session, across one or more requests. (Session attributes)
-   **application** - Beans that are visible to all JSP pages and servlets that are part of a web application. (Servlet context attributes)

It is important to remember that JSP pages and servlets in the same web application share the same sets of bean collections. For example, a bean stored as a request attribute in a servlet like this:

`MyCart mycart = new MyCart(...); request.setAttribute("cart", mycart);`

is immediately visible to a JSP page which this servlet forwards to, using a standard action tag like this:

`<jsp:useBean id="cart" scope="request" class="com.mycompany.MyApp.MyCart"/>`

<span id="actionform"></span>
### <span id="a2.3_ActionForm_Beans"></span>2.3 ActionForm Beans

**Note:** While ActionForm beans often have properties that correspond to properties in your Model beans, the form beans themselves should be considered a Controller component. As such, they are able to transfer data between the Model and View layers.

The Struts framework generally assumes that you have defined an `ActionForm` bean (that is, a Java class extending the `ActionForm` class) for the input forms in your application. `ActionForm` beans are sometimes just called "form beans". These may be finely-grained objects, so that there is one bean for each form, or coarsely-grained so that one bean serves several forms, or even an entire application.

If you declare such beans in your Struts configuration file [(see Writing Action Mappings),](building_controller.html.md#4_8_Writing_Action_Mappings) the Struts controller servlet will automatically perform the following services for you, before invoking the appropriate `Action` method:

-   Check for an instance of a bean of the appropriate class, under the appropriate key, in the appropriate scope (request or session).
-   If there is no such bean instance available, a new one is automatically created and added to the appropriate scope (request or session).
-   For every request parameter whose name corresponds to the name of a property in the bean, the corresponding setter method will be called. This operates in a manner similar to the standard JSP action `<jsp:setProperty>` when you use the asterisk wildcard to select all properties.
-   The updated `ActionForm` bean will be passed to the `execute` method of an `Action` class `[org.apache.struts.Action],` so that the values can be made available to your system state and business logic beans.

For more about coding `Actions` and `ActionForm` beans, see the [Building Controller Components](building_controller.html.md) section.

You should note that a "form" (in the sense discussed here) does not necessarily correspond to a single JSP page in the user interface. It is common in many applications to have a "form" (from the user's perspective) that extends over multiple pages. Think, for example, of the wizard style user interface that is commonly used when installing new applications. Struts encourages you to define a single `ActionForm` bean that contains properties for all of the fields, no matter which page the field is actually displayed on. Likewise, the various pages of the same form should all be submitted to the same Action Class. If you follow these suggestions, the page designers can rearrange the fields among the various pages, often without requiring changes to the processing logic.

Smaller applications may only need a single ActionForm to service all of its input forms. Others applications might use a single ActionForm for each major subsystem of the application. Some teams might prefer to have a separate ActionForm class for each distinct input form or workflow. How many or how few ActionForms to use is entirely up to you. The framework doesn't care.

<span id="system_state"></span>
### <span id="a2.4_System_State_Beans"></span>2.4 System State Beans

The actual state of a system is normally represented as a set of one or more JavaBeans classes, whose properties define the current state. A shopping cart system, for example, will include a bean that represents the cart being maintained for each individual shopper, and will (among other things) include the set of items that the shopper has currently selected for purchase. Separately, the system will also include different beans for the user's profile information (including their credit card and ship-to addresses), as well as the catalog of available items and their current inventory levels.

For small scale systems, or for state information that need not be kept for a long period of time, a set of system state beans may contain all the knowledge that the system ever has of these particular details. Or, as is often the case, the system state beans will represent information that is stored permanently in some external database (such as a `CustomerBean` object that corresponds to a particular row in the CUSTOMERS table), and are created or removed from the server's memory as needed. Entity Enterprise JavaBeans are also used for this purpose in large scale applications.

<span id="business_logic"></span>
### <span id="a2.5_Business_Logic_Beans"></span>2.5 Business Logic Beans

You should encapsulate the functional logic of your application as method calls on JavaBeans designed for this purpose. These methods may be part of the same classes used for the system state beans, or they may be in separate classes dedicated to performing the logic. In the latter case, you will usually need to pass the system state beans to be manipulated to these methods as arguments.

For maximum code re-use, business logic beans should be designed and implemented so that they do **not** know they are being executed in a web application environment. If you find yourself having to import a `javax.servlet.*` class in your bean, you are tying this business logic to the web application environment. Consider rearranging things so that your `Action` classes (part of the Controller role, as described below) translate all required information from the HTTP request being processed into property setter calls on your business logic beans, after which a call to an `execute` method can be made. Such a business logic class can be reused in environments other than the web application for which they were initially constructed.

Depending on the complexity and scope of your application, business logic beans might be ordinary JavaBeans that interact with system state beans passed as arguments, or ordinary JavaBeans that access a database using JDBC calls. For larger applications, these beans will often be stateful or stateless Enterprise JavaBeans (EJBs) instead.

For more about using a database with your application, see the [Accessing a Database HowTo.](../faqs/db-howto.html.md)

For more about business logic and data access frameworks, see the [key technologies primer](http://struts.apache.org/primer.html.md).

<span id="dynabeans"></span>
### <span id="a2.5.1_DynaBeans"></span>2.5.1 DynaBeans

DynaBeans combine the extensibility of JavaBeans with the flexibility of a Map. Defining even the simplest JavaBean requires defining a new class and coding a field and two methods for each property. The properties of a DynaBean can be configured via an XML descriptor. The virtual properties of a DynaBean can't be called by standard Java methods, but work well with components that rely on reflection and introspection.

In your application, you can use DynaBeans to describe your HTML forms. This strategy can avoid creating a formal JavaBean subclass to store a few simple properties.

For more about DynaBeans, see

-   The Commons BeanUtils [Package Description](http://commons.apache.org/beanutils/api/org/apache/commons/beanutils/package-summary.html.md#package_description) and [Javadocs.](http://commons.apache.org/beanutils/api/index.html)
-   [Struts FormDef](https://formdef.dev.java.net/)

<span id="chain"></span>
### <span id="a2.6_Commons_Chain"></span>2.6 Commons Chain

A popular technique for organizing the execution of complex processing flows is the "Chain of Responsibility" pattern, as described (among many other places) in the classic ["Gang of Four" design patterns book.](http://www.amazon.com/exec/obidos/tg/detail/-/0201633612/apachesoftwar-20/) The GoF summarizes the Chain of Responsibility pattern as "Avoid coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. Chain the receiving objects and pass the request along the chain until an object handles it."

The CoR pattern helps us keep software components loosely coupled. A component can call a Chain of Responsbility, without knowing what objects are on the chain or how they are implemented. Most importantly, we can adjust the Chain without changing how callers invoke the Chain. As of version 1.3, the default Request Processor, which acts as the framework's "kernel", is a Chain of Responsiblity.

To implement its Chain, the Request Processor uses the [Chain of Responsibility](http://commons.apache.org/chain/) component in the Apache Commons which provides a standard implementation of the CoR pattern, along with various implementations of the Context and Command objects used by the Chain to service a request.

For more about Chain of Responsiblity, see

-   [Commons Chain of Responsibility](http://commons.apache.org/chain/)
-   [A look at Commons Chain](http://www.onjava.com/lpt/a/5671)
-   [Better Code with Struts 1.3](http://www.infonoia.com/en/content.jsp?d=inf.05.06&pr=1)

As of Struts 1.3, Commons Chain is used to construct the default Request Processor for the framework.

Next: [Building View Components](building_view.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


