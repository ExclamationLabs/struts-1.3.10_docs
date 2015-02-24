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
<td align="left"><a href="class-use/UntypedAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/UrlController.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/UntypedAttribute.html"><strong>FRAMES</strong></a>    <a href="UntypedAttribute.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles
 Class UntypedAttribute
-----------------------

    java.lang.Object
      org.apache.struts.tiles.UntypedAttribute

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [AttributeDefinition](../../../../org/apache/struts/tiles/AttributeDefinition.html "interface in org.apache.struts.tiles")

<!-- -->

**Direct Known Subclasses:**  
[DefinitionAttribute](../../../../org/apache/struts/tiles/DefinitionAttribute.html.md "class in org.apache.struts.tiles"), [DefinitionNameAttribute](../../../../org/apache/struts/tiles/DefinitionNameAttribute.html "class in org.apache.struts.tiles"), [DirectStringAttribute](../../../../org/apache/struts/tiles/DirectStringAttribute.html "class in org.apache.struts.tiles"), [PathAttribute](../../../../org/apache/struts/tiles/PathAttribute.html "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class UntypedAttribute

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [AttributeDefinition](../../../../org/apache/struts/tiles/AttributeDefinition.html.md "interface in org.apache.struts.tiles")

Common implementation of attribute definition.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.UntypedAttribute)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`role`
           Role associated to this attribute.

`protected  Object`

`value`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                        |
|------------------------------------------------|
| ` UntypedAttribute(Object value)`              
            Constructor.                         |
| ` UntypedAttribute(Object value, String role)` 
            Constructor.                         |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getRole()`
           Get role.

` Object`

` getValue()`
           Get value.

` void`

` setRole(String role)`
           Set role.

` void`

` setValue(Object value)`
           Set value.

` String`

` toString()`
           Get String representation of this object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="role"></span>

### role

    protected String role

Role associated to this attribute.

------------------------------------------------------------------------

<span id="value"></span>

### value

    protected Object value

<span id="constructor_detail"></span>

**Constructor Detail**

### UntypedAttribute

    public UntypedAttribute(Object value)

Constructor.

**Parameters:**  
`value` - Object to store.

------------------------------------------------------------------------

### UntypedAttribute

    public UntypedAttribute(Object value,
                            String role)

Constructor.

**Parameters:**  
`value` - Object to store.

`role` - Asociated role.

<span id="method_detail"></span>

**Method Detail**

### getRole

    public String getRole()

Get role.

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Set role.

**Specified by:**  
` setRole` in interface `AttributeDefinition`

<!-- -->

**Parameters:**  
`role` - Associated role.

------------------------------------------------------------------------

### getValue

    public Object getValue()

Get value.

**Specified by:**  
` getValue` in interface `AttributeDefinition`

------------------------------------------------------------------------

### setValue

    public void setValue(Object value)

Set value.

**Parameters:**  
`value` - New value.

------------------------------------------------------------------------

### toString

    public String toString()

Get String representation of this object.

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
<td align="left"><a href="class-use/UntypedAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/UrlController.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/UntypedAttribute.html"><strong>FRAMES</strong></a>    <a href="UntypedAttribute.html"><strong>NO FRAMES</strong></a>    
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
