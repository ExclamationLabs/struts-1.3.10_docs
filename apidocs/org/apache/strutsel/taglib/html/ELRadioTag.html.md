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
<td align="left"><a href="class-use/ELRadioTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELPasswordTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELRadioTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELRadioTag.html"><strong>FRAMES</strong></a>    <a href="ELRadioTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.RadioTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELRadioTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.RadioTag
                      org.apache.strutsel.taglib.html.md.ELRadioTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELRadioTag

extends [RadioTag](../../../../../org/apache/struts/taglib.html.md/RadioTag.html "class in org.apache.struts.taglib.html")

Tag for input fields of type "radio".

This class is a subclass of the class `org.apache.struts.taglib.html.md.RadioTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 479635 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELRadioTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.RadioTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[RadioTag](../../../../../org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` idName,  messages, name,  property, text, value`                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` accesskey,  doDisabled,  doReadonly,  indexed,  tabindex`                                                                                                                               |

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
| ` ELRadioTag()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getAccesskeyExpr()`
           Getter method for "accessKey" tag attribute.

` String`

` getAltExpr()`
           Getter method for "alt" tag attribute.

` String`

` getAltKeyExpr()`
           Getter method for "altKey" tag attribute.

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

` getErrorKeyExpr()`
           Getter method for "errorKey" tag attribute.

` String`

` getErrorStyleClassExpr()`
           Getter method for "errorStyleClass" tag attribute.

` String`

` getErrorStyleExpr()`
           Getter method for "errorStyle" tag attribute.

` String`

` getErrorStyleIdExpr()`
           Getter method for "errorStyleId" tag attribute.

` String`

` getIdNameExpr()`
           Getter method for "idName" tag attribute.

` String`

` getIndexedExpr()`
           Getter method for "indexed" tag attribute.

` String`

` getLangExpr()`
           Getter method for "lang" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getOnblurExpr()`
           Getter method for "onblur" tag attribute.

` String`

` getOnchangeExpr()`
           Getter method for "onchange" tag attribute.

` String`

` getOnclickExpr()`
           Getter method for "onclick" tag attribute.

` String`

` getOndblclickExpr()`
           Getter method for "ondblclick" tag attribute.

` String`

` getOnfocusExpr()`
           Getter method for "onfocus" tag attribute.

` String`

` getOnkeydownExpr()`
           Getter method for "onkeydown" tag attribute.

` String`

` getOnkeypressExpr()`
           Getter method for "onkeypress" tag attribute.

` String`

` getOnkeyupExpr()`
           Getter method for "onkeyup" tag attribute.

` String`

` getOnmousedownExpr()`
           Getter method for "onmousedown" tag attribute.

` String`

` getOnmousemoveExpr()`
           Getter method for "onmousemove" tag attribute.

` String`

` getOnmouseoutExpr()`
           Getter method for "onmouseout" tag attribute.

` String`

` getOnmouseoverExpr()`
           Getter method for "onmouseover" tag attribute.

` String`

` getOnmouseupExpr()`
           Getter method for "onmouseup" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

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

` getTabindexExpr()`
           Getter method for "tabindex" tag attribute.

` String`

` getTitleExpr()`
           Getter method for "title" tag attribute.

` String`

` getTitleKeyExpr()`
           Getter method for "titleKey" tag attribute.

` String`

` getValueExpr()`
           Getter method for "value" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setAccesskeyExpr(String accessKeyExpr)`
           Setter method for "accessKey" tag attribute.

` void`

` setAltExpr(String altExpr)`
           Setter method for "alt" tag attribute.

` void`

` setAltKeyExpr(String altKeyExpr)`
           Setter method for "altKey" tag attribute.

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

` setErrorKeyExpr(String errorKeyExpr)`
           Setter method for "errorKey" tag attribute.

` void`

` setErrorStyleClassExpr(String errorStyleClassExpr)`
           Setter method for "errorStyleClass" tag attribute.

` void`

` setErrorStyleExpr(String errorStyleExpr)`
           Setter method for "errorStyle" tag attribute.

` void`

` setErrorStyleIdExpr(String errorStyleIdExpr)`
           Setter method for "errorStyleId" tag attribute.

` void`

` setIdNameExpr(String idNameExpr)`
           Setter method for "idName" tag attribute.

` void`

` setIndexedExpr(String indexedExpr)`
           Setter method for "indexed" tag attribute.

` void`

` setLangExpr(String langExpr)`
           Setter method for "lang" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setOnblurExpr(String onblurExpr)`
           Setter method for "onblur" tag attribute.

