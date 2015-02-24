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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/FacesRequestProcessor.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/ActionListenerImpl.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/FacesTilesRequestProcessor.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/FacesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="FacesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.application
 Class FacesRequestProcessor
-----------------------------------

    java.lang.Object
      org.apache.struts.action.RequestProcessor
          org.apache.struts.faces.application.FacesRequestProcessor

------------------------------------------------------------------------

    public class FacesRequestProcessor

extends [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")

Concrete implementation of `RequestProcessor` that implements the standard Struts request processing lifecycle on a request that was received as an `ActionEvent` by our associated `ActionListener`. It replaces the request processor instance normally configured by Struts, so it must support non-Faces requests as well.

**Version:**  
$Rev: 473326 $ $Date: 2006-11-10 06:58:06 -0600 (Fri, 10 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` LIFECYCLE_ID_ATTR`
           The lifecycle id.

`protected static Log`

` log`
           The log instance for this class.

 <span id="fields_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Fields inherited from class org.apache.struts.action.[RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` actions,  INCLUDE_PATH_INFO,  INCLUDE_SERVLET_PATH,  moduleConfig,  servlet`                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary**    |
|----------------------------|
| ` FacesRequestProcessor()` 
                             |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Set up a Faces Request if we are not already processing one.

`protected  Action`

` processActionCreate(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

`protected  ActionForm`

` processActionForm(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary.

`protected  ActionForward`

` processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  boolean`

` processForward(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process a forward requested by this mapping (if any).

`protected  void`

` processForwardConfig(HttpServletRequest request, HttpServletResponse response, ForwardConfig forward)`
           Forward or redirect to the specified destination, by the specified mechanism.

`protected  boolean`

` processInclude(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
           Process an include requested by this mapping (if any).

`protected  String`

` processPath(HttpServletRequest request, HttpServletResponse response)`
           Identify and return the path component (from the request URI for a non-Faces request, or from the form event for a Faces request) that we will use to select an ActionMapping to dispatch with.

`protected  void`

` processPopulate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           Populate the properties of the specified `ActionForm` instance from the request parameters included with this request, **IF** this is a non-Faces request.

`protected  boolean`

` processValidate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           If this request was not cancelled, and the request's [`ActionMapping`](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors.

 <span id="methods_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Methods inherited from class org.apache.struts.action.[RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")**                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` destroy,  doInclude,  getInternal,  getServletContext,  init,  internalModuleRelativeForward,  internalModuleRelativeInclude,  process,  processCachedMessages,  processContent,  processException,  processLocale,  processMapping,  processMultipart,  processNoCache,  processPreprocess,  processRoles` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

The log instance for this class.

------------------------------------------------------------------------

<span id="LIFECYCLE_ID_ATTR"></span>

### LIFECYCLE\_ID\_ATTR

    public static final String LIFECYCLE_ID_ATTR

The lifecycle id.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.faces.application.FacesRequestProcessor.LIFECYCLE_ID_ATTR)

<span id="constructor_detail"></span>

**Constructor Detail**

### FacesRequestProcessor

    public FacesRequestProcessor()

<span id="method_detail"></span>

**Method Detail**

### doForward

    protected void doForward(String uri,
                             HttpServletRequest request,
                             HttpServletResponse response)
                      throws IOException,
                             ServletException

Set up a Faces Request if we are not already processing one. Next, create a new view if the specified `uri` is different from the current view identifier. Finally, cause the new view to be rendered, and call `FacesContext.responseComplete()` to indicate that this has already been done.

**Overrides:**  
` doForward` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`uri` - Context-relative path to forward to

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet error occurs

------------------------------------------------------------------------

### processActionCreate

    protected Action processActionCreate(HttpServletRequest request,
                                         HttpServletResponse response,
                                         ActionMapping mapping)
                                  throws IOException

**Description copied from class: ` RequestProcessor`**

Return an `Action` instance that will be used to process the current request, creating a new one if necessary.

**Overrides:**  
` processActionCreate` in class `RequestProcessor`

<!-- -->

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

**Description copied from class: ` RequestProcessor`**

Retrieve and return the `ActionForm` associated with this mapping, creating and retaining one if necessary. If there is no `ActionForm` associated with this mapping, return `null`.

**Overrides:**  
` processActionForm` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`mapping` - The mapping we are using

**Returns:**  
The `ActionForm` associated with this mapping.

------------------------------------------------------------------------

### processActionPerform

    protected ActionForward processActionPerform(HttpServletRequest request,
                                                 HttpServletResponse response,
                                                 Action action,
                                                 ActionForm form,
                                                 ActionMapping mapping)
                                          throws IOException,
                                                 ServletException

**Description copied from class: ` RequestProcessor`**

Ask the specified `Action` instance to handle this request. Return the `ActionForward` instance (if any) returned by the called `Action` for further processing.

**Overrides:**  
` processActionPerform` in class `RequestProcessor`

<!-- -->

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

### processForward

    protected boolean processForward(HttpServletRequest request,
                                     HttpServletResponse response,
                                     ActionMapping mapping)
                              throws IOException,
                                     ServletException

**Description copied from class: ` RequestProcessor`**

Process a forward requested by this mapping (if any). Return `true` if standard processing should continue, or `false` if we have already handled this request.

**Overrides:**  
` processForward` in class `RequestProcessor`

<!-- -->

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

### processForwardConfig

    protected void processForwardConfig(HttpServletRequest request,
                                        HttpServletResponse response,
                                        ForwardConfig forward)
                                 throws IOException,
                                        ServletException

**Description copied from class: ` RequestProcessor`**

Forward or redirect to the specified destination, by the specified mechanism. This method uses a `ForwardConfig` object instead an `ActionForward`.

**Overrides:**  
` processForwardConfig` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`forward` - The ForwardConfig controlling where we go next

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

**Description copied from class: ` RequestProcessor`**

Process an include requested by this mapping (if any). Return `true` if standard processing should continue, or `false` if we have already handled this request.

**Overrides:**  
` processInclude` in class `RequestProcessor`

<!-- -->

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

### processPath

    protected String processPath(HttpServletRequest request,
                                 HttpServletResponse response)
                          throws IOException

Identify and return the path component (from the request URI for a non-Faces request, or from the form event for a Faces request) that we will use to select an ActionMapping to dispatch with. If no such path can be identified, create an error response and return `null`.

**Overrides:**  
` processPath` in class `RequestProcessor`

<!-- -->

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

Populate the properties of the specified `ActionForm` instance from the request parameters included with this request, **IF** this is a non-Faces request. For a Faces request, this will have already been done by the *Update Model Values* phase of the request processing lifecycle, so all we have to do is recognize whether the request was cancelled or not.

**Overrides:**  
` processPopulate` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

`form` - The ActionForm instance we are populating

`mapping` - The ActionMapping we are using

**Throws:**  
`ServletException` - if thrown by RequestUtils.populate()

------------------------------------------------------------------------

### processValidate

    protected boolean processValidate(HttpServletRequest request,
                                      HttpServletResponse response,
                                      ActionForm form,
                                      ActionMapping mapping)
                               throws IOException,
                                      ServletException,
                                      InvalidCancelException

**Description copied from class: ` RequestProcessor`**

If this request was not cancelled, and the request's [`ActionMapping`](../../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") has not disabled validation, call the `validate` method of the specified [`ActionForm`](../../../../../org/apache/struts/action/ActionForm.html "class in org.apache.struts.action"), and forward to the input path if there were any errors. Return `true` if we should continue processing, or `false` if we have already forwarded control back to the input form.

**Overrides:**  
` processValidate` in class `RequestProcessor`

<!-- -->

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/FacesRequestProcessor.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/ActionListenerImpl.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/FacesTilesRequestProcessor.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/FacesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="FacesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
