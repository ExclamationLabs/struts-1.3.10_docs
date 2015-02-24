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
<td align="left"><a href="class-use/ELFrameTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELFormTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELFrameTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELFrameTag.html"><strong>FRAMES</strong></a>    <a href="ELFrameTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.FrameTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.html.md
 Class ELFrameTag
-------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.LinkTag
                      org.apache.struts.taglib.html.md.FrameTag
                          org.apache.strutsel.taglib.html.md.ELFrameTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELFrameTag

extends [FrameTag](http://struts.apache.org/apidocs/org/apache/struts/taglib.html.md/FrameTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")

Generate an HTML `<frame>` tag with similar capabilities as those the `.html.md:link>` tag provides for hyperlink elements. The `src` element is rendered using the same technique that [`LinkTag`](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/LinkTag.html?is-external=true "class or interface in org.apache.struts.taglib.html") uses to render the `href` attribute of a hyperlink. Additionally, the HTML 4.0 frame tag attributes `noresize`, `scrolling`, `marginheight`, `marginwidth`, `frameborder`, and `longdesc` are supported. The frame `name` attribute is rendered based on the `frameName` property.

Note that the value of `longdesc` is intended to be a URI, but currently no rewriting is supported. The attribute is set directly from the property value.

This class is a subclass of the class `org.apache.struts.taglib.html.md.FrameTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.html.ELFrameTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.FrameTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[FrameTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/FrameTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `frameborder, frameName, longdesc, marginheight, marginwidth, noresize, scrolling`                                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.LinkTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[LinkTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/LinkTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `action, anchor, forward, href, indexId, linkName, messages, module, name, page, parameters, paramId, paramName, paramProperty, paramScope, property, scope, target, text, transaction, useLocalEncoding`                   |

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
| ` ELFrameTag()`         
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

` getAnchorExpr()`
           Getter method for "anchor" tag attribute.

` String`

` getBundleExpr()`
           Getter method for "bundle" tag attribute.

` String`

` getForwardExpr()`
           Getter method for "forward" tag attribute.

` String`

` getFrameborderExpr()`
           Getter method for "frameborder" tag attribute.

` String`

` getFrameNameExpr()`
           Getter method for "frameName" tag attribute.

` String`

` getHrefExpr()`
           Getter method for "href" tag attribute.

` String`

` getLongdescExpr()`
           Getter method for "longdesc" tag attribute.

` String`

` getMarginheightExpr()`
           Getter method for "marginheight" tag attribute.

` String`

` getMarginwidthExpr()`
           Getter method for "marginwidth" tag attribute.

` String`

` getModuleExpr()`
           Getter method for "module" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getNoresizeExpr()`
           Getter method for "noresize" tag attribute.

` String`

` getPageExpr()`
           Getter method for "page" tag attribute.

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

` getScrollingExpr()`
           Getter method for "scrolling" tag attribute.

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

` getTransactionExpr()`
           Getter method for "transaction" tag attribute.

` void`

` release()`
           Resets attribute values for tag reuse.

` void`

` setActionExpr(String actionExpr)`
           Setter method for "action" tag attribute.

` void`

` setAnchorExpr(String anchorExpr)`
           Setter method for "anchor" tag attribute.

` void`

` setBundleExpr(String bundleExpr)`
           Setter method for "bundle" tag attribute.

` void`

` setForwardExpr(String forwardExpr)`
           Setter method for "forward" tag attribute.

` void`

` setFrameborderExpr(String frameborderExpr)`
           Setter method for "frameborder" tag attribute.

` void`

` setFrameNameExpr(String frameNameExpr)`
           Setter method for "frameName" tag attribute.

` void`

` setHrefExpr(String hrefExpr)`
           Setter method for "href" tag attribute.

` void`

` setLongdescExpr(String longdescExpr)`
           Setter method for "longdesc" tag attribute.

` void`

` setMarginheightExpr(String marginheightExpr)`
           Setter method for "marginheight" tag attribute.

` void`

` setMarginwidthExpr(String marginwidthExpr)`
           Setter method for "marginwidth" tag attribute.

` void`

` setModuleExpr(String moduleExpr)`
           Setter method for "module" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setNoresizeExpr(String noresizeExpr)`
           Setter method for "noresize" tag attribute.

` void`

` setPageExpr(String pageExpr)`
           Setter method for "page" tag attribute.

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

` setScrollingExpr(String scrollingExpr)`
           Setter method for "scrolling" tag attribute.

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

` setTransactionExpr(String transactionExpr)`
           Setter method for "transaction" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.FrameTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[FrameTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/FrameTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getFrameborder, getFrameName, getLongdesc, getMarginheight, getMarginwidth, getNoresize, getScrolling, setFrameborder, setFrameName, setLongdesc, setMarginheight, setMarginwidth, setNoresize, setScrolling`       |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.LinkTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[LinkTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/LinkTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addParameter, calculateURL, doAfterBody, getAction, getAnchor, getForward, getHref, getIndexId, getLinkName, getModule, getName, getPage, getParamId, getParamName, getParamProperty, getParamScope, getProperty, getScope, getTarget, getTransaction, isUseLocalEncoding, setAction, setAnchor, setForward, setHref, setIndexId, setLinkName, setModule, setName, setPage, setParamId, setParamName, setParamProperty, setParamScope, setProperty, setScope, setTarget, setTransaction, setUseLocalEncoding` |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/html/BaseHandlerTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doErrorsExist, getAccesskey, getAlt, getAltKey, getBundle, getDir, getDisabled, getElementClose, getErrorKey, getErrorStyle, getErrorStyleClass, getErrorStyleId, getIndexed, getIndexValue, getLang, getLocale, getOnblur, getOnchange, getOnclick, getOndblclick, getOnfocus, getOnkeydown, getOnkeypress, getOnkeyup, getOnmousedown, getOnmousemove, getOnmouseout, getOnmouseover, getOnmouseup, getOnselect, getReadonly, getStyle, getStyleClass, getStyleId, getTabindex, getTitle, getTitleKey, is.html.md, lookupProperty, message, prepareAttribute, prepareEventHandlers, prepareFocusEvents, prepareIndex, prepareInternationalization, prepareKeyEvents, prepareMouseEvents, prepareName, prepareOtherAttributes, prepareStyles, prepareTextEvents, setAccesskey, setAlt, setAltKey, setBundle, setDir, setDisabled, setErrorKey, setErrorStyle, setErrorStyleClass, setErrorStyleId, setIndexed, setLang, setLocale, setOnblur, setOnchange, setOnclick, setOndblclick, setOnfocus, setOnkeydown, setOnkeypress, setOnkeyup, setOnmousedown, setOnmousemove, setOnmouseout, setOnmouseover, setOnmouseup, setOnselect, setReadonly, setStyle, setStyleClass, setStyleId, setTabindex, setTitle, setTitleKey` |

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

### ELFrameTag

    public ELFrameTag()

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

### getAnchorExpr

    public String getAnchorExpr()

Getter method for "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getBundleExpr

    public String getBundleExpr()

Getter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getForwardExpr

    public String getForwardExpr()

Getter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFrameborderExpr

    public String getFrameborderExpr()

Getter method for "frameborder" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getFrameNameExpr

    public String getFrameNameExpr()

Getter method for "frameName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getHrefExpr

    public String getHrefExpr()

Getter method for "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getLongdescExpr

    public String getLongdescExpr()

Getter method for "longdesc" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMarginheightExpr

    public String getMarginheightExpr()

Getter method for "marginheight" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMarginwidthExpr

    public String getMarginwidthExpr()

Getter method for "marginwidth" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getNoresizeExpr

    public String getNoresizeExpr()

Getter method for "noresize" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPageExpr

    public String getPageExpr()

Getter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getParamIdExpr

    public String getParamIdExpr()

Getter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getScrollingExpr

    public String getScrollingExpr()

Getter method for "scrolling" tag attribute. (Mapping set in associated BeanInfo class.)

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

### getTransactionExpr

    public String getTransactionExpr()

Getter method for "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setActionExpr

    public void setActionExpr(String actionExpr)

Setter method for "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setModuleExpr

    public void setModuleExpr(String moduleExpr)

Setter method for "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setAnchorExpr

    public void setAnchorExpr(String anchorExpr)

Setter method for "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setBundleExpr

    public void setBundleExpr(String bundleExpr)

Setter method for "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setForwardExpr

    public void setForwardExpr(String forwardExpr)

Setter method for "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFrameborderExpr

    public void setFrameborderExpr(String frameborderExpr)

Setter method for "frameborder" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setFrameNameExpr

    public void setFrameNameExpr(String frameNameExpr)

Setter method for "frameName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setHrefExpr

    public void setHrefExpr(String hrefExpr)

Setter method for "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setLongdescExpr

    public void setLongdescExpr(String longdescExpr)

Setter method for "longdesc" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMarginheightExpr

    public void setMarginheightExpr(String marginheightExpr)

Setter method for "marginheight" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMarginwidthExpr

    public void setMarginwidthExpr(String marginwidthExpr)

Setter method for "marginwidth" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNoresizeExpr

    public void setNoresizeExpr(String noresizeExpr)

Setter method for "noresize" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPageExpr

    public void setPageExpr(String pageExpr)

Setter method for "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setParamIdExpr

    public void setParamIdExpr(String paramIdExpr)

Setter method for "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setScrollingExpr

    public void setScrollingExpr(String scrollingExpr)

Setter method for "scrolling" tag attribute. (Mapping set in associated BeanInfo class.)

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

### setTransactionExpr

    public void setTransactionExpr(String transactionExpr)

Setter method for "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Resets attribute values for tag reuse.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `FrameTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `LinkTag`

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
<td align="left"><a href="class-use/ELFrameTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/ELFormTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/ELFrameTagBeanInfo.html" title="class in org.apache.strutsel.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/html/ELFrameTag.html"><strong>FRAMES</strong></a>    <a href="ELFrameTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.html.md.FrameTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
