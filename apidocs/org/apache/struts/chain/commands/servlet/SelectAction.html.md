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
<td align="left"><a href="class-use/SelectAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/RequestNoCache.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/SelectForward.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/SelectAction.html"><strong>FRAMES</strong></a>    <a href="SelectAction.html"><strong>NO FRAMES</strong></a>    
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
 Class SelectAction
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractSelectAction
              org.apache.struts.chain.commands.servlet.SelectAction

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class SelectAction

extends [AbstractSelectAction](../../../../../../org/apache/struts/chain/commands/AbstractSelectAction.html.md "class in org.apache.struts.chain.commands")

Cache the `ActionConfig` instance for the action to be used for processing this request.

**Version:**  
$Rev: 508312 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

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
| ` SelectAction()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  String`

` getPath(ActionContext context)`
           Return the path to be used to select the `ActionConfig` for this request.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.AbstractSelectAction"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[AbstractSelectAction](../../../../../../org/apache/struts/chain/commands/AbstractSelectAction.html.md "class in org.apache.struts.chain.commands")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                         |

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

### SelectAction

    public SelectAction()

<span id="method_detail"></span>

**Method Detail**

### getPath

    protected String getPath(ActionContext context)

**Description copied from class: ` AbstractSelectAction`**

Return the path to be used to select the `ActionConfig` for this request.

**Specified by:**  
` getPath` in class `AbstractSelectAction`

<!-- -->

**Parameters:**  
`context` - The `Context` for this request

**Returns:**  
Path to be used to select the ActionConfig

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
<td align="left"><a href="class-use/SelectAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/RequestNoCache.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/SelectForward.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/SelectAction.html"><strong>FRAMES</strong></a>    <a href="SelectAction.html"><strong>NO FRAMES</strong></a>    
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