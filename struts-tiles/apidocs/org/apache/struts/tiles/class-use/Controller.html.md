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
<td align="left"><a href="../../../../../org/apache/struts/tiles/Controller.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useController.html"><strong>FRAMES</strong></a>    <a href="Controller.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.tiles.Controller**
-------------------------------------

Packages that use [Controller](../../../../../org/apache/struts/tiles/Controller.html.md "interface in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.taglib**](#org.apache.struts.tiles.taglib)

The "struts-tiles" tag library contains tags that are useful in creating dynamic reusable components. 

 

<span id="org.apache.struts.tiles"></span>

Uses of [Controller](../../../../../org/apache/struts/tiles/Controller.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Classes in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that implement [Controller](../../../../../org/apache/struts/tiles/Controller.html "interface in org.apache.struts.tiles")

` class`

`ActionController`
           Struts wrapper implementation of Controller.

` class`

`ControllerSupport`
           Basic implementation of Controller.

` class`

`UrlController`
           Tiles controller including a local URL.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [Controller](../../../../../org/apache/struts/tiles/Controller.html "interface in org.apache.struts.tiles")

`static Controller`

`ComponentDefinition.createController(String name, String controllerType)`
           Create a new instance of controller named in parameter.

`static Controller`

`ComponentDefinition.createControllerFromClassname(String classname)`
           Create a controller from specified classname

` Controller`

`ComponentDefinition.getControllerInstance()`
           Get controller instance.

` Controller`

`ComponentDefinition.getOrCreateController()`
           Get or create controller.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [Controller](../../../../../org/apache/struts/tiles/Controller.html "interface in org.apache.struts.tiles")

` void`

`ComponentDefinition.setControllerInstance(Controller controller)`
           Set controller.

 

<span id="org.apache.struts.tiles.taglib"></span>

Uses of [Controller](../../../../../org/apache/struts/tiles/Controller.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html)

 

Fields in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html.md) declared as [Controller](../../../../../org/apache/struts/tiles/Controller.html "interface in org.apache.struts.tiles")

`protected  Controller`

`InsertTag.InsertHandler.controller`
            

 

| Constructors in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html.md) with parameters of type [Controller](../../../../../org/apache/struts/tiles/Controller.html "interface in org.apache.struts.tiles") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` InsertTag.InsertHandler(Map attributes, String page, String role, Controller controller)`                                                                                                                                                              
            Constructor.                                                                                                                                                                                                                                   |
| ` InsertTag.InsertHandler(String page, String role, Controller controller)`                                                                                                                                                                              
            Constructor.                                                                                                                                                                                                                                   |

 

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
<td align="left"><a href="../../../../../org/apache/struts/tiles/Controller.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useController.html"><strong>FRAMES</strong></a>    <a href="Controller.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
