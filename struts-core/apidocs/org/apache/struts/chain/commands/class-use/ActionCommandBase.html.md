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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md" title="class in org.apache.struts.chain.commands"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands//class-useActionCommandBase.html"><strong>FRAMES</strong></a>    <a href="ActionCommandBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.chain.commands.ActionCommandBase**
-----------------------------------------------------

Packages that use [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.generic**](#org.apache.struts.chain.commands.generic)

Contains generic commands. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands](../../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Subclasses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands](../../../../../../org/apache/struts/chain/commands/package-summary.html)

` class`

`AbstractAuthorizeAction`
           Determine whether the requested action is authorized for the current user.

` class`

`AbstractCreateAction`
            Create (if necessary) and cache an `Action` for this request.

` class`

`AbstractExceptionHandler`
           Invoke the local or global exception handler configured for the exception class that occurred.

` class`

`AbstractExecuteAction`
           Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

` class`

`AbstractPerformForward`
           Perform forwarding or redirection based on the specified `ForwardConfig` (if any).

` class`

`AbstractPerformInclude`
           Perform forwarding or redirection based on the specified `String` (if any).

` class`

`AbstractPopulateActionForm`
           Populate the form bean (if any) for this request.

` class`

`AbstractRequestNoCache`
           Check to see if the controller is configured to prevent caching, and if so, request no cache flags to be set.

` class`

`AbstractSelectAction`
           Cache the `ActionConfig` instance for the action to be used for processing this request.

` class`

`AbstractSelectForward`
           Select and cache the `ActionForward` for this `ActionConfig` if specified.

` class`

`AbstractSelectInput`
           Select and cache a `ForwardConfig` that returns us to the input page for the current action, if any.

` class`

`AbstractSelectLocale`
           Select the `Locale` to be used for this request.

` class`

`AbstractSelectModule`
           Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.

` class`

`AbstractSetContentType`
           Check to see if the content type is set, and if so, set it for this response.

` class`

`AbstractSetOriginalURI`
           Check to original uri is set, and if not, set it for this request.

` class`

`AbstractValidateActionForm`
           Validate the properties of the form bean for this request.

` class`

`CreateActionForm`
           Create (if necessary) and cache a form bean for this request.

` class`

`ExceptionCatcher`
           Intercept any exception thrown by a subsequent `Command` in this processing chain, and fire the configured exception handler chain after storing the exception that has occurred into the `Context`.

` class`

`ExecuteCommand`
           Invoke the appropriate `Command` for this request.

` class`

`ExecuteForwardCommand`
           Look up and execute a commons-chain `Command` based on properties of the ActionContext's `forwardConfig` property.

` class`

`RemoveCachedMessages`
           Remove cached messages stored in the session.

` class`

`SelectInclude`
           Select and cache the include for this `ActionConfig` if specified.

 

<span id="org.apache.struts.chain.commands.generic"></span>

Uses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands.generic](../../../../../../org/apache/struts/chain/commands/generic/package-summary.html)

 

Subclasses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands.generic](../../../../../../org/apache/struts/chain/commands/generic/package-summary.html)

` class`

`CopyFormToContext`
           Subclass this command and configure it as part of a per-forward chain to perform any necessary pre-population or other preparation for a form before control is dispatched to the view layer.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands.servlet](../../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Subclasses of [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands") in [org.apache.struts.chain.commands.servlet](../../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

` class`

`AuthorizeAction`
           Determine if the action is authorized for the given roles.

` class`

`CreateAction`
           Concrete implementation of `AbstractCreateAction` for use in a Servlet API chain.

` class`

`ExceptionHandler`
           Handle the specified exception.

` class`

`ExecuteAction`
           Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

` class`

`PerformForward`
           Perform forwarding or redirection based on the specified `ForwardConfig` (if any).

` class`

`PerformInclude`
           Perform forwarding or redirection based on the specified include uri (if any).

` class`

`PopulateActionForm`
           Populate the form bean (if any) for this request.

` class`

`RequestNoCache`
           Check to see if the controller is configured to prevent caching, and if so, set the no cache HTTP response headers.

` class`

`SelectAction`
           Cache the `ActionConfig` instance for the action to be used for processing this request.

` class`

`SelectForward`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

` class`

`SelectInput`
           Validate the properties of the form bean for this request.

` class`

`SelectLocale`
           Select the `Locale` to be used for this request.

` class`

`SelectModule`
           Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.

` class`

`SetContentType`
           Check to see if the content type is set, and if so, set it for this response.

` class`

`SetOriginalURI`
           Set the servlet path.

` class`

`ValidateActionForm`
           Validate the properties of the form bean for this request.

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md" title="class in org.apache.struts.chain.commands"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands//class-useActionCommandBase.html"><strong>FRAMES</strong></a>    <a href="ActionCommandBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
