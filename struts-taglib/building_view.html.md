<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Taglib

-   [Welcome](index.html.md)

##### FAQs and HOWTOs

-   [Taglib FAQ](faq.html.md)
-   **Building View Components**
-   [Indexed Properties](indexedprops.html.md)

##### Struts Taglib Guides

-   [Bean](dev_bean.html.md)
-   [HTML](dev.html.md.html)
-   [Logic](dev_logic.html.md)
-   [Nested](dev_nested.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Related Resources

-   [Display Tag](http://displaytag.sourceforge.net/)
-   .html.md2](http://www.rabago.net/struts/html2/)
-   [JSTL](http://java.sun.com/products/jsp/jstl/)
-   [JSF](http://java.sun.com/j2ee/javaserverfaces/)
-   [Struts Layout](http://struts.application-servers.com)
-   [Struts Menu](http://struts-menu.sourceforge.net/)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="How_to_Build_View_Components"></span>How to Build View Components
---------------------------------------------------------------------------

This section focuses on the task of building the *View* components for use with Struts. Many applications rely on JavaServer Pages (JSP) technology to create the presentation layer. The distribution includes a comprehensive JSP tag library that provides support for building internationalized applications, as well as for interacting with input forms. Several other topics related to the View components are briefly discussed.

### <span id="Internationalized_Messages"></span>Internationalized Messages

A few years ago, application developers could count on having to support only residents of their own country, who are used to only one (or sometimes two) languages, and one way to represent numeric quantities like dates, numbers, and monetary values. However, the explosion of application development based on web technologies, as well as the deployment of such applications on the Internet and other broadly accessible networks, have rendered national boundaries invisible in many cases. This has translated (if you will pardon the pun) into a need for applications to support *internationalization* (often called "i18n" because 18 is the number of letters in between the "i" and the "n") and *localization* .

The framework builds upon the standard classes available on the Java platform to build internationalized and localized applications. The key concepts to become familiar with are:

-   [**Locale**](http://java.sun.com/j2se/1.4.1/docs/api/java/util/Locale.html.md) - The fundamental Java class that supports internationalization is `Locale` . Each `Locale` represents a particular choice of country and language (plus an optional language variant), and also a set of formatting assumptions for things like numbers and dates.
-   [**ResourceBundle**](http://java.sun.com/j2se/1.4.1/docs/api/java/util/ResourceBundle.html.md) - The `java.util.ResourceBundle` class provides the fundamental tools for supporting messages in multiple languages. See the Javadocs for the `ResourceBundle` class, and the information on Internationalization in the documentation bundle for your JDK release, for more information.
-   [**PropertyResourceBundle**](http://java.sun.com/j2se/1.4.1/docs/api/java/util/PropertyResourceBundle.html.md) - One of the standard implementations of `ResourceBundle` allows you to define resources using the same "name=value" syntax used to initialize properties files. This is very convenient for preparing resource bundles with messages that are used in a web application, because these messages are generally text oriented.
-   [**MessageFormat**](http://java.sun.com/j2se/1.4.1/docs/api/java/text/MessageFormat.html.md) - The `java.text.MessageFormat` class allows you to replace portions of a message string (in this case, one retrieved from a resource bundle) with arguments specified at run time. This is useful in cases where you are creating a sentence, but the words would appear in a different order in different languages. The placeholder string `{0}` in the message is replaced by the first runtime argument, `{1}` is replaced by the second argument, and so on.
-   [**MessageResources**](../struts-action/apidocs/org/apache/struts/util/MessageResources.html.md) - The framework class `org.apache.struts.util.MessageResources` lets you treat a set of resource bundles like a database, and allows you to request a particular message string for a particular Locale (normally one associated with the current user) instead of for the default Locale the server itself is running in.

Please note that the i18n support in a framework like Struts is limited to the **presentation** of internationalized text and images to the user. Support for Locale specific **input methods** (used with languages such as Japanese, Chinese, and Korean) is left up to the client device, whichis usually a web browser.

For an internationalized application, follow the steps described in the Internationalization document in the JDK documentation bundle for your platform to create a properties file containing the messages for each language. An example will illustrate this further:

Assume that your source code is created in package `com.mycompany.mypackage` , so it is stored in a directory (relative to your source directory) named `com/mycompany/mypackage` . To create a resource bundle called `com.mycompany.mypackage.MyApplication` , you would create the following files in the `com/mycompany/mypackage` directory:

-   **MyApplication.properties** - Contains the messages in the default language for your server. If your default language is English, you might have an entry like this: `prompt.hello=Hello`
-   **MyApplication\_xx.properties** - Contains the same messages in the language whose ISO language code is "xx" (See the [ResourceBundle Javadoc](http://java.sun.com/j2se/1.4.1/docs/api/java/util/ResourceBundle.html.md) page for a link to the current list). For a French version of the message shown above, you would have this entry: `prompt.hello=Bonjour` You can have resource bundle files for as many languages as you need.

When you configure the controller servlet in the web application deployment descriptor, one of the things you will need to define in an initialization parameter is the base name of the resource bundle for the application. In the case described above, it would be `com.mycompany.mypackage.MyApplication` .

    <servlet>
    <servlet-name>action</servlet-name>
    <servlet-class>
    org.apache.struts.action.ActionServlet
    </servlet-class>
    <init-param>
    <param-name>application</param-name>
    <param-value>
        com.mycompany.mypackage.MyResources
    </param-value>
    </init-param>
    <!-- ... -->
    </servlet>

The important thing is for the resource bundle to be found on the class path for your application. Another approach is to store the `MyResources.properties` file in your application's `classes` folder. You can then simply specify "myResources" as the application value. Just be careful it is not deleted if your build script deletes classes as part of a "clean" target.

If it does, here is an Ant task to run when compiling your application that copies the contents of a `src/conf` directory to the `classes` directory:

    <!-- Copy any configuration files -->
    <copy todir="classes">
    <fileset dir="src/conf"/>
    </copy>

### <span id="Forms_and_FormBean_Interactions"></span>Forms and FormBean Interactions

**Note:** While the examples given here use JSP and custom tags, the ActionForm beans and the other controller components are View neutral. Struts can be used with Velocity Templates, XSL, and any other presentation technology that can be rendered via a Java servlet.

At one time or another, most web developers have built forms using the standard capabilities of HTML, such as the `<input>` tag. Users have come to expect interactive applications to have certain behaviors, and one of these expectations relates to error handling -- if the user makes an error, the application should allow them to fix just what needs to be changed -- without having to re-enter any of the rest of the information on the current page or form.

Fulfilling this expectation is tedious and cumbersome when coding with standard HTML and JSP pages. For example, an input element for a `username` field might look like this (in JSP):

    <input type="text" name="username"
    value="<%= loginBean.getUsername() >"/>

which is difficult to type correctly, confuses HTML developers who are not knowledgeable about programming concepts, and can cause problems with HTML editors. Instead, Struts provides a comprehensive facility for building forms, based on the Custom Tag Library facility of JSP 1.1. The case above would be rendered like this using Struts:

    .html.md:text property="username"/>;

with no need to explicitly refer to the JavaBean from which the initial value is retrieved. That is handled automatically by the JSP tag, using facilities provided by the framework.

HTML forms are sometimes used to upload other files. Most browsers support this through a \<input type="file"\> element, that generates a file browse button, but it's up to the developer to handle the incoming files. Struts handles these "multipart" forms in a way identical to building normal forms.

For an example of using Struts to create a simple login form, see the [Buiding an ActionForm Howto.](../faqs/actionForm.html.md)

### <span id="Indexed_and_Mapped_Properties"></span>Indexed and Mapped Properties

Property references in JSP pages using the Struts framework can reference Java Bean properties as described in the JavaBeans specification. Most of these references refer to "scalar" bean properties, referring to primitive or single Object properties. However, Struts, along with the Commons Beanutils library, allow you to use property references which refer to individual items in an array, collection, or map, which are represented by bean methods using well-defined naming and signature schemes.

Documentation on the Beanutils package can be found at [http://commons.apache.org/beanutils/api/index.html.md.](http://commons.apache.org/beanutils/api/index.html) More information about using indexed and mapped properties in Struts can be found in the FAQ describing [*Indexed Properties, Mapped Properties, and Indexed Tags.*](../faqs/indexedprops.html)

### <span id="Input_Field_Types_Supported"></span>Input Field Types Supported

Struts defines HTML tags for all of the following types of input fields, with hyperlinks to the corresponding reference information.

-   [checkboxes](struts.html.md.html#checkbox)
-   [hidden](struts.html.md.html#hidden) fields
-   [password](struts.html.md.html#password) input fields
-   [radio](struts.html.md.html#radio) buttons
-   [reset](struts.html.md.html#reset) buttons
-   [select](struts.html.md.html#select) lists with embedded option or options items
-   [option](struts.html.md.html#option)
-   [options](struts.html.md.html#options)
-   [submit](struts.html.md.html#submit) buttons
-   [text](struts.html.md.html#text) input fields
-   [textareas](struts.html.md.html#textarea)

In every case, a field tag must be nested within a `form` tag, so that the field knows what bean to use for initializing displayed values.

### <span id="Other_Useful_Presentation_Tags"></span>Other Useful Presentation Tags

There are several tags useful for creating presentations, consult the documentation on each specific tag library, along with the Tag Developers Guides, for more information:

-   [logic] [iterate](struts-logic.html.md#iterate) repeats its tag body once for each element of a specified collection (which can be an Enumeration, a Hashtable, a Vector, or an array of objects).
-   [logic] [present](struts-logic.html.md#present) depending on which attribute is specified, this tag checks the current request, and evaluates the nested body content of this tag only if the specified value is present. Only one of the attributes may be used in one occurrence of this tag, unless you use the property attribute, in which case the name attribute is also required. The attributes include cookie, header, name, parameter, property, role, scope, and user.
-   [logic] [notPresent](struts-logic.html.md#notPresent) the companion tag to present, notPresent provides the same functionality when the specified attribute is not present.
-   .html.md] [link](struts-html.html#link) generates a HTML \<a\> element as an anchor definition or a hyperlink to the specified URL, and automatically applies URL encoding to maintain session state in the absence of cookie support.
-   .html.md] [img](struts-html.html#img) generates a HTML \<img\> element with the ability to dynamically modify the URLs specified by the "src" and "lowsrc" attributes in the same manner that \<html:link\> can.
-   [bean] [parameter](struts-bean.html.md#parameter) retrieves the value of the specified request parameter, and defines the result as a page scope attribute of type String or String[].

### <span id="Automatic_Form_Validation"></span>Automatic Form Validation

In addition to the form and bean interactions described above, the framework offers an additional facility to validate the input fields it has received. To utilize this feature, override the following method in your ActionForm class:

    validate(ActionMapping mapping,
    HttpServletRequest request);

The `validate` method is called by the controller servlet after the bean properties have been populated, but before the corresponding action class's `execute` method is invoked. The `validate` method has the following options:

-   Perform the appropriate validations and find no problems -- Return either `null` or a zero-length ActionErrors instance, and the controller servlet will proceed to call the `perform` method of the appropriate `Action` class.
-   Perform the appropriate validations and find problems -- Return an ActionErrors instance containing `ActionMessage` 's, which are classes that contain the error message keys (into the application's `MessageResources` bundle) that should be displayed. The controller servlet will store this array as a request attribute suitable for use by the `.html.md:errors>` tag, and will forward control back to the input form (identified by the `input` property for this `ActionMapping` ).

As mentioned earlier, this feature is entirely optional. The default implementation of the `validate` method returns `null` , and the controller servlet will assume that any required validation is done by the action class.

One common approach is to perform simple, prima facia validations using the ActionForm `validate` method, and then handle the "business logic" validation from the Action.

The Struts Validator, covered in the next section, may be used to easily validate ActionForms.

<span id="other_presentations"></span>
### <span id="Other_Presentation_Techniques"></span>Other Presentation Techniques

Although the look and feel of your application can be completely constructed based on the standard capabilities of JSP and Struts Taglibs, you should consider employing other techniques that will improve component reuse, reduce maintenance efforts, and/or reduce errors. Several options are discussed in the following sections.

### <span id="Application-Specific_Custom_Tags"></span>Application-Specific Custom Tags

Beyond using the custom tags provided by the Struts JSP tags, it is easy to create tags that are specific to the application you are building, to assist in creating the user interface. The MailReader example application included with the distribution illustrates this principle by creating the following tags unique to the implementation of this application:

-   **checkLogon** - Checks for the existence of a particular session object, and forwards control to the logon page if it is missing. This is used to catch cases where a user has bookmarked a page in the middle of your application and tries to bypass logging on, or if the user's session has been timed out. (Note that there are better ways to authenticate users; the checkLogon tag is simply meant to demonstrate writing your own custom tags.)
-   **linkSubscription** - Generates a hyperlink to a details page for a Subscription, which passes the required primary key values as request attributes. This is used when listing the subscriptions associated with a user, and providing links to edit or delete them.
-   **linkUser** - Generates a hyperlink to a details page for a User, which passes the required primary key values as request attributes.

The source code for these tags is in the `src/example` directory, in package `org.apache.struts.example` , along with the other Java classes that are used in this application.

### <span id="Page_Composition_With_Includes"></span>Page Composition With Includes

Creating the entire presentation of a page in one JSP file (with custom tags and beans to access the required dynamic data) is a very common design approach, and was employed in the example application included with the distribution. However, many applications require the display of multiple logically distinct portions of your application together on a single page.

For example, a portal application might have some or all of the following functional capabilities available on the portal's "home" page:

-   Access to a search engine for this portal.
-   One or more "news feed" displays, with the topics of interest customizedfrom the user's registration profile.
-   Access to discussion topics related to this portal.
-   A "mail waiting" indicator if your portal provides free email accounts.

The development of the various segments of this site is easier if you can divide up the work, and assign different developers to the different segments. Then, you can use the *include* capability of JavaServer Pages technology to combine the results into a single result page, or use the include tag provided with the framework. There are three types of *include* available, depending on when you w ant the combination of output to occur:

-   An `<%@ include file="xxxxx" %>` directive can include a file that contains Java code or JSP tags. The code in the included file can even reference variables declared earlier in the outer jsp page. The code is inlined into the other JavaServer Page before it is compiled so it can definitely contain more than just HTML.
-   The include *action* ( `<jsp:include page="xxxxx" flush="true" />` ) is processed at request time, and is handled transparently by the server. Among other things, that means you can conditionally perform the include by nesting it within a tag like [equal](struts-logic.html.md#equal) by using it's parameter attribute.
-   The [bean:include](struts-bean.html.md#include) tag takes either a an argument "forward" representing a logical name mapped to the jsp to include, or the "id" argument, which represents a page context String variable to print out to the jsp page.

### <span id="Page_Composition_With_Tiles"></span>Page Composition With Tiles

Tiles is a powerful templating library that allows you to construct views by combining various "tiles". Here's a quick setup guide:

1.  Create a /layout/layout.jsp file that contains your app's common look and feel:
        .html.md>
        <body>
        <tiles:insert attribute="body"/>
        </body>
        <.html.md>

2.  Create your /index.jsp homepage file:
        <h1>This is my homepage</h1>

3.  Create a /WEB-INF/tiles-defs.xml file that looks like this:
        <tiles-definitions>
        <definition 
            name="layout" 
            path="/layout/layout.jsp">
            <put name="body" value=""/>
        </definition>
        <definition name="homepage" extends="layout">
            <put 
                name="body" 
                value="/index.jsp"/>
        </definition>
        <tiles-definitions>

4.  Setup the TilesPlugin in the struts-config.xml file:
        <plug-in 
            className="org.apache.struts.tiles.TilesPlugin">
            <set-property 
                property="definitions-config" 
                value="/WEB-INF/tiles-defs.xml"/>
        </plug-in>

5.  Setup an action mapping in struts-config.xml to point to your homepage tile:
        <action 
        path="/index"
        type="org.apache.struts.actions.ForwardAction"
        parameter="homepage"/>

The TilesPlugin configures a special RequestProcessor that determines if the requested view is a tile and processes it accordingly. Note that we made the homepage tile extend our root layout tile and changed the body attribute. Tiles inserts the file named in the body attribute into the main layout.

See the tiles-documentation webapp for in-depth examples.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


