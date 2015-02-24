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
<td align="left"><a href="class-use/ExceptionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ControllerConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/FormBeanConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="ExceptionConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class ExceptionConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ExceptionConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ExceptionConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-08-06 18:03:30 -0400 (Sat, 06 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.ExceptionConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`bundle`
           The servlet context attribute under which the message resources bundle to be used for this exception is located.

`protected  boolean`

` extensionProcessed`
           Have the inheritance values for this class been applied?

`protected  String`

` handler`
           The fully qualified Java class name of the exception handler class which should be instantiated to handle this exception.

`protected  String`

` inherit`
           The type of the ExceptionConfig that this object should inherit properties from.

`protected  String`

`key`
           The message resources key specifying the error message associated with this exception.

`protected  String`

`path`
           The module-relative path of the resource to forward to if this exception occurs during an `Action`.

`protected  String`

`scope`
           The scope in which we should expose the ActionMessage for this exception handler.

`protected  String`

`type`
           The fully qualified Java class name of the exception that is to be handled by this handler.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ExceptionConfig()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  boolean`

` checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

` String`

` getBundle()`
            

` String`

` getExtends()`
            

` String`

` getHandler()`
            

` String`

` getKey()`
            

` String`

` getPath()`
            

` String`

` getScope()`
            

` String`

` getType()`
            

` void`

` inheritFrom(ExceptionConfig config)`
           Inherit values that have not been overridden from the provided config object.

` boolean`

` isExtensionProcessed()`
            

` void`

` processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ExceptionConfig that this instance is extending.

` void`

` setBundle(String bundle)`
            

` void`

` setExtends(String inherit)`
            

` void`

` setHandler(String handler)`
            

` void`

` setKey(String key)`
            

` void`

` setPath(String path)`
            

` void`

` setScope(String scope)`
            

` void`

` setType(String type)`
            

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

<span id="bundle"></span>

### bundle

    protected String bundle

The servlet context attribute under which the message resources bundle to be used for this exception is located. If not set, the default message resources for the current module is assumed.

------------------------------------------------------------------------

<span id="inherit"></span>

### inherit

    protected String inherit

The type of the ExceptionConfig that this object should inherit properties from.

------------------------------------------------------------------------

<span id="extensionProcessed"></span>

### extensionProcessed

    protected boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

<span id="handler"></span>

### handler

    protected String handler

The fully qualified Java class name of the exception handler class which should be instantiated to handle this exception.

------------------------------------------------------------------------

<span id="key"></span>

### key

    protected String key

The message resources key specifying the error message associated with this exception.

------------------------------------------------------------------------

<span id="path"></span>

### path

    protected String path

The module-relative path of the resource to forward to if this exception occurs during an `Action`.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope in which we should expose the ActionMessage for this exception handler.

------------------------------------------------------------------------

<span id="type"></span>

### type

    protected String type

The fully qualified Java class name of the exception that is to be handled by this handler.

<span id="constructor_detail"></span>

**Constructor Detail**

### ExceptionConfig

    public ExceptionConfig()

<span id="method_detail"></span>

**Method Detail**

### getBundle

    public String getBundle()

------------------------------------------------------------------------

### setBundle

    public void setBundle(String bundle)

------------------------------------------------------------------------

### getExtends

    public String getExtends()

------------------------------------------------------------------------

### setExtends

    public void setExtends(String inherit)

------------------------------------------------------------------------

### isExtensionProcessed

    public boolean isExtensionProcessed()

------------------------------------------------------------------------

### getHandler

    public String getHandler()

------------------------------------------------------------------------

### setHandler

    public void setHandler(String handler)

------------------------------------------------------------------------

### getKey

    public String getKey()

------------------------------------------------------------------------

### setKey

    public void setKey(String key)

------------------------------------------------------------------------

### getPath

    public String getPath()

------------------------------------------------------------------------

### setPath

    public void setPath(String path)

------------------------------------------------------------------------

### getScope

    public String getScope()

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

------------------------------------------------------------------------

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### checkCircularInheritance

    protected boolean checkCircularInheritance(ModuleConfig moduleConfig,
                                               ActionConfig actionConfig)

Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this config is from.

`actionConfig` - The [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") that this config is from, if applicable. This parameter must be null if this is a global handler.

**Returns:**  
true if circular inheritance was detected.

------------------------------------------------------------------------

### inheritFrom

    public void inheritFrom(ExceptionConfig config)
                     throws ClassNotFoundException,
                            IllegalAccessException,
                            InstantiationException,
                            InvocationTargetException

Inherit values that have not been overridden from the provided config object. Subclasses overriding this method should verify that the given parameter is of a class that contains a property it is trying to inherit:

     if (config instanceof MyCustomConfig) {
         MyCustomConfig myConfig =
             (MyCustomConfig) config;

         if (getMyCustomProp() == null) {
             setMyCustomProp(myConfig.getMyCustomProp());
         }
     }
     

If the given `config` is extending another object, those extensions should be resolved before it's used as a parameter to this method.

**Parameters:**  
`config` - The object that this instance will be inheriting its values from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`processExtends(ModuleConfig, ActionConfig)`](../../../../org/apache/struts/config/ExceptionConfig.html.md#processExtends(org.apache.struts.config.ModuleConfig,%20org.apache.struts.config.ActionConfig))

------------------------------------------------------------------------

### processExtends

    public void processExtends(ModuleConfig moduleConfig,
                               ActionConfig actionConfig)
                        throws ClassNotFoundException,
                               IllegalAccessException,
                               InstantiationException,
                               InvocationTargetException

Inherit configuration information from the ExceptionConfig that this instance is extending. This method verifies that any exception config object that it inherits from has also had its processExtends() method called.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this config is from.

`actionConfig` - The [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") that this config is from, if applicable. This must be null for global forwards.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(ExceptionConfig)`](../../../../org/apache/struts/config/ExceptionConfig.html.md#inheritFrom(org.apache.struts.config.ExceptionConfig))

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
<td align="left"><a href="class-use/ExceptionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ControllerConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/FormBeanConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="ExceptionConfig.html"><strong>NO FRAMES</strong></a>    
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
