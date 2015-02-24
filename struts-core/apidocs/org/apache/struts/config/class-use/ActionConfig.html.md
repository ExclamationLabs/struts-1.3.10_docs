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
<td align="left"><a href="../../../../../org/apache/struts/config/ActionConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useActionConfig.html"><strong>FRAMES</strong></a>    <a href="ActionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.ActionConfig**
----------------------------------------

Packages that use [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionMapping`
           An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.

` class`

`RequestActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `request`.

` class`

`SessionActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `session`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`protected  ActionConfig`

`ActionServlet.processActionConfigClass(ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Checks if the current actionConfig is using the correct class based on the class of its ancestor ActionConfig.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`protected  ActionConfig`

`ActionServlet.processActionConfigClass(ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Checks if the current actionConfig is using the correct class based on the class of its ancestor ActionConfig.

`protected  void`

`ActionServlet.processActionConfigExtension(ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Extend the action's configuration as necessary.

`protected  ExceptionConfig`

`ActionServlet.processExceptionConfigClass(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current exceptionConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

`ActionServlet.processExceptionExtension(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the exception's configuration as necessary.

`protected  ForwardConfig`

`ActionServlet.processForwardConfigClass(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

`ActionServlet.processForwardExtension(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the forward's configuration as necessary.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`protected abstract  ForwardConfig`

`AbstractExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ForwardConfig`.

`protected abstract  Action`

`AbstractCreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            Create and return the appropriate `Action` class for the given `type` and `actionConfig`.

`protected abstract  String`

`AbstractAuthorizeAction.getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            Retrieve error message from context.

`protected abstract  ForwardConfig`

`AbstractExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

`protected  void`

`AbstractPopulateActionForm.handleCancel(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Take into account whether the request includes any defined value for the global "cancel" parameter.

`protected  boolean`

`AbstractAuthorizeAction.isAuthorizationRequired(ActionConfig actionConfig)`
           Must authorization rules be consulted? The base implementation returns `true` if the given `ActionConfig` has one or more roles defined.

`protected abstract  boolean`

`AbstractAuthorizeAction.isAuthorized(ActionContext context, String[] roles, ActionConfig actionConfig)`
           Determine if the action is authorized for the given roles.

`protected abstract  void`

`AbstractPopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            Populate the given `ActionForm` with request parameter values, taking into account any prefix/suffix values configured on the given `ActionConfig`.

`protected abstract  void`

`AbstractPopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `reset()` method on the specified form bean.

`protected  String`

`AbstractPopulateActionForm.trimParameterName(ActionConfig actionConfig, String name)`
           For a given request parameter name, trim off any prefix and/or suffix which are defined in `actionConfig` and return what remains.

`protected abstract  ActionErrors`

`AbstractValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`protected  ForwardConfig`

`ExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ActionForward`.

`protected  Action`

`CreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            

`protected  String`

`AuthorizeAction.getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            

`protected  ForwardConfig`

`ExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
            

`protected  boolean`

`AuthorizeAction.isAuthorized(ActionContext context, String[] roles, ActionConfig mapping)`
            

`protected  void`

`PopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  void`

`PopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  ActionErrors`

`ValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

` ActionConfig`

`ActionContextBase.getActionConfig()`
            

` ActionConfig`

`ActionContext.getActionConfig()`
            Get the ActionConfig which contains the details for processing this request.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

` void`

`ServletActionContext.setActionConfig(ActionConfig actionConfig)`
            

` void`

`ActionContextBase.setActionConfig(ActionConfig config)`
            

` void`

`ActionContext.setActionConfig(ActionConfig config)`
            Set the ActionConfig class contains the details for processing this request.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`protected  ActionConfig`

`ActionConfigMatcher.convertActionConfig(String path, ActionConfig orig, Map vars)`
            Clones the ActionConfig and its children, replacing various properties with the values of the wildcard-matched strings.

` ActionConfig`

`ModuleConfig.findActionConfig(String path)`
            Return the action configuration for the specified path, if any; otherwise return `null`.

` ActionConfig`

`ModuleConfig.findActionConfigId(String actionId)`
           Returns the action configuration for the specifed action action identifier.

` ActionConfig[]`

`ModuleConfig.findActionConfigs()`
            Return the action configurations for this module.

` ActionConfig`

`ActionConfigMatcher.match(String path)`
            Matches the path against the compiled wildcard patterns.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addActionConfig(ActionConfig config)`
            Add a new `ActionConfig` instance to the set associated with this module.

`protected  boolean`

`ForwardConfig.checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

`protected  boolean`

`ExceptionConfig.checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

`protected  ActionConfig`

`ActionConfigMatcher.convertActionConfig(String path, ActionConfig orig, Map vars)`
            Clones the ActionConfig and its children, replacing various properties with the values of the wildcard-matched strings.

`protected  void`

`ActionConfig.inheritExceptionHandlers(ActionConfig baseConfig)`
           Compare the exception handlers of this action with that of the given and copy those that are not present.

`protected  void`

`ActionConfig.inheritForwards(ActionConfig baseConfig)`
           Compare the forwards of this action with that of the given and copy those that are not present.

` void`

`ActionConfig.inheritFrom(ActionConfig config)`
           Inherit values that have not been overridden from the provided config object.

` void`

`ForwardConfig.processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ForwardConfig that this instance is extending.

` void`

`ExceptionConfig.processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ExceptionConfig that this instance is extending.

` void`

`ModuleConfig.removeActionConfig(ActionConfig config)`
            Remove the specified action configuration instance.

 

| Constructors in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config") |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionConfigMatcher(ActionConfig[] configs)`                                                                                                                                                                                                 
             Finds and precompiles the wildcard patterns from the ActionConfig "path" attributes.                                                                                                                                                |

 

<span id="org.apache.struts.config.impl"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

` ActionConfig`

`ModuleConfigImpl.findActionConfig(String path)`
            Return the action configuration for the specified path, first looking a direct match, then if none found, a wildcard pattern match; otherwise return `null`.

` ActionConfig`

`ModuleConfigImpl.findActionConfigId(String actionId)`
           Returns the action configuration for the specifed action action identifier.

` ActionConfig[]`

`ModuleConfigImpl.findActionConfigs()`
            Return the action configurations for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addActionConfig(ActionConfig config)`
            Ad d a new `ActionConfig` instance to the set associated with this module.

` void`

`ModuleConfigImpl.removeActionConfig(ActionConfig config)`
            Remove the specified action configuration instance.

 

<span id="org.apache.struts.util"></span>

Uses of [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [ActionConfig](../../../../../org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config")

`static String`

`RequestUtils.actionURL(HttpServletRequest request, ActionConfig action, String pattern)`
           Return the context-relative URL that corresponds to the specified [`ActionConfig`](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config"), relative to the module associated with the current modules's [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config").

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/ActionConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useActionConfig.html"><strong>FRAMES</strong></a>    <a href="ActionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
