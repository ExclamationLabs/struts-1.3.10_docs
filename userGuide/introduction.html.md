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

<span id="a1._Introduction"></span>1. Introduction
--------------------------------------------------

> *"Read the directions and directly you will be directed in the right direction."*

The framework documentation is written for active web developers and assumes a working knowledge about how Java web applications are built. For more about the underlying nuts and bolts, see the [Key Technologies Primer.](http://struts.apache.org/primer.html.md)

<span id="history"></span>
### <span id="a1.1_Forward_into_the_Past_or_a_brief_history_of_Struts"></span>1.1 Forward into the Past! (or a brief history of Struts)

When Java servlets were first invented, many programmers quickly realized that they were a Good Thing. They were faster and more powerful that standard CGI, portable, and infinitely extensible.

But writing HTML to send to the browser in endless `println()` statements was tiresome and problematic. The answer to that was [JavaServer Pages,](http://java.sun.com/products/jsp/product.html.md) which turned [Servlet](http://www.novocode.com/doc/servlet-essentials/) writing inside-out. Now developers could easily mix HTML with Java code, and have all the advantages of servlets. The sky was the limit!

Java web applications quickly became "JSP-centric". This in-and-of itself was not a Bad Thing, but it did little to resolve flow control issues and other problems endemic to web applications.

Clearly, another paradigm was needed ...

Many clever developers realized that JavaServer Pages AND servlets could be used **together** to deploy web applications. The servlets could help with the control-flow, and the JSPs could focus on the nasty business of writing HTML. In due course, using JSPs and servlets together became known as [Model 2](http://www.javaworld.com/javaworld/jw-12-1999/jw-12-ssj-jspmvc.html.md) (meaning, presumably, that using JSPs alone was Model 1).

Of course, there is nothing new under the Sun ... and many have been quick to point out that JSP's Model 2 follows the classic [Model-View-Controller](http://java.sun.com/blueprints/patterns/j2ee_patterns/model_view_controller/) design pattern abstracted from the venerable [Smalltalk MVC framework.](http://st-www.cs.uiuc.edu/users/smarch/st-docs/mvc.html.md) Java Web developers now tend to use the terms Model 2 and MVC interchangeably. In this guide, we use the MVC paradigm to describe the framework architecture, which might be best termed a Model 2/MVC design.

The Apache Struts Project was launched in May 2000 by Craig R. McClanahan to provide a standard MVC framework to the Java community. In July 2001, version 1.0 was released, and IOHO, Java Model 2 development has never been quite the same.

<span id="mvc"></span>
### <span id="a1.2_The_Model-View-Controller_MVC_Design_Pattern"></span>1.2 The Model-View-Controller ('MVC') Design Pattern

The term "MVC" originated with the SmallTalk Model-View-Controller framework. Under MVC, an application is seen as having three distinct parts. The problem domain is represented by the Model. The output to the user is represented by the View. And, the input from the user is represented by Controller.

<span id="modelConcepts"></span>
### <span id="a1.2.1_The_Model:_System_State_and_Business_Logic_JavaBeans"></span>1.2.1 The Model: System State and Business Logic JavaBeans

The *Model* portion of an MVC-based system can be often be divided into two major subsystems -- the **internal state** of the system and the **actions** that can be taken to change that state.

In grammatical terms, we might think about state information as **nouns** (things) and actions as **verbs** (changes to the state of those things).

Many applications represent the internal state of the system as a set of one or more JavaBeans. The bean properties represent the details of the system' state. Depending on your application's complexity, these beans may be self contained (and know how to persist their own state), or they may be facades that know how to retrieve the system's state from another component. This component may be a database, a search engine, an Entity Enterprise JavaBean, a LDAP server, or something else entirely.

Large-scale applications will often represent the set of possible business operations as methods that can be called on the bean or beans maintaining the state information. For example, you might have a shopping cart bean, stored in session scope for each current user, with properties that represent the current set of items that the user has decided to purchase. This bean might also have a `checkOut()` method that authorizes the user's credit card and sends the order to the warehouse to be picked and shipped. Other systems will represent the available operations separately, perhaps as Session Enterprise JavaBeans (Session EJBs).

In a smaller scale application, on the other hand, the available operations might be embedded within the `Action` classes that are part of the framework control layer. This can be useful when the logic is very simple or where reuse of the business logic in other environments is not contemplated.

The framework architecture is flexible enough to support most any approach to accessing the Model, but we **strongly** recommend that you separate the business logic ("how it's done") from the role that `Action` classes play ("what to do"). 'nuff said.

For more about adapting your application's Model to the framework, see the [Building Model Components](building_model.html.md) chapter.

<span id="presentationConcepts"></span>
### <span id="a1.2.2_The_View:_JSP_Pages_and_Presentation_Components"></span>1.2.2 The View: JSP Pages and Presentation Components

The *View* portion of a Struts-based application is most often constructed using JavaServer Pages (JSP) technology. JSP pages can contain static HTML (or XML) text called "template text", plus the ability to insert dynamic content based on the interpretation (at page request time) of special action tags. The JSP environment includes a set of standard action tags, such as `<jsp:useBean>` whose purpose is described in the [JavaServer Pages Specification.](http://java.sun.com/products/jsp/download.html.md) In addition to the built-in actions, there is a standard facility to define your own tags, which are organized into "custom tag libraries."

The framework includes a set of custom tag libraries that facilitate creating user interfaces that are fully internationalized and interact gracefully with `ActionForm` beans. ActionForms capture and validate whatever input is required by the application.

For more about the Struts taglibs and using presentation pages with the framework, see the [Building View Components](building_view.html.md) section. Additional documentation regarding the taglibs is also available in the Taglibs subproject.

<span id="controllerConcepts"></span>
### <span id="a1.2.3_The_Controller:_ActionServlet_and_ActionMapping"></span>1.2.3 The Controller: ActionServlet and ActionMapping

Struts provides the *Controller* portion of the application. The Controller is focused on receiving requests from the client (typically a user running a web browser), deciding what business logic function is to be performed, and then delegating responsibility for producing the next phase of the user interface to an appropriate View component. The primary component of the Controller in the framework is a servlet of class `ActionServlet.` This servlet is configured by defining a set of `ActionMappings.` An ActionMapping defines a `path` that is matched against the request URI of the incoming request and usually specifies the fully qualified class name of an Action class. All Actions are subclassed from `[org.apache.struts.action.Action].` Actions encapsulate calls to business logic classes, interpret the outcome, and ultimately dispatch control to the appropriate View component to create the response. While the framework dispatches to a View, actually rendering the View is outside its scope.

The framework also supports the ability to use `ActionMapping` classes that have additional properties beyond the standard ones required to operate the controller. This allows you to store additional information specific to your application and still utilize the remaining features of the framework. In addition, the framework lets you define logical "names" to which control should be forwarded so that an action method can ask for the "Main Menu" page (for example), without knowing the location of the corresponding JSP page. These features greatly assist you in separating the control logic (what to do) with the view logic (how it's rendered).

For more about the control layer, see the [Building Controller Components](building_controller.html.md) chapter.

<span id="flow"></span>
### <span id="a1.3_Framework_Control_Flow"></span>1.3 Framework Control Flow

The framework provides several components that make up the **Control** layer of a MVC-style application. These include a controller component (servlet), developer-defined request handlers, and several supporting objects.

The Struts Taglib component provides direct support for the **View** layer of a MVC application. Some of these tags access the control-layer objects. Others are generic tags found convenient when writing applications. Other taglibs, including [JSTL,](http://java.sun.com/products/jsp/jstl/index.html.md) can also be used with the framework. Other presentation technologies, like [Velocity Templates](http://jakarta.apache.org/velocity/index.html) and [XSLT](http://www.w3.org/TR/xslt) can also be used with the framework.

The **Model** layer in a MVC application is often project-specific. The framework is designed to make it easy to access the business-end of your application, but leaves that part of the programming to other products, like [JDBC,](http://java.sun.com/products/jdbc/index.html.md) [Enterprise Java Beans,](http://java.sun.com/products/ejb/index.html)[Object Relational Bridge,](http://db.apache.org/ojb/) or [iBATIS,](http://ibatis.apache.org/) to name a few.

Let's step through how this all fits together.

When initialized, the controller parses a configuration file `(struts-config.xml)` and uses it to deploy other control layer objects. Together, these objects form the **Struts Configuration.** The Configuration defines (among other things) the collection of [ActionMappings](../apidocs/org/apache/struts/action/ActionMapping.html.md)`[org.apache.struts.action.ActionMappings]` for an application.

The controller component consults the ActionMappings as it routes HTTP requests to other components in the framework. Requests may be forwarded to JavaServer Pages or [Action](../apidocs/org/apache/struts/action/Action.html.md)`[org.apache.struts.action.Action]` subclasses provided by the application developer. Often, a request is first forwarded to an Action and then to a JSP (or other presentation page). The mappings help the controller turn HTTP requests into application actions.

An individual [ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html.md)`[org.apache.struts.action.ActionMapping]` will usually contain a number of properties including:

-   a **request path** (or "URI"),
-   the **object type** (Action subclass) to act upon the request, and
-   other properties as needed.

The Action object can handle the request and respond to the client (usually a Web browser) or indicate that control should be forwarded elsewhere. For example, if a login succeeds, a login action may wish to forward the request onto the mainMenu page.

Action objects have access to the application's controller component, and so have access to that members's methods. When forwarding control, an Action object can indirectly forward one or more shared objects, including [JavaBeans,](http://java.sun.com/products/javabeans/) by placing them in one of the standard contexts shared by Java Servlets.

For example, an Action object can create a shopping cart bean, add an item to the cart, place the bean in the session context, and then forward control to another mapping. That mapping may use a JavaServer Page to display the contents of the user's cart. Since each client has their own session, they will each also have their own shopping cart.

Most of the business logic in an application can be represented using JavaBeans. An Action can call the properties of a JavaBean without knowing how it actually works. This encapsulates the business logic, so that the Action can focus on error handling and where to forward control.

JavaBeans can also be used to manage input forms. A key problem in designing Web applications is retaining and validating what a user has entered between requests. You can define your own set of input bean classes, by subclassing [ActionForm](../apidocs/org/apache/struts/action/ActionForm.html.md)`[org.apache.struts.action.ActionForm].` The ActionForm class makes it easy to store **and validate** the data for your application's input forms. The ActionForm bean is automatically saved in one of the standard, shared context collections, so that it can be used by other objects, like an Action object or another JSP.

The form bean can be used by a JSP to collect data from the user ... by an Action object to validate the user-entered data ... and then by the JSP again to re-populate the form fields. In the case of validation errors, the framework has a shared mechanism for raising and displaying error messages.

Another element of the Configuration are the [ActionFormBeans](../apidocs/org/apache/struts/action/ActionFormBeans.html.md)`[org.apache.struts.action.ActionFormBeans].` This is a collection of [descriptor objects](../apidocs/org/apache/struts/action/ActionFormBean.html) that are used to create instances of the ActionForm objects at runtime. When a mapping needs an ActionForm, the servlet looks up the form-bean descriptor by name and uses it to create an ActionForm instance of the specified type.

Here is the sequence of events that occur when a request calls for an mapping that uses an ActionForm:

-   The controller servlet either retrieves or creates the ActionForm bean instance.
-   The controller servlet passes the bean to the Action object.
-   If the request is being used to submit an input page, the Action object can examine the data. If necessary, the data can be sent back to the input form along with a list of messages to display on the page. Otherwise the data can be passed along to the business tier.
-   If the request is being used to create an input page, the Action object can populate the bean with any data that the input page might need.

The Struts Taglib component provides custom tags that can automatically populate fields from a JavaBean. All most JavaServer Pages really need to know is the field names to use and where to submit the form.

Other tags can automatically output messages queued by an Action or ActionForm and simply need to be integrated into the page's markup. The messages are designed for [localization](http://developer.java.sun.com/developer/technicalArticles/Intl/IntlIntro/) and will render the best available message for a user's locale.

The framework and Struts Taglib were designed from the ground-up to support the internationalization features built into the Java platform. All the field labels and messages can be retrieved from a [message resource.](../apidocs/org/apache/struts/util/MessageResources.html.md) To provide messages for another language, simply add another file to the resource bundle.

Internationalism aside, other benefits to the message resources approach are consistent labeling between forms, and the ability to review all labels and messages from a central location.

For the simplest applications, an Action object may sometimes handle the business logic associated with a request. **However, in most cases, an Action object should invoke another object, usually a JavaBean, to perform the actual business logic.** This lets the Action focus on error handling and control flow, rather than business logic. To allow reuse on other platforms, business-logic JavaBeans should not refer to any Web application objects. The Action object should translate needed details from the HTTP request and pass those along to the business-logic beans as regular Java variables.

In a database application, for example:

-   A business-logic bean will connect to and query the database,
-   The business-logic bean returns the result to the Action,
-   The Action stores the result in a form bean in the request,
-   The JavaServer Page displays the result in a HTML form.

Neither the Action nor the JSP need to know (or care) from where the result comes. They just need to know how to package and display it.

[Other sections](index.html.md) in this document cover the various framework components in greater detail. The Struts Taglib component includes several Developer Guides covering various aspects of the custom tags. A number of sample applications are bundled with the distribution that show how it all comes together.

The framework is distributed under the [Apache Software Foundation license.](http://www.apache.org/licenses/) The code is copyrighted, but is free to use in any application.

Next: [Building Model Components](building_model.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


