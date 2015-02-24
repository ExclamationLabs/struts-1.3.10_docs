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
<td align="left"><a href="class-use/ActionCommandBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/ActionCommand.html.md" title="interface in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/CreateActionForm.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ActionCommandBase.html"><strong>FRAMES</strong></a>    <a href="ActionCommandBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.commands
 Class ActionCommandBase
--------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

<!-- -->

**Direct Known Subclasses:**  
[AbstractAuthorizeAction](../../../../../org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md "class in org.apache.struts.chain.commands"), [AbstractCreateAction](../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html "class in org.apache.struts.chain.commands"), [AbstractExceptionHandler](../../../../../org/apache/struts/chain/commands/AbstractExceptionHandler.html "class in org.apache.struts.chain.commands"), [AbstractExecuteAction](../../../../../org/apache/struts/chain/commands/AbstractExecuteAction.html "class in org.apache.struts.chain.commands"), [AbstractPerformForward](../../../../../org/apache/struts/chain/commands/AbstractPerformForward.html "class in org.apache.struts.chain.commands"), [AbstractPerformInclude](../../../../../org/apache/struts/chain/commands/AbstractPerformInclude.html "class in org.apache.struts.chain.commands"), [AbstractPopulateActionForm](../../../../../org/apache/struts/chain/commands/AbstractPopulateActionForm.html "class in org.apache.struts.chain.commands"), [AbstractRequestNoCache](../../../../../org/apache/struts/chain/commands/AbstractRequestNoCache.html "class in org.apache.struts.chain.commands"), [AbstractSelectAction](../../../../../org/apache/struts/chain/commands/AbstractSelectAction.html "class in org.apache.struts.chain.commands"), [AbstractSelectForward](../../../../../org/apache/struts/chain/commands/AbstractSelectForward.html "class in org.apache.struts.chain.commands"), [AbstractSelectInput](../../../../../org/apache/struts/chain/commands/AbstractSelectInput.html "class in org.apache.struts.chain.commands"), [AbstractSelectLocale](../../../../../org/apache/struts/chain/commands/AbstractSelectLocale.html "class in org.apache.struts.chain.commands"), [AbstractSelectModule](../../../../../org/apache/struts/chain/commands/AbstractSelectModule.html "class in org.apache.struts.chain.commands"), [AbstractSetContentType](../../../../../org/apache/struts/chain/commands/AbstractSetContentType.html "class in org.apache.struts.chain.commands"), [AbstractSetOriginalURI](../../../../../org/apache/struts/chain/commands/AbstractSetOriginalURI.html "class in org.apache.struts.chain.commands"), [AbstractValidateActionForm](../../../../../org/apache/struts/chain/commands/AbstractValidateActionForm.html "class in org.apache.struts.chain.commands"), [CopyFormToContext](../../../../../org/apache/struts/chain/commands/generic/CopyFormToContext.html "class in org.apache.struts.chain.commands.generic"), [CreateActionForm](../../../../../org/apache/struts/chain/commands/CreateActionForm.html "class in org.apache.struts.chain.commands"), [ExceptionCatcher](../../../../../org/apache/struts/chain/commands/ExceptionCatcher.html "class in org.apache.struts.chain.commands"), [ExecuteCommand](../../../../../org/apache/struts/chain/commands/ExecuteCommand.html "class in org.apache.struts.chain.commands"), [RemoveCachedMessages](../../../../../org/apache/struts/chain/commands/RemoveCachedMessages.html "class in org.apache.struts.chain.commands"), [SelectInclude](../../../../../org/apache/struts/chain/commands/SelectInclude.html "class in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public abstract class ActionCommandBase

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

Simple abstract class which avoids frequent casting to `ActionContext` in commands explicitly intended for use with that class.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ActionCommandBase()`  
                          |

  <span id="method_summary"></span>

**Method Summary**

`abstract  boolean`

` execute(ActionContext actionContext)`
            

` boolean`

` execute(org.apache.commons.chain.Context context)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionCommandBase

    public ActionCommandBase()

<span id="method_detail"></span>

**Method Detail**

### execute

    public abstract boolean execute(ActionContext actionContext)
                             throws Exception

**Specified by:**  
` execute` in interface `ActionCommand`

<!-- -->

**Parameters:**  
`actionContext` - The `Context` for the current request

**Returns:**  
TRUE if processing should halt

**Throws:**  
`Exception` - On any error

------------------------------------------------------------------------

### execute

    public boolean execute(org.apache.commons.chain.Context context)
                    throws Exception

**Specified by:**  
`execute` in interface `org.apache.commons.chain.Command`

<!-- -->

**Throws:**  
`Exception`

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
<td align="left"><a href="class-use/ActionCommandBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/ActionCommand.html.md" title="interface in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/CreateActionForm.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ActionCommandBase.html"><strong>FRAMES</strong></a>    <a href="ActionCommandBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