` void`

` setOnchangeExpr(String onchangeExpr)`
           Setter method for "onchange" tag attribute.

` void`

` setOnclickExpr(String onclickExpr)`
           Setter method for "onclick" tag attribute.

` void`

` setOndblclickExpr(String ondblclickExpr)`
           Setter method for "ondblclick" tag attribute.

` void`

` setOnfocusExpr(String onfocusExpr)`
           Setter method for "onfocus" tag attribute.

` void`

` setOnkeydownExpr(String onkeydownExpr)`
           Setter method for "onkeydown" tag attribute.

` void`

` setOnkeypressExpr(String onkeypressExpr)`
           Setter method for "onkeypress" tag attribute.

` void`

` setOnkeyupExpr(String onkeyupExpr)`
           Setter method for "onkeyup" tag attribute.

` void`

` setOnmousedownExpr(String onmousedownExpr)`
           Setter method for "onmousedown" tag attribute.

` void`

` setOnmousemoveExpr(String onmousemoveExpr)`
           Setter method for "onmousemove" tag attribute.

` void`

` setOnmouseoutExpr(String onmouseoutExpr)`
           Setter method for "onmouseout" tag attribute.

` void`

` setOnmouseoverExpr(String onmouseoverExpr)`
           Setter method for "onmouseover" tag attribute.

` void`

` setOnmouseupExpr(String onmouseupExpr)`
           Setter method for "onmouseup" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

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

` setTabindexExpr(String tabindexExpr)`
           Setter method for "tabindex" tag attribute.

` void`

` setTitleExpr(String titleExpr)`
           Setter method for "title" tag attribute.

` void`

` setTitleKeyExpr(String titleKeyExpr)`
           Setter method for "titleKey" tag attribute.

` void`

