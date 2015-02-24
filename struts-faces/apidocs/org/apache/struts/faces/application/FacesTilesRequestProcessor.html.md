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
<td align="left"><a href="class-use/FacesTilesRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/FacesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/PropertyResolverImpl.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/FacesTilesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="FacesTilesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
 Class FacesTilesRequestProcessor
-----------------------------------

    java.lang.Object
      org.apache.struts.action.RequestProcessor
          org.apache.struts.tiles.TilesRequestProcessor
              org.apache.struts.faces.application.FacesTilesRequestProcessor

------------------------------------------------------------------------

    public class FacesTilesRequestProcessor

extends [TilesRequestProcessor](http://struts.apache.org/apidocs/org/apache/struts/tiles/TilesRequestProcessor.html.md?is-external=true "class or interface in org.apache.struts.tiles")

Concrete implementation of `RequestProcessor` that implements the standard Struts request processing lifecycle on a request that was received as an `ActionEvent` by our associated `ActionListener`. It replaces the request processor instance normally configured by Struts+Tiles, so it must support non-Faces requests as well.

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

 <span id="fields_inherited_from_class_org.apache.struts.tiles.TilesRequestProcessor"></span>

| **Fields inherited from class org.apache.struts.tiles.[TilesRequestProcessor](http://struts.apache.org/apidocs/org/apache/struts/tiles/TilesRequestProcessor.html.md?is-external=true "class or interface in org.apache.struts.tiles")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `definitionsFactory`                                                                                                                                                                                                                  |

 <span id="fields_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Fields inherited from class org.apache.struts.action.[RequestProcessor](http://struts.apache.org/apidocs/org/apache/struts/action/RequestProcessor.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `actions, INCLUDE_PATH_INFO, INCLUDE_SERVLET_PATH, moduleConfig, servlet`                                                                                                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` FacesTilesRequestProcessor()` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Set up a Faces Request if we are not already processing one.

`protected  void`

` internalModuleRelativeForward(String uri, HttpServletRequest request, HttpServletResponse response)`
            

`protected  Action`

` processActionCreate(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
            

`protected  ActionForm`

` processActionForm(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
            

`protected  ActionForward`

` processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
            

`protected  boolean`

` processForward(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
            

`protected  void`

` processForwardConfig(HttpServletRequest request, HttpServletResponse response, ForwardConfig forward)`
            

`protected  boolean`

` processInclude(HttpServletRequest request, HttpServletResponse response, ActionMapping mapping)`
            

`protected  String`

` processPath(HttpServletRequest request, HttpServletResponse response)`
           Identify and return the path component (from the request URI for a non-Faces request, or from the form event for a Faces request) that we will use to select an ActionMapping to dispatch with.

`protected  void`

` processPopulate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
           Populate the properties of the specified `ActionForm` instance from the request parameters included with this request, **IF** this is a non-Faces request.

`protected  boolean`

` processValidate(HttpServletRequest request, HttpServletResponse response, ActionForm form, ActionMapping mapping)`
            

 <span id="methods_inherited_from_class_org.apache.struts.tiles.TilesRequestProcessor"></span>

| **Methods inherited from class org.apache.struts.tiles.[TilesRequestProcessor](http://struts.apache.org/apidocs/org/apache/struts/tiles/TilesRequestProcessor.html.md?is-external=true "class or interface in org.apache.struts.tiles")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getDefinitionsFactory, init, initDefinitionsMapping, internalModuleRelativeInclude, processTilesDefinition, processTilesDefinition`                                                                                                   |

 <span id="methods_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Methods inherited from class org.apache.struts.action.[RequestProcessor](http://struts.apache.org/apidocs/org/apache/struts/action/RequestProcessor.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `destroy, doInclude, getInternal, getServletContext, process, processCachedMessages, processContent, processException, processLocale, processMapping, processMultipart, processNoCache, processPreprocess, processRoles`        |

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
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.faces.application.FacesTilesRequestProcessor.LIFECYCLE_ID_ATTR)

<span id="constructor_detail"></span>

**Constructor Detail**

### FacesTilesRequestProcessor

    public FacesTilesRequestProcessor()

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
`doForward` in class `TilesRequestProcessor`

<!-- -->

**Parameters:**  
`uri` - Context-relative path to forward to

`request` - Current page request

`response` - Current page response

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet error occurs

------------------------------------------------------------------------

### internalModuleRelativeForward

    protected void internalModuleRelativeForward(String uri,
                                                 HttpServletRequest request,
                                                 HttpServletResponse response)
                                          throws IOException,
                                                 ServletException

**Overrides:**  
`internalModuleRelativeForward` in class `TilesRequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processActionCreate

    protected Action processActionCreate(HttpServletRequest request,
                                         HttpServletResponse response,
                                         ActionMapping mapping)
                                  throws IOException

**Overrides:**  
`processActionCreate` in class `RequestProcessor`

<!-- -->

**Throws:**  
`IOException`

------------------------------------------------------------------------

### processActionForm

    protected ActionForm processActionForm(HttpServletRequest request,
                                           HttpServletResponse response,
                                           ActionMapping mapping)

**Overrides:**  
`processActionForm` in class `RequestProcessor`

------------------------------------------------------------------------

### processActionPerform

    protected ActionForward processActionPerform(HttpServletRequest request,
                                                 HttpServletResponse response,
                                                 Action action,
                                                 ActionForm form,
                                                 ActionMapping mapping)
                                          throws IOException,
                                                 ServletException

**Overrides:**  
`processActionPerform` in class `RequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processForward

    protected boolean processForward(HttpServletRequest request,
                                     HttpServletResponse response,
                                     ActionMapping mapping)
                              throws IOException,
                                     ServletException

**Overrides:**  
`processForward` in class `RequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processForwardConfig

    protected void processForwardConfig(HttpServletRequest request,
                                        HttpServletResponse response,
                                        ForwardConfig forward)
                                 throws IOException,
                                        ServletException

**Overrides:**  
`processForwardConfig` in class `TilesRequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processInclude

    protected boolean processInclude(HttpServletRequest request,
                                     HttpServletResponse response,
                                     ActionMapping mapping)
                              throws IOException,
                                     ServletException

**Overrides:**  
`processInclude` in class `RequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processPath

    protected String processPath(HttpServletRequest request,
                                 HttpServletResponse response)
                          throws IOException

Identify and return the path component (from the request URI for a non-Faces request, or from the form event for a Faces request) that we will use to select an ActionMapping to dispatch with. If no such path can be identified, create an error response and return `null`.

**Overrides:**  
`processPath` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing

`response` - The servlet response we are creating

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
`processPopulate` in class `RequestProcessor`

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

**Overrides:**  
`processValidate` in class `RequestProcessor`

<!-- -->

**Throws:**  
`IOException`

`ServletException`

`InvalidCancelException`

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
<td align="left"><a href="class-use/FacesTilesRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/FacesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/PropertyResolverImpl.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/FacesTilesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="FacesTilesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
