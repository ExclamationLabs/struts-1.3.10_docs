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
<td align="left"> <a href="../../../../../org/apache/struts/chain/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/generic/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.struts.chain.commands
----------------------------------------

Configurable commands that may be placed within the request processor.

**See:**
           [**Description**](#package_description)

**Interface Summary**

**[ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")**

Marks a commons-chain `Command` which expects to operate upon a Struts `ActionContext`.

 

**Class Summary**

**[AbstractAuthorizeAction](../../../../../org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md "class in org.apache.struts.chain.commands")**

Determine whether the requested action is authorized for the current user.

**[AbstractCreateAction](../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html.md "class in org.apache.struts.chain.commands")**

Create (if necessary) and cache an `Action` for this request.

**[AbstractExceptionHandler](../../../../../org/apache/struts/chain/commands/AbstractExceptionHandler.html.md "class in org.apache.struts.chain.commands")**

Invoke the local or global exception handler configured for the exception class that occurred.

**[AbstractExecuteAction](../../../../../org/apache/struts/chain/commands/AbstractExecuteAction.html.md "class in org.apache.struts.chain.commands")**

Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

**[AbstractPerformForward](../../../../../org/apache/struts/chain/commands/AbstractPerformForward.html.md "class in org.apache.struts.chain.commands")**

Perform forwarding or redirection based on the specified `ForwardConfig` (if any).

**[AbstractPerformInclude](../../../../../org/apache/struts/chain/commands/AbstractPerformInclude.html.md "class in org.apache.struts.chain.commands")**

Perform forwarding or redirection based on the specified `String` (if any).

**[AbstractPopulateActionForm](../../../../../org/apache/struts/chain/commands/AbstractPopulateActionForm.html.md "class in org.apache.struts.chain.commands")**

Populate the form bean (if any) for this request.

**[AbstractRequestNoCache](../../../../../org/apache/struts/chain/commands/AbstractRequestNoCache.html.md "class in org.apache.struts.chain.commands")**

Check to see if the controller is configured to prevent caching, and if so, request no cache flags to be set.

**[AbstractSelectAction](../../../../../org/apache/struts/chain/commands/AbstractSelectAction.html.md "class in org.apache.struts.chain.commands")**

Cache the `ActionConfig` instance for the action to be used for processing this request.

**[AbstractSelectForward](../../../../../org/apache/struts/chain/commands/AbstractSelectForward.html.md "class in org.apache.struts.chain.commands")**

Select and cache the `ActionForward` for this `ActionConfig` if specified.

**[AbstractSelectInput](../../../../../org/apache/struts/chain/commands/AbstractSelectInput.html.md "class in org.apache.struts.chain.commands")**

Select and cache a `ForwardConfig` that returns us to the input page for the current action, if any.

**[AbstractSelectLocale](../../../../../org/apache/struts/chain/commands/AbstractSelectLocale.html.md "class in org.apache.struts.chain.commands")**

Select the `Locale` to be used for this request.

**[AbstractSelectModule](../../../../../org/apache/struts/chain/commands/AbstractSelectModule.html.md "class in org.apache.struts.chain.commands")**

Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.

**[AbstractSetContentType](../../../../../org/apache/struts/chain/commands/AbstractSetContentType.html.md "class in org.apache.struts.chain.commands")**

Check to see if the content type is set, and if so, set it for this response.

**[AbstractSetOriginalURI](../../../../../org/apache/struts/chain/commands/AbstractSetOriginalURI.html.md "class in org.apache.struts.chain.commands")**

Check to original uri is set, and if not, set it for this request.

**[AbstractValidateActionForm](../../../../../org/apache/struts/chain/commands/AbstractValidateActionForm.html.md "class in org.apache.struts.chain.commands")**

Validate the properties of the form bean for this request.

**[ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")**

Simple abstract class which avoids frequent casting to `ActionContext` in commands explicitly intended for use with that class.

**[CreateActionForm](../../../../../org/apache/struts/chain/commands/CreateActionForm.html.md "class in org.apache.struts.chain.commands")**

Create (if necessary) and cache a form bean for this request.

**[ExceptionCatcher](../../../../../org/apache/struts/chain/commands/ExceptionCatcher.html.md "class in org.apache.struts.chain.commands")**

Intercept any exception thrown by a subsequent `Command` in this processing chain, and fire the configured exception handler chain after storing the exception that has occurred into the `Context`.

**[ExecuteCommand](../../../../../org/apache/struts/chain/commands/ExecuteCommand.html.md "class in org.apache.struts.chain.commands")**

Invoke the appropriate `Command` for this request.

**[ExecuteForwardCommand](../../../../../org/apache/struts/chain/commands/ExecuteForwardCommand.html.md "class in org.apache.struts.chain.commands")**

Look up and execute a commons-chain `Command` based on properties of the ActionContext's `forwardConfig` property.

**[RemoveCachedMessages](../../../../../org/apache/struts/chain/commands/RemoveCachedMessages.html.md "class in org.apache.struts.chain.commands")**

Remove cached messages stored in the session.

**[SelectInclude](../../../../../org/apache/struts/chain/commands/SelectInclude.html.md "class in org.apache.struts.chain.commands")**

Select and cache the include for this `ActionConfig` if specified.

 

**Exception Summary**

**[InvalidPathException](../../../../../org/apache/struts/chain/commands/InvalidPathException.html.md "class in org.apache.struts.chain.commands")**

Exception thrown when no mapping can be found for the specified path.

**[UnauthorizedActionException](../../../../../org/apache/struts/chain/commands/UnauthorizedActionException.html.md "class in org.apache.struts.chain.commands")**

Exception thrown when the chosen action mapping is not authorized for the current request.

 

<span id="package_description"></span>

Package org.apache.struts.chain.commands Description
----------------------------------------------------

Configurable commands that may be placed within the request processor.

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
<td align="left"> <a href="../../../../../org/apache/struts/chain/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/generic/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
