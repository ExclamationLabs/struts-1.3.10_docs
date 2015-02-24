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
<td align="left"><a href="class-use/MessageResourcesConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ForwardConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ModuleConfig.html" title="interface in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/MessageResourcesConfig.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class MessageResourcesConfig
-----------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.MessageResourcesConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class MessageResourcesConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of a `<message-resources>` element in a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.MessageResourcesConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` factory`
           Fully qualified Java class name of the MessageResourcesFactory class we should use.

`protected  String`

` key`
           The servlet context attributes key under which this MessageResources instance is stored.

`protected  boolean`

` nullValue`
           Should we return `null` for unknown message keys?

`protected  String`

` parameter`
           Parameter that is passed to the `createResources()` method of our MessageResourcesFactory implementation.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**     |
|-----------------------------|
| ` MessageResourcesConfig()` 
                              |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getFactory()`
            

` String`

` getKey()`
            

` boolean`

` getNull()`
            

` String`

` getParameter()`
            

` boolean`

` isEscape()`
           Indicates whether 'escape processing' should be performed on the error message string.

` void`

` setEscape(boolean escape)`
           Set whether 'escape processing' should be performed on the error message string.

` void`

` setFactory(String factory)`
            

` void`

` setKey(String key)`
            

` void`

` setNull(boolean nullValue)`
            

` void`

` setParameter(String parameter)`
            

` String`

` toString()`
           Return a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties, freeze,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                    |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="factory"></span>

### factory

    protected String factory

Fully qualified Java class name of the MessageResourcesFactory class we should use.

------------------------------------------------------------------------

<span id="key"></span>

### key

    protected String key

The servlet context attributes key under which this MessageResources instance is stored.

------------------------------------------------------------------------

<span id="nullValue"></span>

### nullValue

    protected boolean nullValue

Should we return `null` for unknown message keys?

------------------------------------------------------------------------

<span id="parameter"></span>

### parameter

    protected String parameter

Parameter that is passed to the `createResources()` method of our MessageResourcesFactory implementation.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessageResourcesConfig

    public MessageResourcesConfig()

<span id="method_detail"></span>

**Method Detail**

### getFactory

    public String getFactory()

------------------------------------------------------------------------

### setFactory

    public void setFactory(String factory)

------------------------------------------------------------------------

### getKey

    public String getKey()

------------------------------------------------------------------------

### setKey

    public void setKey(String key)

------------------------------------------------------------------------

### getNull

    public boolean getNull()

------------------------------------------------------------------------

### setNull

    public void setNull(boolean nullValue)

------------------------------------------------------------------------

### isEscape

    public boolean isEscape()

Indicates whether 'escape processing' should be performed on the error message string.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### setEscape

    public void setEscape(boolean escape)

Set whether 'escape processing' should be performed on the error message string.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### getParameter

    public String getParameter()

------------------------------------------------------------------------

### setParameter

    public void setParameter(String parameter)

------------------------------------------------------------------------

### toString

    public String toString()

Return a String representation of this object.

**Overrides:**  
`toString` in class `Object`

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
<td align="left"><a href="class-use/MessageResourcesConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ForwardConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ModuleConfig.html" title="interface in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/MessageResourcesConfig.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesConfig.html"><strong>NO FRAMES</strong></a>    
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
