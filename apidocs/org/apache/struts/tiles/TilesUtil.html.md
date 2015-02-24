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
<td align="left"><a href="class-use/TilesUtil.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtil.html"><strong>FRAMES</strong></a>    <a href="TilesUtil.html"><strong>NO FRAMES</strong></a>    
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
 Class TilesUtil
-----------------------

    java.lang.Object
      org.apache.struts.tiles.TilesUtil

**Direct Known Subclasses:**  
[DefinitionsUtil](../../../../org/apache/struts/tiles/DefinitionsUtil.html.md "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class TilesUtil

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Class containing utility methods for Tiles. Methods of this class are static and thereby accessible from anywhere. The underlying implementation can be changed with [`setTilesUtil(TilesUtilImpl)`](../../../../org/apache/struts/tiles/TilesUtil.html.md#setTilesUtil(org.apache.struts.tiles.TilesUtilImpl)).
 Real implementation classes should derive from the [`TilesUtilImpl`](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles") class.
 Some methods are specified to throw the `UnsupportedOperationException` if the underlying implementation doesn't support the operation.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Log`

`log`
           Commons Logging instance.

`protected static TilesUtilImpl`

`tilesUtilImpl`
           The implementation of tilesUtilImpl

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| `TilesUtil()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

`static DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do a forward using request dispatcher.

`static void`

` doInclude(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do an include using request dispatcher.

`static void`

` doInclude(String uri, PageContext pageContext)`
           Do an include using PageContext.include().

`static void`

` doInclude(String uri, PageContext pageContext, boolean flush)`
           Do an include using PageContext.include().

`static ComponentDefinition`

` getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

`static DefinitionsFactory`

` getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get definition factory from appropriate servlet context.

`static TilesUtilImpl`

` getTilesUtil()`
           Get the real implementation.

`static void`

` setTilesUtil(TilesUtilImpl tilesUtil)`
           Set the real implementation.

`protected static void`

`testReset()`
           Reset internal state.

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

------------------------------------------------------------------------

<span id="tilesUtilImpl"></span>

### tilesUtilImpl

    protected static TilesUtilImpl tilesUtilImpl

The implementation of tilesUtilImpl

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesUtil

    public TilesUtil()

<span id="method_detail"></span>

**Method Detail**

### getTilesUtil

    public static TilesUtilImpl getTilesUtil()

Get the real implementation.

**Returns:**  
The underlying implementation object.

------------------------------------------------------------------------

### setTilesUtil

    public static void setTilesUtil(TilesUtilImpl tilesUtil)

Set the real implementation. This method should be called only once. Successive calls have no effect.

**Parameters:**  
`tilesUtil` - The implementaion.

------------------------------------------------------------------------

### doForward

    public static void doForward(String uri,
                                 HttpServletRequest request,
                                 HttpServletResponse response,
                                 ServletContext servletContext)
                          throws IOException,
                                 ServletException

Do a forward using request dispatcher. This method is used by the Tiles package anytime a forward is required.

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

    public static void doInclude(String uri,
                                 HttpServletRequest request,
                                 HttpServletResponse response,
                                 ServletContext servletContext)
                          throws IOException,
                                 ServletException

Do an include using request dispatcher. This method is used by the Tiles package when an include is required. The Tiles package can use indifferently any form of this method.

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

    public static void doInclude(String uri,
                                 PageContext pageContext)
                          throws IOException,
                                 ServletException

Do an include using PageContext.include(). This method is used by the Tiles package when an include is required. The Tiles package can use indifferently any form of this method.

**Parameters:**  
`uri` - Uri or Definition name to forward.

`pageContext` - Current page context.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### doInclude

    public static void doInclude(String uri,
                                 PageContext pageContext,
                                 boolean flush)
                          throws IOException,
                                 ServletException

Do an include using PageContext.include(). This method is used by the Tiles package when an include is required. The Tiles package can use indifferently any form of this method.

**Parameters:**  
`uri` - Uri or Definition name to forward.

`flush` - If the writer should be flushed before the include

`pageContext` - Current page context.

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### getDefinitionsFactory

    public static DefinitionsFactory getDefinitionsFactory(ServletRequest request,
                                                           ServletContext servletContext)

Get definition factory from appropriate servlet context.

**Returns:**  
Definitions factory or `null` if not found.

------------------------------------------------------------------------

### createDefinitionsFactory

    public static DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                              DefinitionsFactoryConfig factoryConfig)
                                                       throws DefinitionsFactoryException

Create Definition factory from specified configuration object. Create a ConfigurableDefinitionsFactory and initialize it with the configuration object. This later can contain the factory classname to use. Factory is made accessible from tags.

Fallback of several factory creation methods.

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`factoryConfig` - Configuration object passed to factory.

**Returns:**  
newly created factory of type ConfigurableDefinitionsFactory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### getDefinition

    public static ComponentDefinition getDefinition(String definitionName,
                                                    ServletRequest request,
                                                    ServletContext servletContext)
                                             throws FactoryNotFoundException,
                                                    DefinitionsFactoryException

Get a definition by its name. First, retrieve definition factory and then get requested definition. Throw appropriate exception if definition or definition factory is not found.

**Parameters:**  
`definitionName` - Name of requested definition.

`request` - Current servelet request.

`servletContext` - current servlet context.

**Throws:**  
`FactoryNotFoundException` - Can't find definition factory.

`DefinitionsFactoryException` - General error in factory while getting definition.

`NoSuchDefinitionException` - No definition found for specified name

------------------------------------------------------------------------

### testReset

    protected static void testReset()

Reset internal state. This method is used by test suites to reset the class to its original state.

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
<td align="left"><a href="class-use/TilesUtil.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtil.html"><strong>FRAMES</strong></a>    <a href="TilesUtil.html"><strong>NO FRAMES</strong></a>    
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
