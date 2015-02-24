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

<span id="Struts_Validator_Guide"></span>Struts Validator Guide
---------------------------------------------------------------

The Struts Validator, in some form, has been available since the days of Struts 0.5. It was orignally packaged as a developer contribution. Later, the core code was moved to the Jakarta Commons and a Struts specific extension became part of Struts since 1.1.

For the convenience of the many developers who have been using the Struts Validator all along, this document first overviews the core functionality and then covers the changes and new functionality added since Struts 1.1.

Once you have configured the Validator Plug-In, so that it can load your Validator Resources you just have to extend `org.apache.struts.validator.action.ValidatorForm` instead of `org.apache.struts.action.ActionForm` . Then when the `validate` method is called, the action's name attribute from the Struts Configuration is used to load the validations for the current form. The form element's `name` attribute in the Validator configuration should match the action element's `name` attribute.

An alternative approach is to use the action mapping path attribute. In this case, you extend the ValidatorActionForm instead of the ValidatorForm. The ValidatorActionForm uses the action element's `path` attribute from the Struts configuration which should match the form element's `name` attribute in the Validator configuration.

Then a separate action mapping can be defined for each page in a multi-page form, and the validation form can be associated with the action rather than a page number (as shown in the example of a multi-page form in the validator example).

### <span id="Internationalization"></span>Internationalization

Each validator form is grouped within a `FormSet` element in the Validator configuration file. The `FormSet` has language, country, and variant attributes that correspond with the `java.util.Locale` class. If these attributes are not specified, the `FormSet` will be set to the default locale. A `FormSet` can also have constants associated with it. On the same level as a `FormSet` there can be a global element which can also have constants and have validator actions that perform validations.

**Note** : You must declare a default `FormSet` without internationalization before your internationalized `FormSet` s. This allows the Validator to fall back to the default version if no locale is found.

The default error message for a pluggable validator can be overriden with the `msg` element. So instead of using the `msg` attribute for the mask validator to generate the error message the `msg` attribute from the field will be used if the name of the field's name attribute matches the validator's name attribute.

The arguments for error messages can be set with the arg element and position attribute. If the arg elements' name attribute isn't set, it will become the default arg value for the different error messages constructed. If the name attribute is set, you can specify the argument for a specific pluggable validator and then this will be used for constructing the error message.

    <field
        property="lastName"
        depends="required,mask">
        <msg
            name="mask"
            key="registrationForm.lastname.maskmsg"/>
        <arg position="0" key="registrationForm.lastname.displayname"/>
        <var>
            <var-name>mask</var-name>
            <var-value>^[a-zA-Z]*$</var-value>
        </var>
    </field>

By default the arg elements will try to look up the `key` attribute in the message resources. If the resource attribute is set to false, it will pass in the value directly without retrieving the value from the message resources.

Note that since Struts 1.1, you must explicitly define your message resource in any module that is going to use the Validator, due to a problem accessing the top-level resource. This only effects applications which are using modules.

    <field
        property="integer"
        depends="required,integer,intRange">
        <arg position="0" key="typeForm.integer.displayname"/>
        <arg position="1"
            name="intRange"
            key="${var:min}"
            resource="false"/>
        <arg position="2"
            name="intRange"
            key="${var:max}"
            resource="false"/>
        <var>
            <var-name>min</var-name>
            <var-value>10</var-value>
        </var>
        <var>
            <var-name>max</var-name>
            <var-value>20</var-value>
        </var>
        </field>

### <span id="Standard_Built_In_Validations"></span>Standard Built In Validations

Validator ships with a set of pre-defined validators, as follows:

-   **required** - mandatory field validation. Has no variables.
            <field property="name" depends="required">
                <arg position="0" key="customer.name"/>
            </field>
            

-   **requiredif** - field dependant validator

        Deprecated, use validwhen.

-   **validwhen** - validator for checking one field against another.

        see later section titled
                                    Designing "Complex Validations with
                                        validwhen"
                                    .
                                

-   **minlength** - validate input data isn't less than a specified minimum length. Requires a `minlength` variable.
            <field property="name" depends="required,minlength">
                <arg position="0" key="customer.name"/>
                <arg position="1" name="minlength" key="${var:minlength}" resource="false"/>
                <var><var-name>minlength</var-name><var-value>3</var-value></var>
            </field>
            

