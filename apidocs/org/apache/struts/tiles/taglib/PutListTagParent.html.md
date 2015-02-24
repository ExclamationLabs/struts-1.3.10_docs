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
<td align="left"><a href="class-use/PutListTagParent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/PutListTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutListTagParent.html"><strong>FRAMES</strong></a>    <a href="PutListTagParent.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.taglib
 Interface PutListTagParent
------------------------------

**All Known Implementing Classes:**  
[DefinitionTag](../../../../../org/apache/struts/tiles/taglib/DefinitionTag.html.md "class in org.apache.struts.tiles.taglib"), [ELDefinitionTag](../../../../../org/apache/strutsel/taglib/tiles/ELDefinitionTag.html "class in org.apache.strutsel.taglib.tiles"), [ELGetTag](../../../../../org/apache/strutsel/taglib/tiles/ELGetTag.html "class in org.apache.strutsel.taglib.tiles"), [ELInsertTag](../../../../../org/apache/strutsel/taglib/tiles/ELInsertTag.html "class in org.apache.strutsel.taglib.tiles"), [ELPutListTag](../../../../../org/apache/strutsel/taglib/tiles/ELPutListTag.html "class in org.apache.strutsel.taglib.tiles"), [GetTag](../../../../../org/apache/struts/tiles/taglib/GetTag.html "class in org.apache.struts.tiles.taglib"), [InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html "class in org.apache.struts.tiles.taglib"), [PutListTag](../../../../../org/apache/struts/tiles/taglib/PutListTag.html "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public interface PutListTagParent

Tag classes implementing this interface can contains nested PutTag. This interface defines a method called by nested tags.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

` processNestedTag(PutListTag nestedTag)`
           Add an attribute to container.

 

<span id="method_detail"></span>

**Method Detail**

### processNestedTag

    void processNestedTag(PutListTag nestedTag)
                          throws JspException

Add an attribute to container.

**Parameters:**  
`nestedTag` - Nested PutTag defining the attribute.

**Throws:**  
`JspException`

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
<td align="left"><a href="class-use/PutListTagParent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/PutListTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutListTagParent.html"><strong>FRAMES</strong></a>    <a href="PutListTagParent.html"><strong>NO FRAMES</strong></a>    
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
