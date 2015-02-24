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
<td align="left"><a href="class-use/XmlAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinition.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlAttribute.html"><strong>FRAMES</strong></a>    <a href="XmlAttribute.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.xmlDefinition
 Class XmlAttribute
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.XmlAttribute

**Direct Known Subclasses:**  
[XmlListAttribute](../../../../../org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html.md "class in org.apache.struts.tiles.xmlDefinition")

------------------------------------------------------------------------

    public class XmlAttribute

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

A property key-value pair. This class is used to read configuration files.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                    |
|--------------------------------------------|
| ` XmlAttribute()`                          
            Constructor.                     |
| ` XmlAttribute(String name, Object value)` 
            Constructor.                     |

  <span id="method_summary"></span>

**Method Summary**

`protected  Object`

` computeRealValue()`
           Compute real value from attributes setting.

` String`

` getAttribute()`
           Another access method for the name property.

` String`

` getName()`
           Access method for the name property.

` String`

` getRole()`
           Access method for the name property.

` Object`

` getValue()`
           Access method for the value property.

` void`

` setAttribute(String aName)`
           Sets the value of the name property.

` void`

` setBody(String body)`
           Sets the value of the value property.

` void`

` setContent(Object aValue)`
           Sets the value of the value property.

` void`

` setDirect(String value)`
           Sets the value of the value property.

` void`

` setName(String aName)`
           Sets the value of the name property.

` void`

` setRole(String role)`
           Sets the value of the name property.

` void`

` setType(String value)`
           Sets the value of the value property.

` void`

` setValue(Object aValue)`
           Sets the value of the value property.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### XmlAttribute

    public XmlAttribute()

Constructor.

------------------------------------------------------------------------

### XmlAttribute

    public XmlAttribute(String name,
                        Object value)

Constructor.

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

Access method for the name property.

**Returns:**  
The current value of the name property.

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Sets the value of the name property.

**Parameters:**  
`role` - the new value of the name property

------------------------------------------------------------------------

### getRole

    public String getRole()

Access method for the name property.

**Returns:**  
The current value of the name property.

------------------------------------------------------------------------

### setName

    public void setName(String aName)

Sets the value of the name property.

**Parameters:**  
`aName` - the new value of the name property.

------------------------------------------------------------------------

### getAttribute

    public String getAttribute()

Another access method for the name property.

**Returns:**  
the current value of the name property

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String aName)

Sets the value of the name property.

**Parameters:**  
`aName` - the new value of the name property

------------------------------------------------------------------------

### getValue

    public Object getValue()

Access method for the value property. Return the value or a QualifiedAttribute containing the value if 'direct' is set.

**Returns:**  
The current value of the value property.

------------------------------------------------------------------------

### setValue

    public void setValue(Object aValue)

Sets the value of the value property.

**Parameters:**  
`aValue` - the new value of the value property

------------------------------------------------------------------------

### setContent

    public void setContent(Object aValue)

Sets the value of the value property.

**Parameters:**  
`aValue` - the new value of the value property

------------------------------------------------------------------------

### setBody

    public void setBody(String body)

Sets the value of the value property.

**Parameters:**  
`body` - the new value of the value property

------------------------------------------------------------------------

### setDirect

    public void setDirect(String value)

Sets the value of the value property.

**Parameters:**  
`value` - the new value of the value property

------------------------------------------------------------------------

### setType

    public void setType(String value)

Sets the value of the value property.

**Parameters:**  
`value` - the new value of the value property

------------------------------------------------------------------------

### computeRealValue

    protected Object computeRealValue()

Compute real value from attributes setting.

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
<td align="left"><a href="class-use/XmlAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinition.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlAttribute.html"><strong>FRAMES</strong></a>    <a href="XmlAttribute.html"><strong>NO FRAMES</strong></a>    
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
