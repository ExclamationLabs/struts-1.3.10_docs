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
<td align="left"><a href="class-use/ELMessageTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELIncludeTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELMessageTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELMessageTag.html"><strong>FRAMES</strong></a>    <a href="ELMessageTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.MessageTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.bean
 Class ELMessageTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.MessageTag
              org.apache.strutsel.taglib.bean.ELMessageTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELMessageTag

extends [MessageTag](../../../../../org/apache/struts/taglib/bean/MessageTag.html.md "class in org.apache.struts.taglib.bean")

Custom tag that retrieves an internationalized messages string (with optional parametric replacement) from the `ActionResources` object stored as a context attribute by our associated `ActionServlet` implementation.

This class is a subclass of the class `org.apache.struts.taglib.bean.MessageTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.bean.ELMessageTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.bean.MessageTag"></span>

| **Fields inherited from class org.apache.struts.taglib.bean.[MessageTag](../../../../../org/apache/struts/taglib/bean/MessageTag.html.md "class in org.apache.struts.taglib.bean")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` arg0,  arg1,  arg2,  arg3,  arg4,  bundle, key,  localeKey,  messages,  name,  property,  scope`                                                                                |

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

| **Constructor Summary** |
|-------------------------|
| ` ELMessageTag()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getArg0Expr()`
           Getter method for "arg0" tag attribute.

` String`

` getArg1Expr()`
           Getter method for "arg1" tag attribute.

` String`

` getArg2Expr()`
           Getter method for "arg2" tag attribute.

` String`

` getArg3Expr()`
           Getter method for "arg3" tag attribute.

` String`

` getArg4Expr()`
           Getter method for "arg4" tag attribute.

` String`

` getBundleExpr()`
           Getter method for "bundle" tag attribute.

` String`

` getKeyExpr()`
           Getter method for "key" tag attribute.

` String`

` getLocaleExpr()`
           Getter method for "locale" tag attribute.

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
           Resets attribute values for tag reuse.

` void`

` setArg0Expr(String arg0Expr)`
           Setter method for "arg0" tag attribute.

` void`

` setArg1Expr(String arg1Expr)`
           Setter method for "arg1" tag attribute.

` void`

` setArg2Expr(String arg2Expr)`
           Setter method for "arg2" tag attribute.

` void`

` setArg3Expr(String arg3Expr)`
           Setter method for "arg3" tag attribute.

` void`

` setArg4Expr(String arg4Expr)`
           Setter method for "arg4" tag attribute.

` void`

` setBundleExpr(String bundleExpr)`
           Setter method for "bundle" tag attribute.

` void`

` setKeyExpr(String keyExpr)`
           Setter method for "key" tag attribute.

` void`

` setLocaleExpr(String localeExpr)`
           Setter method for "locale" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.bean.MessageTag"></span>

| **Methods inherited from class org.apache.struts.taglib.bean.[MessageTag](../../../../../org/apache/struts/taglib/bean/MessageTag.html.md "class in org.apache.struts.taglib.bean")**                                                           |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getArg0,  getArg1,  getArg2,  getArg3,  getArg4,  getBundle,  getKey,  getLocale,  getName,  getProperty,  getScope,  setArg0,  setArg1,  setArg2,  setArg3,  setArg4,  setBundle,  setKey,  setLocale,  setName,  setProperty,  setScope` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                           |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELMessageTag

    public ELMessageTag()

<span id="method_detail"></span>

**Method Detail**

### getArg0Expr

    public String getArg0Expr()

Getter method for "arg0" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getArg1Expr

    public String getArg1Expr()

Getter method for "arg1" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getArg2Expr

    public String getArg2Expr()

Getter method for "arg2" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getArg3Expr

    public String getArg3Expr()

Getter method for "arg3" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getArg4Expr

    public String getArg4Expr()

Getter method for "arg4" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBundleExpr

    public String getBundleExpr()

Getter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getKeyExpr

    public String getKeyExpr()

Getter method for "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLocaleExpr

    public String getLocaleExpr()

Getter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setArg0Expr

    public void setArg0Expr(String arg0Expr)

Setter method for "arg0" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setArg1Expr

    public void setArg1Expr(String arg1Expr)

Setter method for "arg1" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setArg2Expr

    public void setArg2Expr(String arg2Expr)

Setter method for "arg2" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setArg3Expr

    public void setArg3Expr(String arg3Expr)

Setter method for "arg3" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setArg4Expr

    public void setArg4Expr(String arg4Expr)

Setter method for "arg4" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBundleExpr

    public void setBundleExpr(String bundleExpr)

Setter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setKeyExpr

    public void setKeyExpr(String keyExpr)

Setter method for "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLocaleExpr

    public void setLocaleExpr(String localeExpr)

Setter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

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

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `MessageTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `MessageTag`

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
<td align="left"><a href="class-use/ELMessageTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/bean/ELIncludeTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/bean/ELMessageTagBeanInfo.html" title="class in org.apache.strutsel.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/ELMessageTag.html"><strong>FRAMES</strong></a>    <a href="ELMessageTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.bean.MessageTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
