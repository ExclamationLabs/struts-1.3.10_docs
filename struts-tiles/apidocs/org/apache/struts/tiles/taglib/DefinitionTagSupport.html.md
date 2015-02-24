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
<td align="left"><a href="class-use/DefinitionTagSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/DefinitionTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/GetAttributeTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/DefinitionTagSupport.html"><strong>FRAMES</strong></a>    <a href="DefinitionTagSupport.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.taglib
 Class DefinitionTagSupport
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.DefinitionTagSupport

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[DefinitionTag](../../../../../org/apache/struts/tiles/taglib/DefinitionTag.html.md "class in org.apache.struts.tiles.taglib"), [InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public class DefinitionTagSupport

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Common base class for tags dealing with Tiles definitions. This class defines properties used in Definition Tags. It also extends TagSupport.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.DefinitionTagSupport)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` controllerName`
           Associated Controller name (classname or url)

`protected  String`

` controllerType`
           Associated Controller type

`protected  String`

` page`
           Uri of page assoicated to this definition.

`protected  String`

` role`
           Role associated to definition.

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.IterationTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_AGAIN`                                                                                                                                                                                                               |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary**   |
|---------------------------|
| ` DefinitionTagSupport()` 
                            |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getControllerName()`
           Get controller name.

` String`

` getControllerType()`
           Get controller type.

` String`

` getPage()`
           Get the page.

` String`

` getRole()`
           Get associated role.

` String`

` getTemplate()`
           Get the template.

` void`

` release()`
           Release class properties.

` void`

` setController(String controller)`
           Set associated controller name.

` void`

` setControllerClass(String controller)`
           Set associated controller name as a classtype and controller type as "classname".

` void`

` setControllerName(String controller)`
           Set associated controller name.

` void`

` setControllerType(String controllerType)`
           Set associated controller type.

` void`

` setControllerUrl(String controller)`
           Set associated controller name as an url, and controller type as "url".

` void`

` setPage(String page)`
           Set the page.

` void`

` setRole(String role)`
           Set associated role.

` void`

` setTemplate(String template)`
           Set the template.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, doStartTag, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                               |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="controllerType"></span>

### controllerType

    protected String controllerType

Associated Controller type

------------------------------------------------------------------------

<span id="controllerName"></span>

### controllerName

    protected String controllerName

Associated Controller name (classname or url)

------------------------------------------------------------------------

<span id="role"></span>

### role

    protected String role

Role associated to definition.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

Uri of page assoicated to this definition.

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionTagSupport

    public DefinitionTagSupport()

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Release class properties.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

------------------------------------------------------------------------

### getControllerType

    public String getControllerType()

Get controller type. Type can be 'classname', 'url'.

**Returns:**  
Controller type.

------------------------------------------------------------------------

### getControllerName

    public String getControllerName()

Get controller name. Name denotes a fully qualified classname, or an url. Exact type can be specified with [`setControllerType(java.lang.String)`](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md#setControllerType(java.lang.String)).

**Returns:**  
Controller name.

------------------------------------------------------------------------

### setControllerType

    public void setControllerType(String controllerType)

Set associated controller type. Type denotes a fully qualified classname.

**Parameters:**  
`controllerType` - Type of associated controller.

------------------------------------------------------------------------

### setController

    public void setController(String controller)

Set associated controller name. Name denotes a fully qualified classname, or an url. Exact type can be specified with [`setControllerType(java.lang.String)`](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md#setControllerType(java.lang.String)).

**Parameters:**  
`controller` - Controller classname or url.

------------------------------------------------------------------------

### setControllerName

    public void setControllerName(String controller)

Set associated controller name. Name denote a fully qualified classname, or an url. Exact type can be specified with setControllerType.

**Parameters:**  
`controller` - Controller classname or url

------------------------------------------------------------------------

### setControllerUrl

    public void setControllerUrl(String controller)

Set associated controller name as an url, and controller type as "url". Name must be an url (not checked). Convenience method.

**Parameters:**  
`controller` - Controller url

------------------------------------------------------------------------

### setControllerClass

    public void setControllerClass(String controller)

Set associated controller name as a classtype and controller type as "classname". Name denotes a fully qualified classname. Convenience method.

**Parameters:**  
`controller` - Controller classname.

------------------------------------------------------------------------

### getRole

    public String getRole()

Get associated role.

**Returns:**  
Associated role.

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Set associated role.

**Parameters:**  
`role` - Associated role.

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

Set the page.

**Parameters:**  
`page` - Page.

------------------------------------------------------------------------

### getPage

    public String getPage()

Get the page.

**Returns:**  
Page.

------------------------------------------------------------------------

### getTemplate

    public String getTemplate()

Get the template. Same as getPage().

**Returns:**  
Template.

------------------------------------------------------------------------

### setTemplate

    public void setTemplate(String template)

Set the template. Same as setPage().

**Parameters:**  
`template` - Template.

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
<td align="left"><a href="class-use/DefinitionTagSupport.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/DefinitionTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/GetAttributeTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/DefinitionTagSupport.html"><strong>FRAMES</strong></a>    <a href="DefinitionTagSupport.html"><strong>NO FRAMES</strong></a>    
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
