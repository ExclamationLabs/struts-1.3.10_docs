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
<td align="left"><a href="class-use/PropertyResolverImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/ViewHandlerImpl.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/PropertyResolverImpl.html"><strong>FRAMES</strong></a>    <a href="PropertyResolverImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.application
 Class PropertyResolverImpl
-----------------------------------

    java.lang.Object
      javax.faces.el.PropertyResolver
          org.apache.struts.faces.application.PropertyResolverImpl

------------------------------------------------------------------------

    public class PropertyResolverImpl

extends javax.faces.el.PropertyResolver

Custom `PropertyResolver` implementation that adds support for `DynaBean` property access to the facilities of the default `PropertyResolver` provided by JavaServer Faces.

This class implements the following specific rules:

-   Indexed variants of each call are directly passed through to the `PropertyResolver` instance that we are wrapping.
-   If the specified base object is an instance of `DynaActionForm`, and the requested property name is `map`, maintain compatibility with the way that JSP and JSTL expressions can access this property:
    -   `getValue()` will return the result of calling `getMap()` on the base object.
    -   `setValue()` will throw an exception, because the map of property values is a read-only property of the `DynaActionForm` class.
    -   `isReadOnly()` returns `true`.
    -   `getType()` returns the `Class` object for `java.util.Map`.
-   If the specified base object is an instance of `DynaBean`, provide access to its named properties as follows:
    -   `getValue()` will return the result of calling `get()` on the base object.
    -   `setValue()` will call `set()` on the base object.
    -   `isReadOnly()` returns `false` (because the DynaBean APIs provide no mechanism to make this determination, but most implementations will provide mutable properties).
    -   `getType()` returns the `Class` object for the underlying dynamic property.
-   Named variant calls with any other type of base object are passed through to the `PropertyResolver` that we are wrapping.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                                                                            |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` PropertyResolverImpl(javax.faces.el.PropertyResolver resolver)`                                                                                                                                                                                  
            Construct a new `PropertyResolver` instance, wrapping the specified instance using the Decorator pattern such that this class need implement only the new functionality it supports, and not need to re-implement the basic facilities.  |

  <span id="method_summary"></span>

**Method Summary**

` Class`

` getType(Object base, int index)`
           Return the `java.lang.Class` representing the type of value at the specified index of the specified base object, or `null` if this value is `null`.

` Class`

` getType(Object base, Object name)`
           Return the `java.lang.Class` representing the type of the specified property of the specified base object, if it can be determined; otherwise return `null`.

` Object`

` getValue(Object base, int index)`
           Return the value at the specified index of the specified base object.

` Object`

` getValue(Object base, Object name)`
           Return the value of the property with the specified name from the specified base object.

` boolean`

` isReadOnly(Object base, int index)`
           Return `true` if the value at the specified index of the specified base object is known to be immutable; otherwise, return `false`.

` boolean`

` isReadOnly(Object base, Object name)`
           Return `true` if the specified property of the specified base object is known to be immutable; otherwise, return `false`.

` void`

` setValue(Object base, int index, Object value)`
           Set the value at the specified index of the specified base object.

` void`

` setValue(Object base, Object name, Object value)`
           Set the specified value of the property with the specified name on the specified base object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### PropertyResolverImpl

    public PropertyResolverImpl(javax.faces.el.PropertyResolver resolver)

Construct a new `PropertyResolver` instance, wrapping the specified instance using the Decorator pattern such that this class need implement only the new functionality it supports, and not need to re-implement the basic facilities.

**Parameters:**  
`resolver` - The original resolver to be wrapped

**Throws:**  
`NullPointerException` - if `resolver` is `null`

<span id="method_detail"></span>

**Method Detail**

### getValue

    public Object getValue(Object base,
                           Object name)
                    throws javax.faces.el.PropertyNotFoundException

Return the value of the property with the specified name from the specified base object.

**Specified by:**  
`getValue` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property value is to be returned

`name` - Name of the property to be returned

**Throws:**  
`NullPointerException` - if `base` or `name` is `null`

`javax.faces.el.PropertyNotFoundException` - if the specified property name does not exist, or is not readable

