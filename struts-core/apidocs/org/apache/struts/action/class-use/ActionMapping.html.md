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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMapping.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMapping.html"><strong>FRAMES</strong></a>    <a href="ActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionMapping**
-----------------------------------------

Packages that use [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`RequestActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `request`.

` class`

`SessionActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `session`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

`protected  ActionMapping`

`RequestProcessor.processMapping(HttpServletRequest request, HttpServletResponse response, String path)`
           Select the mapping used to process the selection path for this request.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

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

` void`

`DynaActionForm.initialize(ActionMapping mapping)`
           Initialize all bean properties to their initial values, as specified in the [`FormPropertyConfig`](../../../../../org/apache/struts/config/FormPropertyConfig.html.md "class in org.apache.struts.config") elements associated with the definition of this `DynaActionForm`.

`protected  Action`

`RequestProcessor.processActionCreate(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

`protected  ActionForm`

`RequestProcessor.processActionForm(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary.

`protected  ActionForward`

`RequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  ActionForward`

`RequestProcessor.processException(HttpServletRequest request, HttpServletResponse response, Exception exception, ActionForm form, ActionMapping mapping)`
           Ask our exception handler to handle the exception.

`protected  boolean`

`RequestProcessor.processForward(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process a forward requested by this mapping (if any).

`protected  boolean`

`RequestProcessor.processInclude(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process an include requested by this mapping (if any).

`protected  void`

`RequestProcessor.processPopulate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           Populate the properties of the specified `ActionForm` instance from the request parameters included with this request.

`protected  boolean`

`RequestProcessor.processRoles(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           If this action is protected by security roles, make sure that the current user possesses at least one of them.

`protected  boolean`

`RequestProcessor.processValidate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           If this request was not cancelled, and the request's [`ActionMapping`](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors.

` void`

`DynaActionForm.reset(ActionMapping mapping, HttpServletRequest request)`
           Reset the properties to their `initial` value if their `reset` configuration is set to true or if `reset` is set to a list of HTTP request methods that includes the method of given `request` object.

` void`

`ActionForm.reset(ActionMapping mapping, HttpServletRequest request)`
           Can be used to reset bean properties to their default state, as needed.

` void`

`DynaActionForm.reset(ActionMapping mapping, ServletRequest request)`
           Reset bean properties to their default state, as needed.

` void`

`ActionForm.reset(ActionMapping mapping, ServletRequest request)`
           \>Can be used to reset all bean properties to their default state.

` ActionErrors`

`ActionForm.validate(ActionMapping mapping, HttpServletRequest request)`
           Can be used to validate the properties that have been set for this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

` ActionErrors`

`ActionForm.validate(ActionMapping mapping, ServletRequest request)`
           Can be used to validate the properties that have been set for this non-HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` ActionMapping`

`ConfigHelperInterface.getActionMapping(String path)`
            Return the mapping associated with the specified request path, if any; otherwise return `null`.

` ActionMapping`

`ConfigHelper.getActionMapping(String path)`
            Return the mapping associated with the specified request path, if any; otherwise return `null`.

` ActionMapping`

`ConfigHelperInterface.getMapping()`
            The `org.apache.struts.ActionMapping` instance for this request.

` ActionMapping`

`ConfigHelper.getMapping()`
            The `org.apache.struts.ActionMapping` instance for this request.

 

<span id="org.apache.struts.mock"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Methods in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) that return [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` ActionMapping`

`MockMultipartRequestHandler.getMapping()`
           Get the ActionMapping instance for this mock request.

 

Methods in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) with parameters of type [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` void`

`MockMultipartRequestHandler.setMapping(ActionMapping mapping)`
           Convienience method to set a reference to a mock ActionMapping instance.

 

<span id="org.apache.struts.upload"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html)

 

Methods in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) that return [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` ActionMapping`

`MultipartRequestHandler.getMapping()`
            Get the ActionMapping instance for this request

` ActionMapping`

`CommonsMultipartRequestHandler.getMapping()`
            Retrieves the action mapping with which this handler is associated.

 

Methods in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) with parameters of type [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` void`

`MultipartRequestHandler.setMapping(ActionMapping mapping)`
            Convienience method to set a reference to a working ActionMapping instance.

` void`

`CommonsMultipartRequestHandler.setMapping(ActionMapping mapping)`
            Sets the action mapping with which this handler is associated.

 

<span id="org.apache.struts.util"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

`static ActionForm`

`RequestUtils.createActionForm(HttpServletRequest request, ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet)`
           Create (if necessary) and return an `ActionForm` instance appropriate for this request.

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [ActionMapping](../../../../../org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action")

` String`

`ValidatorForm.getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key.

` String`

`DynaValidatorForm.getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key.

` String`

`BeanValidatorForm.getValidationKey(ActionMapping mapping, HttpServletRequest request)`
           Returns the Validation key

` void`

`ValidatorForm.reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

`DynaValidatorForm.reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMapping.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMapping.html"><strong>FRAMES</strong></a>    <a href="ActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
