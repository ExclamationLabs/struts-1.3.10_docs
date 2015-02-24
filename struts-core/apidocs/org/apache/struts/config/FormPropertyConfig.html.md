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
<td align="left"><a href="class-use/FormPropertyConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/FormBeanConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ForwardConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/FormPropertyConfig.html"><strong>FRAMES</strong></a>    <a href="FormPropertyConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class FormPropertyConfig
-------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.FormPropertyConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class FormPropertyConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of a `<form-property>` element in a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 11:52:08 -0500 (Sat, 12 Nov 2005)$

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.FormPropertyConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` initial`
           String representation of the initial value for this property.

`protected  String`

` name`
           The JavaBean property name of the property described by this element.

`protected  String`

` reset`
           The conditions under which the property described by this element should be reset to its `initial` value when the form's `reset` method is called.

`protected  int`

` size`
           The size of the array to be created if this property is an array type and there is no specified `initial` value.

`protected  String`

` type`
           The fully qualified Java class name of the implementation class of this bean property, optionally followed by `[]` to indicate that the property is indexed.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                 |
|-----------------------------------------------------------------------------------------|
| ` FormPropertyConfig()`                                                                 
            Standard no-arguments constructor for dynamic instantiation.                  |
| ` FormPropertyConfig(String name, String type, String initial)`                         
            Constructor that preconfigures the relevant properties.                       |
| ` FormPropertyConfig(String name, String type, String initial, int size)`               
            Constructor that preconfigures the relevant properties.                       |
| ` FormPropertyConfig(String name, String type, String initial, String reset)`           
            Constructor that preconfigures the relevant properties.                       |
| ` FormPropertyConfig(String name, String type, String initial, String reset, int size)` 
            Constructor that preconfigures the relevant properties.                       |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getInitial()`
            

` String`

` getName()`
            

` String`

` getReset()`
            

` int`

` getSize()`
            

` String`

` getType()`
            

` Class`

` getTypeClass()`
           Return a Class corresponds to the value specified for the `type` property, taking into account the trailing "[]" for arrays (as well as the ability to specify primitive Java types).

` void`

` inheritFrom(FormPropertyConfig config)`
           Inherit values that have not been overridden from the provided config object.

` Object`

` initial()`
           Return an object representing the initial value of this property.

` void`

` setInitial(String initial)`
            

` void`

` setName(String name)`
            

` void`

` setReset(String reset)`
            

` void`

` setSize(int size)`
            

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

<span id="initial"></span>

### initial

    protected String initial

String representation of the initial value for this property.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The JavaBean property name of the property described by this element.

------------------------------------------------------------------------

<span id="reset"></span>

### reset

    protected String reset

The conditions under which the property described by this element should be reset to its `initial` value when the form's `reset` method is called.

This may be set to true (to always reset the property) or a comma-separated list of HTTP request methods.

**Since:**  
Struts 1.3

------------------------------------------------------------------------

<span id="size"></span>

### size

    protected int size

The size of the array to be created if this property is an array type and there is no specified `initial` value. This value must be non-negative.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="type"></span>

### type

    protected String type

The fully qualified Java class name of the implementation class of this bean property, optionally followed by `[]` to indicate that the property is indexed.

<span id="constructor_detail"></span>

**Constructor Detail**

### FormPropertyConfig

    public FormPropertyConfig()

Standard no-arguments constructor for dynamic instantiation.

------------------------------------------------------------------------

### FormPropertyConfig

    public FormPropertyConfig(String name,
                              String type,
                              String initial)

Constructor that preconfigures the relevant properties.

**Parameters:**  
`name` - Name of this property

`type` - Fully qualified class name of this property

`initial` - Initial value of this property (if any)

------------------------------------------------------------------------

### FormPropertyConfig

    public FormPropertyConfig(String name,
                              String type,
                              String initial,
                              String reset)

Constructor that preconfigures the relevant properties.

**Parameters:**  
`name` - Name of this property

`type` - Fully qualified class name of this property

`initial` - Initial value of this property (if any)

`reset` - The conditions under which this property will be reset to its initial value.

------------------------------------------------------------------------

### FormPropertyConfig

    public FormPropertyConfig(String name,
                              String type,
                              String initial,
                              int size)

Constructor that preconfigures the relevant properties.

**Parameters:**  
`name` - Name of this property

`type` - Fully qualified class name of this property

`initial` - Initial value of this property (if any)

`size` - Size of the array to be created if this property is an array with no defined initial value

------------------------------------------------------------------------

### FormPropertyConfig

    public FormPropertyConfig(String name,
                              String type,
                              String initial,
                              String reset,
                              int size)

Constructor that preconfigures the relevant properties.

**Parameters:**  
`name` - Name of this property

`type` - Fully qualified class name of this property

`initial` - Initial value of this property (if any)

`size` - Size of the array to be created if this property is an array with no defined initial value

`reset` - The conditions under which this property will be reset to its initial value.

<span id="method_detail"></span>

**Method Detail**

### getInitial

    public String getInitial()

------------------------------------------------------------------------

### setInitial

    public void setInitial(String initial)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getReset

    public String getReset()

------------------------------------------------------------------------

### setReset

    public void setReset(String reset)

------------------------------------------------------------------------

### getSize

    public int getSize()

------------------------------------------------------------------------

### setSize

    public void setSize(int size)

------------------------------------------------------------------------

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### getTypeClass

    public Class getTypeClass()

Return a Class corresponds to the value specified for the `type` property, taking into account the trailing "[]" for arrays (as well as the ability to specify primitive Java types).

------------------------------------------------------------------------

### initial

    public Object initial()

Return an object representing the initial value of this property. This is calculated according to the following algorithm:

-   If the value you have specified for the `type` property represents an array (i.e. it ends with "[]"):
    -   If you have specified a value for the `initial` property, `ConvertUtils.convert` will be called to convert it into an instance of the specified array type.
    -   If you have not specified a value for the `initial` property, an array of the length specified by the `size` property will be created. Each element of the array will be instantiated via the zero-args constructor on the specified class (if any). Otherwise, `null` will be returned.
-   If the value you have specified for the `type` property does not represent an array:
    -   If you have specified a value for the `initial` property, `ConvertUtils.convert` will be called to convert it into an object instance.
    -   If you have not specified a value for the `initial` attribute, Struts will instantiate an instance via the zero-args constructor on the specified class (if any). Otherwise, `null` will be returned.

------------------------------------------------------------------------

### inheritFrom

    public void inheritFrom(FormPropertyConfig config)
                     throws IllegalAccessException,
                            InvocationTargetException,
                            InstantiationException,
                            ClassNotFoundException

Inherit values that have not been overridden from the provided config object. Subclasses overriding this method should verify that the given parameter is of a class that contains a property it is trying to inherit:

     if (config instanceof MyCustomFormPropertyConfig) {
         MyCustomFormPropertyConfig myConfig =
             (MyCustomFormPropertyConfig) config;

         if (getMyCustomProp() == null) {
             setMyCustomProp(myConfig.getMyCustomProp());
         }
     }
     

**Parameters:**  
`config` - The object that this instance will be inheriting its values from.

**Throws:**  
`IllegalAccessException`

`InvocationTargetException`

`InstantiationException`

`ClassNotFoundException`

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
<td align="left"><a href="class-use/FormPropertyConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/FormBeanConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ForwardConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/FormPropertyConfig.html"><strong>FRAMES</strong></a>    <a href="FormPropertyConfig.html"><strong>NO FRAMES</strong></a>    
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
