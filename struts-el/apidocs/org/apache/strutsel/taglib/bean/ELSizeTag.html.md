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
<td align="left"><a href="class-use/ELSizeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELResourceTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELSizeTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELSizeTag.html"><strong>FRAMES</strong></a>    <a href="ELSizeTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.SizeTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.bean
 Class ELSizeTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.SizeTag
              org.apache.strutsel.taglib.bean.ELSizeTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELSizeTag

extends [SizeTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/SizeTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")

Define a scripting variable that will contain the number of elements found in a specified array, Collection, or Map.

This class is a subclass of the class `org.apache.struts.taglib.bean.SizeTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.bean.ELSizeTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.bean.SizeTag"></span>

| **Fields inherited from class org.apache.struts.taglib.bean.[SizeTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/SizeTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `collection, id, messages, name, property, scope`                                                                                                                                                                           |

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
| ` ELSizeTag()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getCollectionExpr()`
           Getter method for "collection" tag attribute.

` String`

` getIdExpr()`
           Getter method for "id" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

` String`

` getScopeExpr()`
           Getter method for "scope" tag attribute.

` void`

` release()`
           Releases state of custom tag so this instance can be reused.

` void`

` setCollectionExpr(String collectionExpr)`
           Setter method for "collection" tag attribute.

` void`

` setIdExpr(String idExpr)`
           Setter method for "id" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.bean.SizeTag"></span>

| **Methods inherited from class org.apache.struts.taglib.bean.[SizeTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/bean/SizeTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.bean")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getCollection, getId, getName, getProperty, getScope, setCollection, setId, setName, setProperty, setScope`                                                                                                                 |

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

### ELSizeTag

    public ELSizeTag()

<span id="method_detail"></span>

**Method Detail**

### getCollectionExpr

    public String getCollectionExpr()

Getter method for "collection" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getIdExpr

    public String getIdExpr()

Getter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScopeExpr

    public String getScopeExpr()

Getter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setCollectionExpr

    public void setCollectionExpr(String collectionExpr)

Setter method for "collection" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIdExpr

    public void setIdExpr(String idExpr)

Setter method for "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScopeExpr

    public void setScopeExpr(String scopeExpr)

Setter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Releases state of custom tag so this instance can be reused.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `SizeTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `SizeTag`

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
<td align="left"><a href="class-use/ELSizeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELResourceTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELSizeTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELSizeTag.html"><strong>FRAMES</strong></a>    <a href="ELSizeTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.SizeTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
