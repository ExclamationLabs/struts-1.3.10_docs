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
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.tiles.DefinitionsFactory**
---------------------------------------------

Packages that use [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md "interface in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.definition**](#org.apache.struts.tiles.definition)

  

 

<span id="org.apache.struts.tiles"></span>

Uses of [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Fields in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) declared as [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles")

`protected  DefinitionsFactory`

`TilesPlugin.definitionFactory`
           Associated definition factory.

`protected  DefinitionsFactory`

`TilesRequestProcessor.definitionsFactory`
           Definitions factory.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles")

`protected  DefinitionsFactory`

`TilesUtilImpl.createDefinitionFactoryInstance(String classname)`
           Create Definition factory of specified classname.

` DefinitionsFactory`

`TilesUtilImpl.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static DefinitionsFactory`

`TilesUtil.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, Map properties)`
           **Deprecated.** Create default Definition factory.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, Map properties, String classname)`
           **Deprecated.** *Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)*

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)`
           **Deprecated.** Create Definition factory.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig, boolean checkIfExist)`
           **Deprecated.** Create Definition factory.

` DefinitionsFactory`

`TilesRequestProcessor.getDefinitionsFactory()`
           Get associated definition factory.

`static DefinitionsFactory`

`DefinitionsUtil.getDefinitionsFactory(ServletContext servletContext)`
           **Deprecated.** *Use [`TilesUtil.getDefinitionsFactory(ServletRequest, ServletContext)`](../../../../../org/apache/struts/tiles/TilesUtil.html.md#getDefinitionsFactory(javax.servlet.ServletRequest,%20javax.servlet.ServletContext))*

` DefinitionsFactory`

`TilesUtilStrutsModulesImpl.getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to specified moduleConfig.

` DefinitionsFactory`

`TilesUtilStrutsImpl.getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to the specified moduleConfig.

` DefinitionsFactory`

`TilesUtilStrutsModulesImpl.getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get the definition factory from appropriate servlet context.

` DefinitionsFactory`

`TilesUtilImpl.getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get definition factory from appropriate servlet context.

`static DefinitionsFactory`

`TilesUtil.getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get definition factory from appropriate servlet context.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles")

`protected  void`

`TilesUtilStrutsModulesImpl.makeDefinitionsFactoryAccessible(DefinitionsFactory factory, ServletContext servletContext)`
           Make definition factory accessible to tags.

`protected  void`

`TilesUtilImpl.makeDefinitionsFactoryAccessible(DefinitionsFactory factory, ServletContext servletContext)`
           Make definition factory accessible to Tags.

 

<span id="org.apache.struts.tiles.definition"></span>

Uses of [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md "interface in org.apache.struts.tiles") in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html)

 

Classes in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that implement [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles")

` class`

`ComponentDefinitionsFactoryWrapper`
           Wrapper from new definition factory interface to old interface.

 

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
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
