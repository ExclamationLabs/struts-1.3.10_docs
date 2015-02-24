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
<td align="left"><a href="class-use/LinkTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/JavascriptValidatorTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/MessagesTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/LinkTag.html"><strong>FRAMES</strong></a>    <a href="LinkTag.html"><strong>NO FRAMES</strong></a>    
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
 Class LinkTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.LinkTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELLinkTag](../../../../../org/apache/strutsel/taglib.html.md/ELLinkTag.html "class in org.apache.strutsel.taglib.html"), [FrameTag](../../../../../org/apache/struts/taglib/html/FrameTag.html "class in org.apache.struts.taglib.html"), [NestedLinkTag](../../../../../org/apache/struts/taglib/nested/html/NestedLinkTag.html "class in org.apache.struts.taglib.nested.html"), [RewriteTag](../../../../../org/apache/struts/taglib/html/RewriteTag.html "class in org.apache.struts.taglib.html")

------------------------------------------------------------------------

    public class LinkTag

extends [BaseHandlerTag](../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html "class in org.apache.struts.taglib.html")

Generate a URL-encoded hyperlink to the specified URI.

**Version:**  
$Rev: 519563 $ $Date: 2005-04-06 02:37:00 -0400 (Wed, 06 Apr 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.LinkTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`action`
           The module-relative action (beginning with a slash) which will be called by this link

`protected  String`

`anchor`
           The anchor to be added to the end of the generated hyperlink.

`protected  String`

` forward`
           The logical forward name from which to retrieve the hyperlink URI.

`protected  String`

`href`
           The hyperlink URI.

`protected  String`

` indexId`
           Name of parameter to generate to hold index number

`protected  String`

` linkName`
           The link name for named links.

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
           The module-relative page URL (beginning with a slash) to which this hyperlink will be rendered.

`protected  Map`

` parameters`
           Additional parameters included programatically.

`protected  String`

` paramId`
           The single-parameter request parameter name to generate.

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

`target`
           The window target.

`protected  String`

`text`
           The body content of this tag (if any).

`protected  boolean`

` transaction`
           Include transaction token (if any) in the hyperlink?

`protected  boolean`

` useLocalEncoding`
            

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
| ` LinkTag()`            
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addParameter(String paramName, Object paramValue)`
           Adds a parameter to this link.

`protected  String`

` calculateURL()`
           Return the complete URL to which this hyperlink will direct the user.

` int`

` doAfterBody()`
           Save the associated label from the body content.

` int`

` doEndTag()`
           Render the end of the hyperlink.

` int`

` doStartTag()`
           Render the beginning of the hyperlink.

` String`

` getAction()`
            

` String`

` getAnchor()`
            

` String`

` getForward()`
            

` String`

` getHref()`
            

` String`

` getIndexId()`
            

` String`

` getLinkName()`
            

` String`

` getModule()`
            

` String`

` getName()`
            

` String`

` getPage()`
            

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

` getTarget()`
            

` boolean`

` getTransaction()`
            

` boolean`

` isUseLocalEncoding()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setAction(String action)`
            

` void`

` setAnchor(String anchor)`
            

` void`

` setForward(String forward)`
            

` void`

` setHref(String href)`
            

` void`

` setIndexId(String indexId)`
            

` void`

` setLinkName(String linkName)`
            

` void`

` setModule(String module)`
            

` void`

` setName(String name)`
            

` void`

` setPage(String page)`
            

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

` setTarget(String target)`
            

` void`

` setTransaction(boolean transaction)`
            

` void`

` setUseLocalEncoding(boolean b)`
            

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

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="text"></span>

### text

    protected String text

The body content of this tag (if any).

------------------------------------------------------------------------

<span id="anchor"></span>

### anchor

    protected String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

<span id="forward"></span>

### forward

    protected String forward

The logical forward name from which to retrieve the hyperlink URI.

Usage note: If a forward config is used in a hyperlink, and a module is specified, the path must lead to another action and not directly to a page. This is in keeping with rule that in a modular application all links must be to an action rather than a page.

------------------------------------------------------------------------

<span id="href"></span>

### href

    protected String href

The hyperlink URI.

------------------------------------------------------------------------

<span id="linkName"></span>

### linkName

    protected String linkName

The link name for named links.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

The module-relative page URL (beginning with a slash) to which this hyperlink will be rendered.

------------------------------------------------------------------------

<span id="action"></span>

### action

    protected String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

<span id="module"></span>

### module

    protected String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

<span id="paramId"></span>

### paramId

    protected String paramId

The single-parameter request parameter name to generate.

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

<span id="target"></span>

### target

    protected String target

The window target.

------------------------------------------------------------------------

<span id="transaction"></span>

### transaction

    protected boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

<span id="parameters"></span>

### parameters

    protected Map parameters

Additional parameters included programatically.

------------------------------------------------------------------------

<span id="indexId"></span>

### indexId

    protected String indexId

Name of parameter to generate to hold index number

------------------------------------------------------------------------

<span id="useLocalEncoding"></span>

### useLocalEncoding

    protected boolean useLocalEncoding

<span id="constructor_detail"></span>

**Constructor Detail**

### LinkTag

    public LinkTag()

<span id="method_detail"></span>

**Method Detail**

### getAnchor

    public String getAnchor()

------------------------------------------------------------------------

### setAnchor

    public void setAnchor(String anchor)

------------------------------------------------------------------------

### getForward

    public String getForward()

------------------------------------------------------------------------

### setForward

    public void setForward(String forward)

------------------------------------------------------------------------

### getHref

    public String getHref()

------------------------------------------------------------------------

### setHref

    public void setHref(String href)

------------------------------------------------------------------------

### getLinkName

    public String getLinkName()

------------------------------------------------------------------------

### setLinkName

    public void setLinkName(String linkName)

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

### getTarget

    public String getTarget()

------------------------------------------------------------------------

### setTarget

    public void setTarget(String target)

------------------------------------------------------------------------

### getTransaction

    public boolean getTransaction()

------------------------------------------------------------------------

### setTransaction

    public void setTransaction(boolean transaction)

------------------------------------------------------------------------

### getIndexId

    public String getIndexId()

------------------------------------------------------------------------

### setIndexId

    public void setIndexId(String indexId)

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

Render the beginning of the hyperlink.

Support for indexed property since Struts 1.1

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doAfterBody

    public int doAfterBody()
                    throws JspException

Save the associated label from the body content.

**Specified by:**  
`doAfterBody` in interface `IterationTag`

**Overrides:**  
`doAfterBody` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Render the end of the hyperlink.

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

### calculateURL

    protected String calculateURL()
                           throws JspException

Return the complete URL to which this hyperlink will direct the user. Support for indexed property since Struts 1.1

**Throws:**  
`JspException` - if an exception is thrown calculating the value

------------------------------------------------------------------------

### addParameter

    public void addParameter(String paramName,
                             Object paramValue)

Adds a parameter to this link.

**Parameters:**  
`paramName` - the parameter name

`paramValue` - the parameter value

**Since:**  
Struts 1.3.6

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
<td align="left"><a href="class-use/LinkTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/JavascriptValidatorTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/MessagesTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/LinkTag.html"><strong>FRAMES</strong></a>    <a href="LinkTag.html"><strong>NO FRAMES</strong></a>    
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
