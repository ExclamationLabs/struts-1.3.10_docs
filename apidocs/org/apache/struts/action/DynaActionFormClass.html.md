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
<td align="left"><a href="class-use/DynaActionFormClass.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/DynaActionForm.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ExceptionHandler.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/DynaActionFormClass.html"><strong>FRAMES</strong></a>    <a href="DynaActionFormClass.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class DynaActionFormClass
--------------------------

    java.lang.Object
      org.apache.struts.action.DynaActionFormClass

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [DynaClass](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaClass.html?is-external=true "class or interface in org.apache.commons.beanutils")

------------------------------------------------------------------------

    public class DynaActionFormClass

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [DynaClass](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaClass.html.md?is-external=true "class or interface in org.apache.commons.beanutils"), [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html?is-external=true "class or interface in java.io")

Implementation of `DynaClass` for `DynaActionForm` classes that allow developers to define ActionForms without having to individually code all of the classes. **NOTE** - This class is only used in the internal implementation of dynamic action form beans. Application developers never need to consult this documentation.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-01-17 07:26:20 -0500 (Tue, 17 Jan 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.DynaActionFormClass)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Class`

` beanClass`
           The `DynaActionForm` implementation `Class` which we will use to create new bean instances.

`protected  FormBeanConfig`

` config`
           The form bean configuration information for this class.

`protected  String`

` name`
           The "dynamic class name" for this `DynaClass`.

`protected  DynaProperty[]`

` properties`
           The set of dynamic properties that are part of this DynaClass.

`protected  HashMap`

` propertiesMap`
           The set of dynamic properties that are part of this `DynaClass`, keyed by the property name.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                     |
|---------------------------------------------------------------------------------------------|
| ` DynaActionFormClass(FormBeanConfig config)`                                               
            Construct a new `DynaActionFormClass` for the specified form bean configuration.  |

  <span id="method_summary"></span>

**Method Summary**

`static DynaActionFormClass`

` createDynaActionFormClass(FormBeanConfig config)`
           Return the `DynaActionFormClass` instance for the specified form bean configuration instance.

`protected  Class`

` getBeanClass()`
           Return the implementation class we are using to construct new instances, re-introspecting our [`FormBeanConfig`](../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") if necessary (that is, after being deserialized, since `beanClass` is marked transient).

` DynaProperty[]`

` getDynaProperties()`
           Return an array of `DynaProperty`s for the properties currently defined in this `DynaClass`.

` DynaProperty`

` getDynaProperty(String name)`
           Return a property descriptor for the specified property, if it exists; otherwise, return `null`.

` String`

` getName()`
           Return the name of this `DynaClass` (analogous to the `getName()` method of `java.lang.Class`, which allows the same `DynaClass` implementation class to support different dynamic classes, with different sets of properties.

`protected  void`

` introspect(FormBeanConfig config)`
           Introspect our form bean configuration to identify the supported properties.

` DynaBean`

` newInstance()`
           Instantiate and return a new [`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action") instance, associated with this `DynaActionFormClass`.

` String`

` toString()`
           Render a `String` representation of this object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="beanClass"></span>

### beanClass

    protected transient Class beanClass

The `DynaActionForm` implementation `Class` which we will use to create new bean instances.

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected FormBeanConfig config

The form bean configuration information for this class.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The "dynamic class name" for this `DynaClass`.

------------------------------------------------------------------------

<span id="properties"></span>

### properties

    protected DynaProperty[] properties

The set of dynamic properties that are part of this DynaClass.

------------------------------------------------------------------------

<span id="propertiesMap"></span>

### propertiesMap

    protected HashMap propertiesMap

The set of dynamic properties that are part of this `DynaClass`, keyed by the property name. Individual descriptor instances will be the same instances as those in the `properties` list.

<span id="constructor_detail"></span>

**Constructor Detail**

### DynaActionFormClass

    public DynaActionFormClass(FormBeanConfig config)

Construct a new `DynaActionFormClass` for the specified form bean configuration. This constructor is private; `DynaActionFormClass` instances will be created as needed via calls to the static `createDynaActionFormClass()` method.

**Parameters:**  
`config` - The FormBeanConfig instance describing the properties of the bean to be created

**Throws:**  
`IllegalArgumentException` - if the bean implementation class specified in the configuration is not DynaActionForm (or a subclass of DynaActionForm)

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

Return the name of this `DynaClass` (analogous to the `getName()` method of `java.lang.Class`, which allows the same `DynaClass` implementation class to support different dynamic classes, with different sets of properties.

**Specified by:**  
`getName` in interface `DynaClass`

<!-- -->

**Returns:**  
The name of this `DynaClass`.

------------------------------------------------------------------------

### getDynaProperty

    public DynaProperty getDynaProperty(String name)

Return a property descriptor for the specified property, if it exists; otherwise, return `null`.

**Specified by:**  
`getDynaProperty` in interface `DynaClass`

<!-- -->

**Parameters:**  
`name` - Name of the dynamic property for which a descriptor is requested

**Returns:**  
A property descriptor for the specified property.

**Throws:**  
`IllegalArgumentException` - if no property name is specified

------------------------------------------------------------------------

### getDynaProperties

    public DynaProperty[] getDynaProperties()

Return an array of `DynaProperty`s for the properties currently defined in this `DynaClass`. If no properties are defined, a zero-length array will be returned.

**Specified by:**  
`getDynaProperties` in interface `DynaClass`

<!-- -->

**Returns:**  
An array of property instances for this class.

------------------------------------------------------------------------

### newInstance

    public DynaBean newInstance()
                         throws IllegalAccessException,
                                InstantiationException

Instantiate and return a new [`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action") instance, associated with this `DynaActionFormClass`. The properties of the returned [`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html "class in org.apache.struts.action") will have been initialized to the default values specified in the form bean configuration information.

**Specified by:**  
`newInstance` in interface `DynaClass`

<!-- -->

**Returns:**  
A new [`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action") instance.

**Throws:**  
`IllegalAccessException` - if the Class or the appropriate constructor is not accessible

`InstantiationException` - if this Class represents an abstract class, an array class, a primitive type, or void; or if instantiation fails for some other reason

------------------------------------------------------------------------

### toString

    public String toString()

Render a `String` representation of this object.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
The string representation of this instance.

------------------------------------------------------------------------

### createDynaActionFormClass

    public static DynaActionFormClass createDynaActionFormClass(FormBeanConfig config)

Return the `DynaActionFormClass` instance for the specified form bean configuration instance.

**Parameters:**  
`config` - The config for which the class should be created.

**Returns:**  
The instance for the specified form bean config.

------------------------------------------------------------------------

### getBeanClass

    protected Class getBeanClass()

Return the implementation class we are using to construct new instances, re-introspecting our [`FormBeanConfig`](../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") if necessary (that is, after being deserialized, since `beanClass` is marked transient).

**Returns:**  
The implementation class used to construct new instances.

------------------------------------------------------------------------

### introspect

    protected void introspect(FormBeanConfig config)

Introspect our form bean configuration to identify the supported properties.

**Parameters:**  
`config` - The FormBeanConfig instance describing the properties of the bean to be created

**Throws:**  
`IllegalArgumentException` - if the bean implementation class specified in the configuration is not DynaActionForm (or a subclass of DynaActionForm)

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
<td align="left"><a href="class-use/DynaActionFormClass.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/DynaActionForm.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ExceptionHandler.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/DynaActionFormClass.html"><strong>FRAMES</strong></a>    <a href="DynaActionFormClass.html"><strong>NO FRAMES</strong></a>    
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
