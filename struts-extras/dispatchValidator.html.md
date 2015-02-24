<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Extras

-   [Welcome](index.html.md)

##### FAQs and HOWTOs

-   **Dispatching And Validating**

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Creating_a_Multipage_Wizard_with_DispatchAction_and_Validator"></span>Creating a Multipage Wizard with DispatchAction and Validator
---------------------------------------------------------------------------------------------------------------------------------------------

This is simple example to illustrate how to build a multi-page wizard that utilizes both the `DispatchAction` and Commons Validator. Using the `DispatchAction` helps to minimize the number of action classes while the Validator supports the declarative (non-programmatic) specification of form field validations.

### <span id="Using_the_DispatchAction"></span>Using the DispatchAction

The example used is a simple two page wizard. The first page prompts for a name, while the second for an address. The application URL has the form

    http://localhost:8080/howto/name.do?submitName=enterName

where the `submitName` parameter is used to specify the name of the method in the action class that will be called to process the request. In the action mapping the value of the `parameter` attribute specifies the name of the dispatch request parameter (i.e. `parameter="submitName"` ).

    <action path="/name"
            type="com.acme.AcmeAction"
            name="acmeForm"
            scope="session"
            input="/pages/name.jsp"
            parameter="submitName">
        <forward name="name"
                 path="/pages/name.jsp"/>
        <forward name="address"
                path="/pages/address.jsp"/>
    </action>

The method `enterName` simply forwards to the first page.

    public ActionForward enterName(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response)
           throws Exception {

        return mapping.findForward("name");

    }

On the page `name.jsp` is a hidden field for the `submitName` parameter. Submitting the name page calls method `enterAddress` by using Javascript to set the `submitName` parameter

    .html.md:submit onclick="this.form.submitName.value='enterAddress'"/>

The `enterAddress` method then forwards to the address page.

    public ActionForward enterAddress(ActionMapping mapping,
                                      ActionForm form,
                                      HttpServletRequest request,
                                      HttpServletResponse response)
          throws Exception {

        return mapping.findForward("address");
    }

On the `adddress.jsp` page, we again dynamically set the `submitName` parameter.

    .html.md:submit value="submit" onclick="this.form.submitName.value='submitAddress'"/>

And the action path that is submitted is

        .html.md:form action="/address">

The action mapping for `/address` is

    <action path="/address"
            type="com.acme.AcmeAction"
            name="acmeForm"
            scope="session"
            input="/pages/address.jsp"
            parameter="submitName">

            <forward name="previous"
                     path="/pages/name.jsp"/>

            <forward name="done"
                     path="/pages/done.jsp"/>

    </action>

Note that two action mappings are required to handle the page flow (we'll discuss why in the next section).

### <span id="Validations"></span>Validations

Let's now add some validations to require input fields using the Validator. In validation.xml, there's a `formset` definition that specifies two field validations for the form bean named `acmeForm.`

    <formset>
       <form name="acmeForm">
          <field property="firstName" page="1" depends="required">
              <arg0 key="prompt.name"/>
          </field>
           <field property="streetAddress" page="2" depends="required">
              <arg0 key="prompt.address"/>
          </field>
        </form>
      </formset>

We need to identify the page where the input field resides so that we can control which validations are triggered for a given form submission. Without using the page property, any request that involves the `acmeForm` would trigger all of the validations associated with `acmeForm` (even validations for fields that the user has not seen yet).

On each of the pages, a hidden field is used to identify the page number.

In `name.jsp`

    .html.md:hidden property="page" value="1"/>

In `address.jsp`

    .html.md:hidden property="page" value="2"/>

The Validator will use the value of the page property in determining which validations to run.

Now let's revisit the reason for having two action mappings. An action mapping is required for each page since the `input` attribute specifies the page to forward to in case validation fails. Therefore we need to define an action mapping for each page that could be displayed after a validation fails.

### <span id="Cancel_and_Previous"></span>Cancel and Previous

The tricky part is how to setup Previous and Cancel buttons for each of the pages. If the user clicks Previous then the validations for the currrent page should not be triggered. For Cancel, none of the validations should be triggered.

The solution for Previous is to set the page number property to the number of the previous page, effectively circumventing the validations associated with the current page.

       .html.md:submit value="previous"
              onclick="this.form.submitName.value='previous'; this.form.page.value='1'"/>

For cancel, there are two options. We could use the Struts Taglib Cancel button or create an action specifically designed to process a cancel request. The `cancel` action has no associated validations.

    <action path="/cancel"
            type="com.acme.CancelAction">

        <forward name="cancel"
                 path="/pages/cancel.jsp"/>

    </action>

And the Cancel button submits to the `/cancel` action path.

    .html.md:submit value="cancel" onclick="this.form.action='/acme/cancel.do'"/>

The full example is [available for download.](#dispatchValidator.zip)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


