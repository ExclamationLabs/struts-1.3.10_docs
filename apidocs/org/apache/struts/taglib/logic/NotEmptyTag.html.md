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
<td align="left"><a href="class-use/NotEmptyTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/MessagesPresentTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/NotEqualTag.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/NotEmptyTag.html"><strong>FRAMES</strong></a>    <a href="NotEmptyTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.logic
 Class NotEmptyTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.ConditionalTagBase
              org.apache.struts.taglib.logic.EmptyTag
                  org.apache.struts.taglib.logic.NotEmptyTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedNotEmptyTag](../../../../../org/apache/struts/taglib/nested/logic/NestedNotEmptyTag.html.md "class in org.apache.struts.taglib.nested.logic")

------------------------------------------------------------------------

    public class NotEmptyTag

extends [EmptyTag](../../../../../org/apache/struts/taglib/logic/EmptyTag.html.md "class in org.apache.struts.taglib.logic")

Evalute the nested body content of this tag if the specified value is not empty for this request.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.logic.NotEmptyTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cookie,  header,  messages,  name,  parameter,  property,  role,  scope,  user`                                                                                                                    |

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
| ` NotEmptyTag()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  boolean`

` condition()`
           Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.EmptyTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[EmptyTag](../../../../../org/apache/struts/taglib/logic/EmptyTag.html.md "class in org.apache.struts.taglib.logic")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` condition`                                                                                                                                                                      |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")**                          |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doEndTag,  doStartTag,  getCookie,  getHeader,  getName,  getParameter,  getProperty,  getRole,  getScope,  getUser,  release,  setCookie,  setHeader,  setName,  setParameter,  setProperty,  setRole,  setScope,  setUser` |

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

### NotEmptyTag

    public NotEmptyTag()

<span id="method_detail"></span>

**Method Detail**

### condition

    protected boolean condition()
                         throws JspException

Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped. This method must be implemented by concrete subclasses.

**Overrides:**  
` condition` in class `EmptyTag`

<!-- -->

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
<td align="left"><a href="class-use/NotEmptyTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/MessagesPresentTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/NotEqualTag.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/NotEmptyTag.html"><strong>FRAMES</strong></a>    <a href="NotEmptyTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
