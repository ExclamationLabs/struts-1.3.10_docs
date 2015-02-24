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
<td align="left"><a href="../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/CustomValidator.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../examples/validator/ProcessValidatorAction.html.md" title="class in examples.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../index.html.md?examples/validator/CustomValidator.html"><strong>FRAMES</strong></a>    <a href="CustomValidator.html"><strong>NO FRAMES</strong></a>    
<a href="../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

examples.validator
 Class CustomValidator
----------------------

    java.lang.Object
      examples.validator.CustomValidator

------------------------------------------------------------------------

    public class CustomValidator

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

A custom validator example

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                     |
|---------------------------------------------|
| `CustomValidator()`                         
            Constructor for CustomValidator.  |

  <span id="method_summary"></span>

**Method Summary**

`static boolean`

` validateTwoFields(Object bean, ValidatorAction va, Field field, ActionMessages errors, HttpServletRequest request)`
           Example validator for comparing the equality of two fields http://struts.apache.org/userGuide/dev\_validator.html.md http://www.raibledesigns.com/page/rd/20030226

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### CustomValidator

    public CustomValidator()

Constructor for CustomValidator.

<span id="method_detail"></span>

**Method Detail**

### validateTwoFields

    public static boolean validateTwoFields(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            HttpServletRequest request)

Example validator for comparing the equality of two fields http://struts.apache.org/userGuide/dev\_validator.html.md http://www.raibledesigns.com/page/rd/20030226

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
<td align="left"><a href="../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/CustomValidator.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../examples/validator/ProcessValidatorAction.html.md" title="class in examples.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../index.html.md?examples/validator/CustomValidator.html"><strong>FRAMES</strong></a>    <a href="CustomValidator.html"><strong>NO FRAMES</strong></a>    
<a href="../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
