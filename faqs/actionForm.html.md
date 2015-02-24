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

<span id="How_to_Build_an_Action_Form"></span>How to Build an Action Form
-------------------------------------------------------------------------

This is a simple example of a login form to illustrate how Struts Action Framework makes dealing with forms much less painful than using straight HTML and standard JSP facilities. Consider the following page (based on the Struts MailReader example) named `logon.jsp:`

------------------------------------------------------------------------

    <%@ page language="java" %>
    <%@ taglib  uri="/WEB-INF/struts.html.md.tld" prefix="html" %>
    <%@ taglib uri="/WEB-INF/struts-bean.tld" prefix="bean" %>

    .html.md:html>
    <head>
    <title>
        <bean:message key="logon.title"/>
    </title>
    </head>

    <body bgcolor="white">

    .html.md:errors/>

    .html.md:form action="/logon" focus="username">
    <table border="0" width="100%">
        <tr>
            <th class="right">
                <bean:message key="prompt.username"/>
            </th>
            <td class="left">
                .html.md:text  property="username" size="16"/>
            </td>
        </tr>
        <tr>
            <th class="right">
                <bean:message key="prompt.password"/>
            </th>
            <td class="left">
                .html.md:password property="password" size="16"/>
            </td>
        </tr>
        <tr>
            <td class="right">
                .html.md:submit>
                    <bean:message key="button.submit"/>
                <.html.md:submit>
            </td>
            <td class="right">
                .html.md:reset>
                    <bean:message key="button.reset"/>
                <.html.md:reset>
            </td>
        </tr>
    </table>

    <.html.md:form>
    </body>
    <.html.md:html>

------------------------------------------------------------------------

The following items illustrate the key features of form handling, based on this example:

-   The `taglib` directive tells the JSP page compiler where to find the *tag library descriptor* for the Struts JSP tags. In this case, we are using `bean` as the prefix that identifies tags from the struts-bean library, and .html.md" as the prefix that identifies tags from the struts-html library. Any desired prefix can be used.
-   This page uses several occurrences of the **message** tag to look up internationalized message strings from a `MessageResources` object containing all the resources for this application. For this page to work, the following message keys must be defined in these resources:
    -   **logon.title** - Title of the logon page
    -   **prompt.username** - A "Username:" prompt string
    -   **prompt.password** - A "Password:" prompt string
    -   **button.submit** - "Submit" for the button label
    -   **button.reset** - "Reset" for the button label

    When the user logs on, the application can store a `Locale` object in the user's session. This `Locale` will be used to select messages in the appropriate language. This makes it easy to implement giving the user an option to switch languages -- simply change the stored `Locale` object, and all messages are switched automatically.
-   The **errors** tag displays any error messages that have been stored by a business logic component, or nothing if no errors have been stored. This tag will be described further below.
-   The **form** tag renders an HTML `<form>` element, based on the specified attributes. It also associates all of the fields within this form with a `ActionForm` bean `[org.apache.struts.action.ActionForm].` The tag looks up the `/logon` action mapping in the Struts configuration. The `logon` mapping tells the tag that the form bean is stored in the session context under the key `logonForm.` The developer provides the Java implementation of the ActionForm bean, subclassing the Struts class `ActionForm` (see [Building Controller](../userGuide/building_controller.html.md#4_3_ActionForm_Classes) components). This bean is used to provide initial values for all of the input fields that have names matching the property names of the bean. If an appropriate bean is not found, a new one will be created automatically, using the Java class name specified through the action mapping.
-   The form bean can also be specified in the tag by providing `name` and `type` attributes. But most often, everything is specified in the [Struts Configuration File.](../userGuide/building_controller.html.md#4_8_Writing_Action_Mappings)
-   The **text** tag renders an HTML `<input>` element of type "text". In this case, the number of character positions to occupy on the browser's screen has been specified as well. When this page is executed, the current value of the `username` property of the corresponding bean (that is, the value returned by `getUsername` ).
-   The **password** tag is used similarly. The difference is that the browser will echo asterisk characters, instead of the input value, as the user types their password.
-   The **submit** and **reset** tags generate the corresponding buttons at the bottom of the form. The text labels for each button are created using message tags, as with the prompts, so that these values are internationalized.

### <span id="Transferring_Data"></span>Transferring Data

To transfer data between ActionForms and business objects, many developers use the Commons BeanUtil methods. To transfer data from an ActionForm to a business object, you can use a statement like:

                PropertyUtils.copyProperties(actionForm, businessObject);

To transfer data from a business object to an ActionForm, you can reverse the parameters

                PropertyUtils.copyProperties(businessObject, actionForm);

For more about using this technique, see the [Commons BeanUtils documentation,](http://commons.apache.org/beanutils/) and the Struts MailReader example application.

Aside from BeanUtils, there are other tools available that make it easier to use business objects and ActionForms together. For more about POJO ActionForms, see the [FormDef](https://formdef.dev.java.net/) extension and the [Struts Live](https://strutslive.dev.java.net/) toolkit.

### <span id="Multipart_Forms"></span>Multipart Forms

Handling multipart forms is also easy. Obviously when you create a multipart form you're creating a form that has at least one input of type "file". The first step to creating a multipart form is to utilize the struts.html.md taglib to create the presentation page:

    <%@page language="java">
    <%@taglib
        uri="/WEB-INF/struts.html.md.tld"
       prefix=.html.md">

    .html.md:form action="uploadAction.do" enctype="multipart/form-data">

        Please Input Text: .html.md:text property="myText">
        Please Input The File You Wish to Upload: .html.md:file property="myFile">

       .html.md:submit />

    <.html.md:form>

------------------------------------------------------------------------

The next step is to create your ActionForm bean:

------------------------------------------------------------------------

    import javax.servlet.http.HttpServletRequest;
    import javax.servlet.http.HttpServletResponse;
    import org.apache.struts.action.ActionForm;
    import org.apache.struts.action.ActionMapping;
    import org.apache.struts.upload.FormFile;

    public class UploadForm extends ActionForm {

        protected String myText;
        protected FormFile myFile;

        public void setMyText(String text) {
            myText = text;
        }

        public String getMyText() {
            return myText;
        }

        public void setMyFile(FormFile file) {
            myFile = file;
        }

        public FormFile getMyFile() {
            return myFile;
        }

    }

------------------------------------------------------------------------

Look at the Javadocs for `FormFile` to see the methods it exposes to manipulate files in file uploading. Also look at the Javadocs for [ActionServlet](../apidocs/org/apache/struts/action/ActionServlet.html.md) and [ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html) for the various parameters you can specify to change how files are uploaded. Basically in your `execute` method in your action class you would call `((UploadForm) form).getMyFile()` to retrieve the FormFile and do what you want with it.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


