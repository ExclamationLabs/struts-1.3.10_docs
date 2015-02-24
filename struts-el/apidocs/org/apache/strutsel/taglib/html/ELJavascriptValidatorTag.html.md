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
<td align="left"><a href="class-use/ELJavascriptValidatorTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELImgTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELJavascriptValidatorTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELJavascriptValidatorTag.html"><strong>FRAMES</strong></a>    <a href="ELJavascriptValidatorTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.JavascriptValidatorTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELJavascriptValidatorTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.JavascriptValidatorTag
                  org.apache.strutsel.taglib.html.md.ELJavascriptValidatorTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELJavascriptValidatorTag

extends [JavascriptValidatorTag](http://struts.apache.org/apidocs/org/apache/struts/taglib.html.md/JavascriptValidatorTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")

Custom tag that generates JavaScript for client side validation based on the validation rules loaded by the `ValidatorPlugIn` defined in the struts-config.xml file.

This class is a subclass of the class `org.apache.struts.taglib.html.md.JavascriptValidatorTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELJavascriptValidatorTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.JavascriptValidatorTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[JavascriptValidatorTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/JavascriptValidatorTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bundle, cdata, dynamicJavascript, formName, HTML_BEGIN_COMMENT, HTML_END_COMMENT,.html.mdComment, jsFormName, lineEnd, methodName, page, scriptLanguage, src, staticJavascript`                                                                             |

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

| **Constructor Summary**       |
|-------------------------------|
| ` ELJavascriptValidatorTag()` 
                                |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getBundleExpr()`
           Getter method for "bundle" tag attribute.

` String`

` getCdataExpr()`
           Getter method for "cdata" tag attribute.

` String`

` getDynamicJavascriptExpr()`
           Getter method for "dynamicJavascript" tag attribute.

` String`

` getFormNameExpr()`
           Getter method for "formName" tag attribute.

` String`

` getHtmlCommentExpr()`
           Getter method for .html.mdComment" tag attribute.

` String`

` getMethodExpr()`
           Getter method for "method" tag attribute.

` String`

` getPageExpr()`
           Getter method for "page" tag attribute.

` String`

` getScriptLanguageExpr()`
           Getter method for "scriptLanguage" tag attribute.

` String`

` getSrcExpr()`
           Getter method for "src" tag attribute.

` String`

` getStaticJavascriptExpr()`
           Getter method for "staticJavascript" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setBundleExpr(String bundleExpr)`
           Setter method for "bundle" tag attribute.

` void`

` setCdataExpr(String cdataExpr)`
           Setter method for "cdata" tag attribute.

` void`

` setDynamicJavascriptExpr(String dynamicJavascriptExpr)`
           Setter method for "dynamicJavascript" tag attribute.

` void`

` setFormNameExpr(String formNameExpr)`
           Setter method for "formName" tag attribute.

` void`

` setHtmlCommentExpr(String�.html.mdCommentExpr)`
           Setter method for .html.mdComment" tag attribute.

` void`

` setMethodExpr(String methodExpr)`
           Setter method for "method" tag attribute.

` void`

` setPageExpr(String pageExpr)`
           Setter method for "page" tag attribute.

` void`

` setScriptLanguageExpr(String scriptLanguageExpr)`
           Setter method for "scriptLanguage" tag attribute.

` void`

` setSrcExpr(String srcExpr)`
           Setter method for "src" tag attribute.

` void`

` setStaticJavascriptExpr(String staticJavascriptExpr)`
           Setter method for "staticJavascript" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.JavascriptValidatorTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[JavascriptValidatorTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/JavascriptValidatorTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getBundle, getCdata, getDynamicJavascript, getFormName, getHtmlComment, getJavascriptBegin, getJavascriptEnd, getJavascriptStaticMethods, getJsFormName, getMethod, getPage, getScriptLanguage, getSrc, getStaticJavascript, renderJavascript, renderStartElement, setBundle, setCdata, setDynamicJavascript, setFormName, setHtmlComment, setJsFormName, setMethod, setPage, setScriptLanguage, setSrc, setStaticJavascript` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                              |

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

### ELJavascriptValidatorTag

    public ELJavascriptValidatorTag()

<span id="method_detail"></span>

**Method Detail**

### getCdataExpr

    public String getCdataExpr()

Getter method for "cdata" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDynamicJavascriptExpr

    public String getDynamicJavascriptExpr()

Getter method for "dynamicJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFormNameExpr

    public String getFormNameExpr()

Getter method for "formName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMethodExpr

    public String getMethodExpr()

Getter method for "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageExpr

    public String getPageExpr()

Getter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScriptLanguageExpr

    public String getScriptLanguageExpr()

Getter method for "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getSrcExpr

    public String getSrcExpr()

Getter method for "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getStaticJavascriptExpr

    public String getStaticJavascriptExpr()

Getter method for "staticJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHtmlCommentExpr

    public String getHtmlCommentExpr()

Getter method for .html.mdComment" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBundleExpr

    public String getBundleExpr()

Getter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setCdataExpr

    public void setCdataExpr(String cdataExpr)

Setter method for "cdata" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDynamicJavascriptExpr

    public void setDynamicJavascriptExpr(String dynamicJavascriptExpr)

Setter method for "dynamicJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFormNameExpr

    public void setFormNameExpr(String formNameExpr)

Setter method for "formName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMethodExpr

    public void setMethodExpr(String methodExpr)

Setter method for "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageExpr

    public void setPageExpr(String pageExpr)

Setter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScriptLanguageExpr

    public void setScriptLanguageExpr(String scriptLanguageExpr)

Setter method for "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setSrcExpr

    public void setSrcExpr(String srcExpr)

Setter method for "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setStaticJavascriptExpr

    public void setStaticJavascriptExpr(String staticJavascriptExpr)

Setter method for "staticJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHtmlCommentExpr

    public void setHtmlCommentExpr(String.html.mdCommentExpr)

Setter method for .html.mdComment" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBundleExpr

    public void setBundleExpr(String bundleExpr)

Setter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `JavascriptValidatorTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `JavascriptValidatorTag`

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
<td align="left"><a href="class-use/ELJavascriptValidatorTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELImgTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELJavascriptValidatorTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELJavascriptValidatorTag.html"><strong>FRAMES</strong></a>    <a href="ELJavascriptValidatorTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.JavascriptValidatorTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
