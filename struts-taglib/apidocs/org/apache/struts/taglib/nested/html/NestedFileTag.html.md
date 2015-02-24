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
<td align="left"><a href="class-use/NestedFileTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested.html.md/NestedErrorsTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/html/NestedFormTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/html/NestedFileTag.html"><strong>FRAMES</strong></a>    <a href="NestedFileTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseFieldTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested.html.md
 Class NestedFileTag
------------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.BaseInputTag
                      org.apache.struts.taglib.html.md.BaseFieldTag
                          org.apache.struts.taglib.html.md.FileTag
                              org.apache.struts.taglib.nested.html.md.NestedFileTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested"), [NestedPropertySupport](../../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html "interface in org.apache.struts.taglib.nested"), [NestedTagSupport](../../../../../../org/apache/struts/taglib/nested/NestedTagSupport.html "interface in org.apache.struts.taglib.nested")

------------------------------------------------------------------------

    public class NestedFileTag

extends [FileTag](../../../../../../org/apache/struts/taglib.html.md/FileTag.html "class in org.apache.struts.taglib.html")

implements [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")

NestedFileTag.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../../serialized-form.html.md#org.apache.struts.taglib.nested.html.NestedFileTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseFieldTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[BaseFieldTag](../../../../../../org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` accept,  redisplay,  type`                                                                                                                                                             |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseInputTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[BaseInputTag](../../../../../../org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cols,  maxlength,  messages,  name,  property,  rows,  value`                                                                                                                          |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` accesskey,  doDisabled,  doReadonly,  indexed,  tabindex`                                                                                                                                  |

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
| ` NestedFileTag()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Complete the processing of the tag.

` int`

` doStartTag()`
           Overriding method of the heart of the matter.

` void`

` release()`
           Release the tag's resources and reset the values.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseFieldTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseFieldTag](../../../../../../org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` formatValue,  getAccept,  getRedisplay,  prepareValue,  renderInputElement,  setAccept,  setRedisplay`                                                                                  |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseInputTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseInputTag](../../../../../../org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html")**                          |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getAutocomplete,  getCols,  getMaxlength,  getName,  getProperty,  getRows,  getSize,  getValue,  prepareName,  setAutocomplete,  setCols,  setMaxlength,  setName,  setProperty,  setRows,  setSize,  setValue` |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doErrorsExist,  getAccesskey,  getAlt,  getAltKey,  getBundle,  getDir,  getDisabled,  getElementClose,  getErrorKey,  getErrorStyle,  getErrorStyleClass,  getErrorStyleId,  getIndexed,  getIndexValue,  getLang,  getLocale,  getOnblur,  getOnchange,  getOnclick,  getOndblclick,  getOnfocus,  getOnkeydown,  getOnkeypress,  getOnkeyup,  getOnmousedown,  getOnmousemove,  getOnmouseout,  getOnmouseover,  getOnmouseup,  getOnselect,  getReadonly,  getStyle,  getStyleClass,  getStyleId,  getTabindex,  getTitle,  getTitleKey,  is.html.md,  lookupProperty,  message,  prepareAttribute,  prepareEventHandlers,  prepareFocusEvents,  prepareIndex,  prepareInternationalization,  prepareKeyEvents,  prepareMouseEvents,  prepareOtherAttributes,  prepareStyles,  prepareTextEvents,  setAccesskey,  setAlt,  setAltKey,  setBundle,  setDir,  setDisabled,  setErrorKey,  setErrorStyle,  setErrorStyleClass,  setErrorStyleId,  setIndexed,  setLang,  setLocale,  setOnblur,  setOnchange,  setOnclick,  setOndblclick,  setOnfocus,  setOnkeydown,  setOnkeypress,  setOnkeyup,  setOnmousedown,  setOnmousemove,  setOnmouseout,  setOnmouseover,  setOnmouseup,  setOnselect,  setReadonly,  setStyle,  setStyleClass,  setStyleId,  setTabindex,  setTitle,  setTitleKey` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                                        |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                                  |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.nested.NestedNameSupport"></span>

| **Methods inherited from interface org.apache.struts.taglib.nested.[NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getName,  setName`                                                                                                                                                                                              |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.nested.NestedPropertySupport"></span>

| **Methods inherited from interface org.apache.struts.taglib.nested.[NestedPropertySupport](../../../../../../org/apache/struts/taglib/nested/NestedPropertySupport.html.md "interface in org.apache.struts.taglib.nested")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getProperty,  setProperty`                                                                                                                                                                                              |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Methods inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getParent, setPageContext, setParent`                                                                                                                                                                         |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### NestedFileTag

    public NestedFileTag()

<span id="method_detail"></span>

**Method Detail**

### doStartTag

    public int doStartTag()
                   throws JspException

Overriding method of the heart of the matter. Gets the relative property and leaves the rest up to the original tag implementation. Sweet.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `BaseFieldTag`

<!-- -->

**Returns:**  
int JSP continuation directive. This is in the hands of the super class.

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Complete the processing of the tag. The nested tags here will restore all the original value for the tag itself and the nesting context.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
` doEndTag` in class `BaseInputTag`

<!-- -->

**Returns:**  
int to describe the next step for the JSP processor

**Throws:**  
`JspException` - for the bad things JSP's do

------------------------------------------------------------------------

### release

    public void release()

Release the tag's resources and reset the values.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `BaseFieldTag`

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
<td align="left"><a href="class-use/NestedFileTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested.html.md/NestedErrorsTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/html/NestedFormTag.html" title="class in org.apache.struts.taglib.nested.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/html/NestedFileTag.html"><strong>FRAMES</strong></a>    <a href="NestedFileTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseFieldTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
