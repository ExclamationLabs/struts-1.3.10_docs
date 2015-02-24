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
<td align="left"><a href="class-use/ActionErrors.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/Action.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionForm.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionErrors.html"><strong>FRAMES</strong></a>    <a href="ActionErrors.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_classes_inherited_from_class_org.apache.struts.action.ActionMessages">NESTED</a> | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionMessages">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.action.ActionMessages">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class ActionErrors
------------------------

    java.lang.Object
      org.apache.struts.action.ActionMessages
          org.apache.struts.action.ActionErrors

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ActionErrors

extends [ActionMessages](../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`. Validation errors are either global to the entire `ActionForm` bean they are associated with, or they are specific to a particular bean property (and, therefore, a particular input field on the corresponding form).

Each individual error is described by an `ActionMessage` object, which contains a message key (to be looked up in an appropriate message resources database), and up to four placeholder arguments used for parametric substitution in the resulting message.

**IMPLEMENTATION NOTE** - It is assumed that these objects are created and manipulated only within the context of a single thread. Therefore, no synchronization is required for access to internal collections.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-06 18:03:30 -0400 (Sat, 06 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionErrors)

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_org.apache.struts.action.ActionMessages"></span>

| **Nested classes/interfaces inherited from class org.apache.struts.action.[ActionMessages](../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ActionMessages.ActionMessageItem`                                                                                                                                                         |

  <span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionMessages"></span>

| **Fields inherited from class org.apache.struts.action.[ActionMessages](../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` accessed,  GLOBAL_MESSAGE, iCount,  messages`                                                                                                                         |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                         |
|---------------------------------------------------------------------------------|
| ` ActionErrors()`                                                               
            Create an empty `ActionErrors` object.                                |
| ` ActionErrors(ActionErrors messages)`                                          
            Create an `ActionErrors` object initialized with the given messages.  |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionMessages"></span>

| **Methods inherited from class org.apache.struts.action.[ActionMessages](../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` add,  add, clear, get,  get,  isAccessed,  isEmpty,  properties, size,  size,  toString`                                                                               |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionErrors

    public ActionErrors()

Create an empty `ActionErrors` object.

------------------------------------------------------------------------

### ActionErrors

    public ActionErrors(ActionErrors messages)

Create an `ActionErrors` object initialized with the given messages.

**Parameters:**  
`messages` - The messages to be initially added to this object. This parameter can be `null`.

**Since:**  
Struts 1.1

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
<td align="left"><a href="class-use/ActionErrors.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/Action.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionForm.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionErrors.html"><strong>FRAMES</strong></a>    <a href="ActionErrors.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_classes_inherited_from_class_org.apache.struts.action.ActionMessages">NESTED</a> | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionMessages">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.action.ActionMessages">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
