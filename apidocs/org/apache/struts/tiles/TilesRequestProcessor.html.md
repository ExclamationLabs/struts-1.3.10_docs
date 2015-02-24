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
<td align="left"><a href="class-use/TilesRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesPlugin.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtil.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="TilesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles
 Class TilesRequestProcessor
----------------------------

    java.lang.Object
      org.apache.struts.action.RequestProcessor
          org.apache.struts.tiles.TilesRequestProcessor

**Direct Known Subclasses:**  
[FacesTilesRequestProcessor](../../../../org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md "class in org.apache.struts.faces.application")

------------------------------------------------------------------------

    public class TilesRequestProcessor

extends [RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")

**RequestProcessor** contains the processing logic that the Struts controller servlet performs as it receives each servlet request from the container.

This processor subclasses the Struts RequestProcessor in order to intercept calls to forward or include. When such calls are done, the Tiles processor checks if the specified URI is a definition name. If true, the definition is retrieved and included. If false, the original URI is included or a forward is performed.

Actually, catching is done by overloading the following methods:

-   [`processForwardConfig(HttpServletRequest,HttpServletResponse,ForwardConfig)`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md#processForwardConfig(javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20org.apache.struts.config.ForwardConfig))
-   [`internalModuleRelativeForward(String, HttpServletRequest , HttpServletResponse)`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md#internalModuleRelativeForward(java.lang.String,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse))
-   [`internalModuleRelativeInclude(String, HttpServletRequest , HttpServletResponse)`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md#internalModuleRelativeInclude(java.lang.String,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse))

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  DefinitionsFactory`

` definitionsFactory`
           Definitions factory.

`protected static Log`

` log`
           Commons Logging instance.

 <span id="fields_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Fields inherited from class org.apache.struts.action.[RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` actions,  INCLUDE_PATH_INFO,  INCLUDE_SERVLET_PATH,  moduleConfig,  servlet`                                                                                              |

  <span id="constructor_summary"></span>

| **Constructor Summary**    |
|----------------------------|
| ` TilesRequestProcessor()` 
                             |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do a forward using request dispatcher.

` DefinitionsFactory`

` getDefinitionsFactory()`
           Get associated definition factory.

` void`

` init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

`protected  void`

` initDefinitionsMapping()`
           Read component instance mapping configuration file.

`protected  void`

` internalModuleRelativeForward(String uri, HttpServletRequest request, HttpServletResponse response)`
           Catch the call to a module relative forward.

`protected  void`

` internalModuleRelativeInclude(String uri, HttpServletRequest request, HttpServletResponse response)`
           Do a module relative include to specified uri using request dispatcher.

`protected  void`

` processForwardConfig(HttpServletRequest request, HttpServletResponse response, ForwardConfig forward)`
           Overloaded method from Struts' RequestProcessor.

`protected  boolean`

` processTilesDefinition(String definitionName, boolean contextRelative, HttpServletRequest request, HttpServletResponse response)`
           **Deprecated.** *use processTilesDefinition(definitionName, request, response) instead. This method will be removed in a version after 1.3.0.*

`protected  boolean`

` processTilesDefinition(String definitionName, HttpServletRequest request, HttpServletResponse response)`
           Process a Tile definition name.

 <span id="methods_inherited_from_class_org.apache.struts.action.RequestProcessor"></span>

| **Methods inherited from class org.apache.struts.action.[RequestProcessor](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")**                                                                                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` destroy,  doInclude,  getInternal,  getServletContext,  process,  processActionCreate,  processActionForm,  processActionPerform,  processCachedMessages,  processContent,  processException,  processForward,  processInclude,  processLocale,  processMapping,  processMultipart,  processNoCache,  processPath,  processPopulate,  processPreprocess,  processRoles,  processValidate` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="definitionsFactory"></span>

### definitionsFactory

    protected DefinitionsFactory definitionsFactory

Definitions factory.

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesRequestProcessor

    public TilesRequestProcessor()

<span id="method_detail"></span>

**Method Detail**

### init

    public void init(ActionServlet servlet,
                     ModuleConfig moduleConfig)
              throws ServletException

Initialize this request processor instance.

**Overrides:**  
` init` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`servlet` - The ActionServlet we are associated with.

`moduleConfig` - The ModuleConfig we are associated with.

**Throws:**  
`ServletException` - If an error occurs during initialization.

------------------------------------------------------------------------

### initDefinitionsMapping

    protected void initDefinitionsMapping()
                                   throws ServletException

Read component instance mapping configuration file. This is where we read files properties.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### processTilesDefinition

    protected boolean processTilesDefinition(String definitionName,
                                             boolean contextRelative,
                                             HttpServletRequest request,
                                             HttpServletResponse response)
                                      throws IOException,
                                             ServletException

**Deprecated.** *use processTilesDefinition(definitionName, request, response) instead. This method will be removed in a version after 1.3.0.*

Process a Tile definition name. This method tries to process the parameter `definitionName` as a definition name. It returns `true` if a definition has been processed, or `false` otherwise. This method is deprecated; the method without the `contextRelative` parameter should be used instead.

**Parameters:**  
`definitionName` - Definition name to insert.

`contextRelative` - Is the definition marked contextRelative ?

`request` - Current page request.

`response` - Current page response.

**Returns:**  
`true` if the method has processed uri as a definition name, `false` otherwise.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### processTilesDefinition

    protected boolean processTilesDefinition(String definitionName,
                                             HttpServletRequest request,
                                             HttpServletResponse response)
                                      throws IOException,
                                             ServletException

Process a Tile definition name. This method tries to process the parameter `definitionName` as a definition name. It returns `true` if a definition has been processed, or `false` otherwise.

**Parameters:**  
`definitionName` - Definition name to insert.

`request` - Current page request.

`response` - Current page response.

**Returns:**  
`true` if the method has processed uri as a definition name, `false` otherwise.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### doForward

    protected void doForward(String uri,
                             HttpServletRequest request,
                             HttpServletResponse response)
                      throws IOException,
                             ServletException

Do a forward using request dispatcher. Uri is a valid uri. If response has already been commited, do an include instead.

**Overrides:**  
` doForward` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`uri` - Uri or Definition name to forward.

`request` - Current page request.

`response` - Current page response.

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

Overloaded method from Struts' RequestProcessor. Forward or redirect to the specified destination by the specified mechanism. This method catches the Struts' actionForward call. It checks if the actionForward is done on a Tiles definition name. If true, process the definition and insert it. If false, call the original parent's method.

**Overrides:**  
` processForwardConfig` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`request` - The servlet request we are processing.

`response` - The servlet response we are creating.

`forward` - The ActionForward controlling where we go next.

**Throws:**  
`IOException` - if an input/output error occurs.

`ServletException` - if a servlet exception occurs.

------------------------------------------------------------------------

### internalModuleRelativeForward

    protected void internalModuleRelativeForward(String uri,
                                                 HttpServletRequest request,
                                                 HttpServletResponse response)
                                          throws IOException,
                                                 ServletException

Catch the call to a module relative forward. If the specified uri is a tiles definition name, insert it. Otherwise, parent processing is called. Do a module relative forward to specified uri using request dispatcher. Uri is relative to the current module. The real uri is computed by prefixing the module name. **This method is used internally and is not part of the public API. It is advised to not use it in subclasses.**

**Overrides:**  
` internalModuleRelativeForward` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`uri` - Module-relative URI to forward to.

`request` - Current page request.

`response` - Current page response.

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

Do a module relative include to specified uri using request dispatcher. Uri is relative to the current module. The real uri is computed by prefixing the module name. **This method is used internally and is not part of the public API. It is advised to not use it in subclasses.**

**Overrides:**  
` internalModuleRelativeInclude` in class `RequestProcessor`

<!-- -->

**Parameters:**  
`uri` - Module-relative URI to forward to.

`request` - Current page request.

`response` - Current page response.

**Throws:**  
`IOException` - if an input/output error occurs

`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getDefinitionsFactory

    public DefinitionsFactory getDefinitionsFactory()

Get associated definition factory.

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
<td align="left"><a href="class-use/TilesRequestProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesPlugin.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtil.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="TilesRequestProcessor.html"><strong>NO FRAMES</strong></a>    
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
