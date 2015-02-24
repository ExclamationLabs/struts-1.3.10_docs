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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/util/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/struts/config/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.struts.chain.contexts
----------------------------------------

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing.

**See:**
           [**Description**](#package_description)

**Interface Summary**

**[ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")**

An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services

 

**Class Summary**

**[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")**

Provide an abstract but semi-complete implementation of ActionContext to serve as the base for concrete implementations.

**[ContextWrapper](../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md "class in org.apache.struts.chain.contexts")**

Provide a base class for any Context Implementation which is primarily intended for use in a subchain.

**[MockActionContext](../../../../../org/apache/struts/chain/contexts/MockActionContext.html.md "class in org.apache.struts.chain.contexts")**

Implement `ActionContext` with empty maps for `applicationScope`, `sessionScope`, `requestScope`, and `parameterMap` properties.

**[ServletActionContext](../../../../../org/apache/struts/chain/contexts/ServletActionContext.html.md "class in org.apache.struts.chain.contexts")**

Implement ActionContext interface while making Servlet API-specific values available.

**[WebActionContext](../../../../../org/apache/struts/chain/contexts/WebActionContext.html.md "class in org.apache.struts.chain.contexts")**

Provide a Subclass of ActionContextBase which is understood to be wrapping an instance of `org.apache.commons.chain.web.WebContext`.

 

<span id="package_description"></span>

Package org.apache.struts.chain.contexts Description
----------------------------------------------------

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing.

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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/util/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/struts/config/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
