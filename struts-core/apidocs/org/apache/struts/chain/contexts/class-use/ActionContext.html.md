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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md" title="interface in org.apache.struts.chain.contexts"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/contexts//class-useActionContext.html"><strong>FRAMES</strong></a>    <a href="ActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.chain.contexts.ActionContext**
-------------------------------------------------

Packages that use [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

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

 

<span id="org.apache.struts.chain"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.chain](../../../../../../org/apache/struts/chain/package-summary.html)

 

Methods in [org.apache.struts.chain](../../../../../../org/apache/struts/chain/package-summary.html.md) that return [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

`protected  ActionContext`

`ComposableRequestProcessor.contextInstance(HttpServletRequest request, HttpServletResponse response)`
           Provide the initialized `ActionContext` instance which will be used by this request.

`protected  ActionContext`

`ComposableRequestProcessor.createActionContextInstance(ServletContext servletContext, HttpServletRequest request, HttpServletResponse response)`
           Create a new instance of `ActionContext` according to configuration.

 

Methods in [org.apache.struts.chain](../../../../../../org/apache/struts/chain/package-summary.html.md) with parameters of type [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

`protected  void`

`ComposableRequestProcessor.initializeActionContext(ActionContext context)`
           Set common properties on the given `ActionContext` instance so that commands in the chain can count on their presence.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.chain.commands](../../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

` boolean`

`SelectInclude.execute(ActionContext actionCtx)`
           Select and cache the include uri for this `ActionConfig` if specified.

` boolean`

`RemoveCachedMessages.execute(ActionContext actionCtx)`
           Removes any `ActionMessages` object stored in the session under `Globals.MESSAGE_KEY` and `Globals.ERROR_KEY` if the messages' `isAccessed` method returns true.

` boolean`

`ExecuteCommand.execute(ActionContext actionCtx)`
           If the `context` is "valid", lookup a command and execute it.

` boolean`

`ExceptionCatcher.execute(ActionContext actionCtx)`
           Clear any existing stored exception and pass the `context` on to the remainder of the current chain.

` boolean`

`CreateActionForm.execute(ActionContext actionCtx)`
           Create (if necessary) and cache a form bean for this request.

`abstract  boolean`

`ActionCommandBase.execute(ActionContext actionContext)`
            

` boolean`

`ActionCommand.execute(ActionContext actionContext)`
            

` boolean`

`AbstractValidateActionForm.execute(ActionContext actionCtx)`
           Validate the properties of the form bean for this request.

` boolean`

`AbstractSetOriginalURI.execute(ActionContext actionCtx)`
           Check to original uri is set, and if not, set it for this request.

` boolean`

`AbstractSetContentType.execute(ActionContext actionCtx)`
           Check to see if the content type is set, and if so, set it for this response.

` boolean`

`AbstractSelectModule.execute(ActionContext actionCtx)`
           Cache the `ModuleConfig` and `MessageResources` instances for the sub-application module to be used for processing this request.

` boolean`

`AbstractSelectLocale.execute(ActionContext actionCtx)`
           Select the `Locale` to be used for this request.

` boolean`

`AbstractSelectInput.execute(ActionContext actionCtx)`
           Select and cache a `ForwardConfig` for the input page for the current request.

` boolean`

`AbstractSelectForward.execute(ActionContext actionCtx)`
           Select and cache the `ActionForward` for this `ActionConfig` if specified.

` boolean`

`AbstractSelectAction.execute(ActionContext actionCtx)`
           Cache the `ActionConfig` instance for the action to be used for processing this request.

` boolean`

`AbstractRequestNoCache.execute(ActionContext actionCtx)`
           Check to see if the controller is configured to prevent caching, and if so, request no cache flags to be set.

` boolean`

`AbstractPopulateActionForm.execute(ActionContext actionCtx)`
           Populate the form bean (if any) for this request.

` boolean`

`AbstractPerformInclude.execute(ActionContext actionCtx)`
           Perform an include based on the specified include uri (if any).

` boolean`

`AbstractPerformForward.execute(ActionContext actionCtx)`
           Perform forwarding or redirection based on the specified `ActionForward` (if any).

` boolean`

`AbstractExecuteAction.execute(ActionContext actionCtx)`
           Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

` boolean`

`AbstractExceptionHandler.execute(ActionContext actionCtx)`
           Invoke the appropriate `Action` for this request, and cache the returned `ActionForward`.

` boolean`

`AbstractCreateAction.execute(ActionContext actionCtx)`
           Create (if necessary) and cache an `Action` for this request.

` boolean`

`AbstractAuthorizeAction.execute(ActionContext actionCtx)`
           Determine whether the requested action is authorized for the current user.

`protected abstract  ForwardConfig`

`AbstractExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ForwardConfig`.

`protected abstract  ForwardConfig`

`AbstractSelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  ForwardConfig`

`AbstractSelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  Action`

`AbstractCreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            Create and return the appropriate `Action` class for the given `type` and `actionConfig`.

`protected  org.apache.commons.chain.Command`

`ExecuteForwardCommand.getCommand(ActionContext context)`
           Return the command specified by the `command` and `catalog` properties of the `forwardConfig` property of the given `ActionContext`.

`protected  org.apache.commons.chain.Command`

`ExecuteCommand.getCommand(ActionContext context)`
           Find the `ActionConfig` in the current context and, if it is properly configured, lookup the appropriate `commons-chain` command.

`protected abstract  String`

`AbstractAuthorizeAction.getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            Retrieve error message from context.

`protected abstract  Locale`

`AbstractSelectLocale.getLocale(ActionContext context)`
           Return the `Locale` to be used for this request.

`protected abstract  String`

`AbstractSelectAction.getPath(ActionContext context)`
           Return the path to be used to select the `ActionConfig` for this request.

`protected abstract  String`

`AbstractSelectModule.getPrefix(ActionContext context)`
           Calculate and return the module prefix for the module to be selected for this request.

`protected abstract  ForwardConfig`

`AbstractExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

`protected  void`

`AbstractPopulateActionForm.handleCancel(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Take into account whether the request includes any defined value for the global "cancel" parameter.

`protected  String`

`AbstractPerformInclude.includePath(ActionContext actionContext, String include)`
           Returns the path to perform the include.

`protected abstract  boolean`

`AbstractAuthorizeAction.isAuthorized(ActionContext context, String[] roles, ActionConfig actionConfig)`
           Determine if the action is authorized for the given roles.

`protected abstract  void`

`AbstractPerformForward.perform(ActionContext context, ForwardConfig forwardConfig)`
           Perform the appropriate processing on the specified `ForwardConfig`.

`protected abstract  void`

`AbstractPerformInclude.perform(ActionContext context, String include)`
           Perform the appropriate processing on the specified include uri.

`protected abstract  void`

`AbstractPopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            Populate the given `ActionForm` with request parameter values, taking into account any prefix/suffix values configured on the given `ActionConfig`.

`protected abstract  void`

`AbstractRequestNoCache.requestNoCache(ActionContext context)`
           Request no cache flags are set.

`protected abstract  void`

`AbstractPopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `reset()` method on the specified form bean.

`protected abstract  void`

`AbstractSetContentType.setContentType(ActionContext context, String contentType)`
           Request no cache flags are set.

`protected abstract  void`

`AbstractSetOriginalURI.setOriginalURI(ActionContext context)`
           Set the original uri.

`protected  boolean`

`ExecuteForwardCommand.shouldProcess(ActionContext context)`
            Determine whether the forwardConfig should be processed.

`protected  boolean`

`ExecuteCommand.shouldProcess(ActionContext context)`
           Evaluate the current context to see if a command should even be executed.

`protected abstract  ActionErrors`

`AbstractValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.commands.generic"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.chain.commands.generic](../../../../../../org/apache/struts/chain/commands/generic/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.generic](../../../../../../org/apache/struts/chain/commands/generic/package-summary.html.md) with parameters of type [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

` boolean`

`CopyFormToContext.execute(ActionContext actionContext)`
           Look up an ActionForm instance based on the configured properties of this command and copy it into the `Context`.

`protected  ActionForm`

`CopyFormToContext.findOrCreateForm(ActionContext context)`
           Based on the properties of this command and the given `ActionContext`, find or create an ActionForm instance for preparation.

`protected  ActionForm`

`CopyFormToContext.findOrCreateForm(ActionContext ctx, String effectiveFormName, String effectiveScope)`
           Actually find or create an instance of ActionForm configured under the form-bean-name `effectiveFormName`, looking in in the `ActionContext's` scope as identified by `effectiveScope`.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.chain.commands.servlet](../../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

`protected  Action`

`CreateAction.createAction(ActionContext context, String type)`
           Invoked by `getAction` when the `Action` actually has to be created.

`protected  ForwardConfig`

`ExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ActionForward`.

`protected  ForwardConfig`

`SelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  ForwardConfig`

`SelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  Action`

`CreateAction.getAction(ActionContext context, String type, ActionConfig actionConfig)`
            

`protected  String`

`AuthorizeAction.getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            

`protected  Locale`

`SelectLocale.getLocale(ActionContext context)`
           Return the `Locale` to be used for this request.

`protected  String`

`SelectAction.getPath(ActionContext context)`
            

`protected  String`

`SelectModule.getPrefix(ActionContext context)`
            

`protected  ForwardConfig`

`ExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
            

`protected  String`

`PerformInclude.includePath(ActionContext actionContext, String include)`
            

`protected  boolean`

`AuthorizeAction.isAuthorized(ActionContext context, String[] roles, ActionConfig mapping)`
            

`protected  void`

`PerformForward.perform(ActionContext context, ForwardConfig forwardConfig)`
           Perform the appropriate processing on the specified `ForwardConfig`.

`protected  void`

`PerformInclude.perform(ActionContext context, String uri)`
           Perform the appropriate processing on the specified include uri.

`protected  void`

`PopulateActionForm.populate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  void`

`RequestNoCache.requestNoCache(ActionContext context)`
            

`protected  void`

`PopulateActionForm.reset(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
            

`protected  void`

`SetContentType.setContentType(ActionContext context, String contentType)`
            

`protected  void`

`SetOriginalURI.setOriginalURI(ActionContext context)`
            

`protected  ActionErrors`

`ValidateActionForm.validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.chain.contexts](../../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Classes in [org.apache.struts.chain.contexts](../../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that implement [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

` class`

`ActionContextBase`
            Provide an abstract but semi-complete implementation of ActionContext to serve as the base for concrete implementations.

` class`

`MockActionContext`
            Implement `ActionContext` with empty maps for `applicationScope`, `sessionScope`, `requestScope`, and `parameterMap` properties.

` class`

`ServletActionContext`
            Implement ActionContext interface while making Servlet API-specific values available.

` class`

`WebActionContext`
            Provide a Subclass of ActionContextBase which is understood to be wrapping an instance of `org.apache.commons.chain.web.WebContext`.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts") in [org.apache.struts.config](../../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionContext](../../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

` ActionForm`

`FormBeanConfig.createActionForm(ActionContext context)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/chain/contexts/ActionContext.html.md" title="interface in org.apache.struts.chain.contexts"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/contexts//class-useActionContext.html"><strong>FRAMES</strong></a>    <a href="ActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
