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
<td align="left"><a href="class-use/NestedRootTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedReference.html.md" title="class in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html" title="interface in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedRootTag.html"><strong>FRAMES</strong></a>    <a href="NestedRootTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested
 Class NestedRootTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.nested.NestedRootTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [NestedNameSupport](../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested"), [NestedPropertySupport](../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html "interface in org.apache.struts.taglib.nested"), [NestedTagSupport](../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html "interface in org.apache.struts.taglib.nested")

------------------------------------------------------------------------

    public class NestedRootTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

implements [NestedNameSupport](../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")

NestedRootTag. The only other addition in this nested suite of tags. This tag allows for a nested structure to start without relying on the bean and workings of the FormTag. Useful for view pages that don't update when returning to the server, or use hyperlinks rather than form submits. The Bean that it uses can come out of a jsp:useBean tag or define another bean that's already in scope. As long as the other Struts tags can find the bean by name, it'll work. It's simply recognised by the helper class and it's property is added to the nesting list.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.nested.NestedRootTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bodyContent`                                                                                                                                                                                                                   |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

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
| ` NestedRootTag()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doAfterBody()`
           Render the resulting content evaluation.

` int`

` doEndTag()`
           Evaluate the rest of the page

` int`

` doStartTag()`
           Overriding method of the heart of the tag.

` String`

` getName()`
           Getter method for the *name* property

` String`

` getProperty()`
           Getter method for the *property* property

` void`

` release()`
           JSP method to release all resources held by the tag.

` void`

` setName(String name)`
           Setter method for the *name* property

` void`

` setProperty(String property)`
           Setter method for the *property* property

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

### NestedRootTag

    public NestedRootTag()

<span id="method_detail"></span>

**Method Detail**

### getProperty

    public String getProperty()

Getter method for the *property* property

**Specified by:**  
` getProperty` in interface `NestedPropertySupport`

<!-- -->

**Returns:**  
String value of the property property

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

Setter method for the *property* property

**Specified by:**  
` setProperty` in interface `NestedPropertySupport`

<!-- -->

**Parameters:**  
`property` - new value for the property property

------------------------------------------------------------------------

### getName

    public String getName()

Getter method for the *name* property

**Specified by:**  
` getName` in interface `NestedNameSupport`

<!-- -->

**Returns:**  
String value of the name property

------------------------------------------------------------------------

### setName

    public void setName(String name)

Setter method for the *name* property

**Specified by:**  
` setName` in interface `NestedNameSupport`

<!-- -->

**Parameters:**  
`name` - new value for the name property

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Overriding method of the heart of the tag. Gets the relative property and tells the JSP engine to evaluate its body content.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Returns:**  
int JSP continuation directive.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doAfterBody

    public int doAfterBody()
                    throws JspException

Render the resulting content evaluation.

**Specified by:**  
`doAfterBody` in interface `IterationTag`

**Overrides:**  
`doAfterBody` in class `BodyTagSupport`

<!-- -->

**Returns:**  
int JSP continuation directive.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Evaluate the rest of the page

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

<!-- -->

**Returns:**  
int JSP continuation directive.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### release

    public void release()

JSP method to release all resources held by the tag.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `BodyTagSupport`

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
<td align="left"><a href="class-use/NestedRootTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/nested/NestedReference.html.md" title="class in org.apache.struts.taglib.nested"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html" title="interface in org.apache.struts.taglib.nested"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/nested/NestedRootTag.html"><strong>FRAMES</strong></a>    <a href="NestedRootTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
