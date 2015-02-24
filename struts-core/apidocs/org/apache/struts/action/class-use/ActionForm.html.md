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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForm.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForm.html"><strong>FRAMES</strong></a>    <a href="ActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionForm**
--------------------------------------

Packages that use [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.generic**](#org.apache.struts.chain.commands.generic)

Contains generic commands. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`DynaActionForm`
           Specialized subclass of `ActionForm` that allows the creation of form beans with dynamic sets of properties, without requiring the developer to create a Java class for each type of form bean.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

`protected  ActionForm`

`RequestProcessor.processActionForm(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, ServletRequest request, ServletResponse response)`
           Process the specified non-HTTP request, and create the corresponding non-HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`ExceptionHandler.execute(Exception ex, ExceptionConfig ae, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response)`
            Handle the Exception.

`protected  void`

`ExceptionHandler.handleCommittedResponse(Exception ex, ExceptionConfig config, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response, ActionForward actionForward)`
           Attempt to give good information when the response has already been committed when the exception was thrown.

`protected  ActionForward`

`RequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  ActionForward`

`RequestProcessor.processException(HttpServletRequest request, HttpServletResponse response, Exception exception, ActionForm form, ActionMapping mapping)`
           Ask our exception handler to handle the exception.

`protected  void`

`RequestProcessor.processPopulate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           Populate the properties of the specified `ActionForm` instance from the request parameters included with this request.

`protected  boolean`

`RequestProcessor.processValidate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           If this request was not cancelled, and the request's [`ActionMapping`](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

`protected abstract  ForwardConfig`

`AbstractExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ForwardConfig`.

`protected  void`

`AbstractPopulateActionForm.handleCancel(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Take into account whether the request includes any defined value for the global "cancel" parameter.

`protected abstract  void`

`AbstractPopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            Populate the given `ActionForm` with request parameter values, taking into account any prefix/suffix values configured on the given `ActionConfig`.

`protected abstract  void`

`AbstractPopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `reset()` method on the specified form bean.

`protected abstract  ActionErrors`

`AbstractValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.commands.generic"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands.generic](../../../../../org/apache/struts/chain/commands/generic/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.generic](../../../../../org/apache/struts/chain/commands/generic/package-summary.html.md) that return [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

`protected  ActionForm`

`CopyFormToContext.findOrCreateForm(ActionContext context)`
           Based on the properties of this command and the given `ActionContext`, find or create an ActionForm instance for preparation.

`protected  ActionForm`

`CopyFormToContext.findOrCreateForm(ActionContext ctx, String effectiveFormName, String effectiveScope)`
           Actually find or create an instance of ActionForm configured under the form-bean-name `effectiveFormName`, looking in in the `ActionContext's` scope as identified by `effectiveScope`.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

`protected  ForwardConfig`

`ExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ActionForward`.

`protected  void`

`PopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  void`

`PopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  ActionErrors`

`ValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

` ActionForm`

`ActionContextBase.findOrCreateActionForm(String formName, String scopeName)`
            Using this `ActionContext`'s default `ModuleConfig`, return an existing `ActionForm` in the specified scope, or create a new one and add it to the specified scope.

` ActionForm`

`ActionContextBase.findOrCreateActionForm(String formName, String scopeName, ModuleConfig moduleConfig)`
            In the context of the given `ModuleConfig` and this `ActionContext`, look for an existing `ActionForm` in the specified scope.

` ActionForm`

`ActionContextBase.getActionForm()`
            

` ActionForm`

`ActionContext.getActionForm()`
            Get the ActionForm instance which will carry any data submitted as part of this request.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

` void`

`ActionContextBase.setActionForm(ActionForm form)`
            

` void`

`ActionContext.setActionForm(ActionForm form)`
            Set the ActionForm instance which will carry any data submitted as part of this request.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

` ActionForm`

`FormBeanConfig.createActionForm(ActionContext context)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

` ActionForm`

`FormBeanConfig.createActionForm(ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

` ActionForm`

`ConfigHelperInterface.getActionForm()`
            Retrieve and return the `ActionForm` bean associated with this mapping, creating and stashing one if necessary.

` ActionForm`

`ConfigHelper.getActionForm()`
            

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

` boolean`

`FormBeanConfig.canReuse(ActionForm form)`
           Checks if the given `ActionForm` instance is suitable for use as an alternative to calling this `FormBeanConfig` instance's `createActionForm` method.

 

<span id="org.apache.struts.mock"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Subclasses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

` class`

`MockFormBean`
           General purpose form bean for unit tests.

 

<span id="org.apache.struts.util"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) that return [ActionForm](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action")

`static ActionForm`

`RequestUtils.createActionForm(FormBeanConfig config, ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in `config`.

`static ActionForm`

`RequestUtils.createActionForm(HttpServletRequest request, ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet)`
           Create (if necessary) and return an `ActionForm` instance appropriate for this request.

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Subclasses of [ActionForm](../../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

` class`

`BeanValidatorForm`
           Struts *validator* `ActionForm` backed by either a `DynaBean` or POJO JavaBean.

` class`

`DynaValidatorForm`
           This class extends **DynaActionForm** and provides basic field validation based on an XML file.

` class`

`LazyValidatorForm`
           Struts *Lazy* `ActionForm` which *wraps* a `LazyDynaBean`.

` class`

`ValidatorForm`
           This class extends **ActionForm** and provides basic field validation based on an XML file.

 

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForm.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForm.html"><strong>FRAMES</strong></a>    <a href="ActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
