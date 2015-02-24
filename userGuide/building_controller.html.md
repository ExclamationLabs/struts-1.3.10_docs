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

<span id="a4._Building_Controller_Components"></span>4. Building Controller Components
--------------------------------------------------------------------------------------

> *"It would be so nice if something made sense for a change."*

<span id="overview"></span>
### <span id="a4.1_Overview"></span>4.1 Overview

Now that we understand how to construct the [Model](building_model.html.md) and [View](building_view.html) components of your application, it is time to focus on the Controller components. The framework includes a servlet that implements the primary function of mapping a request URI to an Action class. Therefore, your primary responsibilities related to the Controller are:

-   Write an ActionForm class to mediate between the Model and the View. [(See also Building an ActionForm.)](../faqs/actionForm.html.md)
-   Write an Action class for each logical request that may be received (extend the `[org.apache.struts.action.Action]` class).
-   Configure a ActionMapping (in XML) for each logical request that may be submitted. The XML configuration file is usually named struts-config.xml.

To deploy your application, you will also need to:

-   Update the web application deployment descriptor file (in XML) for your application to reference the additional components.
-   Include the additional components with your application.

The latter two items are covered in the ["Configuring Applications"](configuration.html.md) chapter.

<span id="action_servlet"></span>
### <span id="a4.2_The_ActionServlet"></span>4.2 The ActionServlet

For those of you familiar with MVC architecture, the ActionServlet represents the C - the controller. The job of the controller is to:

-   process user requests,
-   determine what the user is trying to achieve according to the request,
-   pull data from the model (if necessary) to be given to the appropriate view, and
-   select the proper view to respond to the user.

