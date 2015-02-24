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
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentDefinition.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentDefinition.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinition.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.tiles.ComponentDefinition**
----------------------------------------------

Packages that use [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.definition**](#org.apache.struts.tiles.definition)

  

[**org.apache.struts.tiles.taglib**](#org.apache.struts.tiles.taglib)

The "struts-tiles" tag library contains tags that are useful in creating dynamic reusable components. 

[**org.apache.struts.tiles.taglib.util**](#org.apache.struts.tiles.taglib.util)

  

[**org.apache.struts.tiles.xmlDefinition**](#org.apache.struts.tiles.xmlDefinition)

  

 

<span id="org.apache.struts.tiles"></span>

Uses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

`static ComponentDefinition`

`DefinitionsUtil.getActionDefinition(ServletRequest request)`
           **Deprecated.** Get Definition stored in jsp context by an action.

`static ComponentDefinition`

`TilesUtil.getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`DefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`ComponentDefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           **Deprecated.** Get a definition by its name.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

`static void`

`DefinitionsUtil.removeActionDefinition(ServletRequest request, ComponentDefinition definition)`
           **Deprecated.** Remove Definition stored in jsp context.

`static void`

`DefinitionsUtil.setActionDefinition(ServletRequest request, ComponentDefinition definition)`
           **Deprecated.** Store definition in jsp context.

 

| Constructors in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ComponentDefinition(ComponentDefinition definition)`                                                                                                                                                                                                   
            Copy Constructor.                                                                                                                                                                                                                              |

 

<span id="org.apache.struts.tiles.definition"></span>

Uses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html)

 

Methods in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that return [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

` ComponentDefinition`

`ReloadableDefinitionsFactory.getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`ComponentDefinitionsFactoryWrapper.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get requested definition.

 

<span id="org.apache.struts.tiles.taglib"></span>

Uses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html)

 

Methods in [org.apache.struts.tiles.taglib](../../../../../org/apache/struts/tiles/taglib/package-summary.html.md) with parameters of type [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

`protected  InsertTag.TagHandler`

`InsertTag.processDefinition(ComponentDefinition definition)`
           End of Process tag attribute "definition".

 

<span id="org.apache.struts.tiles.taglib.util"></span>

Uses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.taglib.util](../../../../../org/apache/struts/tiles/taglib/util/package-summary.html)

 

Methods in [org.apache.struts.tiles.taglib.util](../../../../../org/apache/struts/tiles/taglib/util/package-summary.html.md) that return [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

`static ComponentDefinition`

`TagUtils.getComponentDefinition(String name, PageContext pageContext)`
           Get component definition by its name.

 

<span id="org.apache.struts.tiles.xmlDefinition"></span>

Uses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html)

 

Subclasses of [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html)

` class`

`XmlDefinition`
           A definition read from an XML definitions file.

 

Methods in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html.md) that return [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

` ComponentDefinition`

`FactorySet.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`DefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

 

Methods in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html.md) with parameters of type [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles")

` void`

`DefinitionsFactory.putDefinition(ComponentDefinition definition)`
           Put definition in set.

 

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
<td align="left"><a href="../../../../../org/apache/struts/tiles/ComponentDefinition.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useComponentDefinition.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinition.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
