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
<td align="left"><a href="class-use/ELStrutsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELSizeTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELStrutsTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELStrutsTag.html"><strong>FRAMES</strong></a>    <a href="ELStrutsTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.StrutsTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.bean
 Class ELStrutsTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.StrutsTag
              org.apache.strutsel.taglib.bean.ELStrutsTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELStrutsTag

extends [StrutsTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/StrutsTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")

Define a scripting variable that exposes the requested Struts internal configuraton object.

This class is a subclass of the class `org.apache.struts.taglib.bean.StrutsTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.bean.ELStrutsTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.bean.StrutsTag"></span>

| **Fields inherited from class org.apache.struts.taglib.bean.[StrutsTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/StrutsTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `formBean, forward, id, mapping, messages`                                                                                                                                                                                      |

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
| ` ELStrutsTag()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getFormBeanExpr()`
           Getter method for "formBean" tag attribute.

` String`

` getForwardExpr()`
           Getter method for "forward" tag attribute.

` String`

` getIdExpr()`
           Getter method for "id" tag attribute.

` String`

` getMappingExpr()`
           Getter method for "mapping" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setFormBeanExpr(String formBeanExpr)`
           Setter method for "formBean" tag attribute.

` void`

` setForwardExpr(String forwardExpr)`
           Setter method for "forward" tag attribute.

` void`

` setIdExpr(String idExpr)`
           Setter method for "id" tag attribute.

` void`

` setMappingExpr(String mappingExpr)`
           Setter method for "mapping" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.bean.StrutsTag"></span>

| **Methods inherited from class org.apache.struts.taglib.bean.[StrutsTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/StrutsTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getFormBean, getForward, getId, getMapping, setFormBean, setForward, setId, setMapping`                                                                                                                                         |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, findAncestorWithClass, getParent, getValue, getValues, removeValue, setPageContext, setParent, setValue`                                                                                         |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELStrutsTag

    public ELStrutsTag()

<span id="method_detail"></span>

**Method Detail**

### getIdExpr

    public String getIdExpr()

Getter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFormBeanExpr

    public String getFormBeanExpr()

Getter method for "formBean" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getForwardExpr

    public String getForwardExpr()

Getter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMappingExpr

    public String getMappingExpr()

Getter method for "mapping" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIdExpr

    public void setIdExpr(String idExpr)

Setter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFormBeanExpr

    public void setFormBeanExpr(String formBeanExpr)

Setter method for "formBean" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setForwardExpr

    public void setForwardExpr(String forwardExpr)

Setter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMappingExpr

    public void setMappingExpr(String mappingExpr)

Setter method for "mapping" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `StrutsTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `StrutsTag`

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
<td align="left"><a href="class-use/ELStrutsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELSizeTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELStrutsTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELStrutsTag.html"><strong>FRAMES</strong></a>    <a href="ELStrutsTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.StrutsTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
