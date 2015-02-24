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
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactoryConfig.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.tiles.DefinitionsFactoryConfig**
---------------------------------------------------

Packages that use [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md "class in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.definition**](#org.apache.struts.tiles.definition)

  

 

<span id="org.apache.struts.tiles"></span>

Uses of [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html "class in org.apache.struts.tiles")

` DefinitionsFactoryConfig`

`DefinitionsFactory.getConfig()`
           Get factory configuration.

`protected  DefinitionsFactoryConfig`

`TilesPlugin.readFactoryConfig(ActionServlet servlet, ModuleConfig config)`
           Create FactoryConfig and initialize it from web.xml and struts-config.xml.

`protected static DefinitionsFactoryConfig`

`DefinitionsUtil.readFactoryConfig(ServletConfig servletConfig)`
           **Deprecated.** Create FactoryConfig and initialize it from web.xml.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html "class in org.apache.struts.tiles")

` DefinitionsFactory`

`TilesUtilImpl.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static DefinitionsFactory`

`TilesUtil.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

` void`

`DefinitionsFactory.init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Init definition factory.

`static void`

`DefinitionsUtil.populateDefinitionsFactoryConfig(DefinitionsFactoryConfig factoryConfig, ServletConfig servletConfig)`
           **Deprecated.** Populate Definition Factory Config from web.xml properties.

` void`

`DefinitionsFactory.setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set factory configuration.

 

<span id="org.apache.struts.tiles.definition"></span>

Uses of [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html)

 

Methods in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that return [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html "class in org.apache.struts.tiles")

` DefinitionsFactoryConfig`

`ComponentDefinitionsFactoryWrapper.getConfig()`
           Get underlying factory configuration.

 

Methods in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) with parameters of type [DefinitionsFactoryConfig](../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html "class in org.apache.struts.tiles")

`static Map`

`ComponentDefinitionsFactoryWrapper.createConfigMap(DefinitionsFactoryConfig config)`
           Create map of configuration attributes from configuration object.

` void`

`ComponentDefinitionsFactoryWrapper.init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Call underlying factory init method.

` void`

`ComponentDefinitionsFactoryWrapper.setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set underlying factory configuration.

 

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
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactoryConfig.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
