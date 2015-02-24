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
<td align="left"><a href="../../../../../org/apache/struts/config/MessageResourcesConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useMessageResourcesConfig.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.MessageResourcesConfig**
--------------------------------------------------

Packages that use [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

 

<span id="org.apache.struts.config"></span>

Uses of [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` MessageResourcesConfig`

`ModuleConfig.findMessageResourcesConfig(String key)`
            Return the message resources configuration for the specified key, if any; otherwise return `null`.

` MessageResourcesConfig[]`

`ModuleConfig.findMessageResourcesConfigs()`
            Return the message resources configurations for this module.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addMessageResourcesConfig(MessageResourcesConfig config)`
            Add a new `MessageResourcesConfig` instance to the set associated with this module.

` void`

`ModuleConfig.removeMessageResourcesConfig(MessageResourcesConfig config)`
            Remove the specified message resources configuration instance.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` MessageResourcesConfig`

`ModuleConfigImpl.findMessageResourcesConfig(String key)`
            Return the message resources configuration for the specified key, if any; otherwise return `null`.

` MessageResourcesConfig[]`

`ModuleConfigImpl.findMessageResourcesConfigs()`
            Return the message resources configurations for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addMessageResourcesConfig(MessageResourcesConfig config)`
            Add a new `MessageResourcesConfig` instance to the set associated with this module.

` void`

`ModuleConfigImpl.removeMessageResourcesConfig(MessageResourcesConfig config)`
            Remove the specified message resources configuration instance.

 

<span id="org.apache.struts.util"></span>

Uses of [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Fields in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) declared as [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

`protected  MessageResourcesConfig`

`MessageResourcesFactory.config`
           Configuration information for Message Resources.

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) that return [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` MessageResourcesConfig`

`MessageResourcesFactory.getConfig()`
           Set the configuration information for Message Resources.

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [MessageResourcesConfig](../../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config")

` void`

`MessageResourcesFactory.setConfig(MessageResourcesConfig config)`
           Return the configuration information for Message Resources.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/MessageResourcesConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useMessageResourcesConfig.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
