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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactoryException.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryException.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.tiles.DefinitionsFactoryException**
------------------------------------------------------

Packages that use [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles")

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.definition**](#org.apache.struts.tiles.definition)

  

[**org.apache.struts.tiles.xmlDefinition**](#org.apache.struts.tiles.xmlDefinition)

  

 

<span id="org.apache.struts.tiles"></span>

Uses of [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Subclasses of [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

` class`

`FactoryNotFoundException`
           Exception thrown when definitions factory is not found.

` class`

`NoSuchDefinitionException`
           Exception thrown when a definition is not found.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that throw [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles")

`protected  DefinitionsFactory`

`TilesUtilImpl.createDefinitionFactoryInstance(String classname)`
           Create Definition factory of specified classname.

` DefinitionsFactory`

`TilesUtilImpl.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static DefinitionsFactory`

`TilesUtil.createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)`
           Create Definition factory from specified configuration object.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, Map properties)`
           **Deprecated.** Create default Definition factory.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, Map properties, String classname)`
           **Deprecated.** *Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)*

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)`
           **Deprecated.** Create Definition factory.

`static DefinitionsFactory`

`DefinitionsUtil.createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig, boolean checkIfExist)`
           **Deprecated.** Create Definition factory.

`static ComponentDefinition`

`TilesUtil.getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`DefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`ComponentDefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           **Deprecated.** Get a definition by its name.

` void`

`DefinitionsFactory.init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Init definition factory.

` void`

`ComponentDefinitionsFactory.initFactory(ServletContext servletContext, Map properties)`
           **Deprecated.** Init factory.

`protected static DefinitionsFactoryConfig`

`DefinitionsUtil.readFactoryConfig(ServletConfig servletConfig)`
           **Deprecated.** Create FactoryConfig and initialize it from web.xml.

` void`

`DefinitionsFactory.setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set factory configuration.

 

<span id="org.apache.struts.tiles.definition"></span>

Uses of [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html)

 

Methods in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that throw [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles")

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createDefaultFactory(ServletContext servletContext, Map properties)`
           Create default Definition factory.

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createFactory(ServletContext servletContext, Map properties)`
           Create Definition factory.

` ComponentDefinitionsFactory`

`ReloadableDefinitionsFactory.createFactoryFromClassname(ServletContext servletContext, Map properties, String classname)`
           Create Definition factory from provided classname.

`protected  ComponentDefinitionsFactory`

`ComponentDefinitionsFactoryWrapper.createFactoryInstance(String classname)`
           Create Definition factory from provided classname which must implement [`ComponentDefinitionsFactory`](../../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles").

` ComponentDefinition`

`ReloadableDefinitionsFactory.getDefinition(String definitionName, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`ComponentDefinitionsFactoryWrapper.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get requested definition.

` void`

`ComponentDefinitionsFactoryWrapper.init(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Call underlying factory init method.

` void`

`ReloadableDefinitionsFactory.initFactory(ServletContext servletContext, Map properties)`
           Init factory.

` void`

`ReloadableDefinitionsFactory.reload(ServletContext servletContext)`
           Reload underlying factory.

` void`

`ComponentDefinitionsFactoryWrapper.setConfig(DefinitionsFactoryConfig config, ServletContext servletContext)`
           Set underlying factory configuration.

 

| Constructors in [org.apache.struts.tiles.definition](../../../../../org/apache/struts/tiles/definition/package-summary.html.md) that throw [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ReloadableDefinitionsFactory(ServletContext servletContext, Map properties)`                                                                                                                                                                                                    
            Constructor.                                                                                                                                                                                                                                                            |
| ` ReloadableDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)`                                                                                                                                                                                       
            Constructor.                                                                                                                                                                                                                                                            |

 

<span id="org.apache.struts.tiles.xmlDefinition"></span>

Uses of [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html)

 

Methods in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html.md) that throw [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles")

`protected  DefinitionsFactory`

`I18nFactorySet.createDefaultFactory(ServletContext servletContext)`
           Create default factory .

`protected  DefinitionsFactory`

`I18nFactorySet.createFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Create a factory for specified key.

`protected abstract  DefinitionsFactory`

`FactorySet.createFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Create a factory for specified key.

` ComponentDefinition`

`FactorySet.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

` ComponentDefinition`

`DefinitionsFactory.getDefinition(String name, ServletRequest request, ServletContext servletContext)`
           Get a definition by its name.

`protected  DefinitionsFactory`

`FactorySet.getFactory(Object key, ServletRequest request, ServletContext servletContext)`
           Get a factory by its key.

` void`

`I18nFactorySet.initFactory(ServletContext servletContext, Map properties)`
           Initialization method.

`abstract  void`

`FactorySet.initFactory(ServletContext servletContext, Map properties)`
           Init factory set.

`protected  void`

`I18nFactorySet.initFactory(ServletContext servletContext, String proposedFilename)`
           Initialization method.

`protected  XmlDefinitionsSet`

`I18nFactorySet.parseXmlFile(ServletContext servletContext, String filename, XmlDefinitionsSet xmlDefinitions)`
           Parse specified xml file and add definition to specified definitions set.

`protected  XmlDefinitionsSet`

`I18nFactorySet.parseXmlFiles(ServletContext servletContext, String postfix, XmlDefinitionsSet xmlDefinitions)`
           Parse files associated to postix if they exist.

 

| Constructors in [org.apache.struts.tiles.xmlDefinition](../../../../../org/apache/struts/tiles/xmlDefinition/package-summary.html.md) that throw [DefinitionsFactoryException](../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` I18nFactorySet(ServletContext servletContext, Map properties)`                                                                                                                                                                                                                        
            Constructor.                                                                                                                                                                                                                                                                  |

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/tiles/DefinitionsFactoryException.html.md" title="class in org.apache.struts.tiles"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles//class-useDefinitionsFactoryException.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryException.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