` setValueExpr(String valueExpr)`
           Setter method for "value" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.RadioTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[RadioTag](../../../../../org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doAfterBody,  doEndTag,  getIdName,  getName,  getProperty,  getValue,  prepareName,  renderRadioElement,  setIdName,  setName,  setProperty,  setValue`                     |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doErrorsExist,  getAccesskey,  getAlt,  getAltKey,  getBundle,  getDir,  getDisabled,  getElementClose,  getErrorKey,  getErrorStyle,  getErrorStyleClass,  getErrorStyleId,  getIndexed,  getIndexValue,  getLang,  getLocale,  getOnblur,  getOnchange,  getOnclick,  getOndblclick,  getOnfocus,  getOnkeydown,  getOnkeypress,  getOnkeyup,  getOnmousedown,  getOnmousemove,  getOnmouseout,  getOnmouseover,  getOnmouseup,  getOnselect,  getReadonly,  getStyle,  getStyleClass,  getStyleId,  getTabindex,  getTitle,  getTitleKey,  is.html.md,  lookupProperty,  message,  prepareAttribute,  prepareEventHandlers,  prepareFocusEvents,  prepareIndex,  prepareInternationalization,  prepareKeyEvents,  prepareMouseEvents,  prepareOtherAttributes,  prepareStyles,  prepareTextEvents,  setAccesskey,  setAlt,  setAltKey,  setBundle,  setDir,  setDisabled,  setErrorKey,  setErrorStyle,  setErrorStyleClass,  setErrorStyleId,  setIndexed,  setLang,  setLocale,  setOnblur,  setOnchange,  setOnclick,  setOndblclick,  setOnfocus,  setOnkeydown,  setOnkeypress,  setOnkeyup,  setOnmousedown,  setOnmousemove,  setOnmouseout,  setOnmouseover,  setOnmouseup,  setOnselect,  setReadonly,  setStyle,  setStyleClass,  setStyleId,  setTabindex,  setTitle,  setTitleKey` |

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

### ELRadioTag

    public ELRadioTag()

<span id="method_detail"></span>

**Method Detail**

### getAccesskeyExpr

    public String getAccesskeyExpr()

Getter method for "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAltExpr

    public String getAltExpr()

Getter method for "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAltKeyExpr

    public String getAltKeyExpr()

Getter method for "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

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

### getErrorKeyExpr

    public String getErrorKeyExpr()

Getter method for "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getErrorStyleExpr

    public String getErrorStyleExpr()

Getter method for "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getErrorStyleClassExpr

    public String getErrorStyleClassExpr()

Getter method for "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getErrorStyleIdExpr

    public String getErrorStyleIdExpr()

Getter method for "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLangExpr

    public String getLangExpr()

Getter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getIdNameExpr

    public String getIdNameExpr()

Getter method for "idName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getIndexedExpr

    public String getIndexedExpr()

Getter method for "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnblurExpr

    public String getOnblurExpr()

Getter method for "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnchangeExpr

    public String getOnchangeExpr()

Getter method for "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnclickExpr

    public String getOnclickExpr()

Getter method for "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOndblclickExpr

    public String getOndblclickExpr()

Getter method for "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnfocusExpr

    public String getOnfocusExpr()

Getter method for "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnkeydownExpr

    public String getOnkeydownExpr()

Getter method for "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnkeypressExpr

    public String getOnkeypressExpr()

Getter method for "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnkeyupExpr

    public String getOnkeyupExpr()

Getter method for "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnmousedownExpr

    public String getOnmousedownExpr()

Getter method for "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnmousemoveExpr

    public String getOnmousemoveExpr()

Getter method for "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnmouseoutExpr

    public String getOnmouseoutExpr()

Getter method for "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnmouseoverExpr

    public String getOnmouseoverExpr()

Getter method for "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnmouseupExpr

    public String getOnmouseupExpr()

Getter method for "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getTabindexExpr

    public String getTabindexExpr()

Getter method for "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTitleExpr

    public String getTitleExpr()

Getter method for "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTitleKeyExpr

    public String getTitleKeyExpr()

Getter method for "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getValueExpr

    public String getValueExpr()

Getter method for "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAccesskeyExpr

    public void setAccesskeyExpr(String accessKeyExpr)

Setter method for "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAltExpr

    public void setAltExpr(String altExpr)

Setter method for "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAltKeyExpr

    public void setAltKeyExpr(String altKeyExpr)

Setter method for "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setErrorKeyExpr

    public void setErrorKeyExpr(String errorKeyExpr)

Setter method for "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setErrorStyleExpr

    public void setErrorStyleExpr(String errorStyleExpr)

Setter method for "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setErrorStyleClassExpr

    public void setErrorStyleClassExpr(String errorStyleClassExpr)

Setter method for "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setErrorStyleIdExpr

    public void setErrorStyleIdExpr(String errorStyleIdExpr)

Setter method for "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIdNameExpr

    public void setIdNameExpr(String idNameExpr)

Setter method for "idName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIndexedExpr

    public void setIndexedExpr(String indexedExpr)

Setter method for "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLangExpr

    public void setLangExpr(String langExpr)

Setter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnblurExpr

    public void setOnblurExpr(String onblurExpr)

Setter method for "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnchangeExpr

    public void setOnchangeExpr(String onchangeExpr)

Setter method for "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnclickExpr

    public void setOnclickExpr(String onclickExpr)

Setter method for "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOndblclickExpr

    public void setOndblclickExpr(String ondblclickExpr)

Setter method for "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnfocusExpr

    public void setOnfocusExpr(String onfocusExpr)

Setter method for "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnkeydownExpr

    public void setOnkeydownExpr(String onkeydownExpr)

Setter method for "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnkeypressExpr

    public void setOnkeypressExpr(String onkeypressExpr)

Setter method for "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnkeyupExpr

    public void setOnkeyupExpr(String onkeyupExpr)

Setter method for "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnmousedownExpr

    public void setOnmousedownExpr(String onmousedownExpr)

Setter method for "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnmousemoveExpr

    public void setOnmousemoveExpr(String onmousemoveExpr)

Setter method for "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnmouseoutExpr

    public void setOnmouseoutExpr(String onmouseoutExpr)

Setter method for "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnmouseoverExpr

    public void setOnmouseoverExpr(String onmouseoverExpr)

Setter method for "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnmouseupExpr

    public void setOnmouseupExpr(String onmouseupExpr)

Setter method for "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setTabindexExpr

    public void setTabindexExpr(String tabindexExpr)

Setter method for "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTitleExpr

    public void setTitleExpr(String titleExpr)

Setter method for "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTitleKeyExpr

    public void setTitleKeyExpr(String titleKeyExpr)

Setter method for "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

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
` release` in class `RadioTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
` doStartTag` in class `RadioTag`

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
<td align="left"><a href="class-use/ELRadioTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELPasswordTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELRadioTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELRadioTag.html"><strong>FRAMES</strong></a>    <a href="ELRadioTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.RadioTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
