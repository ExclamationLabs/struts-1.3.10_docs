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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedDefineTei.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested/bean/NestedDefineTag.html.md" title="class in org.apache.struts.taglib.nested.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/bean/NestedMessageTag.html" title="class in org.apache.struts.taglib.nested.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/bean/NestedDefineTei.html"><strong>FRAMES</strong></a>    <a href="NestedDefineTei.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested.bean
 Class NestedDefineTei
------------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagExtraInfo
          org.apache.struts.taglib.logic.IterateTei
              org.apache.struts.taglib.nested.bean.NestedDefineTei

------------------------------------------------------------------------

    public class NestedDefineTei

extends [IterateTei](../../../../../../org/apache/struts/taglib/logic/IterateTei.html.md "class in org.apache.struts.taglib.logic")

NestedDefineTei to make sure that the implied setting of the name property of a nested tag is properly handed in the casting of the defined object. Currently goes to String, but for the purposes of most nested objects they will benefit more from a simple Object casting.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` NestedDefineTei()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

` VariableInfo[]`

` getVariableInfo(TagData data)`
           Return information about the scripting variables to be created.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagExtraInfo"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagExtraInfo](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagExtraInfo.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getTagInfo, isValid, setTagInfo`                                                                                                                                                                                            |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### NestedDefineTei

    public NestedDefineTei()

<span id="method_detail"></span>

**Method Detail**

### getVariableInfo

    public VariableInfo[] getVariableInfo(TagData data)

Return information about the scripting variables to be created.

**Overrides:**  
` getVariableInfo` in class `IterateTei`

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedDefineTei.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested/bean/NestedDefineTag.html.md" title="class in org.apache.struts.taglib.nested.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/bean/NestedMessageTag.html" title="class in org.apache.struts.taglib.nested.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/bean/NestedDefineTei.html"><strong>FRAMES</strong></a>    <a href="NestedDefineTei.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
