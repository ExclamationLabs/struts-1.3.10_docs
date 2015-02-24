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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/validator/RegistrationAction.html.md" title="class in org.apache.struts.webapp.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/validator/ShowFileAction.html" title="class in org.apache.struts.webapp.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/validator/RegistrationForm.html"><strong>FRAMES</strong></a>    <a href="RegistrationForm.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.webapp.validator
 Class RegistrationForm
----------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.webapp.validator.RegistrationForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class RegistrationForm

extends [ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Form bean for the user registration page.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.validator.RegistrationForm)

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
            

` String`

` getAddr()`
            

` CityStateZip`

` getCityStateZip()`
            

` String`

` getEmail()`
            

` String`

` getFirstName()`
            

` String`

` getLastName()`
            

` String`

` getPhone()`
            

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setAction(String action)`
            

` void`

` setAddr(String sAddr)`
            

` void`

` setCityStateZip(CityStateZip csz)`
            

` void`

` setEmail(String sEmail)`
            

` void`

` setFirstName(String sFirstName)`
            

` void`

` setLastName(String sLastName)`
            

` void`

` setPhone(String sPhone)`
            

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getPage, getResultValueMap, getValidationKey, getValidatorResults, setPage, setValidatorResults, validate`                                                                                                                        |

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

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

------------------------------------------------------------------------

### getFirstName

    public String getFirstName()

------------------------------------------------------------------------

### setFirstName

    public void setFirstName(String sFirstName)

------------------------------------------------------------------------

### getLastName

    public String getLastName()

------------------------------------------------------------------------

### setLastName

    public void setLastName(String sLastName)

------------------------------------------------------------------------

### getAddr

    public String getAddr()

------------------------------------------------------------------------

### setAddr

    public void setAddr(String sAddr)

------------------------------------------------------------------------

### getCityStateZip

    public CityStateZip getCityStateZip()

------------------------------------------------------------------------

### setCityStateZip

    public void setCityStateZip(CityStateZip csz)

------------------------------------------------------------------------

### getPhone

    public String getPhone()

------------------------------------------------------------------------

### setPhone

    public void setPhone(String sPhone)

------------------------------------------------------------------------

### getEmail

    public String getEmail()

------------------------------------------------------------------------

### setEmail

    public void setEmail(String sEmail)

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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/validator/RegistrationAction.html.md" title="class in org.apache.struts.webapp.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/validator/ShowFileAction.html" title="class in org.apache.struts.webapp.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/validator/RegistrationForm.html"><strong>FRAMES</strong></a>    <a href="RegistrationForm.html"><strong>NO FRAMES</strong></a>    
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
