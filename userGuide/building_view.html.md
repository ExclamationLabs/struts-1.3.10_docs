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

<span id="a3._Building_View_Components"></span>3. Building View Components
--------------------------------------------------------------------------

> *"What if I should fall right through the center of the earth... oh, and come out the other side, where people walk upside down."*

<span id="overview"></span>
### <span id="a3.1_Overview"></span>3.1 Overview

The framework provides infrastructural support for view components, but does not provide any actual view components of its own. Several [presentation technologies](#presentation_frameworks) are available, including, among others, Cocoon, JSP, Velocity Templates, and XSLT.

Features provided by the framework for direct use by view components include [Message Resources](#i18n) for localizing text and images, and [FormBeans](#form_beans) to provide for automatic population and validation.

<span id="i18n"></span>
### <span id="a3.2_Internationalized_Messages"></span>3.2 Internationalized Messages

A few years ago, application developers could count on having to support only residents of their own country, who are used to only one (or sometimes two) languages, and one way to represent numeric quantities like dates, numbers, and monetary values. However, the explosion of application development based on web technologies, as well as the deployment of such applications on the Internet and other broadly accessible networks, have rendered national boundaries invisible in many cases. This has translated (if you will pardon the pun) into a need for applications to support *internationalization* (often called "i18n" because 18 is the number of letters in between the "i" and the "n") and *localization.*

The framework builds upon the standard classes available on the Java platform to build internationalized and localized applications. The key concepts to become familiar with are:

-   [**Locale**](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md) - The fundamental Java class that supports internationalization is `Locale` . Each `Locale` represents a particular choice of country and language (plus an optional language variant), and also a set of formatting assumptions for things like numbers and dates.
-   [**ResourceBundle**](http://java.sun.com/j2se/1.4.2/docs/api/java/util/ResourceBundle.html.md) - The `java.util.ResourceBundle` class provides the fundamental tools for supporting messages in multiple languages. See the Javadocs for the `ResourceBundle` class, and the information on Internationalization in the documentation bundle for your JDK release, for more information.
-   [**PropertyResourceBundle**](http://java.sun.com/j2se/1.4.2/docs/api/java/util/PropertyResourceBundle.html.md) - One of the standard implementations of `ResourceBundle` allows you to define resources using the same "name=value" syntax used to initialize properties files. This is very convenient for preparing resource bundles with messages that are used in a web application, because these messages are generally text oriented.
-   [**MessageFormat**](http://java.sun.com/j2se/1.4.2/docs/api/java/text/MessageFormat.html.md) - The `java.text.MessageFormat` class allows you to replace portions of a message string (in this case, one retrieved from a resource bundle) with arguments specified at run time. This is useful in cases where you are creating a sentence, but the words would appear in a different order in different languages. The placeholder string `{0}` in the message is replaced by the first runtime argument, `{1}` is replaced by the second argument, and so on.
-   [**MessageResources**](../apidocs/org/apache/struts/util/MessageResources.html.md) - The framework class `org.apache.struts.util.MessageResources` lets you treat a set of resource bundles like a database, and allows you to request a particular message string for a particular Locale (normally one associated with the current user) instead of for the default Locale the server itself is running in.

Please note that the i18n support in a server-side framework is limited to the **presentation** of internationalized text and images to the user. Support for Locale specific **input methods** (used with languages such as Japanese, Chinese, and Korean) is left up to the client device, which is usually a web browser.

For an internationalized application, follow the steps described in the Internationalization document in the JDK documentation bundle for your platform to create a properties file containing the messages for each language. An example will illustrate this further:

Assume that your source code is created in package `com.mycompany.mypackage` , so it is stored in a directory (relative to your source directory) named `com/mycompany/mypackage.` To create a resource bundle called `com.mycompany.mypackage.MyApplication,` you would create the following files in the `com/mycompany/mypackage` directory:

-   **MyApplication.properties** - Contains the messages in the default language for your server. If your default language is English, you might have an entry like this: `prompt.hello=Hello`
-   **MyApplication\_xx.properties** - Contains the same messages in the language whose ISO language code is "xx" (See the [ResourceBundle Javadoc](http://java.sun.com/j2se/1.4.2/docs/api/java/util/ResourceBundle.html.md) page for a link to the current list). For a French version of the message shown above, you would have this entry: `prompt.hello=Bonjour` You can have resource bundle files for as many languages as you need.

When you configure the controller servlet via the struts-config.xml configuration file, one of the things you will need to define is the base name of the resource bundle for the application. In the case described above, it would be `com.mycompany.mypackage.MyApplication.`

    <message-resources parameter="com.mycompany.mypackage.MyApplication"/>

The important thing is for the resource bundle to be found on the class path for your application. Another approach is to store the `MyResources.properties` file in your application's `classes` folder. You can then simply specify "myResources" as the application value. Just be careful it is not deleted if your build script deletes classes as part of a "clean" target.

If it does, here is an Ant task to run when compiling your application that copies the contents of a `src/conf` directory to the `classes` directory:

    <!-- Copy any configuration files -->
    <copy todir="classes">
    <fileset dir="src/conf"/>
    </copy>

<span id="form_beans"></span>
### <span id="a3.3_Forms_and_FormBean_Interactions"></span>3.3 Forms and FormBean Interactions

**Note:** While the examples given here use JSP and custom tags, the ActionForm beans and the other controller components are View neutral. The framework can also be used with Cocoon, Velocity Templates, XSLT, and any other presentation technology that can be rendered via a Java servlet.

<span id="form_population"></span>
### <span id="a3.3.1_Automatic_Form_Population"></span>3.3.1 Automatic Form Population

At one time or another, most web developers have built forms using the standard capabilities of HTML, such as the `<input>` tag. Users have come to expect interactive applications to have certain behaviors, and one of these expectations relates to error handling -- if the user makes an error, the application should allow them to fix just what needs to be changed -- without having to re-enter any of the rest of the information on the current page or form.

Fulfilling this expectation is tedious and cumbersome when coding with standard HTML and JSP pages. For example, an input element for a `username` field might look like this (in JSP):

    <input type="text" name="username"
    value="<%= loginBean.getUsername() >"/>

which is difficult to type correctly, confuses HTML developers who are not knowledgeable about programming concepts, and can cause problems with HTML editors. Instead, Struts Taglibs provides a comprehensive facility for building forms, based on the Custom Tag Library facility of JSP 1.1. The case above would be rendered like this using Struts Taglibs:

    .html.md:text property="username"/>;

with no need to explicitly refer to the JavaBean from which the initial value is retrieved. That is handled automatically by the JSP tag, using facilities provided by the framework.

HTML forms are sometimes used to upload other files. Most browsers support this through a \<input type="file"\> element, that generates a file browse button, but it's up to the developer to handle the incoming files. The framework handles these "multipart" forms in a way identical to building normal forms.

For an example of using the framework to create a simple login form, see the [Buiding an ActionForm Howto.](../faqs/actionForm.html.md)

<span id="form_validation"></span>
### <span id="a3.3.2_Automatic_Form_Validation"></span>3.3.2 Automatic Form Validation

In addition to the form and bean interactions described above, The framework offers an additional facility to validate the input fields it has received. To utilize this feature, override the following method in your ActionForm class:

    validate(ActionMapping mapping,
    HttpServletRequest request);

The `validate` method is called by the controller servlet after the bean properties have been populated, but before the corresponding action class's `execute` method is invoked. The `validate` method has the following options:

-   Perform the appropriate validations and find no problems -- Return either `null` or a zero-length ActionErrors instance, and the controller servlet will proceed to call the `execute` method of the appropriate `Action` class.
-   Perform the appropriate validations and find problems -- Return an ActionErrors instance containing `ActionMessage's,` which are classes that contain the error message keys (into the application's `MessageResources` bundle) that should be displayed. The controller servlet will store this array as a request attribute suitable for use by the `.html.md:errors>` tag, and will forward control back to the input form (identified by the `input` property for this `ActionMapping` ).

As mentioned earlier, this feature is entirely optional. The default implementation of the `validate` method returns `null,` and the controller servlet will assume that any required validation is done by the action class.

One common approach is to perform simple, prima facia validations using the ActionForm `validate` method, and then handle the "business logic" validation from the Action.

The Struts Validator, covered in the next section, may be used to easily validate ActionForms.

<span id="validator"></span>
### <span id="a3.3.3_The_Struts_Validator"></span>3.3.3 The Struts Validator

Configuring the Validator to perform form validation is easy.

1.  The ActionForm bean must extend ValidatorForm.
2.  The form's JSP must include the [\.html.md:javascript\>](struts-html.html) tag for client side validation.
3.  You must define the validation rules in an xml file like this:
        <form-validation>
        <formset>
        <form name="logonForm">
          <field property="username" depends="required">
            <msg name="required" key="error.username"/>
          </field>
        </form>
        </formset>
        </form-validation>

    The msg element points to the message resource key to use when generating the error message.
4.  Lastly, you must enable the ValidatorPlugin in the struts-config.xml file like this:
        <plug-in className="org.apache.struts.validator.ValidatorPlugIn">
        <set-property
        property="pathnames"
        value="/org/apache/struts/validator/validator-rules.xml,
            /WEB-INF/validation.xml"/>
        </plug-in>

**Note:** If your required form property is one of the Java object representations of primitive types (ie. java.lang.Integer), you must set the ActionServlet's convertNull init. parameter to true. Failing to do this will result in the required validation not being performed on that field because it will default to 0.

For more about the Struts Validator, see the [Developers Guide.](../faqs/validator.html.md)

<span id="Tiles"></span>
### <span id="a3.3.4_Page_Composition_With_Tiles"></span>3.3.4 Page Composition With Tiles

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

See the [Struts Tiles website](http://struts.apache.org/struts-tiles/) for in-depth examples.

<span id="presentation_frameworks"></span>
### <span id="a3.4_Presentation_Frameworks"></span>3.4 Presentation Frameworks

The framework is supported by many presentation technologies, and there are a great number of extensions that make creating view components even easier. Some popular presentation technologies include:

-   [Struts Taglib](http://struts.apache.org/struts-taglib/)
-   [Struts Cocoon](http://struts.sourceforge.net/struts-cocoon/)
-   [Velocity Struts](http://jakarta.apache.org/velocity/tools/struts/)
-   [Stxx for XLST](http://stxx.sourceforge.net/)

<span id="other_presentations"></span>
### <span id="a3.5_Other_Presentation_Techniques"></span>3.5 Other Presentation Techniques

Although the look and feel of your application can be completely constructed based on the standard capabilities of presentation libraries, you may need to employ other techniques to render some responses directly.

<span id="image_rendering"></span>
### <span id="a3.5.1_Image_Rendering_Components"></span>3.5.1 Image Rendering Components

Some applications require dynamically generated images, like the price charts on a stock reporting site. Two different approaches are commonly used to meet these requirements:

-   Render a hyperlink with a URL that executes a servlet request. The servlet will use a graphics library to render the graphical image, set the content type appropriately (such as to `image/gif` ), and send back the bytes of that image to the browser, which will display them just as if it had received a static file.
-   Render the HTML code necessary to download a Java applet that creates the required graph. You can configure the graph by setting appropriate initialization parameters for the applet in the rendered code, or you can have the applet make its own connection to the server to receive these parameters.

<span id="text_rendering"></span>
### <span id="a3.5.2_Rendering_Text"></span>3.5.2 Rendering Text

Some applications require dynamically generated text or markup, such as XML. If a complete page is being rendered, and can be output using a PrintWriter, this is very easy to do from an Action:

    response.setContentType("text/plain"); // or text/xml
    PrintWriter writer = response.getWriter();
    // use writer to render text
    return(null);

Next: [Building Controller Components](building_controller.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


