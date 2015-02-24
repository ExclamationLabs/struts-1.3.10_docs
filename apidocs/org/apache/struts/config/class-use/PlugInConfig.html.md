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
<td align="left"><a href="../../../../../org/apache/struts/config/PlugInConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-usePlugInConfig.html"><strong>FRAMES</strong></a>    <a href="PlugInConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.PlugInConfig**
----------------------------------------

Packages that use [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

 

<span id="org.apache.struts.config"></span>

Uses of [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

` PlugInConfig[]`

`ModuleConfig.findPlugInConfigs()`
            Return the configured plug-in actions for this module.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addPlugInConfig(PlugInConfig plugInConfig)`
            Add a newly configured [`PlugInConfig`](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

` PlugInConfig[]`

`ModuleConfigImpl.findPlugInConfigs()`
            Return the configured plug-in actions for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addPlugInConfig(PlugInConfig plugInConfig)`
            Add a newly configured [`PlugInConfig`](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

 

<span id="org.apache.struts.tiles"></span>

Uses of [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Fields in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) declared as [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

`protected  PlugInConfig`

`TilesPlugin.currentPlugInConfigObject`
           The plugin config object provided by the ActionServlet initializing this plugin.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [PlugInConfig](../../../../../org/apache/struts/config/PlugInConfig.html "class in org.apache.struts.config")

` void`

`TilesPlugin.setCurrentPlugInConfigObject(PlugInConfig plugInConfigObject)`
           Method used by the ActionServlet initializing this plugin.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/PlugInConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-usePlugInConfig.html"><strong>FRAMES</strong></a>    <a href="PlugInConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
