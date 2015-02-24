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
<td align="left"><a href="class-use/CompareTagBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/CompareTagBase.html"><strong>FRAMES</strong></a>    <a href="CompareTagBase.html"><strong>NO FRAMES</strong></a>    
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
 Class CompareTagBase
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.ConditionalTagBase
              org.apache.struts.taglib.logic.CompareTagBase

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[EqualTag](../../../../../org/apache/struts/taglib/logic/EqualTag.html.md "class in org.apache.struts.taglib.logic"), [GreaterEqualTag](../../../../../org/apache/struts/taglib/logic/GreaterEqualTag.html "class in org.apache.struts.taglib.logic"), [GreaterThanTag](../../../../../org/apache/struts/taglib/logic/GreaterThanTag.html "class in org.apache.struts.taglib.logic"), [LessEqualTag](../../../../../org/apache/struts/taglib/logic/LessEqualTag.html "class in org.apache.struts.taglib.logic"), [LessThanTag](../../../../../org/apache/struts/taglib/logic/LessThanTag.html "class in org.apache.struts.taglib.logic"), [NotEqualTag](../../../../../org/apache/struts/taglib/logic/NotEqualTag.html "class in org.apache.struts.taglib.logic")

------------------------------------------------------------------------

    public abstract class CompareTagBase

extends [ConditionalTagBase](../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")

Abstract base class for comparison tags. Concrete subclasses need only define values for desired1 and desired2.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.logic.CompareTagBase)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static int`

` DOUBLE_COMPARE`
           We will do a double/float comparison.

`protected static int`

` LONG_COMPARE`
           We will do a long/int comparison.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected static int`

` STRING_COMPARE`
           We will do a String comparison.

` String`

` value`
           The value to which the variable specified by other attributes of this tag will be compared.

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cookie,  header,  name,  parameter,  property,  role,  scope,  user`                                                                                                                               |

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
| ` CompareTagBase()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected abstract  boolean`

` condition()`
           Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped.

`protected  boolean`

` condition(int desired1, int desired2)`
           Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped.

` String`

` getValue()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setValue(String value)`
            

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")**                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doEndTag,  doStartTag,  getCookie,  getHeader,  getName,  getParameter,  getProperty,  getRole,  getScope,  getUser,  setCookie,  setHeader,  setName,  setParameter,  setProperty,  setRole,  setScope,  setUser` |

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

<span id="DOUBLE_COMPARE"></span>

### DOUBLE\_COMPARE

    protected static final int DOUBLE_COMPARE

We will do a double/float comparison.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.taglib.logic.CompareTagBase.DOUBLE_COMPARE)

------------------------------------------------------------------------

<span id="LONG_COMPARE"></span>

### LONG\_COMPARE

    protected static final int LONG_COMPARE

We will do a long/int comparison.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.taglib.logic.CompareTagBase.LONG_COMPARE)

------------------------------------------------------------------------

<span id="STRING_COMPARE"></span>

### STRING\_COMPARE

    protected static final int STRING_COMPARE

We will do a String comparison.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.taglib.logic.CompareTagBase.STRING_COMPARE)

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="value"></span>

### value

    public String value

The value to which the variable specified by other attributes of this tag will be compared.

<span id="constructor_detail"></span>

**Constructor Detail**

### CompareTagBase

    public CompareTagBase()

<span id="method_detail"></span>

**Method Detail**

### getValue

    public String getValue()

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

------------------------------------------------------------------------

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `ConditionalTagBase`

------------------------------------------------------------------------

### condition

    protected abstract boolean condition()
                                  throws JspException

Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped. This method must be implemented by concrete subclasses.

**Specified by:**  
` condition` in class `ConditionalTagBase`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception occurs

------------------------------------------------------------------------

### condition

    protected boolean condition(int desired1,
                                int desired2)
                         throws JspException

Evaluate the condition that is being tested by this particular tag, and return `true` if the nested body content of this tag should be evaluated, or `false` if it should be skipped. This method must be implemented by concrete subclasses.

**Parameters:**  
`desired1` - First desired value for a true result (-1, 0, +1)

`desired2` - Second desired value for a true result (-1, 0, +1)

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
<td align="left"><a href="class-use/CompareTagBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/CompareTagBase.html"><strong>FRAMES</strong></a>    <a href="CompareTagBase.html"><strong>NO FRAMES</strong></a>    
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
