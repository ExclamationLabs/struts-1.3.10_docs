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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionErrors.html"><strong>FRAMES</strong></a>    <a href="ActionErrors.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionErrors**
----------------------------------------

Packages that use [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.scripting**](#org.apache.struts.scripting)

The scripting package is the core of the Struts Scripting framework, which builds on Struts Action to allow Struts Actions be written with the scripting language of your choice. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action")

` ActionErrors`

`ActionForm.validate(ActionMapping mapping, HttpServletRequest request)`
           Can be used to validate the properties that have been set for this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

` ActionErrors`

`ActionForm.validate(ActionMapping mapping, ServletRequest request)`
           Can be used to validate the properties that have been set for this non-HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action") |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionErrors(ActionErrors messages)`                                                                                                                                                                                                         
            Create an `ActionErrors` object initialized with the given messages.                                                                                                                                                                 |

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) that return [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action")

`protected abstract  ActionErrors`

`AbstractValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) that return [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action")

`protected  ActionErrors`

`ValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.scripting"></span>

Uses of [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") in [org.apache.struts.scripting](../../../../../org/apache/struts/scripting/package-summary.html)

 

Methods in [org.apache.struts.scripting](../../../../../org/apache/struts/scripting/package-summary.html.md) with parameters of type [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action")

` void`

`ScriptAction.saveErrors(HttpServletRequest req, ActionErrors errs)`
           **Deprecated.** *Use saveErrors(HttpServletRequest, ActionMessages) instead. This will be removed after Struts 1.2.*

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) that return [ActionErrors](../../../../../org/apache/struts/action/ActionErrors.html "class in org.apache.struts.action")

` ActionErrors`

`ValidatorForm.validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

` ActionErrors`

`DynaValidatorForm.validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

 

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionErrors.html"><strong>FRAMES</strong></a>    <a href="ActionErrors.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