-   **maxlength** - validate input data doesn't exceed a specified maximum length. Requires a `maxlength` variable.
            <field property="name" depends="required,maxlength">
                <arg position="0" key="customer.name"/>
                <arg position="1" name="maxlength" key="${var:maxlength}" resource="false"/>
                <var><var-name>maxlength</var-name><var-value>30</var-value></var>
            </field>
            

-   **mask** - validate format according to a regular expression. Requires a `mask` variable to specify the regular expression. Since version 1.1, the regular expression must start with a `^` and end with a `$` (see example below).
            <field property="name" depends="required,mask">
                <msg name="mask" key="registrationForm.lastname.maskmsg"/>
                <arg position="0" key="registration.name"/>
                <var><var-name>mask</var-name><var-value>^[a-zA-Z]*$</var-value></var>
            </field>
            

-   **byte** - validates that a field can be converted to a Byte.
            <field property="age" depends="byte">
                <arg position="0" key="employee.age"/>
            </field>
            

-   **short** - validates that a field can be converted to a Short.
            <field property="productnumber" depends="short">
                <arg position="0" key="order.prodno"/>
            </field>
            

-   **integer** - validates that a field can be converted to an Integer.
            <field property="ordernumber" depends="integer">
                <arg position="0" key="order.number"/>
            </field>
            

-   **long** - validates that a field can be converted to a Long.
            <field property="ordernumber" depends="long">
                <arg position="0" key="order.number"/>
            </field>
            

-   **float** - validates that a field can be converted to a Float.
            <field property="amount" depends="float">
                <arg position="0" key="sale.amount"/>
            </field>
            

-   **double** - validates that a field can be converted to a Double.
            <field property="amount" depends="double">
                <arg position="0" key="sale.amount"/>
            </field>
            

-   **date** - validates that a field can be converted to a Date. This validator uses `java.text.SimpleDateFormat` to parse the date and optionally either a `datePattern` or `datePatternStrict` variable can be used. If no pattern is specified the default short date format is assumed. The difference between using the `datePatternStrict` and `datePattern` variables is that `datePatternStrict` checks additionally that the input data is the same length as the pattern specified (so for example 1/1/2004 would fail with a pattern of `MM/dd/yyyy` ).
            <field property="saledate" depends="required,date">
                <arg position="0" key="myForm.saledate"/>
                <var><var-name>datePattern</var-name><var-value>MM/dd/yyyy</var-value></var>
            </field>
            

            <field property="saledate" depends="required,date">
                <arg position="0" key="sale.orderdate"/>
                <var><var-name>datePatternStrict</var-name><var-value>MM/dd/yyyy</var-value></var>
            </field>
            

-   **range** - validate number range.

        Deprecated, use intRange, longRange, floatRange
                                    or doubleRange.

-   **intRange** - validates that an integer field is within a specified range. Requires `min` and `max` variables to specify the range. This validator depends on the `integer` validator which must also be in the field's `depends` attribute.
            <field property="age" depends="required,integer,intRange">
                <arg position="0" key="employee.age"/>
                <arg position="1" name="intRange" key="${var:min}" resource="false"/>
                <arg position="2" name="intRange" key="${var:max}" resource="false"/>
                <var><var-name>min</var-name><var-value>18</var-value></var>
                <var><var-name>max</var-name><var-value>65</var-value></var>
            </field>
            

-   **longRange** - validates that a long field is within a specified range. Requires `min` and `max` variables to specify the range. This validator depends on the `long` validator which must also be in the field's `depends` attribute.
            <field property="age" depends="required,long,longRange">
                <arg position="0" key="employee.age"/>
                <arg position="1" name="longRange" key="${var:min}" resource="false"/>
                <arg position="2" name="longRange" key="${var:max}" resource="false"/>
                <var><var-name>min</var-name><var-value>18</var-value></var>
                <var><var-name>max</var-name><var-value>65</var-value></var>
            </field>
            

-   **floatRange** - validates that a float field is within a specified range Requires `min` and `max` variables to specify the range. This validator depends on the `float` validator which must also be in the field's `depends` attribute.
            <field property="ordervalue" depends="required,float,floatRange">
                <arg position="0" key="order.value"/>
                <arg position="1" name="floatRange" key="${var:min}" resource="false"/>
                <arg position="2" name="floatRange" key="${var:max}" resource="false"/>
                <var><var-name>min</var-name><var-value>100</var-value></var>
                <var><var-name>max</var-name><var-value>4.99</var-value></var>
            </field>
            

