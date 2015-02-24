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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionServlet.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/action/ActionRedirect.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionServletWrapper.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionServlet.html"><strong>FRAMES</strong></a>    <a href="ActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class ActionServlet
------------------------

    java.lang.Object
      javax.servlet.GenericServlet
          javax.servlet.http.HttpServlet
              org.apache.struts.action.ActionServlet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [Servlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/Servlet.html?is-external=true "class or interface in javax.servlet"), [ServletConfig](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletConfig.html?is-external=true "class or interface in javax.servlet")

<!-- -->

**Direct Known Subclasses:**  
[MockActionServlet](../../../../org/apache/struts/mock/MockActionServlet.html.md "class in org.apache.struts.mock")

------------------------------------------------------------------------

    public class ActionServlet

extends [HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html.md?is-external=true "class or interface in javax.servlet.http")

**ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2". This nomenclature originated with a description in the JavaServerPages Specification, version 0.92, and has persisted ever since (in the absence of a better name).

Generally, a "Model 2" application is architected as follows:

-   The user interface will generally be created with server pages, which will not themselves contain any business logic. These pages represent the "view" component of an MVC architecture.
-   Forms and hyperlinks in the user interface that require business logic to be executed will be submitted to a request URI that is mapped to this servlet.
-   There can be **one** instance of this servlet class, which receives and processes all requests that change the state of a user's interaction with the application. The servlet delegates the handling of a request to a [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") object. This component represents the "controller" component of an MVC architecture.
-   The `RequestProcessor` selects and invokes an [`Action`](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action") class to perform the requested business logic, or delegates the response to another resource.
-   The `Action` classes can manipulate the state of the application's interaction with the user, typically by creating or modifying JavaBeans that are stored as request or session attributes (depending on how long they need to be available). Such JavaBeans represent the "model" component of an MVC architecture.
-   Instead of producing the next page of the user interface directly, `Action` classes generally return an [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") to indicate which resource should handle the response. If the `Action` does not return null, the `RequestProcessor` forwards or redirects to the specified resource (by utilizing `RequestDispatcher.forward` or `Response.sendRedirect`) so as to produce the next page of the user interface.

The standard version of `RequestsProcessor` implements the following logic for each incoming HTTP request. You can override some or all of this functionality by subclassing this object and implementing your own version of the processing.

-   Identify, from the incoming request URI, the substring that will be used to select an action procedure.
-   Use this substring to map to the Java class name of the corresponding action class (an implementation of the `Action` interface).
-   If this is the first request for a particular `Action` class, instantiate an instance of that class and cache it for future use.
-   Optionally populate the properties of an `ActionForm` bean associated with this mapping.
-   Call the `execute` method of this `Action` class, passing on a reference to the mapping that was used, the relevant form-bean (if any), and the request and the response that were passed to the controller by the servlet container (thereby providing access to any specialized properties of the mapping itself as well as to the ServletContext).

The standard version of `ActionServlet` is configured based on the following servlet initialization parameters, which you will specify in the web application deployment descriptor (`/WEB-INF/web.xml`) for your application. Subclasses that specialize this servlet are free to define additional initialization parameters.

-   **config** - Comma-separated list of context-relative path(s) to the XML resource(s) containing the configuration information for the default module. (Multiple files support since Struts 1.1) [/WEB-INF/struts-config.xml].
-   **config/${module}** - Comma-separated list of Context-relative path(s) to the XML resource(s) containing the configuration information for the module that will use the specified prefix (/${module}). This can be repeated as many times as required for multiple modules. (Since Struts 1.1)
-   **configFactory** - The Java class name of the `ModuleConfigFactory` used to create the implementation of the ModuleConfig interface.
-   **convertNull** - Force simulation of the Struts 1.0 behavior when populating forms. If set to true, the numeric Java wrapper class types (like `java.lang.Integer`) will default to null (rather than 0). (Since Struts 1.1) [false]
-   **rulesets** - Comma-delimited list of fully qualified classnames of additional `org.apache.commons.digester.RuleSet` instances that should be added to the `Digester` that will be processing `struts-config.xml` files. By default, only the `RuleSet` for the standard configuration elements is loaded. (Since Struts 1.1)
-   **validating** - Should we use a validating XML parser to process the configuration file (strongly recommended)? [true]
-   **chainConfig** - Comma-separated list of either context-relative or classloader path(s) to load commons-chain catalog definitions from. If none specified, the default Struts catalog that is provided with Struts will be used.

**Version:**  
$Rev: 592630 $ $Date: 2005-10-14 19:54:16 -0400 (Fri, 14 Oct 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionServlet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` chainConfig`
           Comma-separated list of context or classloader-relative path(s) that contain the configuration for the default commons-chain catalog(s).

`protected  String`

`config`
           Comma-separated list of context-relative path(s) to our configuration resource(s) for the default module.

`protected  org.apache.commons.digester.Digester`

` configDigester`
           The Digester used to produce ModuleConfig objects from a Struts configuration file.

`protected  boolean`

` convertNull`
           The flag to request backwards-compatible conversions for form bean properties of the Java wrapper class types.

`protected  MessageResources`

`internal`
           The resources object for our internal resources.

`protected  String`

` internalName`
           The Java base name of our internal resources.

`protected static Log`

`log`
           Commons Logging instance.

`protected  String[]`

` registrations`
           The set of public identifiers, and corresponding resource names, for the versions of the configuration file DTDs that we know about.

`protected  String`

` servletMapping`
           The URL pattern to which we are mapped in our web application deployment descriptor.

`protected  String`

` servletName`
           The servlet name under which we are registered in our web application deployment descriptor.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ActionServlet()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addServletMapping(String servletName, String urlPattern)`
           Remember a servlet mapping from our web application deployment descriptor, if it is for this servlet.

` void`

` destroy()`
           Gracefully shut down this controller servlet, releasing any resources that were allocated at initialization.

`protected  void`

` destroyConfigDigester()`
           Gracefully release any configDigester instance that we have created.

`protected  void`

` destroyInternal()`
           Gracefully terminate use of the internal MessageResources.

`protected  void`

` destroyModules()`
           Gracefully terminate use of any modules associated with this application (if any).

` void`

` doGet(HttpServletRequest request, HttpServletResponse response)`
           Process an HTTP "GET" request.

` void`

` doPost(HttpServletRequest request, HttpServletResponse response)`
           Process an HTTP "POST" request.

` MessageResources`

` getInternal()`
           Return the `MessageResources` instance containing our internal message strings.

`protected  ModuleConfig`

` getModuleConfig(HttpServletRequest request)`
           Return the module configuration object for the currently selected module.

`protected  RequestProcessor`

` getRequestProcessor(ModuleConfig config)`
           Look up and return the [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

` void`

`init()`
           Initialize this servlet.

`protected  void`

` initChain()`
           Parse the configuration documents specified by the `chainConfig` init-param to configure the default `Catalog` that is registered in the `CatalogFactory` instance for this application.

`protected  org.apache.commons.digester.Digester`

` initConfigDigester()`
           Create (if needed) and return a new `Digester` instance that has been initialized to process Struts module configuration files and configure a corresponding `ModuleConfig` object (which must be pushed on to the evaluation stack before parsing begins).

`protected  void`

` initInternal()`
           Initialize our internal MessageResources bundle.

`protected  void`

` initModuleActions(ModuleConfig config)`
           Initialize the action configs for the specified module.

`protected  ModuleConfig`

` initModuleConfig(String prefix, String paths)`
           Initialize the module configuration information for the specified module.

`protected  void`

` initModuleConfigFactory()`
           Initialize the factory used to create the module configuration.

`protected  void`

` initModuleExceptionConfigs(ModuleConfig config)`
           Initialize the exception handlers for the specified module.

`protected  void`

` initModuleFormBeans(ModuleConfig config)`
           Initialize the form beans for the specified module.

`protected  void`

` initModuleForwards(ModuleConfig config)`
           Initialize the forwards for the specified module.

`protected  void`

` initModuleMessageResources(ModuleConfig config)`
           Initialize the application `MessageResources` for the specified module.

`protected  void`

` initModulePlugIns(ModuleConfig config)`
           Initialize the plug ins for the specified module.

`protected  void`

` initModulePrefixes(ServletContext context)`
           Saves a String[] of module prefixes in the ServletContext under Globals.MODULE\_PREFIXES\_KEY.

`protected  void`

` initOther()`
           Initialize other global characteristics of the controller servlet.

`protected  void`

` initServlet()`
           Initialize the servlet mapping under which our controller servlet is being accessed.

`protected  void`

` parseModuleConfigFile(org.apache.commons.digester.Digester digester, String path)`
           **Deprecated.** *use parseModuleConfigFile(Digester digester, URL url) instead*

`protected  void`

` parseModuleConfigFile(org.apache.commons.digester.Digester digester, URL url)`
           Parses one module config file.

`protected  void`

` process(HttpServletRequest request, HttpServletResponse response)`
           Perform the standard request processing for this request, and create the corresponding response.

`protected  ActionConfig`

` processActionConfigClass(ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Checks if the current actionConfig is using the correct class based on the class of its ancestor ActionConfig.

`protected  void`

` processActionConfigExtension(ActionConfig actionConfig, ModuleConfig moduleConfig)`
           Extend the action's configuration as necessary.

`protected  ExceptionConfig`

` processExceptionConfigClass(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current exceptionConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

` processExceptionExtension(ExceptionConfig exceptionConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the exception's configuration as necessary.

`protected  FormBeanConfig`

` processFormBeanConfigClass(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Checks if the current beanConfig is using the correct class based on the class of its ancestor form bean config.

`protected  void`

` processFormBeanExtension(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Extend the form bean's configuration as necessary.

`protected  ForwardConfig`

` processForwardConfigClass(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor.

`protected  void`

` processForwardExtension(ForwardConfig forwardConfig, ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Extend the forward's configuration as necessary.

`protected  List`

` splitAndResolvePaths(String paths)`
           Takes a comma-delimited string and splits it into paths, then resolves those paths using the ServletContext and appropriate ClassLoader.

 <span id="methods_inherited_from_class_javax.servlet.http.HttpServlet"></span>

| **Methods inherited from class javax.servlet.http.[HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html.md?is-external=true "class or interface in javax.servlet.http")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doDelete, doHead, doOptions, doPut, doTrace, getLastModified, service, service`                                                                                                                         |

 <span id="methods_inherited_from_class_javax.servlet.GenericServlet"></span>

| **Methods inherited from class javax.servlet.[GenericServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/GenericServlet.html.md?is-external=true "class or interface in javax.servlet")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getInitParameter, getInitParameterNames, getServletConfig, getServletContext, getServletInfo, getServletName, init, log, log`                                                                  |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected String config

Comma-separated list of context-relative path(s) to our configuration resource(s) for the default module.

------------------------------------------------------------------------

<span id="chainConfig"></span>

### chainConfig

    protected String chainConfig

Comma-separated list of context or classloader-relative path(s) that contain the configuration for the default commons-chain catalog(s).

------------------------------------------------------------------------

<span id="configDigester"></span>

### configDigester

    protected org.apache.commons.digester.Digester configDigester

The Digester used to produce ModuleConfig objects from a Struts configuration file.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="convertNull"></span>

### convertNull

    protected boolean convertNull

The flag to request backwards-compatible conversions for form bean properties of the Java wrapper class types.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="internal"></span>

### internal

    protected MessageResources internal

The resources object for our internal resources.

------------------------------------------------------------------------

<span id="internalName"></span>

### internalName

    protected String internalName

The Java base name of our internal resources.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="registrations"></span>

### registrations

    protected String[] registrations

The set of public identifiers, and corresponding resource names, for the versions of the configuration file DTDs that we know about. There **MUST** be an even number of Strings in this list!

------------------------------------------------------------------------

<span id="servletMapping"></span>

### servletMapping

    protected String servletMapping

The URL pattern to which we are mapped in our web application deployment descriptor.

------------------------------------------------------------------------

<span id="servletName"></span>

### servletName

    protected String servletName

The servlet name under which we are registered in our web application deployment descriptor.

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionServlet

    public ActionServlet()

<span id="method_detail"></span>

**Method Detail**

### destroy

    public void destroy()

Gracefully shut down this controller servlet, releasing any resources that were allocated at initialization.

**Specified by:**  
`destroy` in interface `Servlet`

**Overrides:**  
`destroy` in class `GenericServlet`

------------------------------------------------------------------------

### init

    public void init()
              throws ServletException

Initialize this servlet. Most of the processing has been factored into support methods so that you can override particular functionality at a fairly granular level.

**Overrides:**  
`init` in class `GenericServlet`

<!-- -->

**Throws:**  
`ServletException` - if we cannot configure ourselves correctly

------------------------------------------------------------------------

### initModulePrefixes

    protected void initModulePrefixes(ServletContext context)

Saves a String[] of module prefixes in the ServletContext under Globals.MODULE\_PREFIXES\_KEY. **NOTE** - the "" prefix for the default module is not included in this list.

**Parameters:**  
`context` - The servlet context.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### doGet

    public void doGet(HttpServletRequest request,
                      HttpServletResponse response)
               throws IOException,
                      ServletException

Process an HTTP "GET" request.

**Overrides:**  
`doGet` in class `HttpServlet`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### doPost

    public void doPost(HttpServletRequest request,
                       HttpServletResponse response)
                throws IOException,
                       ServletException

Process an HTTP "POST" request.

**Overrides:**  
`doPost` in class `HttpServlet`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### addServletMapping

    public void addServletMapping(String servletName,
                                  String urlPattern)

Remember a servlet mapping from our web application deployment descriptor, if it is for this servlet.

**Parameters:**  
`servletName` - The name of the servlet being mapped

`urlPattern` - The URL pattern to which this servlet is mapped

------------------------------------------------------------------------

### getInternal

    public MessageResources getInternal()

Return the `MessageResources` instance containing our internal message strings.

**Returns:**  
the `MessageResources` instance containing our internal message strings.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### destroyModules

    protected void destroyModules()

Gracefully terminate use of any modules associated with this application (if any).

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### destroyConfigDigester

    protected void destroyConfigDigester()

Gracefully release any configDigester instance that we have created.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### destroyInternal

    protected void destroyInternal()

Gracefully terminate use of the internal MessageResources.

------------------------------------------------------------------------

### getModuleConfig

    protected ModuleConfig getModuleConfig(HttpServletRequest request)

Return the module configuration object for the currently selected module.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
The module configuration object for the currently selected module.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getRequestProcessor

    protected RequestProcessor getRequestProcessor(ModuleConfig config)
                                            throws ServletException

Look up and return the [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

**Parameters:**  
`config` - The module configuration for which to acquire and return a RequestProcessor.

**Returns:**  
The [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module,

**Throws:**  
`ServletException` - If we cannot instantiate a RequestProcessor instance a [`UnavailableException`](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/UnavailableException.html.md?is-external=true "class or interface in javax.servlet") is thrown, meaning your application is not loaded and will not be available.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### initModuleConfigFactory

    protected void initModuleConfigFactory()

Initialize the factory used to create the module configuration.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### initModuleConfig

    protected ModuleConfig initModuleConfig(String prefix,
                                            String paths)
                                     throws ServletException

Initialize the module configuration information for the specified module.

**Parameters:**  
`prefix` - Module prefix for this module

`paths` - Comma-separated list of context-relative resource path(s) for this modules's configuration resource(s)

**Returns:**  
The new module configuration instance.

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### parseModuleConfigFile

    protected void parseModuleConfigFile(org.apache.commons.digester.Digester digester,
                                         String path)
                                  throws UnavailableException

**Deprecated.** *use parseModuleConfigFile(Digester digester, URL url) instead*

Parses one module config file.

**Parameters:**  
`digester` - Digester instance that does the parsing

`path` - The path to the config file to parse.

**Throws:**  
`UnavailableException` - if file cannot be read or parsed

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### parseModuleConfigFile

    protected void parseModuleConfigFile(org.apache.commons.digester.Digester digester,
                                         URL url)
                                  throws UnavailableException

Parses one module config file.

**Parameters:**  
`digester` - Digester instance that does the parsing

`url` - The url to the config file to parse.

**Throws:**  
`UnavailableException` - if file cannot be read or parsed

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### initModulePlugIns

    protected void initModulePlugIns(ModuleConfig config)
                              throws ServletException

Initialize the plug ins for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### initModuleFormBeans

    protected void initModuleFormBeans(ModuleConfig config)
                                throws ServletException

Initialize the form beans for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### processFormBeanExtension

    protected void processFormBeanExtension(FormBeanConfig beanConfig,
                                            ModuleConfig moduleConfig)
                                     throws ServletException

Extend the form bean's configuration as necessary.

**Parameters:**  
`beanConfig` - the configuration to process.

`moduleConfig` - the module configuration for this module.

**Throws:**  
`ServletException` - if initialization cannot be performed.

------------------------------------------------------------------------

### processFormBeanConfigClass

    protected FormBeanConfig processFormBeanConfigClass(FormBeanConfig beanConfig,
                                                        ModuleConfig moduleConfig)
                                                 throws ServletException

Checks if the current beanConfig is using the correct class based on the class of its ancestor form bean config.

**Parameters:**  
`beanConfig` - The form bean to check.

`moduleConfig` - The config for the current module.

**Returns:**  
The form bean config using the correct class as determined by the config's ancestor and its own overridden value.

**Throws:**  
`UnavailableException` - if an instance of the form bean config class cannot be created.

`ServletException` - on class creation error

------------------------------------------------------------------------

### initModuleForwards

    protected void initModuleForwards(ModuleConfig config)
                               throws ServletException

Initialize the forwards for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

------------------------------------------------------------------------

### processForwardExtension

    protected void processForwardExtension(ForwardConfig forwardConfig,
                                           ModuleConfig moduleConfig,
                                           ActionConfig actionConfig)
                                    throws ServletException

Extend the forward's configuration as necessary. If actionConfig is provided, then this method will process the forwardConfig as part of that actionConfig. If actionConfig is null, the forwardConfig will be processed as a global forward.

**Parameters:**  
`forwardConfig` - the configuration to process.

`moduleConfig` - the module configuration for this module.

`actionConfig` - If applicable, the config for the current action.

**Throws:**  
`ServletException` - if initialization cannot be performed.

------------------------------------------------------------------------

### processForwardConfigClass

    protected ForwardConfig processForwardConfigClass(ForwardConfig forwardConfig,
                                                      ModuleConfig moduleConfig,
                                                      ActionConfig actionConfig)
                                               throws ServletException

Checks if the current forwardConfig is using the correct class based on the class of its configuration ancestor. If actionConfig is provided, then this method will process the forwardConfig as part of that actionConfig. If actionConfig is null, the forwardConfig will be processed as a global forward.

**Parameters:**  
`forwardConfig` - The forward to check.

`moduleConfig` - The config for the current module.

`actionConfig` - If applicable, the config for the current action.

**Returns:**  
The forward config using the correct class as determined by the config's ancestor and its own overridden value.

**Throws:**  
`UnavailableException` - if an instance of the forward config class cannot be created.

`ServletException` - on class creation error

------------------------------------------------------------------------

### initModuleExceptionConfigs

    protected void initModuleExceptionConfigs(ModuleConfig config)
                                       throws ServletException

Initialize the exception handlers for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### processExceptionExtension

    protected void processExceptionExtension(ExceptionConfig exceptionConfig,
                                             ModuleConfig moduleConfig,
                                             ActionConfig actionConfig)
                                      throws ServletException

Extend the exception's configuration as necessary. If actionConfig is provided, then this method will process the exceptionConfig as part of that actionConfig. If actionConfig is null, the exceptionConfig will be processed as a global forward.

**Parameters:**  
`exceptionConfig` - the configuration to process.

`moduleConfig` - the module configuration for this module.

`actionConfig` - If applicable, the config for the current action.

**Throws:**  
`ServletException` - if initialization cannot be performed.

------------------------------------------------------------------------

### processExceptionConfigClass

    protected ExceptionConfig processExceptionConfigClass(ExceptionConfig exceptionConfig,
                                                          ModuleConfig moduleConfig,
                                                          ActionConfig actionConfig)
                                                   throws ServletException

Checks if the current exceptionConfig is using the correct class based on the class of its configuration ancestor. If actionConfig is provided, then this method will process the exceptionConfig as part of that actionConfig. If actionConfig is null, the exceptionConfig will be processed as a global forward.

**Parameters:**  
`exceptionConfig` - The config to check.

`moduleConfig` - The config for the current module.

`actionConfig` - If applicable, the config for the current action.

**Returns:**  
The exception config using the correct class as determined by the config's ancestor and its own overridden value.

**Throws:**  
`ServletException` - if an instance of the exception config class cannot be created.

------------------------------------------------------------------------

### initModuleActions

    protected void initModuleActions(ModuleConfig config)
                              throws ServletException

Initialize the action configs for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### processActionConfigExtension

    protected void processActionConfigExtension(ActionConfig actionConfig,
                                                ModuleConfig moduleConfig)
                                         throws ServletException

Extend the action's configuration as necessary.

**Parameters:**  
`actionConfig` - the configuration to process.

`moduleConfig` - the module configuration for this module.

**Throws:**  
`ServletException` - if initialization cannot be performed.

------------------------------------------------------------------------

### processActionConfigClass

    protected ActionConfig processActionConfigClass(ActionConfig actionConfig,
                                                    ModuleConfig moduleConfig)
                                             throws ServletException

Checks if the current actionConfig is using the correct class based on the class of its ancestor ActionConfig.

**Parameters:**  
`actionConfig` - The action config to check.

`moduleConfig` - The config for the current module.

**Returns:**  
The config object using the correct class as determined by the config's ancestor and its own overridden value.

**Throws:**  
`ServletException` - if an instance of the action config class cannot be created.

------------------------------------------------------------------------

### initModuleMessageResources

    protected void initModuleMessageResources(ModuleConfig config)
                                       throws ServletException

Initialize the application `MessageResources` for the specified module.

**Parameters:**  
`config` - ModuleConfig information for this module

**Throws:**  
`ServletException` - if initialization cannot be performed

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### initConfigDigester

    protected org.apache.commons.digester.Digester initConfigDigester()
                                                               throws ServletException

Create (if needed) and return a new `Digester` instance that has been initialized to process Struts module configuration files and configure a corresponding `ModuleConfig` object (which must be pushed on to the evaluation stack before parsing begins).

**Returns:**  
A new configured `Digester` instance.

**Throws:**  
`ServletException` - if a Digester cannot be configured

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### initInternal

    protected void initInternal()
                         throws ServletException

Initialize our internal MessageResources bundle.

**Throws:**  
`ServletException` - if we cannot initialize these resources

`UnavailableException` - if we cannot load resources

------------------------------------------------------------------------

### initChain

    protected void initChain()
                      throws ServletException

Parse the configuration documents specified by the `chainConfig` init-param to configure the default `Catalog` that is registered in the `CatalogFactory` instance for this application.

**Throws:**  
`ServletException` - if an error occurs.

------------------------------------------------------------------------

### initOther

    protected void initOther()
                      throws ServletException

Initialize other global characteristics of the controller servlet.

**Throws:**  
`ServletException` - if we cannot initialize these resources

------------------------------------------------------------------------

### initServlet

    protected void initServlet()
                        throws ServletException

Initialize the servlet mapping under which our controller servlet is being accessed. This will be used in the `.html.md:form>` tag to generate correct destination URLs for form submissions.

**Throws:**  
`ServletException` - if error happens while scanning web.xml

------------------------------------------------------------------------

### splitAndResolvePaths

    protected List splitAndResolvePaths(String paths)
                                 throws ServletException

Takes a comma-delimited string and splits it into paths, then resolves those paths using the ServletContext and appropriate ClassLoader. When loading from the classloader, multiple resources per path are supported to support, for example, multiple jars containing the same named config file.

**Parameters:**  
`paths` - A comma-delimited string of paths

**Returns:**  
A list of resolved URL's for all found resources

**Throws:**  
`ServletException` - if a servlet exception is thrown

------------------------------------------------------------------------

### process

    protected void process(HttpServletRequest request,
                           HttpServletResponse response)
                    throws IOException,
                           ServletException

Perform the standard request processing for this request, and create the corresponding response.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception is thrown

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionServlet.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/action/ActionRedirect.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionServletWrapper.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionServlet.html"><strong>FRAMES</strong></a>    <a href="ActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