------------------------------------------------------------------------

### getValue

    public Object getValue(Object base,
                           int index)
                    throws javax.faces.el.PropertyNotFoundException

Return the value at the specified index of the specified base object.

**Specified by:**  
`getValue` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property value is to be returned

`index` - Index of the value to return

**Throws:**  
`IndexOutOfBoundsException` - if thrown by the underlying access to the base object

`NullPointerException` - if `base` is `null`

`javax.faces.el.PropertyNotFoundException` - if some other exception occurs

------------------------------------------------------------------------

### setValue

    public void setValue(Object base,
                         Object name,
                         Object value)
                  throws javax.faces.el.PropertyNotFoundException

Set the specified value of the property with the specified name on the specified base object.

**Specified by:**  
`setValue` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property value is to be set

`name` - Name of the property to be set

`value` - Value of the property to be set

**Throws:**  
`NullPointerException` - if `base` or `name` is `null`

`javax.faces.el.PropertyNotFoundException` - if the specified property name does not exist, or is not writeable

------------------------------------------------------------------------

### setValue

    public void setValue(Object base,
                         int index,
                         Object value)
                  throws javax.faces.el.PropertyNotFoundException

Set the value at the specified index of the specified base object.

**Specified by:**  
`setValue` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property value is to be set

`index` - Index of the value to set

`value` - Value to be set

**Throws:**  
`IndexOutOfBoundsException` - if thrown by the underlying access to the base object

`NullPointerException` - if `base` is `null`

`javax.faces.el.PropertyNotFoundException` - if some other exception occurs

------------------------------------------------------------------------

### isReadOnly

    public boolean isReadOnly(Object base,
                              Object name)
                       throws javax.faces.el.PropertyNotFoundException

Return `true` if the specified property of the specified base object is known to be immutable; otherwise, return `false`.

**Specified by:**  
`isReadOnly` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property is to analyzed

`name` - Name of the property to be analyzed

**Throws:**  
`NullPointerException` - if `base` or `name` is `null`

`javax.faces.el.PropertyNotFoundException` - if the specified property name does not exist

------------------------------------------------------------------------

### isReadOnly

    public boolean isReadOnly(Object base,
                              int index)
                       throws javax.faces.el.PropertyNotFoundException

Return `true` if the value at the specified index of the specified base object is known to be immutable; otherwise, return `false`.

**Specified by:**  
`isReadOnly` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property is to analyzed

`index` - Index of the value whose type is to be returned

**Throws:**  
`IndexOutOfBoundsException` - if thrown by the underlying accessed to the indexed property

`NullPointerException` - if `base` is `null`

`javax.faces.el.PropertyNotFoundException` - if some other exception occurs

------------------------------------------------------------------------

### getType

    public Class getType(Object base,
                         Object name)
                  throws javax.faces.el.PropertyNotFoundException

Return the `java.lang.Class` representing the type of the specified property of the specified base object, if it can be determined; otherwise return `null`.

**Specified by:**  
`getType` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property is to analyzed

`name` - Name of the property to be analyzed

**Throws:**  
`NullPointerException` - if `base` or `name` is `null`

`javax.faces.el.PropertyNotFoundException` - if the specified property name does not exist

------------------------------------------------------------------------

### getType

    public Class getType(Object base,
                         int index)
                  throws javax.faces.el.PropertyNotFoundException

Return the `java.lang.Class` representing the type of value at the specified index of the specified base object, or `null` if this value is `null`.

**Specified by:**  
`getType` in class `javax.faces.el.PropertyResolver`

<!-- -->

**Parameters:**  
`base` - The base object whose property is to analyzed

`index` - Index of the value whose type is to be returned

**Throws:**  
`IndexOutOfBoundsException` - if thrown by the underlying accessed to the indexed property

`NullPointerException` - if `base` is `null`

`javax.faces.el.PropertyNotFoundException` - if some other exception occurs

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
<td align="left"><a href="class-use/PropertyResolverImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/FacesTilesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/application/ViewHandlerImpl.html" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/PropertyResolverImpl.html"><strong>FRAMES</strong></a>    <a href="PropertyResolverImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
