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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.chain.commands**
-----------------------------------

Packages that use [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md)

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.generic**](#org.apache.struts.chain.commands.generic)

Contains generic commands. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

 

<span id="org.apache.struts.chain.commands"></span>

| Classes in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) used by [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionCommand**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommand.html.md#org.apache.struts.chain.commands)**                                                                                               
            Marks a commons-chain `Command` which expects to operate upon a Struts `ActionContext`.                                                                                                                                    |
| **[**ActionCommandBase**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommandBase.html.md#org.apache.struts.chain.commands)**                                                                                       
            Simple abstract class which avoids frequent casting to `ActionContext` in commands explicitly intended for use with that class.                                                                                            |
| **[**ExecuteCommand**](../../../../../org/apache/struts/chain/commands/class-use/ExecuteCommand.html.md#org.apache.struts.chain.commands)**                                                                                             
            Invoke the appropriate `Command` for this request.                                                                                                                                                                         |

 

<span id="org.apache.struts.chain.commands.generic"></span>

| Classes in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) used by [org.apache.struts.chain.commands.generic](../../../../../org/apache/struts/chain/commands/generic/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionCommand**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommand.html.md#org.apache.struts.chain.commands.generic)**                                                                                                       
            Marks a commons-chain `Command` which expects to operate upon a Struts `ActionContext`.                                                                                                                                                    |
| **[**ActionCommandBase**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommandBase.html.md#org.apache.struts.chain.commands.generic)**                                                                                               
            Simple abstract class which avoids frequent casting to `ActionContext` in commands explicitly intended for use with that class.                                                                                                            |

 

<span id="org.apache.struts.chain.commands.servlet"></span>

| Classes in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) used by [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**AbstractAuthorizeAction**](../../../../../org/apache/struts/chain/commands/class-use/AbstractAuthorizeAction.html.md#org.apache.struts.chain.commands.servlet)**                                                                                   
            Determine whether the requested action is authorized for the current user.                                                                                                                                                                 |
| **[**AbstractCreateAction**](../../../../../org/apache/struts/chain/commands/class-use/AbstractCreateAction.html.md#org.apache.struts.chain.commands.servlet)**                                                                                         
             Create (if necessary) and cache an `Action` for this request.                                                                                                                                                                             |
| **[**AbstractExceptionHandler**](../../../../../org/apache/struts/chain/commands/class-use/AbstractExceptionHandler.html.md#org.apache.struts.chain.commands.servlet)**                                                                                 
            Invoke the local or global exception handler configured for the exception class that occurred.                                                                                                                                             |
| **[**AbstractExecuteAction**](../../../../../org/apache/struts/chain/commands/class-use/AbstractExecuteAction.html.md#org.apache.struts.chain.commands.servlet)**                                                                                       
            Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.                                                                                                                                                  |
| **[**AbstractPerformForward**](../../../../../org/apache/struts/chain/commands/class-use/AbstractPerformForward.html.md#org.apache.struts.chain.commands.servlet)**                                                                                     
            Perform forwarding or redirection based on the specified `ForwardConfig` (if any).                                                                                                                                                         |
| **[**AbstractPerformInclude**](../../../../../org/apache/struts/chain/commands/class-use/AbstractPerformInclude.html.md#org.apache.struts.chain.commands.servlet)**                                                                                     
            Perform forwarding or redirection based on the specified `String` (if any).                                                                                                                                                                |
| **[**AbstractPopulateActionForm**](../../../../../org/apache/struts/chain/commands/class-use/AbstractPopulateActionForm.html.md#org.apache.struts.chain.commands.servlet)**                                                                             
            Populate the form bean (if any) for this request.                                                                                                                                                                                          |
| **[**AbstractRequestNoCache**](../../../../../org/apache/struts/chain/commands/class-use/AbstractRequestNoCache.html.md#org.apache.struts.chain.commands.servlet)**                                                                                     
            Check to see if the controller is configured to prevent caching, and if so, request no cache flags to be set.                                                                                                                              |
| **[**AbstractSelectAction**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSelectAction.html.md#org.apache.struts.chain.commands.servlet)**                                                                                         
            Cache the `ActionConfig` instance for the action to be used for processing this request.                                                                                                                                                   |
| **[**AbstractSelectForward**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSelectForward.html.md#org.apache.struts.chain.commands.servlet)**                                                                                       
            Select and cache the `ActionForward` for this `ActionConfig` if specified.                                                                                                                                                                 |
| **[**AbstractSelectInput**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSelectInput.html.md#org.apache.struts.chain.commands.servlet)**                                                                                           
            Select and cache a `ForwardConfig` that returns us to the input page for the current action, if any.                                                                                                                                       |
| **[**AbstractSelectLocale**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSelectLocale.html.md#org.apache.struts.chain.commands.servlet)**                                                                                         
            Select the `Locale` to be used for this request.                                                                                                                                                                                           |
| **[**AbstractSelectModule**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSelectModule.html.md#org.apache.struts.chain.commands.servlet)**                                                                                         
            Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.                                                                                                           |
| **[**AbstractSetContentType**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSetContentType.html.md#org.apache.struts.chain.commands.servlet)**                                                                                     
            Check to see if the content type is set, and if so, set it for this response.                                                                                                                                                              |
| **[**AbstractSetOriginalURI**](../../../../../org/apache/struts/chain/commands/class-use/AbstractSetOriginalURI.html.md#org.apache.struts.chain.commands.servlet)**                                                                                     
            Check to original uri is set, and if not, set it for this request.                                                                                                                                                                         |
| **[**AbstractValidateActionForm**](../../../../../org/apache/struts/chain/commands/class-use/AbstractValidateActionForm.html.md#org.apache.struts.chain.commands.servlet)**                                                                             
            Validate the properties of the form bean for this request.                                                                                                                                                                                 |
| **[**ActionCommand**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommand.html.md#org.apache.struts.chain.commands.servlet)**                                                                                                       
            Marks a commons-chain `Command` which expects to operate upon a Struts `ActionContext`.                                                                                                                                                    |
| **[**ActionCommandBase**](../../../../../org/apache/struts/chain/commands/class-use/ActionCommandBase.html.md#org.apache.struts.chain.commands.servlet)**                                                                                               
            Simple abstract class which avoids frequent casting to `ActionContext` in commands explicitly intended for use with that class.                                                                                                            |

 

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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
