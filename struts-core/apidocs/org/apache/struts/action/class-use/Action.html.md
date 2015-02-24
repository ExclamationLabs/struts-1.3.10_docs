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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/Action.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useAction.html"><strong>FRAMES</strong></a>    <a href="Action.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.Action**
----------------------------------

Packages that use [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

 

<span id="org.apache.struts.action"></span>

Uses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected  Action`

`RequestProcessor.processActionCreate(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected  ActionForward`

`RequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) that return [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected abstract  Action`

`AbstractCreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            Create and return the appropriate `Action` class for the given `type` and `actionConfig`.

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected abstract  ForwardConfig`

`AbstractExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ForwardConfig`.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) that return [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected  Action`

`CreateAction.createAction(ActionContext context, String type)`
           Invoked by `getAction` when the `Action` actually has to be created.

`protected  Action`

`CreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

`protected  ForwardConfig`

`ExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ActionForward`.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

` Action`

`ActionContextBase.getAction()`
            

` Action`

`ActionContext.getAction()`
            Get the action which has been identified to be executed as part of processing this request.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [Action](../../../../../org/apache/struts/action/Action.html "class in org.apache.struts.action")

` void`

`ActionContextBase.setAction(Action action)`
            

` void`

`ActionContext.setAction(Action action)`
            Set the action which has been identified to be executed as part of processing this request.

 

<span id="org.apache.struts.mock"></span>

Uses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Subclasses of [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

` class`

`MockAction`
           General purpose Action for unit tests.

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/Action.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useAction.html"><strong>FRAMES</strong></a>    <a href="Action.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
