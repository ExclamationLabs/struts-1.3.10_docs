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
<td align="left"><a href="class-use/DefinitionsFactoryConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryException.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactoryConfig.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class DefinitionsFactoryConfig
-------------------------------

    java.lang.Object
      org.apache.struts.tiles.DefinitionsFactoryConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class DefinitionsFactoryConfig

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A TilesFactoryConfig object hold configuration attributes for a tile definition factory.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` definitionConfigFiles`
           Definition configuration file specified by user.

`static String`

` DEFINITIONS_CONFIG_PARAMETER_NAME`
           Alternate name for definition files properties in configuration file.

`static String`

` FACTORY_CLASSNAME_PARAMETER_NAME`
           Alternate name for factory classname properties in configuration file.

`protected  String`

` factoryClassname`
           Fully qualified classname of the factory to create.

`protected  String`

` factoryName`
           The name associated to this factory.

`protected  boolean`

` moduleAware`
           Specifies whether the factory is "module-aware".

`static String`

` PARSER_DETAILS_PARAMETER_NAME`
           **Deprecated.** *This will be removed in a release after Struts 1.2.*

`static String`

` PARSER_VALIDATE_PARAMETER_NAME`
           Alternate name for parser validate properties in configuration file.

`protected  boolean`

` parserValidate`
           Specifies whether the parser will validate configuration files.

`static String`

` TILES_DETAILS_PARAMETER_NAME`
           **Deprecated.** *This will be removed in a release after Struts 1.2.*

  <span id="constructor_summary"></span>

| **Constructor Summary**                         |
|-------------------------------------------------|
| ` DefinitionsFactoryConfig()`                   
            Default constructor.                  |
| ` DefinitionsFactoryConfig(Map initParameters)` 
            Constructor.                          |

  <span id="method_summary"></span>

**Method Summary**

` Object`

` getAttribute(String name)`
           Get value of an additional attribute.

` Map`

` getAttributes()`
           Get additional attributes as a Map.

` String`

` getDefinitionConfigFiles()`
           Get the definition config files.

` String`

` getFactoryClassname()`
           Get the classname of the factory.

` String`

` getFactoryName()`
           Get the factory name.

` boolean`

` getParserValidate()`
           Determines if the parser is validating.

` boolean`

` isModuleAware()`
           Get the module aware flag.

`static void`

` linkOldPropertyNames(Map properties)`
           Link old property names to new property names.

` void`

` populate(Map properties)`
           Populate this config object from properties map, based on the specified name/value pairs.

` void`

` setAttribute(String name, Object value)`
           Set value of an additional attribute.

` void`

` setDefinitionConfigFiles(String aDefinitionConfigFiles)`
           Set the definition config files.

` void`

` setFactoryClassname(String aFactoryClassname)`
           Set the classname of the factory..

` void`

` setFactoryName(String factoryName)`
           Set the factory name.

` void`

` setModuleAware(boolean moduleAware)`
           Set the module aware flag.

` void`

` setParserValidate(boolean aParserValidate)`
           Set the validating mode for the parser.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="factoryClassname"></span>

### factoryClassname

    protected String factoryClassname

Fully qualified classname of the factory to create. If no classname is set, a default factory is created (of class "org.apache.struts.tiles.xmlDefinition.I18nFactorySet").

------------------------------------------------------------------------

<span id="parserValidate"></span>

### parserValidate

    protected boolean parserValidate

Specifies whether the parser will validate configuration files. Default value is true.

------------------------------------------------------------------------

<span id="definitionConfigFiles"></span>

### definitionConfigFiles

    protected String definitionConfigFiles

Definition configuration file specified by user.

------------------------------------------------------------------------

<span id="moduleAware"></span>

### moduleAware

    protected boolean moduleAware

Specifies whether the factory is "module-aware".

------------------------------------------------------------------------

<span id="factoryName"></span>

### factoryName

    protected String factoryName

The name associated to this factory.
 With Struts 1.1, this name is the module name to which this factory belong. It is set by the system.
 In prior versions, this property is not used.

------------------------------------------------------------------------

<span id="PARSER_DETAILS_PARAMETER_NAME"></span>

### PARSER\_DETAILS\_PARAMETER\_NAME

    public static final String PARSER_DETAILS_PARAMETER_NAME

**Deprecated.** *This will be removed in a release after Struts 1.2.*

Alternate name for parser debug details properties in configuration file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig.PARSER_DETAILS_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="PARSER_VALIDATE_PARAMETER_NAME"></span>

### PARSER\_VALIDATE\_PARAMETER\_NAME

    public static final String PARSER_VALIDATE_PARAMETER_NAME

Alternate name for parser validate properties in configuration file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig.PARSER_VALIDATE_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="FACTORY_CLASSNAME_PARAMETER_NAME"></span>

### FACTORY\_CLASSNAME\_PARAMETER\_NAME

    public static final String FACTORY_CLASSNAME_PARAMETER_NAME

Alternate name for factory classname properties in configuration file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig.FACTORY_CLASSNAME_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="DEFINITIONS_CONFIG_PARAMETER_NAME"></span>