-   **doubleRange** - validates that a double field is within a specified range Requires `min` and `max` variables to specify the range. This validator depends on the `double` validator which must also be in the field's `depends` attribute.
            <field property="ordervalue" depends="required,double,doubleRange">
                <arg position="0" key="employee.age"/>
                <arg position="1" name="doubleRange" key="${var:min}" resource="false"/>
                <arg position="2" name="doubleRange" key="${var:max}" resource="false"/>
                <var><var-name>min</var-name><var-value>100</var-value></var>
                <var><var-name>max</var-name><var-value>4.99</var-value></var>
            </field>
            

-   **creditCard** - validate credit card number format
            <field property="name" depends="required, creditCard">
                <arg position="0" key="customer.cardnumber"/>
            </field>
            

-   **email** - validate email address format
            <field property="customeremail" depends="email">
                <arg position="0" key="customer.email"/>
            </field>
            

-   **url** - validates url format. Has four *optional* variables ( `allowallschemes` , `allow2slashes` , `nofragments` and `schemes` ) which can be used to configure this validator.
    -   **allowallschemes** specifies whether all schemes are allowed. Valid values are `true` or `false` (default is `false` ). If this is set to `true` then the `schemes` variable is ignored.
    -   **allow2slashes** specifies whether double '/' characters are allowed. Valid values are `true` or `false` (default is `false` ).
    -   **nofragments** specifies whether fragements are allowed. Valid values are `true` or `false` (default is `false` - i.e. fragments are allowed).
    -   **schemes** - use to specify a comma separated list of valid schemes. If not specified then the defaults are used which are `http` , `https` and `ftp` .

            <field property="custUrl" depends="url">
                <arg position="0" key="customer.url"/>
            </field>

            <field property="custUrl" depends="url">
                <arg position="0" key="customer.url"/>
                <var>
                   <var-name>nofragments</var-name>
                   <var-value>true</var-value>
                </var>
                <var>
                   <var-name>schemes</var-name>
                   <var-value>http,https,telnet,file</var-value>
                </var>
            </field>
            

### <span id="ConstantsVariables"></span>Constants/Variables

Global constants can be inside the global tags and FormSet/Locale constants can be created in the formset tags. Constants are currently only replaced in the Field's property attribute, the Field's var element value attribute, the Field's msg element key attribute, and Field's arg element's key attribute. A Field's variables can also be substituted in the arg elements (ex: ${var:min}). The order of replacement is FormSet/Locale constants are replaced first, Global constants second, and for the arg elements variables are replaced last.

    <global>
        <constant>
            <constant-name>zip</constant-name>
            <constant-value>^\d{5}(-\d{4})?$</constant-value>
        </constant>
    </global>

    <field
       property="zip"
       depends="required,mask">
    <arg position="0" key="registrationForm.zippostal.displayname"/>
    <var>
     <var-name>mask</var-name>
     <var-value>${zip}</var-value>
    </var>
    </field>

The var element under a field can be used to store variables for use by a pluggable validator. These variables are available through the Field's `getVar(String key)` method.

    <field
        property="integer"
        depends="required,integer,intRange">
        <arg position="0" key="typeForm.integer.displayname"/>
        <arg position="1"
            name="intRange"
            key="${var:min}"
            resource="false"/>
        <arg position="2"
            name="intRange"
            key="${var:max}"
            resource="false"/>
        <var>
            <var-name>min</var-name>
            <var-value>10</var-value>
        </var>
        <var>
            <var-name>max</var-name>
            <var-value>20</var-value>
        </var>
        </field>

### <span id="Designing_Complex_Validations_with_validwhen"></span>Designing Complex Validations with validwhen

[Since Struts 1.2.0] A frequent requirement in validation design is to validate one field against another (for example, if you have asked the user to type in a password twice for confirmation, to make sure that the values match.) In addition, there are fields in a form that may only be required if other fields have certain values. The `validwhen` validator is designed to handle these cases.

The `validwhen` validator takes a single `var` field, called `test` . The value of this var is a boolean expression which must be true in order for the validation to success. The values which are allowed in the expression are:

-   The token `*this*` , which contains the value of the field currently being tested
-   Other fields in the form referenced by field name, such as `customerAge`
-   The token `null` which will match against either null or an empty string
-   Single or double-quoted string literals.
-   Integer literals in decimal, hex or octal format

