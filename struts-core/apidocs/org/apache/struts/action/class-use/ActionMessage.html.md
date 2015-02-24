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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMessage.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMessage.html"><strong>FRAMES</strong></a>    <a href="ActionMessage.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionMessage**
-----------------------------------------

Packages that use [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html "class in org.apache.struts.action")

` void`

`ActionMessages.add(String property, ActionMessage message)`
           Add a message to the set of messages for the specified property.

`protected  void`

`ExceptionHandler.storeException(HttpServletRequest request, String property, ActionMessage error, ActionForward forward, String scope)`
           Default implementation for handling an `ActionMessage` generated from an `Exception` during `Action` delegation.

 

<span id="org.apache.struts.util"></span>

Uses of [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html.md "class in org.apache.struts.action") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Fields in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) declared as [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html "class in org.apache.struts.action")

`protected  ActionMessage`

`ModuleException.message`
           The ActionMessage associated with this exception.

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) that return [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html "class in org.apache.struts.action")

` ActionMessage`

`ModuleException.getActionMessage()`
           Returns the error associated with the exception.

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) that return [ActionMessage](../../../../../org/apache/struts/action/ActionMessage.html "class in org.apache.struts.action")

`static ActionMessage`

`Resources.getActionMessage(HttpServletRequest request, ValidatorAction va, Field field)`
           **Deprecated.** *Use getActionMessage(Validator, HttpServletRequest, ValidatorAction, Field) method instead*

`static ActionMessage`

`Resources.getActionMessage(Validator validator, HttpServletRequest request, ValidatorAction va, Field field)`
           Gets the `ActionMessage` based on the `ValidatorAction` message and the `Field`'s arg objects.

 

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMessage.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMessage.html"><strong>FRAMES</strong></a>    <a href="ActionMessage.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
