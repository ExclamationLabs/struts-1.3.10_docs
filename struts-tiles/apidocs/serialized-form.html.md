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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
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

**Class [org.apache.struts.tiles.ComponentContext](org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributes

    Map<K,V> attributes

Component attributes.

<span id="org.apache.struts.tiles.ComponentDefinition"></span>

**Class [org.apache.struts.tiles.ComponentDefinition](org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

Definition name

------------------------------------------------------------------------

### path

    String path

Component / template path (URL).

------------------------------------------------------------------------

### attributes

    Map<K,V> attributes

Attributes defined for the component.

------------------------------------------------------------------------

### role

    String role

Role associated to definition.

------------------------------------------------------------------------

### controller

    String controller

Associated Controller URL or classname, if defined

------------------------------------------------------------------------

### controllerType

    String controllerType

Associated Controller typename, if controllerName defined. Can be CONTROLLER, ACTION or URL, or null.

------------------------------------------------------------------------

### controllerInstance

    Controller controllerInstance

Controller associated to Definition. Lazy creation : only on first request

<span id="org.apache.struts.tiles.DefinitionAttribute"></span>

**Class [org.apache.struts.tiles.DefinitionAttribute](org/apache/struts/tiles/DefinitionAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.DefinitionNameAttribute"></span>

**Class [org.apache.struts.tiles.DefinitionNameAttribute](org/apache/struts/tiles/DefinitionNameAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.DefinitionsFactoryConfig"></span>

**Class [org.apache.struts.tiles.DefinitionsFactoryConfig](org/apache/struts/tiles/DefinitionsFactoryConfig.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factoryClassname

    String factoryClassname

Fully qualified classname of the factory to create. If no classname is set, a default factory is created (of class "org.apache.struts.tiles.xmlDefinition.I18nFactorySet").

------------------------------------------------------------------------

### parserValidate

    boolean parserValidate

Specifies whether the parser will validate configuration files. Default value is true.

------------------------------------------------------------------------

### definitionConfigFiles

    String definitionConfigFiles

Definition configuration file specified by user.

------------------------------------------------------------------------

### moduleAware

    boolean moduleAware

Specifies whether the factory is "module-aware".

------------------------------------------------------------------------

### factoryName

    String factoryName

The name associated to this factory.
 With Struts 1.1, this name is the module name to which this factory belong. It is set by the system.
 In prior versions, this property is not used.

------------------------------------------------------------------------

### extraAttributes

    Map<K,V> extraAttributes

Map of extra attribute available.

<span id="org.apache.struts.tiles.DefinitionsFactoryException"></span>

**Class [org.apache.struts.tiles.DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") extends [TilesException](org/apache/struts/tiles/TilesException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

Any "wrapped" exception will be exposed when this is serialized.

 

<span id="org.apache.struts.tiles.DirectStringAttribute"></span>

**Class [org.apache.struts.tiles.DirectStringAttribute](org/apache/struts/tiles/DirectStringAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.FactoryNotFoundException"></span>

**Class [org.apache.struts.tiles.FactoryNotFoundException](org/apache/struts/tiles/FactoryNotFoundException.html.md "class in org.apache.struts.tiles") extends [DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.NoSuchDefinitionException"></span>

**Class [org.apache.struts.tiles.NoSuchDefinitionException](org/apache/struts/tiles/NoSuchDefinitionException.html.md "class in org.apache.struts.tiles") extends [DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.PathAttribute"></span>

**Class [org.apache.struts.tiles.PathAttribute](org/apache/struts/tiles/PathAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.RedeployableActionServlet"></span>

**Class [org.apache.struts.tiles.RedeployableActionServlet](org/apache/struts/tiles/RedeployableActionServlet.html.md "class in org.apache.struts.tiles") extends [ActionServlet](http://struts.apache.org/apidocs/org/apache/struts/action/ActionServlet.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### tileProcessor

    TilesRequestProcessor tileProcessor

<span id="org.apache.struts.tiles.TilesException"></span>

**Class [org.apache.struts.tiles.TilesException](org/apache/struts/tiles/TilesException.html.md "class in org.apache.struts.tiles") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

Any "wrapped" exception will be exposed when this is serialized.

 

<span id="org.apache.struts.tiles.TilesUtilImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilImpl](org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilStrutsImpl](org/apache/struts/tiles/TilesUtilStrutsImpl.html.md "class in org.apache.struts.tiles") extends [TilesUtilImpl](org/apache/struts/tiles/TilesUtilImpl.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsModulesImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilStrutsModulesImpl](org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md "class in org.apache.struts.tiles") extends [TilesUtilStrutsImpl](org/apache/struts/tiles/TilesUtilStrutsImpl.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.UntypedAttribute"></span>

**Class [org.apache.struts.tiles.UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### role

    String role

Role associated to this attribute.

------------------------------------------------------------------------

### value

    Object value

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.beans**

<span id="org.apache.struts.tiles.beans.SimpleMenuItem"></span>

**Class [org.apache.struts.tiles.beans.SimpleMenuItem](org/apache/struts/tiles/beans/SimpleMenuItem.html.md "class in org.apache.struts.tiles.beans") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### value

    String value

------------------------------------------------------------------------

### link

    String link

------------------------------------------------------------------------

### icon

    String icon

------------------------------------------------------------------------

### tooltip

    String tooltip

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.definition**

<span id="org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper"></span>

**Class [org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper](org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md "class in org.apache.struts.tiles.definition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    ComponentDefinitionsFactory factory

The underlying factory.

------------------------------------------------------------------------

### config

    DefinitionsFactoryConfig config

Factory configuration,

<span id="org.apache.struts.tiles.definition.ReloadableDefinitionsFactory"></span>

**Class [org.apache.struts.tiles.definition.ReloadableDefinitionsFactory](org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html.md "class in org.apache.struts.tiles.definition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    ComponentDefinitionsFactory factory

The real factory instance.

------------------------------------------------------------------------

### properties

    Map<K,V> properties

Initialization parameters.

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.taglib**

<span id="org.apache.struts.tiles.taglib.AddTag"></span>

**Class [org.apache.struts.tiles.taglib.AddTag](org/apache/struts/tiles/taglib/AddTag.html.md "class in org.apache.struts.tiles.taglib") extends [PutTag](org/apache/struts/tiles/taglib/PutTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="org.apache.struts.tiles.taglib.AttributeToScopeTag"></span>

**Class [org.apache.struts.tiles.taglib.AttributeToScopeTag](org/apache/struts/tiles/taglib/AttributeToScopeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### scopeName

    String scopeName

**Deprecated.** 

The scope name.

------------------------------------------------------------------------

### scope

    int scope

**Deprecated.** 

The scope value.

------------------------------------------------------------------------

### property

    String property

**Deprecated.** 

The property name to be exposed.

<span id="org.apache.struts.tiles.taglib.DefinitionTag"></span>

**Class [org.apache.struts.tiles.taglib.DefinitionTag](org/apache/struts/tiles/taglib/DefinitionTag.html.md "class in org.apache.struts.tiles.taglib") extends [DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

Definition identifier.

------------------------------------------------------------------------

### scope

    String scope

Scope into which definition will be saved.

------------------------------------------------------------------------

### extendsDefinition

    String extendsDefinition

Extends attribute value.

------------------------------------------------------------------------

### definition

    ComponentDefinition definition

Template definition

<span id="org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

**Class [org.apache.struts.tiles.taglib.DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### controllerType

    String controllerType

Associated Controller type

------------------------------------------------------------------------

### controllerName

    String controllerName

Associated Controller name (classname or url)

------------------------------------------------------------------------

### role

    String role

Role associated to definition.

------------------------------------------------------------------------

### page

    String page

Uri of page assoicated to this definition.

<span id="org.apache.struts.tiles.taglib.GetAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.GetAttributeTag](org/apache/struts/tiles/taglib/GetAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attribute

    String attribute

------------------------------------------------------------------------

### role

    String role

Role attribute

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Do we ignore error if attribute is not found. Default value is `false`, which will throw an exception.

<span id="org.apache.struts.tiles.taglib.GetTag"></span>

**Class [org.apache.struts.tiles.taglib.GetTag](org/apache/struts/tiles/taglib/GetTag.html.md "class in org.apache.struts.tiles.taglib") extends [InsertTag](org/apache/struts/tiles/taglib/InsertTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="org.apache.struts.tiles.taglib.ImportAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.ImportAttributeTag](org/apache/struts/tiles/taglib/ImportAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

Class name of object.

------------------------------------------------------------------------

### scopeName

    String scopeName

The scope name.

------------------------------------------------------------------------

### scope

    int scope

The scope value.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute `ignore`. Default value is `false`, which throws an exception. Only "attribute not found" - errors are ignored.

<span id="org.apache.struts.tiles.taglib.InitDefinitionsTag"></span>

**Class [org.apache.struts.tiles.taglib.InitDefinitionsTag](org/apache/struts/tiles/taglib/InitDefinitionsTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filename

    String filename

------------------------------------------------------------------------

### classname

    String classname

<span id="org.apache.struts.tiles.taglib.InsertTag"></span>

**Class [org.apache.struts.tiles.taglib.InsertTag](org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib") extends [DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### flush

    boolean flush

Flush attribute value.

------------------------------------------------------------------------

### name

    String name

Name to insert.

------------------------------------------------------------------------

### attribute

    String attribute

Name of attribute from which to read page name to include.

------------------------------------------------------------------------

### beanName

    String beanName

Name of bean used as entity to include.

------------------------------------------------------------------------

### beanProperty

    String beanProperty

Name of bean property, if any.

------------------------------------------------------------------------

### beanScope

    String beanScope

Scope of bean, if any.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute 'ignore'. Default value is false, which throw an exception. Only 'attribute not found' errors are ignored.

------------------------------------------------------------------------

### definitionName

    String definitionName

Name of component instance to include.

------------------------------------------------------------------------

### processEndTag

    boolean processEndTag

Does the end tag need to be processed. Default value is true. Boolean set in case of ignored errors.

------------------------------------------------------------------------

### cachedCurrentContext

    ComponentContext cachedCurrentContext

Current component context.

------------------------------------------------------------------------

### tagHandler

    InsertTag.TagHandler tagHandler

Final handler of tag methods.

------------------------------------------------------------------------

### pageContext

    PageContext pageContext

Trick to allows inner classes to access pageContext.

<span id="org.apache.struts.tiles.taglib.PutListTag"></span>

**Class [org.apache.struts.tiles.taglib.PutListTag](org/apache/struts/tiles/taglib/PutListTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributeName

    String attributeName

Name of this attribute.

------------------------------------------------------------------------

### list

    List<E> list

The list itself.

------------------------------------------------------------------------

### role

    String role

Role attribute.

<span id="org.apache.struts.tiles.taglib.PutTag"></span>

**Class [org.apache.struts.tiles.taglib.PutTag](org/apache/struts/tiles/taglib/PutTag.html.md "class in org.apache.struts.tiles.taglib") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributeName

    String attributeName

Name of attribute to put in component context.

------------------------------------------------------------------------

### value

    Object value

Associated attribute value.

------------------------------------------------------------------------

### direct

    String direct

JSP Template compatibility.

------------------------------------------------------------------------

### valueType

    String valueType

Requested type for the value.

------------------------------------------------------------------------

### beanName

    String beanName

Bean name attribute.

------------------------------------------------------------------------

### beanProperty

    String beanProperty

Bean property attribute.

------------------------------------------------------------------------

### beanScope

    String beanScope

Bean scope attribute.

------------------------------------------------------------------------

### role

    String role

Role attribute.

------------------------------------------------------------------------

### realValue

    Object realValue

Cached real value computed from tag attributes.

------------------------------------------------------------------------

### body

    String body

The body content of this tag.

<span id="org.apache.struts.tiles.taglib.UseAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.UseAttributeTag](org/apache/struts/tiles/taglib/UseAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### classname

    String classname

Class name of object.

------------------------------------------------------------------------

### scopeName

    String scopeName

The scope name.

------------------------------------------------------------------------

### scope

    int scope

The scope value.

------------------------------------------------------------------------

### attributeName

    String attributeName

The attribute name to be exposed.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute 'ignore'. Default value is `false`, which throws an exception. Only "attribute not found" - errors are ignored.

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.xmlDefinition**

<span id="org.apache.struts.tiles.xmlDefinition.DefinitionsFactory"></span>

**Class [org.apache.struts.tiles.xmlDefinition.DefinitionsFactory](org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### definitions

    Map<K,V> definitions

Underlying map containing all definitions.

<span id="org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

**Class [org.apache.struts.tiles.xmlDefinition.FactorySet](org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factories

    Map<K,V> factories

Loaded factories

<span id="org.apache.struts.tiles.xmlDefinition.I18nFactorySet"></span>

**Class [org.apache.struts.tiles.xmlDefinition.I18nFactorySet](org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [FactorySet](org/apache/struts/tiles/xmlDefinition/FactorySet.html "class in org.apache.struts.tiles.xmlDefinition") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### defaultFactory

    DefinitionsFactory defaultFactory

Default factory.

------------------------------------------------------------------------

### isValidatingParser

    boolean isValidatingParser

Do we want validating parser. Default is `false`. Can be set from servlet config file.

------------------------------------------------------------------------

### parserDetailLevel

    int parserDetailLevel

Parser detail level. Default is 0. Can be set from servlet config file.

------------------------------------------------------------------------

### filenames

    List<E> filenames

Names of files containing instances descriptions.

------------------------------------------------------------------------

### loaded

    Map<K,V> loaded

Collection of already loaded definitions set, referenced by their suffix.

<span id="org.apache.struts.tiles.xmlDefinition.XmlDefinition"></span>

**Class [org.apache.struts.tiles.xmlDefinition.XmlDefinition](org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [ComponentDefinition](org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### inherit

    String inherit

Extends attribute value.

------------------------------------------------------------------------

### isVisited

    boolean isVisited

Used for resolving inheritance.

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
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
