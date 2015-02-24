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
<td align="left"><a href="class-use/NestedReference.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedPropertyTag.html.md" title="class in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedRootTag.html" title="class in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedReference.html"><strong>FRAMES</strong></a>    <a href="NestedReference.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested
 Class NestedReference
-------------------------------

    java.lang.Object
      org.apache.struts.taglib.nested.NestedReference

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class NestedReference

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

So that a nested hierarchy can penetrate a dynamic JSP include, this class will hold the details of a bean name and nested property.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.nested.NestedReference)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                       |
|-------------------------------------------------------------------------------|
| ` NestedReference()`                                                          
            Empty constructor.                                                  |
| ` NestedReference(String name, String property)`                              
            Constructor takes the all the relevant details to init the object.  |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getBeanName()`
           Getter for the bean name

` String`

` getNestedProperty()`
           Getter for the nested property

` void`

` setBeanName(String newName)`
           Setter for the bean name

` void`

` setNestedProperty(String newProperty)`
           Setter for the nested property

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### NestedReference

    public NestedReference()

Empty constructor.

------------------------------------------------------------------------

### NestedReference

    public NestedReference(String name,
                           String property)

Constructor takes the all the relevant details to init the object.

**Parameters:**  
`name` - String name of the bean that the include is to reference

`property` - String nested property value that the include will be continuing on with.

<span id="method_detail"></span>

**Method Detail**

### getBeanName

    public String getBeanName()

Getter for the bean name

**Returns:**  
String value that will be the bean's reference

------------------------------------------------------------------------

### setBeanName

    public void setBeanName(String newName)

Setter for the bean name

**Parameters:**  
`newName` - String value to set the bean reference.

------------------------------------------------------------------------

### getNestedProperty

    public String getNestedProperty()

Getter for the nested property

**Returns:**  
String value that is the nested property for the current nesting

------------------------------------------------------------------------

### setNestedProperty

    public void setNestedProperty(String newProperty)

Setter for the nested property

**Parameters:**  
`newProperty` - String value of the new current nesting level

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
<td align="left"><a href="class-use/NestedReference.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedPropertyTag.html.md" title="class in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedRootTag.html" title="class in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedReference.html"><strong>FRAMES</strong></a>    <a href="NestedReference.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
