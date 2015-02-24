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
<td align="left"><a href="class-use/ELDefinitionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/tiles/ELAddTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/tiles/ELDefinitionTagBeanInfo.html" title="class in org.apache.strutsel.taglib.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/tiles/ELDefinitionTag.html"><strong>FRAMES</strong></a>    <a href="ELDefinitionTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.strutsel.taglib.tiles
 Class ELDefinitionTag
--------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.DefinitionTagSupport
              org.apache.struts.tiles.taglib.DefinitionTag
                  org.apache.strutsel.taglib.tiles.ELDefinitionTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [PutListTagParent](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/PutListTagParent.html?is-external=true "class or interface in org.apache.struts.tiles.taglib"), [PutTagParent](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/PutTagParent.html?is-external=true "class or interface in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public class ELDefinitionTag

extends [DefinitionTag](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/DefinitionTag.html.md?is-external=true "class or interface in org.apache.struts.tiles.taglib")

This is the tag handler for \<tiles:definition\>, which defines a tiles (or template / component). Definition is put in requested context and can be used in \<tiles:insert&gt.

This class is a subclass of the class `org.apache.struts.taglib.tiles.DefinitionTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.tiles.ELDefinitionTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Fields inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md?is-external=true "class or interface in org.apache.struts.tiles.taglib")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `controllerName, controllerType, page, role`                                                                                                                                                                                                             |

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
| ` ELDefinitionTag()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getExtendsExpr()`
           Getter method for "extends" tag attribute.

` String`

` getIdExpr()`
           Getter method for "id" tag attribute.

` String`

` getPageExpr()`
           Getter method for "page" tag attribute.

` String`

` getRoleExpr()`
           Getter method for "role" tag attribute.

` String`

` getScopeExpr()`
           Getter method for "scope" tag attribute.

` String`

` getTemplateExpr()`
           Getter method for "template" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setExtendsExpr(String extendsExpr)`
           Setter method for "extends" tag attribute.

` void`

` setIdExpr(String idExpr)`
           Setter method for "id" tag attribute.

` void`

` setPageExpr(String pageExpr)`
           Setter method for "page" tag attribute.

` void`

` setRoleExpr(String roleExpr)`
           Setter method for "role" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

` void`

` setTemplateExpr(String templateExpr)`
           Setter method for "template" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTag"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[DefinitionTag](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/DefinitionTag.html.md?is-external=true "class or interface in org.apache.struts.tiles.taglib")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getExtends, getId, getScope, processNestedTag, processNestedTag, putAttribute, releaseInternal, setExtends, setId, setScope`                                                                                                     |

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](http://struts.apache.org/apidocs/org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md?is-external=true "class or interface in org.apache.struts.tiles.taglib")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getControllerName, getControllerType, getPage, getRole, getTemplate, setController, setControllerClass, setControllerName, setControllerType, setControllerUrl, setPage, setRole, setTemplate`                                                           |

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

### ELDefinitionTag

    public ELDefinitionTag()

<span id="method_detail"></span>

**Method Detail**

### getIdExpr

    public String getIdExpr()

Getter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScopeExpr

    public String getScopeExpr()

Getter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTemplateExpr

    public String getTemplateExpr()

Getter method for "template" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageExpr

    public String getPageExpr()

Getter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getRoleExpr

    public String getRoleExpr()

Getter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getExtendsExpr

    public String getExtendsExpr()

Getter method for "extends" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIdExpr

    public void setIdExpr(String idExpr)

Setter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScopeExpr

    public void setScopeExpr(String scopeExpr)

Setter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTemplateExpr

    public void setTemplateExpr(String templateExpr)

Setter method for "template" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageExpr

    public void setPageExpr(String pageExpr)

Setter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setRoleExpr

    public void setRoleExpr(String roleExpr)

Setter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setExtendsExpr

    public void setExtendsExpr(String extendsExpr)

Setter method for "extends" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `DefinitionTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `DefinitionTag`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

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
<td align="left"><a href="class-use/ELDefinitionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/tiles/ELAddTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/tiles/ELDefinitionTagBeanInfo.html" title="class in org.apache.strutsel.taglib.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/tiles/ELDefinitionTag.html"><strong>FRAMES</strong></a>    <a href="ELDefinitionTag.html"><strong>NO FRAMES</strong></a>    
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
