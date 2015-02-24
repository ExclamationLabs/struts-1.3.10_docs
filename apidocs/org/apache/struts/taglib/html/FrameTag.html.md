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
<td align="left"><a href="class-use/FrameTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/FormTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/HiddenTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/FrameTag.html"><strong>FRAMES</strong></a>    <a href="FrameTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.taglib.html.md
 Class FrameTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.LinkTag
                      org.apache.struts.taglib.html.md.FrameTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELFrameTag](../../../../../org/apache/strutsel/taglib.html.md/ELFrameTag.html "class in org.apache.strutsel.taglib.html")

------------------------------------------------------------------------

    public class FrameTag

extends [LinkTag](../../../../../org/apache/struts/taglib.html.md/LinkTag.html "class in org.apache.struts.taglib.html")

Generate an HTML `<frame>` tag with similar capabilities as those the `.html.md:link>` tag provides for hyperlink elements. The `src` element is rendered using the same technique that [`LinkTag`](../../../../../org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") uses to render the `href` attribute of a hyperlink. Additionall, the HTML 4.0 frame tag attributes `noresize`, `scrolling`, `marginheight`, `marginwidth`, `frameborder`, and `longdesc` are supported. The frame `name` attribute is rendered based on the `frameName` property. Note that the value of `longdesc` is intended to be a URI, but currently no rewriting is supported. The attribute is set directly from the property value.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.FrameTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` frameborder`
           The frameborder attribute that should be rendered (1, 0).

`protected  String`

` frameName`
           The `name` attribute that should be rendered for this frame.

`protected  String`

` longdesc`
           URI of a long description of this frame (complements title).

`protected  Integer`

` marginheight`
           The margin height in pixels, or zero for no setting.

`protected  Integer`

` marginwidth`
           The margin width in pixels, or null for no setting.

`protected  boolean`

` noresize`
           Should users be disallowed to resize the frame?

`protected  String`

` scrolling`
           What type of scrolling should be supported (yes, no, auto)?

 <span id="fields_inherited_from_class_org.apache.struts.taglib.html.md.LinkTag"></span>

| **Fields inherited from class org.apache.struts.taglib.html.md.[LinkTag](../../../../../org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html")**                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `action, anchor,  forward, href,  indexId,  linkName,  messages, module, name, page,  parameters,  paramId,  paramName,  paramProperty,  paramScope,  property, scope, target, text,  transaction,  useLocalEncoding` |

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
| ` FrameTag()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Render the appropriately encoded URI.

` String`

` getFrameborder()`
            

` String`

` getFrameName()`
            

` String`

` getLongdesc()`
            

` Integer`

` getMarginheight()`
            

` Integer`

` getMarginwidth()`
            

` boolean`

` getNoresize()`
            

` String`

` getScrolling()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setFrameborder(String frameborder)`
            

` void`

` setFrameName(String frameName)`
            

` void`

` setLongdesc(String longdesc)`
            

` void`

` setMarginheight(Integer marginheight)`
            

` void`

` setMarginwidth(Integer marginwidth)`
            

` void`

` setNoresize(boolean noresize)`
            

` void`

` setScrolling(String scrolling)`
            

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.LinkTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[LinkTag](../../../../../org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addParameter,  calculateURL,  doAfterBody,  doStartTag,  getAction,  getAnchor,  getForward,  getHref,  getIndexId,  getLinkName,  getModule,  getName,  getPage,  getParamId,  getParamName,  getParamProperty,  getParamScope,  getProperty,  getScope,  getTarget,  getTransaction,  isUseLocalEncoding,  setAction,  setAnchor,  setForward,  setHref,  setIndexId,  setLinkName,  setModule,  setName,  setPage,  setParamId,  setParamName,  setParamProperty,  setParamScope,  setProperty,  setScope,  setTarget,  setTransaction,  setUseLocalEncoding` |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doErrorsExist,  getAccesskey,  getAlt,  getAltKey,  getBundle,  getDir,  getDisabled,  getElementClose,  getErrorKey,  getErrorStyle,  getErrorStyleClass,  getErrorStyleId,  getIndexed,  getIndexValue,  getLang,  getLocale,  getOnblur,  getOnchange,  getOnclick,  getOndblclick,  getOnfocus,  getOnkeydown,  getOnkeypress,  getOnkeyup,  getOnmousedown,  getOnmousemove,  getOnmouseout,  getOnmouseover,  getOnmouseup,  getOnselect,  getReadonly,  getStyle,  getStyleClass,  getStyleId,  getTabindex,  getTitle,  getTitleKey,  is.html.md,  lookupProperty,  message,  prepareAttribute,  prepareEventHandlers,  prepareFocusEvents,  prepareIndex,  prepareInternationalization,  prepareKeyEvents,  prepareMouseEvents,  prepareName,  prepareOtherAttributes,  prepareStyles,  prepareTextEvents,  setAccesskey,  setAlt,  setAltKey,  setBundle,  setDir,  setDisabled,  setErrorKey,  setErrorStyle,  setErrorStyleClass,  setErrorStyleId,  setIndexed,  setLang,  setLocale,  setOnblur,  setOnchange,  setOnclick,  setOndblclick,  setOnfocus,  setOnkeydown,  setOnkeypress,  setOnkeyup,  setOnmousedown,  setOnmousemove,  setOnmouseout,  setOnmouseover,  setOnmouseup,  setOnselect,  setReadonly,  setStyle,  setStyleClass,  setStyleId,  setTabindex,  setTitle,  setTitleKey` |

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

 

<span id="field_detail"></span>

**Field Detail**

<span id="frameborder"></span>

### frameborder

    protected String frameborder

The frameborder attribute that should be rendered (1, 0).

------------------------------------------------------------------------

<span id="frameName"></span>

### frameName

    protected String frameName

The `name` attribute that should be rendered for this frame.

------------------------------------------------------------------------

<span id="longdesc"></span>

### longdesc

    protected String longdesc

URI of a long description of this frame (complements title).

------------------------------------------------------------------------

<span id="marginheight"></span>

### marginheight

    protected Integer marginheight

The margin height in pixels, or zero for no setting.

------------------------------------------------------------------------

<span id="marginwidth"></span>

### marginwidth

    protected Integer marginwidth

The margin width in pixels, or null for no setting.

------------------------------------------------------------------------

<span id="noresize"></span>

### noresize

    protected boolean noresize

Should users be disallowed to resize the frame?

------------------------------------------------------------------------

<span id="scrolling"></span>

### scrolling

    protected String scrolling

What type of scrolling should be supported (yes, no, auto)?

<span id="constructor_detail"></span>

**Constructor Detail**

### FrameTag

    public FrameTag()

<span id="method_detail"></span>

**Method Detail**

### getFrameborder

    public String getFrameborder()

------------------------------------------------------------------------

### setFrameborder

    public void setFrameborder(String frameborder)

------------------------------------------------------------------------

### getFrameName

    public String getFrameName()

------------------------------------------------------------------------

### setFrameName

    public void setFrameName(String frameName)

------------------------------------------------------------------------

### getLongdesc

    public String getLongdesc()

------------------------------------------------------------------------

### setLongdesc

    public void setLongdesc(String longdesc)

------------------------------------------------------------------------

### getMarginheight

    public Integer getMarginheight()

------------------------------------------------------------------------

### setMarginheight

    public void setMarginheight(Integer marginheight)

------------------------------------------------------------------------

### getMarginwidth

    public Integer getMarginwidth()

------------------------------------------------------------------------

### setMarginwidth

    public void setMarginwidth(Integer marginwidth)

------------------------------------------------------------------------

### getNoresize

    public boolean getNoresize()

------------------------------------------------------------------------

### setNoresize

    public void setNoresize(boolean noresize)

------------------------------------------------------------------------

### getScrolling

    public String getScrolling()

------------------------------------------------------------------------

### setScrolling

    public void setScrolling(String scrolling)

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Render the appropriately encoded URI.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
` doEndTag` in class `LinkTag`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `LinkTag`

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
<td align="left"><a href="class-use/FrameTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/FormTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/HiddenTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/FrameTag.html"><strong>FRAMES</strong></a>    <a href="FrameTag.html"><strong>NO FRAMES</strong></a>    
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
