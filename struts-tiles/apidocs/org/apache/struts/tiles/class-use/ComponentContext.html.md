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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentContext.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentContext.html"><strong>FRAMES</strong></a>    <a href="ComponentContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.tiles.ComponentContext**
-------------------------------------------

Packages that use [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.actions**](#org.apache.struts.tiles.actions)

  

[**org.apache.struts.tiles.taglib**](#org.apache.struts.tiles.taglib)

The "struts-tiles" tag library contains tags that are useful in creating dynamic reusable components. 

 

<span id="org.apache.struts.tiles"></span>

Uses of [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html "class in org.apache.struts.tiles")

`static ComponentContext`

`ComponentContext.getContext(ServletRequest request)`
           Get component context from request.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html "class in org.apache.struts.tiles")

` void`

`UrlController.execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
            

` void`

`ControllerSupport.execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
            

` void`

`Controller.execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Method associated to a tile and called immediately before the tile is included.

` void`

`ActionController.execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
            

` void`

`UrlController.perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Method associated to a tile and called immediately before the tile is included.

` void`

`ControllerSupport.perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           **Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

` void`

`Controller.perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           **Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

` void`

`ActionController.perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Method associated to a tile and called immediately before tile is included.

`static void`

`ComponentContext.setContext(ComponentContext context, ServletRequest request)`
           Store component context into request.

 

<span id="org.apache.struts.tiles.actions"></span>

Uses of [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.actions](../../../../../org/apache/struts/tiles/actions/package-summary.html)

 

Methods in [org.apache.struts.tiles.actions](../../../../../org/apache/struts/tiles/actions/package-summary.html.md) with parameters of type [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html "class in org.apache.struts.tiles")

` ActionForward`

`TilesAction.execute(ComponentContext context, ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

 

<span id="org.apache.struts.tiles.taglib"></span>

Uses of [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html)

 

Fields in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html.md) declared as [ComponentContext](../../../../../org/apache/struts/tiles/ComponentContext.html "class in org.apache.struts.tiles")

`protected  ComponentContext`

`InsertTag.cachedCurrentContext`
           Current component context.

`protected  ComponentContext`

`InsertTag.InsertHandler.currentContext`
            

`protected  ComponentContext`

`InsertTag.InsertHandler.subCompContext`
            

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentContext.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentContext.html"><strong>FRAMES</strong></a>    <a href="ComponentContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
