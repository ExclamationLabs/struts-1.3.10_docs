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
<td align="left"><a href="class-use/ControllerSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/Controller.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ControllerSupport.html"><strong>FRAMES</strong></a>    <a href="ControllerSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Class ControllerSupport
------------------------

    java.lang.Object
      org.apache.struts.tiles.ControllerSupport

**All Implemented Interfaces:**  
[Controller](../../../../org/apache/struts/tiles/Controller.html.md "interface in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class ControllerSupport

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Controller](../../../../org/apache/struts/tiles/Controller.html.md "interface in org.apache.struts.tiles")

Basic implementation of Controller. Implementations can extend this class to insulate themselves from changes in the `Controller` interface.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ControllerSupport()`  
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` execute(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Method associated to a tile and called immediately before the tile is included.

` void`

` perform(ComponentContext tileContext, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           **Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ControllerSupport

    public ControllerSupport()

<span id="method_detail"></span>

**Method Detail**

### perform

    public void perform(ComponentContext tileContext,
                        HttpServletRequest request,
                        HttpServletResponse response,
                        ServletContext servletContext)
                 throws ServletException,
                        IOException

**Deprecated.** *Use execute() instead. This will be removed after Struts 1.2.*

Method associated to a tile and called immediately before tile is included. This implementation does nothing.

**Specified by:**  
` perform` in interface `Controller`

<!-- -->

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

    public void execute(ComponentContext tileContext,
                        HttpServletRequest request,
                        HttpServletResponse response,
                        ServletContext servletContext)
                 throws Exception

**Description copied from interface: ` Controller`**

Method associated to a tile and called immediately before the tile is included.

**Specified by:**  
` execute` in interface `Controller`

<!-- -->

**Parameters:**  
`tileContext` - Current tile context.

`request` - Current request

`response` - Current response

`servletContext` - Current servlet context

**Throws:**  
`Exception`

**See Also:**  
[`Controller.execute(org.apache.struts.tiles.ComponentContext, javax.servlet.http.HttpServletRequest, javax.servlet.http.HttpServletResponse, javax.servlet.ServletContext)`](../../../../org/apache/struts/tiles/Controller.html.md#execute(org.apache.struts.tiles.ComponentContext,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20javax.servlet.ServletContext))

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
<td align="left"><a href="class-use/ControllerSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/Controller.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ControllerSupport.html"><strong>FRAMES</strong></a>    <a href="ControllerSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
