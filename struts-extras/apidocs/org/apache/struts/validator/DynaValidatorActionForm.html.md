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
<td align="left"><a href="class-use/DynaValidatorActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/validator/ValidatorActionForm.html.md" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/DynaValidatorActionForm.html"><strong>FRAMES</strong></a>    <a href="DynaValidatorActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.DynaValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator
 Class DynaValidatorActionForm
------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.action.DynaActionForm
              org.apache.struts.validator.DynaValidatorForm
                  org.apache.struts.validator.DynaValidatorActionForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html?is-external=true "class or interface in org.apache.commons.beanutils")

------------------------------------------------------------------------

    public class DynaValidatorActionForm

extends [DynaValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/DynaValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")

implements [DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html.md?is-external=true "class or interface in org.apache.commons.beanutils"), [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html?is-external=true "class or interface in java.io")

This class extends **DynaValidatorForm** and provides basic field validation based on an XML file. The key passed into the validator is the action element's 'path' attribute from the struts-config.xml which should match the form element's name attribute in the validation.xml.

-   See `ValidatorPlugin` definition in struts-config.xml for validation rules.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.validator.DynaValidatorActionForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.validator.DynaValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[DynaValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/DynaValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `page, validatorResults`                                                                                                                                                                                                                  |

 <span id="fields_inherited_from_class_org.apache.struts.action.DynaActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[DynaActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/DynaActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `dynaClass, dynaValues`                                                                                                                                                                                                    |

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` DynaValidatorActionForm()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key.

 <span id="methods_inherited_from_class_org.apache.struts.validator.DynaValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[DynaValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/DynaValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getPage, getResultValueMap, getValidatorResults, reset, setPage, setPageFromDynaProperty, setValidatorResults, validate`                                                                                                                  |

 <span id="methods_inherited_from_class_org.apache.struts.action.DynaActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[DynaActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/DynaActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `contains, get, get, get, getDynaClass, getDynaProperty, getMap, getString, getStrings, initialize, initialize, isDynaAssignable, remove, reset, set, set, set, toString`                                                   |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMultipartRequestHandler, getServlet, getServletWrapper, setMultipartRequestHandler, setServlet, validate`                                                                                                       |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 <span id="methods_inherited_from_class_org.apache.commons.beanutils.DynaBean"></span>

| **Methods inherited from interface org.apache.commons.beanutils.[DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html.md?is-external=true "class or interface in org.apache.commons.beanutils")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `contains, get, get, get, getDynaClass, remove, set, set, set`                                                                                                                                                                             |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### DynaValidatorActionForm

    public DynaValidatorActionForm()

<span id="method_detail"></span>

**Method Detail**

### getValidationKey

    public String getValidationKey(ActionMapping mapping,
                                   HttpServletRequest request)

Returns the Validation key.

**Overrides:**  
`getValidationKey` in class `DynaValidatorForm`

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
<td align="left"><a href="class-use/DynaValidatorActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/validator/ValidatorActionForm.html.md" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/DynaValidatorActionForm.html"><strong>FRAMES</strong></a>    <a href="DynaValidatorActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.DynaValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
