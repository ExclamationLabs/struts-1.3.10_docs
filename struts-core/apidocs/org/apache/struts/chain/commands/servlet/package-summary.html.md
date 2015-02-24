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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/generic/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/util/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.struts.chain.commands.servlet
------------------------------------------------

Commands which are particular to servlet processing.

**See:**
           [**Description**](#package_description)

**Class Summary**

**[AuthorizeAction](../../../../../../org/apache/struts/chain/commands/servlet/AuthorizeAction.html.md "class in org.apache.struts.chain.commands.servlet")**

Determine if the action is authorized for the given roles.

**[CreateAction](../../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html.md "class in org.apache.struts.chain.commands.servlet")**

Concrete implementation of `AbstractCreateAction` for use in a Servlet API chain.

**[ExceptionHandler](../../../../../../org/apache/struts/chain/commands/servlet/ExceptionHandler.html.md "class in org.apache.struts.chain.commands.servlet")**

Handle the specified exception.

**[ExecuteAction](../../../../../../org/apache/struts/chain/commands/servlet/ExecuteAction.html.md "class in org.apache.struts.chain.commands.servlet")**

Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

**[PerformForward](../../../../../../org/apache/struts/chain/commands/servlet/PerformForward.html.md "class in org.apache.struts.chain.commands.servlet")**

Perform forwarding or redirection based on the specified `ForwardConfig` (if any).

**[PerformInclude](../../../../../../org/apache/struts/chain/commands/servlet/PerformInclude.html.md "class in org.apache.struts.chain.commands.servlet")**

Perform forwarding or redirection based on the specified include uri (if any).

**[PopulateActionForm](../../../../../../org/apache/struts/chain/commands/servlet/PopulateActionForm.html.md "class in org.apache.struts.chain.commands.servlet")**

Populate the form bean (if any) for this request.

**[RequestNoCache](../../../../../../org/apache/struts/chain/commands/servlet/RequestNoCache.html.md "class in org.apache.struts.chain.commands.servlet")**

Check to see if the controller is configured to prevent caching, and if so, set the no cache HTTP response headers.

**[SelectAction](../../../../../../org/apache/struts/chain/commands/servlet/SelectAction.html.md "class in org.apache.struts.chain.commands.servlet")**

Cache the `ActionConfig` instance for the action to be used for processing this request.

**[SelectForward](../../../../../../org/apache/struts/chain/commands/servlet/SelectForward.html.md "class in org.apache.struts.chain.commands.servlet")**

Create and return a `ForwardConfig` representing the specified module-relative destination.

**[SelectInput](../../../../../../org/apache/struts/chain/commands/servlet/SelectInput.html.md "class in org.apache.struts.chain.commands.servlet")**

Validate the properties of the form bean for this request.

**[SelectLocale](../../../../../../org/apache/struts/chain/commands/servlet/SelectLocale.html.md "class in org.apache.struts.chain.commands.servlet")**

Select the `Locale` to be used for this request.

**[SelectModule](../../../../../../org/apache/struts/chain/commands/servlet/SelectModule.html.md "class in org.apache.struts.chain.commands.servlet")**

Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.

**[SetContentType](../../../../../../org/apache/struts/chain/commands/servlet/SetContentType.html.md "class in org.apache.struts.chain.commands.servlet")**

Check to see if the content type is set, and if so, set it for this response.

**[SetOriginalURI](../../../../../../org/apache/struts/chain/commands/servlet/SetOriginalURI.html.md "class in org.apache.struts.chain.commands.servlet")**

Set the servlet path.

**[ValidateActionForm](../../../../../../org/apache/struts/chain/commands/servlet/ValidateActionForm.html.md "class in org.apache.struts.chain.commands.servlet")**

Validate the properties of the form bean for this request.

 

<span id="package_description"></span>

Package org.apache.struts.chain.commands.servlet Description
------------------------------------------------------------

Commands which are particular to servlet processing.

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/generic/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/util/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
