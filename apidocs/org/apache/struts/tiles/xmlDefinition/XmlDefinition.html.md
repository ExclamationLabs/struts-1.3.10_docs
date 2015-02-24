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
<td align="left"><a href="class-use/XmlDefinition.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlDefinition.html"><strong>FRAMES</strong></a>    <a href="XmlDefinition.html"><strong>NO FRAMES</strong></a>    
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
 Class XmlDefinition
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.ComponentDefinition
          org.apache.struts.tiles.xmlDefinition.XmlDefinition

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class XmlDefinition

extends [ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles")

A definition read from an XML definitions file.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.xmlDefinition.XmlDefinition)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Log`

` log`
           Commons Logging instance.

 <span id="fields_inherited_from_class_org.apache.struts.tiles.ComponentDefinition"></span>

| **Fields inherited from class org.apache.struts.tiles.[ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ACTION,  attributes,  controller,  CONTROLLER,  controllerType,  name,  path,  role,  URL`                                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` XmlDefinition()`      
            Constructor.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addAttribute(XmlAttribute attribute)`
           Add an attribute to this component.

` String`

` getExtends()`
           Get extends.

` boolean`

` isExtending()`
           Get extends flag.

` void`

` overload(XmlDefinition child)`
           Overload this definition with passed child.

` void`

` resolveInheritance(XmlDefinitionsSet definitionsSet)`
           Resolve inheritance.

` void`

` setExtends(String name)`
           Set extends.

` void`

` setIsVisited(boolean isVisited)`
           Set isVisited.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.ComponentDefinition"></span>

| **Methods inherited from class org.apache.struts.tiles.[ComponentDefinition](../../../../../org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles")**                                                                                                                                                                                                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createController,  createControllerFromClassname,  getAttribute,  getAttributes,  getController,  getControllerInstance,  getControllerType,  getName,  getOrCreateController,  getPage,  getPath,  getRole,  getTemplate,  put,  put,  put,  put,  putAttribute,  setController,  setControllerClass,  setControllerInstance,  setControllerType,  setControllerUrl,  setName,  setPage,  setPath,  setRole,  setTemplate,  toString` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

<span id="constructor_detail"></span>

**Constructor Detail**

### XmlDefinition

    public XmlDefinition()

Constructor.

<span id="method_detail"></span>

**Method Detail**

### addAttribute

    public void addAttribute(XmlAttribute attribute)

Add an attribute to this component.

**Parameters:**  
`attribute` - Attribute to add.

------------------------------------------------------------------------

### setExtends

    public void setExtends(String name)

Set extends.

**Parameters:**  
`name` - Name of the extended definition.

------------------------------------------------------------------------

### getExtends

    public String getExtends()

Get extends.

**Returns:**  
Name of the extended definition.

------------------------------------------------------------------------

### isExtending

    public boolean isExtending()

Get extends flag.

------------------------------------------------------------------------

### setIsVisited

    public void setIsVisited(boolean isVisited)

Set isVisited.

------------------------------------------------------------------------

### resolveInheritance

    public void resolveInheritance(XmlDefinitionsSet definitionsSet)
                            throws NoSuchDefinitionException

Resolve inheritance. First, resolve parent's inheritance, then set path to the parent's path. Also copy attributes setted in parent, and not set in child If instance doesn't extend anything, do nothing.

**Throws:**  
`NoSuchDefinitionException` - If an inheritance can not be solved.

------------------------------------------------------------------------

### overload

    public void overload(XmlDefinition child)

Overload this definition with passed child. All attributes from child are copied to this definition. Previous attributes with same name are disguarded. Special attribute 'path','role' and 'extends' are overloaded if defined in child.

**Parameters:**  
`child` - Child used to overload this definition.

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
<td align="left"><a href="class-use/XmlDefinition.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlAttribute.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlDefinition.html"><strong>FRAMES</strong></a>    <a href="XmlDefinition.html"><strong>NO FRAMES</strong></a>    
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
