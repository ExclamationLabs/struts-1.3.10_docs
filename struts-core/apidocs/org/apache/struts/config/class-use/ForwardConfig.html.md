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
<td align="left"><a href="../../../../../org/apache/struts/config/ForwardConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useForwardConfig.html"><strong>FRAMES</strong></a>    <a href="ForwardConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.ForwardConfig**
-----------------------------------------

Packages that use [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")

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

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionForward`
           An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.

` class`

`ActionRedirect`
            A subclass of [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.

` class`

`ForwardingActionForward`
           A subclass of `ActionForward` that defaults the `redirect` attribute to `false`.

` class`

`RedirectingActionForward`
           A subclass of **ActionForward** that defaults the `redirect` attribute to `true`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected  ForwardConfig`

`ActionServlet.processForwardConfigClass(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected  void`

`RequestProcessor.processForwardConfig(HttpServletRequest request, HttpServletResponse response, ForwardConfig forward)`
           Forward or redirect to the specified destination, by the specified mechanism.

`protected  ForwardConfig`

`ActionServlet.processForwardConfigClass(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

`ActionServlet.processForwardExtension(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the forward's configuration as necessary.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionRedirect(ForwardConfig baseConfig)`                                                                                                                                                                                                      
            Construct a new instance with a [`ForwardConfig`](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") object to copy name, path, contextRelative, and arbitrary property values from.      |

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected abstract  ForwardConfig`

`AbstractExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ForwardConfig`.

`protected abstract  ForwardConfig`

`AbstractSelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  ForwardConfig`

`AbstractSelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  ForwardConfig`

`AbstractExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected abstract  void`

`AbstractPerformForward.perform(ActionContext context, ForwardConfig forwardConfig)`
           Perform the appropriate processing on the specified `ForwardConfig`.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected  ForwardConfig`

`ExecuteAction.execute(ActionContext context, Action action, ActionConfig actionConfig, ActionForm actionForm)`
           Execute the specified `Action`, and return the resulting `ActionForward`.

`protected  ForwardConfig`

`SelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  ForwardConfig`

`SelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  ForwardConfig`

`ExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
            

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`protected  void`

`PerformForward.perform(ActionContext context, ForwardConfig forwardConfig)`
           Perform the appropriate processing on the specified `ForwardConfig`.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` ForwardConfig`

`ActionContextBase.getForwardConfig()`
            

` ForwardConfig`

`ActionContext.getForwardConfig()`
            Get the ForwardConfig which has been identified as the basis for view-processing.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` void`

`ActionContextBase.setForwardConfig(ForwardConfig forward)`
            

` void`

`ActionContext.setForwardConfig(ForwardConfig forward)`
            Set the ForwardConfig which should be used as the basis of the view segment of the overall processing.

 

<span id="org.apache.struts.config"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` ForwardConfig`

`ModuleConfig.findForwardConfig(String name)`
            Return the forward configuration for the specified key, if any; otherwise return `null`.

` ForwardConfig`

`ActionConfig.findForwardConfig(String name)`
            Return the forward configuration for the specified key, if any; otherwise return `null`.

` ForwardConfig[]`

`ModuleConfig.findForwardConfigs()`
            Return the form bean configurations for this module.

` ForwardConfig[]`

`ActionConfig.findForwardConfigs()`
            Return all forward configurations for this module.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addForwardConfig(ForwardConfig config)`
            Add a new `ForwardConfig` instance to the set of global forwards associated with this module.

` void`

`ActionConfig.addForwardConfig(ForwardConfig config)`
            Add a new `ForwardConfig` instance to the set of global forwards associated with this action.

` void`

`ForwardConfig.inheritFrom(ForwardConfig config)`
           Inherit values that have not been overridden from the provided config object.

` void`

`ModuleConfig.removeForwardConfig(ForwardConfig config)`
            Remove the specified forward configuration instance.

` void`

`ActionConfig.removeForwardConfig(ForwardConfig config)`
            Remove the specified forward configuration instance.

 

| Constructors in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ForwardConfig(ForwardConfig copyMe)`                                                                                                                                                                                                           
            Construct a new instance based on the values of another ForwardConfig.                                                                                                                                                                 |

 

<span id="org.apache.struts.config.impl"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` ForwardConfig`

`ModuleConfigImpl.findForwardConfig(String name)`
            Return the forward configuration for the specified key, if any; otherwise return `null`.

` ForwardConfig[]`

`ModuleConfigImpl.findForwardConfigs()`
            Return the form bean configurations for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addForwardConfig(ForwardConfig config)`
            Add a new `ForwardConfig` instance to the set of global forwards associated with this module.

` void`

`ModuleConfigImpl.removeForwardConfig(ForwardConfig config)`
            Remove the specified forward configuration instance.

 

<span id="org.apache.struts.util"></span>

Uses of [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [ForwardConfig](../../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config")

`static String`

`RequestUtils.actionIdURL(ForwardConfig forward, HttpServletRequest request, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static String`

`RequestUtils.forwardURL(HttpServletRequest request, ForwardConfig forward)`
           Return the context-relative URL that corresponds to the specified `ForwardConfig`.

`static String`

`RequestUtils.forwardURL(HttpServletRequest request, ForwardConfig forward, ModuleConfig moduleConfig)`
           Return the context-relative URL that corresponds to the specified `ForwardConfig`.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/ForwardConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useForwardConfig.html"><strong>FRAMES</strong></a>    <a href="ForwardConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
