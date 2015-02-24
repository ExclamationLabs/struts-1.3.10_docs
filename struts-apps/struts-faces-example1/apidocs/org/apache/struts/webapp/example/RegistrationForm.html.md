------------------------------------------------------------------------

<span id="navbar_top"></span> [](#skip-navbar_top "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_top_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/RegistrationForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/RegistrationBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/SaveRegistrationAction.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/RegistrationForm.html"><strong>FRAMES</strong></a>    <a href="RegistrationForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.ValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example
 Class RegistrationForm
--------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.webapp.example.RegistrationForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class RegistrationForm

extends [ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")

Form bean for the user registration page. This form has the following fields, with default values in square brackets:

-   **action** - The maintenance action we are performing (Create, Delete, or Edit).
-   **fromAddress** - The EMAIL address of the sender, to be included on sent messages. [REQUIRED]
-   **fullName** - The full name of the sender, to be included on sent messages. [REQUIRED]
-   **password** - The password used by this user to log on.
-   **password2** - The confirmation password, which must match the password when changing or setting.
-   **replyToAddress** - The "Reply-To" address to be included on sent messages. [Same as from address]
-   **username** - The registered username, which must be unique. [REQUIRED]

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.example.RegistrationForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `page, validatorResults`                                                                                                                                                                                                          |

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` RegistrationForm()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getAction()`
           Return the maintenance action.

` String`

` getFromAddress()`
           Return the from address.

` String`

` getFullName()`
           Return the full name.

` String`

` getPassword()`
           Return the password.

` String`

` getPassword2()`
           Return the confirmation password.

` String`

` getReplyToAddress()`
           Return the reply to address.

` String`

` getUsername()`
           Return the username.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setAction(String action)`
           Set the maintenance action.

` void`

` setFromAddress(String fromAddress)`
           Set the from address.

` void`

` setFullName(String fullName)`
           Set the full name.

` void`

` setPassword(String password)`
           Set the password.

` void`

` setPassword2(String password2)`
           Set the confirmation password.

` void`

` setReplyToAddress(String replyToAddress)`
           Set the reply to address.

` void`

` setUsername(String username)`
           Set the username.

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionMessages` object that encapsulates any validation errors that have been found.

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getPage, getResultValueMap, getValidationKey, getValidatorResults, setPage, setValidatorResults`                                                                                                                                  |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMultipartRequestHandler, getServlet, getServletWrapper, reset, setMultipartRequestHandler, setServlet, validate`                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### RegistrationForm

    public RegistrationForm()

<span id="method_detail"></span>

**Method Detail**

### getAction

    public String getAction()

Return the maintenance action.

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

Set the maintenance action.

**Parameters:**  
`action` - The new maintenance action.

------------------------------------------------------------------------

### getFromAddress

    public String getFromAddress()

Return the from address.

------------------------------------------------------------------------

### setFromAddress

    public void setFromAddress(String fromAddress)

Set the from address.

**Parameters:**  
`fromAddress` - The new from address

------------------------------------------------------------------------

### getFullName

    public String getFullName()

Return the full name.

------------------------------------------------------------------------

### setFullName

    public void setFullName(String fullName)

Set the full name.

**Parameters:**  
`fullName` - The new full name

------------------------------------------------------------------------

### getPassword

    public String getPassword()

Return the password.

------------------------------------------------------------------------

### setPassword

    public void setPassword(String password)

Set the password.

**Parameters:**  
`password` - The new password

------------------------------------------------------------------------

### getPassword2

    public String getPassword2()

Return the confirmation password.

------------------------------------------------------------------------

### setPassword2

    public void setPassword2(String password2)

Set the confirmation password.

**Parameters:**  
`password2` - The new confirmation password

------------------------------------------------------------------------

### getReplyToAddress

    public String getReplyToAddress()

Return the reply to address.

------------------------------------------------------------------------

### setReplyToAddress

    public void setReplyToAddress(String replyToAddress)

Set the reply to address.

**Parameters:**  
`replyToAddress` - The new reply to address

------------------------------------------------------------------------

### getUsername

    public String getUsername()

Return the username.

------------------------------------------------------------------------

### setUsername

    public void setUsername(String username)

Set the username.

**Parameters:**  
`username` - The new username

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset all properties to their default values.

**Overrides:**  
`reset` in class `ValidatorForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 HttpServletRequest request)

Validate the properties that have been set from this HTTP request, and return an `ActionMessages` object that encapsulates any validation errors that have been found. If no errors are found, return `null` or an `ActionMessages` object with no recorded error messages.

**Overrides:**  
`validate` in class `ValidatorForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

<span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_bottom_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/RegistrationForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/RegistrationBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/SaveRegistrationAction.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/RegistrationForm.html"><strong>FRAMES</strong></a>    <a href="RegistrationForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.ValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
