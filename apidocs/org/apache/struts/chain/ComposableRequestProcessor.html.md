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
<td align="left"><a href="class-use/ComposableRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/chain/Constants.html.md" title="class in org.apache.struts.chain"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/chain/ComposableRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="ComposableRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.chain
 Class ComposableRequestProcessor
---------------------------------

    java.lang.Object
      org.apache.struts.action.RequestProcessor
          org.apache.struts.chain.ComposableRequestProcessor

------------------------------------------------------------------------

    public class ComposableRequestProcessor

extends [RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")

ComposableRequestProcessor uses the Chain Of Resposibility design pattern (as implemented by the commons-chain package in Jakarta Commons) to support external configuration of command chains to be used. It is configured via the following context initialization parameters:

-   [org.apache.struts.chain.CATALOG\_NAME] - Name of the Catalog in which we will look up the Command to be executed for each request. If not specified, the default value is struts.
-   org.apache.struts.chain.COMMAND\_NAME - Name of the Command which we will execute for each request, to be looked up in the specified Catalog. If not specified, the default value is servlet-standard.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` ACTION_CONTEXT_CLASS`
            Token for ActionContext clazss so that it can be stored in the ControllerConfig.

`protected  org.apache.commons.chain.Catalog`

` catalog`
           The `Catalog` containing all of the available command chains for this module.

`protected  org.apache.commons.chain.CatalogFactory`

` catalogFactory`
           The `CatalogFactory` from which catalog containing the the base request-processing `Command` will be retrieved.

`protected  org.apache.commons.chain.Command`

` command`
           The `Command` to be executed for each request.

`protected static Log`

` LOG`
           The `Log` instance for this class.

 <span id="fields_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Fields inherited from class org.apache.struts.action.[RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` actions,  INCLUDE_PATH_INFO,  INCLUDE_SERVLET_PATH, log,  moduleConfig,  servlet`                                                                                         |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` ComposableRequestProcessor()` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

`protected  ActionContext`

` contextInstance(HttpServletRequest request, HttpServletResponse response)`
           Provide the initialized `ActionContext` instance which will be used by this request.

`protected  ActionContext`

` createActionContextInstance(ServletContext servletContext, HttpServletRequest request, HttpServletResponse response)`
           Create a new instance of `ActionContext` according to configuration.

` void`

` destroy()`
           Clean up in preparation for a shutdown of this application.

` void`

` init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

`protected  void`

` initCatalogFactory(ActionServlet servlet, ModuleConfig moduleConfig)`
            Establish the CatalogFactory which will be used to look up the catalog which has the request processing command.

`protected  void`

` initializeActionContext(ActionContext context)`
           Set common properties on the given `ActionContext` instance so that commands in the chain can count on their presence.

` void`

` process(HttpServletRequest request, HttpServletResponse response)`
           Process an `HttpServletRequest` and create the corresponding `HttpServletResponse`.

`protected  HttpServletRequest`

` processMultipart(HttpServletRequest request)`
           If this is a multipart request, wrap it with a special wrapper.

` void`

` setCatalogFactory(org.apache.commons.chain.CatalogFactory catalogFactory)`
           Set the `CatalogFactory` instance which should be used to find the request-processing command.

 <span id="methods_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Methods inherited from class org.apache.struts.action.[RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")**                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doForward,  doInclude,  getInternal,  getServletContext,  internalModuleRelativeForward,  internalModuleRelativeInclude,  processActionCreate,  processActionForm,  processActionPerform,  processCachedMessages,  processContent,  processException,  processForward,  processForwardConfig,  processInclude,  processLocale,  processMapping,  processNoCache,  processPath,  processPopulate,  processPreprocess,  processRoles,  processValidate` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="ACTION_CONTEXT_CLASS"></span>

### ACTION\_CONTEXT\_CLASS

    public static final String ACTION_CONTEXT_CLASS

Token for ActionContext clazss so that it can be stored in the ControllerConfig.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.ComposableRequestProcessor.ACTION_CONTEXT_CLASS)

------------------------------------------------------------------------

<span id="LOG"></span>

### LOG

    protected static final Log LOG

The `Log` instance for this class.

------------------------------------------------------------------------

<span id="catalogFactory"></span>

### catalogFactory

    protected org.apache.commons.chain.CatalogFactory catalogFactory

The `CatalogFactory` from which catalog containing the the base request-processing `Command` will be retrieved.

------------------------------------------------------------------------

<span id="catalog"></span>

### catalog

    protected org.apache.commons.chain.Catalog catalog

