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
<td align="left"><a href="class-use/TilesUtilImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtil.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilImpl.html"><strong>NO FRAMES</strong></a>    
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
 Class TilesUtilImpl
-----------------------

    java.lang.Object
      org.apache.struts.tiles.TilesUtilImpl

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[TilesUtilStrutsImpl](../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html.md "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class TilesUtilImpl

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Default implementation of TilesUtil. This class contains default implementation of utilities. This implementation is intended to be used without Struts.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.TilesUtilImpl)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` DEFINITIONS_FACTORY`
           Constant name used to store factory in servlet context

`protected static Log`

`log`
           Commons Logging instance.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TilesUtilImpl()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  DefinitionsFactory`

` createDefinitionFactoryInstance(String classname)`
           Create Definition factory of specified classname.

` DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

` void`

` doForward(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do a forward using request dispatcher.

` void`

` doInclude(String uri, HttpServletRequest request, HttpServletResponse response, ServletContext servletContext)`
           Do an include using request dispatcher.

` void`

` doInclude(String uri, PageContext pageContext, boolean flush)`
           Do an include using PageContext.include().

` DefinitionsFactory`

` getDefinitionsFactory(ServletRequest request, ServletContext servletContext)`
           Get definition factory from appropriate servlet context.

`protected  void`

` makeDefinitionsFactoryAccessible(DefinitionsFactory factory, ServletContext servletContext)`
           Make definition factory accessible to Tags.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static final Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="DEFINITIONS_FACTORY"></span>

### DEFINITIONS\_FACTORY

    public static final String DEFINITIONS_FACTORY

Constant name used to store factory in servlet context

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.TilesUtilImpl.DEFINITIONS_FACTORY)

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesUtilImpl

    public TilesUtilImpl()

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

**Parameters:**  
`uri` - Uri or Definition name to forward.

`request` - Current page request.

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

    public void doInclude(String uri,
                          PageContext pageContext,
                          boolean flush)
                   throws IOException,
                          ServletException

Do an include using PageContext.include(). This method is used by the Tiles package when an include is required. The Tiles package can use indifferently any form of this method.

**Parameters:**  
`uri` - Uri or Definition name to forward.

`pageContext` - Current page context.

`flush` - If the writer should be flushed before the include

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### getDefinitionsFactory

    public DefinitionsFactory getDefinitionsFactory(ServletRequest request,
                                                    ServletContext servletContext)

Get definition factory from appropriate servlet context.

**Returns:**  
Definitions factory or `null` if not found.

------------------------------------------------------------------------

### createDefinitionsFactory

    public DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                       DefinitionsFactoryConfig factoryConfig)
                                                throws DefinitionsFactoryException

Create Definition factory from specified configuration object. Create an instance of the factory with the class specified in the config object. Then, initialize this factory and finally store the factory in appropriate context by calling [`makeDefinitionsFactoryAccessible(DefinitionsFactory, ServletContext)`](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md#makeDefinitionsFactoryAccessible(org.apache.struts.tiles.DefinitionsFactory,%20javax.servlet.ServletContext)). Factory creation is done by [`createDefinitionFactoryInstance(String)`](../../../../org/apache/struts/tiles/TilesUtilImpl.html#createDefinitionFactoryInstance(java.lang.String)).

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`factoryConfig` - Configuration object passed to factory.

**Returns:**  
newly created factory of type specified in the config object.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createDefinitionFactoryInstance

    protected DefinitionsFactory createDefinitionFactoryInstance(String classname)
                                                          throws DefinitionsFactoryException

Create Definition factory of specified classname. Factory class must extend the [`DefinitionsFactory`](../../../../org/apache/struts/tiles/DefinitionsFactory.html.md "interface in org.apache.struts.tiles") class. The factory is wrapped appropriately with [`ComponentDefinitionsFactoryWrapper`](../../../../org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html "class in org.apache.struts.tiles.definition") if it is an instance of the deprecated ComponentDefinitionsFactory class.

**Parameters:**  
`classname` - Class name of the factory to create.

**Returns:**  
newly created factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### makeDefinitionsFactoryAccessible

    protected void makeDefinitionsFactoryAccessible(DefinitionsFactory factory,
                                                    ServletContext servletContext)

Make definition factory accessible to Tags. Factory is stored in servlet context.

**Parameters:**  
`factory` - Factory to be made accessible.

`servletContext` - Current servlet context.

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
<td align="left"><a href="class-use/TilesUtilImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtil.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilImpl.html"><strong>NO FRAMES</strong></a>    
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
