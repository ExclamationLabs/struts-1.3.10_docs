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
<td align="left"><a href="class-use/TilesUtilStrutsModulesImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/UntypedAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilStrutsModulesImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Class TilesUtilStrutsModulesImpl
---------------------------------

    java.lang.Object
      org.apache.struts.tiles.TilesUtilImpl
          org.apache.struts.tiles.TilesUtilStrutsImpl
              org.apache.struts.tiles.TilesUtilStrutsModulesImpl

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class TilesUtilStrutsModulesImpl

extends [TilesUtilStrutsImpl](../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html.md "class in org.apache.struts.tiles")

Implementation of TilesUtil for Struts multi modules. Methods in this implementation are aware of the Struts module context.

-   The method getFactory(...) returns the factory for the current Struts module.
-   Methods doForward() and doInclude() use their counterparts in the current RequestProcessor (todo).
-   The method createFactory(...) creates a factory for the current module and stores it under the appropriate property name.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.TilesUtilStrutsModulesImpl)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl"></span>

| **Fields inherited from class org.apache.struts.tiles.[TilesUtilImpl](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` DEFINITIONS_FACTORY, log`                                                                                                                                        |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` TilesUtilStrutsModulesImpl()` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do a forward using request dispatcher.

` void`

` doInclude(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do an include using request dispatcher.

` DefinitionsFactory`

` getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to specified moduleConfig.

` DefinitionsFactory`

` getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get the definition factory from appropriate servlet context.

`protected  ModuleConfig`

` getModuleConfig(HttpServletRequest request, ServletContext servletContext)`
           Get the current ModuleConfig.

`protected  TilesRequestProcessor`

` getRequestProcessor(HttpServletRequest request, ServletContext servletContext)`
           Get Tiles RequestProcessor associated to the current module.

`protected  void`

` makeDefinitionsFactoryAccessible(DefinitionsFactory factory, ServletContext servletContext)`
           Make definition factory accessible to tags.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl"></span>

| **Methods inherited from class org.apache.struts.tiles.[TilesUtilImpl](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createDefinitionFactoryInstance,  createDefinitionsFactory,  doInclude`                                                                                           |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesUtilStrutsModulesImpl

    public TilesUtilStrutsModulesImpl()

<span id="method_detail"></span>

**Method Detail**

### doForward

    public void doForward(String uri,
                          HttpServletRequest request,
                          HttpServletResponse response,
                          ServletContext servletContext)
                   throws IOException,
                          ServletException

Do a forward using request dispatcher. This method is used by the Tiles package anytime a forward is required.

**Overrides:**  
` doForward` in class `TilesUtilImpl`

<!-- -->

**Parameters:**  
`uri` - Uri or Definition name to forward.

`request` - Current page request.

`response` - Current page response.

`servletContext` - Current servlet context.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### doInclude

    public void doInclude(String uri,
                          HttpServletRequest request,
                          HttpServletResponse response,
                          ServletContext servletContext)
                   throws IOException,
                          ServletException

Do an include using request dispatcher. This method is used by the Tiles package anytime an include is required.

**Overrides:**  
` doInclude` in class `TilesUtilImpl`

<!-- -->

**Parameters:**  
`uri` - Uri or Definition name to forward.

`request` - Current page request.

`response` - Current page response.

`servletContext` - Current servlet context.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### getDefinitionsFactory

    public DefinitionsFactory getDefinitionsFactory(ServletRequest request,
                                                    ServletContext servletContext)

Get the definition factory from appropriate servlet context.

**Overrides:**  
` getDefinitionsFactory` in class `TilesUtilImpl`

<!-- -->

**Parameters:**  
`request` - Current request.

`servletContext` - Current servlet context.

**Returns:**  
Definitions factory or null if not found.

------------------------------------------------------------------------

### getDefinitionsFactory

    public DefinitionsFactory getDefinitionsFactory(ServletContext servletContext,
                                                    ModuleConfig moduleConfig)

Get definition factory for the module attached to specified moduleConfig.

**Overrides:**  
` getDefinitionsFactory` in class `TilesUtilStrutsImpl`

<!-- -->

**Parameters:**  
`servletContext` - Current servlet context.

`moduleConfig` - Module config of the module for which the factory is requested.

**Returns:**  
Definitions factory or null if not found.

------------------------------------------------------------------------

### makeDefinitionsFactoryAccessible

    protected void makeDefinitionsFactoryAccessible(DefinitionsFactory factory,
                                                    ServletContext servletContext)

Make definition factory accessible to tags. Factory is stored in servlet context.

**Overrides:**  
` makeDefinitionsFactoryAccessible` in class `TilesUtilImpl`

<!-- -->

**Parameters:**  
`factory` - Factory to be made accessible.

`servletContext` - Current servlet context.

------------------------------------------------------------------------

### getRequestProcessor

    protected TilesRequestProcessor getRequestProcessor(HttpServletRequest request,
                                                        ServletContext servletContext)

Get Tiles RequestProcessor associated to the current module.

**Parameters:**  
`request` - Current request.

`servletContext` - Current servlet context.

**Returns:**  
The [`TilesRequestProcessor`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md "class in org.apache.struts.tiles") for the current request.

------------------------------------------------------------------------

### getModuleConfig

    protected ModuleConfig getModuleConfig(HttpServletRequest request,
                                           ServletContext servletContext)

Get the current ModuleConfig.
 Lookup in the request and do selectModule if not found. The side effect is, that the ModuleConfig object is set in the request if it was not present.

**Parameters:**  
`request` - Current request.

`servletContext` - Current servlet context\*.

**Returns:**  
The ModuleConfig for current request.

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
<td align="left"><a href="class-use/TilesUtilStrutsModulesImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/UntypedAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilStrutsModulesImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
