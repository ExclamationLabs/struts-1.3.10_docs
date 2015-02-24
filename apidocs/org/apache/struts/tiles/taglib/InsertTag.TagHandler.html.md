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
<td align="left"><a href="class-use/InsertTag.TagHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutListTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.TagHandler.html"><strong>FRAMES</strong></a>    <a href="InsertTag.TagHandler.html"><strong>NO FRAMES</strong></a>    
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
 Interface InsertTag.TagHandler
-------------------------------

**All Known Implementing Classes:**  
[InsertTag.DirectStringHandler](../../../../../org/apache/struts/tiles/taglib/InsertTag.DirectStringHandler.html.md "class in org.apache.struts.tiles.taglib"), [InsertTag.InsertHandler](../../../../../org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html "class in org.apache.struts.tiles.taglib")

<!-- -->

**Enclosing class:**  
[InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    protected static interface InsertTag.TagHandler

Inner Interface. Sub handler for tag.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Do include for type depicted by implementation class.

` int`

` doStartTag()`
           Create ComponentContext for type depicted by implementation class.

` void`

` putAttribute(String name, Object value)`
           Add a component parameter (attribute) to subContext.

 

<span id="method_detail"></span>

**Method Detail**

### doStartTag

    int doStartTag()
                   throws JspException

Create ComponentContext for type depicted by implementation class.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doEndTag

    int doEndTag()
                 throws JspException

Do include for type depicted by implementation class.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### putAttribute

    void putAttribute(String name,
                      Object value)

Add a component parameter (attribute) to subContext.

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
<td align="left"><a href="class-use/InsertTag.TagHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutListTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.TagHandler.html"><strong>FRAMES</strong></a>    <a href="InsertTag.TagHandler.html"><strong>NO FRAMES</strong></a>    
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
