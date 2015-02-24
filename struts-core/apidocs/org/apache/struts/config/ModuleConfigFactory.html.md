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
<td align="left"><a href="class-use/ModuleConfigFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ModuleConfig.html.md" title="interface in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/PlugInConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ModuleConfigFactory.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigFactory.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class ModuleConfigFactory
--------------------------

    java.lang.Object
      org.apache.struts.config.ModuleConfigFactory

**Direct Known Subclasses:**  
[DefaultModuleConfigFactory](../../../../org/apache/struts/config/impl/DefaultModuleConfigFactory.html.md "class in org.apache.struts.config.impl")

------------------------------------------------------------------------

    public abstract class ModuleConfigFactory

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

A factory interface for creating [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config")s.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config")

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Class`

` clazz`
           The Java class to be used for `ModuleConfigFactory` instances.

`protected static String`

` factoryClass`
           The fully qualified class name to be used for `ModuleConfigFactory` instances.

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` ModuleConfigFactory()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

`static ModuleConfigFactory`

` createFactory()`
           Create and return a `ModuleConfigFactory` instance of the appropriate class, which can be used to create customized `ModuleConfig` instances.

`abstract  ModuleConfig`

` createModuleConfig(String prefix)`
           Create and return a newly instansiated [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

`static String`

` getFactoryClass()`
           The fully qualified class name that is used for `ModuleConfigFactory` instances.

`static void`

` setFactoryClass(String factoryClass)`
           Set the fully qualified class name that is used for `ModuleConfigFactory` instances.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="clazz"></span>

### clazz

    protected static Class clazz

The Java class to be used for `ModuleConfigFactory` instances.

------------------------------------------------------------------------

<span id="factoryClass"></span>

### factoryClass

    protected static String factoryClass

The fully qualified class name to be used for `ModuleConfigFactory` instances.

<span id="constructor_detail"></span>

**Constructor Detail**

### ModuleConfigFactory

    public ModuleConfigFactory()

<span id="method_detail"></span>

**Method Detail**

### createModuleConfig

    public abstract ModuleConfig createModuleConfig(String prefix)

Create and return a newly instansiated [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config"). This method must be implemented by concrete subclasses.

**Parameters:**  
`prefix` - Module prefix for Configuration

------------------------------------------------------------------------

### getFactoryClass

    public static String getFactoryClass()

The fully qualified class name that is used for `ModuleConfigFactory` instances.

**Returns:**  
class name that is used for `ModuleConfigFactory` instances

------------------------------------------------------------------------

### setFactoryClass

    public static void setFactoryClass(String factoryClass)

Set the fully qualified class name that is used for `ModuleConfigFactory` instances.

**Parameters:**  
`factoryClass` - name that is used for `ModuleConfigFactory` instances

------------------------------------------------------------------------

### createFactory

    public static ModuleConfigFactory createFactory()

Create and return a `ModuleConfigFactory` instance of the appropriate class, which can be used to create customized `ModuleConfig` instances. If no such factory can be created, return `null` instead.

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
<td align="left"><a href="class-use/ModuleConfigFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ModuleConfig.html.md" title="interface in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/PlugInConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ModuleConfigFactory.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigFactory.html"><strong>NO FRAMES</strong></a>    
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
