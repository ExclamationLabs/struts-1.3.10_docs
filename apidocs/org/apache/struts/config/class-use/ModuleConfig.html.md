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
<td align="left"><a href="../../../../../org/apache/struts/config/ModuleConfig.html.md" title="interface in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useModuleConfig.html"><strong>FRAMES</strong></a>    <a href="ModuleConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.config.ModuleConfig**
----------------------------------------

Packages that use [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

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

[**org.apache.struts.faces.application**](#org.apache.struts.faces.application)

  

[**org.apache.struts.faces.component**](#org.apache.struts.faces.component)

  

[**org.apache.struts.faces.util**](#org.apache.struts.faces.util)

  

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.plugins**](#org.apache.struts.plugins)

  

[**org.apache.struts.taglib**](#org.apache.struts.taglib)

  

[**org.apache.struts.taglib.html.md**](#org.apache.struts.taglib.html)

The "struts.html.md" tag library contains JSP custom tags useful in creating dynamic HTML user interfaces, including input forms. 

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Fields in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) declared as [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`RequestProcessor.moduleConfig`
           The `ModuleConfiguration` with which we are associated.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`ActionServlet.getModuleConfig(HttpServletRequest request)`
           Return the module configuration object for the currently selected module.

`protected  ModuleConfig`

`ActionServlet.initModuleConfig(String prefix, String paths)`
           Initialize the module configuration information for the specified module.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  RequestProcessor`

`ActionServlet.getRequestProcessor(ModuleConfig config)`
           Look up and return the [`RequestProcessor`](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

` void`

`RequestProcessor.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

` void`

`PlugIn.init(ActionServlet servlet, ModuleConfig config)`
           Receive notification that the specified module is being started up.

`protected  void`

`ActionServlet.initModuleActions(ModuleConfig config)`
           Initialize the action configs for the specified module.

`protected  void`

`ActionServlet.initModuleExceptionConfigs(ModuleConfig config)`
           Initialize the exception handlers for the specified module.

`protected  void`

`ActionServlet.initModuleFormBeans(ModuleConfig config)`
           Initialize the form beans for the specified module.

`protected  void`

`ActionServlet.initModuleForwards(ModuleConfig config)`
           Initialize the forwards for the specified module.

`protected  void`

`ActionServlet.initModuleMessageResources(ModuleConfig config)`
           Initialize the application `MessageResources` for the specified module.

`protected  void`

`ActionServlet.initModulePlugIns(ModuleConfig config)`
           Initialize the plug ins for the specified module.

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

`protected  FormBeanConfig`

`ActionServlet.processFormBeanConfigClass(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Checks if the current beanConfig is using the correct class based on the class of its ancestor form bean config.

`protected  void`

`ActionServlet.processFormBeanExtension(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Extend the form bean's configuration as necessary.

`protected  ForwardConfig`

`ActionServlet.processForwardConfigClass(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

`ActionServlet.processForwardExtension(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the forward's configuration as necessary.

 

<span id="org.apache.struts.chain"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html)

 

Methods in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` void`

`ComposableRequestProcessor.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

`protected  void`

`ComposableRequestProcessor.initCatalogFactory(ActionServlet servlet, ModuleConfig moduleConfig)`
            Establish the CatalogFactory which will be used to look up the catalog which has the request processing command.

 

<span id="org.apache.struts.chain.commands"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html)

 

Methods in [org.apache.struts.chain.commands](../../../../../org/apache/struts/chain/commands/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected abstract  ForwardConfig`

`AbstractSelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  ForwardConfig`

`AbstractSelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected abstract  ForwardConfig`

`AbstractExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Perform the required handling of the specified exception.

 

<span id="org.apache.struts.chain.commands.servlet"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html)

 

Methods in [org.apache.struts.chain.commands.servlet](../../../../../org/apache/struts/chain/commands/servlet/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ForwardConfig`

`SelectInput.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  ForwardConfig`

`SelectForward.forward(ActionContext context, ModuleConfig moduleConfig, String uri)`
           Create and return a `ForwardConfig` representing the specified module-relative destination.

`protected  ForwardConfig`

`ExceptionHandler.handle(ActionContext context, Exception exception, ExceptionConfig exceptionConfig, ActionConfig actionConfig, ModuleConfig moduleConfig)`
            

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`WebActionContext.getModuleConfig()`
            

` ModuleConfig`

`ActionContextBase.getModuleConfig()`
            

` ModuleConfig`

`ActionContext.getModuleConfig()`
            Get the ModuleConfig which is operative for the current request.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ActionForm`

`ActionContextBase.findOrCreateActionForm(String formName, String scopeName, ModuleConfig moduleConfig)`
            In the context of the given `ModuleConfig` and this `ActionContext`, look for an existing `ActionForm` in the specified scope.

` void`

`WebActionContext.setModuleConfig(ModuleConfig moduleConfig)`
            

` void`

`ActionContextBase.setModuleConfig(ModuleConfig config)`
            

` void`

`ActionContext.setModuleConfig(ModuleConfig config)`
            Set the ModuleConfig which is operative for the current request.

 

<span id="org.apache.struts.config"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Fields in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) declared as [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`ActionConfig.moduleConfig`
            The module configuration with which we are associated.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`abstract  ModuleConfig`

`ModuleConfigFactory.createModuleConfig(String prefix)`
           Create and return a newly instansiated [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

` ModuleConfig`

`ActionConfig.getModuleConfig()`
            The module configuration with which we are associated.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  boolean`

`FormBeanConfig.checkCircularInheritance(ModuleConfig moduleConfig)`
           Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

`protected  boolean`

`ActionConfig.checkCircularInheritance(ModuleConfig moduleConfig)`
           Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

`protected  boolean`

`ForwardConfig.checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

`protected  boolean`

`ExceptionConfig.checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

` void`

`FormBeanConfig.processExtends(ModuleConfig moduleConfig)`
           Inherit configuration information from the FormBeanConfig that this instance is extending.

` void`

`ActionConfig.processExtends(ModuleConfig moduleConfig)`
           Inherit configuration information from the ActionConfig that this instance is extending.

` void`

`ForwardConfig.processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ForwardConfig that this instance is extending.

` void`

`ExceptionConfig.processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ExceptionConfig that this instance is extending.

` void`

`ActionConfig.setModuleConfig(ModuleConfig moduleConfig)`
            The module configuration with which we are associated.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Classes in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that implement [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` class`

`ModuleConfigImpl`
           The collection of static configuration information that describes a Struts-based module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`DefaultModuleConfigFactory.createModuleConfig(String prefix)`
           Create and return a newly instansiated [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

 

<span id="org.apache.struts.faces.application"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html)

 

Methods in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  RequestProcessor`

`ActionListenerImpl.getRequestProcessor(ModuleConfig config, ServletContext context)`
           Look up and return the `RequestProcessor` responsible for the specified module, creating a new one if necessary.

 

<span id="org.apache.struts.faces.component"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.faces.component](../../../../../org/apache/struts/faces/component/package-summary.html)

 

Methods in [org.apache.struts.faces.component](../../../../../org/apache/struts/faces/component/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`FormComponent.lookupModuleConfig(javax.faces.context.FacesContext context)`
           Return the `ModuleConfig` for the application module this form is being processed for.

 

<span id="org.apache.struts.faces.util"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.faces.util](../../../../../org/apache/struts/faces/util/package-summary.html)

 

Methods in [org.apache.struts.faces.util](../../../../../org/apache/struts/faces/util/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`StrutsContext.getModuleConfig()`
           Return the `ModuleConfig` for the application module to which this request has been assigned (if any).

 

<span id="org.apache.struts.mock"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Fields in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) declared as [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`TestMockBase.moduleConfig`
            

`protected  ModuleConfig`

`TestMockBase.moduleConfig2`
            

`protected  ModuleConfig`

`TestMockBase.moduleConfig3`
            

 

<span id="org.apache.struts.plugins"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.plugins](../../../../../org/apache/struts/plugins/package-summary.html)

 

Fields in [org.apache.struts.plugins](../../../../../org/apache/struts/plugins/package-summary.html.md) declared as [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`ModuleConfigVerifier.config`
           The [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") instance for our module.

`protected  ModuleConfig`

`DigestingPlugIn.moduleConfig`
            

 

Methods in [org.apache.struts.plugins](../../../../../org/apache/struts/plugins/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` void`

`ModuleConfigVerifier.init(ActionServlet servlet, ModuleConfig config)`
            

` void`

`DigestingPlugIn.init(ActionServlet servlet, ModuleConfig config)`
           Initialize a `Digester` and use it to parse a configuration file, resulting in a root object which will be placed into the ServletContext.

 

<span id="org.apache.struts.taglib"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.taglib](../../../../../org/apache/struts/taglib/package-summary.html)

 

Methods in [org.apache.struts.taglib](../../../../../org/apache/struts/taglib/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`TagUtils.getModuleConfig(PageContext pageContext)`
           Return the default ModuleConfig object if it exists, null if otherwise.

` ModuleConfig`

`TagUtils.getModuleConfig(String module, PageContext pageContext)`
           Return the specified ModuleConfig object for the given prefix if it exists, otherwise a NullPointerException will be thrown.

 

Methods in [org.apache.struts.taglib](../../../../../org/apache/struts/taglib/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` String`

`TagUtils.pageURL(HttpServletRequest request, String page, ModuleConfig moduleConfig)`
           Return the context-relative URL that corresponds to the specified `page` attribute value, calculated based on the `pagePattern` property of the current module's [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

 

<span id="org.apache.struts.taglib.html.md"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.taglib.html](../../../../../org/apache/struts/taglib/html/package-summary.html)

 

Fields in [org.apache.struts.taglib.html.md](../../../../../org/apache/struts/taglib/html/package-summary.html) declared as [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`FormTag.moduleConfig`
           The module configuration for our module.

 

<span id="org.apache.struts.tiles"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  ModuleConfig`

`TilesUtilStrutsModulesImpl.getModuleConfig(HttpServletRequest request, ServletContext servletContext)`
           Get the current ModuleConfig.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  Map`

`TilesPlugin.findStrutsPlugInConfigProperties(ActionServlet servlet, ModuleConfig config)`
           Find original properties set in the Struts PlugInConfig object.

` DefinitionsFactory`

`TilesUtilStrutsModulesImpl.getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to specified moduleConfig.

` DefinitionsFactory`

`TilesUtilStrutsImpl.getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to the specified moduleConfig.

`protected  RequestProcessor`

`RedeployableActionServlet.getRequestProcessor(ModuleConfig config)`
            

` void`

`TilesRequestProcessor.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

` void`

`TilesPlugin.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Receive notification that the specified module is being started up.

`protected  void`

`TilesPlugin.initRequestProcessorClass(ModuleConfig config)`
           Set RequestProcessor to appropriate Tiles [`RequestProcessor`](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action").

`protected  DefinitionsFactoryConfig`

`TilesPlugin.readFactoryConfig(ActionServlet servlet, ModuleConfig config)`
           Create FactoryConfig and initialize it from web.xml and struts-config.xml.

 

<span id="org.apache.struts.upload"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html)

 

Methods in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`protected  String`

`CommonsMultipartRequestHandler.getRepositoryPath(ModuleConfig mc)`
            Returns the path to the temporary directory to be used for uploaded files which are written to disk.

`protected  long`

`CommonsMultipartRequestHandler.getSizeMax(ModuleConfig mc)`
            Returns the maximum allowable size, in bytes, of an uploaded file.

`protected  long`

`CommonsMultipartRequestHandler.getSizeThreshold(ModuleConfig mc)`
            Returns the size threshold which determines whether an uploaded file will be written to disk or cached in memory.

 

<span id="org.apache.struts.util"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) that return [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` ModuleConfig`

`ModuleUtils.getModuleConfig(HttpServletRequest request)`
           Return the current ModuleConfig object stored in request, if it exists, null otherwise.

` ModuleConfig`

`ModuleUtils.getModuleConfig(HttpServletRequest request, ServletContext context)`
           Return the ModuleConfig object is it exists, null otherwise.

` ModuleConfig`

`ModuleUtils.getModuleConfig(String prefix, HttpServletRequest request, ServletContext context)`
           Return the desired ModuleConfig object stored in context, if it exists, otherwise return the current ModuleConfig

` ModuleConfig`

`ModuleUtils.getModuleConfig(String prefix, ServletContext context)`
           Return the desired ModuleConfig object stored in context, if it exists, null otherwise.

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

`static String`

`RequestUtils.actionIdURL(String originalPath, ModuleConfig moduleConfig, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static ActionForm`

`RequestUtils.createActionForm(HttpServletRequest request, ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet)`
           Create (if necessary) and return an `ActionForm` instance appropriate for this request.

`static String`

`RequestUtils.forwardURL(HttpServletRequest request, ForwardConfig forward, ModuleConfig moduleConfig)`
           Return the context-relative URL that corresponds to the specified `ForwardConfig`.

 

<span id="org.apache.struts.validator"></span>

Uses of [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

` void`

`ValidatorPlugIn.init(ActionServlet servlet, ModuleConfig config)`
           Initialize and load our resources.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/ModuleConfig.html.md" title="interface in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useModuleConfig.html"><strong>FRAMES</strong></a>    <a href="ModuleConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
