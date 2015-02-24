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
<td align="left"><a href="class-use/DefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
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
 Class DefinitionsFactory
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.DefinitionsFactory

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class DefinitionsFactory

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

A factory for definitions. This factory allows to retrieve definitions by their keys.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.xmlDefinition.DefinitionsFactory)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Map`

` definitions`
           Underlying map containing all definitions.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                 |
|---------------------------------------------------------|
| ` DefinitionsFactory(XmlDefinitionsSet xmlDefinitions)` 
            Constructor.                                  |

  <span id="method_summary"></span>

**Method Summary**

` ComponentDefinition`

` getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` void`

` putDefinition(ComponentDefinition definition)`
           Put definition in set.

` String`

` toString()`
           Return String representation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="definitions"></span>

### definitions

    protected Map definitions

Underlying map containing all definitions.

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionsFactory

    public DefinitionsFactory(XmlDefinitionsSet xmlDefinitions)
                       throws NoSuchDefinitionException

Constructor. Create a factory initialized with definitions from [`XmlDefinitionsSet`](../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html.md "class in org.apache.struts.tiles.xmlDefinition").

**Parameters:**  
`xmlDefinitions` - Resolved definition from XmlDefinitionSet.

**Throws:**  
`NoSuchDefinitionException` - If an error occurs while resolving inheritance

<span id="method_detail"></span>

**Method Detail**

### getDefinition

    public ComponentDefinition getDefinition(String name,
                                             ServletRequest request,
                                             ServletContext servletContext)
                                      throws NoSuchDefinitionException,
                                             DefinitionsFactoryException

Get a definition by its name.

**Parameters:**  
`name` - Name of the definition.

`request` - Servlet request.

`servletContext` - Servlet context.

**Throws:**  
`DefinitionsFactoryException` - An error occur while getting definition.

`NoSuchDefinitionException` - No definition found for specified name Implementation can throw more accurate exception as a subclass of this exception.

------------------------------------------------------------------------

### putDefinition

    public void putDefinition(ComponentDefinition definition)

Put definition in set.

**Parameters:**  
`definition` - Definition to put.

------------------------------------------------------------------------

### toString

    public String toString()

Return String representation.

**Overrides:**  
`toString` in class `Object`

<!-- -->

**Returns:**  
String representation.

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
<td align="left"><a href="class-use/DefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
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
