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
<td align="left"><a href="class-use/ReloadableDefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md" title="class in org.apache.struts.tiles.definition"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ReloadableDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.definition
 Class ReloadableDefinitionsFactory
-----------------------------------

    java.lang.Object
      org.apache.struts.tiles.definition.ReloadableDefinitionsFactory

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class ReloadableDefinitionsFactory

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles")

A reloadable factory. This factory is the main entrance to any factory implementation. It takes in charge real implementation instance, and allows reloading by creating a new instance.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.definition.ReloadableDefinitionsFactory)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` DEFINITIONS_FACTORY_CLASSNAME`
           Name of init property carrying factory class name.

`protected  ComponentDefinitionsFactory`

` factory`
           The real factory instance.

`protected  Map`

` properties`
           Initialization parameters.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                     |
|---------------------------------------------------------------------------------------------|
| ` ReloadableDefinitionsFactory(ServletContext servletContext, Map properties)`              
            Constructor.                                                                      |
| ` ReloadableDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)` 
            Constructor.                                                                      |

  <span id="method_summary"></span>

**Method Summary**

` ComponentDefinitionsFactory`

` createDefaultFactory(ServletContext servletContext, Map properties)`
           Create default Definition factory.

` ComponentDefinitionsFactory`

` createFactory(ServletContext servletContext, Map properties)`
           Create Definition factory.

` ComponentDefinitionsFactory`

` createFactoryFromClassname(ServletContext servletContext, Map properties, String classname)`
           Create Definition factory from provided classname.

` ComponentDefinition`

` getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinitionsFactory`

` getFactory()`
           Get underlying factory instance.

` void`

` initFactory(ServletContext servletContext, Map properties)`
           Init factory.

` void`

` reload(ServletContext servletContext)`
           Reload underlying factory.

` String`

` toString()`
           Return String representation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="factory"></span>

### factory

    protected ComponentDefinitionsFactory factory

The real factory instance.

------------------------------------------------------------------------

<span id="properties"></span>

### properties

    protected Map properties

Initialization parameters.

------------------------------------------------------------------------

<span id="DEFINITIONS_FACTORY_CLASSNAME"></span>

### DEFINITIONS\_FACTORY\_CLASSNAME

    public static final String DEFINITIONS_FACTORY_CLASSNAME

Name of init property carrying factory class name.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.definition.ReloadableDefinitionsFactory.DEFINITIONS_FACTORY_CLASSNAME)

<span id="constructor_detail"></span>

**Constructor Detail**

### ReloadableDefinitionsFactory

    public ReloadableDefinitionsFactory(ServletContext servletContext,
                                        ServletConfig servletConfig)
                                 throws DefinitionsFactoryException

Constructor. Create a factory according to servlet settings.

**Parameters:**  
`servletContext` - Our servlet context.

`servletConfig` - Our servlet config.

**Throws:**  
`DefinitionsFactoryException` - If factory creation fail.

------------------------------------------------------------------------

### ReloadableDefinitionsFactory

    public ReloadableDefinitionsFactory(ServletContext servletContext,
                                        Map properties)
                                 throws DefinitionsFactoryException

Constructor. Create a factory according to servlet settings.

**Parameters:**  
`servletContext` - Our servlet context.

`properties` - Map containing all properties.

**Throws:**  
`DefinitionsFactoryException` - If factory creation fail.

<span id="method_detail"></span>

**Method Detail**

### createFactoryFromClassname

    public ComponentDefinitionsFactory createFactoryFromClassname(ServletContext servletContext,
                                                                  Map properties,
                                                                  String classname)
                                                           throws DefinitionsFactoryException

Create Definition factory from provided classname. If a factory class name is provided, a factory of this class is created. Otherwise, a default factory is created. Factory must have a constructor taking ServletContext and Map as parameter.

**Parameters:**  
`classname` - Class name of the factory to create.

`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property passed to newly created factory.

**Returns:**  
newly created factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createDefaultFactory

    public ComponentDefinitionsFactory createDefaultFactory(ServletContext servletContext,
                                                            Map properties)
                                                     throws DefinitionsFactoryException

Create default Definition factory. Factory must have a constructor taking ServletContext and Map as parameter. In this implementation, default factory is of class I18nFactorySet

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property passed to newly created factory.

**Returns:**  
newly created factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createFactory

    public ComponentDefinitionsFactory createFactory(ServletContext servletContext,
                                                     Map properties)
                                              throws DefinitionsFactoryException

Create Definition factory. Convenience method. ServletConfig is wrapped into a Map allowing retrieval of init parameters. Factory classname is also retrieved, as well as debug level. Finally, approriate createDefinitionsFactory() is called.

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map containing all properties.

**Throws:**  
`DefinitionsFactoryException`

------------------------------------------------------------------------

### getDefinition

    public ComponentDefinition getDefinition(String definitionName,
                                             ServletRequest request,
                                             ServletContext servletContext)
                                      throws FactoryNotFoundException,
                                             DefinitionsFactoryException

Get a definition by its name. Call appropriate method on underlying factory instance. Throw appropriate exception if definition or definition factory is not found.

**Specified by:**  
` getDefinition` in interface `ComponentDefinitionsFactory`

<!-- -->

**Parameters:**  
`definitionName` - Name of requested definition.

`request` - Current servlet request.

`servletContext` - Current servlet context.

**Throws:**  
`FactoryNotFoundException` - Can't find definition factory.

`DefinitionsFactoryException` - General error in factory while getting definition.

------------------------------------------------------------------------

### reload

    public void reload(ServletContext servletContext)
                throws DefinitionsFactoryException

Reload underlying factory. Reload is done by creating a new factory instance, and replacing the old instance with the new one.

**Parameters:**  
`servletContext` - Current servlet context.

**Throws:**  
`DefinitionsFactoryException` - If factory creation fails.

------------------------------------------------------------------------

### getFactory

    public ComponentDefinitionsFactory getFactory()

Get underlying factory instance.

**Returns:**  
ComponentDefinitionsFactory

------------------------------------------------------------------------

### initFactory

    public void initFactory(ServletContext servletContext,
                            Map properties)
                     throws DefinitionsFactoryException

Init factory. This method is required by interface ComponentDefinitionsFactory. It is not used in this implementation, as it manages itself the underlying creation and initialization.

**Specified by:**  
` initFactory` in interface `ComponentDefinitionsFactory`

<!-- -->

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property passed to newly created factory. Map can contain more properties than requested.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### toString

    public String toString()

Return String representation.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
String representation.

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
<td align="left"><a href="class-use/ReloadableDefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md" title="class in org.apache.struts.tiles.definition"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ReloadableDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
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
