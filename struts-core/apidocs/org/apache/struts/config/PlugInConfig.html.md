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
<td align="left"><a href="class-use/PlugInConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ModuleConfigFactory.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/PlugInConfig.html"><strong>FRAMES</strong></a>    <a href="PlugInConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class PlugInConfig
------------------------

    java.lang.Object
      org.apache.struts.config.PlugInConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class PlugInConfig

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A JavaBean representing the configuration information of a `<plug-in>` element in a Struts configuration file.

Note that this class does not extend `BaseConfig` because it is more "internal" than the other classes which do, and because this class has an existing "properties" object which collides with the one in `BaseConfig`. Also, since one always writes a concrete PlugIn implementation, there seems to be less call for an arbitrary property map; one can simply use bean properties instead.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-12 18:41:19 -0400 (Thu, 12 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.PlugInConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`className`
           The fully qualified Java class name of the `PlugIn` implementation class being configured.

`protected  boolean`

` configured`
           Has this component been completely configured?

`protected  Map`

` properties`
           A `Map` of the name-value pairs that will be used to configure the property values of a `PlugIn` instance.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` PlugInConfig()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addProperty(String name, String value)`
           Add a new property name and value to the set that will be used to configure the `PlugIn` instance.

` void`

`freeze()`
           Freeze the configuration of this component.

` String`

` getClassName()`
            

` Map`

` getProperties()`
           Return the properties that will be used to configure a `PlugIn` instance.

` void`

` setClassName(String className)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="configured"></span>

### configured

    protected boolean configured

Has this component been completely configured?

------------------------------------------------------------------------

<span id="properties"></span>

### properties

    protected Map properties

A `Map` of the name-value pairs that will be used to configure the property values of a `PlugIn` instance.

------------------------------------------------------------------------

<span id="className"></span>

### className

    protected String className

The fully qualified Java class name of the `PlugIn` implementation class being configured.

<span id="constructor_detail"></span>

**Constructor Detail**

### PlugInConfig

    public PlugInConfig()

<span id="method_detail"></span>

**Method Detail**

### getClassName

    public String getClassName()

------------------------------------------------------------------------

### setClassName

    public void setClassName(String className)

------------------------------------------------------------------------

### addProperty

    public void addProperty(String name,
                            String value)

Add a new property name and value to the set that will be used to configure the `PlugIn` instance.

**Parameters:**  
`name` - Property name

`value` - Property value

------------------------------------------------------------------------

### freeze

    public void freeze()

Freeze the configuration of this component.

------------------------------------------------------------------------

### getProperties

    public Map getProperties()

Return the properties that will be used to configure a `PlugIn` instance.

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
<td align="left"><a href="class-use/PlugInConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ModuleConfigFactory.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/PlugInConfig.html"><strong>FRAMES</strong></a>    <a href="PlugInConfig.html"><strong>NO FRAMES</strong></a>    
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
