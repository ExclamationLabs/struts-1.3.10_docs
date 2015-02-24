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
<td align="left"><a href="class-use/TilesUtilStrutsImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilStrutsImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilStrutsImpl.html"><strong>NO FRAMES</strong></a>    
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
 Class TilesUtilStrutsImpl
--------------------------

    java.lang.Object
      org.apache.struts.tiles.TilesUtilImpl
          org.apache.struts.tiles.TilesUtilStrutsImpl

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[TilesUtilStrutsModulesImpl](../../../../org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class TilesUtilStrutsImpl

extends [TilesUtilImpl](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles")

TilesUtil implementation for Struts 1.1 with one single factory. This class contains default implementation of utilities. This implementation is intended to be used with Struts 1.1. This class is used as the base class for all Struts 1.1 implementations of TilesUtil.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.TilesUtilStrutsImpl)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl"></span>

| **Fields inherited from class org.apache.struts.tiles.[TilesUtilImpl](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` DEFINITIONS_FACTORY, log`                                                                                                                                        |

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` TilesUtilStrutsImpl()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

` DefinitionsFactory`

` getDefinitionsFactory(ServletContext servletContext, ModuleConfig moduleConfig)`
           Get definition factory for the module attached to the specified moduleConfig.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.TilesUtilImpl"></span>

| **Methods inherited from class org.apache.struts.tiles.[TilesUtilImpl](../../../../org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createDefinitionFactoryInstance,  createDefinitionsFactory,  doForward,  doInclude,  doInclude,  getDefinitionsFactory,  makeDefinitionsFactoryAccessible`        |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesUtilStrutsImpl

    public TilesUtilStrutsImpl()

<span id="method_detail"></span>

**Method Detail**

### getDefinitionsFactory

    public DefinitionsFactory getDefinitionsFactory(ServletContext servletContext,
                                                    ModuleConfig moduleConfig)

Get definition factory for the module attached to the specified moduleConfig.

**Parameters:**  
`servletContext` - Current servlet context

`moduleConfig` - Module config of the module for which the factory is requested.

**Returns:**  
Definitions factory or null if not found.

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
<td align="left"><a href="class-use/TilesUtilStrutsImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesUtilStrutsImpl.html"><strong>FRAMES</strong></a>    <a href="TilesUtilStrutsImpl.html"><strong>NO FRAMES</strong></a>    
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
