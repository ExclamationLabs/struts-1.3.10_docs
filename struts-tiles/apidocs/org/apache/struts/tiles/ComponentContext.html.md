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
<td align="left"><a href="class-use/ComponentContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/AttributeDefinition.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ComponentDefinition.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentContext.html"><strong>FRAMES</strong></a>    <a href="ComponentContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Class ComponentContext
-----------------------

    java.lang.Object
      org.apache.struts.tiles.ComponentContext

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ComponentContext

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Component context.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.ComponentContext)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**             |
|-------------------------------------|
| ` ComponentContext()`               
            Constructor.              |
| ` ComponentContext(Map attributes)` 
            Constructor.              |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addAll(Map newAttributes)`
           Add all attributes to this context.

` void`

` addMissing(Map defaultAttributes)`
           Add all missing attributes to this context.

` Object`

` findAttribute(String beanName, PageContext pageContext)`
           Find object in one of the contexts.

` Object`

` getAttribute(String name)`
           Get an attribute from context.

` Object`

` getAttribute(String beanName, int scope, PageContext pageContext)`
           Get object from requested context.

` Iterator`

` getAttributeNames()`
           Get names of all attributes.

`static ComponentContext`

` getContext(ServletRequest request)`
           Get component context from request.

` void`

` putAttribute(String name, Object value)`
           Put a new attribute to context.

`static void`

` setContext(ComponentContext context, ServletRequest request)`
           Store component context into request.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ComponentContext

    public ComponentContext()

Constructor.

------------------------------------------------------------------------

### ComponentContext

    public ComponentContext(Map attributes)

Constructor. Create a context and set specified attributes.

**Parameters:**  
`attributes` - Attributes to initialize context.

<span id="method_detail"></span>

**Method Detail**

### addAll

    public void addAll(Map newAttributes)

Add all attributes to this context. Copies all of the mappings from the specified attribute map to this context. New attribute mappings will replace any mappings that this context had for any of the keys currently in the specified attribute map.

**Parameters:**  
`newAttributes` - Attributes to add.

------------------------------------------------------------------------

### addMissing

    public void addMissing(Map defaultAttributes)

Add all missing attributes to this context. Copies all of the mappings from the specified attributes map to this context. New attribute mappings will be added only if they don't already exist in this context.

**Parameters:**  
`defaultAttributes` - Attributes to add.

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name)

Get an attribute from context.

**Parameters:**  
`name` - Name of the attribute.

**Returns:**  
\<{Object}\>

------------------------------------------------------------------------

### getAttributeNames

    public Iterator getAttributeNames()

Get names of all attributes.

**Returns:**  
\<{Object}\>

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(String name,
                             Object value)

Put a new attribute to context.

**Parameters:**  
`name` - Name of the attribute.

`value` - Value of the attribute.

------------------------------------------------------------------------

### findAttribute

    public Object findAttribute(String beanName,
                                PageContext pageContext)

Find object in one of the contexts. Order : component then pageContext.findAttribute()

**Parameters:**  
`beanName` - Name of the bean to find.

`pageContext` - Page context.

**Returns:**  
Requested bean or `null` if not found.

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String beanName,
                               int scope,
                               PageContext pageContext)

Get object from requested context. Context can be 'component'.

**Parameters:**  
`beanName` - Name of the bean to find.

`scope` - Search scope (see [`PageContext`](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/PageContext.html.md?is-external=true "class or interface in javax.servlet.jsp")).

`pageContext` - Page context.

**Returns:**  
requested bean or `null` if not found.

------------------------------------------------------------------------

### getContext

    public static ComponentContext getContext(ServletRequest request)

Get component context from request.

**Parameters:**  
`request` - ServletRequest.

**Returns:**  
ComponentContext or null if context is not found or an jspException is present in the request.

------------------------------------------------------------------------

### setContext

    public static void setContext(ComponentContext context,
                                  ServletRequest request)

Store component context into request.

**Parameters:**  
`context` - ComponentContext to store.

`request` - Request to store ComponentContext.

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
<td align="left"><a href="class-use/ComponentContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/AttributeDefinition.html.md" title="interface in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ComponentDefinition.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentContext.html"><strong>FRAMES</strong></a>    <a href="ComponentContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
