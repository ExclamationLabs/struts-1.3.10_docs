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
<td align="left"><a href="class-use/ELOptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELOptionsTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELOptionTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELOptionTag.html"><strong>FRAMES</strong></a>    <a href="ELOptionTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.OptionTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELOptionTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.OptionTag
                  org.apache.strutsel.taglib.html.md.ELOptionTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELOptionTag

extends [OptionTag](../../../../../org/apache/struts/taglib.html.md/OptionTag.html "class in org.apache.struts.taglib.html")

Tag for select options. The body of this tag is presented to the user in the option list, while the value attribute is the value returned to the server if this option is selected.

This class is a subclass of the class `org.apache.struts.taglib.html.md.OptionTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 479635 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELOptionTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.OptionTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[OptionTag](../../../../../org/apache/struts/taglib/html/OptionTag.html "class in org.apache.struts.taglib.html")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` bundle,  disabled,  filter, key,  locale,  messages,  styleId, text,  value`                                                                                                  |

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
| ` ELOptionTag()`        
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

` getDirExpr()`
           Getter method for "dir" tag attribute.

` String`

` getDisabledExpr()`
           Getter method for "disabled" tag attribute.

` String`

` getFilterExpr()`
           Getter method for "filter" tag attribute.

` String`

` getKeyExpr()`
           Getter method for "key" tag attribute.

` String`

` getLangExpr()`
           Getter method for "lang" tag attribute.

` String`

` getLocaleExpr()`
           Getter method for "locale" tag attribute.

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

` getValueExpr()`
           Getter method for "value" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setBundleExpr(String bundleExpr)`
           Setter method for "bundle" tag attribute.

` void`

` setDirExpr(String dirExpr)`
           Setter method for "dir" tag attribute.

` void`

` setDisabledExpr(String disabledExpr)`
           Setter method for "disabled" tag attribute.

` void`

` setFilterExpr(String filterExpr)`
           Setter method for "filter" tag attribute.

` void`

` setKeyExpr(String keyExpr)`
           Setter method for "key" tag attribute.

` void`

` setLangExpr(String langExpr)`
           Setter method for "lang" tag attribute.

` void`

` setLocaleExpr(String localeExpr)`
           Setter method for "locale" tag attribute.

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

` setValueExpr(String valueExpr)`
           Setter method for "value" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.OptionTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[OptionTag](../../../../../org/apache/struts/taglib/html/OptionTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                         |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doAfterBody,  doEndTag,  getBundle,  getDir,  getDisabled,  getFilter,  getKey,  getLang,  getLocale,  getStyle,  getStyleClass,  getStyleId,  getValue,  renderOptionElement,  setBundle,  setDir,  setDisabled,  setFilter,  setKey,  setLang,  setLocale,  setStyle,  setStyleClass,  setStyleId,  setValue,  text` |

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

### ELOptionTag

    public ELOptionTag()

<span id="method_detail"></span>

**Method Detail**

### getBundleExpr

    public String getBundleExpr()

Getter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDirExpr

    public String getDirExpr()

Getter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDisabledExpr

    public String getDisabledExpr()

Getter method for "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFilterExpr

    public String getFilterExpr()

Getter method for "filter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLangExpr

    public String getLangExpr()

Getter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getKeyExpr

    public String getKeyExpr()

Getter method for "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLocaleExpr

    public String getLocaleExpr()

Getter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getValueExpr

    public String getValueExpr()

Getter method for "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBundleExpr

    public void setBundleExpr(String bundleExpr)

Setter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDirExpr

    public void setDirExpr(String dirExpr)

Setter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDisabledExpr

    public void setDisabledExpr(String disabledExpr)

Setter method for "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFilterExpr

    public void setFilterExpr(String filterExpr)

Setter method for "filter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setKeyExpr

    public void setKeyExpr(String keyExpr)

Setter method for "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLangExpr

    public void setLangExpr(String langExpr)

Setter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLocaleExpr

    public void setLocaleExpr(String localeExpr)

Setter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setValueExpr

    public void setValueExpr(String valueExpr)

Setter method for "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `OptionTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `OptionTag`

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
<td align="left"><a href="class-use/ELOptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELOptionsTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELOptionTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELOptionTag.html"><strong>FRAMES</strong></a>    <a href="ELOptionTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.OptionTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
