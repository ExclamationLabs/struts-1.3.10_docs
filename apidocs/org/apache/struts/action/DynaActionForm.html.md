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
<td align="left"><a href="class-use/DynaActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionServletWrapper.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/DynaActionFormClass.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/DynaActionForm.html"><strong>FRAMES</strong></a>    <a href="DynaActionForm.html"><strong>NO FRAMES</strong></a>    
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
 Class DynaActionForm
------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.action.DynaActionForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html?is-external=true "class or interface in org.apache.commons.beanutils")

<!-- -->

**Direct Known Subclasses:**  
[DynaValidatorForm](../../../../org/apache/struts/validator/DynaValidatorForm.html.md "class in org.apache.struts.validator")

------------------------------------------------------------------------

    public class DynaActionForm

extends [ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")

implements [DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html.md?is-external=true "class or interface in org.apache.commons.beanutils")

Specialized subclass of `ActionForm` that allows the creation of form beans with dynamic sets of properties, without requiring the developer to create a Java class for each type of form bean.

**USAGE NOTE** - Since Struts 1.1, the `reset` method no longer initializes property values to those specified in `<form-property>` elements in the Struts module configuration file. If you wish to utilize that behavior, the simplest solution is to subclass `DynaActionForm` and call the `initialize` method inside it.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 11:52:08 -0500 (Sat, 12 Nov 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.DynaActionForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  DynaActionFormClass`

` dynaClass`
           The `DynaActionFormClass` with which we are associated.

`protected  HashMap`

` dynaValues`
           The set of property values for this `DynaActionForm`, keyed by property name.

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` multipartRequestHandler, servlet`                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` DynaActionForm()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` contains(String name, String key)`
           Indicates if the specified mapped property contain a value for the specified key value.

` Object`

` get(String name)`
           Return the value of a simple property with the specified name.

` Object`

` get(String name, int index)`
           Return the value of an indexed property with the specified name.

` Object`

` get(String name, String key)`
           Return the value of a mapped property with the specified name, or `null` if there is no value for the specified key.

` DynaClass`

` getDynaClass()`
           Return the `DynaClass` instance that describes the set of properties available for this `DynaBean`.

`protected  DynaProperty`

` getDynaProperty(String name)`
           Return the property descriptor for the specified property name.

` Map`

` getMap()`
           Returns the `Map` containing the property values.

` String`

` getString(String name)`
           Return the value of a `String` property with the specified name.

` String[]`

` getStrings(String name)`
           Return the value of a `String[]` property with the specified name.

` void`

` initialize(ActionMapping mapping)`
           Initialize all bean properties to their initial values, as specified in the [`FormPropertyConfig`](../../../../org/apache/struts/config/FormPropertyConfig.html.md "class in org.apache.struts.config") elements associated with the definition of this `DynaActionForm`.

` void`

` initialize(FormBeanConfig config)`
           Initialize the specified form bean.

`protected  boolean`

` isDynaAssignable(Class dest, Class source)`
           Indicates if an object of the source class is assignable to the destination class.

` void`

` remove(String name, String key)`
           Remove any existing value for the specified key on the specified mapped property.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset the properties to their `initial` value if their `reset` configuration is set to true or if `reset` is set to a list of HTTP request methods that includes the method of given `request` object.

` void`

` reset(ActionMapping mapping, ServletRequest request)`
           Reset bean properties to their default state, as needed.

` void`

` set(String name, int index, Object value)`
           Set the value of an indexed property with the specified name.

` void`

` set(String name, Object value)`
           Set the value of a simple property with the specified name.

` void`

` set(String name, String key, Object value)`
           Set the value of a mapped property with the specified name.

` String`

` toString()`
           Render a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getMultipartRequestHandler,  getServlet,  getServletWrapper,  setMultipartRequestHandler,  setServlet,  validate,  validate`                                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="dynaClass"></span>

### dynaClass

    protected DynaActionFormClass dynaClass

The `DynaActionFormClass` with which we are associated.

------------------------------------------------------------------------

<span id="dynaValues"></span>

### dynaValues

    protected HashMap dynaValues

The set of property values for this `DynaActionForm`, keyed by property name.

<span id="constructor_detail"></span>

**Constructor Detail**

### DynaActionForm

    public DynaActionForm()

<span id="method_detail"></span>

**Method Detail**

### initialize

    public void initialize(ActionMapping mapping)

Initialize all bean properties to their initial values, as specified in the [`FormPropertyConfig`](../../../../org/apache/struts/config/FormPropertyConfig.html.md "class in org.apache.struts.config") elements associated with the definition of this `DynaActionForm`.

**Parameters:**  
`mapping` - The mapping used to select this instance

------------------------------------------------------------------------

### initialize

    public void initialize(FormBeanConfig config)

Initialize the specified form bean.

**Parameters:**  
`config` - The configuration for the form bean to initialize.

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      ServletRequest request)

Reset bean properties to their default state, as needed. This method is called before the properties are repopulated by the controller.

The default implementation attempts to forward to the HTTP version of this method.

**Overrides:**  
` reset` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset the properties to their `initial` value if their `reset` configuration is set to true or if `reset` is set to a list of HTTP request methods that includes the method of given `request` object.

**Overrides:**  
` reset` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### contains

    public boolean contains(String name,
                            String key)

Indicates if the specified mapped property contain a value for the specified key value.

**Specified by:**  
`contains` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property to check

`key` - Name of the key to check

**Returns:**  
`true` if the specified mapped property contains a value for the specified key value; `true` otherwise.

**Throws:**  
`NullPointerException` - if there is no property of the specified name

`IllegalArgumentException` - if there is no mapped property of the specified name

------------------------------------------------------------------------

### get

    public Object get(String name)

Return the value of a simple property with the specified name.

**Specified by:**  
`get` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be retrieved

**Returns:**  
The value of a simple property with the specified name.

**Throws:**  
`IllegalArgumentException` - if there is no property of the specified name

`NullPointerException` - if the type specified for the property is invalid

------------------------------------------------------------------------

### get

    public Object get(String name,
                      int index)

Return the value of an indexed property with the specified name.

**Specified by:**  
`get` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be retrieved

`index` - Index of the value to be retrieved

**Returns:**  
The value of an indexed property with the specified name.

**Throws:**  
`IllegalArgumentException` - if there is no property of the specified name

`IllegalArgumentException` - if the specified property exists, but is not indexed

`NullPointerException` - if no array or List has been initialized for this property

------------------------------------------------------------------------

### get

    public Object get(String name,
                      String key)

Return the value of a mapped property with the specified name, or `null` if there is no value for the specified key.

**Specified by:**  
`get` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be retrieved

`key` - Key of the value to be retrieved

**Returns:**  
The value of a mapped property with the specified name, or `null` if there is no value for the specified key.

**Throws:**  
`NullPointerException` - if there is no property of the specified name

`IllegalArgumentException` - if the specified property exists, but is not mapped

------------------------------------------------------------------------

### getString

    public String getString(String name)

Return the value of a `String` property with the specified name. This is equivalent to calling `(String) dynaForm.get(name)`.

**Parameters:**  
`name` - Name of the property whose value is to be retrieved.

**Returns:**  
The value of a `String` property with the specified name.

**Throws:**  
`IllegalArgumentException` - if there is no property of the specified name

`NullPointerException` - if the type specified for the property is invalid

`ClassCastException` - if the property is not a String.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### getStrings

    public String[] getStrings(String name)

Return the value of a `String[]` property with the specified name. This is equivalent to calling `(String[]) dynaForm.get(name)`.

**Parameters:**  
`name` - Name of the property whose value is to be retrieved.

**Returns:**  
The value of a `String[]` property with the specified name.

**Throws:**  
`IllegalArgumentException` - if there is no property of the specified name

`NullPointerException` - if the type specified for the property is invalid

`ClassCastException` - if the property is not a String[].

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### getDynaClass

    public DynaClass getDynaClass()

Return the `DynaClass` instance that describes the set of properties available for this `DynaBean`.

**Specified by:**  
`getDynaClass` in interface `DynaBean`

<!-- -->

**Returns:**  
The `DynaClass` instance that describes the set of properties available for this `DynaBean`.

------------------------------------------------------------------------

### getMap

    public Map getMap()

Returns the `Map` containing the property values. This is done mostly to facilitate accessing the `DynaActionForm` through JavaBeans accessors, in order to use the JavaServer Pages Standard Tag Library (JSTL).

For instance, the normal JSTL EL syntax for accessing an `ActionForm` would be something like this:

      ${formbean.prop}

The JSTL EL syntax for accessing a `DynaActionForm` looks something like this (because of the presence of this `getMap()` method):

      ${dynabean.map.prop}

**Returns:**  
The `Map` containing the property values.

------------------------------------------------------------------------

### remove

    public void remove(String name,
                       String key)

Remove any existing value for the specified key on the specified mapped property.

**Specified by:**  
`remove` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property for which a value is to be removed

`key` - Key of the value to be removed

**Throws:**  
`NullPointerException` - if there is no property of the specified name

`IllegalArgumentException` - if there is no mapped property of the specified name

------------------------------------------------------------------------

### set

    public void set(String name,
                    Object value)

Set the value of a simple property with the specified name.

**Specified by:**  
`set` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be set

`value` - Value to which this property is to be set

**Throws:**  
`ConversionException` - if the specified value cannot be converted to the type required for this property

`IllegalArgumentException` - if there is no property of the specified name

`NullPointerException` - if the type specified for the property is invalid

`NullPointerException` - if an attempt is made to set a primitive property to null

------------------------------------------------------------------------

### set

    public void set(String name,
                    int index,
                    Object value)

Set the value of an indexed property with the specified name.

**Specified by:**  
`set` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be set

`index` - Index of the property to be set

`value` - Value to which this property is to be set

**Throws:**  
`ConversionException` - if the specified value cannot be converted to the type required for this property

`NullPointerException` - if there is no property of the specified name

`IllegalArgumentException` - if the specified property exists, but is not indexed

`IndexOutOfBoundsException` - if the specified index is outside the range of the underlying property

------------------------------------------------------------------------

### set

    public void set(String name,
                    String key,
                    Object value)

Set the value of a mapped property with the specified name.

**Specified by:**  
`set` in interface `DynaBean`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be set

`key` - Key of the property to be set

`value` - Value to which this property is to be set

**Throws:**  
`NullPointerException` - if there is no property of the specified name

`IllegalArgumentException` - if the specified property exists, but is not mapped

------------------------------------------------------------------------

### toString

    public String toString()

Render a String representation of this object.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
A string representation of this object.

------------------------------------------------------------------------

### getDynaProperty

    protected DynaProperty getDynaProperty(String name)

Return the property descriptor for the specified property name.

**Parameters:**  
`name` - Name of the property for which to retrieve the descriptor

**Returns:**  
The property descriptor for the specified property name.

**Throws:**  
`IllegalArgumentException` - if this is not a valid property name for our DynaClass

------------------------------------------------------------------------

### isDynaAssignable

    protected boolean isDynaAssignable(Class dest,
                                       Class source)

Indicates if an object of the source class is assignable to the destination class.

**Parameters:**  
`dest` - Destination class

`source` - Source class

**Returns:**  
`true` if the source is assignable to the destination; `false` otherwise.

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
<td align="left"><a href="class-use/DynaActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionServletWrapper.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/DynaActionFormClass.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/DynaActionForm.html"><strong>FRAMES</strong></a>    <a href="DynaActionForm.html"><strong>NO FRAMES</strong></a>    
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
