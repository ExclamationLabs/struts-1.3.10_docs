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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.chain.contexts**
-----------------------------------

Packages that use [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md)

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.generic**](#org.apache.struts.chain.commands.generic)

Contains generic commands. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.tiles.commands**](#org.apache.struts.tiles.commands)

  

 

<span id="org.apache.struts.chain"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.chain)**                                                                                      
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                           |

 

<span id="org.apache.struts.chain.commands"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.chain.commands)**                                                                                               
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                                             |

 

<span id="org.apache.struts.chain.commands.generic"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.chain.commands.generic](../../../../../org/apache/struts/chain/commands/generic/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.chain.commands.generic)**                                                                                                       
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                                                             |

 

<span id="org.apache.struts.chain.commands.servlet"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.chain.commands.servlet)**                                                                                                       
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                                                             |

 

<span id="org.apache.struts.chain.contexts"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.chain.contexts)**                                                                                               
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                                             |
| **[**ActionContextBase**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContextBase.html.md#org.apache.struts.chain.contexts)**                                                                                       
             Provide an abstract but semi-complete implementation of ActionContext to serve as the base for concrete implementations.                                                                                                  |
| **[**ContextWrapper**](../../../../../org/apache/struts/chain/contexts/class-use/ContextWrapper.html.md#org.apache.struts.chain.contexts)**                                                                                             
             Provide a base class for any Context Implementation which is primarily intended for use in a subchain.                                                                                                                    |
| **[**WebActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/WebActionContext.html.md#org.apache.struts.chain.contexts)**                                                                                         
             Provide a Subclass of ActionContextBase which is understood to be wrapping an instance of `org.apache.commons.chain.web.WebContext`.                                                                                      |

 

<span id="org.apache.struts.config"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ActionContext.html.md#org.apache.struts.config)**                                                                                       
            An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services                                                             |

 

<span id="org.apache.struts.tiles.commands"></span>

| Classes in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) used by [org.apache.struts.tiles.commands](../../../../../org/apache/struts/tiles/commands/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ServletActionContext**](../../../../../org/apache/struts/chain/contexts/class-use/ServletActionContext.html.md#org.apache.struts.tiles.commands)**                                                                                 
             Implement ActionContext interface while making Servlet API-specific values available.                                                                                                                                     |

 

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
