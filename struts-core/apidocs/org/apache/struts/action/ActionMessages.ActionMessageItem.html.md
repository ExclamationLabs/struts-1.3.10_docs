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
<td align="left"><a href="class-use/ActionMessages.ActionMessageItem.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMessages.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionRedirect.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMessages.ActionMessageItem.html"><strong>FRAMES</strong></a>    <a href="ActionMessages.ActionMessageItem.html"><strong>NO FRAMES</strong></a>    
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
 Class ActionMessages.ActionMessageItem
---------------------------------------

    java.lang.Object
      org.apache.struts.action.ActionMessages.ActionMessageItem

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Enclosing class:**  
[ActionMessages](../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

    protected class ActionMessages.ActionMessageItem

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

This class is used to store a set of messages associated with a property/key and the position it was initially added to list.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionMessages.ActionMessageItem)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  int`

` iOrder`
           The position in the list of messages.

`protected  List`

` list`
           The list of `ActionMessage`s.

`protected  String`

` property`
           The property associated with `ActionMessage`.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                     |
|-----------------------------------------------------------------------------|
| ` ActionMessages.ActionMessageItem(List list, int iOrder, String property)` 
            Construct an instance of this class.                              |

  <span id="method_summary"></span>

**Method Summary**

` List`

` getList()`
           Retrieve the list of messages associated with this item.

` int`

` getOrder()`
           Retrieve the position in the message list.

` String`

` getProperty()`
           Retrieve the property associated with this item.

` void`

` setList(List list)`
           Set the list of messages associated with this item.

` void`

` setOrder(int iOrder)`
           Set the position in the message list.

` void`

` setProperty(String property)`
           Set the property associated with this item.

` String`

` toString()`
           Construct a string representation of this object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="list"></span>

### list

    protected List list

The list of `ActionMessage`s.

------------------------------------------------------------------------

<span id="iOrder"></span>

### iOrder

    protected int iOrder

The position in the list of messages.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The property associated with `ActionMessage`.

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionMessages.ActionMessageItem

    public ActionMessages.ActionMessageItem(List list,
                                            int iOrder,
                                            String property)

Construct an instance of this class.

**Parameters:**  
`list` - The list of ActionMessages.

`iOrder` - The position in the list of messages.

`property` - The property associated with ActionMessage.

<span id="method_detail"></span>

**Method Detail**

### getList

    public List getList()

Retrieve the list of messages associated with this item.

**Returns:**  
The list of messages associated with this item.

------------------------------------------------------------------------

### setList

    public void setList(List list)

Set the list of messages associated with this item.

**Parameters:**  
`list` - The list of messages associated with this item.

------------------------------------------------------------------------

### getOrder

    public int getOrder()

Retrieve the position in the message list.

**Returns:**  
The position in the message list.

------------------------------------------------------------------------

### setOrder

    public void setOrder(int iOrder)

Set the position in the message list.

**Parameters:**  
`iOrder` - The position in the message list.

------------------------------------------------------------------------

### getProperty

    public String getProperty()

Retrieve the property associated with this item.

**Returns:**  
The property associated with this item.

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

Set the property associated with this item.

**Parameters:**  
`property` - The property associated with this item.

------------------------------------------------------------------------

### toString

    public String toString()

Construct a string representation of this object.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
A string representation of this object.

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
<td align="left"><a href="class-use/ActionMessages.ActionMessageItem.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMessages.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionRedirect.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMessages.ActionMessageItem.html"><strong>FRAMES</strong></a>    <a href="ActionMessages.ActionMessageItem.html"><strong>NO FRAMES</strong></a>    
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
