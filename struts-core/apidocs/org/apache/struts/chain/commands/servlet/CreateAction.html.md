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
<td align="left"><a href="class-use/CreateAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/AuthorizeAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/ExceptionHandler.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/CreateAction.html"><strong>FRAMES</strong></a>    <a href="CreateAction.html"><strong>NO FRAMES</strong></a>    
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
 Class CreateAction
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractCreateAction
              org.apache.struts.chain.commands.servlet.CreateAction

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class CreateAction

extends [AbstractCreateAction](../../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html.md "class in org.apache.struts.chain.commands")

Concrete implementation of `AbstractCreateAction` for use in a Servlet API chain. Expects that the ActionContext passed into it can safely be cast to `ServletActionContext`.

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
| ` CreateAction()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  Action`

` createAction(ActionContext context, String type)`
           Invoked by `getAction` when the `Action` actually has to be created.

`protected  Action`

` getAction(ActionContext context, String type, ActionConfig actionConfig)`
            Create and return the appropriate `Action` class for the given `type` and `actionConfig`.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.AbstractCreateAction"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[AbstractCreateAction](../../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html.md "class in org.apache.struts.chain.commands")** |
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

### CreateAction

    public CreateAction()

<span id="method_detail"></span>

**Method Detail**

### getAction

    protected Action getAction(ActionContext context,
                               String type,
                               ActionConfig actionConfig)
                        throws Exception

**Description copied from class: ` AbstractCreateAction`**

Create and return the appropriate `Action` class for the given `type` and `actionConfig`.

NOTE: The dependence on ActionServlet suggests that this should be broken up along the lines of the other Abstract/concrete pairs in the org.apache.struts.chain.commands package.

**Specified by:**  
` getAction` in class `AbstractCreateAction`

<!-- -->

**Parameters:**  
`context` - The `Context` for this request

`type` - Name of class to instantiate

`actionConfig` - The [`ActionConfig`](../../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") for this request

**Returns:**  
Instantiated Action class

**Throws:**  
`Exception` - if there are any problems instantiating the Action class.

------------------------------------------------------------------------

### createAction

    protected Action createAction(ActionContext context,
                                  String type)
                           throws Exception

Invoked by `getAction` when the `Action` actually has to be created. If the instance is already created and cached, this method will not be called.

**Parameters:**  
`context` - The `Context` for this request

`type` - Name of class to instantiate

**Returns:**  
Instantiated Action class

**Throws:**  
`Exception` - if there are any problems instantiating the Action class.

**Since:**  
Struts 1.3.7

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
<td align="left"><a href="class-use/CreateAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/servlet/AuthorizeAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/chain/commands/servlet/ExceptionHandler.html" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/CreateAction.html"><strong>FRAMES</strong></a>    <a href="CreateAction.html"><strong>NO FRAMES</strong></a>    
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
