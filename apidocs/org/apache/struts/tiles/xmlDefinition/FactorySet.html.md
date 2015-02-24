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
<td align="left"><a href="class-use/FactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/FactorySet.html"><strong>FRAMES</strong></a>    <a href="FactorySet.html"><strong>NO FRAMES</strong></a>    
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
 Class FactorySet
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.FactorySet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html "interface in org.apache.struts.tiles")

<!-- -->

**Direct Known Subclasses:**  
[I18nFactorySet](../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition")

------------------------------------------------------------------------

    public abstract class FactorySet

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [ComponentDefinitionsFactory](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles")

Component Definitions factory. This factory contains several factories identified by a key. The getDefinition() method first looks for the factory key, retrieves or creates this factory and then calls its getDefinition().

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.xmlDefinition.FactorySet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Map`

` factories`
           Loaded factories

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` FactorySet()`         
            Constructor.  |

  <span id="method_summary"></span>

**Method Summary**

`protected abstract  DefinitionsFactory`

` createFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Create a factory for specified key.

`protected abstract  DefinitionsFactory`

` getDefaultFactory()`
           Get default factory.

` ComponentDefinition`

` getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

`protected abstract  Object`

` getDefinitionsFactoryKey(String name, ServletRequest request, ServletContext servletContext)`
           Extract key that will be used to get the sub factory.

`protected  DefinitionsFactory`

` getFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Get a factory by its key.

`abstract  void`

` initFactory(ServletContext servletContext, Map properties)`
           Init factory set.

` String`

` toString()`
           Return String representation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="factories"></span>

### factories

    protected Map factories

Loaded factories

<span id="constructor_detail"></span>

**Constructor Detail**

### FactorySet

    public FactorySet()

Constructor.

<span id="method_detail"></span>

**Method Detail**

### getDefinitionsFactoryKey

    protected abstract Object getDefinitionsFactoryKey(String name,
                                                       ServletRequest request,
                                                       ServletContext servletContext)

Extract key that will be used to get the sub factory.

**Parameters:**  
`name` - Name of requested definition.

`request` - Current servlet request.

`servletContext` - Current servlet context.

**Returns:**  
Object.

------------------------------------------------------------------------

### getDefaultFactory

    protected abstract DefinitionsFactory getDefaultFactory()

Get default factory.

**Returns:**  
Default factory.

------------------------------------------------------------------------

### getFactory

    protected DefinitionsFactory getFactory(Object key,
                                            ServletRequest request,
                                            ServletContext servletContext)
                                     throws DefinitionsFactoryException

Get a factory by its key. If key is `null`, return defaultFactory. Search in loaded factories. If not found, create factory and store return value in loaded factories.

**Parameters:**  
`key` - Key of requested definition.

`request` - Current servlet request.

`servletContext` - Current servlet context.

**Throws:**  
`DefinitionsFactoryException` - If an error occur while creating factory.

------------------------------------------------------------------------

### getDefinition

    public ComponentDefinition getDefinition(String name,
                                             ServletRequest request,
                                             ServletContext servletContext)
                                      throws NoSuchDefinitionException,
                                             DefinitionsFactoryException

Get a definition by its name.

**Specified by:**  
` getDefinition` in interface `ComponentDefinitionsFactory`

<!-- -->

**Parameters:**  
`name` - Name of requested definition.

`request` - Current servlet request.

`servletContext` - Current servlet context.

**Throws:**  
`NoSuchDefinitionException` - No definition found for specified name

`DefinitionsFactoryException` - General exception

------------------------------------------------------------------------

### createFactory

    protected abstract DefinitionsFactory createFactory(Object key,
                                                        ServletRequest request,
                                                        ServletContext servletContext)
                                                 throws DefinitionsFactoryException

Create a factory for specified key. This method is called by getFactory() when the requested factory doesn't already exist. Must return a factory, or a default one. Real implementation needs to provide this method.

**Parameters:**  
`key` - Key of requested definition.

`request` - Current servlet request.

`servletContext` - Current servlet context

**Throws:**  
`DefinitionsFactoryException` - If an error occur while creating factory.

------------------------------------------------------------------------

### initFactory

    public abstract void initFactory(ServletContext servletContext,
                                     Map properties)
                              throws DefinitionsFactoryException

Init factory set.

**Specified by:**  
` initFactory` in interface `ComponentDefinitionsFactory`

<!-- -->

**Parameters:**  
`servletContext` - Current servlet context

`properties` - properties used to initialized factory set;

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

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
<td align="left"><a href="class-use/FactorySet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html" title="class in org.apache.struts.tiles.xmlDefinition"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/FactorySet.html"><strong>FRAMES</strong></a>    <a href="FactorySet.html"><strong>NO FRAMES</strong></a>    
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
