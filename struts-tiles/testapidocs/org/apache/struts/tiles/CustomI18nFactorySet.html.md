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
<td align="left"><a href="../../../../org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/CustomI18nFactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/tiles/TestTilesPlugin.html.md" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/CustomI18nFactorySet.html"><strong>FRAMES</strong></a>    <a href="CustomI18nFactorySet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.xmlDefinition.I18nFactorySet">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Class CustomI18nFactorySet
---------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.FactorySet
          org.apache.struts.tiles.xmlDefinition.I18nFactorySet
              org.apache.struts.tiles.CustomI18nFactorySet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), org.apache.struts.tiles.ComponentDefinitionsFactory

------------------------------------------------------------------------

    public class CustomI18nFactorySet

extends org.apache.struts.tiles.xmlDefinition.I18nFactorySet

Test I18nFactorySet.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.CustomI18nFactorySet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.xmlDefinition.I18nFactorySet"></span>

| **Fields inherited from class org.apache.struts.tiles.xmlDefinition.I18nFactorySet**                                                                                                                                        |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `DEFAULT_DEFINITION_FILENAMES, defaultFactory, DEFINITIONS_CONFIG_PARAMETER_NAME, FILENAME_EXTENSION, isValidatingParser, log, PARSER_DETAILS_PARAMETER_NAME, PARSER_VALIDATE_PARAMETER_NAME, parserDetailLevel, xmlParser` |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

| **Fields inherited from class org.apache.struts.tiles.xmlDefinition.FactorySet** |
|----------------------------------------------------------------------------------|
| `factories`                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                |
|------------------------------------------------------------------------|
| ` CustomI18nFactorySet(ServletContext servletContext, Map properties)` 
            Constructor.                                                 |

  <span id="method_summary"></span>

**Method Summary**

` org.apache.struts.tiles.xmlDefinition.DefinitionsFactory`

` createFactory(Object key, ServletRequest request, ServletContext servletContext)`
            

 <span id="methods_inherited_from_class_org.apache.struts.tiles.xmlDefinition.I18nFactorySet"></span>

| **Methods inherited from class org.apache.struts.tiles.xmlDefinition.I18nFactorySet**                                                |
|--------------------------------------------------------------------------------------------------------------------------------------|
| `createDefaultFactory, getDefaultFactory, getDefinitionsFactoryKey, initFactory, initFactory, parseXmlFile, parseXmlFiles, toString` |

 <span id="methods_inherited_from_class_org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

| **Methods inherited from class org.apache.struts.tiles.xmlDefinition.FactorySet** |
|-----------------------------------------------------------------------------------|
| `getDefinition, getFactory`                                                       |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### CustomI18nFactorySet

    public CustomI18nFactorySet(ServletContext servletContext,
                                Map properties)
                         throws org.apache.struts.tiles.DefinitionsFactoryException

Constructor. Init the factory by reading appropriate configuration file.

**Parameters:**  
`servletContext` - Servlet context.

`properties` - Map containing all properties.

**Throws:**  
`FactoryNotFoundException` - Can't find factory configuration file.

`org.apache.struts.tiles.DefinitionsFactoryException`

<span id="method_detail"></span>

**Method Detail**

### createFactory

    public org.apache.struts.tiles.xmlDefinition.DefinitionsFactory createFactory(Object key,
                                                                                  ServletRequest request,
                                                                                  ServletContext servletContext)
                                                                           throws org.apache.struts.tiles.DefinitionsFactoryException

**Overrides:**  
`createFactory` in class `org.apache.struts.tiles.xmlDefinition.I18nFactorySet`

<!-- -->

**Throws:**  
`org.apache.struts.tiles.DefinitionsFactoryException`

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
<td align="left"><a href="../../../../org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/CustomI18nFactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/tiles/TestTilesPlugin.html.md" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/CustomI18nFactorySet.html"><strong>FRAMES</strong></a>    <a href="CustomI18nFactorySet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.xmlDefinition.I18nFactorySet">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
