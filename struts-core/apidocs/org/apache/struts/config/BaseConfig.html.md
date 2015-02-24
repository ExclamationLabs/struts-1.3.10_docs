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
<td align="left"><a href="class-use/BaseConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigHelper.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/BaseConfig.html"><strong>FRAMES</strong></a>    <a href="BaseConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class BaseConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[ActionConfig](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config"), [ControllerConfig](../../../../org/apache/struts/config/ControllerConfig.html "class in org.apache.struts.config"), [ExceptionConfig](../../../../org/apache/struts/config/ExceptionConfig.html "class in org.apache.struts.config"), [FormBeanConfig](../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config"), [FormPropertyConfig](../../../../org/apache/struts/config/FormPropertyConfig.html "class in org.apache.struts.config"), [ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config"), [MessageResourcesConfig](../../../../org/apache/struts/config/MessageResourcesConfig.html "class in org.apache.struts.config"), [ModuleConfigImpl](../../../../org/apache/struts/config/impl/ModuleConfigImpl.html "class in org.apache.struts.config.impl")

------------------------------------------------------------------------

    public abstract class BaseConfig

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A abstract base class for all config classes. Provide basic support for arbitrary properties

**Since:**  
Struts 1.3

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.BaseConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  boolean`

`configured`
           Indicates if configuration of this component been completed.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` BaseConfig()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  Properties`

` copyProperties()`
           Return a copy of the properties held by this object.

` void`

`freeze()`
           Freeze the configuration of this action.

`protected  Properties`

` getProperties()`
            Return the entire set of properties configured for this object.

` String`

` getProperty(String key)`
           Return the property-value for the specified key, if any; otherwise return `null`.

`protected  void`

` inheritProperties(BaseConfig baseConfig)`
           Compare the properties of this config with that of the given and copy those that are not present.

`protected  void`

` setProperties(Properties properties)`
           Set the entire set of properties configured for this object.

` void`

` setProperty(String key, String value)`
            Set an arbitary key/value pair which can be retrieved by this config class.

` void`

` throwIfConfigured()`
           Throw `IllegalStateException` if configuration is frozen.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="configured"></span>

### configured

    protected boolean configured

Indicates if configuration of this component been completed. TODO change protected to private and use methods provided by extenders?

<span id="constructor_detail"></span>

**Constructor Detail**

### BaseConfig

    public BaseConfig()

<span id="method_detail"></span>

**Method Detail**

### freeze

    public void freeze()

Freeze the configuration of this action.

------------------------------------------------------------------------

### throwIfConfigured

    public void throwIfConfigured()

Throw `IllegalStateException` if configuration is frozen.

**Throws:**  
`IllegalStateException` - if configuration is frozen

------------------------------------------------------------------------

### setProperty

    public void setProperty(String key,
                            String value)

Set an arbitary key/value pair which can be retrieved by this config class. This facility should eliminate many use cases for subclassing `*Config` classes by providing a mechanism to pass any amount of arbitrary configuration information into an config class.

This method must not be called after configuration is complete, or an `IllegalStateException` will be thrown.

**Example**

     <action path="/example" type="com.example.MyAction">
        <set-property key="foo" property="bar" />
     </action>
     

**Parameters:**  
`key` - the key by which this value will be retrieved

`value` - the value to store with the supplied key

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### getProperty

    public String getProperty(String key)

Return the property-value for the specified key, if any; otherwise return `null`.

**Parameters:**  
`key` - a key specified in the `struts-config` file

**Returns:**  
the value stored with the supplied key

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### getProperties

    protected Properties getProperties()

Return the entire set of properties configured for this object. At this time, this only needs to be exposed to support inheritance, so choosing a conservative access modifier ("protected").

**Returns:**  
set of properties configured for this object

------------------------------------------------------------------------

### setProperties

    protected void setProperties(Properties properties)

Set the entire set of properties configured for this object. At this time, this only needs to be exposed to support inheritance, so choosing a conservative access modifier ("protected").

------------------------------------------------------------------------

### inheritProperties

    protected void inheritProperties(BaseConfig baseConfig)

Compare the properties of this config with that of the given and copy those that are not present. This method is used by subclasses that support configuration inheritance.

**Parameters:**  
`baseConfig` - The config object to copy properties from.

------------------------------------------------------------------------

### copyProperties

    protected Properties copyProperties()

Return a copy of the properties held by this object.

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
<td align="left"><a href="class-use/BaseConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigHelper.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/BaseConfig.html"><strong>FRAMES</strong></a>    <a href="BaseConfig.html"><strong>NO FRAMES</strong></a>    
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
