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
<td align="left"><a href="class-use/ELNotPresentTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELNotMatchTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELNotPresentTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELNotPresentTag.html"><strong>FRAMES</strong></a>    <a href="ELNotPresentTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.PresentTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.logic
 Class ELNotPresentTag
--------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.ConditionalTagBase
              org.apache.struts.taglib.logic.PresentTag
                  org.apache.struts.taglib.logic.NotPresentTag
                      org.apache.strutsel.taglib.logic.ELNotPresentTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELNotPresentTag

extends [NotPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/NotPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")

Evaluates the nested body content of this tag if the specified value is not present for this request.

This class is a subclass of the class `org.apache.struts.taglib.logic.NotPresentTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.logic.ELNotPresentTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.PresentTag"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[PresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/PresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ROLE_DELIMITER`                                                                                                                                                                                                                     |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/ConditionalTagBase.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `cookie, header, messages, name, parameter, property, role, scope, user`                                                                                                                                                                             |

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
| ` ELNotPresentTag()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getCookieExpr()`
           Getter method for "cookie" tag attribute.

` String`

` getHeaderExpr()`
           Getter method for "header" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getParameterExpr()`
           Getter method for "parameter" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

` String`

` getRoleExpr()`
           Getter method for "role" tag attribute.

` String`

` getScopeExpr()`
           Getter method for "scope" tag attribute.

` String`

` getUserExpr()`
           Getter method for "user" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setCookieExpr(String cookieExpr)`
           Setter method for "cookie" tag attribute.

` void`

` setHeaderExpr(String headerExpr)`
           Setter method for "header" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setParameterExpr(String parameterExpr)`
           Setter method for "parameter" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

` void`

` setRoleExpr(String roleExpr)`
           Setter method for "role" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

` void`

` setUserExpr(String userExpr)`
           Setter method for "user" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.NotPresentTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[NotPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/NotPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `condition`                                                                                                                                                                                                                                 |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.PresentTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[PresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/PresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `condition, isBeanPresent, isCookiePresent`                                                                                                                                                                                           |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/ConditionalTagBase.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getCookie, getHeader, getName, getParameter, getProperty, getRole, getScope, getUser, setCookie, setHeader, setName, setParameter, setProperty, setRole, setScope, setUser`                                                                |

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

### ELNotPresentTag

    public ELNotPresentTag()

<span id="method_detail"></span>

**Method Detail**

### getCookieExpr

    public String getCookieExpr()

Getter method for "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHeaderExpr

    public String getHeaderExpr()

Getter method for "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParameterExpr

    public String getParameterExpr()

Getter method for "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getRoleExpr

    public String getRoleExpr()

Getter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScopeExpr

    public String getScopeExpr()

Getter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getUserExpr

    public String getUserExpr()

Getter method for "user" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setCookieExpr

    public void setCookieExpr(String cookieExpr)

Setter method for "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHeaderExpr

    public void setHeaderExpr(String headerExpr)

Setter method for "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParameterExpr

    public void setParameterExpr(String parameterExpr)

Setter method for "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setRoleExpr

    public void setRoleExpr(String roleExpr)

Setter method for "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScopeExpr

    public void setScopeExpr(String scopeExpr)

Setter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setUserExpr

    public void setUserExpr(String userExpr)

Setter method for "user" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `ConditionalTagBase`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `ConditionalTagBase`

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
<td align="left"><a href="class-use/ELNotPresentTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELNotMatchTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELNotPresentTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELNotPresentTag.html"><strong>FRAMES</strong></a>    <a href="ELNotPresentTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.PresentTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
