<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/)

------------------------------------------------------------------------

##### Struts 1

-   **Welcome**
-   [Learning](learning.html.md)
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

<span id="Welcome_to_Struts_1"></span>Welcome to Struts 1
---------------------------------------------------------

<span id="Welcome"></span>
Struts is a flexible control layer based on [standard technologies](userGuide/preface.html.md) like Java Servlets, JavaBeans, ResourceBundles, and XML, as well as various [Apache Commons](http://commons.apache.org/index.html) packages, like BeanUtils and Chain of Responsibility. The framework helps you create an extensible development environment for your application, based on published standards and proven design patterns.

### <span id="Struts_in_a_Nutshell"></span>Struts in a Nutshell

<span id="nutshell"></span>
The framework provides its own web **Controller** component and integrates with other technologies to provide the Model and the View. For the **Model,** the framework can interact with standard data access technologies, like [JDBC](http://java.sun.com/products/jdbc/) and [EJB,](http://java.sun.com/products/ejb/) as well as most any third-party packages, like [Hibernate,](http://hibernate.org/)[iBATIS,](http://ibatis.apache.org/) or [Object Relational Bridge.](http://db.apache.org/ojb/) For the **View,** the framework works well with [JavaServer Pages,](http://java.sun.com/products/jsp/) including [JSTL](struts-el/index.html.md) and [JSF,](struts-faces/index.html) as well as [Velocity Templates,](http://velocity.apache.org/tools/struts/)[XSLT,](http://stxx.sourceforge.net/) and other presentation systems.

The framework's Controller acts as a bridge between the application's Model and the web View. When a request is received, the Controller invokes an **Action** class. The Action class consults with the Model (or, preferably, a **Facade** representing your Model) to examine or update the application's state. The framework provides an **ActionForm** class to help transfer data between Model and View.

Most often, the Model is represented as a set of **JavaBeans.** Typically, developers will use the Commons **BeanUtils** to transfer data between ActionForms and the Model objects (or a Facade). Preferably, the Model will do the "heavy lifting", and the Action will act as a "traffic cop" or adapter.

### <span id="Struts_Config_in_a_Nutshell"></span>Struts Config in a Nutshell

<span id="nutshell-config"></span>
A web application uses a deployment descriptor to initialize resources like [servlets](userGuide/preface.html.md#servlets) and [taglibs.](userGuide/preface.html#jsp) The deployment descriptor is formatted as a [XML](userGuide/preface.html#xml) document and named "web.xml". Likewise, the framework uses a configuration file to initialize its own resources. These resources include [ActionForms](userGuide/building_controller.html#action_form_classes) to collect input from users, [ActionMappings](http://struts.apache.org/userGuide/building_controller.html#actionmapping) to direct input to server-side [Actions,](http://struts.apache.org/userGuide/building_controller.html#action_classes) and ActionForwards to select output pages.

Here's a simple configuration (struts-config.xml) for a login workflow:


        <?xml version="1.0" encoding="ISO-8859-1" ?>
        <!DOCTYPE struts-config PUBLIC
              "-//Apache Software Foundation//DTD Struts Configuration 1.3//EN"
              "http://struts.apache.org/dtds/struts-config_1_3.dtd">
        <struts-config>
            <form-beans>
                <form-bean
                    name="logonForm"
                    type="app.LogonForm"/>
            </form-beans>
            <action-mappings>
                <action
                    path="/Welcome"
                    forward="/pages/Welcome.jsp"/>
                <action
                    path="/Logon"
                    forward="/pages/Logon.jsp"/>
                <action
                    path="/LogonSubmit"
                    type="app.LogonAction"
                    name="logonForm"
                    scope="request"
                    validate="true"
                    input="/pages/Logon.jsp">
                    <forward
                        name="success"
                        path="/pages/Welcome.jsp"/>
                    <forward
                        name="failure"
                        path="/pages/Logon.jsp"/>
                </action>
                <action
                    path="/Logoff"
                    type="app.LogoffAction">
                    <forward
                        name="success"
                        path="/pages/Logoff.jsp"/>
                </action>
            </action-mappings>
            <message-resources parameter="resources.application"/>
        </struts-config>
        

There are several other resources you can specify in the framework's configuration file. You can specify validations for the ActionForms in an XML descriptor, using the [Struts Validator](faqs/validator.html.md). A standard extension, [Tiles](http://struts.apache.org/struts-tiles/dev_tiles.html), helps you build pages from smaller fragments.

Struts is extensible. Every class deployed by the framework can be replaced by your own default class. The properties of your default class can be set using the [Digester's](http://commons.apache.org/digester/)`set-property` feature. This is one reason why there are so many [contributor extensions.](learning.html.md#resources) We provide the base framework, but you can still write **your** application **your** way.

For more about the framework and its underlying technologies, see the [User Guide.](userGuide/index.html.md)

### <span id="Is_Struts_the_best_choice_for_every_project"></span>Is Struts the best choice for every project?

No. If you need to write a very simple application, with a handful of pages, then you might consider a "Model 1" solution that uses only server pages.

But, if you are writing a more complicated application, with dozens of pages, that need to be maintained over time, then Struts can help. For more about whether Model 1 or MVC/Model 2 is right for you, see [Understanding JavaServer Pages Model 2 architecture.](http://www.javaworld.com/javaworld/jw-12-1999/jw-12-ssj-jspmvc.html.md)

Next: [Learning about Struts](learning.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


