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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ExceptionHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/ExecuteAction.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/ExceptionHandler.html"><strong>FRAMES</strong></a>    <a href="ExceptionHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.commands.servlet
 Class ExceptionHandler
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractExceptionHandler
              org.apache.struts.chain.commands.servlet.ExceptionHandler

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class ExceptionHandler

extends [AbstractExceptionHandler](../../../../../../org/apache/struts/chain/commands/AbstractExceptionHandler.html.md "class in org.apache.struts.chain.commands")

Handle the specified exception.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

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
| ` ExceptionHandler()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  ForwardConfig`

` handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.AbstractExceptionHandler"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[AbstractExceptionHandler](../../../../../../org/apache/struts/chain/commands/AbstractExceptionHandler.html.md "class in org.apache.struts.chain.commands")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                                 |

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.ActionCommandBase"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ExceptionHandler

    public ExceptionHandler()

<span id="method_detail"></span>

**Method Detail**

### handle

    protected ForwardConfig handle(ActionContext context,
                                   Exception exception,
                                   ExceptionConfig exceptionConfig,
                                   ActionConfig actionConfig,
                                   ModuleConfig moduleConfig)
                            throws Exception

**Description copied from class: ` AbstractExceptionHandler`**

Perform the required handling of the specified exception.

**Specified by:**  
` handle` in class `AbstractExceptionHandler`

<!-- -->

**Parameters:**  
`context` - The `Context` for this request

`exception` - The exception being handled

`exceptionConfig` - The corresponding [`ExceptionConfig`](../../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config")

`actionConfig` - The [`ActionConfig`](../../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") for this request

`moduleConfig` - The [`ModuleConfig`](../../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") for this request

**Returns:**  
the `ForwardConfig` to be processed next (if any), or `null` if processing has been completed

**Throws:**  
`Exception` - if there are any problems handling the exception

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ExceptionHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/ExecuteAction.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/ExceptionHandler.html"><strong>FRAMES</strong></a>    <a href="ExceptionHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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