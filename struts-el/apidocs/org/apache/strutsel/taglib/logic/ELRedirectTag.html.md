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
<td align="left"><a href="class-use/ELRedirectTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELPresentTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELRedirectTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELRedirectTag.html"><strong>FRAMES</strong></a>    <a href="ELRedirectTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.RedirectTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.logic
 Class ELRedirectTag
--------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.RedirectTag
              org.apache.strutsel.taglib.logic.ELRedirectTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELRedirectTag

extends [RedirectTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/RedirectTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")

Generate a URL-encoded redirect to the specified URI.

This class is a subclass of the class `org.apache.struts.taglib.logic.RedirectTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.logic.ELRedirectTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.RedirectTag"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[RedirectTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/RedirectTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `action, anchor, forward, href, messages, module, name, page, paramId, paramName, paramProperty, paramScope, property, scope, transaction, useLocalEncoding`                                                                           |

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
| ` ELRedirectTag()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getActionExpr()`
           Getter method for "action" tag attribute.

` String`

` getAnchorExpr()`
           Getter method for "anchor" tag attribute.

` String`

` getForwardExpr()`
           Getter method for "forward" tag attribute.

` String`

` getHrefExpr()`
           Getter method for "href" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getPageExpr()`
           Getter method for "page" tag attribute.

` String`

` getParamIdExpr()`
           Getter method for "paramId" tag attribute.

` String`

` getParamNameExpr()`
           Getter method for "paramName" tag attribute.

` String`

` getParamPropertyExpr()`
           Getter method for "paramProperty" tag attribute.

` String`

` getParamScopeExpr()`
           Getter method for "paramScope" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

` String`

` getScopeExpr()`
           Getter method for "scope" tag attribute.

` String`

` getTransactionExpr()`
           Getter method for "transaction" tag attribute.

` String`

` getUseLocalEncodingExpr()`
           Getter method for "useLocalEncoding" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setActionExpr(String actionExpr)`
           Setter method for "action" tag attribute.

` void`

` setAnchorExpr(String anchorExpr)`
           Setter method for "anchor" tag attribute.

` void`

` setForwardExpr(String forwardExpr)`
           Setter method for "forward" tag attribute.

` void`

` setHrefExpr(String hrefExpr)`
           Setter method for "href" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setPageExpr(String pageExpr)`
           Setter method for "page" tag attribute.

` void`

` setParamIdExpr(String paramIdExpr)`
           Setter method for "paramId" tag attribute.

` void`

` setParamNameExpr(String paramNameExpr)`
           Setter method for "paramName" tag attribute.

` void`

` setParamPropertyExpr(String paramPropertyExpr)`
           Setter method for "paramProperty" tag attribute.

` void`

` setParamScopeExpr(String paramScopeExpr)`
           Setter method for "paramScope" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

` void`

` setTransactionExpr(String transactionExpr)`
           Setter method for "transaction" tag attribute.

` void`

` setUseLocalEncodingExpr(String useLocalEncodingExpr)`
           Setter method for "useLocalEncoding" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.RedirectTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[RedirectTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/RedirectTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")**                                                                                                                                                                                                  |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, doRedirect, generateRedirectURL, getAction, getAnchor, getForward, getHref, getModule, getName, getPage, getParamId, getParamName, getParamProperty, getParamScope, getProperty, getScope, getTransaction, isUseLocalEncoding, setAction, setAnchor, setForward, setHref, setModule, setName, setPage, setParamId, setParamName, setParamProperty, setParamScope, setProperty, setScope, setTransaction, setUseLocalEncoding` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELRedirectTag

    public ELRedirectTag()

<span id="method_detail"></span>

**Method Detail**

### getActionExpr

    public String getActionExpr()

Getter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAnchorExpr

    public String getAnchorExpr()

Getter method for "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getForwardExpr

    public String getForwardExpr()

Getter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHrefExpr

    public String getHrefExpr()

Getter method for "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageExpr

    public String getPageExpr()

Getter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamIdExpr

    public String getParamIdExpr()

Getter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamNameExpr

    public String getParamNameExpr()

Getter method for "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamPropertyExpr

    public String getParamPropertyExpr()

Getter method for "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamScopeExpr

    public String getParamScopeExpr()

Getter method for "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScopeExpr

    public String getScopeExpr()

Getter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTransactionExpr

    public String getTransactionExpr()

Getter method for "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getUseLocalEncodingExpr

    public String getUseLocalEncodingExpr()

Getter method for "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setActionExpr

    public void setActionExpr(String actionExpr)

Setter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAnchorExpr

    public void setAnchorExpr(String anchorExpr)

Setter method for "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setForwardExpr

    public void setForwardExpr(String forwardExpr)

Setter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHrefExpr

    public void setHrefExpr(String hrefExpr)

Setter method for "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageExpr

    public void setPageExpr(String pageExpr)

Setter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamIdExpr

    public void setParamIdExpr(String paramIdExpr)

Setter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamNameExpr

    public void setParamNameExpr(String paramNameExpr)

Setter method for "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamPropertyExpr

    public void setParamPropertyExpr(String paramPropertyExpr)

Setter method for "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamScopeExpr

    public void setParamScopeExpr(String paramScopeExpr)

Setter method for "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScopeExpr

    public void setScopeExpr(String scopeExpr)

Setter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTransactionExpr

    public void setTransactionExpr(String transactionExpr)

Setter method for "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setUseLocalEncodingExpr

    public void setUseLocalEncodingExpr(String useLocalEncodingExpr)

Setter method for "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `RedirectTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `RedirectTag`

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
<td align="left"><a href="class-use/ELRedirectTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELPresentTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELRedirectTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELRedirectTag.html"><strong>FRAMES</strong></a>    <a href="ELRedirectTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.RedirectTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
