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
<td align="left"><a href="class-use/DefinitionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/DefinitionTag.html"><strong>FRAMES</strong></a>    <a href="DefinitionTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib
 Class DefinitionTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.DefinitionTagSupport
              org.apache.struts.tiles.taglib.DefinitionTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib"), [PutTagParent](../../../../../org/apache/struts/tiles/taglib/PutTagParent.html "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Direct Known Subclasses:**  
[ELDefinitionTag](../../../../../org/apache/strutsel/taglib/tiles/ELDefinitionTag.html.md "class in org.apache.strutsel.taglib.tiles")

------------------------------------------------------------------------

    public class DefinitionTag

extends [DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")

implements [PutTagParent](../../../../../org/apache/struts/tiles/taglib/PutTagParent.html.md "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib")

This is the tag handler for \<tiles:definition\>, which defines a tiles (or template / component). Definition is put in requested context and can be used in \<tiles:insert&gt.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.DefinitionTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Fields inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` controllerName,  controllerType,  page,  role`                                                                                                                                                         |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pageContext`                                                                                                                                                                                                           |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.IterationTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_AGAIN`                                                                                                                                                                                                               |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` DefinitionTag()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Process the end tag by putting the definition in appropriate context.

` int`

` doStartTag()`
           Process the start tag by creating a new definition.

` String`

` getExtends()`
           Get `extends` (parent) definition name.

` String`

` getId()`
           Get the ID.

` String`

` getScope()`
           Get the scope.

` void`

` processNestedTag(PutListTag nestedTag)`
           Process nested &lg;putList\> tag.

` void`

` processNestedTag(PutTag nestedTag)`
           Process nested &lg;put\> tag.

` void`

` putAttribute(String name, Object content)`
           This method is a convenience for other tags for putting content into the tile definition.

` void`

` release()`
           Reset member values for reuse.

`protected  void`

` releaseInternal()`
           Release internal references.

` void`

` setExtends(String definitionName)`
           Set `extends` (parent) definition name.

` void`

` setId(String id)`
           Set the ID.

` void`

` setScope(String aScope)`
           Set the scope.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")**    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getControllerName,  getControllerType,  getPage,  getRole,  getTemplate,  setController,  setControllerClass,  setControllerName,  setControllerType,  setControllerUrl,  setPage,  setRole,  setTemplate` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getParent, getValue, getValues, removeValue, setPageContext, setParent, setValue`                                                                                                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionTag

    public DefinitionTag()

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Reset member values for reuse. This method calls super.release(), which invokes TagSupport.release(), which typically does nothing.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `DefinitionTagSupport`

------------------------------------------------------------------------

### releaseInternal

    protected void releaseInternal()

Release internal references.

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(String name,
                             Object content)

This method is a convenience for other tags for putting content into the tile definition. Content is already typed by caller.

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(PutTag nestedTag)
                          throws JspException

Process nested &lg;put\> tag. Method is called from nested &lg;put\> tags. Nested list is added to current list. If role is defined, nested attribute is wrapped into an untyped definition containing attribute value and role.

**Specified by:**  
` processNestedTag` in interface `PutTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested tag to process.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(PutListTag nestedTag)
                          throws JspException

Process nested &lg;putList\> tag. Method is called from nested &lg;putList\> tags. Nested list is added to current list. If role is defined, nested attribute is wrapped into an untyped definition containing attribute value and role.

**Specified by:**  
` processNestedTag` in interface `PutListTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested PutTag defining the attribute.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### getId

    public String getId()

Get the ID.

**Overrides:**  
`getId` in class `TagSupport`

<!-- -->

**Returns:**  
ID

------------------------------------------------------------------------

### setId

    public void setId(String id)

Set the ID.

**Overrides:**  
`setId` in class `TagSupport`

<!-- -->

**Parameters:**  
`id` - New ID.

------------------------------------------------------------------------

### getScope

    public String getScope()

Get the scope.

**Returns:**  
Scope.

------------------------------------------------------------------------

### setScope

    public void setScope(String aScope)

Set the scope.

**Parameters:**  
`aScope` - Scope.

------------------------------------------------------------------------

### setExtends

    public void setExtends(String definitionName)

Set `extends` (parent) definition name.

**Parameters:**  
`definitionName` - Name of parent definition.

------------------------------------------------------------------------

### getExtends

    public String getExtends()

Get `extends` (parent) definition name.

**Returns:**  
Name of parent definition.

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag by creating a new definition.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - On errors processing tag.

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Process the end tag by putting the definition in appropriate context.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - On errors processing tag.

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
<td align="left"><a href="class-use/DefinitionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/DefinitionTag.html"><strong>FRAMES</strong></a>    <a href="DefinitionTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
