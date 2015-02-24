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

<span id="top"></span>Newbie FAQ
--------------------------------

1.  [How do I load a custom chain config file?](#chain)
2.  [What is a modular application? What does module-relative mean?](#modules)
3.  [Why are some of the class and element names counter-intuitive?](#naming)
4.  [Whither ActionForms?](#actionForms)
5.  [Why is ActionForm a base class rather than an interface?](#actionFormInterface)
6.  [Do ActionForms have to be true JavaBeans?](#JavaBeans)
7.  [Can I use other beans or hashmaps with ActionForms?](#otherBeans)
8.  [How can I authenticate my users?](#authenticate)
9.  [Do I have to use JSPs with my application?](#jsp)
10. [Do ActionForms have to be true JavaBeans?](#formbeans)
11. [Do I have to have a separate ActionForm bean for every HTML form?](#separate)
12. [How can I prepopulate a form?](#prepopulate)
13. [Can I have an Action without a form?](#noForm)
14. [Can you give me a simple example of using the requiredif Validator rule?](#requiredif)
15. [When is the best time to validate input?](#validate)
16. [How can I avoid validating a form before data is entered?"](#avoidValidate)
17. [How can I create a wizard workflow?](#wizard)
18. [How can I 'chain' Actions?](#chaining)
19. [If you would like to contribute, here is a list of popular but undocumented questions](#undocumented)

<span id="chain"></span>How do I load a custom chain config file?  
Use the `chainConfig` init param for ActionServlet to specify a comma delimited list of chain config files.

This will override the default value of `chainConfig`, so unless you are overriding the default request processing chain, you must include the default chain config file in the list.

                            <init-param>
                                <param-name>chainConfig</param-name>
                                <param-value>
                                    org/apache/struts/chain/chain-config.xml,
                                    /WEB-INF/custom-chain-config.xml
                                </param-value>
                            </init-param>
                       

For another method of loading chain config files, see [Load a Catalog From a Web Application](http://jakarta.apache.org/commons/chain/cookbook.html.md#Load_a_Catalog_From_a_Web_Application) in the Commons Chain Cookbook.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="modules"></span>What is a modular application? What does module-relative mean?  
Since Struts 1.1, the framework supports multiple application modules. All applications have at least one root, or default, module. Like the root directory in a file system, the default application has no name. (Or is named with an empty string, depending your viewpoint.) Developing an application with only a default module is no different from how applications were developed under Struts 1.0. Since Struts 1.1, you can add additional modules to your application, each of which can have their own configuration files, messages resources, and so forth. Each module is developed in the same way as the default module. Applications that were developed as a single module can added to a multiple module application, and modules can promoted to a standalone application without change. For more about configuring your application to support multiple modules, see [Configuring Applications](../userGuide/configuration.html.md#dd_config_modules) in the User Guide.

But to answer the question =:0), a modular application is an application that uses more than one module. Module-relative means that the URI starts at the module level, rather than at the context level, or the absolute-URL level.

-   Absolute URL: http://localhost/myApplication/myModule/myAction.do
-   context-relative: /myModule/myAction.do
-   module-relative: /myAction.do

The Struts Examples application is a modular application that was assembled from several applications that were created independently.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="naming"></span>Why are some of the class and element names counter-intuitive?  
The framework grew in the telling and, as it evolved, some of the names drifted.

The good thing about a nightly build, is that everything becomes available to the community as soon as it is written. The bad thing about a nightly build is that things like class names get locked down early and then become difficult to change.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="actionForms"></span>Whither ActionForms?  
<http://www.mail-archive.com/struts-user@jakarta.apache.org/msg19281.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg19338.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg20833.html.md>

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="actionFormInterface"></span>Why is ActionForm a base class rather than an interface?  
Originally, the rationale as that making ActionForm a class takes advantage of the single inheritance restriction of Java to it makes it more difficult for people to do things that they should not do. At the time, EJBs were becoming popular, and most developers were trying to combine EJB remoting with ActionForms, and the result was not pretty.

Since then, most developers use different approaches to data persistent, and most developers now have a good understanding of why we want to separate the model from the view. Accordingly, we do plan to introduce more interfaces into the framework. It's just a matter of when.

Meanwhile, DynaActionForms relieve developers of maintaining simple ActionForms. For near zero maintenance, try [LazyActionForm](../userGuide/building_controller.html.md#lazy_action_form_classes/) and Hubert Rabago's [FormDef.](https://formdef.dev.java.net/)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="JavaBeans"></span>Do ActionForms have to be true JavaBeans?  
The utilities that the framework uses (Commons-BeanUtils since 1.1) require that ActionForm properties follow the JavaBean patterns for mutators and accessors (get\*,set\*,is\*). Since the framework uses the Introspection API with the ActionForms, some containers may require that all the JavaBean patterns be followed, including declaring `"implements Serializable"` for each subclass. The safest thing is to review the [JavaBean specification](../userGuide/preface.html.md#javabeans) and follow all the prescribed patterns.

Since Struts 1.1, you can also use DynaActionForms and mapped-backed forms, which are not true JavaBeans. For more see [ActionForm classes](../userGuide/building_controller.html.md#action_form_classes) in the User Guide and [Using Hashmaps with ActionForms](#otherBeans) in this FAQ.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="otherBeans"></span>Can I use other beans or hashmaps with ActionForms?  
Yes. There are several ways that you can use other beans or hashmaps with ActionForms.

-   ActionForms can have other beans or hashmaps as properties
-   "Value Beans" or "Data Transfer Objects" (DTOs) can be used independently of ActionForms to transfer data to the view
-   ActionForms can use Maps to support "dynamic" properties (since Struts 1.1)

ActionForms (a.k.a. "form beans") are really just JavaBeans (with a few special methods) that the framework creates and puts into session or request scope for you. There is nothing preventing you from using other beans, or including them in your form beans. Let's look at some examples.

*Collections as properties* Suppose that you need to display a pulldown list of available colors on an input form in your application. You can include a string-valued `colorSelected` property in your `ActionForm` to represent the user's selection and a `colorOptions` property implemented as a `Collection` (of strings) to store the available color choices. Assuming that you have defined the getters and setters for the `colorSelected` and `colorOptions` properties in your `orderEntryForm` form bean, you can render the pulldown list using:

                        .html.md:select property="colorSelected">
                        .html.md:options property="colorOptions"
                        name="orderEntryForm"/>
                        <.html.md:select>
                   

The list will be populated using the strings in the `colorOptions` collection of the `orderEntryForm` and the value that the user selects will go into the `colorSelected` property that gets posted to the subsequent `Action` . Note that we are assuming here that the `colorOptions` property of the `orderEntryForm` has already been set.

See [How can I prepopulate a form?](#prepopulate) for instructions on how to set form bean properties before rendering edit forms that expect properties to be pre-set.

*Independent DTO* An `Action` that retrieves a list of open orders (as an `ArrayList` of `Order` objects) can use a DTO independently of any form bean to transfer search results to the view. First, the Action's `execute` method performs the search and puts the DTO into the request:

                        ArrayList results =
                        businessObject.executeSearch(searchParameters);
                        request.setAttribute("searchResults",results);
                   

Then the view can iterate through the results using the "searchResults" request key to reference the DTO: \`

                        <logic:iterate id="order" name="searchResults"
                        type="com.foo.bar.Order">
                        <tr><td><bean:write name="order"
                        property="orderNumber"/><td>
                        <td>..other properties...</td></tr>
                        </logic:iterate>
                   

See also: [Map-Backed ActionForms](../userGuide/building_controller.html.md#map_action_form_classes) (since Struts 1.1)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="authenticate"></span>How can I authenticate my users?  
<http://www.mail-archive.com/struts-user@jakarta.apache.org/msg24504.html.md>
 <http://www.mail-archive.com/struts-user@jakarta.apache.org/msg22949.html.md>

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="jsp"></span>Do I have to use JSPs with my application?  
The short answer to this question is: No, you are not limited to JavaServer Pages.

The longer answer is that you can use any type of presentation technology which can be returned by a web server or Java container. The list includes but is not limited to:

-   JavaServer Pages,
-   HTML pages,
-   WML files,
-   Java servlets,
-   Velocity templates, and
-   XML/XLST

Some people even mix and match apparently unrelated technologies, like PHP, into the same web application.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="formbeans"></span>Do ActionForms have to be true JavaBeans?  
ActionForms are added to a servlet scope (session or request) as beans. What this means is that, for certain functionality to be available, your ActionForms will have to follow a few simple rules.

First, your ActionForm bean must have a zero-arguments constructor. This is required because the framework must be able to dynamically create new instances of your form bean class, while knowing only the class name. This is not an onerous restriction, however, because the framework will also populate your form bean's properties (from the request parameters) for you.

Second, the fields of your form bean are made available to the framework by supplying public getter and setter methods that follow the naming design patterns described in the JavaBeans Specification. For most users, that means using the following idiom for each of your form bean's properties:

                        private {type} fieldName;

                        public {type} getFieldName() {
                        return (this.fieldName);
                        }

                        public void setFieldName({type} fieldName) {
                        this.fieldName = fieldName;
                        }
                   

**NOTE** - you *MUST* obey the capitalization conventions shown above for your ActionForm properties to be recognized. The property name in this example is "fieldName", and that must also be the name of the input field that corresponds to this property. A bean property may have a "getter" method and a "setter" method (in a form bean, it is typical to have both) whose name starts with "get" or "set", followed by the property name with the first character capitalized. (For boolean properties, it is also legal to use "is" instead of "get" as the prefix for the getter method.)

Advanced JavaBeans users will know that you can tell the system you want to use different names for the getter and setter methods, by using a `java.beans.BeanInfo` class associated with your form bean. Normally, however, it is much more convenient to follow the standard conventions.

**WARNING** - developers might be tempted to use one of the following techniques, but any of them will cause your property not to be recognized by the JavaBeans introspection facilities, and therefore cause your applications to misbehave:

-   *Using getter and setter method names that do not match* - if you have a `getFoo()` method for your getter, but a `setBar()` method for your setter, Java will not recognize these methods as referring to the same property. Instead, the language will think you have a read-only property named "foo" and a write-only property named "bar".
-   *Using more than one setter method with the same name* - The Java language lets you "overload" methods, as long as the argument types are different. For example, you could have a `setStartDate(java.util.Date date)` method and a `setStartDate(String date)` method in the same class, and the compiled code would know which method to call based on the parameter type being passed. However, doing this for form bean properties will prevent Java from recognizing that you have a "startDate" property at all.

There are other rules to follow if you want other features of your form beans to be exposed, especially in terms of indexed attributes and mapped attributes. Specific rules are covered in detail in other areas of the documentation, in particular, [Indexed Properties, Mapped Properties, and Indexed Tags.](indexedprops.html.md)

For a complete explanation of what a JavaBean is, and everything it can do, see the [JavaBeans Specification (version 1.01).](http://java.sun.com/products/javabeans/docs/beans.101.pdf)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="separate"></span>Do I have to have a separate ActionForm bean for every HTML form?  
This is an interesting question. As a newbie, it is a good practice to create a new `ActionForm` for each action sequence. You can use `DynaActionForm` s to help reduce the effort required, or use the code generation facilities of your IDE.

Some issues to keep in mind regarding reuse of form beans are as follows:

-   *Validation* - You might need to use different validation rules depending upon the action that is currently being executed.
-   *Persistence* - Be careful that a form populated in one action is not **unexpectedly** reused in a different action. Multiple `<form-bean>` entries in `struts-config.xml` for the same `ActionForm` subclass can help (especially if you store your form beans in session scope). Alternatively, storing form beans in request scope can avoid unexpected interactions (as well as reduce the memory footprint of your application, because no server-side objects will need to be saved in between requests.
-   *Checkboxes* - If you do as recommended and reset your boolean properties (for fields presented as checkboxes), and the page you are currently displaying does not have a checkbox for every boolean property on the form bean, the undisplayed boolean properties will always appear to have a `false` value.
-   *Workflow* - The most common need for form bean reuse is workflow. Out of the box, the framework has limited support for workflow, but a common pattern is to use a single form bean with all of the properties for all of the pages of a workflow. You will need a good understanding of the environment ( `ActionForm` s, `Action` s, etc.) prior to being able to put together a smooth workflow environment using a single form bean.

As you get more comfortable, there are a few shortcuts you can take in order to reuse your `ActionForm` beans. Most of these shortcuts depend on how you have chosen to implement your `Action` / `ActionForm` combinations.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="prepopulate"></span>How can I prepopulate a form?  
The simplest way to prepopulate a form is to have an `Action` whose sole purpose is to populate an `ActionForm` and forward to the servlet or JSP to render that form back to the client. A separate `Action` would then be use to process the submitted form fields, by declaring an instance of the same form bean name.

The *MailReader* application, part of the Struts Applications subrpoject, illustrates this design pattern nicely. Note the following definitions from the `struts-config.xml` file:

                        ...
                        <form-beans>
                        ...
                        <-- Registration form bean -->
                        <form-bean name="registrationForm"
                        type="org.apache.struts.webapp.example.RegistrationForm"/>
                        ...
                        </form-beans>
                        ...
                        <action-mappings>
                        ...
                        <-- Edit user registration -->
                        <action path="/editRegistration"
                        type="org.apache.struts.webapp.example.EditRegistrationAction"
                        name="registrationForm"
                        scope="request"
                        validate="false"/>
                        ...
                        <-- Save user registration -->
                        <action path="/saveRegistration"
                        type="org.apache.struts.webapp.example.SaveRegistrationAction"
                        name="registrationForm"
                        input="registration"
                        scope="request"/>
                        ...
                        </action-mappings>
                   

Note the following features of this approach:

-   Both the `/editRegistration` and `/saveRegistration` actions use the same form bean.
-   When the `/editRegistration` action is entered, the framework will have pre-created an empty form bean instance, and passed it to the `execute()` method. The setup action is free to preconfigure the values that will be displayed when the form is rendered, simply by setting the corresponding form bean properties.
-   When the setup action completes configuring the properties of the form bean, it should return an `ActionForm` that points at the page which will display this form. If you are using the Struts JSP tag library, the `action` attribute on your \.html.md:form\> tag will be set to `/saveRegistration` in order for the form to be submitted to the processing action.
-   Note that the setup action ( `/editRegistration` ) turns off validation on the form that is being set up. You will normally want to include this attribute in the configuration of your setup actions, because you are not planning to actually process the results -- you simply want to take advantage of the fact that the framework will precreate a form bean instance of the correct class for you.
-   The processing action ( `/saveRegistration` ), on the other hand, leaves out the `validate` attribute, which defaults to `true` . This tells the framework to perform the validations associated with this form bean before invoking the processing action at all. If any validation errors have occurred, the framework will forward back to your input page (technically, it forwards back to an `ActionForward` named "registration" in this case, because the example webapp uses the `inputForward` attribute in the `<controller>` element -- see the documentation describing `struts-config.xml` for more information) instead of calling your processing action.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="noForm"></span>Can I have an Action without a form?  
Yes. If your `Action` does not need any data and it does not need to make any data available to the view or controller component that it forwards to, it doesn't need a form. A good example of an `Action` with no `ActionForm` is the `LogoffAction` in the Struts MailReader application:

                        <action path="/logoff"
                        type="org.apache.struts.webapp.example.LogoffAction">
                        <forward name="success" path="/index.jsp"/>
                        </action>
                   

This action needs no data other than the user's session, which it can get from the `Request` , and it doesn't need to prepare any view elements for display, so it does not need a form.

However, you cannot use the \.html.md:form\> **tag** without an ActionForm. Even if you want to use the \<html:form\> tag with a simple Action that does not require input, the tag will expect you to use some type of ActionForm, even if it is an empty subclass without any properties.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="requiredif"></span>Can you give me a simple example of using the requiredif Validator rule?  
First off, there's an even newer Validator rule called `validwhen` , which is almost certainly what you want to use, since it is much easier and more powerful. It will be available in the first release after 1.1 ships. The example shown below could be coded with validwhen as:

                        <form name="medicalStatusForm">

                        <field
                        property="pregnancyTest" depends="validwhen">
                        <arg0 key="medicalStatusForm.pregnancyTest.label"/>
                        <var>
                        <var-name>test</var-name>
                        <var-value>((((sex == 'm') OR (sex == 'M')) AND
                        (*this* == null)) OR (*this* != null))</test>
                        </var>
                        </field>
                   

Let's assume you have a medical information form with three fields, sex, pregnancyTest, and testResult. If sex is 'f' or 'F', pregnancyTest is required. If pregnancyTest is not blank, testResult is required. The entry in your validation.xml file would look like this:

                        <form name="medicalStatusForm">

                        <field
                        property="pregnancyTest" depends="requiredif">
                        <arg0 key="medicalStatusForm.pregnancyTest.label"/>
                        <var>
                        <var-name>field[0]</var-name>
                        <var-value>sex</var-value>
                        </var>
                        <var>
                        <var-name>fieldTest[0]</var-name>
                        <var-value>EQUAL</var-value>
                        </var>
                        <var>
                        <var-name>fieldValue[0]</var-name>
                        <var-value>F</var-value>
                        </var>
                        <var>
                        <var-name>field[1]</var-name>
                        <var-value>sex</var-value>
                        </var>
                        <var>
                        <var-name>fieldTest[1]</var-name>
                        <var-value>EQUAL</var-value>
                        </var>
                        <var>
                        <var-name>fieldValue[1]</var-name>
                        <var-value>f</var-value>
                        </var>
                        <var>
                        <var-name>fieldJoin</var-name>
                        <var-value>OR</var-value>
                        </var>
                        </field>

                        <field
                        property="testResult" depends="requiredif">
                        <arg0 key="medicalStatusForm.testResult.label"/>
                        <var>
                        <var-name>field[0]</var-name>
                        <var-value>pregnancyTest</var-value>
                        </var>
                        <var>
                        <var-name>fieldTest[0]</var-name>
                        <var-value>NOTNULL</var-value>
                        </var>
                        </field>
                        </form>
                   

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="validate"></span>When is the best time to validate input?  
This is an excellent question. Let's step back a second and think about a typical mid to large size application. If we start from the back end and work toward the view we have:

1) Database: Most modern databases are going to validate for required fields, duplicate records, security constraints, etc.

2) Business Logic: Here you are going to check for valid data relationships and things that make sense for the particular problem you are triing to solve.

... This is where the framework comes into the picture, by now the system should be pretty well bulletproof. What we are going to do is make validation friendlier and informative. Rember it is OK to have duplicate validations...

3) `ActionErrors validate(ActionMapping map, HttpServletRequest req)` is where you can do your validation and feed back to the view, information required to correct any errors. `validate` is run after the form has been `reset` and after the `ActionForm` properties have been set from corresponding view based input. Also remember you can turn validation off with `validate="false"` in the `action` mapping in the `struts-config.xml` . This is done by returning an `ActionErrors` collection with messages from your `ApplicationResources.properties` file.

Here you have access to the request so you can see what kinds of action is being requested to fine tune your validations. The \.html.md:error\> tag allows you to dump all errors on your page or a particular error associated with a particular property. The `input` attribute of the `struts-config.xml` `action` allows you to send validation errors to a particular jsp / html / tile page.

4) You can have the system perform low level validations and client side feedback using a `ValidatorForm` or its derivatives. This will generate javascript and give instant feedback to the user for simple data entry errors. You code your validations in the `validator-rules.xml` file. A working knowledge of [regular expressions](http://etext.lib.virginia.edu/helpsheets/regex.html.md) is necessary to use this feature effectively. For more information, see [User Guide](../userGuide/dev_validator.html)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="avoidValidate"></span>How can I avoid validating a form before data is entered?"  
The simplest way is to have two actions. The first one has the job of setting the form data, i.e. a blank registration screen. The second action in our writes the registration data to the database. The framework would take care of invoking the validation and returning the user to the correct screen if validation was not complete.

The EditRegistration action in the Struts MailReader application illustrates this:

                        <action path="/editRegistration"
                        type="org.apache.struts.webapp.example.EditRegistrationAction"
                        attribute="registrationForm"
                        scope="request"
                        validate="false">
                        <forward name="success path="/registration.jsp"/>
                        </action>
                   

When the /editRegistration action is invoked, a registrationForm is created and added to the request, but its validate method is not called. The default value of the `validate` attribute is `true` , so if you do not want an action to trigger form validation, you need to remember to add this attribute and set it to `false` .

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="wizard"></span>How can I create a wizard workflow?  
The basic idea is a series of actions with next, back, cancel and finish actions with a common bean. Using a LookupDispatchAction is reccomended as it fits the design pattern well and can be internationalized easily. Since the bean is shared, each choice made will add data to the wizards base of information. A sample of struts-config.xml follows:

                        <form-beans>
                        <form-bean name="MyWizard"
                        type="forms.MyWizard" />
                        </form-beans>

                        <!-- the first screen of the wizard (next action only
                        available) -->
                        <!-- no validation, since the finish action is not
                        available -->
                        <actions>
                        <action path="/mywizard1"
                        type="actions.MyWizard"
                        name="MyWizard"
                        validate="false"
                        input="/WEB-INF/jsp/mywizard1.jsp">
                        <forward name="next"
                        path="/WEB-INF/jsp/mywizard2.jsp" />
                        <forward name="cancel"
                        path="/WEB-INF/jsp/mywizardcancel.jsp" />
                        </action>

                        <!-- the second screen of the wizard (back, next and
                        finish) -->
                        <!-- since finish action is available, bean should
                        validated, note
                        validation should not necessarily validate if back action
                        requested, you
                        might delay validation or do conditional validation -->
                        <action path="/mywizard2"
                        type="actions.MyWizard"
                        name="MyWizard"
                        validate="true"
                        input="/WEB-INF/jsp/mywizard2.jsp">
                        <forward name="back"
                        path="/WEB-INF/jsp/mywizard1.jsp" />
                        <forward name="next"
                        path="/WEB-INF/jsp/mywizard3.jsp" />
                        <forward name="finish"
                        path="/WEB-INF/jsp/mywizarddone.jsp" />
                        <forward name="cancel"
                        path="/WEB-INF/jsp/mywizardcancel.jsp" />
                        </action>

                        <!-- the last screen of the wizard (back, finish and
                        cancel only) -->
                        <action path="/mywizard3"
                        type="actions.MyWizard"
                        name="MyWizard"
                        validate="true"
                        input="/WEB-INF/jsp/mywizard3.jsp">
                        <forward name="back"
                        path="/WEB-INF/jsp/mywizard2.jsp" />
                        <forward name="finish"
                        path="/WEB-INF/jsp/mywizarddone.jsp" />
                        <forward name="cancel"
                        path="/WEB-INF/jsp/mywizardcancel.jsp" />
                        </action>
                   

The pieces of the wizard are as follows:

**forms.MyWizard.java** - the form bean holding the information required

**actions.MyWizard.java** - the actions of the wizard, note the use of LookupDispatchAction allows for one action class with several methods. All the real work will be done in the 'finish' method.

**mywizard[x].jsp** - the data collection jsp's

**mywizarddone.jsp** - the 'success' page

**mywizardcancel.jsp** - the 'cancel' page

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="chaining"></span>How can I 'chain' Actions?  
Chaining actions can be done by simply using the proper mapping in your forward entries in the struts-config.xml file. Assume you had the following two classes:

        /* com/AAction.java */
        ...

        public class AAction extends Action
        {
            public ActionForward
                    execute(ActionMapping mapping,
                            ActionForm form,
                            HttpServletRequest request,
                            HttpServletResponse response) throws
                                                          Exception
            {
                // Do something

                return mapping.findForward("success");
            }
        }
        

        /* com/BAction.java */
        ...

        public class BAction extends Action
        {
            public ActionForward
                    execute(ActionMapping mapping,
                            ActionForm form,
                            HttpServletRequest request,
                            HttpServletResponse response) throws
                                                          Exception
            {
                // Do something else

                return mapping.findForward("success");
            }
        }
        

Then you can chain together these two actions with the Struts configuration as shown in the following excerpt:

        ...
        <action-mappings type="org.apache.struts.action.ActionMapping">
           <action path="/A"
                   type="com.AAction"
                   validate="false">
              <forward name="success" path="/B.do" />
           </action>
           <action path="/B"
                   type="com.BAction"
                   scope="session"
                   validate="false">
              <forward name="success" path="/result.jsp" />
           </action>
        </action-mappings>
        ...
        

Here we are assuming you are using a suffix-based ( `.do` ) servlet mapping, which is recommended since module support requires it. When you send your browser to the web application and name the action `A.do` (i.e. `http://localhost:8080/app/A.do` ) it will execute `AAction.execute()` , which will then forward to the "success" mapping.

This causes the execution of `BAction.execute()` since the `<forward>` entry for "success" in the configuration file uses the `.do` suffix.

Of course it is also possible to chain actions programmatically, but the power and ease of being able to "reroute" your web application's structure using the XML configuration file is much easier to maintain.

As a rule, chaining Actions is **not** recommended. If your business classes are properly factored, you should be able to call whatever methods you need from any Action, without splicing them together into a cybernetic Rube Goldberg device.

If you must chain Actions, be aware of the following: calling the second Action from the first Action has the same effect as calling the second Action from scratch. If both of your Actions change the properties of a formbean, the changes made by the first Action will be lost because the framework calls the reset() method on the formbean when the second Action is called.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="undocumented"></span>If you would like to contribute, here is a list of popular but undocumented questions  
-   How can I capture binary or formatted values, like dates or telephone numbers?
-   Can I create dynamic ActionForwards?
-   How can I use my own (ActionForm, ActionForward, ActionMapping, ActionServlet) class?

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


