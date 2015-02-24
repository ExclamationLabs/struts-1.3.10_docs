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
<td align="left"><a href="class-use/I18nFactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html"><strong>FRAMES</strong></a>    <a href="I18nFactorySet.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.xmlDefinition
 Class I18nFactorySet
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.FactorySet
          org.apache.struts.tiles.xmlDefinition.I18nFactorySet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class I18nFactorySet

extends [FactorySet](../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition")

Definitions factory. This implementation allows to have a set of definition factories. There is a main factory and one factory for each file associated to a Locale. To retrieve a definition, we first search for the appropriate factory using the Locale found in session context. If no factory is found, use the default one. Then we ask the factory for the definition. A definition factory file is loaded using main filename extended with locale code (ex : `templateDefinitions_fr.xml`). If no file is found under this name, use default file.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.xmlDefinition.I18nFactorySet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String[]`

` DEFAULT_DEFINITION_FILENAMES`
           Possible definition filenames.

`protected  DefinitionsFactory`

` defaultFactory`
           Default factory.

`static String`

` DEFINITIONS_CONFIG_PARAMETER_NAME`
           Config file parameter name.

`static String`

` FILENAME_EXTENSION`
           Default filenames extension.

`protected  boolean`

` isValidatingParser`
           Do we want validating parser.

`protected static Log`

` log`
           Commons Logging instance.

`static String`

` PARSER_DETAILS_PARAMETER_NAME`
           Config file parameter name.

`static String`

` PARSER_VALIDATE_PARAMETER_NAME`
           Config file parameter name.

`protected  int`

` parserDetailLevel`
           Parser detail level.

`protected  XmlParser`

` xmlParser`
           XML parser used.

 <span id="fields_inherited_from_class_org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

| **Fields inherited from class org.apache.struts.tiles.xmlDefinition.[FactorySet](../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` factories`                                                                                                                                                                                              |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                          |
|------------------------------------------------------------------|
| ` I18nFactorySet()`                                              
            Parameterless Constructor.                             |
| ` I18nFactorySet(ServletContext servletContext, Map properties)` 
            Constructor.                                           |

  <span id="method_summary"></span>

**Method Summary**

`protected  DefinitionsFactory`

` createDefaultFactory(ServletContext servletContext)`
           Create default factory .

`protected  DefinitionsFactory`

` createFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Create a factory for specified key.

`protected  DefinitionsFactory`

` getDefaultFactory()`
           Get default factory.

`protected  Object`

` getDefinitionsFactoryKey(String name, ServletRequest request, ServletContext servletContext)`
           Extract key that will be used to get the sub factory.

` void`

` initFactory(ServletContext servletContext, Map properties)`
           Initialization method.

`protected  void`

` initFactory(ServletContext servletContext, String proposedFilename)`
           Initialization method.

`protected  XmlDefinitionsSet`

` parseXmlFile(ServletContext servletContext, String filename, XmlDefinitionsSet xmlDefinitions)`
           Parse specified xml file and add definition to specified definitions set.

`protected  XmlDefinitionsSet`

` parseXmlFiles(ServletContext servletContext, String postfix, XmlDefinitionsSet xmlDefinitions)`
           Parse files associated to postix if they exist.

` String`

` toString()`
           Return String representation.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

| **Methods inherited from class org.apache.struts.tiles.xmlDefinition.[FactorySet](../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getDefinition,  getFactory`                                                                                                                                                                              |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="DEFINITIONS_CONFIG_PARAMETER_NAME"></span>

### DEFINITIONS\_CONFIG\_PARAMETER\_NAME

    public static final String DEFINITIONS_CONFIG_PARAMETER_NAME

Config file parameter name.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.xmlDefinition.I18nFactorySet.DEFINITIONS_CONFIG_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="PARSER_DETAILS_PARAMETER_NAME"></span>

### PARSER\_DETAILS\_PARAMETER\_NAME

    public static final String PARSER_DETAILS_PARAMETER_NAME

Config file parameter name.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.xmlDefinition.I18nFactorySet.PARSER_DETAILS_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="PARSER_VALIDATE_PARAMETER_NAME"></span>

### PARSER\_VALIDATE\_PARAMETER\_NAME

    public static final String PARSER_VALIDATE_PARAMETER_NAME

Config file parameter name.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.xmlDefinition.I18nFactorySet.PARSER_VALIDATE_PARAMETER_NAME)

------------------------------------------------------------------------

<span id="DEFAULT_DEFINITION_FILENAMES"></span>

### DEFAULT\_DEFINITION\_FILENAMES

    public static final String[] DEFAULT_DEFINITION_FILENAMES

Possible definition filenames.

------------------------------------------------------------------------

<span id="FILENAME_EXTENSION"></span>

### FILENAME\_EXTENSION

    public static final String FILENAME_EXTENSION

Default filenames extension.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.xmlDefinition.I18nFactorySet.FILENAME_EXTENSION)

------------------------------------------------------------------------

<span id="defaultFactory"></span>

### defaultFactory

    protected DefinitionsFactory defaultFactory

Default factory.

------------------------------------------------------------------------

<span id="xmlParser"></span>

### xmlParser

    protected transient XmlParser xmlParser

XML parser used. Attribute is transient to allow serialization. In this implementaiton, xmlParser is created each time we need it ;-(.

------------------------------------------------------------------------

<span id="isValidatingParser"></span>

### isValidatingParser

    protected boolean isValidatingParser

Do we want validating parser. Default is `false`. Can be set from servlet config file.

------------------------------------------------------------------------

<span id="parserDetailLevel"></span>

### parserDetailLevel

    protected int parserDetailLevel

Parser detail level. Default is 0. Can be set from servlet config file.

<span id="constructor_detail"></span>

**Constructor Detail**

### I18nFactorySet

    public I18nFactorySet()

Parameterless Constructor. Method [`initFactory(javax.servlet.ServletContext, java.util.Map)`](../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md#initFactory(javax.servlet.ServletContext,%20java.util.Map)) must be called prior to any use of created factory.

------------------------------------------------------------------------

### I18nFactorySet

    public I18nFactorySet(ServletContext servletContext,
                          Map properties)
                   throws DefinitionsFactoryException

Constructor. Init the factory by reading appropriate configuration file.

**Parameters:**  
`servletContext` - Servlet context.

`properties` - Map containing all properties.

**Throws:**  
`FactoryNotFoundException` - Can't find factory configuration file.

`DefinitionsFactoryException`

<span id="method_detail"></span>

**Method Detail**

### initFactory

    public void initFactory(ServletContext servletContext,
                            Map properties)
                     throws DefinitionsFactoryException

Initialization method. Init the factory by reading appropriate configuration file. This method is called exactly once immediately after factory creation in case of internal creation (by DefinitionUtil).

**Specified by:**  
` initFactory` in interface `ComponentDefinitionsFactory`

**Specified by:**  
` initFactory` in class `FactorySet`

<!-- -->

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property passed to newly created factory. Map can contains more properties than requested.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

------------------------------------------------------------------------

### initFactory

    protected void initFactory(ServletContext servletContext,
                               String proposedFilename)
                        throws DefinitionsFactoryException,
                               FileNotFoundException

Initialization method. Init the factory by reading appropriate configuration file. This method is called exactly once immediately after factory creation in case of internal creation (by DefinitionUtil).

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`proposedFilename` - File names, comma separated, to use as base file names.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

`FileNotFoundException`

------------------------------------------------------------------------

### getDefaultFactory

    protected DefinitionsFactory getDefaultFactory()

Get default factory.

**Specified by:**  
` getDefaultFactory` in class `FactorySet`

<!-- -->

**Returns:**  
Default factory

------------------------------------------------------------------------

### createDefaultFactory

    protected DefinitionsFactory createDefaultFactory(ServletContext servletContext)
                                               throws DefinitionsFactoryException,
                                                      FileNotFoundException

Create default factory . Create InstancesMapper for specified Locale. If creation failes, use default mapper and log error message.

**Parameters:**  
`servletContext` - Current servlet context. Used to open file.

**Returns:**  
Created default definition factory.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while creating factory.

`FileNotFoundException` - if factory can't be loaded from filenames.

------------------------------------------------------------------------

### getDefinitionsFactoryKey

    protected Object getDefinitionsFactoryKey(String name,
                                              ServletRequest request,
                                              ServletContext servletContext)

Extract key that will be used to get the sub factory.

**Specified by:**  
` getDefinitionsFactoryKey` in class `FactorySet`

<!-- -->

**Parameters:**  
`name` - Name of requested definition

`request` - Current servlet request.

`servletContext` - Current servlet context.

**Returns:**  
the key or `null` if not found.

------------------------------------------------------------------------

### createFactory

    protected DefinitionsFactory createFactory(Object key,
                                               ServletRequest request,
                                               ServletContext servletContext)
                                        throws DefinitionsFactoryException

Create a factory for specified key. If creation failes, return default factory and log an error message.

**Specified by:**  
` createFactory` in class `FactorySet`

<!-- -->

**Parameters:**  
`key` - The key.

`request` - Servlet request.

`servletContext` - Servlet context.

**Returns:**  
Definition factory for specified key.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while creating factory.

------------------------------------------------------------------------

### parseXmlFiles

    protected XmlDefinitionsSet parseXmlFiles(ServletContext servletContext,
                                              String postfix,
                                              XmlDefinitionsSet xmlDefinitions)
                                       throws DefinitionsFactoryException

Parse files associated to postix if they exist. For each name in filenames, append postfix before file extension, then try to load the corresponding file. If file doesn't exist, try next one. Each file description is added to the XmlDefinitionsSet description. The XmlDefinitionsSet description is created only if there is a definition file. Inheritance is not resolved in the returned XmlDefinitionsSet. If no description file can be opened and no definiion set is provided, return `null`.

**Parameters:**  
`postfix` - Postfix to add to each description file.

`xmlDefinitions` - Definitions set to which definitions will be added. If `null`, a definitions set is created on request.

**Returns:**  
XmlDefinitionsSet The definitions set created or passed as parameter.

**Throws:**  
`DefinitionsFactoryException` - On errors parsing file.

------------------------------------------------------------------------

### parseXmlFile

    protected XmlDefinitionsSet parseXmlFile(ServletContext servletContext,
                                             String filename,
                                             XmlDefinitionsSet xmlDefinitions)
                                      throws DefinitionsFactoryException

Parse specified xml file and add definition to specified definitions set. This method is used to load several description files in one instances list. If filename exists and definition set is `null`, create a new set. Otherwise, return passed definition set (can be `null`).

**Parameters:**  
`servletContext` - Current servlet context. Used to open file.

`filename` - Name of file to parse.

`xmlDefinitions` - Definitions set to which definitions will be added. If null, a definitions set is created on request.

**Returns:**  
XmlDefinitionsSet The definitions set created or passed as parameter.

**Throws:**  
`DefinitionsFactoryException` - On errors parsing file.

------------------------------------------------------------------------

### toString

    public String toString()

Return String representation.

**Overrides:**  
` toString` in class `FactorySet`

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
<td align="left"><a href="class-use/I18nFactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html"><strong>FRAMES</strong></a>    <a href="I18nFactorySet.html"><strong>NO FRAMES</strong></a>    
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
