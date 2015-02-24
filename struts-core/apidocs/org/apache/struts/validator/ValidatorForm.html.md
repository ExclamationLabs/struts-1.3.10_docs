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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ValidatorForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/validator/Resources.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorPlugIn.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorForm.html"><strong>FRAMES</strong></a>    <a href="ValidatorForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator
 Class ValidatorForm
---------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[BeanValidatorForm](../../../../org/apache/struts/validator/BeanValidatorForm.html.md "class in org.apache.struts.validator")

------------------------------------------------------------------------

    public class ValidatorForm

extends [ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

This class extends **ActionForm** and provides basic field validation based on an XML file. The key passed into the validator is the action element's 'name' attribute from the struts-config.xml which should match the form element's name attribute in the validation.xml.

-   See `ValidatorPlugin` definition in struts-config.xml for validation rules.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[`ActionForm`](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action"), [Serialized Form](../../../../serialized-form.html#org.apache.struts.validator.ValidatorForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  int`

`page`
           Used to indicate the current page of a multi-page form.

`protected  ValidatorResults`

` validatorResults`
           The results returned from the validation performed by the `Validator`.

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` multipartRequestHandler, servlet`                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ValidatorForm()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` getPage()`
           Gets page.

` Map`

` getResultValueMap()`
           Returns a `Map` of values returned from any validation that returns a value other than `null` or `Boolean` with the key the full property path of the field.

` String`

` getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key.

` ValidatorResults`

` getValidatorResults()`
           Get results of the validation performed by the `Validator`.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setPage(int page)`
           Sets page.

` void`

` setValidatorResults(ValidatorResults validatorResults)`
           Set results of the validation performed by the `Validator`.

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getMultipartRequestHandler,  getServlet,  getServletWrapper,  reset,  setMultipartRequestHandler,  setServlet,  validate`                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="validatorResults"></span>

### validatorResults

    protected ValidatorResults validatorResults

The results returned from the validation performed by the `Validator`.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected int page

Used to indicate the current page of a multi-page form.

<span id="constructor_detail"></span>

**Constructor Detail**

### ValidatorForm

    public ValidatorForm()

<span id="method_detail"></span>

**Method Detail**

### getPage

    public int getPage()

Gets page.

**Returns:**  
page number

------------------------------------------------------------------------

### setPage

    public void setPage(int page)

Sets page.

**Parameters:**  
`page` - page number

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 HttpServletRequest request)

Validate the properties that have been set from this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found. If no errors are found, return `null` or an `ActionErrors` object with no recorded error messages.

**Overrides:**  
` validate` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
`ActionErrors` object that encapsulates any validation errors

**See Also:**  
[`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

### getValidationKey

    public String getValidationKey(ActionMapping mapping,
                                   HttpServletRequest request)

Returns the Validation key.

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
validation key - the form element's name in this case

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset all properties to their default values.

**Overrides:**  
` reset` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### getValidatorResults

    public ValidatorResults getValidatorResults()

Get results of the validation performed by the `Validator`.

**Returns:**  
results of the validation

------------------------------------------------------------------------

### setValidatorResults

    public void setValidatorResults(ValidatorResults validatorResults)

Set results of the validation performed by the `Validator`.

**Parameters:**  
`validatorResults` - results of validation

------------------------------------------------------------------------

### getResultValueMap

    public Map getResultValueMap()

Returns a `Map` of values returned from any validation that returns a value other than `null` or `Boolean` with the key the full property path of the field.

**Returns:**  
`Map` of non-null values

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ValidatorForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/validator/Resources.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorPlugIn.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorForm.html"><strong>FRAMES</strong></a>    <a href="ValidatorForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