References to indexed fields are also allowed in the expression:

-   Indexed fields in the form referenced by an explicit integer, such as `childLastName[2]`
-   Indexed fields in the form referenced by an implicit integer, such as `childLastName[]` , which will use the same index into the array as the index of the field being tested.
-   Properties of indexed fields in the form referenced by an explicit or implicit integer, such as `child[].lastName` , which will use the same index into the array as the index of the field being tested.

As an example of how this would work, consider a form with fields `sendNewsletter` and `emailAddress` . The `emailAddress` field is only required if the `sendNewsletter` field is not null. You could code this using validwhen as:

    <field property="emailAddress" depends="validwhen">
      <arg position="0" key="userinfo.emailAddress.label"/>
      <var>
        <var-name>test</var-name>
        <var-value>((sendNewsletter == null) or (*this* != null))</var-value>
      </var>
    </field>

Which reads as: this field is valid if `sendNewsletter` is `null` or the field value is not `null` .

Here's a slightly more complicated example using indexed fields. Assume a form with a number of lines to allow the user to enter part numbers and quantities they wish to order. An array of beans of class `orderLine` is used to hold the entries in a property called orderLines. If you wished to verify that every line with part number also had a quantity entered, you could do it with:

    <field property="quantity" indexedListProperty="orderLines" depends="validwhen">
      <arg position="0" key="orderform.quantity.label"/>
      <var>
        <var-name>test</var-name>
        <var-value>((orderLines[].partNumber == null) or (*this* != null))</var-value>
      </var>
    </field>

Which reads as: This field is valid if the corresponding `partNumber` field is `null` , or this field is not `null` .

As a final example, imagine a form where the user must enter their height in inches, and if they are under 60 inches in height, it is an error to have checked off nbaPointGuard as a career.

    <field property="nbaPointGuard" depends="validwhen">
      <arg position="0" key="careers.nbaPointGuard.label"/>
      <var>
        <var-name>test</var-name>
        <var-value>((heightInInches >= 60) or (*this* == null))</var-value>
      </var>
    </field>

A few quick notes on the grammer.

-   All comparisons must be enclosed in parens.
-   Only two items may be joined with `and` or `or`
-   If both items to be compared are convertable to ints, a numeric comparison is done, otherwise a string comparison is done.

### <span id="Pluggable_Validators"></span>Pluggable Validators

By convention, the validators your application uses can be loaded through a file named "validator-rules.xml", and the validator forms (or "validations") can be configured separately (say, in a "validations.xml" file). This approach separates the validators, that you might reuse in another application, from the validations that are specific to each application.

The Validator comes bundled with several ready-to-use validators. The bundled validators include: required, mask ,byte, short, int, long, float, double, date (without locale support), and a numeric range.

The 'mask' validator depends on 'required' in the default setup. That means that 'required' has to complete successfully before 'mask' will run. The 'required' and 'mask' validators are partially built into the framework. Any field that isn't 'required' will skip other validations if the field is null or has a length of zero. Regardless, the implementations of 'required' and 'mask' are still plugged in through the configuration file, like all the others.

