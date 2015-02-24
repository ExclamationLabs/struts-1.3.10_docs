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
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionCommand.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/AbstractValidateActionForm.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ActionCommandBase.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ActionCommand.html"><strong>FRAMES</strong></a>    <a href="ActionCommand.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.commands
 Interface ActionCommand
--------------------------------

**All Superinterfaces:**  
org.apache.commons.chain.Command

<!-- -->

**All Known Implementing Classes:**  
[AbstractAuthorizeAction](../../../../../org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md "class in org.apache.struts.chain.commands"), [AbstractCreateAction](../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html "class in org.apache.struts.chain.commands"), [AbstractExceptionHandler](../../../../../org/apache/struts/chain/commands/AbstractExceptionHandler.html "class in org.apache.struts.chain.commands"), [AbstractExecuteAction](../../../../../org/apache/struts/chain/commands/AbstractExecuteAction.html "class in org.apache.struts.chain.commands"), [AbstractPerformForward](../../../../../org/apache/struts/chain/commands/AbstractPerformForward.html "class in org.apache.struts.chain.commands"), [AbstractPerformInclude](../../../../../org/apache/struts/chain/commands/AbstractPerformInclude.html "class in org.apache.struts.chain.commands"), [AbstractPopulateActionForm](../../../../../org/apache/struts/chain/commands/AbstractPopulateActionForm.html "class in org.apache.struts.chain.commands"), [AbstractRequestNoCache](../../../../../org/apache/struts/chain/commands/AbstractRequestNoCache.html "class in org.apache.struts.chain.commands"), [AbstractSelectAction](../../../../../org/apache/struts/chain/commands/AbstractSelectAction.html "class in org.apache.struts.chain.commands"), [AbstractSelectForward](../../../../../org/apache/struts/chain/commands/AbstractSelectForward.html "class in org.apache.struts.chain.commands"), [AbstractSelectInput](../../../../../org/apache/struts/chain/commands/AbstractSelectInput.html "class in org.apache.struts.chain.commands"), [AbstractSelectLocale](../../../../../org/apache/struts/chain/commands/AbstractSelectLocale.html "class in org.apache.struts.chain.commands"), [AbstractSelectModule](../../../../../org/apache/struts/chain/commands/AbstractSelectModule.html "class in org.apache.struts.chain.commands"), [AbstractSetContentType](../../../../../org/apache/struts/chain/commands/AbstractSetContentType.html "class in org.apache.struts.chain.commands"), [AbstractSetOriginalURI](../../../../../org/apache/struts/chain/commands/AbstractSetOriginalURI.html "class in org.apache.struts.chain.commands"), [AbstractValidateActionForm](../../../../../org/apache/struts/chain/commands/AbstractValidateActionForm.html "class in org.apache.struts.chain.commands"), [ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html "class in org.apache.struts.chain.commands"), [AuthorizeAction](../../../../../org/apache/struts/chain/commands/servlet/AuthorizeAction.html "class in org.apache.struts.chain.commands.servlet"), [CopyFormToContext](../../../../../org/apache/struts/chain/commands/generic/CopyFormToContext.html "class in org.apache.struts.chain.commands.generic"), [CreateAction](../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html "class in org.apache.struts.chain.commands.servlet"), [CreateActionForm](../../../../../org/apache/struts/chain/commands/CreateActionForm.html "class in org.apache.struts.chain.commands"), [ExceptionCatcher](../../../../../org/apache/struts/chain/commands/ExceptionCatcher.html "class in org.apache.struts.chain.commands"), [ExceptionHandler](../../../../../org/apache/struts/chain/commands/servlet/ExceptionHandler.html "class in org.apache.struts.chain.commands.servlet"), [ExecuteAction](../../../../../org/apache/struts/chain/commands/servlet/ExecuteAction.html "class in org.apache.struts.chain.commands.servlet"), [ExecuteCommand](../../../../../org/apache/struts/chain/commands/ExecuteCommand.html "class in org.apache.struts.chain.commands"), [ExecuteForwardCommand](../../../../../org/apache/struts/chain/commands/ExecuteForwardCommand.html "class in org.apache.struts.chain.commands"), [PerformForward](../../../../../org/apache/struts/chain/commands/servlet/PerformForward.html "class in org.apache.struts.chain.commands.servlet"), [PerformInclude](../../../../../org/apache/struts/chain/commands/servlet/PerformInclude.html "class in org.apache.struts.chain.commands.servlet"), [PopulateActionForm](../../../../../org/apache/struts/chain/commands/servlet/PopulateActionForm.html "class in org.apache.struts.chain.commands.servlet"), [RemoveCachedMessages](../../../../../org/apache/struts/chain/commands/RemoveCachedMessages.html "class in org.apache.struts.chain.commands"), [RequestNoCache](../../../../../org/apache/struts/chain/commands/servlet/RequestNoCache.html "class in org.apache.struts.chain.commands.servlet"), [SelectAction](../../../../../org/apache/struts/chain/commands/servlet/SelectAction.html "class in org.apache.struts.chain.commands.servlet"), [SelectForward](../../../../../org/apache/struts/chain/commands/servlet/SelectForward.html "class in org.apache.struts.chain.commands.servlet"), [SelectInclude](../../../../../org/apache/struts/chain/commands/SelectInclude.html "class in org.apache.struts.chain.commands"), [SelectInput](../../../../../org/apache/struts/chain/commands/servlet/SelectInput.html "class in org.apache.struts.chain.commands.servlet"), [SelectLocale](../../../../../org/apache/struts/chain/commands/servlet/SelectLocale.html "class in org.apache.struts.chain.commands.servlet"), [SelectModule](../../../../../org/apache/struts/chain/commands/servlet/SelectModule.html "class in org.apache.struts.chain.commands.servlet"), [SetContentType](../../../../../org/apache/struts/chain/commands/servlet/SetContentType.html "class in org.apache.struts.chain.commands.servlet"), [SetOriginalURI](../../../../../org/apache/struts/chain/commands/servlet/SetOriginalURI.html "class in org.apache.struts.chain.commands.servlet"), [ValidateActionForm](../../../../../org/apache/struts/chain/commands/servlet/ValidateActionForm.html "class in org.apache.struts.chain.commands.servlet")

------------------------------------------------------------------------

    public interface ActionCommand

extends org.apache.commons.chain.Command

Marks a commons-chain `Command` which expects to operate upon a Struts `ActionContext`.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(ActionContext actionContext)`
            

 <span id="methods_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Methods inherited from interface org.apache.commons.chain.Command** |
|-----------------------------------------------------------------------|
| `execute`                                                             |

 

<span id="method_detail"></span>

**Method Detail**

### execute

    boolean execute(ActionContext actionContext)
                    throws Exception

**Parameters:**  
`actionContext` - The `Context` for the current request

**Returns:**  
TRUE if processing should halt

**Throws:**  
`Exception` - On any error

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
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionCommand.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/AbstractValidateActionForm.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ActionCommandBase.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ActionCommand.html"><strong>FRAMES</strong></a>    <a href="ActionCommand.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
