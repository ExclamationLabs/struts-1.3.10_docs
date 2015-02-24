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
<td align="left"><a href="class-use/XmlListAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlParser.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html"><strong>FRAMES</strong></a>    <a href="XmlListAttribute.html"><strong>NO FRAMES</strong></a>    
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
 Class XmlListAttribute
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.XmlAttribute
          org.apache.struts.tiles.xmlDefinition.XmlListAttribute

------------------------------------------------------------------------

    public class XmlListAttribute

extends [XmlAttribute](../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html.md "class in org.apache.struts.tiles.xmlDefinition")

An attribute as a `List`. This attribute associates a name with a list. The list can be found by the property name. Elements in list are retrieved using List methods. This class is used to read configuration files.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                      |
|----------------------------------------------|
| ` XmlListAttribute()`                        
            Constructor.                       |
| ` XmlListAttribute(String name, List value)` 
            Constructor.                       |

  <span id="method_summary"></span>

**Method Summary**

` void`

` add(Object value)`
           Add an element in list.

` void`

` add(XmlAttribute element)`
           Add an element in list.

` void`

` addObject(Object value)`
           Add an element in list.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.xmlDefinition.XmlAttribute"></span>

| **Methods inherited from class org.apache.struts.tiles.xmlDefinition.[XmlAttribute](../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html.md "class in org.apache.struts.tiles.xmlDefinition")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` computeRealValue,  getAttribute,  getName,  getRole,  getValue,  setAttribute,  setBody,  setContent,  setDirect,  setName,  setRole,  setType,  setValue`                                                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### XmlListAttribute

    public XmlListAttribute()

Constructor.

------------------------------------------------------------------------

### XmlListAttribute

    public XmlListAttribute(String name,
                            List value)

Constructor.

**Parameters:**  
`name` - Name.

`value` - List.

<span id="method_detail"></span>

**Method Detail**

### add

    public void add(XmlAttribute element)

Add an element in list. We use a property to avoid rewriting a new class.

**Parameters:**  
`element` - XmlAttribute to add.

------------------------------------------------------------------------

### add

    public void add(Object value)

Add an element in list.

**Parameters:**  
`value` - Object to add.

------------------------------------------------------------------------

### addObject

    public void addObject(Object value)

Add an element in list.

**Parameters:**  
`value` - Object to add.

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
<td align="left"><a href="class-use/XmlListAttribute.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlParser.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html"><strong>FRAMES</strong></a>    <a href="XmlListAttribute.html"><strong>NO FRAMES</strong></a>    
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
