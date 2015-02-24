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
<td align="left"><a href="class-use/DefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionNameAttribute.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Interface DefinitionsFactory
-----------------------------

**All Superinterfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**All Known Implementing Classes:**  
[ComponentDefinitionsFactoryWrapper](../../../../org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md "class in org.apache.struts.tiles.definition")

------------------------------------------------------------------------

    public interface DefinitionsFactory

extends [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Tiles Definition factory. This interface replace old ComponentDefinitionsFactory. Main method getDefinition() is exactly the same. Initialization method change. This interface allows to retrieve a definition by its name, independently of the factory implementation. Object life cycle is as follow:

-   Constructor: create object
-   setConfig: set config and initialize factory. After first call to this method, factory is operational.
-   destroy: factory is being shutdown.

Implementation must be Serializable, in order to be compliant with web Container having this constraint (Weblogic 6.x).

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

` destroy()`
           Receive notification that the factory is being shut down.

` DefinitionsFactoryConfig`

` getConfig()`
           Get factory configuration.

` ComponentDefinition`

` getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` void`

` init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Init definition factory.

` void`

` setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set factory configuration.

 

<span id="method_detail"></span>

**Method Detail**

### getDefinition

    ComponentDefinition getDefinition(String name,
                                      ServletRequest request,
                                      ServletContext servletContext)
                                      throws NoSuchDefinitionException,
                                             DefinitionsFactoryException

Get a definition by its name.

**Parameters:**  
`name` - Name of requested definition.

`request` - Current servelet request

`servletContext` - current servlet context

**Throws:**  
`DefinitionsFactoryException` - An error occur while getting definition.

`NoSuchDefinitionException` - No definition found for specified name Implementation can throw more accurate exception as a subclass of this exception

------------------------------------------------------------------------

### init

    void init(DefinitionsFactoryConfig config,
              ServletContext servletContext)
              throws DefinitionsFactoryException

Init definition factory. This method is called immediately after factory creation, and prior any call to setConfig().

**Parameters:**  
`config` - Configuration object used to set factory configuration.

`servletContext` - Servlet Context passed to factory.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### destroy

    void destroy()

Receive notification that the factory is being shut down.

------------------------------------------------------------------------

### setConfig

    void setConfig(DefinitionsFactoryConfig config,
                   ServletContext servletContext)
                   throws DefinitionsFactoryException

Set factory configuration. This method is used to change factory configuration. This method is optional, and can send an exception if implementation doesn't allow change in configuration.

**Parameters:**  
`config` - Configuration object used to set factory configuration.

`servletContext` - Servlet Context passed to factory.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### getConfig

    DefinitionsFactoryConfig getConfig()

Get factory configuration.

**Returns:**  
TilesConfig

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
<td align="left"><a href="class-use/DefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionNameAttribute.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
