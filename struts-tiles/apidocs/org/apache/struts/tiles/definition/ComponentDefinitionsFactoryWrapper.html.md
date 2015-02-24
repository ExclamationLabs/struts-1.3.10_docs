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
<td align="left"><a href="class-use/ComponentDefinitionsFactoryWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html.md" title="class in org.apache.struts.tiles.definition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactoryWrapper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.definition
 Class ComponentDefinitionsFactoryWrapper
-----------------------------------------

    java.lang.Object
      org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class ComponentDefinitionsFactoryWrapper

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [DefinitionsFactory](../../../../../org/apache/struts/tiles/DefinitionsFactory.html.md "interface in org.apache.struts.tiles")

Wrapper from new definition factory interface to old interface. This class provides mapping from the old interface's life cycle to the new life cycle.

**Since:**  
20020708

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                    |
|----------------------------------------------------------------------------|
| ` ComponentDefinitionsFactoryWrapper()`                                    
            Constructor.                                                     |
| ` ComponentDefinitionsFactoryWrapper(ComponentDefinitionsFactory factory)` 
            Constructor.                                                     |

  <span id="method_summary"></span>

**Method Summary**

`static Map`

` createConfigMap(DefinitionsFactoryConfig config)`
           Create map of configuration attributes from configuration object.

`protected  ComponentDefinitionsFactory`

` createFactoryInstance(String classname)`
           Create Definition factory from provided classname which must implement [`ComponentDefinitionsFactory`](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles").

` void`

` destroy()`
           Do nothing because old life cycle has no equivalent.

` DefinitionsFactoryConfig`

` getConfig()`
           Get underlying factory configuration.

` ComponentDefinition`

` getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get requested definition.

` ComponentDefinitionsFactory`

` getInternalFactory()`
           Get internal factory.

` void`

` init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Call underlying factory init method.

` void`

` setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set underlying factory configuration.

` String`

` toString()`
           Return String representation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ComponentDefinitionsFactoryWrapper

    public ComponentDefinitionsFactoryWrapper(ComponentDefinitionsFactory factory)

Constructor. Create new wrapper for specified factory.

**Parameters:**  
`factory` - The factory to create a wrapper for.

------------------------------------------------------------------------

### ComponentDefinitionsFactoryWrapper

    public ComponentDefinitionsFactoryWrapper()

Constructor. Create new wrapper. The config object passed to init method should reference a factory implementing [`ComponentDefinitionsFactory`](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles").

<span id="method_detail"></span>

**Method Detail**

### getDefinition

    public ComponentDefinition getDefinition(String name,
                                             ServletRequest request,
                                             ServletContext servletContext)
                                      throws NoSuchDefinitionException,
                                             DefinitionsFactoryException

Get requested definition.

**Specified by:**  
` getDefinition` in interface `DefinitionsFactory`

<!-- -->

**Parameters:**  
`name` - Name of the definition.

`request` - The request we are processing.

`servletContext` - Our servlet context.

**Returns:**  
ComponentDefition

**Throws:**  
`NoSuchDefinitionException` - No definition found for specified name Implementation can throw more accurate exception as a subclass of this exception

`DefinitionsFactoryException` - An error occur while getting definition.

------------------------------------------------------------------------

### init

    public void init(DefinitionsFactoryConfig config,
                     ServletContext servletContext)
              throws DefinitionsFactoryException

Call underlying factory init method.

**Specified by:**  
` init` in interface `DefinitionsFactory`

<!-- -->

**Parameters:**  
`config` - DefinitionsFactoryConfig.

`servletContext` - Our servlet context.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### destroy

    public void destroy()

Do nothing because old life cycle has no equivalent.

**Specified by:**  
` destroy` in interface `DefinitionsFactory`

------------------------------------------------------------------------

### setConfig

    public void setConfig(DefinitionsFactoryConfig config,
                          ServletContext servletContext)
                   throws DefinitionsFactoryException

Set underlying factory configuration.

**Specified by:**  
` setConfig` in interface `DefinitionsFactory`

<!-- -->

**Parameters:**  
`config` - DefinitionsFactoryConfig to use.

`servletContext` - Our servlet context.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### getConfig

    public DefinitionsFactoryConfig getConfig()

Get underlying factory configuration.

**Specified by:**  
` getConfig` in interface `DefinitionsFactory`

<!-- -->

**Returns:**  
DefinitionsFactoryConfig.

------------------------------------------------------------------------

### getInternalFactory

    public ComponentDefinitionsFactory getInternalFactory()

Get internal factory.

**Returns:**  
The internal ComponentDefitionsFactory.

------------------------------------------------------------------------

### createFactoryInstance

    protected ComponentDefinitionsFactory createFactoryInstance(String classname)
                                                         throws DefinitionsFactoryException

Create Definition factory from provided classname which must implement [`ComponentDefinitionsFactory`](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles"). Factory class must extend [`DefinitionsFactory`](../../../../../org/apache/struts/tiles/DefinitionsFactory.html "interface in org.apache.struts.tiles").

**Parameters:**  
`classname` - Class name of the factory to create.

**Returns:**  
newly created factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### toString

    public String toString()

Return String representation. Calls toString() on underlying factory.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
String representation.

------------------------------------------------------------------------

### createConfigMap

    public static Map createConfigMap(DefinitionsFactoryConfig config)

Create map of configuration attributes from configuration object. Mapping is done between old names and new names.

**Parameters:**  
`config` - The DefinitionsFactoryConfig to use.

**Returns:**  
Map Map of name/value pairs.

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
<td align="left"><a href="class-use/ComponentDefinitionsFactoryWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html.md" title="class in org.apache.struts.tiles.definition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactoryWrapper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
