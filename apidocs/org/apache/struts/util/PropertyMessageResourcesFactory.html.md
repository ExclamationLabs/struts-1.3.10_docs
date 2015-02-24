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
<td align="left"><a href="class-use/PropertyMessageResourcesFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/PropertyMessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/RequestUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/PropertyMessageResourcesFactory.html"><strong>FRAMES</strong></a>    <a href="PropertyMessageResourcesFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.util.MessageResourcesFactory">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class PropertyMessageResourcesFactory
--------------------------------------

    java.lang.Object
      org.apache.struts.util.MessageResourcesFactory
          org.apache.struts.util.PropertyMessageResourcesFactory

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class PropertyMessageResourcesFactory

extends [MessageResourcesFactory](../../../../org/apache/struts/util/MessageResourcesFactory.html.md "class in org.apache.struts.util")

Factory for `PropertyMessageResources` instances. The configuration paramter for such instances is the base Java package name of the resources entries from which our keys and values will be loaded.

**Version:**  
$Rev: 480549 $ $Date: 2006-11-29 06:16:15 -0600 (Wed, 29 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.PropertyMessageResourcesFactory)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.util.MessageResourcesFactory"></span>

| **Fields inherited from class org.apache.struts.util.[MessageResourcesFactory](../../../../org/apache/struts/util/MessageResourcesFactory.html.md "class in org.apache.struts.util")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` clazz,  config,  factoryClass,  returnNull`                                                                                                                                       |

  <span id="constructor_summary"></span>

| **Constructor Summary**              |
|--------------------------------------|
| ` PropertyMessageResourcesFactory()` 
                                       |

  <span id="method_summary"></span>

**Method Summary**

` MessageResources`

` createResources(String config)`
           Create and return a newly instansiated `MessageResources`.

 <span id="methods_inherited_from_class_org.apache.struts.util.MessageResourcesFactory"></span>

| **Methods inherited from class org.apache.struts.util.[MessageResourcesFactory](../../../../org/apache/struts/util/MessageResourcesFactory.html.md "class in org.apache.struts.util")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createFactory,  getConfig,  getFactoryClass,  getReturnNull,  setConfig,  setFactoryClass,  setReturnNull`                                                                         |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### PropertyMessageResourcesFactory

    public PropertyMessageResourcesFactory()

<span id="method_detail"></span>

**Method Detail**

### createResources

    public MessageResources createResources(String config)

Create and return a newly instansiated `MessageResources`. This method must be implemented by concrete subclasses.

**Specified by:**  
` createResources` in class `MessageResourcesFactory`

<!-- -->

**Parameters:**  
`config` - Configuration parameter(s) for the requested bundle

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
<td align="left"><a href="class-use/PropertyMessageResourcesFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/PropertyMessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/RequestUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/PropertyMessageResourcesFactory.html"><strong>FRAMES</strong></a>    <a href="PropertyMessageResourcesFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.util.MessageResourcesFactory">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
