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
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.tiles.ComponentDefinitionsFactory**
------------------------------------------------------

Packages that use [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles")

[**org.apache.struts.tiles.definition**](#org.apache.struts.tiles.definition)

  

[**org.apache.struts.tiles.xmlDefinition**](#org.apache.struts.tiles.xmlDefinition)

  

 

<span id="org.apache.struts.tiles.definition"></span>

Uses of [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html)

 

Classes in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that implement [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

` class`

`ReloadableDefinitionsFactory`
           A reloadable factory.

 

Fields in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) declared as [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

`protected  ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.factory`
           The real factory instance.

 

Methods in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that return [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createDefaultFactory(ServletContext servletContext, Map properties)`
           Create default Definition factory.

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createFactory(ServletContext servletContext, Map properties)`
           Create Definition factory.

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createFactoryFromClassname(ServletContext servletContext, Map properties, String classname)`
           Create Definition factory from provided classname.

`protected  ComponentDefinitionsFactory`

`ComponentDefinitionsFactoryWrapper.createFactoryInstance(String classname)`
           Create Definition factory from provided classname which must implement [`ComponentDefinitionsFactory`](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles").

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.getFactory()`
           Get underlying factory instance.

` ComponentDefinitionsFactory`

`ComponentDefinitionsFactoryWrapper.getInternalFactory()`
           Get internal factory.

 

| Constructors in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) with parameters of type [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ComponentDefinitionsFactoryWrapper(ComponentDefinitionsFactory factory)`                                                                                                                                                                                                                         
            Constructor.                                                                                                                                                                                                                                                                             |

 

<span id="org.apache.struts.tiles.xmlDefinition"></span>

Uses of [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html)

 

Classes in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html.md) that implement [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

` class`

`FactorySet`
           Component Definitions factory.

` class`

`I18nFactorySet`
           Definitions factory.

 

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
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
