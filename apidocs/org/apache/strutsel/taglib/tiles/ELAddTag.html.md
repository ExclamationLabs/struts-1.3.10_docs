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
<td align="left"><a href="class-use/ELAddTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/strutsel/taglib/tiles/ELAddTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/tiles/ELAddTag.html"><strong>FRAMES</strong></a>    <a href="ELAddTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.PutTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.tiles
 Class ELAddTag
--------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.tiles.taglib.PutTag
                  org.apache.struts.tiles.taglib.AddTag
                      org.apache.strutsel.taglib.tiles.ELAddTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public class ELAddTag

extends [AddTag](../../../../../org/apache/struts/tiles/taglib/AddTag.html.md "class in org.apache.struts.tiles.taglib")

Adds an element to the surrounding list tag. Same syntax as `<put>`.

This class is a subclass of the class `org.apache.struts.taglib.tiles.AddTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.tiles.ELAddTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.PutTag"></span>

| **Fields inherited from class org.apache.struts.tiles.taglib.[PutTag](../../../../../org/apache/struts/tiles/taglib/PutTag.html.md "class in org.apache.struts.tiles.taglib")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` attributeName, body,  realValue`                                                                                                                                           |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bodyContent`                                                                                                                                                                                                                   |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.ComponentConstants"></span>

| **Fields inherited from interface org.apache.struts.tiles.taglib.[ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` COMPONENT_CONTEXT,  COMPONENT_SCOPE,  EXCEPTION_KEY,  LOCALE_KEY`                                                                                                                                          |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_BUFFERED, EVAL_BODY_TAG`                                                                                                                                                                                   |

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
| ` ELAddTag()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getBeanNameExpr()`
           Getter method for "beanName" tag attribute.

` String`

` getBeanPropertyExpr()`
           Getter method for "beanProperty" tag attribute.

` String`

` getBeanScopeExpr()`
           Getter method for "beanScope" tag attribute.

` String`

` getContentExpr()`
           Getter method for "content" tag attribute.

` String`

` getDirectExpr()`
           Getter method for "direct" tag attribute.

` String`

` getRoleExpr()`
           Getter method for "role" tag attribute.

` String`

` getTypeExpr()`
           Getter method for "type" tag attribute.

` String`

` getValueExpr()`
           Getter method for "value" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setBeanNameExpr(String beanNameExpr)`
           Setter method for "beanName" tag attribute.

` void`

` setBeanPropertyExpr(String beanPropertyExpr)`
           Setter method for "beanProperty" tag attribute.

` void`

` setBeanScopeExpr(String beanScopeExpr)`
           Setter method for "beanScope" tag attribute.

` void`

` setContentExpr(String contentExpr)`
           Setter method for "content" tag attribute.

` void`

` setDirectExpr(String directExpr)`
           Setter method for "direct" tag attribute.

` void`

` setRoleExpr(String roleExpr)`
           Setter method for "role" tag attribute.

` void`

` setTypeExpr(String typeExpr)`
           Setter method for "type" tag attribute.

` void`

` setValueExpr(String valueExpr)`
           Setter method for "value" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.AddTag"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[AddTag](../../../../../org/apache/struts/tiles/taglib/AddTag.html.md "class in org.apache.struts.tiles.taglib")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` callParent,  findEnclosingPutListTagParent`                                                                                                                                 |

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.PutTag"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[PutTag](../../../../../org/apache/struts/tiles/taglib/PutTag.html.md "class in org.apache.struts.tiles.taglib")**                                                                                                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` computeRealValue,  doAfterBody,  doEndTag,  findEnclosingPutTagParent,  getBeanName,  getBeanProperty,  getBeanScope,  getContent,  getName,  getRealValue,  getRealValueFromBean,  getRole,  getType,  getValue,  releaseInternal,  setBeanName,  setBeanProperty,  setBeanScope,  setContent,  setContent,  setDirect,  setName,  setObjectValue,  setRole,  setType,  setValue,  setValue` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                                                     |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                                  |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Methods inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getParent, setPageContext, setParent`                                                                                                                                                                         |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELAddTag

    public ELAddTag()

<span id="method_detail"></span>

**Method Detail**

### getValueExpr

    public String getValueExpr()

Getter method for "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getContentExpr

    public String getContentExpr()

Getter method for "content" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDirectExpr

    public String getDirectExpr()

Getter method for "direct" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTypeExpr

    public String getTypeExpr()

Getter method for "type" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBeanNameExpr

    public String getBeanNameExpr()

Getter method for "beanName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBeanPropertyExpr

    public String getBeanPropertyExpr()

Getter method for "beanProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBeanScopeExpr

    public String getBeanScopeExpr()

Getter method for "beanScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getRoleExpr

    public String getRoleExpr()

Getter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setValueExpr

    public void setValueExpr(String valueExpr)

Setter method for "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setContentExpr

    public void setContentExpr(String contentExpr)

Setter method for "content" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDirectExpr

    public void setDirectExpr(String directExpr)

Setter method for "direct" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTypeExpr

    public void setTypeExpr(String typeExpr)

Setter method for "type" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBeanNameExpr

    public void setBeanNameExpr(String beanNameExpr)

Setter method for "beanName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBeanPropertyExpr

    public void setBeanPropertyExpr(String beanPropertyExpr)

Setter method for "beanProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBeanScopeExpr

    public void setBeanScopeExpr(String beanScopeExpr)

Setter method for "beanScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setRoleExpr

    public void setRoleExpr(String roleExpr)

Setter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `PutTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `PutTag`

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
<td align="left"><a href="class-use/ELAddTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/strutsel/taglib/tiles/ELAddTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/tiles/ELAddTag.html"><strong>FRAMES</strong></a>    <a href="ELAddTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.PutTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
