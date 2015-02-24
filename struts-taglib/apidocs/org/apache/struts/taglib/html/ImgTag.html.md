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
<td align="left"><a href="class-use/ImgTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/ImageTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/JavascriptValidatorTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/ImgTag.html"><strong>FRAMES</strong></a>    <a href="ImgTag.html"><strong>NO FRAMES</strong></a>    
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
 Class ImgTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.ImgTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedImgTag](../../../../../org/apache/struts/taglib/nested.html.md/NestedImgTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class ImgTag

extends [BaseHandlerTag](../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html "class in org.apache.struts.taglib.html")

Generate an IMG tag to the specified image URI.

TODO:

-   Make the **alt** and **src** settable from properties (for i18n)

**Version:**  
$Rev: 552353 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.ImgTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`action`
           The module-relative action (beginning with a slash) which will be used as the source for this image.

`protected  String`

`align`
           The property to specify where to align the image.

`protected  String`

`border`
           The border size around the image.

`protected  String`

`height`
           The image height.

`protected  String`

`hspace`
           The horizontal spacing around the image.

`protected  String`

` imageName`
           The image name for named images.

`protected  String`

`ismap`
           Server-side image map declaration.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

`module`
           The module prefix (beginning with a slash) which will be used to find the action for this link.

`protected  String`

`name`
           The JSP bean name for query parameters.

`protected  String`

`page`
           The module-relative path, starting with a slash character, of the image to be displayed by this rendered tag.

`protected  String`

`pageKey`
           The message resources key under which we should look up the `page` attribute for this generated tag, if any.

`protected  String`

`paramId`
           In situations where an image is dynamically generated (such as to create a chart graph), this specifies the single-parameter request parameter name to generate.

`protected  String`

` paramName`
           The single-parameter JSP bean name.

`protected  String`

` paramProperty`
           The single-parameter JSP bean property.

`protected  String`

` paramScope`
           The single-parameter JSP bean scope.

`protected  String`

` property`
           The JSP bean property name for query parameters.

`protected  String`

`scope`
           The scope of the bean specified by the name property, if any.

`protected  String`

`src`
           The image source URI.

`protected  String`

`srcKey`
           The message resources key under which we should look up the `src` attribute for this generated tag, if any.

`protected  boolean`

` useLocalEncoding`
            

`protected  String`

`usemap`
           Client-side image map declaration.

`protected  String`

`vspace`
           The vertical spacing around the image.

`protected  String`

`width`
           The image width.

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
| ` ImgTag()`             
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Render the end of the IMG tag.

` int`

` doStartTag()`
           Render the beginning of the IMG tag.

` String`

` getAction()`
            

` String`

` getAlign()`
            

` String`

` getBorder()`
            

` String`

` getHeight()`
            

` String`

` getHspace()`
            

` String`

` getImageName()`
            

` String`

` getIsmap()`
            

` String`

` getModule()`
            

` String`

` getName()`
            

` String`

` getPage()`
            

` String`

` getPageKey()`
            

` String`

` getParamId()`
            

` String`

` getParamName()`
            

` String`

` getParamProperty()`
            

` String`

` getParamScope()`
            

` String`

` getProperty()`
            

` String`

` getScope()`
            

` String`

` getSrc()`
            

` String`

` getSrcKey()`
            

` String`

` getUsemap()`
            

` String`

` getVspace()`
            

` String`

` getWidth()`
            

` boolean`

` isUseLocalEncoding()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setAction(String action)`
            

` void`

` setAlign(String align)`
            

` void`

` setBorder(String border)`
            

` void`

` setHeight(String height)`
            

` void`

` setHspace(String hspace)`
            

` void`

` setImageName(String imageName)`
            

` void`

` setIsmap(String ismap)`
            

` void`

` setModule(String module)`
            

` void`

` setName(String name)`
            

` void`

` setPage(String page)`
            

` void`

` setPageKey(String pageKey)`
            

` void`

` setParamId(String paramId)`
            

` void`

` setParamName(String paramName)`
            

` void`

` setParamProperty(String paramProperty)`
            

` void`

` setParamScope(String paramScope)`
            

` void`

` setProperty(String property)`
            

` void`

` setScope(String scope)`
            

` void`

` setSrc(String src)`
            

` void`

` setSrcKey(String srcKey)`
            

` void`

` setUseLocalEncoding(boolean b)`
            

` void`

` setUsemap(String usemap)`
            

` void`

` setVspace(String vspace)`
            

` void`

` setWidth(String width)`
            

`protected  String`

`src()`
           Return the base source URL that will be rendered in the `src` property for this generated element, or `null` if there is no such URL.

`protected  String`

` url(String url)`
           Return the specified src URL, modified as necessary with optional request parameters.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doErrorsExist,  getAccesskey,  getAlt,  getAltKey,  getBundle,  getDir,  getDisabled,  getElementClose,  getErrorKey,  getErrorStyle,  getErrorStyleClass,  getErrorStyleId,  getIndexed,  getIndexValue,  getLang,  getLocale,  getOnblur,  getOnchange,  getOnclick,  getOndblclick,  getOnfocus,  getOnkeydown,  getOnkeypress,  getOnkeyup,  getOnmousedown,  getOnmousemove,  getOnmouseout,  getOnmouseover,  getOnmouseup,  getOnselect,  getReadonly,  getStyle,  getStyleClass,  getStyleId,  getTabindex,  getTitle,  getTitleKey,  is.html.md,  lookupProperty,  message,  prepareAttribute,  prepareEventHandlers,  prepareFocusEvents,  prepareIndex,  prepareInternationalization,  prepareKeyEvents,  prepareMouseEvents,  prepareName,  prepareOtherAttributes,  prepareStyles,  prepareTextEvents,  setAccesskey,  setAlt,  setAltKey,  setBundle,  setDir,  setDisabled,  setErrorKey,  setErrorStyle,  setErrorStyleClass,  setErrorStyleId,  setIndexed,  setLang,  setLocale,  setOnblur,  setOnchange,  setOnclick,  setOndblclick,  setOnfocus,  setOnkeydown,  setOnkeypress,  setOnkeyup,  setOnmousedown,  setOnmousemove,  setOnmouseout,  setOnmouseover,  setOnmouseup,  setOnselect,  setReadonly,  setStyle,  setStyleClass,  setStyleId,  setTabindex,  setTitle,  setTitleKey` |

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

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="align"></span>

### align

    protected String align

The property to specify where to align the image.

------------------------------------------------------------------------

<span id="border"></span>

### border

    protected String border

The border size around the image.

------------------------------------------------------------------------

<span id="height"></span>

### height

    protected String height

The image height.

------------------------------------------------------------------------

<span id="hspace"></span>

### hspace

    protected String hspace

The horizontal spacing around the image.

------------------------------------------------------------------------

<span id="imageName"></span>

### imageName

    protected String imageName

The image name for named images.

------------------------------------------------------------------------

<span id="ismap"></span>

### ismap

    protected String ismap

Server-side image map declaration.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

The module-relative path, starting with a slash character, of the image to be displayed by this rendered tag.

------------------------------------------------------------------------

<span id="pageKey"></span>

### pageKey

    protected String pageKey

The message resources key under which we should look up the `page` attribute for this generated tag, if any.

------------------------------------------------------------------------

<span id="action"></span>

### action

    protected String action

The module-relative action (beginning with a slash) which will be used as the source for this image.

------------------------------------------------------------------------

<span id="module"></span>

### module

    protected String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

<span id="paramId"></span>

### paramId

    protected String paramId

In situations where an image is dynamically generated (such as to create a chart graph), this specifies the single-parameter request parameter name to generate.

------------------------------------------------------------------------

<span id="paramName"></span>

### paramName

    protected String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

<span id="paramProperty"></span>

### paramProperty

    protected String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

<span id="paramScope"></span>

### paramScope

    protected String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

<span id="src"></span>

### src

    protected String src

The image source URI.

------------------------------------------------------------------------

<span id="srcKey"></span>

### srcKey

    protected String srcKey

The message resources key under which we should look up the `src` attribute for this generated tag, if any.

------------------------------------------------------------------------

<span id="usemap"></span>

### usemap

    protected String usemap

Client-side image map declaration.

------------------------------------------------------------------------

<span id="vspace"></span>

### vspace

    protected String vspace

The vertical spacing around the image.

------------------------------------------------------------------------

<span id="width"></span>

### width

    protected String width

The image width.

------------------------------------------------------------------------

<span id="useLocalEncoding"></span>

### useLocalEncoding

    protected boolean useLocalEncoding

<span id="constructor_detail"></span>

**Constructor Detail**

### ImgTag

    public ImgTag()

<span id="method_detail"></span>

**Method Detail**

### getAlign

    public String getAlign()

------------------------------------------------------------------------

### setAlign

    public void setAlign(String align)

------------------------------------------------------------------------

### getBorder

    public String getBorder()

------------------------------------------------------------------------

### setBorder

    public void setBorder(String border)

------------------------------------------------------------------------

### getHeight

    public String getHeight()

------------------------------------------------------------------------

### setHeight

    public void setHeight(String height)

------------------------------------------------------------------------

### getHspace

    public String getHspace()

------------------------------------------------------------------------

### setHspace

    public void setHspace(String hspace)

------------------------------------------------------------------------

### getImageName

    public String getImageName()

------------------------------------------------------------------------

### setImageName

    public void setImageName(String imageName)

------------------------------------------------------------------------

### getIsmap

    public String getIsmap()

------------------------------------------------------------------------

### setIsmap

    public void setIsmap(String ismap)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getPage

    public String getPage()

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

------------------------------------------------------------------------

### getPageKey

    public String getPageKey()

------------------------------------------------------------------------

### setPageKey

    public void setPageKey(String pageKey)

------------------------------------------------------------------------

### getAction

    public String getAction()

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

------------------------------------------------------------------------

### getModule

    public String getModule()

------------------------------------------------------------------------

### setModule

    public void setModule(String module)

------------------------------------------------------------------------

### getParamId

    public String getParamId()

------------------------------------------------------------------------

### setParamId

    public void setParamId(String paramId)

------------------------------------------------------------------------

### getParamName

    public String getParamName()

------------------------------------------------------------------------

### setParamName

    public void setParamName(String paramName)

------------------------------------------------------------------------

### getParamProperty

    public String getParamProperty()

------------------------------------------------------------------------

### setParamProperty

    public void setParamProperty(String paramProperty)

------------------------------------------------------------------------

### getParamScope

    public String getParamScope()

------------------------------------------------------------------------

### setParamScope

    public void setParamScope(String paramScope)

------------------------------------------------------------------------

### getProperty

    public String getProperty()

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

------------------------------------------------------------------------

### getScope

    public String getScope()

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

------------------------------------------------------------------------

### getSrc

    public String getSrc()

------------------------------------------------------------------------

### setSrc

    public void setSrc(String src)

------------------------------------------------------------------------

### getSrcKey

    public String getSrcKey()

------------------------------------------------------------------------

### setSrcKey

    public void setSrcKey(String srcKey)

------------------------------------------------------------------------

### getUsemap

    public String getUsemap()

------------------------------------------------------------------------

### setUsemap

    public void setUsemap(String usemap)

------------------------------------------------------------------------

### getVspace

    public String getVspace()

------------------------------------------------------------------------

### setVspace

    public void setVspace(String vspace)

------------------------------------------------------------------------

### getWidth

    public String getWidth()

------------------------------------------------------------------------

### setWidth

    public void setWidth(String width)

------------------------------------------------------------------------

### isUseLocalEncoding

    public boolean isUseLocalEncoding()

------------------------------------------------------------------------

### setUseLocalEncoding

    public void setUseLocalEncoding(boolean b)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Render the beginning of the IMG tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Render the end of the IMG tag.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

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
` release` in class `BaseHandlerTag`

------------------------------------------------------------------------

### src

    protected String src()
                  throws JspException

Return the base source URL that will be rendered in the `src` property for this generated element, or `null` if there is no such URL.

**Throws:**  
`JspException` - if an error occurs

------------------------------------------------------------------------

### url

    protected String url(String url)
                  throws JspException

Return the specified src URL, modified as necessary with optional request parameters.

**Parameters:**  
`url` - The URL to be modified (or null if this url will not be used)

**Throws:**  
`JspException` - if an error occurs preparing the URL

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
<td align="left"><a href="class-use/ImgTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/ImageTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/JavascriptValidatorTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/ImgTag.html"><strong>FRAMES</strong></a>    <a href="ImgTag.html"><strong>NO FRAMES</strong></a>    
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
