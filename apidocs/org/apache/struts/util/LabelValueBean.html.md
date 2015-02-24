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
<td align="left"><a href="class-use/LabelValueBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/IteratorAdapter.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/MessageResources.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/LabelValueBean.html"><strong>FRAMES</strong></a>    <a href="LabelValueBean.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.util
 Class LabelValueBean
----------------------

    java.lang.Object
      org.apache.struts.util.LabelValueBean

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [Comparable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Comparable.html?is-external=true "class or interface in java.lang")

------------------------------------------------------------------------

    public class LabelValueBean

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Comparable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Comparable.html.md?is-external=true "class or interface in java.lang"), [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html?is-external=true "class or interface in java.io")

A simple JavaBean to represent label-value pairs. This is most commonly used when constructing user interface elements which have a label to be displayed to the user, and a corresponding value to be returned to the server. One example is the `.html.md:options>` tag.

Note: this class has a natural ordering that is inconsistent with equals.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.LabelValueBean)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static Comparator`

` CASE_INSENSITIVE_ORDER`
           Comparator that can be used for a case insensitive sort of `LabelValueBean` objects.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                             |
|---------------------------------------------------------------------|
| ` LabelValueBean()`                                                 
            Default constructor.                                      |
| ` LabelValueBean(String label, String value)`                       
            Construct an instance with the supplied property values.  |

  <span id="method_summary"></span>

**Method Summary**

` int`

` compareTo(Object o)`
           Compare LabelValueBeans based on the label, because that's the human viewable part of the object.

` boolean`

` equals(Object obj)`
           LabelValueBeans are equal if their values are both null or equal.

` String`

` getLabel()`
            

` String`

` getValue()`
            

` int`

` hashCode()`
           The hash code is based on the object's value.

` void`

` setLabel(String label)`
            

` void`

` setValue(String value)`
            

` String`

` toString()`
           Return a string representation of this object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, finalize, getClass, notify, notifyAll, wait, wait, wait`                                                                                                      |

 

<span id="field_detail"></span>

**Field Detail**

<span id="CASE_INSENSITIVE_ORDER"></span>

### CASE\_INSENSITIVE\_ORDER

    public static final Comparator CASE_INSENSITIVE_ORDER

Comparator that can be used for a case insensitive sort of `LabelValueBean` objects.

<span id="constructor_detail"></span>

**Constructor Detail**

### LabelValueBean

    public LabelValueBean()

Default constructor.

------------------------------------------------------------------------

### LabelValueBean

    public LabelValueBean(String label,
                          String value)

Construct an instance with the supplied property values.

**Parameters:**  
`label` - The label to be displayed to the user.

`value` - The value to be returned to the server.

<span id="method_detail"></span>

**Method Detail**

### getLabel

    public String getLabel()

------------------------------------------------------------------------

### setLabel

    public void setLabel(String label)

------------------------------------------------------------------------

### getValue

    public String getValue()

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

------------------------------------------------------------------------

### compareTo

    public int compareTo(Object o)

Compare LabelValueBeans based on the label, because that's the human viewable part of the object.

**Specified by:**  
`compareTo` in interface `Comparable`

<!-- -->

**See Also:**  
[`Comparable`](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Comparable.html.md?is-external=true "class or interface in java.lang")

------------------------------------------------------------------------

### toString

    public String toString()

Return a string representation of this object.

**Overrides:**  
`toString` in class `Object`

------------------------------------------------------------------------

### equals

    public boolean equals(Object obj)

LabelValueBeans are equal if their values are both null or equal.

**Overrides:**  
`equals` in class `Object`

<!-- -->

**See Also:**  
[`Object.equals(Object)`](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true#equals(java.lang.Object) "class or interface in java.lang")

------------------------------------------------------------------------

### hashCode

    public int hashCode()

The hash code is based on the object's value.

**Overrides:**  
`hashCode` in class `Object`

<!-- -->

**See Also:**  
[`Object.hashCode()`](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true#hashCode() "class or interface in java.lang")

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
<td align="left"><a href="class-use/LabelValueBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/IteratorAdapter.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/MessageResources.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/LabelValueBean.html"><strong>FRAMES</strong></a>    <a href="LabelValueBean.html"><strong>NO FRAMES</strong></a>    
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
