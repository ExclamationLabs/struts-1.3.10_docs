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
<td align="left"><a href="class-use/ValidatorActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/Resources.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorActionForm.html"><strong>FRAMES</strong></a>    <a href="ValidatorActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.ValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator
 Class ValidatorActionForm
---------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.validator.ValidatorActionForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ValidatorActionForm

extends [ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

This class extends **ValidatorForm** and provides basic field validation based on an XML file. The key passed into the validator is the action element's 'path' attribute from the struts-config.xml which should match the form element's name attribute in the validation.xml.

-   See `ValidatorPlugin` definition in struts-config.xml for validation rules.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.validator.ValidatorActionForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `page,  validatorResults`                                                                                                                                                      |

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` multipartRequestHandler, servlet`                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` ValidatorActionForm()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key.

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getPage,  getResultValueMap,  getValidatorResults,  reset,  setPage,  setValidatorResults,  validate`                                                                         |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getMultipartRequestHandler,  getServlet,  getServletWrapper,  reset,  setMultipartRequestHandler,  setServlet,  validate`                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ValidatorActionForm

    public ValidatorActionForm()

<span id="method_detail"></span>

**Method Detail**

### getValidationKey

    public String getValidationKey(ActionMapping mapping,
                                   HttpServletRequest request)

Returns the Validation key.

**Overrides:**  
` getValidationKey` in class `ValidatorForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
validation key - the action element's 'path' attribute in this case

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
<td align="left"><a href="class-use/ValidatorActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/Resources.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorActionForm.html"><strong>FRAMES</strong></a>    <a href="ValidatorActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
