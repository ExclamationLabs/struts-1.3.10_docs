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
<td align="left"><a href="class-use/ELImgTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELImageTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELImgTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELImgTag.html"><strong>FRAMES</strong></a>    <a href="ELImgTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.ImgTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELImgTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.ImgTag
                      org.apache.strutsel.taglib.html.md.ELImgTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELImgTag

extends [ImgTag](http://struts.apache.org/apidocs/org/apache/struts/taglib.html.md/ImgTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")

Generate an IMG tag to the specified image URI.

TODO:

-   make the **alt** and **src** settable from properties (for i18n)
-   handle **onLoad**, **onAbort**, and **onError** events (my JavaScript book is very old, there may be more unsupported events in the past couple of IE versions)

This class is a subclass of the class `org.apache.struts.taglib.html.md.ImgTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 479635 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELImgTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.ImgTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[ImgTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/ImgTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `action, align, border, height, hspace, imageName, ismap, messages, module, name, page, pageKey, paramId, paramName, paramProperty, paramScope, property, scope, src, srcKey, useLocalEncoding, usemap, vspace, width`    |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/BaseHandlerTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `accesskey, doDisabled, doReadonly, indexed, tabindex`                                                                                                                                                                                    |

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
| ` ELImgTag()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getActionExpr()`
           Getter method for "action" tag attribute.

` String`

` getAlignExpr()`
           Getter method for "align" tag attribute.

` String`

` getAltExpr()`
           Getter method for "alt" tag attribute.

` String`

` getAltKeyExpr()`
           Getter method for "altKey" tag attribute.

` String`

` getBorderExpr()`
           Getter method for "border" tag attribute.

` String`

` getBundleExpr()`
           Getter method for "bundle" tag attribute.

` String`

` getDirExpr()`
           Getter method for "dir" tag attribute.

` String`

` getHeightExpr()`
           Getter method for "height" tag attribute.

` String`

` getHspaceExpr()`
           Getter method for "hspace" tag attribute.

` String`

` getImageNameExpr()`
           Getter method for "imageName" tag attribute.

` String`

` getIsmapExpr()`
           Getter method for "ismap" tag attribute.

` String`

` getLangExpr()`
           Getter method for "lang" tag attribute.

` String`

` getLocaleExpr()`
           Getter method for "locale" tag attribute.

` String`

` getModuleExpr()`
           Getter method for "module" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getOnclickExpr()`
           Getter method for "onclick" tag attribute.

` String`

` getOndblclickExpr()`
           Getter method for "ondblclick" tag attribute.

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

` getPageExpr()`
           Getter method for "page" tag attribute.

` String`

` getPageKeyExpr()`
           Getter method for "pageKey" tag attribute.

` String`

` getParamIdExpr()`
           Getter method for "paramId" tag attribute.

` String`

` getParamNameExpr()`
           Getter method for "paramName" tag attribute.

` String`

` getParamPropertyExpr()`
           Getter method for "paramProperty" tag attribute.

` String`

` getParamScopeExpr()`
           Getter method for "paramScope" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

` String`

` getScopeExpr()`
           Getter method for "scope" tag attribute.

` String`

` getSrcExpr()`
           Getter method for "src" tag attribute.

` String`

` getSrcKeyExpr()`
           Getter method for "srcKey" tag attribute.

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

` getTitleExpr()`
           Getter method for "title" tag attribute.

` String`

` getTitleKeyExpr()`
           Getter method for "titleKey" tag attribute.

` String`

` getUseLocalEncodingExpr()`
           Getter method for "useLocalEncoding" tag attribute.

` String`

` getUsemapExpr()`
           Getter method for "usemap" tag attribute.

` String`

` getVspaceExpr()`
           Getter method for "vspace" tag attribute.

` String`

` getWidthExpr()`
           Getter method for "width" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setActionExpr(String actionExpr)`
           Setter method for "action" tag attribute.

` void`

` setAlignExpr(String alignExpr)`
           Setter method for "align" tag attribute.

` void`

` setAltExpr(String altExpr)`
           Setter method for "alt" tag attribute.

` void`

` setAltKeyExpr(String altKeyExpr)`
           Setter method for "altKey" tag attribute.

` void`

` setBorderExpr(String borderExpr)`
           Setter method for "border" tag attribute.

` void`

` setBundleExpr(String bundleExpr)`
           Setter method for "bundle" tag attribute.

` void`

` setDirExpr(String dirExpr)`
           Setter method for "dir" tag attribute.

` void`

` setHeightExpr(String heightExpr)`
           Setter method for "height" tag attribute.

` void`

` setHspaceExpr(String hspaceExpr)`
           Setter method for "hspace" tag attribute.

` void`

` setImageNameExpr(String imageNameExpr)`
           Setter method for "imageName" tag attribute.

` void`

` setIsmapExpr(String ismapExpr)`
           Setter method for "ismap" tag attribute.

` void`

` setLangExpr(String langExpr)`
           Setter method for "lang" tag attribute.

` void`

` setLocaleExpr(String localeExpr)`
           Setter method for "locale" tag attribute.

` void`

` setModuleExpr(String moduleExpr)`
           Setter method for "module" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setOnclickExpr(String onclickExpr)`
           Setter method for "onclick" tag attribute.

` void`

` setOndblclickExpr(String ondblclickExpr)`
           Setter method for "ondblclick" tag attribute.

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

` setPageExpr(String pageExpr)`
           Setter method for "page" tag attribute.

` void`

` setPageKeyExpr(String pageKeyExpr)`
           Setter method for "pageKey" tag attribute.

` void`

` setParamIdExpr(String paramIdExpr)`
           Setter method for "paramId" tag attribute.

` void`

` setParamNameExpr(String paramNameExpr)`
           Setter method for "paramName" tag attribute.

` void`

` setParamPropertyExpr(String paramPropertyExpr)`
           Setter method for "paramProperty" tag attribute.

` void`

` setParamScopeExpr(String paramScopeExpr)`
           Setter method for "paramScope" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

` void`

` setScopeExpr(String scopeExpr)`
           Setter method for "scope" tag attribute.

` void`

` setSrcExpr(String srcExpr)`
           Setter method for "src" tag attribute.

` void`

` setSrcKeyExpr(String srcKeyExpr)`
           Setter method for "srcKey" tag attribute.

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

` setTitleExpr(String titleExpr)`
           Setter method for "title" tag attribute.

` void`

` setTitleKeyExpr(String titleKeyExpr)`
           Setter method for "titleKey" tag attribute.

` void`

` setUseLocalEncodingExpr(String useLocalEncodingExpr)`
           Setter method for "useLocalEncoding" tag attribute.

` void`

` setUsemapExpr(String usemapExpr)`
           Setter method for "usemap" tag attribute.

` void`

` setVspaceExpr(String vspaceExpr)`
           Setter method for "vspace" tag attribute.

` void`

` setWidthExpr(String widthExpr)`
           Setter method for "width" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.ImgTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[ImgTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/ImgTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getAction, getAlign, getBorder, getHeight, getHspace, getImageName, getIsmap, getModule, getName, getPage, getPageKey, getParamId, getParamName, getParamProperty, getParamScope, getProperty, getScope, getSrc, getSrcKey, getUsemap, getVspace, getWidth, isUseLocalEncoding, setAction, setAlign, setBorder, setHeight, setHspace, setImageName, setIsmap, setModule, setName, setPage, setPageKey, setParamId, setParamName, setParamProperty, setParamScope, setProperty, setScope, setSrc, setSrcKey, setUseLocalEncoding, setUsemap, setVspace, setWidth, src, url` |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/BaseHandlerTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doErrorsExist, getAccesskey, getAlt, getAltKey, getBundle, getDir, getDisabled, getElementClose, getErrorKey, getErrorStyle, getErrorStyleClass, getErrorStyleId, getIndexed, getIndexValue, getLang, getLocale, getOnblur, getOnchange, getOnclick, getOndblclick, getOnfocus, getOnkeydown, getOnkeypress, getOnkeyup, getOnmousedown, getOnmousemove, getOnmouseout, getOnmouseover, getOnmouseup, getOnselect, getReadonly, getStyle, getStyleClass, getStyleId, getTabindex, getTitle, getTitleKey, is.html.md, lookupProperty, message, prepareAttribute, prepareEventHandlers, prepareFocusEvents, prepareIndex, prepareInternationalization, prepareKeyEvents, prepareMouseEvents, prepareName, prepareOtherAttributes, prepareStyles, prepareTextEvents, setAccesskey, setAlt, setAltKey, setBundle, setDir, setDisabled, setErrorKey, setErrorStyle, setErrorStyleClass, setErrorStyleId, setIndexed, setLang, setLocale, setOnblur, setOnchange, setOnclick, setOndblclick, setOnfocus, setOnkeydown, setOnkeypress, setOnkeyup, setOnmousedown, setOnmousemove, setOnmouseout, setOnmouseover, setOnmouseup, setOnselect, setReadonly, setStyle, setStyleClass, setStyleId, setTabindex, setTitle, setTitleKey` |

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

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Methods inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getParent, setPageContext, setParent`                                                                                                                                                                         |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELImgTag

    public ELImgTag()

<span id="method_detail"></span>

**Method Detail**

### getActionExpr

    public String getActionExpr()

Getter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getModuleExpr

    public String getModuleExpr()

Getter method for "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAlignExpr

    public String getAlignExpr()

Getter method for "align" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAltExpr

    public String getAltExpr()

Getter method for "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getAltKeyExpr

    public String getAltKeyExpr()

Getter method for "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBorderExpr

    public String getBorderExpr()

Getter method for "border" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBundleExpr

    public String getBundleExpr()

Getter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getDirExpr

    public String getDirExpr()

Getter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHeightExpr

    public String getHeightExpr()

Getter method for "height" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHspaceExpr

    public String getHspaceExpr()

Getter method for "hspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getImageNameExpr

    public String getImageNameExpr()

Getter method for "imageName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getIsmapExpr

    public String getIsmapExpr()

Getter method for "ismap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLangExpr

    public String getLangExpr()

Getter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLocaleExpr

    public String getLocaleExpr()

Getter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOnclickExpr

    public String getOnclickExpr()

Getter method for "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getOndblclickExpr

    public String getOndblclickExpr()

Getter method for "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getParamIdExpr

    public String getParamIdExpr()

Getter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageExpr

    public String getPageExpr()

Getter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageKeyExpr

    public String getPageKeyExpr()

Getter method for "pageKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamNameExpr

    public String getParamNameExpr()

Getter method for "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamPropertyExpr

    public String getParamPropertyExpr()

Getter method for "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamScopeExpr

    public String getParamScopeExpr()

Getter method for "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getScopeExpr

    public String getScopeExpr()

Getter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getSrcExpr

    public String getSrcExpr()

Getter method for "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getSrcKeyExpr

    public String getSrcKeyExpr()

Getter method for "srcKey" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getTitleExpr

    public String getTitleExpr()

Getter method for "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getTitleKeyExpr

    public String getTitleKeyExpr()

Getter method for "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getUseLocalEncodingExpr

    public String getUseLocalEncodingExpr()

Getter method for "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getUsemapExpr

    public String getUsemapExpr()

Getter method for "usemap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getVspaceExpr

    public String getVspaceExpr()

Getter method for "vspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getWidthExpr

    public String getWidthExpr()

Getter method for "width" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setActionExpr

    public void setActionExpr(String actionExpr)

Setter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setModuleExpr

    public void setModuleExpr(String moduleExpr)

Setter method for "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAlignExpr

    public void setAlignExpr(String alignExpr)

Setter method for "align" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAltExpr

    public void setAltExpr(String altExpr)

Setter method for "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAltKeyExpr

    public void setAltKeyExpr(String altKeyExpr)

Setter method for "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBorderExpr

    public void setBorderExpr(String borderExpr)

Setter method for "border" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBundleExpr

    public void setBundleExpr(String bundleExpr)

Setter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setDirExpr

    public void setDirExpr(String dirExpr)

Setter method for "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHeightExpr

    public void setHeightExpr(String heightExpr)

Setter method for "height" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHspaceExpr

    public void setHspaceExpr(String hspaceExpr)

Setter method for "hspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setImageNameExpr

    public void setImageNameExpr(String imageNameExpr)

Setter method for "imageName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setIsmapExpr

    public void setIsmapExpr(String ismapExpr)

Setter method for "ismap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLangExpr

    public void setLangExpr(String langExpr)

Setter method for "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLocaleExpr

    public void setLocaleExpr(String localeExpr)

Setter method for "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOnclickExpr

    public void setOnclickExpr(String onclickExpr)

Setter method for "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setOndblclickExpr

    public void setOndblclickExpr(String ondblclickExpr)

Setter method for "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setParamIdExpr

    public void setParamIdExpr(String paramIdExpr)

Setter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageExpr

    public void setPageExpr(String pageExpr)

Setter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageKeyExpr

    public void setPageKeyExpr(String pageKeyExpr)

Setter method for "pageKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamNameExpr

    public void setParamNameExpr(String paramNameExpr)

Setter method for "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamPropertyExpr

    public void setParamPropertyExpr(String paramPropertyExpr)

Setter method for "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamScopeExpr

    public void setParamScopeExpr(String paramScopeExpr)

Setter method for "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setScopeExpr

    public void setScopeExpr(String scopeExpr)

Setter method for "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setSrcExpr

    public void setSrcExpr(String srcExpr)

Setter method for "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setSrcKeyExpr

    public void setSrcKeyExpr(String srcKeyExpr)

Setter method for "srcKey" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setTitleExpr

    public void setTitleExpr(String titleExpr)

Setter method for "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setTitleKeyExpr

    public void setTitleKeyExpr(String titleKeyExpr)

Setter method for "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setUseLocalEncodingExpr

    public void setUseLocalEncodingExpr(String useLocalEncodingExpr)

Setter method for "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setUsemapExpr

    public void setUsemapExpr(String usemapExpr)

Setter method for "usemap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setVspaceExpr

    public void setVspaceExpr(String vspaceExpr)

Setter method for "vspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setWidthExpr

    public void setWidthExpr(String widthExpr)

Setter method for "width" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `ImgTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `ImgTag`

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
<td align="left"><a href="class-use/ELImgTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELImageTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELImgTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELImgTag.html"><strong>FRAMES</strong></a>    <a href="ELImgTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.ImgTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