The `Catalog` containing all of the available command chains for this module.

------------------------------------------------------------------------

<span id="command"></span>

### command

    protected org.apache.commons.chain.Command command

The `Command` to be executed for each request.

<span id="constructor_detail"></span>

**Constructor Detail**

### ComposableRequestProcessor

    public ComposableRequestProcessor()

<span id="method_detail"></span>

**Method Detail**

### destroy

    public void destroy()

Clean up in preparation for a shutdown of this application.

**Overrides:**  
` destroy` in class `RequestProcessor`

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig moduleConfig)
              throws ServletException

Initialize this request processor instance.

**Overrides:**  
` init` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`servlet` - The ActionServlet we are associated with

`moduleConfig` - The ModuleConfig we are associated with.

**Throws:**  
`ServletException` - If an error occurs during initialization

------------------------------------------------------------------------

### initCatalogFactory

    protected void initCatalogFactory(ActionServlet servlet,
                                      ModuleConfig moduleConfig)

Establish the CatalogFactory which will be used to look up the catalog which has the request processing command.

The base implementation simply calls CatalogFactory.getInstance(), unless the catalogFactory property of this object has already been set, in which case it is not changed.

**Parameters:**  
`servlet` - The ActionServlet we are processing

`moduleConfig` - The ModuleConfig we are processing

------------------------------------------------------------------------

### process

    public void process(HttpServletRequest request,
                        HttpServletResponse response)
                 throws IOException,
                        ServletException

Process an `HttpServletRequest` and create the corresponding `HttpServletResponse`.

**Overrides:**  
` process` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a processing exception occurs

------------------------------------------------------------------------

### contextInstance

    protected ActionContext contextInstance(HttpServletRequest request,
                                            HttpServletResponse response)
                                     throws ServletException

Provide the initialized `ActionContext` instance which will be used by this request. Internally, this simply calls `createActionContextInstance` followed by `initializeActionContext`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Returns:**  
Initiliazed ActionContext

**Throws:**  
`ServletException` - if a processing exception occurs

------------------------------------------------------------------------

### createActionContextInstance

    protected ActionContext createActionContextInstance(ServletContext servletContext,
                                                        HttpServletRequest request,
                                                        HttpServletResponse response)
                                                 throws ServletException

Create a new instance of `ActionContext` according to configuration. If no alternative was specified at initialization, a new instance `ServletActionContext` is returned. If an alternative was specified using the `ACTION_CONTEXT_CLASS` property, then that value is treated as a classname, and an instance of that class is created. If that class implements the same constructor that `ServletActionContext` does, then that constructor will be used: `ServletContext, HttpServletRequest, HttpServletResponse`; otherwise, it is assumed that the class has a no-arguments constructor. If these constraints do not suit you, simply override this method in a subclass.

**Parameters:**  
`servletContext` - The servlet context we are processing

`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Returns:**  
New instance of ActionContext

**Throws:**  
`ServletException` - if a processing exception occurs

------------------------------------------------------------------------

### initializeActionContext

    protected void initializeActionContext(ActionContext context)

Set common properties on the given `ActionContext` instance so that commands in the chain can count on their presence. Note that while this method does not require that its argument be an instance of `ServletActionContext`, at this time many common Struts commands will be expecting to receive an `ActionContext` which is also a `ServletActionContext`.

**Parameters:**  
`context` - The ActionContext we are processing

------------------------------------------------------------------------

### processMultipart

    protected HttpServletRequest processMultipart(HttpServletRequest request)

If this is a multipart request, wrap it with a special wrapper. Otherwise, return the request unchanged.

**Overrides:**  
` processMultipart` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The HttpServletRequest we are processing

**Returns:**  
Original or wrapped request as appropriate

------------------------------------------------------------------------

### setCatalogFactory

    public void setCatalogFactory(org.apache.commons.chain.CatalogFactory catalogFactory)

Set the `CatalogFactory` instance which should be used to find the request-processing command. In the base implementation, if this value is not already set, then it will be initialized when [`initCatalogFactory(org.apache.struts.action.ActionServlet, org.apache.struts.config.ModuleConfig)`](../../../../org/apache/struts/chain/ComposableRequestProcessor.html.md#initCatalogFactory(org.apache.struts.action.ActionServlet,%20org.apache.struts.config.ModuleConfig)) is called.

**Parameters:**  
`catalogFactory` - Our CatalogFactory instance

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
<td align="left"><a href="class-use/ComposableRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/chain/Constants.html.md" title="class in org.apache.struts.chain"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/chain/ComposableRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="ComposableRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
