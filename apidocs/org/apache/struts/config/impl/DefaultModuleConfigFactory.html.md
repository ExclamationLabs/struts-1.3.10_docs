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
<td align="left"><a href="class-use/DefaultModuleConfigFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/config/impl/ModuleConfigImpl.html.md" title="class in org.apache.struts.config.impl"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config/impl/DefaultModuleConfigFactory.html"><strong>FRAMES</strong></a>    <a href="DefaultModuleConfigFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ModuleConfigFactory">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config.impl
 Class DefaultModuleConfigFactory
---------------------------------

    java.lang.Object
      org.apache.struts.config.ModuleConfigFactory
          org.apache.struts.config.impl.DefaultModuleConfigFactory

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class DefaultModuleConfigFactory

extends [ModuleConfigFactory](../../../../../org/apache/struts/config/ModuleConfigFactory.html.md "class in org.apache.struts.config")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A factory for creating [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") instances.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:45:39 -0400 (Sat, 07 May 2005) $

**See Also:**  
[`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config"), [`ModuleConfigFactory`](../../../../../org/apache/struts/config/ModuleConfigFactory.html "class in org.apache.struts.config"), [Serialized Form](../../../../../serialized-form.html#org.apache.struts.config.impl.DefaultModuleConfigFactory)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.ModuleConfigFactory"></span>

| **Fields inherited from class org.apache.struts.config.[ModuleConfigFactory](../../../../../org/apache/struts/config/ModuleConfigFactory.html.md "class in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` clazz,  factoryClass`                                                                                                                                                              |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` DefaultModuleConfigFactory()` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

` ModuleConfig`

` createModuleConfig(String prefix)`
           Create and return a newly instansiated [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

 <span id="methods_inherited_from_class_org.apache.struts.config.ModuleConfigFactory"></span>

| **Methods inherited from class org.apache.struts.config.[ModuleConfigFactory](../../../../../org/apache/struts/config/ModuleConfigFactory.html.md "class in org.apache.struts.config")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createFactory,  getFactoryClass,  setFactoryClass`                                                                                                                                  |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### DefaultModuleConfigFactory

    public DefaultModuleConfigFactory()

<span id="method_detail"></span>

**Method Detail**

### createModuleConfig

    public ModuleConfig createModuleConfig(String prefix)

Create and return a newly instansiated [`ModuleConfig`](../../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config"). This method must be implemented by concrete subclasses.

**Specified by:**  
` createModuleConfig` in class `ModuleConfigFactory`

<!-- -->

**Parameters:**  
`prefix` - Module prefix for Configuration

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
<td align="left"><a href="class-use/DefaultModuleConfigFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/config/impl/ModuleConfigImpl.html.md" title="class in org.apache.struts.config.impl"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config/impl/DefaultModuleConfigFactory.html"><strong>FRAMES</strong></a>    <a href="DefaultModuleConfigFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ModuleConfigFactory">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
