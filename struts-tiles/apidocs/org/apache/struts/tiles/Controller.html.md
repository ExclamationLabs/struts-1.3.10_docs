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
<td align="left"><a href="class-use/Controller.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ControllerSupport.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/Controller.html"><strong>FRAMES</strong></a>    <a href="Controller.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Interface Controller
-----------------------

**All Known Implementing Classes:**  
[ActionController](../../../../org/apache/struts/tiles/ActionController.html.md "class in org.apache.struts.tiles"), [ControllerSupport](../../../../org/apache/struts/tiles/ControllerSupport.html "class in org.apache.struts.tiles"), [UrlController](../../../../org/apache/struts/tiles/UrlController.html "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public interface Controller

A controller is a piece of code called before rendering a jsp page. A controller can be associated to a tile. See \<insert\> or \<definition\> for association syntax.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

` execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Method associated to a tile and called immediately before the tile is included.

` void`

` perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           **Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

 

<span id="method_detail"></span>

**Method Detail**

### perform

    void perform(ComponentContext tileContext,
                 HttpServletRequest request,
                 HttpServletResponse response,
                 ServletContext servletContext)
                 throws ServletException,
                        IOException

**Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

Method associated to a tile and called immediately before the tile is included.

**Parameters:**  
`tileContext` - Current tile context.

`request` - Current request

`response` - Current response

`servletContext` - Current servlet context

**Throws:**  
`ServletException`

`IOException`

------------------------------------------------------------------------

### execute

    void execute(ComponentContext tileContext,
                 HttpServletRequest request,
                 HttpServletResponse response,
                 ServletContext servletContext)
                 throws Exception

Method associated to a tile and called immediately before the tile is included.

**Parameters:**  
`tileContext` - Current tile context.

`request` - Current request

`response` - Current response

`servletContext` - Current servlet context

**Throws:**  
`Exception`

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
<td align="left"><a href="class-use/Controller.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ControllerSupport.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/Controller.html"><strong>FRAMES</strong></a>    <a href="Controller.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
