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
<td align="left"><a href="class-use/XmlDefinitionsSet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html"><strong>FRAMES</strong></a>    <a href="XmlDefinitionsSet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.xmlDefinition
 Class XmlDefinitionsSet
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.XmlDefinitionsSet

------------------------------------------------------------------------

    public class XmlDefinitionsSet

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

A set of definitions read from XML definitions file.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Map`

` definitions`
           Defined definitions.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` XmlDefinitionsSet()`  
            Constructor.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` extend(XmlDefinitionsSet child)`
           Add definitions from specified child definitions set.

` XmlDefinition`

` getDefinition(String name)`
           Get requested definition.

` Map`

` getDefinitions()`
           Get definitions map.

` void`

` putDefinition(XmlDefinition definition)`
           Put definition in set.

` void`

` resolveInheritances()`
           Resolve extended instances.

` String`

` toString()`
           Get String representation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="definitions"></span>

### definitions

    protected Map definitions

Defined definitions.

<span id="constructor_detail"></span>

**Constructor Detail**

### XmlDefinitionsSet

    public XmlDefinitionsSet()

Constructor.

<span id="method_detail"></span>

**Method Detail**

### putDefinition

    public void putDefinition(XmlDefinition definition)

Put definition in set.

**Parameters:**  
`definition` - Definition to add.

------------------------------------------------------------------------

### getDefinition

    public XmlDefinition getDefinition(String name)

Get requested definition.

**Parameters:**  
`name` - Definition name.

------------------------------------------------------------------------

### getDefinitions

    public Map getDefinitions()

Get definitions map.

------------------------------------------------------------------------

### resolveInheritances

    public void resolveInheritances()
                             throws NoSuchDefinitionException

Resolve extended instances.

**Throws:**  
`NoSuchDefinitionException`

------------------------------------------------------------------------

### extend

    public void extend(XmlDefinitionsSet child)

Add definitions from specified child definitions set. For each definition in child, look if it already exists in this set. If not, add it, if yes, overload parent's definition with child definition.

**Parameters:**  
`child` - Definition used to overload this object.

------------------------------------------------------------------------

### toString

    public String toString()

Get String representation.

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/XmlDefinitionsSet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html"><strong>FRAMES</strong></a>    <a href="XmlDefinitionsSet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
