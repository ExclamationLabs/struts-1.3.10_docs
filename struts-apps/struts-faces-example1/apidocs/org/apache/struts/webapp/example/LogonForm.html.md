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
<td align="left"><a href="class-use/LogonForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/LogonAction.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/MainMenuBacking.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/LogonForm.html"><strong>FRAMES</strong></a>    <a href="LogonForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example
 Class LogonForm
--------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.webapp.example.LogonForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class LogonForm

extends [ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")

Form bean for the user profile page. This form has the following fields, with default values in square brackets:

-   **password** - Entered password value
-   **username** - Entered username value

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.example.LogonForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` LogonForm()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getPassword()`
           Return the password.

` String`

` getUsername()`
           Return the username.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setPassword(String password)`
           Set the password.

` void`

` setUsername(String username)`
           Set the username.

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionMessages` object that encapsulates any validation errors that have been found.

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

### LogonForm

    public LogonForm()

<span id="method_detail"></span>

**Method Detail**

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
`reset` in class `ActionForm`

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
`validate` in class `ActionForm`

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
<td align="left"><a href="class-use/LogonForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/LogonAction.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/MainMenuBacking.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/LogonForm.html"><strong>FRAMES</strong></a>    <a href="LogonForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
