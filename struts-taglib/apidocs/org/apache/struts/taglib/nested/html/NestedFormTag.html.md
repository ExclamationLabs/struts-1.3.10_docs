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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedFormTag.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested.html.md/NestedFileTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/html/NestedHiddenTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/html/NestedFormTag.html"><strong>FRAMES</strong></a>    <a href="NestedFormTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested.html.md
 Class NestedFormTag
------------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.html.md.FormTag
              org.apache.struts.taglib.nested.html.md.NestedFormTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested"), [NestedPropertySupport](../../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html "interface in org.apache.struts.taglib.nested"), [NestedTagSupport](../../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html "interface in org.apache.struts.taglib.nested")

------------------------------------------------------------------------

    public class NestedFormTag

extends [FormTag](../../../../../../org/apache/struts/taglib.html.md/FormTag.html "class in org.apache.struts.taglib.html")

implements [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")

NestedFormTag.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../../serialized-form.html.md#org.apache.struts.taglib.nested.html.NestedFormTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` name`
           The name

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.FormTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[FormTag](../../../../../../org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html")**                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` acceptCharset,  action,  beanName,  beanScope,  beanType,  enctype,  focus,  focusIndex,  lineEnd,  mapping,  messages,  method,  moduleConfig,  onreset,  onsubmit,  readonly,  scriptLanguage,  servlet,  style,  styleClass,  styleId,  target` |

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
| ` NestedFormTag()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           This is only overriden to clean up the include reference

` int`

` doStartTag()`
           Overriding to allow the chance to set the details of the system, so that dynamic includes can be possible

` String`

` getName()`
           Return the name.

` String`

` getProperty()`
           Get the string value of the "property" property.

` void`

` release()`
           Release the tag's resources and reset the values.

` void`

` setName(String name)`
           Set the name.

` void`

` setProperty(String newProperty)`
           Setter for the "property" property

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.FormTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[FormTag](../../../../../../org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getAcceptCharset,  getAction,  getAutocomplete,  getBeanName,  getDir,  getEnctype,  getFocus,  getFocusIndex,  getLang,  getMethod,  getOnreset,  getOnsubmit,  getScriptLanguage,  getStyle,  getStyleClass,  getStyleId,  getTarget,  initFormBean,  isDisabled,  isReadonly,  lookup,  renderAction,  renderAttribute,  renderFocusJavascript,  renderFormStartElement,  renderName,  renderOtherAttributes,  renderToken,  setAcceptCharset,  setAction,  setAutocomplete,  setDir,  setDisabled,  setEnctype,  setFocus,  setFocusIndex,  setLang,  setMethod,  setOnreset,  setOnsubmit,  setReadonly,  setScriptLanguage,  setStyle,  setStyleClass,  setStyleId,  setTarget` |

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

<span id="name"></span>

### name

    protected String name

The name

<span id="constructor_detail"></span>

**Constructor Detail**

### NestedFormTag

    public NestedFormTag()

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

Return the name.

**Specified by:**  
` getName` in interface `NestedNameSupport`

<!-- -->

**Returns:**  
String value of the tags' name property

------------------------------------------------------------------------

### setName

    public void setName(String name)

Set the name.

**Specified by:**  
` setName` in interface `NestedNameSupport`

<!-- -->

**Parameters:**  
`name` - The new name

------------------------------------------------------------------------

### getProperty

    public String getProperty()

Get the string value of the "property" property.

**Specified by:**  
` getProperty` in interface `NestedPropertySupport`

<!-- -->

**Returns:**  
the property property

------------------------------------------------------------------------

### setProperty

    public void setProperty(String newProperty)

Setter for the "property" property

**Specified by:**  
` setProperty` in interface `NestedPropertySupport`

<!-- -->

**Parameters:**  
`newProperty` - new value for the property

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Overriding to allow the chance to set the details of the system, so that dynamic includes can be possible

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `FormTag`

<!-- -->

**Returns:**  
int JSP continuation directive.

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

This is only overriden to clean up the include reference

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
` doEndTag` in class `FormTag`

<!-- -->

**Returns:**  
int JSP continuation directive.

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### release

    public void release()

Release the tag's resources and reset the values.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `FormTag`

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedFormTag.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested.html.md/NestedFileTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/html/NestedHiddenTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/html/NestedFormTag.html"><strong>FRAMES</strong></a>    <a href="NestedFormTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
