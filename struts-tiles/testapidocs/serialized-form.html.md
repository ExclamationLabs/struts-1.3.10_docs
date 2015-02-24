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
<td align="left"><a href="org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="org/apache/struts/tiles/package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles**

<span id="org.apache.struts.tiles.ComponentContext"></span>

**Class org.apache.struts.tiles.ComponentContext extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributes

    Map<K,V> attributes

<span id="org.apache.struts.tiles.ComponentDefinition"></span>

**Class org.apache.struts.tiles.ComponentDefinition extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

------------------------------------------------------------------------

### path

    String path

------------------------------------------------------------------------

### attributes

    Map<K,V> attributes

------------------------------------------------------------------------

### role

    String role

------------------------------------------------------------------------

### controller

    String controller

------------------------------------------------------------------------

### controllerType

    String controllerType

------------------------------------------------------------------------

### controllerInstance

    org.apache.struts.tiles.Controller controllerInstance

<span id="org.apache.struts.tiles.CustomI18nFactorySet"></span>

**Class [org.apache.struts.tiles.CustomI18nFactorySet](org/apache/struts/tiles/CustomI18nFactorySet.html.md "class in org.apache.struts.tiles") extends org.apache.struts.tiles.xmlDefinition.I18nFactorySet implements Serializable**

<span id="org.apache.struts.tiles.DefinitionAttribute"></span>

**Class org.apache.struts.tiles.DefinitionAttribute extends org.apache.struts.tiles.UntypedAttribute implements Serializable**

<span id="org.apache.struts.tiles.DefinitionNameAttribute"></span>

**Class org.apache.struts.tiles.DefinitionNameAttribute extends org.apache.struts.tiles.UntypedAttribute implements Serializable**

<span id="org.apache.struts.tiles.DefinitionsFactoryConfig"></span>

**Class org.apache.struts.tiles.DefinitionsFactoryConfig extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factoryClassname

    String factoryClassname

------------------------------------------------------------------------

### parserValidate

    boolean parserValidate

------------------------------------------------------------------------

### definitionConfigFiles

    String definitionConfigFiles

------------------------------------------------------------------------

### moduleAware

    boolean moduleAware

------------------------------------------------------------------------

### factoryName

    String factoryName

------------------------------------------------------------------------

### extraAttributes

    Map<K,V> extraAttributes

<span id="org.apache.struts.tiles.DefinitionsFactoryException"></span>

**Class org.apache.struts.tiles.DefinitionsFactoryException extends org.apache.struts.tiles.TilesException implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

<span id="org.apache.struts.tiles.DirectStringAttribute"></span>

**Class org.apache.struts.tiles.DirectStringAttribute extends org.apache.struts.tiles.UntypedAttribute implements Serializable**

<span id="org.apache.struts.tiles.FactoryNotFoundException"></span>

**Class org.apache.struts.tiles.FactoryNotFoundException extends org.apache.struts.tiles.DefinitionsFactoryException implements Serializable**

<span id="org.apache.struts.tiles.NoSuchDefinitionException"></span>

**Class org.apache.struts.tiles.NoSuchDefinitionException extends org.apache.struts.tiles.DefinitionsFactoryException implements Serializable**

<span id="org.apache.struts.tiles.PathAttribute"></span>

**Class org.apache.struts.tiles.PathAttribute extends org.apache.struts.tiles.UntypedAttribute implements Serializable**

<span id="org.apache.struts.tiles.RedeployableActionServlet"></span>

**Class org.apache.struts.tiles.RedeployableActionServlet extends [ActionServlet](http://struts.apache.org/apidocs/org/apache/struts/action/ActionServlet.html.md?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### tileProcessor

    org.apache.struts.tiles.TilesRequestProcessor tileProcessor

<span id="org.apache.struts.tiles.TilesException"></span>

**Class org.apache.struts.tiles.TilesException extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

<span id="org.apache.struts.tiles.TilesUtilImpl"></span>

**Class org.apache.struts.tiles.TilesUtilImpl extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsImpl"></span>

**Class org.apache.struts.tiles.TilesUtilStrutsImpl extends org.apache.struts.tiles.TilesUtilImpl implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsModulesImpl"></span>

**Class org.apache.struts.tiles.TilesUtilStrutsModulesImpl extends org.apache.struts.tiles.TilesUtilStrutsImpl implements Serializable**

<span id="org.apache.struts.tiles.UntypedAttribute"></span>

**Class org.apache.struts.tiles.UntypedAttribute extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### role

    String role

------------------------------------------------------------------------

### value

    Object value

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
<td align="left"><a href="org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="org/apache/struts/tiles/package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