### DEFINITIONS\_CONFIG\_PARAMETER\_NAME

    public static final String DEFINITIONS_CONFIG_PARAMETER_NAME

Alternate name for definition files properties in configuration file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig.DEFINITIONS_CONFIG_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="TILES_DETAILS_PARAMETER_NAME"></span>

### TILES\_DETAILS\_PARAMETER\_NAME

    public static final String TILES_DETAILS_PARAMETER_NAME

**Deprecated.** *This will be removed in a release after Struts 1.2.*

Alternate name for definition debug details properties in configuration file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.DefinitionsFactoryConfig.TILES_DETAILS_PARAMETER_NAME)

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionsFactoryConfig

    public DefinitionsFactoryConfig()

Default constructor.

------------------------------------------------------------------------

### DefinitionsFactoryConfig

    public DefinitionsFactoryConfig(Map initParameters)

Constructor. Create configuration object, and initialize it with parameters from Map. Parameters corresponding to an attribute are filtered and stored in appropriate attribute.

**Parameters:**  
`initParameters` - Map.

<span id="method_detail"></span>

**Method Detail**

### isModuleAware

    public boolean isModuleAware()

Get the module aware flag.

**Returns:**  
`true`: user wants a single factory instance, `false`: user wants multiple factory instances (one per module with Struts)

------------------------------------------------------------------------

### setModuleAware

    public void setModuleAware(boolean moduleAware)

Set the module aware flag.

**Parameters:**  
`moduleAware` - `true`: user wants a single factory instance, `false`: user wants multiple factory instances (one per module with Struts)

------------------------------------------------------------------------

### getFactoryClassname

    public String getFactoryClassname()

Get the classname of the factory.

**Returns:**  
Classname.

------------------------------------------------------------------------

### setFactoryClassname

    public void setFactoryClassname(String aFactoryClassname)

Set the classname of the factory..

**Parameters:**  
`aFactoryClassname` - Classname of the factory.

------------------------------------------------------------------------

### getParserValidate

    public boolean getParserValidate()

Determines if the parser is validating.

**Returns:**  
`true` when in validating mode.

------------------------------------------------------------------------

### setParserValidate

    public void setParserValidate(boolean aParserValidate)

Set the validating mode for the parser.

**Parameters:**  
`aParserValidate` - `true` for validation, `false` otherwise

------------------------------------------------------------------------

### getDefinitionConfigFiles

    public String getDefinitionConfigFiles()

Get the definition config files.

**Returns:**  
Defition config files.

------------------------------------------------------------------------

### setDefinitionConfigFiles

    public void setDefinitionConfigFiles(String aDefinitionConfigFiles)

Set the definition config files.

**Parameters:**  
`aDefinitionConfigFiles` - Definition config files.

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String name,
                             Object value)

Set value of an additional attribute.

**Parameters:**  
`name` - Name of the attribute.

`value` - Value of the attribute.

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name)

Get value of an additional attribute.

**Parameters:**  
`name` - Name of the attribute.

**Returns:**  
Value of the attribute, or null if not found.

------------------------------------------------------------------------

### getAttributes

    public Map getAttributes()

Get additional attributes as a Map.

**Returns:**  
Map A Map containing attribute name - value pairs.

------------------------------------------------------------------------

### populate

    public void populate(Map properties)
                  throws IllegalAccessException,
                         InvocationTargetException

Populate this config object from properties map, based on the specified name/value pairs. This method uses the populate() method from org.apache.commons.beanutils.BeanUtil.

Properties keys are scanned for old property names, and linked to the new name if necessary. This modifies the properties map.

The particular setter method to be called for each property is determined using the usual JavaBeans introspection mechanisms. Thus, you may identify custom setter methods using a BeanInfo class that is associated with the class of the bean itself. If no such BeanInfo class is available, the standard method name conversion ("set" plus the capitalized name of the property in question) is used.

**NOTE**: It is contrary to the JavaBeans Specification to have more than one setter method (with different argument signatures) for the same property.

**Parameters:**  
`properties` - Map keyed by property name, with the corresponding (String or String[]) value(s) to be set.

**Throws:**  
`IllegalAccessException` - if the caller does not have access to the property accessor method.

`InvocationTargetException` - if the property accessor method throws an exception.

**See Also:**  
[`BeanUtils`](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/BeanUtils.html.md?is-external=true "class or interface in org.apache.commons.beanutils")

------------------------------------------------------------------------

### linkOldPropertyNames

    public static void linkOldPropertyNames(Map properties)

Link old property names to new property names. This modifies the map.

**Parameters:**  
`properties` - Map keyed by property name, with the corresponding (String or String[]) value(s) to be set.

------------------------------------------------------------------------

### getFactoryName

    public String getFactoryName()

Get the factory name.

------------------------------------------------------------------------

### setFactoryName

    public void setFactoryName(String factoryName)

Set the factory name.

**Parameters:**  
`factoryName` - Name of the factory.

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
<td align="left"><a href="class-use/DefinitionsFactoryConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactory.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryException.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactoryConfig.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryConfig.html"><strong>NO FRAMES</strong></a>    
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
