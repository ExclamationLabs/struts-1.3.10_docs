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
<td align="left"><a href="class-use/ActionMessage.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMapping.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMessages.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMessage.html"><strong>FRAMES</strong></a>    <a href="ActionMessage.html"><strong>NO FRAMES</strong></a>    
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
 Class ActionMessage
------------------------

    java.lang.Object
      org.apache.struts.action.ActionMessage

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ActionMessage

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

An encapsulation of an individual message returned by the `validate` method of an `ActionForm`, consisting of a message key (to be used to look up message text in an appropriate message resources database) plus up to four placeholder objects that can be used for parametric replacement in the message text.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionMessage)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`key`
           The message key for this message.

`protected  boolean`

`resource`
           Indicates whether the key is taken to be as a bundle key [true] or literal value [false].

`protected  Object[]`

`values`
           The replacement values for this mesasge.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                  |
|------------------------------------------------------------------------------------------|
| ` ActionMessage(String key)`                                                             
            Construct an action message with no replacement values.                        |
| ` ActionMessage(String key, boolean resource)`                                           
            Construct an action message with the specified replacement values.             |
| ` ActionMessage(String key, Object value0)`                                              
            Construct an action message with the specified replacement values.             |
| ` ActionMessage(String key, Object[] values)`                                            
            Construct an action message with the specified replacement values.             |
| ` ActionMessage(String key, Object value0, Object value1)`                               
            Construct an action message with the specified replacement values.             |
| ` ActionMessage(String key, Object value0, Object value1, Object value2)`                
            Construct an action message with the specified replacement values.             |
| ` ActionMessage(String key, Object value0, Object value1, Object value2, Object value3)` 
            Construct an action message with the specified replacement values.             |

  <span id="method_summary"></span>

**Method Summary**

` String`

`getKey()`
           Get the message key for this message.

` Object[]`

` getValues()`
           Get the replacement values for this message.

` boolean`

` isResource()`
           Indicate whether the key is taken to be as a bundle key [true] or literal value [false].

` String`

` toString()`
           Returns a String in the format: key[value1, value2, etc].

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="key"></span>

### key

    protected String key

The message key for this message.

------------------------------------------------------------------------

<span id="values"></span>

### values

    protected Object[] values

The replacement values for this mesasge.

------------------------------------------------------------------------

<span id="resource"></span>

### resource

    protected boolean resource

Indicates whether the key is taken to be as a bundle key [true] or literal value [false].

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionMessage

    public ActionMessage(String key)

Construct an action message with no replacement values.

**Parameters:**  
`key` - Message key for this message

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         Object value0)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`value0` - First replacement value

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         Object value0,
                         Object value1)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`value0` - First replacement value

`value1` - Second replacement value

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         Object value0,
                         Object value1,
                         Object value2)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`value0` - First replacement value

`value1` - Second replacement value

`value2` - Third replacement value

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         Object value0,
                         Object value1,
                         Object value2,
                         Object value3)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`value0` - First replacement value

`value1` - Second replacement value

`value2` - Third replacement value

`value3` - Fourth replacement value

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         Object[] values)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`values` - Array of replacement values

------------------------------------------------------------------------

### ActionMessage

    public ActionMessage(String key,
                         boolean resource)

Construct an action message with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`resource` - Indicates whether the key is a bundle key or literal value

<span id="method_detail"></span>

**Method Detail**

### getKey

    public String getKey()

Get the message key for this message.

**Returns:**  
The message key for this message.

------------------------------------------------------------------------

### getValues

    public Object[] getValues()

Get the replacement values for this message.

**Returns:**  
The replacement values for this message.

------------------------------------------------------------------------

### isResource

    public boolean isResource()

Indicate whether the key is taken to be as a bundle key [true] or literal value [false].

**Returns:**  
`true` if the key is a bundle key; `false` otherwise.

------------------------------------------------------------------------

### toString

    public String toString()

Returns a String in the format: key[value1, value2, etc].

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
String representation of this message

**See Also:**  
[`Object.toString()`](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true#toString() "class or interface in java.lang")

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
<td align="left"><a href="class-use/ActionMessage.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMapping.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMessages.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMessage.html"><strong>FRAMES</strong></a>    <a href="ActionMessage.html"><strong>NO FRAMES</strong></a>    
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
