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
<td align="left"><a href="class-use/MessagesMap.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/util/StrutsContext.html.md" title="class in org.apache.struts.faces.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/MessagesMap.html"><strong>FRAMES</strong></a>    <a href="MessagesMap.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.util
 Class MessagesMap
----------------------------

    java.lang.Object
      org.apache.struts.faces.util.MessagesMap

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")

------------------------------------------------------------------------

    public class MessagesMap

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")

A limited immutable `Map` implementation that wraps the `MessageResources` instance for the specified `Locale`. Exposing the messages as a `Map` makes them easily accessible via value binding expressions, as well as JSP 2.0 expression language expressions.

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_java.util.Map"></span>

| **Nested classes/interfaces inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Map.Entry<K,V>`                                                                                                                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` MessagesMap(MessageResources messages, Locale locale)`                                                                                                                                                                                                         
            Construct a new [`MessagesMap`](../../../../../org/apache/struts/faces/util/MessagesMap.html.md "class in org.apache.struts.faces.util") instance that wraps the specified `MessageResources` instance, and returns messages for the specified `Locale`.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` clear()`
           The `clear()` method is not supported.

` boolean`

` containsKey(Object key)`
           Return `true` if there is a message for the specified key.

` boolean`

` containsValue(Object value)`
           The `containsValue()` method is not supported.

` Set`

` entrySet()`
           The `entrySet()` method is not supported.

` boolean`

` equals(Object o)`
           The `equals` method checks whether equal `MessageResources` and `Locale` are being wrapped.

` Object`

` get(Object key)`
           Return the message string for the specified key.

` int`

` hashCode()`
           The `hashCode()` method returns values that will be identical if the `equals` method returns `true`.

` boolean`

` isEmpty()`
           The `isEmpty()` method returns `false`, on the assumption that there is always at least one message available.

` Set`

` keySet()`
           The `keySet()` method is not supported.

` Object`

` put(Object key, Object value)`
           The `put()` method is not supported.

` void`

` putAll(Map map)`
           The `putAll()` method is not supported.

` Object`

` remove(Object key)`
           The `remove()` method is not supported.

` int`

` size()`
           The `size()` method is not supported.

` Collection`

` values()`
           The `values()` method is not supported.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, finalize, getClass, notify, notifyAll, toString, wait, wait, wait`                                                                                            |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MessagesMap

    public MessagesMap(MessageResources messages,
                       Locale locale)

Construct a new [`MessagesMap`](../../../../../org/apache/struts/faces/util/MessagesMap.html.md "class in org.apache.struts.faces.util") instance that wraps the specified `MessageResources` instance, and returns messages for the specified `Locale`.

**Parameters:**  
`messages` - `MessageResources` instance to wrap

`locale` - `Locale` for which to retrieve messages, or `null` for the system default `Locale`

**Throws:**  
`NullPointerException` - if `messages` is `null`

<span id="method_detail"></span>

**Method Detail**

### clear

    public void clear()

The `clear()` method is not supported.

**Specified by:**  
`clear` in interface `Map`

------------------------------------------------------------------------

### containsKey

    public boolean containsKey(Object key)

Return `true` if there is a message for the specified key.

**Specified by:**  
`containsKey` in interface `Map`

<!-- -->

**Parameters:**  
`key` - Message key to evaluate

------------------------------------------------------------------------

### containsValue

    public boolean containsValue(Object value)

The `containsValue()` method is not supported.

**Specified by:**  
`containsValue` in interface `Map`

<!-- -->

**Parameters:**  
`value` - Value to evaluate

------------------------------------------------------------------------

### entrySet

    public Set entrySet()

The `entrySet()` method is not supported.

**Specified by:**  
`entrySet` in interface `Map`

------------------------------------------------------------------------

### equals

    public boolean equals(Object o)

The `equals` method checks whether equal `MessageResources` and `Locale` are being wrapped.

**Specified by:**  
`equals` in interface `Map`

**Overrides:**  
`equals` in class `Object`

<!-- -->

**Parameters:**  
`o` - The object to be compared

------------------------------------------------------------------------

### get

    public Object get(Object key)

Return the message string for the specified key.

**Specified by:**  
`get` in interface `Map`

<!-- -->

**Parameters:**  
`key` - Key for message to return

------------------------------------------------------------------------

### hashCode

    public int hashCode()

The `hashCode()` method returns values that will be identical if the `equals` method returns `true`.

**Specified by:**  
`hashCode` in interface `Map`

**Overrides:**  
`hashCode` in class `Object`

------------------------------------------------------------------------

### isEmpty

    public boolean isEmpty()

The `isEmpty()` method returns `false`, on the assumption that there is always at least one message available.

**Specified by:**  
`isEmpty` in interface `Map`

------------------------------------------------------------------------

### keySet

    public Set keySet()

The `keySet()` method is not supported.

**Specified by:**  
`keySet` in interface `Map`

------------------------------------------------------------------------

### put

    public Object put(Object key,
                      Object value)

The `put()` method is not supported.

**Specified by:**  
`put` in interface `Map`

<!-- -->

**Parameters:**  
`key` - Key to store

`value` - Value to store

------------------------------------------------------------------------

### putAll

    public void putAll(Map map)

The `putAll()` method is not supported.

**Specified by:**  
`putAll` in interface `Map`

<!-- -->

**Parameters:**  
`map` - Keys and values to store

------------------------------------------------------------------------

### remove

    public Object remove(Object key)

The `remove()` method is not supported.

**Specified by:**  
`remove` in interface `Map`

<!-- -->

**Parameters:**  
`key` - Key to remove

------------------------------------------------------------------------

### size

    public int size()

The `size()` method is not supported.

**Specified by:**  
`size` in interface `Map`

------------------------------------------------------------------------

### values

    public Collection values()

The `values()` method is not supported.

**Specified by:**  
`values` in interface `Map`

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
<td align="left"><a href="class-use/MessagesMap.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/util/StrutsContext.html.md" title="class in org.apache.struts.faces.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/MessagesMap.html"><strong>FRAMES</strong></a>    <a href="MessagesMap.html"><strong>NO FRAMES</strong></a>    
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