If the [Javascript Tag](../struts-taglib/tagreference.html.md#javascript) is used, the client side Javascript generation looks for a value in the validator's javascript attribute and generates an object that the supplied method can use to validate the form. For a more detailed explanation of how the Javascript Validator Tag works, see the [html taglib API reference](../struts-taglib/tagreference.html#struts-html.tld) .

The 'mask' validator lets you validate a regular expression mask to the field. It uses the Regular Expression Package from the Apache Jakarta site.

The main class used is `org.apache.regexp.RE` .

Example Validator Configuration from the default validator-rules.xml.

    <validator name="required"
          classname="org.apache.struts.validator.FieldChecks"
             method="validateRequired"
       methodParams="java.lang.Object,
                     org.apache.commons.validator.ValidatorAction,
                     org.apache.commons.validator.Field,
                     org.apache.struts.action.ActionMessages,
                     org.apache.commons.validator.Validator,
                     javax.servlet.http.HttpServletRequest"
                msg="errors.required"/>

    <validator name="mask"
          classname="org.apache.struts.validator.FieldChecks"
             method="validateMask"
       methodParams="java.lang.Object,
                     org.apache.commons.validator.ValidatorAction,
                     org.apache.commons.validator.Field,
                     org.apache.struts.action.ActionMessages,
                     org.apache.commons.validator.Validator,
                     javax.servlet.http.HttpServletRequest"
            depends=""
                msg="errors.invalid"/>

**Creating Pluggable Validators**

The `methodParams` attribute takes a comma separated list of class names. The `method` attribute needs to have a signature complying with the above list. The list can be comprised of any combination of the following:

-   `java.lang.Object` - Bean validation is being performed on.
-   `org.apache.commons.validator.ValidatorAction` - The current ValidatorAction being performed.
-   `org.apache.commons.validator.Field` - Field object being validated.
-   `org.apache.struts.action.ActionMessages` - The errors object to add an ActionMessage to if the validation fails.
-   `javax.servlet.http.HttpServletRequest` - Current request object.
-   `javax.servlet.ServletContext` - The application's ServletContext.
-   `org.apache.commons.validator.Validator` - The current org.apache.commons.validator.Validator instance.
-   `java.util.Locale` - The Locale of the current user.

**Multi Page Forms**

The field element has an optional page attribute. It can be set to an integer. All validation for any field on a page less than or equal to the current page is performed server side. All validation for any field on a page equal to the current page is generated for the client side Javascript. A mutli-part form expects the page attribute to be set.

    .html.md:hidden property="page" value="1"/>

**Comparing Two Fields**

This is an example of how you could compare two fields to see if they have the same value. A good example of this is when you are validating a user changing their password and there is the main password field and a confirmation field.

    <validator name="twofields"
           classname="com.mysite.StrutsValidator"
           method="validateTwoFields"
           msg="errors.twofields"/>

    <field property="password"
           depends="required,twofields">
              <arg position="0" key="typeForm.password.displayname"/>
              <var>
                 <var-name>secondProperty</var-name>
                 <var-value>password2</var-value>
              </var>
    </field>

    public static boolean validateTwoFields(
        Object bean,
        ValidatorAction va, 
        Field field,
        ActionErrors errors,
        HttpServletRequest request, 
        ServletContext application) {

        String value = ValidatorUtils.getValueAsString(
            bean, 
            field.getProperty());
        String sProperty2 = field.getVarValue("secondProperty");
        String value2 = ValidatorUtils.getValueAsString(
            bean, 
            sProperty2);

        if (!GenericValidator.isBlankOrNull(value)) {
           try {
              if (!value.equals(value2)) {
                 errors.add(field.getKey(),
                    Resources.getActionError(
                        application,
                        request,
                        va,
                        field));

                 return false;
              }
           } catch (Exception e) {
                 errors.add(field.getKey(),
                    Resources.getActionError(
                        application,
                        request,
                        va,
                        field));
                 return false;
           }
        }

        return true;
    }

### <span id="Known_Issues"></span>Known Issues

Since the Struts Validator relies on the Commons Validator, problem reports and enhancement requests may be listed against either product.

-   [Commons Validator Issue Tracker (JIRA)](http://issues.apache.org/jira/browse/VALIDATOR)

### <span id="Conditionally_required_fields"></span>Conditionally required fields

You can define logic like "only validate this field if field X is non-null and field Y equals 'male'". The recommended way to do this will be with the `validwhen` validator, described above, and available since Struts 1.2.0. The `requiredif` validator, which was added since Struts 1.1, will be deprecated in favor of `validwhen` , and `requiredif` will be removed in a future release. However, if you are using `requiredif` , here is a brief tutorial.

Let's assume you have a medical information form with three fields, sex, pregnancyTest, and testResult. If sex is 'f' or 'F', pregnancyTest is required. If pregnancyTest is not blank, testResult is required. The entry in your Validator configuration would look like this:

                        
    <form name="medicalStatusForm">

    <field
        property="pregnancyTest" depends="requiredif">
      <arg position="0" key="medicalStatusForm.pregnancyTest.label"/>
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
      <arg position="0" key="medicalStatusForm.testResult.label"/>
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

Here's a more complex example using indexed properties.

If you have this in your Struts configuration

    <form-bean
        name="dependentlistForm"
        type="org.apache.struts.webapp.validator.forms.ValidatorForm">
        <form-property
            name="dependents"
            type="org.apache.struts.webapp.validator.Dependent[]" size="10"/>
        <form-property
            name="insureDependents"
            type="java.lang.Boolean"
            initial="false"/>
    </form-bean>

Where dependent is a bean that has properties lastName, firstName, dob, coverageType

You can define a validation:


    <form name="dependentlistForm">

    <field
        property="firstName" indexedListProperty="dependents"
        depends="requiredif">
      <arg position="0" key="dependentlistForm.firstName.label"/>
      <var>
        <var-name>field[0]</var-name>
        <var-value>lastName</var-value>
      </var>
      <var>
        <var-name>fieldIndexed[0]</var-name>
        <var-value>true</var-value>
      </var>
      <var>
        <var-name>fieldTest[0]</var-name>
        <var-value>NOTNULL</var-value>
      </var>
    </field>

    <field
        property="dob"
        indexedListProperty="dependents"
        depends="requiredif,date">
      <arg position="0" key="dependentlistForm.dob.label"/>
      <var>
        <var-name>field[0]</var-name>
        <var-value>lastName</var-value>
      </var>
      <var>
        <var-name>fieldIndexed[0]</var-name>
        <var-value>true</var-value>
      </var>
      <var>
        <var-name>fieldTest[0]</var-name>
        <var-value>NOTNULL</var-value>
      </var>
    </field>

    <field
        property="coverageType"
        indexedListProperty="dependents"
        depends="requiredif">
      <arg position="0" key="dependentlistForm.coverageType.label"/>
      <var>
        <var-name>field[0]</var-name>
        <var-value>lastName</var-value>
      </var>
      <var>
        <var-name>fieldIndexed[0]</var-name>
        <var-value>true</var-value>
      </var>
      <var>
        <var-name>fieldTest[0]</var-name>
        <var-value>NOTNULL</var-value>
      </var>
      <var>
        <var-name>field[1]</var-name>
        <var-value>insureDependents</var-value>
      </var>
      <var>
        <var-name>fieldTest[1]</var-name>
        <var-value>EQUAL</var-value>
      </var>
      <var>
        <var-name>fieldValue[1]</var-name>
        <var-value>true</var-value>
      </var>
      <var>
        <var-name>fieldJoin</var-name>
        <var-value>AND</var-value>
      </var>
    </field>

    </form>

Which is read as follows: The firstName field is only required if the lastName field is non-null. Since fieldIndexed is true, it means that lastName must be a property of the same indexed field as firstName. Same thing for dob, except that we validate for date if not blank.

The coverageType is only required if the lastName for the same indexed bean is not null, and also if the non-indexed field insureDependents is true.

You can have an arbitrary number of fields by using the [n] syntax, the only restriction is that they must all be AND or OR, you can't mix.

### <span id="Unstoppable_JavaScript_Validations"></span>Unstoppable JavaScript Validations

[Since Struts 1.2.0] You can force the clientside Javascript validation to check all constraints, instead of stopping at the first error. By setting a new property, `stopOnFirstError` , on the Validator PlugIn to false.

Here's a sample configuration block that you could use in your Struts configuration file:

                            
      <plug-in className="org.apache.struts.validator.ValidatorPlugIn">
      <set-property property="pathnames"
       value="/WEB-INF/validator-rules.xml,/WEB-INF/validations.xml"/>
      <set-property property="stopOnFirstError" value="false"/>
      </plug-in>
      

                    

### <span id="Validator_API_Guide"></span>Validator API Guide

A concise [Struts Validator API Guide](../apidocs/org/apache/struts/validator/package-summary.html.md#package_description) is available to help you get started.

### <span id="Validator_Resources"></span>Validator Resources

-   [**Check Your Form with Validator**](http://otn.oracle.com/oramag/oracle/04-jan/o14dev_struts.html.md) by James Holmes. Howto article in Oracle Magazine.
-   [**Struts Validator: Validating Two Fields Match**](http://www.raibledesigns.com/page/rd/20030226#struts_validator_validating_two_fields) by Matt Raible. Howto article.
-   [**DynaForms and the Validator**](http://www.strutskickstart.com/) by James Turner and Kevin Bedell. Sample chapter from [Struts Kickstart;](http://www.strutskickstart.com/) available as a free download (PDF).
-   [**Validating user input**](http://www.manning-source.com/books/husted/husted_ch12.pdf) by David Winterfeldt and Ted Husted. Sample chapter from [Struts in Action;](http://www.amazon.com/exec/obidos/ISBN=1930110502/apachesoftwar-20/) available as a free download (PDF).

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


