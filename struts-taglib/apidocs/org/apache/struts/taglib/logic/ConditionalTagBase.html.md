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
<td align="left"><a href="class-use/ConditionalTagBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/CompareTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/EmptyTag.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/ConditionalTagBase.html"><strong>FRAMES</strong></a>    <a href="ConditionalTagBase.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.taglib.logic
 Class ConditionalTagBase
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.ConditionalTagBase

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[CompareTagBase](../../../../../org/apache/struts/taglib/logic/CompareTagBase.html.md "class in org.apache.struts.taglib.logic"), [EmptyTag](../../../../../org/apache/struts/taglib/logic/EmptyTag.html "class in org.apache.struts.taglib.logic"), [MatchTag](../../../../../org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic"), [MessagesPresentTag](../../../../../org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic"), [PresentTag](../../../../../org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic")

------------------------------------------------------------------------

    public abstract class ConditionalTagBase

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Abstract base class for the various conditional evaluation tags.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.logic.ConditionalTagBase)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` cookie`
           The name of the cookie to be used as a variable.

`protected  String`

` header`
           The name of the HTTP request header to be used as a variable.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           The name of the JSP bean to be used as a variable (if `property` is not specified), or whose property is to be accessed (if `property` is specified).

`protected  String`

` parameter`
           The name of the HTTP request parameter to be used as a variable.

`protected  String`

` property`
           The name of the bean property to be used as a variable.

`protected  String`

` role`
           The name of the security role to be checked for.

`protected  String`

` scope`
           The scope to search for the bean named by the name property, or "any scope" if null.

`protected  String`

` user`
           The user principal name to be checked for.

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
| ` ConditionalTagBase()` 
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected abstract  boolean`

` condition()`
           Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped.

` int`

` doEndTag()`
           Evaluate the remainder of the current page normally.

` int`

` doStartTag()`
           Perform the test required for this particular tag, and either evaluate or skip the body of this tag.

` String`

` getCookie()`
            

` String`

` getHeader()`
            

` String`

` getName()`
            

` String`

` getParameter()`
            

` String`

` getProperty()`
            

` String`

` getRole()`
            

` String`

` getScope()`
            

` String`

` getUser()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setCookie(String cookie)`
            

` void`

` setHeader(String header)`
            

` void`

` setName(String name)`
            

` void`

` setParameter(String parameter)`
            

` void`

` setProperty(String property)`
            

` void`

` setRole(String role)`
            

` void`

` setScope(String scope)`
            

` void`

` setUser(String user)`
            

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="cookie"></span>

### cookie

    protected String cookie

The name of the cookie to be used as a variable.

------------------------------------------------------------------------

<span id="header"></span>

### header

    protected String header

The name of the HTTP request header to be used as a variable.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the JSP bean to be used as a variable (if `property` is not specified), or whose property is to be accessed (if `property` is specified).

------------------------------------------------------------------------

<span id="parameter"></span>

### parameter

    protected String parameter

The name of the HTTP request parameter to be used as a variable.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The name of the bean property to be used as a variable.

------------------------------------------------------------------------

<span id="role"></span>

### role

    protected String role

The name of the security role to be checked for.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope to search for the bean named by the name property, or "any scope" if null.

------------------------------------------------------------------------

<span id="user"></span>

### user

    protected String user

The user principal name to be checked for.

<span id="constructor_detail"></span>

**Constructor Detail**

### ConditionalTagBase

    public ConditionalTagBase()

<span id="method_detail"></span>

**Method Detail**

### getCookie

    public String getCookie()

------------------------------------------------------------------------

### setCookie

    public void setCookie(String cookie)

------------------------------------------------------------------------

### getHeader

    public String getHeader()

------------------------------------------------------------------------

### setHeader

    public void setHeader(String header)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getParameter

    public String getParameter()

------------------------------------------------------------------------

### setParameter

    public void setParameter(String parameter)

------------------------------------------------------------------------

### getProperty

    public String getProperty()

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

------------------------------------------------------------------------

### getRole

    public String getRole()

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

------------------------------------------------------------------------

### getScope

    public String getScope()

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

------------------------------------------------------------------------

### getUser

    public String getUser()

------------------------------------------------------------------------

### setUser

    public void setUser(String user)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Perform the test required for this particular tag, and either evaluate or skip the body of this tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception occurs

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Evaluate the remainder of the current page normally.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception occurs

------------------------------------------------------------------------

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

------------------------------------------------------------------------

### condition

    protected abstract boolean condition()
                                  throws JspException

Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped. This method must be implemented by concrete subclasses.

**Throws:**  
`JspException` - if a JSP exception occurs

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
<td align="left"><a href="class-use/ConditionalTagBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/CompareTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/EmptyTag.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/ConditionalTagBase.html"><strong>FRAMES</strong></a>    <a href="ConditionalTagBase.html"><strong>NO FRAMES</strong></a>    
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
