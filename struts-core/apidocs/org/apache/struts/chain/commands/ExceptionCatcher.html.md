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
<td align="left"><a href="class-use/ExceptionCatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/CreateActionForm.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ExecuteCommand.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ExceptionCatcher.html"><strong>FRAMES</strong></a>    <a href="ExceptionCatcher.html"><strong>NO FRAMES</strong></a>    
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
 Class ExceptionCatcher
--------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.ExceptionCatcher

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, org.apache.commons.chain.Filter, [ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class ExceptionCatcher

extends [ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")

implements org.apache.commons.chain.Filter

Intercept any exception thrown by a subsequent `Command` in this processing chain, and fire the configured exception handler chain after storing the exception that has occurred into the `Context`.

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005) $

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
| ` ExceptionCatcher()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(ActionContext actionCtx)`
           Clear any existing stored exception and pass the `context` on to the remainder of the current chain.

` String`

` getCatalogName()`
            Return the name of the `Catalog` in which to perform lookups, or `null` for the default `Catalog`.

` String`

` getExceptionCommand()`
            Return the name of the command to be executed if an exception occurs.

`protected  org.apache.commons.chain.Command`

` lookupExceptionCommand()`
            Return the command to be executed if an exception occurs.

` boolean`

` postprocess(org.apache.commons.chain.Context context, Exception exception)`
           If an exception was thrown by a subsequent `Command`, pass it on to the specified exception handling chain.

` void`

` setCatalogName(String catalogName)`
           Set the name of the `Catalog` in which to perform lookups, or `null` for the default `Catalog`.

` void`

` setExceptionCommand(String exceptionCommand)`
           Set the name of the command to be executed if an exception occurs.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.ActionCommandBase"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Methods inherited from interface org.apache.commons.chain.Command** |
|-----------------------------------------------------------------------|
| `execute`                                                             |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ExceptionCatcher

    public ExceptionCatcher()

<span id="method_detail"></span>

**Method Detail**

### getCatalogName

    public String getCatalogName()

Return the name of the `Catalog` in which to perform lookups, or `null` for the default `Catalog`.

**Returns:**  
Name of catalog to use, or null

------------------------------------------------------------------------

### setCatalogName

    public void setCatalogName(String catalogName)

Set the name of the `Catalog` in which to perform lookups, or `null` for the default `Catalog`.

**Parameters:**  
`catalogName` - The new catalog name or `null`

------------------------------------------------------------------------

### getExceptionCommand

    public String getExceptionCommand()

Return the name of the command to be executed if an exception occurs.

**Returns:**  
The name of the command to be executed on an exception

------------------------------------------------------------------------

### setExceptionCommand

    public void setExceptionCommand(String exceptionCommand)

Set the name of the command to be executed if an exception occurs.

**Parameters:**  
`exceptionCommand` - The name of the chain to be executed

------------------------------------------------------------------------

### execute

    public boolean execute(ActionContext actionCtx)
                    throws Exception

Clear any existing stored exception and pass the `context` on to the remainder of the current chain.

**Specified by:**  
` execute` in interface `ActionCommand`

**Specified by:**  
` execute` in class `ActionCommandBase`

<!-- -->

**Parameters:**  
`actionCtx` - The `Context` for the current request

**Returns:**  
`false` so that processing continues

**Throws:**  
`Exception` - On any error

------------------------------------------------------------------------

### postprocess

    public boolean postprocess(org.apache.commons.chain.Context context,
                               Exception exception)

If an exception was thrown by a subsequent `Command`, pass it on to the specified exception handling chain. Otherwise, do nothing.

**Specified by:**  
`postprocess` in interface `org.apache.commons.chain.Filter`

<!-- -->

**Parameters:**  
`context` - The `Context` to be processed by this `Filter`

`exception` - The `Exception` (if any) that was thrown by the last `Command` that was executed; otherwise `null`

**Returns:**  
TRUE if post processing an exception occurred and the exception processing chain invoked

**Throws:**  
`IllegalStateException` - If exception throws exception

------------------------------------------------------------------------

### lookupExceptionCommand

    protected org.apache.commons.chain.Command lookupExceptionCommand()

Return the command to be executed if an exception occurs.

**Returns:**  
The command to be executed if an exception occurs

**Throws:**  
`IllegalArgumentException` - If catalog cannot be found

`IllegalStateException` - If command property is not specified

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
<td align="left"><a href="class-use/ExceptionCatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/CreateActionForm.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ExecuteCommand.html" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/ExceptionCatcher.html"><strong>FRAMES</strong></a>    <a href="ExceptionCatcher.html"><strong>NO FRAMES</strong></a>    
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
