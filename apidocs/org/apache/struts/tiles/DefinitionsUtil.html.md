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
<td align="left"><a href="class-use/DefinitionsUtil.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DirectStringAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsUtil.html"><strong>FRAMES</strong></a>    <a href="DefinitionsUtil.html"><strong>NO FRAMES</strong></a>    
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
 Class DefinitionsUtil
-----------------------

    java.lang.Object
      org.apache.struts.tiles.TilesUtil
          org.apache.struts.tiles.DefinitionsUtil

**All Implemented Interfaces:**  
[ComponentConstants](../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

**Deprecated.** *Use [`TilesUtil.createDefinitionsFactory(ServletContext, DefinitionsFactoryConfig)`](../../../../org/apache/struts/tiles/TilesUtil.html.md#createDefinitionsFactory(javax.servlet.ServletContext,%20org.apache.struts.tiles.DefinitionsFactoryConfig))*

    public class DefinitionsUtil

extends [TilesUtil](../../../../org/apache/struts/tiles/TilesUtil.html.md "class in org.apache.struts.tiles")

implements [ComponentConstants](../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")

Utilities class for definitions factory. Also define userDebugLevel property (TODO to be moved from this class ?).

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` ACTION_DEFINITION`
           **Deprecated.** Constant name used to store definition in jsp context.

`static String`

` DEFINITIONS_CONFIG_USER_DEBUG_LEVEL`
           **Deprecated.** Name of init property carrying debug level.

`static String`

` DEFINITIONS_FACTORY`
           **Deprecated.** Constant name used to store factory in context.

`static String`

` DEFINITIONS_FACTORY_CLASSNAME`
           **Deprecated.** Name of init property carrying factory class name.

`protected static Log`

`log`
           **Deprecated.** Commons Logging instance.

`static int`

` NO_DEBUG`
           **Deprecated.** *This will be removed in a release after Struts 1.2.*

`static int`

` userDebugLevel`
           **Deprecated.** *This will be removed in a release after Struts 1.2.*

 <span id="fields_inherited_from_class_org.apache.struts.tiles.TilesUtil"></span>

| **Fields inherited from class org.apache.struts.tiles.[TilesUtil](../../../../org/apache/struts/tiles/TilesUtil.html.md "class in org.apache.struts.tiles")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `tilesUtilImpl`                                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.ComponentConstants"></span>

| **Fields inherited from interface org.apache.struts.tiles.taglib.[ComponentConstants](../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` COMPONENT_CONTEXT,  COMPONENT_SCOPE,  EXCEPTION_KEY,  LOCALE_KEY`                                                                                                                                       |

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` DefinitionsUtil()`         
            **Deprecated.**    |

  <span id="method_summary"></span>

**Method Summary**

`static DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, Map properties)`
           **Deprecated.** Create default Definition factory.

`static DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, Map properties, String classname)`
           **Deprecated.** *Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)*

`static DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)`
           **Deprecated.** Create Definition factory.

`static DefinitionsFactory`

` createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig, boolean checkIfExist)`
           **Deprecated.** Create Definition factory.

`static ComponentDefinition`

` getActionDefinition(ServletRequest request)`
           **Deprecated.** Get Definition stored in jsp context by an action.

`static DefinitionsFactory`

` getDefinitionsFactory(ServletContext servletContext)`
           **Deprecated.** *Use [`TilesUtil.getDefinitionsFactory(ServletRequest, ServletContext)`](../../../../org/apache/struts/tiles/TilesUtil.html.md#getDefinitionsFactory(javax.servlet.ServletRequest,%20javax.servlet.ServletContext))*

`static void`

` populateDefinitionsFactoryConfig(DefinitionsFactoryConfig factoryConfig, ServletConfig servletConfig)`
           **Deprecated.** Populate Definition Factory Config from web.xml properties.

`protected static DefinitionsFactoryConfig`

` readFactoryConfig(ServletConfig servletConfig)`
           **Deprecated.** Create FactoryConfig and initialize it from web.xml.

`static void`

` removeActionDefinition(ServletRequest request, ComponentDefinition definition)`
           **Deprecated.** Remove Definition stored in jsp context.

`static void`

` setActionDefinition(ServletRequest request, ComponentDefinition definition)`
           **Deprecated.** Store definition in jsp context.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.TilesUtil"></span>

| **Methods inherited from class org.apache.struts.tiles.[TilesUtil](../../../../org/apache/struts/tiles/TilesUtil.html.md "class in org.apache.struts.tiles")**  |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createDefinitionsFactory,  doForward,  doInclude,  doInclude,  doInclude,  getDefinition,  getDefinitionsFactory,  getTilesUtil,  setTilesUtil, testReset` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

**Deprecated.** 

Commons Logging instance.

------------------------------------------------------------------------

<span id="userDebugLevel"></span>

### userDebugLevel

    public static int userDebugLevel

**Deprecated.** *This will be removed in a release after Struts 1.2.*

Global user defined debug level.

------------------------------------------------------------------------

<span id="NO_DEBUG"></span>

### NO\_DEBUG

    public static final int NO_DEBUG

**Deprecated.** *This will be removed in a release after Struts 1.2.*

User Debug level.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsUtil.NO_DEBUG)

------------------------------------------------------------------------

<span id="DEFINITIONS_CONFIG_USER_DEBUG_LEVEL"></span>

### DEFINITIONS\_CONFIG\_USER\_DEBUG\_LEVEL

    public static final String DEFINITIONS_CONFIG_USER_DEBUG_LEVEL

**Deprecated.** 

Name of init property carrying debug level.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsUtil.DEFINITIONS_CONFIG_USER_DEBUG_LEVEL)

------------------------------------------------------------------------

<span id="DEFINITIONS_FACTORY_CLASSNAME"></span>

### DEFINITIONS\_FACTORY\_CLASSNAME

    public static final String DEFINITIONS_FACTORY_CLASSNAME

**Deprecated.** 

Name of init property carrying factory class name.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsUtil.DEFINITIONS_FACTORY_CLASSNAME)

------------------------------------------------------------------------

<span id="DEFINITIONS_FACTORY"></span>

### DEFINITIONS\_FACTORY

    public static final String DEFINITIONS_FACTORY

**Deprecated.** 

Constant name used to store factory in context.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsUtil.DEFINITIONS_FACTORY)

------------------------------------------------------------------------

<span id="ACTION_DEFINITION"></span>

### ACTION\_DEFINITION

    public static final String ACTION_DEFINITION

**Deprecated.** 

Constant name used to store definition in jsp context. Used to pass definition from a Struts action to servlet forward.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsUtil.ACTION_DEFINITION)

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionsUtil

    public DefinitionsUtil()

**Deprecated.** 

<span id="method_detail"></span>

**Method Detail**

### createDefinitionsFactory

    public static DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                              Map properties,
                                                              String classname)
                                                       throws DefinitionsFactoryException

**Deprecated.** *Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)*

Create Definition factory. If a factory class name is provided, a factory of this class is created. Otherwise, default factory is created.

**Parameters:**  
`classname` - Class name of the factory to create.

`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property used to initialize factory configuration object.

**Returns:**  
newly created factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createDefinitionsFactory

    public static DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                              Map properties)
                                                       throws DefinitionsFactoryException

**Deprecated.** 

Create default Definition factory.

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property used to initialize factory configuration object.

**Returns:**  
newly created factory of type ConfigurableDefinitionsFactory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createDefinitionsFactory

    public static DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                              ServletConfig servletConfig)
                                                       throws DefinitionsFactoryException

**Deprecated.** 

Create Definition factory. Create configuration object from servlet web.xml file, then create ConfigurableDefinitionsFactory and initialized it with object.

Convenience method. Calls createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`servletConfig` - Servlet config containing parameters to be passed to factory configuration object.

**Returns:**  
newly created factory of type ConfigurableDefinitionsFactory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### createDefinitionsFactory

    public static DefinitionsFactory createDefinitionsFactory(ServletContext servletContext,
                                                              ServletConfig servletConfig,
                                                              boolean checkIfExist)
                                                       throws DefinitionsFactoryException

**Deprecated.** 

Create Definition factory. Create configuration object from servlet web.xml file, then create ConfigurableDefinitionsFactory and initialized it with object.

If checkIfExist is true, start by checking if factory already exist. If yes, return it. If no, create a new one.

If checkIfExist is false, factory is always created.

Convenience method. Calls createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`servletConfig` - Servlet config containing parameters to be passed to factory configuration object.

`checkIfExist` - Check if factory already exist. If true and factory exist, return it. If true and factory doesn't exist, create it. If false, create it in all cases.

**Returns:**  
newly created factory of type ConfigurableDefinitionsFactory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while initializing factory

------------------------------------------------------------------------

### getDefinitionsFactory

    public static DefinitionsFactory getDefinitionsFactory(ServletContext servletContext)

**Deprecated.** *Use [`TilesUtil.getDefinitionsFactory(ServletRequest, ServletContext)`](../../../../org/apache/struts/tiles/TilesUtil.html.md#getDefinitionsFactory(javax.servlet.ServletRequest,%20javax.servlet.ServletContext))*

Get definition factory from appropriate servlet context.

**Returns:**  
Definitions factory or null if not found.

**Since:**  
20020708

------------------------------------------------------------------------

### getActionDefinition

    public static ComponentDefinition getActionDefinition(ServletRequest request)

**Deprecated.** 

Get Definition stored in jsp context by an action.

**Returns:**  
ComponentDefinition or null if not found.

------------------------------------------------------------------------

### setActionDefinition

    public static void setActionDefinition(ServletRequest request,
                                           ComponentDefinition definition)

**Deprecated.** 

Store definition in jsp context. Mainly used by Struts to pass a definition defined in an Action to the forward.

------------------------------------------------------------------------

### removeActionDefinition

    public static void removeActionDefinition(ServletRequest request,
                                              ComponentDefinition definition)

**Deprecated.** 

Remove Definition stored in jsp context. Mainly used by Struts to pass a definition defined in an Action to the forward.

------------------------------------------------------------------------

### populateDefinitionsFactoryConfig

    public static void populateDefinitionsFactoryConfig(DefinitionsFactoryConfig factoryConfig,
                                                        ServletConfig servletConfig)
                                                 throws IllegalAccessException,
                                                        InvocationTargetException

**Deprecated.** 

Populate Definition Factory Config from web.xml properties.

**Parameters:**  
`factoryConfig` - Definition Factory Config to populate.

`servletConfig` - Current servlet config containing web.xml properties.

**Throws:**  
`IllegalAccessException` - if the caller does not have access to the property accessor method

`InvocationTargetException` - if the property accessor method throws an exception

**Since:**  
tiles 20020708

**See Also:**  
[`BeanUtils`](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/BeanUtils.html.md?is-external=true "class or interface in org.apache.commons.beanutils")

------------------------------------------------------------------------

### readFactoryConfig

    protected static DefinitionsFactoryConfig readFactoryConfig(ServletConfig servletConfig)
                                                         throws DefinitionsFactoryException

**Deprecated.** 

Create FactoryConfig and initialize it from web.xml.

**Parameters:**  
`servletConfig` - ServletConfig for the module with which this plug in is associated

**Throws:**  
`DefinitionsFactoryException` - if this `PlugIn` cannot be successfully initialized

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
<td align="left"><a href="class-use/DefinitionsUtil.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DirectStringAttribute.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsUtil.html"><strong>FRAMES</strong></a>    <a href="DefinitionsUtil.html"><strong>NO FRAMES</strong></a>    
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
