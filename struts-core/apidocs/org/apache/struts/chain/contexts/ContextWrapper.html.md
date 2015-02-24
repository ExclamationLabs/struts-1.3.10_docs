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
<td align="left"><a href="class-use/ContextWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/MockActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ContextWrapper.html"><strong>FRAMES</strong></a>    <a href="ContextWrapper.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.chain.contexts
 Class ContextWrapper
--------------------------------

    java.lang.Object
      org.apache.struts.chain.contexts.ContextWrapper

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util"), org.apache.commons.chain.Context

<!-- -->

**Direct Known Subclasses:**  
[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public class ContextWrapper

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements org.apache.commons.chain.Context

Provide a base class for any Context Implementation which is primarily intended for use in a subchain.

Classes which extend `ContextWrapper` may implement typesafe property methods which also leave their values in the underlying context.

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_java.util.Map"></span>

| **Nested classes/interfaces inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Map.Entry<K,V>`                                                                                                                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                 |
|-------------------------------------------------------------------------|
| ` ContextWrapper(org.apache.commons.chain.Context context)`             
             Instantiate object as a composite around the given Context.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` clear()`
            

` boolean`

` containsKey(Object o)`
            

` boolean`

` containsValue(Object o)`
            

` Set`

` entrySet()`
            

` Object`

` get(Object key)`
            

`protected  org.apache.commons.chain.Context`

` getBaseContext()`
           Provide the underlying Context for this composite.

` boolean`

` isEmpty()`
            

` Set`

` keySet()`
            

` Object`

` put(Object key, Object value)`
            

` void`

` putAll(Map map)`
            

` Object`

` remove(Object key)`
            

` int`

` size()`
            

` Collection`

` values()`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_java.util.Map"></span>

| **Methods inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `equals, hashCode`                                                                                                                                                  |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ContextWrapper

    public ContextWrapper(org.apache.commons.chain.Context context)

Instantiate object as a composite around the given Context.

**Parameters:**  
`context` - Context instance to wrap

<span id="method_detail"></span>

**Method Detail**

### getBaseContext

    protected org.apache.commons.chain.Context getBaseContext()

Provide the underlying Context for this composite.

**Returns:**  
The undelrying Context

------------------------------------------------------------------------

### entrySet

    public Set entrySet()

**Specified by:**  
`entrySet` in interface `Map`

------------------------------------------------------------------------

### keySet

    public Set keySet()

**Specified by:**  
`keySet` in interface `Map`

------------------------------------------------------------------------

### values

    public Collection values()

**Specified by:**  
`values` in interface `Map`

------------------------------------------------------------------------

### clear

    public void clear()

**Specified by:**  
`clear` in interface `Map`

------------------------------------------------------------------------

### putAll

    public void putAll(Map map)

**Specified by:**  
`putAll` in interface `Map`

------------------------------------------------------------------------

### remove

    public Object remove(Object key)

**Specified by:**  
`remove` in interface `Map`

------------------------------------------------------------------------

### put

    public Object put(Object key,
                      Object value)

**Specified by:**  
`put` in interface `Map`

------------------------------------------------------------------------

### get

    public Object get(Object key)

**Specified by:**  
`get` in interface `Map`

------------------------------------------------------------------------

### containsValue

    public boolean containsValue(Object o)

**Specified by:**  
`containsValue` in interface `Map`

------------------------------------------------------------------------

### containsKey

    public boolean containsKey(Object o)

**Specified by:**  
`containsKey` in interface `Map`

------------------------------------------------------------------------

### isEmpty

    public boolean isEmpty()

**Specified by:**  
`isEmpty` in interface `Map`

------------------------------------------------------------------------

### size

    public int size()

**Specified by:**  
`size` in interface `Map`

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
<td align="left"><a href="class-use/ContextWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/MockActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ContextWrapper.html"><strong>FRAMES</strong></a>    <a href="ContextWrapper.html"><strong>NO FRAMES</strong></a>    
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
