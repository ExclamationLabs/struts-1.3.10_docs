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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionForward**
-----------------------------------------

Packages that use [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.actions**](#org.apache.struts.actions)

The actions package provides special adapters between the incoming HTTP request and the corresponding business logic. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.faces.application**](#org.apache.struts.faces.application)

  

[**org.apache.struts.scripting**](#org.apache.struts.scripting)

The scripting package is the core of the Struts Scripting framework, which builds on Struts Action to allow Struts Actions be written with the scripting language of your choice. 

[**org.apache.struts.tiles.actions**](#org.apache.struts.tiles.actions)

  

 

<span id="org.apache.struts.action"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionRedirect`
            A subclass of [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.

` class`

`ForwardingActionForward`
           A subclass of `ActionForward` that defaults the `redirect` attribute to `false`.

` class`

`RedirectingActionForward`
           A subclass of **ActionForward** that defaults the `redirect` attribute to `true`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, ServletRequest request, ServletResponse response)`
           Process the specified non-HTTP request, and create the corresponding non-HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`ExceptionHandler.execute(Exception ex, ExceptionConfig ae, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response)`
            Handle the Exception.

` ActionForward`

`ActionMapping.findForward(String forwardName)`
           Find and return the `ForwardConfig` instance defining how forwarding to the specified logical name should be handled.

` ActionForward`

`ActionMapping.getInputForward()`
           Create (if necessary) and return an [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") that corresponds to the `input` property of this Action.

`protected  ActionForward`

`RequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  ActionForward`

`RequestProcessor.processException(HttpServletRequest request, HttpServletResponse response, Exception exception, ActionForm form, ActionMapping mapping)`
           Ask our exception handler to handle the exception.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

`protected  String`

`ExceptionHandler.determineIncludePath(ExceptionConfig config, ActionForward actionForward)`
           Return a path to which an include should be attempted in the case when the response was committed before the `ExceptionHandler` was invoked.

`protected  void`

`ExceptionHandler.handleCommittedResponse(Exception ex, ExceptionConfig config, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response, ActionForward actionForward)`
           Attempt to give good information when the response has already been committed when the exception was thrown.

`protected  void`

`ExceptionHandler.storeException(HttpServletRequest request, String property, ActionMessage error, ActionForward forward, String scope)`
           Default implementation for handling an `ActionMessage` generated from an `Exception` during `Action` delegation.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionForward(ActionForward copyMe)`                                                                                                                                                                                                           
            Construct a new instance based on the values of another ActionForward.                                                                                                                                                                 |

 

<span id="org.apache.struts.actions"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html)

 

Methods in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

`protected  ActionForward`

`DispatchAction.cancelled(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when the request is a cancel button submit.

`protected  ActionForward`

`ActionDispatcher.cancelled(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' cancelled method, if present, otherwise returns null.

`protected  ActionForward`

`DispatchAction.dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name)`
           Dispatch to the specified method.

`protected  ActionForward`

`ActionDispatcher.dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name)`
           Dispatch to the specified method.

`protected  ActionForward`

`ActionDispatcher.dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name, Method method)`
           Dispatch to the specified method.

` ActionForward`

`SwitchAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`MappingDispatchAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`LookupDispatchAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`LocaleAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Change the user's [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") based on [`ActionForm`](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action") properties.

` ActionForward`

`IncludeAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`ForwardAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`DownloadAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`DispatchAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

` ActionForward`

`ActionDispatcher.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

`protected  ActionForward`

`MappingDispatchAction.unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when there is no value for the parameter in the ActionMapping.

`protected  ActionForward`

`EventDispatchAction.unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when there is no value for specified request parameter included in the request.

`protected  ActionForward`

`EventActionDispatcher.unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

`protected  ActionForward`

`DispatchAction.unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when there is no value for specified request parameter included in the request.

`protected  ActionForward`

`ActionDispatcher.unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`ConfigHelperInterface.getActionForward(String name)`
            Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

` ActionForward`

`ConfigHelper.getActionForward(String name)`
            Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` void`

`ConfigHelper.setForward(ActionForward forward)`
           Set the forward associated with this instance.

 

<span id="org.apache.struts.faces.application"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html)

 

Methods in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

`protected  ActionForward`

`FacesTilesRequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
            

`protected  ActionForward`

`FacesRequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
            

 

<span id="org.apache.struts.scripting"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.scripting](../../../../../org/apache/struts/scripting/package-summary.html)

 

Methods in [org.apache.struts.scripting](../../../../../org/apache/struts/scripting/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`ScriptAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Executes the script.

` ActionForward`

`StrutsInfo.getForward()`
           Gets the forward object.

 

Methods in [org.apache.struts.scripting](../../../../../org/apache/struts/scripting/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` void`

`StrutsInfo.setForward(ActionForward f)`
           Sets the action forward object.

 

<span id="org.apache.struts.tiles.actions"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.tiles.actions](../../../../../org/apache/struts/tiles/actions/package-summary.html)

 

Methods in [org.apache.struts.tiles.actions](../../../../../org/apache/struts/tiles/actions/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`ViewDefinitionsAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`TilesAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Original Struts Action's method.

` ActionForward`

`ReloadDefinitionsAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`DefinitionDispatcherAction.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`TilesAction.execute(ComponentContext context, ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

 

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
