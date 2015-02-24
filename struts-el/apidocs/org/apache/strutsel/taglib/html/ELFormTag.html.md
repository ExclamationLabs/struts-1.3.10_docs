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
<td align="left"><a href="class-use/ELFormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELFileTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELFormTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELFormTag.html"><strong>FRAMES</strong></a>    <a href="ELFormTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.FormTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELFormTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.html.md.FormTag
              org.apache.strutsel.taglib.html.md.ELFormTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELFormTag

extends [FormTag](http://struts.apache.org/apidocs/org/apache/struts/taglib.html.md/FormTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")

Custom tag that represents an input form, associated with a bean whose properties correspond to the various fields of the form.

This class is a subclass of the class `org.apache.struts.taglib.html.md.FormTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 479635 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELFormTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.FormTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[FormTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/FormTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `acceptCharset, action, beanName, beanScope, beanType, enctype, focus, focusIndex, lineEnd, mapping, messages, method, moduleConfig, onreset, onsubmit, readonly, scriptLanguage, servlet, style, styleClass, styleId, target` |

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
| ` ELFormTag()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getAcceptCharsetExpr()`
           Getter method for "acceptCharset" tag attribute.

` String`

` getActionExpr()`
           Getter method for "action" tag attribute.

` String`

` getDirExpr()`
           Getter method for "dir" tag attribute.

` String`

` getDisabledExpr()`
           Getter method for "disabled" tag attribute.

` String`

` getEnctypeExpr()`
           Getter method for "enctype" tag attribute.

` String`

` getFocusExpr()`
           Getter method for "focus" tag attribute.

` String`

` getFocusIndexExpr()`
           Getter method for "focusIndex" tag attribute.

` String`

` getLangExpr()`
           Getter method for "lang" tag attribute.

` String`

` getMethodExpr()`
           Getter method for "method" tag attribute.

` String`

` getOnresetExpr()`
           Getter method for "onreset" tag attribute.

` String`

` getOnsubmitExpr()`
           Getter method for "onsubmit" tag attribute.

` String`

` getReadonlyExpr()`
           Getter method for "readonly" tag attribute.

` String`

` getScriptLanguageExpr()`
           Getter method for "scriptLanguage" tag attribute.

` String`

` getStyleClassExpr()`
           Getter method for "styleClass" tag attribute.

` String`

` getStyleExpr()`
           Getter method for "style" tag attribute.

` String`

` getStyleIdExpr()`
           Getter method for "styleId" tag attribute.

` String`

` getTargetExpr()`
           Getter method for "target" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setAcceptCharsetExpr(String acceptCharsetExpr)`
           Setter method for "acceptCharset" tag attribute.

` void`

` setActionExpr(String actionExpr)`
           Setter method for "action" tag attribute.

` void`

` setDirExpr(String dirExpr)`
           Setter method for "dir" tag attribute.

` void`

` setDisabledExpr(String disabledExpr)`
           Setter method for "disabled" tag attribute.

` void`

` setEnctypeExpr(String enctypeExpr)`
           Setter method for "enctype" tag attribute.

` void`

` setFocusExpr(String focusExpr)`
           Setter method for "focus" tag attribute.

` void`

` setFocusIndexExpr(String focusIndexExpr)`
           Setter method for "focusIndex" tag attribute.

` void`

` setLangExpr(String langExpr)`
           Setter method for "lang" tag attribute.

` void`

` setMethodExpr(String methodExpr)`
           Setter method for "method" tag attribute.

` void`

` setOnresetExpr(String onresetExpr)`
           Setter method for "onreset" tag attribute.

` void`

` setOnsubmitExpr(String onsubmitExpr)`
           Setter method for "onsubmit" tag attribute.

` void`

` setReadonlyExpr(String readonlyExpr)`
           Setter method for "readonly" tag attribute.

` void`

` setScriptLanguageExpr(String scriptLanguageExpr)`
           Setter method for "scriptLanguage" tag attribute.

` void`

` setStyleClassExpr(String styleClassExpr)`
           Setter method for "styleClass" tag attribute.

` void`

` setStyleExpr(String styleExpr)`
           Setter method for "style" tag attribute.

` void`

` setStyleIdExpr(String styleIdExpr)`
           Setter method for "styleId" tag attribute.

` void`

` setTargetExpr(String targetExpr)`
           Setter method for "target" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.FormTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[FormTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/FormTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getAcceptCharset, getAction, getAutocomplete, getBeanName, getDir, getEnctype, getFocus, getFocusIndex, getLang, getMethod, getOnreset, getOnsubmit, getScriptLanguage, getStyle, getStyleClass, getStyleId, getTarget, initFormBean, isDisabled, isReadonly, lookup, renderAction, renderAttribute, renderFocusJavascript, renderFormStartElement, renderName, renderOtherAttributes, renderToken, setAcceptCharset, setAction, setAutocomplete, setDir, setDisabled, setEnctype, setFocus, setFocusIndex, setLang, setMethod, setOnreset, setOnsubmit, setReadonly, setScriptLanguage, setStyle, setStyleClass, setStyleId, setTarget` |

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

### ELFormTag

    public ELFormTag()

<span id="method_detail"></span>

**Method Detail**

### getActionExpr

    public String getActionExpr()

Getter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDirExpr

    public String getDirExpr()

Getter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDisabledExpr

    public String getDisabledExpr()

Getter method for "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getEnctypeExpr

    public String getEnctypeExpr()

Getter method for "enctype" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFocusExpr

    public String getFocusExpr()

Getter method for "focus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFocusIndexExpr

    public String getFocusIndexExpr()

Getter method for "focusIndex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLangExpr

    public String getLangExpr()

Getter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMethodExpr

    public String getMethodExpr()

Getter method for "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnresetExpr

    public String getOnresetExpr()

Getter method for "onreset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnsubmitExpr

    public String getOnsubmitExpr()

Getter method for "onsubmit" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getReadonlyExpr

    public String getReadonlyExpr()

Getter method for "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScriptLanguageExpr

    public String getScriptLanguageExpr()

Getter method for "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getStyleExpr

    public String getStyleExpr()

Getter method for "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getStyleClassExpr

    public String getStyleClassExpr()

Getter method for "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getStyleIdExpr

    public String getStyleIdExpr()

Getter method for "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTargetExpr

    public String getTargetExpr()

Getter method for "target" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAcceptCharsetExpr

    public String getAcceptCharsetExpr()

Getter method for "acceptCharset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setActionExpr

    public void setActionExpr(String actionExpr)

Setter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDirExpr

    public void setDirExpr(String dirExpr)

Setter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDisabledExpr

    public void setDisabledExpr(String disabledExpr)

Setter method for "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setEnctypeExpr

    public void setEnctypeExpr(String enctypeExpr)

Setter method for "enctype" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFocusExpr

    public void setFocusExpr(String focusExpr)

Setter method for "focus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFocusIndexExpr

    public void setFocusIndexExpr(String focusIndexExpr)

Setter method for "focusIndex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLangExpr

    public void setLangExpr(String langExpr)

Setter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMethodExpr

    public void setMethodExpr(String methodExpr)

Setter method for "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnresetExpr

    public void setOnresetExpr(String onresetExpr)

Setter method for "onreset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnsubmitExpr

    public void setOnsubmitExpr(String onsubmitExpr)

Setter method for "onsubmit" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setReadonlyExpr

    public void setReadonlyExpr(String readonlyExpr)

Setter method for "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScriptLanguageExpr

    public void setScriptLanguageExpr(String scriptLanguageExpr)

Setter method for "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setStyleExpr

    public void setStyleExpr(String styleExpr)

Setter method for "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setStyleClassExpr

    public void setStyleClassExpr(String styleClassExpr)

Setter method for "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setStyleIdExpr

    public void setStyleIdExpr(String styleIdExpr)

Setter method for "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTargetExpr

    public void setTargetExpr(String targetExpr)

Setter method for "target" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAcceptCharsetExpr

    public void setAcceptCharsetExpr(String acceptCharsetExpr)

Setter method for "acceptCharset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `FormTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `FormTag`

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
<td align="left"><a href="class-use/ELFormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELFileTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELFormTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELFormTag.html"><strong>FRAMES</strong></a>    <a href="ELFormTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.FormTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
