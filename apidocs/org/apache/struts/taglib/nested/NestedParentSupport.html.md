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
<td align="left"><a href="class-use/NestedParentSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md" title="interface in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedPropertyHelper.html" title="class in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedParentSupport.html"><strong>FRAMES</strong></a>    <a href="NestedParentSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested
 Interface NestedParentSupport
-------------------------------

**All Superinterfaces:**  
[NestedNameSupport](../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested"), [NestedPropertySupport](../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html "interface in org.apache.struts.taglib.nested"), [NestedTagSupport](../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html "interface in org.apache.struts.taglib.nested")

------------------------------------------------------------------------

    public interface NestedParentSupport

extends [NestedNameSupport](../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")

This interface is so managing classes of the nested tag can identify a tag as a parent tag that other tags retrieve nested properties from.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[`NestedPropertyTag`](../../../../../org/apache/struts/taglib/nested/NestedPropertyTag.html.md "class in org.apache.struts.taglib.nested"), [`NestedIterateTag`](../../../../../org/apache/struts/taglib/nested/logic/NestedIterateTag.html "class in org.apache.struts.taglib.nested.logic")

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` String`

` getNestedProperty()`
           This is required by all parent tags so that the child tags can get a hold of their nested property.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.nested.NestedNameSupport"></span>

| **Methods inherited from interface org.apache.struts.taglib.nested.[NestedNameSupport](../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getName,  setName`                                                                                                                                                                                           |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.nested.NestedPropertySupport"></span>

| **Methods inherited from interface org.apache.struts.taglib.nested.[NestedPropertySupport](../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html.md "interface in org.apache.struts.taglib.nested")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getProperty,  setProperty`                                                                                                                                                                                           |

 

<span id="method_detail"></span>

**Method Detail**

### getNestedProperty

    String getNestedProperty()

This is required by all parent tags so that the child tags can get a hold of their nested property.

**Returns:**  
String of the qaulified nested property to this implementing tag

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
<td align="left"><a href="class-use/NestedParentSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md" title="interface in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedPropertyHelper.html" title="class in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedParentSupport.html"><strong>FRAMES</strong></a>    <a href="NestedParentSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