Our controller delegates most of this grunt work to the [Request Processor](#request_processor) and Action classes.

In addition to being the front controller for your application, the ActionServlet instance also is responsible for initialization and clean-up of resources. When the controller initializes, it first loads the application config corresponding to the "config" init-param. It then goes through an enumeration of all init-param elements, looking for those elements who's name starts with config/. For each of these elements, the framework loads the configuration file specified by the value of that init-param, and assigns a "prefix" value to that module's ModuleConfig instance consisting of the piece of the init-param name following "config/". For example, the module prefix specified by the init-param config/foo would be "foo". This is important to know, since this is how the controller determines which module will be given control of processing the request. To access the module foo, you would use a URL like:

    http://localhost:8080/myApp/foo/someAction.do

For each request made of the controller, the method process(HttpServletRequest, HttpServletResponse) will be called. This method simply determines which module should service the request and then invokes that module's RequestProcessor's process method, passing the same request and response.

<span id="request_processor"></span>
### <span id="a4.2.1_Request_Processor"></span>4.2.1 Request Processor

The RequestProcessor is where the majority of the core processing occurs for each request. Since version 1.3, the default Request Processor `(ComposableRequestProcessor)` is composed using [Commons Chain,](http://commons.apache.org/chain/) which is an implementation of the *Chain of Responsibility* pattern (CoR). It is designed as a drop-in replacement of the Struts 1.2.x behaviour and brings greater flexibility and easier customization to the request processing process. Each step of the processing is represented as a separate Command in the Chain. By inserting, substituting, or removing Commands, you can customize the framework to work *your* way. Let's take a look at the *default* commands for the ComposableRequestProcessor Chain in turn. These Command classes are in either the `org.apache.struts.chain.commands` or `org.apache.struts.chain.commands.servlet` packages.

|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SelectLocale          | Select a locale for this request, if one hasn't already been selected, and place it in the request.                                                                                                                                                     |
| SetOriginalURI        | Store the URI of the original request in the request.                                                                                                                                                                                                   |
| RequestNoCache        | If appropriate, set the following response headers: "Pragma", "Cache-Control", and "Expires".                                                                                                                                                           |
| RemoveCachedMessages  | Removes any `ActionMessages` object stored in the session under `Globals.MESSAGE_KEY` and `Globals.ERROR_KEY` if the messages' `isAccessed` method returns true. This allows messages to be stored in the session, displayed one time, and be released. |
| SetContentType        | Set the default content type (with optional character encoding) for all responses if requested.                                                                                                                                                         |
| SelectAction          | Determine the ActionMapping associated with this path.                                                                                                                                                                                                  |
| AuthorizeAction       | If the mapping has a role associated with it, ensure the requesting client has the specified role. If the client does not, raise an error and stop processing of the request.                                                                           |
| CreateActionForm      | Instantiate (if necessary) the ActionForm associated with this mapping (if any) and place it into the appropriate scope.                                                                                                                                |
| PopulateActionForm    | Populate the ActionForm associated with this request, if any.                                                                                                                                                                                           |
| ValidateActionForm    | Perform validation (if requested) on the ActionForm associated with this request (if any).                                                                                                                                                              |
| SelectInput           | If validation failed, select the appropriate ForwardConfig for return to the input page.                                                                                                                                                                |
| ExecuteCommand        | Lookup and execute a chain command if the current ActionConfig is so-configured.                                                                                                                                                                        |
| SelectForward         | If this mapping represents a forward, forward to the path specified by the mapping.                                                                                                                                                                     |
| SelectInclude         | Select the include uri (if any) for the current action mapping.                                                                                                                                                                                         |
| PerformInclude        | If selected, include the result of invoking the path in this request.                                                                                                                                                                                   |
| CreateAction          | Instantiate an instance of the class specified by the current ActionMapping (if necessary).                                                                                                                                                             |
| ExecuteAction         | This is the point at which your Action's execute method will be called.                                                                                                                                                                                 |
| ExecuteForwardCommand | Lookup and execute a chain command if the current ForwardConfig is so-configured.                                                                                                                                                                       |
| PerformForward        | Finally, the process method of the RequestProcessor takes the ActionForward returned by your Action class, and uses it to select the next resource (if any). Most often the ActionForward leads to the presentation page that renders the response.     |

In Struts 1.2.x, Tiles processing required configuring the framework to use the `TilesRequestProcessor` implementation. In the Struts 1.3 *Chain* based request processor using Tiles simply involves configuring it to use an additional Tiles Command, and deploying the tiles sub-project jar. The following Command is in the `org.apache.struts.tiles.commands` package.

|-------------------|-------------------------------------------------------------------------------------------------|
| TilesPreProcessor | Command class intended to perform responsibilities of the TilesRequestProcessor in Struts 1.2.x |

<span id="process"></span>
### <span id="a4.2.2_Where_did_they_go"></span>4.2.2 Where did they go?

The Struts 1.2.x RequestProcessor utilized a similar but different set of messages. Here we provide a table summarizing the changes.

This chain attempts to emulate (most of) the standard request processing in the standard org.apache.struts.action.RequestProcessor class, by performing the corresponding tasks in individual Commands that are composable. The following list defines a cross reference between the processXxx methods and the Commands that perform the corresponding functionality:
processMultipart
Integrated into servlet and legacy classes
processPath
SelectAction (which also does processMapping)
processException
ExceptionCatcher / ExceptionHandler
processLocale
SelectLocale
processContent
SetContentType
processNoCache
RequestNoCache
processPreprocess
LookupCommand with optional="true". Multiple occurrences of this can easily be added, to support additional processing hooks at any point in the chain without modifying the standard definition.
processCachedMessages
RemoveCachedMessages
processMapping
SelectAction (which also does processPath)
processRoles
AuthorizeAction
processActionForm
CreateActionForm
processPopulate
PopulateActionForm
processValidate
ValidateActionForm / SelectInput
processForward
SelectForward
processInclude
SelectInclude / PerformInclude
processActionCreate
CreateAction
processActionPerform
ExecuteAction

<span id="action_form_classes"></span>
### <span id="a4.3_ActionForm_Classes"></span>4.3 ActionForm Classes

An ActionForm represents an HTML form that the user interacts with over one or more pages. You will provide properties to hold the state of the form with getters and setters to access them. ActionForms can be stored in either the session (default) or request scope. If they're in the session it's important to implement the form's reset method to initialize the form before each use. The framework sets the ActionForm's properties from the request parameters and sends the validated form to the appropriate Action's execute method.

When you code your ActionForm beans, keep the following principles in mind:

-   The ActionForm class itself requires no specific methods to be implemented. It is used to identify the role these particular beans play in the overall architecture. Typically, an ActionForm bean will have only property getter and property setter methods, with no business logic.
-   The ActionForm object also offers a standard validation mechanism. If you override a "stub" method, and provide error messages in the standard application resource, The framework will automatically validate the input from the form (using your method). See [Automatic Form Validation](building_view.html.md#3_3_4_Automatic_Form_Validation) for details. Of course, you can also ignore the ActionForm validation and provide your own in the Action object.
-   Define a property (with associated getXxx and setXxx methods) for each field that is present in the form. The field name and property name must match according to the usual JavaBeans conventions (see the Javadoc for the java.beans.Introspector class for a start on information about this). For example, an input field named username will cause the setUsername method to be called.
-   Buttons and other controls on your form can also be defined as properties. This can help determine which button or control was selected when the form was submitted. Remember, the ActionForm is meant to represent your data-entry form, not just the data beans.
-   Think of your ActionForm beans as a firewall between HTTP and the Action. Use the validate method to ensure all required properties are present, and that they contain reasonable values. An ActionForm that fails validation will not even be presented to the Action for handling.
-   You may also place a bean instance on your form, and use nested property references. For example, you might have a "customer" bean on your ActionForm, and then refer to the property "customer.name" in your presentation page. This would correspond to the methods customer.getName() and customer.setName(String Name) on your customer bean. See the Apache Struts Taglib Developer Guides for more about using the nested syntax.
-   *Caution:* If you nest an existing bean instance on your form, think about the properties it exposes. Any public property on an ActionForm that accepts a single String value can be set with a query string. It may be useful to place beans that can affect the business state inside a thin "wrapper" that exposes only the properties required. This wrapper can also provide a filter to be sure runtime properties are not set to inappropriate values.

<span id="dyna_action_form_classes"></span>
### <span id="a4.3.1_DynaActionForm_Classes"></span>4.3.1 DynaActionForm Classes

Maintaining a separate concrete ActionForm class for each form in your application is time-consuming. It is particularly frustrating when all the ActionForm does is gather and validate simple properties that are passed along to a business JavaBean.

This bottleneck can be alleviated through the use of DynaActionForm classes. Instead of creating a new ActionForm subclass and new get/set methods for each of your bean's properties, you can list its properties, type, and defaults in the framework's configuration file.

For example, add the following to struts-config.xml for a UserForm bean that stores a user's given and family names:

    <form-bean
        name="UserForm"
        type="org.apache.struts.action.DynaActionForm">
        <form-property
            name="givenName"
            type="java.lang.String"
            initial="John"/>
        <form-property
            name="familyName"
            type="java.lang.String"
            initial="Smith"/>
    </form-bean>

The types supported by DynaActionForm include:

-   java.math.BigDecimal
-   java.math.BigInteger
-   boolean and java.lang.Boolean
-   byte and java.lang.Byte
-   char and java.lang.Character
-   java.lang.Class
-   double and java.lang.Double
-   float and java.lang.Float
-   int and java.lang.Integer
-   long and java.lang.Long
-   short and java.lang.Short
-   java.lang.String
-   java.sql.Date
-   java.sql.Time
-   java.sql.Timestamp

You may also specify Arrays of these types (e.g. String[]). You may also specify a concrete implementation of the Map Interface, such as java.util.HashMap, or a List implementation, such as java.util.ArrayList.

If you do not supply an initial attribute, numbers will be initialized to 0 and objects to null.

In JSP pages using the Struts Taglib, attributes of DynaActionForm objects can be referenced just like ordinary ActionForm objects. Wherever a Struts tag refers to a "property", the tags will automatically use the DynaActionForm properties just like those of a conventional JavaBean. You can even expose DynaActionForm properties using bean:define. (Although, you can't use bean:define to **instantiate** a DynaActionForm, since it needs to be setup with the appropriate dyna-properties).

If you are using the Struts JSTL EL taglib, the references are, by default, different. Only properties of ordinary ActionForm objects can be directly accessed through the JSTL expression language syntax. The DynaActionForm properties must be accessed through a slightly different syntax. The JSTL EL syntax for referencing a property of an ActionForm goes like this:

    ${formbean.prop}

The syntax for referencing a property of a DynaActionForm would be:

    ${dynabean.map.prop}

The map property is a property of DynaActionForm which represents the HashMap containing the DynaActionForm properties.

DynaActionForms are meant as an easy solution to a common problem: *Your ActionForms use simple properties and standard validations, and you just pass these properties over to another JavaBean* (say using BeanUtils.copyProperties(myBusinessBean,form)).

DynaActionForms are **not** a drop-in replacement for ActionForms. If you need to access DynaActionForm properties in your Action, you will need to use the map-style accessor, like myForm.get("name"). If you actively use the ActionForm object in your Action, then you may want to use conventional ActionForms instead.

DynaActionForms cannot be instantiated using a no-argument constructor. In order to simulate the extra properties, there is a lot of machinery involved in their construction. You must rely on the framework to instantiate a DynaActionForm for you, via the ActionMapping.

If need be, you can extend the DynaActionForm to add custom validate and reset methods you might need. Simply specify your subclass in the struts-config instead. However, you cannot mix conventional properties and DynaProperties. A conventional getter or setter on a DynaActionForm won't be found by the reflection utilities.

To use DynaActionForms with the Struts Validator, specify org.apache.struts.validator.ValidatorActionForm (or your subclass) as the form-bean class.

And, of course, while the DynaActionForm may support various binary types, properties used with the.html.md:text tag should still be String properties.

DynaActionForms relieve developers of maintaining simple ActionForms. For even less maintenance, try the [LazyActionForm](#lazy_action_form_classes) described in the following section.

<span id="lazy_action_form_classes"></span>
### <span id="a4.3.2_LazyActionForm_Classes"></span>4.3.2 LazyActionForm Classes

Struts *Lazy* ActionForm which *wraps* a LazyDynaBean [(see Commons BeanUtils JavaDoc).](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/package-summary.html.md#dynamic.lazy)

There isn't really that much to this implementation as most of the *lazy* behaviour is in LazyDynaBean and *wrapping* the LazyDynaBean is handled in the parent BeanValidatorForm. The only thing it really does is populate *indexed* properties which are a List type with a LazyDynaBean in the get(name, index) method.

*Lazy* DynaBeans provide several types of *lazy* behaviour:

-   ***lazy* property addition** - properties which do not exist are automatically added.
-   ***lazy* List facilities** - automatically *grows* a List or Array to accomodate the index value being set.
-   ***lazy* List creation** - automatic creation of a List or Array for *indexed* properties, if it doesn't exist.
-   ***lazy* Map creation** - automatic creation of a Map for *mapped* properties, if it doesn't exist.

Using this *lazy* ActionForm means that you don't have to define the ActionForm's properties in the struts-config.xml. However, a word of warning, everything in the Request gets populated into this ActionForm circumventing the normal *firewall* function of Struts forms. Therefore you should only *take out* of this form properties you expect to be there rather than blindly populating all the properties into the business tier.

Having said that it is not necessary to pre-define properties in the struts-config.xml, it is useful to sometimes do so for *mapped* or *indexed* properties. For example, if you want to use a different Map implementation from the default HashMap or an array for indexed properties, rather than the default List type:

                        <form-bean name="myForm" type="org.apache.struts.validator.LazyValidatorForm">
                            <form-property name="myMap" type="java.util.TreeMap" />
                            <form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]" />
                        </form-bean>
                    

Another reason for defining *indexed* properties in the struts-config.xml is that if you are validating indexed properties using the Validator and none are submitted then the indexed property will be null which causes validator to fail. Pre-defining them in the struts-config.xml will result in a zero-length indexed property (array or List) being instantiated, avoiding an issue with validator in that circumstance.

This implementation validates using the ActionForm *name* . If you require a version that validates according to the *path* then it can be easily created in the following manner:

                        public class MyLazyForm extends LazyValidatorForm {

                            public MyLazyForm () {
                                super();
                                setPathValidation(true);
                            }

                        }
                    

Rather than using this class, another alternative is to either use a LazyDynaBean or custom version of LazyDynaBean directly, the framework now automatically *wraps* objects which are not ActionForms in a BeanValidatorForm. For example:

                        <form-bean name="myForm" type="org.apache.commons.beanutils.LazyDynaBean">
                            <form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]" />
                        </form-bean>
                    

For more coding examples, see the [LazyValidatorForm How-To.](http://www.niallp.pwp.blueyonder.co.uk/lazyactionform.html.md)

<span id="map_action_form_classes"></span>
### <span id="a4.3.3_Map-backed_ActionForms"></span>4.3.3 Map-backed ActionForms

The DynaActionForm classes offer the ability to create ActionForm beans at initialization time, based on a list of properties enumerated in the the framework's configuration file. However, many HTML forms are generated dynamically at request time. Since the properties of these forms' ActionForm beans are not all known ahead of time, we need a new approach.

The framework allows you to make one or more of your ActionForm's properties' values a Map instead of a traditional atomic object. You can then store the data from your form's dynamic fields in that Map. Here is an example of a map-backed ActionForm class:

    public FooForm extends ActionForm {

        private final Map values = new HashMap();

        public void setValue(String key, Object value) {
            values.put(key, value);
        }

        public Object getValue(String key) {
            return values.get(key);
        }

    }

In its corresponding JSP page, you can access objects stored in the values map using a special notation: mapname(keyname). The parentheses in the bean property name indicate that:

-   The bean property named mapname is indexed using Strings (probably backed by a Map), and that
-   The framework should look for get/set methods that take a String key parameter to find the correct sub-property value. The framework will, of course, use the keyname value from the parentheses when it calls the get/set methods.

Here is a simple example:

                        .html.md:text property="value(foo)"/>

This will call the getValue method on FooForm with a key value of "foo" to find the property value. To create a form with dynamic field names, you could do the following:

    <%
        for (int i = 0; i < 10; i++) {
            String name = "value(foo-" + i + ")";
    %>
            .html.md:text property="<%= name %>"/>
            <br/>
    <%
        }
    %>

Note that there is nothing special about the name "value". Your map-backed property could instead be named "property", "thingy", or any other bean property name you prefer. You can even have multiple map-backed properties on the same bean.

In addition to map-backed properties, you can also create list-backed properties. You do so by creating indexed get/set methods on your bean:

    public FooForm extends ActionForm {

        private final List values = new ArrayList();

        public void setValue(int key, Object value) {
            values.set(key, value);
        }

        public Object getValue(int key) {
            return values.get(key);
        }
    }

In your presentation pages, you access individual entries in a list-backed property by using a different special notation: listname[index]. The braces in the bean property name indicate that the bean property named listname is indexed (probably backed by a List), and that the framework should look for get/set methods that take an index parameter in order to find the correct sub-property value.

While map-backed ActionForms provide you with more flexibility, they do not support the same range of syntax available to conventional or DynaActionForms. You might have difficulty referencing [indexed or mapped properties](../struts-taglib/indexedprops.html.md) using a map-backed ActionForm. The validwhen validator (since Apache Struts 1.2.1) also does not support map-backed ActionForms.

<span id="action_classes"></span>
### <span id="a4.4_Action_Classes"></span>4.4 Action Classes

The Action class defines two methods that could be executed depending on your servlet environment:

    public ActionForward execute(ActionMapping mapping,
                        ActionForm form,
                        ServletRequest request,
                        ServletResponse response)
                        throws Exception;

    public ActionForward execute(ActionMapping mapping,
                        ActionForm form,
                        HttpServletRequest request,
                        HttpServletResponse response)
                        throws Exception;
                    

Since the majority of teams using the framework are focused on building web applications, most projects will only use the "HttpServletRequest" version. A non-HTTP execute() method has been provided for applications that are not specifically geared towards the HTTP protocol.

The goal of an Action class is to process a request, via its execute method, and return an ActionForward object that identifies where control should be forwarded (e.g. a JSP, Tile definition, Velocity template, or another Action) to provide the appropriate response. In the *MVC/Model 2* design pattern, a typical Action class will often implement logic like the following in its execute method:

-   Validate the current state of the user's session (for example, checking that the user has successfully logged on). If the Action class finds that no logon exists, the request can be forwarded to the presentation page that displays the username and password prompts for logging on. This could occur because a user tried to enter an application "in the middle" (say, from a bookmark), or because the session has timed out, and the servlet container created a new one.
-   If validation is not complete, validate the form bean properties as needed. If a problem is found, store the appropriate error message keys as a request attribute, and forward control back to the input form so that the errors can be corrected.
-   Perform the processing required to deal with this request (such as saving a row into a database). This *can* be done by logic code embedded within the Action class itself, **but** should generally be performed by calling an appropriate method of a business logic bean.
-   Update the server-side objects that will be used to create the next page of the user interface (typically request scope or session scope beans, depending on how long you need to keep these items available).
-   Return an appropriate ActionForward object that identifies the presentation page to be used to generate this response, based on the newly updated beans. Typically, you will acquire a reference to such an object by calling findForward on either the ActionMapping object you received (if you are using a logical name local to this mapping), or on the controller servlet itself (if you are using a logical name global to the application).

In Apache Struts 1.0, Actions called a perform method instead of the now-preferred execute method. These methods use the same parameters and differ only in which exceptions they throw. The elder perform method throws SerlvetException and IOException. The new execute method simply throws Exception. The change was to facilitate the Declarative Exception handling feature introduced in Apache Struts 1.1.

The perform method may still be used in Apache Struts 1.1 but is deprecated. The Apache Struts 1.1 method simply calls the new execute method and wraps any Exception thrown as a ServletException. The deprecated perform method was removed in Apache Struts 1.2.

<span id="action_design_guide"></span>
### <span id="a4.4.1_Action_Class_Design_Guidelines"></span>4.4.1 Action Class Design Guidelines

Remember the following design guidelines when coding Action classes:

-   **Write code for a multi-threaded environment** - Our controller servlet creates **only one instance of your Action class,** and uses this one instance to service all requests. Thus, you need to write thread-safe Action classes. Follow the same guidelines you would use to write thread-safe Servlets. Here are two general guidelines that will help you write scalable, thread-safe Action classes:
    -   **Only Use Local Variables** - The most important principle that aids in thread-safe coding is to use only local variables, **not instance variables** , in your Action class. Local variables are created on a stack that is assigned (by your JVM) to each request thread, so there is no need to worry about sharing them. An Action can be factored into several local methods, so long as all variables needed are passed as method parameters. This assures thread safety, as the JVM handles such variables internally using the call stack which is associated with a single Thread.
    -   **Conserve Resources** - As a general rule, allocating scarce resources and keeping them across requests from the same user (in the user's session) can cause scalability problems. For example, if your application uses JDBC and you allocate a separate JDBC connection for every user, you are probably going to run in some scalability issues when your site suddenly shows up on Slashdot. You should strive to use pools and release resources (such as database connections) prior to forwarding control to the appropriate View component -- even if a bean method you have called throws an exception.
-   **Don't throw it, catch it!** - Ever used a commercial website only to have a stack trace or exception thrown in your face after you've already typed in your credit card number and clicked the purchase button? Let's just say it doesn't inspire confidence. Now is your chance to deal with these application errors - in the Action class. If your application specific code throws expections you should catch these exceptions in your Action class, log them in your application's log (servlet.log("Error message", exception)) and return the appropriate ActionForward.

It is wise to avoid creating lengthy and complex Action classes. If you start to embed too much logic in the Action class itself, you will begin to find the Action class hard to understand, maintain, and impossible to reuse. Rather than creating overly complex Action classes, it is generally a good practice to move most of the persistence, and "business logic" to a separate application layer. When an Action class becomes lengthy and procedural, it may be a good time to refactor your application architecture and move some of this logic to another conceptual layer; otherwise, you may be left with an inflexible application which can only be accessed in a web-application environment. The framework should be viewed as simply the **foundation** for implementing MVC in your applications. Struts provides a useful control layer, but it is not a fully featured platform for building MVC applications, soup to nuts.

<span id="exception_handler"></span>
### <span id="a4.5_Exception_Handler"></span>4.5 Exception Handler

You can define an ExceptionHandler to execute when an Action's execute method throws an Exception. First, you need to subclass org.apache.struts.action.ExceptionHandler and override the execute method. Your execute method should process the Exception and return an ActionForward object to tell the framework where to forward to next. Then you configure your handler in struts-config.xml like this:

    <global-exceptions>
        <exception
          key="some.key"
          type="java.io.IOException"
          handler="com.yourcorp.ExceptionHandler"/>
    </global-exceptions>

This configuration element says that com.yourcorp.ExceptionHandler.execute will be called when any IOException is thrown by an Action. The key is a key into your message resources properties file that can be used to retrieve an error message.

If the handler attribute is not specified, the default handler stores the exception in the request attribute under the value of the Globals.EXCEPTION\_KEY global key.

The possible attributes for the "exception" element are as follows:

| Attribute | Description                                                                                                                                                                                     | Default                                     |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| bundle    | Servlet context attribute for the message resources bundle associated with this handler. The default attribute is the value specified by the string constant declared at Globals.MESSAGES\_KEY. | org.apache.struts.Globals.MESSAGES\_KEY     |
| className | The configuration bean for this ExceptionHandler object. If specified, className must be a subclass of the default configuration bean                                                           | "org.apache.struts.config.ExceptionConfig"  |
| extends   | The name of the exception handler that this will inherit configuration information from.                                                                                                        | None                                        |
| handler   | Fully qualified Java class name for this exception handler.                                                                                                                                     | "org.apache.struts.action.ExceptionHandler" |
| key       | The key to use with this handler's message resource bundle that will retrieve the error message template for this exception.                                                                    | None                                        |
| path      | The module-relative URI to the resource that will complete the request/response if this exception occurs.                                                                                       | None                                        |
| scope     | The context ("request" or "session") that is used to access the ActionMessage object [org.apache.struts.action.ActionMessage] for this exception.                                               | "request"                                   |
| type      | Fully qualified Java class name of the exception type to register with this handler.                                                                                                            | None                                        |

You can override global exception handlers by defining a handler inside an action definition.

A common use of ExceptionHandlers is to configure one for java.lang.Exception so it's called for any exception and log the exception to some data store.

<span id="plugin_classes"></span>
### <span id="a4.6_PlugIn_Classes"></span>4.6 PlugIn Classes

The *PlugIn* interface extends Action and so that applications can easily hook into the ActionServlet lifecycle. This interface defines two methods, init() and destroy(), which are called at application startup and shutdown, respectively. A common use of a Plugin Action is to configure or load application-specific data as the web application is starting up.

At runtime, any resource setup by init would be accessed by Actions or business tier classes. The PlugIn interface allows you to setup resources, but does not provide any special way to access them. Most often, the resource would be stored in application context, under a known key, where other components can find it.

PlugIns are configured using \<plug-in\> elements within the framework's configuration file. See [PlugIn Configuration](configuration.html.md#5_2_3_PlugIn_Configuration) for details.

<span id="actionmapping"></span>
### <span id="a4.7_The_ActionMapping_Implementation"></span>4.7 The ActionMapping Implementation

In order to operate successfully, our controller servlet needs to know several things about how each request URI should be mapped to an appropriate Action class. The required knowledge has been encapsulated in a Java class named *ActionMapping,* the most important properties are as follows:

-   type - Fully qualified Java class name of the Action implementation class used by this mapping.
-   name - The name of the form bean defined in the config file that this action will use.
-   path - The request URI path that is matched to select this mapping. See below for examples of how matching works and how to use wildcards to match multiple request URIs.
-   unknown - Set to true if this action should be configured as the default for this application, to handle all requests not handled by another action. Only one action can be defined as a default within a single application.
-   validate - Set to true if the validate method of the action associated with this mapping should be called.
-   forward - The request URI path to which control is passed when this mapping is invoked. This is an alternative to declaring a type property.

<span id="config"></span>
### <span id="a4.8_Writing_Action_Mappings"></span>4.8 Writing Action Mappings

How does the controller servlet learn about the mappings you want? It would be possible (but tedious) to write a small Java class that simply instantiated new ActionMapping instances, and called all of the appropriate setter methods. To make this process easier, the framework uses the Commons Digester component to parse an XML-based description of the desired mappings and create the appropriate objects initialized to the appropriate default values. See the [Commons website](http://commons.apache.org) for more information about the Digester.

The developer's responsibility is to create an XML file named struts-config.xml and place it in the WEB-INF directory of your application. The format of this document is described by the Document Type Definition (DTD) maintained at [http://struts.apache.org/dtds/struts-config\_1\_3.dtd.](../dtds/struts-config_1_3.dtd) This chapter covers the configuration elements that you will typically write as part of developing your application. There are several other elements that can be placed in the struts-config file to customize your application. See [Configuring Applications](configuration.html.md) for more about the other elements in the framework's configuration file.

The controller uses an internal copy of this document to parse the configuration; an Internet connection is not required for operation.

The outermost XML element must be \<struts-config\>. Inside of the \<struts-config\> element, there are three important elements that are used to describe your actions:

-   \<form-beans\>
-   \<global-forwards\>
-   \<action-mappings\>

**\<form-beans\>**
 This section contains your form bean definitions. Form beans are descriptors that are used to create ActionForm instances at runtime. You use a \<form-bean\> element for each form bean, which has the following important attributes:

-   name: A unique identifier for this bean, which will be used to reference it in corresponding action mappings. Usually, this is also the name of the request or session attribute under which this form bean will be stored.
-   type: The fully-qualified Java classname of the ActionForm subclass to use with this form bean.

**\<global-forwards\>**
 This section contains your global forward definitions. Forwards are instances of the ActionForward class returned from an Action's execute method. These map logical names to specific resources (typically JSPs), allowing you to change the resource without changing references to it throughout your application. You use a \<forward\> element for each forward definition, which has the following important attributes:

-   name: The logical name for this forward. This is used in your Action's execute method to forward to the next appropriate resource. Example: homepage
-   path: The context relative path to the resource. Example: /index.jsp or /index.do
-   redirect: True or false (default). Should the ActionServlet redirect to the resource instead of forward?

**\<action-mappings\>**
 This section contains your action definitions. You use an \<action\> element for each of the mappings you would like to define. Most action elements will define at least the following attributes:

-   path: The application context-relative path to the action.
-   type: The fully qualified java classname of your Action class.
-   name: The name of your \<form-bean\> element to use with this action

Other often-used attributes include:

-   parameter: A general-purpose attribute often used by "standard" Actions to pass a required property.
-   roles: A comma-delimited list of the user security roles that can access this mapping.

For a complete description of the elements that can be used with the action element, see the [configuration DTD](../dtds/struts-config_1_3.dtd) or the online [DTDDoc](../struts-core/dtddoc/struts-config_1_3.dtd.html.md) docs, and the [ActionMapping documentation.](../apidocs/org/apache/struts/action/ActionMapping.html)

<span id="action_mapping_example"></span>
### <span id="a4.8.1_ActionMapping_Example"></span>4.8.1 ActionMapping Example

Here's a mapping entry based on the MailReader example application. The MailReader application now uses DynaActionForms. But in this example, we'll show a conventional ActionForm instead, to illustrate the usual workflow. Note that the entries for all the other actions are left out:

    <struts-config>
        <form-beans>
            <form-bean
                name="logonForm"
                type="org.apache.struts.webapp.example.LogonForm" />
         </form-beans>
        <global-forwards
            type="org.apache.struts.action.ActionForward">
            <forward
                name="logon"
                path="/logon.jsp"
                redirect="false" />
        </global-forwards>
        <action-mappings>
            <action
                path="/logon"
                type="org.apache.struts.webapp.example.LogonAction"
                name="logonForm"
                scope="request"
                input="/logon.jsp"
                unknown="false"
                validate="true" />
        </action-mappings>
    </struts-config>

First the form bean is defined. A basic bean of class "org.apache.struts.webapp.example.LogonForm" is mapped to the logical name "logonForm". This name is used as a request attribute name for the form bean.

The "global-forwards" section is used to create logical name mappings for commonly used presentation pages. Each of these forwards is available through a call to your action mapping instance, i.e. mapping.findForward("logicalName").

As you can see, this mapping matches the path /logon (actually, because the MailReader example application uses extension mapping, the request URI you specify in a JSP page would end in /logon.do). When a request that matches this path is received, an instance of the *LogonAction* class will be created (the first time only) and used. The controller servlet will look for a bean in request scope under key logonForm, creating and saving a bean of the specified class if needed.

Optional but very useful are the local "forward" elements. In the MailReader example application, many actions include a local "success" and/or "failure" forward as part of an action mapping.

    <!-- Edit mail subscription -->
    <action
        path="/editSubscription"
        type="org.apache.struts.webapp.example.EditSubscriptionAction"
        name="subscriptionForm"
        scope="request"
        validate="false">
        <forward
            name="failure"
            path="/mainMenu.jsp"/>
        <forward
            name="success"
            path="/subscription.jsp"/>
    </action>

Using just these two extra properties, the Action classes are almost totally independent of the actual names of the presentation pages. The pages can be renamed (for example) during a redesign, with negligible impact on the Action classes themselves. If the names of the "next" pages were hard coded into the Action classes, all of these classes would also need to be modified. Of course, you can define whatever local forward properties makes sense for your own application.

The configuration file includes several other elements that you can use to customize your application. See [Configuring Applications](configuration.html.md) for details.

<span id="module_config-use_actions"></span>
### <span id="a4.9_Using_ActionMappings_for_Pages"></span>4.9 Using ActionMappings for Pages

Fronting your pages with ActionMappings is *essential* when using modules, since doing so is the only way you involve the controller in the request -- and you want to! The controller puts the application configuration in the request, which makes available all of your module-specific configuration data (including which message resources you are using, request-processor, and so forth).

The simplest way to do this is to use the forward property of the ActionMapping:

    <action path="/view" forward="/view.jsp"/>

<span id="action_mapping_wildcards"></span>
### <span id="a4.10_Using_Wildcards_in_ActionMappings"></span>4.10 Using Wildcards in ActionMappings

[Since Apache Struts 1.2.0] As an application grows in size, so will the number of action mappings. Wildcards can be used to combine similar mappings into one more generic mapping.

The best way to explain wildcards is to show an example and walk through how it works. This example modifies the previous mapping in the [ActionMapping Example](#4_8_1_ActionMapping_Example) section to use wildcards to match all pages that start with /edit:

    <!-- Generic edit* mapping -->
    <action
        path="/edit*"
        type="org.apache.struts.webapp.example.Edit{1}Action"
        name="{1}Form"
        scope="request"
        validate="false">
        <forward
            name="failure"
            path="/mainMenu.jsp"/>
        <forward
            name="success"
            path="/{1}.jsp"/>
    </action>

The "\*" in the path attribute allows the mapping to match the request URIs /editSubscription, editRegistration, or any other URI that starts with /edit, however /editSubscription/add would not be matched. The part of the URI matched by the wildcard will then be substituted into various attributes of the action mapping and its action forwards replacing {1}. For the rest of the request, the framework will see the action mapping and its action forwards containing the new values.

Mappings are matched against the request in the order they appear in the framework's configuration file. If more than one pattern matches the last one wins, so less specific patterns must appear before more specific ones. However, if the request URL can be matched against a path without any wildcards in it, no wildcard matching is performed and order is not important.

Wildcard patterns can contain one or more of the following special tokens:

|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| \*          | Matches zero or more characters excluding the slash ('/') character.                                                                                     |
| \*\*        | Matches zero or more characters including the slash ('/') character.                                                                                     |
| \\character | The backslash character is used as an escape sequence. Thus \\\* matches the character asterisk ('\*'), and \\\\ matches the character backslash ('\\'). |

In the action mapping and action forwards, the wildcard-matched values can be accessed with the token {N} where N is a number from 1 to 9 indicating which wildcard-matched value to substitute. The whole request URI can be accessed with the {0} token.

The action mapping attributes that will accept wildcard-matched strings are:

-   attribute
-   catalog
-   command
-   forward
-   include
-   input
-   multipartClass
-   name
-   parameter
-   prefix
-   roles
-   suffix
-   type

Also, the action mapping properties (set using the \<set-property key="foo" value="bar"\> syntax) will accept wildcard-matched strings in their value attribute.

The action forward attributes that will accept wildcard-matched strings are:

-   catalog
-   command
-   path

Like the action mapping, the action forward properties (set using the \<set-property key="foo" value="bar"\> syntax) will accept wildcard-matched strings in their value attribute.

<span id="logging"></span>
### <span id="a4.11_Commons_Logging_Interface"></span>4.11 Commons Logging Interface

The framework doesn't configure logging itself -- it's all done by [commons-logging](http://commons.apache.org/) under the covers. The default algorithm is a search:

-   If Log4J is there, use it.
-   If JDK 1.4 is there, use it.
-   Otherwise, use SimpleLog.

The commons-logging interface is an *ultra-thin* bridge to many different logging implementations. The intent is to remove compile- and run-time dependencies on any single logging implementation. For more information about the currently-supported implementations, please refer to the [the description for the org.apache.commons.logging package.](http://commons.apache.org/logging/api/index.html.md)

Because the framework uses commons-logging and, therefore, includes the necessary JAR files, you've probably had the occasional fleeting thought, *"Should I use commons-logging?"* The answer (surprise!) depends on the requirements for your particular project. If one of your requirements is the ability to easily change logging implementations with zero impact on your application, then commons-logging is a very good option.

*"Great! What do I do to get started using commons-logging in my own code?"*

Using commons-logging in your own code is very simple - all you need are two imports and a declaration for a logger. Let's take a look:

    package com.foo;
                        // ...
                        import org.apache.commons.logging.Log;
                        import org.apache.commons.logging.LogFactory;
                        ...
                        public class Foo {
                        // ...
                        private static Log log = LogFactory.getLog(Foo.class);
                        // ...
                        public void setBar(Bar bar) {
                        if (log.isTraceEnabled()) {
                        log.trace("Setting bar to " + bar);
                        }
                        this.bar = bar;
                        }
                        // ...
                        }
                    

The general idea is to instantiate a single logger per class and to use a name for the logger which reflects where it's being used. The example is constructed with the class itself. This gives the logger the name of com.foo.Foo. Doing things this way lets you easily see where the output is coming from, so you can quickly pin-point problem areas. In addition, you are able to enable/disable logging in a very fine-grained way.

For examples of using logging in the framework classes, see the Action classes in our MailReader example application.

Next: [Configuring Applications](./configuration.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


