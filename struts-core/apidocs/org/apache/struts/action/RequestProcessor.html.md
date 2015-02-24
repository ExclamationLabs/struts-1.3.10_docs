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
<td align="left"><a href="class-use/RequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/RequestActionMapping.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/SessionActionMapping.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/RequestProcessor.html"><strong>FRAMES</strong></a>    <a href="RequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
 Class RequestProcessor
------------------------

    java.lang.Object
      org.apache.struts.action.RequestProcessor

**Direct Known Subclasses:**  
[ComposableRequestProcessor](../../../../org/apache/struts/chain/ComposableRequestProcessor.html.md "class in org.apache.struts.chain")

------------------------------------------------------------------------

    public class RequestProcessor

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

**RequestProcessor** contains the processing logic that the [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") performs as it receives each servlet request from the container. You can customize the request processing behavior by subclassing this class and overriding the method(s) whose behavior you are interested in changing.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 680350 $ $Date: 2008-07-28 08:32:29 -0500 (Mon, 28 Jul 2008) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  HashMap`

` actions`
           The set of `Action` instances that have been created and initialized, keyed by the fully qualified Java class name of the `Action` class.

`static String`

` INCLUDE_PATH_INFO`
           The request attribute under which the path information is stored for processing during a `RequestDispatcher.include` call.

`static String`

` INCLUDE_SERVLET_PATH`
           The request attribute under which the servlet path information is stored for processing during a `RequestDispatcher.include` call.

`protected static Log`

`log`
           Commons Logging instance.

`protected  ModuleConfig`

` moduleConfig`
           The `ModuleConfiguration` with which we are associated.

`protected  ActionServlet`

` servlet`
           The servlet with which we are associated.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` RequestProcessor()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` destroy()`
           Clean up in preparation for a shutdown of this application.

`protected  void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do a forward to specified URI using a `RequestDispatcher`.

`protected  void`

` doInclude(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do an include of specified URI using a `RequestDispatcher`.

`protected  MessageResources`

` getInternal()`
           Return the `MessageResources` instance containing our internal message strings.

`protected  ServletContext`

` getServletContext()`
           Return the `ServletContext` for the web application in which we are running.

` void`

` init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

`protected  void`

` internalModuleRelativeForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do a module relative forward to specified URI using request dispatcher.

`protected  void`

` internalModuleRelativeInclude(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do a module relative include to specified URI using request dispatcher.

` void`

` process(HttpServletRequest request, HttpServletResponse response)`
           Process an `HttpServletRequest` and create the corresponding `HttpServletResponse` or dispatch to another resource.

`protected  Action`

` processActionCreate(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

`protected  ActionForm`

` processActionForm(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary.

`protected  ActionForward`

` processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  void`

` processCachedMessages(HttpServletRequest request, HttpServletResponse response)`
           Removes any `ActionMessages` object stored in the session under `Globals.MESSAGE_KEY` and `Globals.ERROR_KEY` if the messages' `isAccessed` method returns true.

`protected  void`

` processContent(HttpServletRequest request, HttpServletResponse response)`
           Set the default content type (with optional character encoding) for all responses if requested.

`protected  ActionForward`

` processException(HttpServletRequest request, HttpServletResponse response, Exception exception, ActionForm form, ActionMapping mapping)`
           Ask our exception handler to handle the exception.

`protected  boolean`

` processForward(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process a forward requested by this mapping (if any).

`protected  void`

` processForwardConfig(HttpServletRequest request, HttpServletResponse response, ForwardConfig forward)`
           Forward or redirect to the specified destination, by the specified mechanism.

`protected  boolean`

` processInclude(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process an include requested by this mapping (if any).

`protected  void`

` processLocale(HttpServletRequest request, HttpServletResponse response)`
           Automatically select a `Locale` for the current user, if requested.

`protected  ActionMapping`

` processMapping(HttpServletRequest request, HttpServletResponse response, String path)`
           Select the mapping used to process the selection path for this request.

`protected  HttpServletRequest`

` processMultipart(HttpServletRequest request)`
           If this is a multipart request, wrap it with a special wrapper.

`protected  void`

` processNoCache(HttpServletRequest request, HttpServletResponse response)`
           Set the no-cache headers for all responses, if requested.

`protected  String`

` processPath(HttpServletRequest request, HttpServletResponse response)`
           Identify and return the path component (from the request URI) that we will use to select an `ActionMapping` with which to dispatch.

`protected  void`

` processPopulate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           Populate the properties of the specified `ActionForm` instance from the request parameters included with this request.

`protected  boolean`

` processPreprocess(HttpServletRequest request, HttpServletResponse response)`
           General-purpose preprocessing hook that can be overridden as required by subclasses.

`protected  boolean`

` processRoles(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           If this action is protected by security roles, make sure that the current user possesses at least one of them.

`protected  boolean`

` processValidate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           If this request was not cancelled, and the request's [`ActionMapping`](../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="INCLUDE_PATH_INFO"></span>

### INCLUDE\_PATH\_INFO

    public static final String INCLUDE_PATH_INFO

The request attribute under which the path information is stored for processing during a `RequestDispatcher.include` call.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.action.RequestProcessor.INCLUDE_PATH_INFO)

------------------------------------------------------------------------

<span id="INCLUDE_SERVLET_PATH"></span>

### INCLUDE\_SERVLET\_PATH

    public static final String INCLUDE_SERVLET_PATH

The request attribute under which the servlet path information is stored for processing during a `RequestDispatcher.include` call.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.action.RequestProcessor.INCLUDE_SERVLET_PATH)

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="actions"></span>

### actions

    protected HashMap actions

The set of `Action` instances that have been created and initialized, keyed by the fully qualified Java class name of the `Action` class.

------------------------------------------------------------------------

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

The `ModuleConfiguration` with which we are associated.

------------------------------------------------------------------------

<span id="servlet"></span>

### servlet

    protected ActionServlet servlet

The servlet with which we are associated.

<span id="constructor_detail"></span>

**Constructor Detail**

### RequestProcessor

    public RequestProcessor()

<span id="method_detail"></span>

**Method Detail**

### destroy

    public void destroy()

Clean up in preparation for a shutdown of this application.

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig moduleConfig)
              throws ServletException

Initialize this request processor instance.

**Parameters:**  
`servlet` - The ActionServlet we are associated with

`moduleConfig` - The ModuleConfig we are associated with.

**Throws:**  
`ServletException` - If an error occor during initialization

------------------------------------------------------------------------

### process

    public void process(HttpServletRequest request,
                        HttpServletResponse response)
                 throws IOException,
                        ServletException

Process an `HttpServletRequest` and create the corresponding `HttpServletResponse` or dispatch to another resource.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a processing exception occurs

------------------------------------------------------------------------

### processActionCreate

    protected Action processActionCreate(HttpServletRequest request,
                                         HttpServletResponse response,
                                         ActionMapping mapping)
                                  throws IOException

Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The mapping we are using

**Returns:**  
An `Action` instance that will be used to process the current request.

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### processActionForm

    protected ActionForm processActionForm(HttpServletRequest request,
                                           HttpServletResponse response,
                                           ActionMapping mapping)

Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary. If there is no `ActionForm` associated with this mapping, return `null`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The mapping we are using

**Returns:**  
The `ActionForm` associated with this mapping.

------------------------------------------------------------------------

### processForwardConfig

    protected void processForwardConfig(HttpServletRequest request,
                                        HttpServletResponse response,
                                        ForwardConfig forward)
                                 throws IOException,
                                        ServletException

Forward or redirect to the specified destination, by the specified mechanism. This method uses a `ForwardConfig` object instead an `ActionForward`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`forward` - The ForwardConfig controlling where we go next

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### processActionPerform

    protected ActionForward processActionPerform(HttpServletRequest request,
                                                 HttpServletResponse response,
                                                 Action action,
                                                 ActionForm form,
                                                 ActionMapping mapping)
                                          throws IOException,
                                                 ServletException

Ask the specified `Action` instance to handle this request. Return the `ActionForward` instance (if any) returned by the called `Action` for further processing.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`action` - The Action instance to be used

`form` - The ActionForm instance to pass to this Action

`mapping` - The ActionMapping instance to pass to this Action

**Returns:**  
The `ActionForward` instance (if any) returned by the called `Action`.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### processCachedMessages

    protected void processCachedMessages(HttpServletRequest request,
                                         HttpServletResponse response)

Removes any `ActionMessages` object stored in the session under `Globals.MESSAGE_KEY` and `Globals.ERROR_KEY` if the messages' `isAccessed` method returns true. This allows messages to be stored in the session, display one time, and be released here.

**Parameters:**  
`request` - The servlet request we are processing.

`response` - The servlet response we are creating.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### processContent

    protected void processContent(HttpServletRequest request,
                                  HttpServletResponse response)

Set the default content type (with optional character encoding) for all responses if requested. **NOTE** - This header will be overridden automatically if a `RequestDispatcher.forward` call is ultimately invoked.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

------------------------------------------------------------------------

### processException

    protected ActionForward processException(HttpServletRequest request,
                                             HttpServletResponse response,
                                             Exception exception,
                                             ActionForm form,
                                             ActionMapping mapping)
                                      throws IOException,
                                             ServletException

Ask our exception handler to handle the exception. Return the `ActionForward` instance (if any) returned by the called `ExceptionHandler`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are processing

`exception` - The exception being handled

`form` - The ActionForm we are processing

`mapping` - The ActionMapping we are using

**Returns:**  
The `ActionForward` instance (if any) returned by the called `ExceptionHandler`.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### processForward

    protected boolean processForward(HttpServletRequest request,
                                     HttpServletResponse response,
                                     ActionMapping mapping)
                              throws IOException,
                                     ServletException

Process a forward requested by this mapping (if any). Return `true` if standard processing should continue, or `false` if we have already handled this request.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The ActionMapping we are using

**Returns:**  
`true` to continue normal processing; `false` if a response has been created.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### processInclude

    protected boolean processInclude(HttpServletRequest request,
                                     HttpServletResponse response,
                                     ActionMapping mapping)
                              throws IOException,
                                     ServletException

Process an include requested by this mapping (if any). Return `true` if standard processing should continue, or `false` if we have already handled this request.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The ActionMapping we are using

**Returns:**  
`true` to continue normal processing; `false` if a response has been created.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if thrown by invoked methods

------------------------------------------------------------------------

### processLocale

    protected void processLocale(HttpServletRequest request,
                                 HttpServletResponse response)

Automatically select a `Locale` for the current user, if requested. **NOTE** - configuring Locale selection will trigger the creation of a new `HttpSession` if necessary.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

------------------------------------------------------------------------

### processMapping

    protected ActionMapping processMapping(HttpServletRequest request,
                                           HttpServletResponse response,
                                           String path)
                                    throws IOException

Select the mapping used to process the selection path for this request. If no mapping can be identified, create an error response and return `null`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`path` - The portion of the request URI for selecting a mapping

**Returns:**  
The mapping used to process the selection path for this request.

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### processMultipart

    protected HttpServletRequest processMultipart(HttpServletRequest request)

If this is a multipart request, wrap it with a special wrapper. Otherwise, return the request unchanged.

**Parameters:**  
`request` - The HttpServletRequest we are processing

**Returns:**  
A wrapped request, if the request is multipart; otherwise the original request.

------------------------------------------------------------------------

### processNoCache

    protected void processNoCache(HttpServletRequest request,
                                  HttpServletResponse response)

Set the no-cache headers for all responses, if requested. **NOTE** - This header will be overridden automatically if a `RequestDispatcher.forward` call is ultimately invoked.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

------------------------------------------------------------------------

### processPath

    protected String processPath(HttpServletRequest request,
                                 HttpServletResponse response)
                          throws IOException

Identify and return the path component (from the request URI) that we will use to select an `ActionMapping` with which to dispatch. If no such path can be identified, create an error response and return `null`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Returns:**  
The path that will be used to select an action mapping.

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### processPopulate

    protected void processPopulate(HttpServletRequest request,
                                   HttpServletResponse response,
                                   ActionForm form,
                                   ActionMapping mapping)
                            throws ServletException

Populate the properties of the specified `ActionForm` instance from the request parameters included with this request. In addition, request attribute `Globals.CANCEL_KEY` will be set if the request was submitted with a button created by `CancelTag`.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`form` - The ActionForm instance we are populating

`mapping` - The ActionMapping we are using

**Throws:**  
`ServletException` - if thrown by RequestUtils.populate()

------------------------------------------------------------------------

### processPreprocess

    protected boolean processPreprocess(HttpServletRequest request,
                                        HttpServletResponse response)

General-purpose preprocessing hook that can be overridden as required by subclasses. Return `true` if you want standard processing to continue, or `false` if the response has already been completed. The default implementation does nothing.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Returns:**  
`true` to continue normal processing; `false` if a response has been created.

------------------------------------------------------------------------

### processRoles

    protected boolean processRoles(HttpServletRequest request,
                                   HttpServletResponse response,
                                   ActionMapping mapping)
                            throws IOException,
                                   ServletException

If this action is protected by security roles, make sure that the current user possesses at least one of them. Return `true` to continue normal processing, or `false` if an appropriate response has been created and processing should terminate.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The mapping we are using

**Returns:**  
`true` to continue normal processing; `false` if a response has been created.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

------------------------------------------------------------------------

### processValidate

    protected boolean processValidate(HttpServletRequest request,
                                      HttpServletResponse response,
                                      ActionForm form,
                                      ActionMapping mapping)
                               throws IOException,
                                      ServletException,
                                      InvalidCancelException

If this request was not cancelled, and the request's [`ActionMapping`](../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors. Return `true` if we should continue processing, or `false` if we have already forwarded control back to the input form.

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`form` - The ActionForm instance we are populating

`mapping` - The ActionMapping we are using

**Returns:**  
`true` to continue normal processing; `false` if a response has been created.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

`InvalidCancelException` - if a cancellation is attempted without the proper action configuration.

------------------------------------------------------------------------

### internalModuleRelativeForward

    protected void internalModuleRelativeForward(String uri,
                                                 HttpServletRequest request,
                                                 HttpServletResponse response)
                                          throws IOException,
                                                 ServletException

Do a module relative forward to specified URI using request dispatcher. URI is relative to the current module. The real URI is compute by prefixing the module name.

This method is used internally and is not part of the public API. It is advised to not use it in subclasses.

**Parameters:**  
`uri` - Module-relative URI to forward to

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### internalModuleRelativeInclude

    protected void internalModuleRelativeInclude(String uri,
                                                 HttpServletRequest request,
                                                 HttpServletResponse response)
                                          throws IOException,
                                                 ServletException

Do a module relative include to specified URI using request dispatcher. URI is relative to the current module. The real URI is compute by prefixing the module name.

This method is used internally and is not part of the public API. It is advised to not use it in subclasses.

**Parameters:**  
`uri` - Module-relative URI to include

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### doForward

    protected void doForward(String uri,
                             HttpServletRequest request,
                             HttpServletResponse response)
                      throws IOException,
                             ServletException

Do a forward to specified URI using a `RequestDispatcher`. This method is used by all internal method needing to do a forward.

**Parameters:**  
`uri` - Context-relative URI to forward to

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### doInclude

    protected void doInclude(String uri,
                             HttpServletRequest request,
                             HttpServletResponse response)
                      throws IOException,
                             ServletException

Do an include of specified URI using a `RequestDispatcher`. This method is used by all internal method needing to do an include.

**Parameters:**  
`uri` - Context-relative URI to include

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getInternal

    protected MessageResources getInternal()

Return the `MessageResources` instance containing our internal message strings.

**Returns:**  
The `MessageResources` instance containing our internal message strings.

------------------------------------------------------------------------

### getServletContext

    protected ServletContext getServletContext()

Return the `ServletContext` for the web application in which we are running.

**Returns:**  
The `ServletContext` for the web application.

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
<td align="left"><a href="class-use/RequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/RequestActionMapping.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/SessionActionMapping.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/RequestProcessor.html"><strong>FRAMES</strong></a>    <a href="RequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
