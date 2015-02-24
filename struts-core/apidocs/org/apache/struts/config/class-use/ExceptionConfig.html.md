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
<td align="left"><a href="../../../../../org/apache/struts/config/ExceptionConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="ExceptionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.ExceptionConfig**
-------------------------------------------

Packages that use [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

 

<span id="org.apache.struts.action"></span>

Uses of [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

`protected  ExceptionConfig`

`ActionServlet.processExceptionConfigClass(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current exceptionConfig is using the correct class based on the class of its configuration ancestor.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

`protected  String`

`ExceptionHandler.determineIncludePath(ExceptionConfig config, ActionForward actionForward)`
           Return a path to which an include should be attempted in the case when the response was committed before the `ExceptionHandler` was invoked.

` ActionForward`

`ExceptionHandler.execute(Exception ex, ExceptionConfig ae, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response)`
            Handle the Exception.

`protected  void`

`ExceptionHandler.handleCommittedResponse(Exception ex, ExceptionConfig config, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response, ActionForward actionForward)`
           Attempt to give good information when the response has already been committed when the exception was thrown.

`protected  ExceptionConfig`

`ActionServlet.processExceptionConfigClass(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current exceptionConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

`ActionServlet.processExceptionExtension(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the exception's configuration as necessary.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

`protected abstract  ForwardConfig`

`AbstractExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

`protected  ForwardConfig`

`ExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
            

 

<span id="org.apache.struts.config"></span>

Uses of [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

` ExceptionConfig`

`ModuleConfig.findException(Class type)`
            Perform a recursive search for an ExceptionConfig registered for this class, or for any superclass.

` ExceptionConfig`

`ActionConfig.findException(Class type)`
           Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled.

` ExceptionConfig`

`ModuleConfig.findExceptionConfig(String type)`
            Return the exception configuration for the specified type, if any; otherwise return `null`.

` ExceptionConfig`

`ActionConfig.findExceptionConfig(String type)`
            Return the exception configuration for the specified type, if any; otherwise return `null`.

` ExceptionConfig[]`

`ModuleConfig.findExceptionConfigs()`
            Return the exception configurations for this module.

` ExceptionConfig[]`

`ActionConfig.findExceptionConfigs()`
            Return the exception configurations for this action.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addExceptionConfig(ExceptionConfig config)`
            Add a new `ExceptionConfig` instance to the set associated with this module.

` void`

`ActionConfig.addExceptionConfig(ExceptionConfig config)`
            Add a new `ExceptionConfig` instance to the set associated with this action.

` void`

`ExceptionConfig.inheritFrom(ExceptionConfig config)`
           Inherit values that have not been overridden from the provided config object.

` void`

`ModuleConfig.removeExceptionConfig(ExceptionConfig config)`
            Remove the specified exception configuration instance.

` void`

`ActionConfig.removeExceptionConfig(ExceptionConfig config)`
            Remove the specified exception configuration instance.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

` ExceptionConfig`

`ModuleConfigImpl.findException(Class type)`
           Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled.

` ExceptionConfig`

`ModuleConfigImpl.findExceptionConfig(String type)`
            Return the exception configuration for the specified type, if any; otherwise return `null`.

` ExceptionConfig[]`

`ModuleConfigImpl.findExceptionConfigs()`
            Return the exception configurations for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [ExceptionConfig](../../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addExceptionConfig(ExceptionConfig config)`
            Add a new `ExceptionConfig` instance to the set associated with this module.

` void`

`ModuleConfigImpl.removeExceptionConfig(ExceptionConfig config)`
            Remove the specified exception configuration instance.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/ExceptionConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="ExceptionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
