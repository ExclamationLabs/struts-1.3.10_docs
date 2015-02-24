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
<td align="left"><a href="class-use/ComponentDefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentDefinition.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/Controller.html" title="interface in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Interface ComponentDefinitionsFactory
--------------------------------------

**All Superinterfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**All Known Implementing Classes:**  
[FactorySet](../../../../org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition"), [I18nFactorySet](../../../../org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html "class in org.apache.struts.tiles.xmlDefinition"), [ReloadableDefinitionsFactory](../../../../org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html "class in org.apache.struts.tiles.definition")

------------------------------------------------------------------------

**Deprecated.** *Use DefinitionsFactory instead.*

    public interface ComponentDefinitionsFactory

extends [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Component repository interface. This interface allows to retrieve an definition by its name, independently of the factory implementation. Implementation must be Serializable, in order to be compliant with web Container having this constraint (Weblogic 6.x).

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` ComponentDefinition`

` getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           **Deprecated.** Get a definition by its name.

` void`

` initFactory(ServletContext servletContext, Map properties)`
           **Deprecated.** Init factory.

 

<span id="method_detail"></span>

**Method Detail**

### getDefinition

    ComponentDefinition getDefinition(String name,
                                      ServletRequest request,
                                      ServletContext servletContext)
                                      throws NoSuchDefinitionException,
                                             DefinitionsFactoryException

**Deprecated.** 

Get a definition by its name.

**Parameters:**  
`name` - Name of requested definition.

`request` - Current servelet request

`servletContext` - current servlet context

**Throws:**  
`DefinitionsFactoryException` - An error occur while getting definition.

`NoSuchDefinitionException` - No definition found for specified name Implementation can throw more accurate exception as a subclass of this exception

------------------------------------------------------------------------

### initFactory

    void initFactory(ServletContext servletContext,
                     Map properties)
                     throws DefinitionsFactoryException

**Deprecated.** 

Init factory. This method is called exactly once immediately after factory creation in case of internal creation (by DefinitionUtil).

**Parameters:**  
`servletContext` - Servlet Context passed to newly created factory.

`properties` - Map of name/property passed to newly created factory. Map can contains more properties than requested.

**Throws:**  
`DefinitionsFactoryException` - An error occur during initialization.

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
<td align="left"><a href="class-use/ComponentDefinitionsFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentDefinition.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/Controller.html" title="interface in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentDefinitionsFactory.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinitionsFactory.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
