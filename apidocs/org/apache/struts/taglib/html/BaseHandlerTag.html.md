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
<td align="left"><a href="class-use/BaseHandlerTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/BaseFieldTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/BaseInputTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/BaseHandlerTag.html"><strong>FRAMES</strong></a>    <a href="BaseHandlerTag.html"><strong>NO FRAMES</strong></a>    
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
 Class BaseHandlerTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[BaseInputTag](../../../../../org/apache/struts/taglib.html.md/BaseInputTag.html "class in org.apache.struts.taglib.html"), [CheckboxTag](../../../../../org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html"), [ImgTag](../../../../../org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html"), [LinkTag](../../../../../org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html"), [MultiboxTag](../../../../../org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html"), [RadioTag](../../../../../org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html"), [SelectTag](../../../../../org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html"), [SubmitTag](../../../../../org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html")

------------------------------------------------------------------------

    public abstract class BaseHandlerTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Base class for tags that render form elements capable of including JavaScript event handlers and/or CSS Style attributes. This class does not implement the doStartTag() or doEndTag() methods. Subclasses should provide appropriate implementations of these.

**Version:**  
$Rev: 479633 $ $Date: 2006-11-27 08:25:35 -0600 (Mon, 27 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.BaseHandlerTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` accesskey`
           Access key character.

`protected  boolean`

` doDisabled`
           Indicates whether 'disabled' is a valid attribute

`protected  boolean`

` doReadonly`
           Indicates whether 'readonly' is a valid attribute.

`protected  boolean`

` indexed`
           Whether to created indexed names for fields

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` tabindex`
           Tab index value.

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
| ` BaseHandlerTag()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  boolean`

` doErrorsExist()`
           Determine if there are errors for the component.

` String`

` getAccesskey()`
           Returns the accessKey character.

` String`

` getAlt()`
           Returns the alternate text attribute.

` String`

` getAltKey()`
           Returns the message resources key of the alternate text.

` String`

` getBundle()`
           Returns the name of the message resources bundle to use.

` String`

` getDir()`
           Returns the direction for weak/neutral text this element.

` boolean`

` getDisabled()`
           Returns the disabled event handler.

`protected  String`

` getElementClose()`
           Returns the closing brace for an input element depending on .html.md status.

` String`

` getErrorKey()`
           Returns the error key attribute.

` String`

` getErrorStyle()`
           Returns the error style attribute.

` String`

` getErrorStyleClass()`
           Returns the error style class attribute.

` String`

` getErrorStyleId()`
           Returns the error style id attribute.

` boolean`

` getIndexed()`
           Returns the indexed value.

`protected  int`

` getIndexValue()`
           Returns the index value for tags with 'true' value in 'indexed' attribute.

` String`

` getLang()`
           Returns the language code of this element.

` String`

` getLocale()`
           Returns the name of the session attribute for our locale.

` String`

` getOnblur()`
           Returns the onBlur event handler.

` String`

` getOnchange()`
           Returns the onChange event handler.

` String`

` getOnclick()`
           Returns the onClick event handler.

` String`

` getOndblclick()`
           Returns the onDblClick event handler.

` String`

` getOnfocus()`
           Returns the onFocus event handler.

` String`

` getOnkeydown()`
           Returns the onKeyDown event handler.

` String`

` getOnkeypress()`
           Returns the onKeyPress event handler.

` String`

` getOnkeyup()`
           Returns the onKeyUp event handler.

` String`

` getOnmousedown()`
           Returns the onMouseDown event handler.

` String`

` getOnmousemove()`
           Returns the onMouseMove event handler.

` String`

` getOnmouseout()`
           Returns the onMouseOut event handler.

` String`

` getOnmouseover()`
           Returns the onMouseOver event handler.

` String`

` getOnmouseup()`
           Returns the onMouseUp event handler.

` String`

` getOnselect()`
           Returns the onSelect event handler.

` boolean`

` getReadonly()`
           Returns the readonly event handler.

` String`

` getStyle()`
           Returns the style attribute.

` String`

` getStyleClass()`
           Returns the style class attribute.

` String`

` getStyleId()`
           Returns the style id attribute.

` String`

` getTabindex()`
           Returns the tabIndex value.

` String`

` getTitle()`
           Returns the advisory title attribute.

` String`

` getTitleKey()`
           Returns the message resources key of the advisory title.

`protected  boolean`

` is.html.md()`
           Allows HTML tags to find out if they're nested within an %lt.html.md:html\> tag that has xhtml set to true.

`protected  String`

` lookupProperty(String beanName, String property)`
           Searches all scopes for the bean and calls BeanUtils.getProperty() with the given arguments and converts any exceptions into JspException.

`protected  String`

` message(String literal, String key)`
           Return the text specified by the literal value or the message resources key, if any; otherwise return `null`.

`protected  void`

` prepareAttribute(StringBuffer handlers, String name, Object value)`
           Prepares an attribute if the value is not null, appending it to the the given StringBuffer.

`protected  String`

` prepareEventHandlers()`
           Prepares the event handlers for inclusion in the component's HTML tag.

`protected  void`

` prepareFocusEvents(StringBuffer handlers)`
           Prepares the focus event handlers, appending them to the the given StringBuffer.

`protected  void`

` prepareIndex(StringBuffer handlers, String name)`
           Appends bean name with index in brackets for tags with 'true' value in 'indexed' attribute.

`protected  void`

` prepareInternationalization(StringBuffer handlers)`
           Prepares the internationalization attribtes, appending them to the the given StringBuffer.

`protected  void`

` prepareKeyEvents(StringBuffer handlers)`
           Prepares the keyboard event handlers, appending them to the the given StringBuffer.

`protected  void`

` prepareMouseEvents(StringBuffer handlers)`
           Prepares the mouse event handlers, appending them to the the given StringBuffer.

`protected  String`

` prepareName()`
           Prepares the actual name of the component.

`protected  void`

` prepareOtherAttributes(StringBuffer handlers)`
           'Hook' to enable tags to be extended and additional attributes added.

`protected  String`

` prepareStyles()`
           Prepares the style attributes for inclusion in the component's HTML tag.

`protected  void`

` prepareTextEvents(StringBuffer handlers)`
           Prepares the text event handlers, appending them to the the given StringBuffer.

` void`

` release()`
           Release any acquired resources.

` void`

` setAccesskey(String accessKey)`
           Sets the accessKey character.

` void`

` setAlt(String alt)`
           Sets the alternate text attribute.

` void`

` setAltKey(String altKey)`
           Sets the message resources key of the alternate text.

` void`

` setBundle(String bundle)`
           Sets the name of the message resources bundle to use.

` void`

` setDir(String dir)`
           Sets the direction for weak/neutral text of this element.

` void`

` setDisabled(boolean disabled)`
           Sets the disabled event handler.

` void`

` setErrorKey(String errorKey)`
           Sets the error key attribute.

` void`

` setErrorStyle(String errorStyle)`
           Sets the error style attribute.

` void`

` setErrorStyleClass(String errorStyleClass)`
           Sets the error style class attribute.

` void`

` setErrorStyleId(String errorStyleId)`
           Sets the error style id attribute.

` void`

` setIndexed(boolean indexed)`
           Sets the indexed value.

` void`

` setLang(String lang)`
           Sets the language code of this element.

` void`

` setLocale(String locale)`
           Sets the name of the session attribute for our locale.

` void`

` setOnblur(String onBlur)`
           Sets the onBlur event handler.

` void`

` setOnchange(String onChange)`
           Sets the onChange event handler.

` void`

` setOnclick(String onClick)`
           Sets the onClick event handler.

` void`

` setOndblclick(String onDblClick)`
           Sets the onDblClick event handler.

` void`

` setOnfocus(String onFocus)`
           Sets the onFocus event handler.

` void`

` setOnkeydown(String onKeyDown)`
           Sets the onKeyDown event handler.

` void`

` setOnkeypress(String onKeyPress)`
           Sets the onKeyPress event handler.

` void`

` setOnkeyup(String onKeyUp)`
           Sets the onKeyUp event handler.

` void`

` setOnmousedown(String onMouseDown)`
           Sets the onMouseDown event handler.

` void`

` setOnmousemove(String onMouseMove)`
           Sets the onMouseMove event handler.

` void`

` setOnmouseout(String onMouseOut)`
           Sets the onMouseOut event handler.

` void`

` setOnmouseover(String onMouseOver)`
           Sets the onMouseOver event handler.

` void`

` setOnmouseup(String onMouseUp)`
           Sets the onMouseUp event handler.

` void`

` setOnselect(String onSelect)`
           Sets the onSelect event handler.

` void`

` setReadonly(boolean readonly)`
           Sets the readonly event handler.

` void`

` setStyle(String style)`
           Sets the style attribute.

` void`

` setStyleClass(String styleClass)`
           Sets the style class attribute.

` void`

` setStyleId(String styleId)`
           Sets the style id attribute.

` void`

` setTabindex(String tabIndex)`
           Sets the tabIndex value.

` void`

` setTitle(String title)`
           Sets the advisory title attribute.

` void`

` setTitleKey(String titleKey)`
           Sets the message resources key of the advisory title.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, doInitBody, doStartTag, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                  |

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

<span id="accesskey"></span>

### accesskey

    protected String accesskey

Access key character.

------------------------------------------------------------------------

<span id="tabindex"></span>

### tabindex

    protected String tabindex

Tab index value.

------------------------------------------------------------------------

<span id="indexed"></span>

### indexed

    protected boolean indexed

Whether to created indexed names for fields

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="doDisabled"></span>

### doDisabled

    protected boolean doDisabled

Indicates whether 'disabled' is a valid attribute

------------------------------------------------------------------------

<span id="doReadonly"></span>

### doReadonly

    protected boolean doReadonly

Indicates whether 'readonly' is a valid attribute.

According to the HTML 4.0 Specification \<readonly\> is valid for \<input type="text"\>, \<input type="password"\> and \<textarea"\> elements. Therefore, except for those tags this value is set to `false`.

<span id="constructor_detail"></span>

**Constructor Detail**

### BaseHandlerTag

    public BaseHandlerTag()

<span id="method_detail"></span>

**Method Detail**

### setAccesskey

    public void setAccesskey(String accessKey)

Sets the accessKey character.

------------------------------------------------------------------------

### getAccesskey

    public String getAccesskey()

Returns the accessKey character.

------------------------------------------------------------------------

### setTabindex

    public void setTabindex(String tabIndex)

Sets the tabIndex value.

------------------------------------------------------------------------

### getTabindex

    public String getTabindex()

Returns the tabIndex value.

------------------------------------------------------------------------

### setIndexed

    public void setIndexed(boolean indexed)

Sets the indexed value.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getIndexed

    public boolean getIndexed()

Returns the indexed value.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### setOnclick

    public void setOnclick(String onClick)

Sets the onClick event handler.

------------------------------------------------------------------------

### getOnclick

    public String getOnclick()

Returns the onClick event handler.

------------------------------------------------------------------------

### setOndblclick

    public void setOndblclick(String onDblClick)

Sets the onDblClick event handler.

------------------------------------------------------------------------

### getOndblclick

    public String getOndblclick()

Returns the onDblClick event handler.

------------------------------------------------------------------------

### setOnmousedown

    public void setOnmousedown(String onMouseDown)

Sets the onMouseDown event handler.

------------------------------------------------------------------------

### getOnmousedown

    public String getOnmousedown()

Returns the onMouseDown event handler.

------------------------------------------------------------------------

### setOnmouseup

    public void setOnmouseup(String onMouseUp)

Sets the onMouseUp event handler.

------------------------------------------------------------------------

### getOnmouseup

    public String getOnmouseup()

Returns the onMouseUp event handler.

------------------------------------------------------------------------

### setOnmousemove

    public void setOnmousemove(String onMouseMove)

Sets the onMouseMove event handler.

------------------------------------------------------------------------

### getOnmousemove

    public String getOnmousemove()

Returns the onMouseMove event handler.

------------------------------------------------------------------------

### setOnmouseover

    public void setOnmouseover(String onMouseOver)

Sets the onMouseOver event handler.

------------------------------------------------------------------------

### getOnmouseover

    public String getOnmouseover()

Returns the onMouseOver event handler.

------------------------------------------------------------------------

### setOnmouseout

    public void setOnmouseout(String onMouseOut)

Sets the onMouseOut event handler.

------------------------------------------------------------------------

### getOnmouseout

    public String getOnmouseout()

Returns the onMouseOut event handler.

------------------------------------------------------------------------

### setOnkeydown

    public void setOnkeydown(String onKeyDown)

Sets the onKeyDown event handler.

------------------------------------------------------------------------

### getOnkeydown

    public String getOnkeydown()

Returns the onKeyDown event handler.

------------------------------------------------------------------------

### setOnkeyup

    public void setOnkeyup(String onKeyUp)

Sets the onKeyUp event handler.

------------------------------------------------------------------------

### getOnkeyup

    public String getOnkeyup()

Returns the onKeyUp event handler.

------------------------------------------------------------------------

### setOnkeypress

    public void setOnkeypress(String onKeyPress)

Sets the onKeyPress event handler.

------------------------------------------------------------------------

### getOnkeypress

    public String getOnkeypress()

Returns the onKeyPress event handler.

------------------------------------------------------------------------

### setOnchange

    public void setOnchange(String onChange)

Sets the onChange event handler.

------------------------------------------------------------------------

### getOnchange

    public String getOnchange()

Returns the onChange event handler.

------------------------------------------------------------------------

### setOnselect

    public void setOnselect(String onSelect)

Sets the onSelect event handler.

------------------------------------------------------------------------

### getOnselect

    public String getOnselect()

Returns the onSelect event handler.

------------------------------------------------------------------------

### setOnblur

    public void setOnblur(String onBlur)

Sets the onBlur event handler.

------------------------------------------------------------------------

### getOnblur

    public String getOnblur()

Returns the onBlur event handler.

------------------------------------------------------------------------

### setOnfocus

    public void setOnfocus(String onFocus)

Sets the onFocus event handler.

------------------------------------------------------------------------

### getOnfocus

    public String getOnfocus()

Returns the onFocus event handler.

------------------------------------------------------------------------

### setDisabled

    public void setDisabled(boolean disabled)

Sets the disabled event handler.

------------------------------------------------------------------------

### getDisabled

    public boolean getDisabled()

Returns the disabled event handler.

------------------------------------------------------------------------

### setReadonly

    public void setReadonly(boolean readonly)

Sets the readonly event handler.

------------------------------------------------------------------------

### getReadonly

    public boolean getReadonly()

Returns the readonly event handler.

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

Sets the style attribute.

------------------------------------------------------------------------

### getStyle

    public String getStyle()

Returns the style attribute.

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

Sets the style class attribute.

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

Returns the style class attribute.

------------------------------------------------------------------------

### setStyleId

    public void setStyleId(String styleId)

Sets the style id attribute.

------------------------------------------------------------------------

### getStyleId

    public String getStyleId()

Returns the style id attribute.

------------------------------------------------------------------------

### getErrorKey

    public String getErrorKey()

Returns the error key attribute.

------------------------------------------------------------------------

### setErrorKey

    public void setErrorKey(String errorKey)

Sets the error key attribute.

------------------------------------------------------------------------

### getErrorStyle

    public String getErrorStyle()

Returns the error style attribute.

------------------------------------------------------------------------

### setErrorStyle

    public void setErrorStyle(String errorStyle)

Sets the error style attribute.

------------------------------------------------------------------------

### getErrorStyleClass

    public String getErrorStyleClass()

Returns the error style class attribute.

------------------------------------------------------------------------

### setErrorStyleClass

    public void setErrorStyleClass(String errorStyleClass)

Sets the error style class attribute.

------------------------------------------------------------------------

### getErrorStyleId

    public String getErrorStyleId()

Returns the error style id attribute.

------------------------------------------------------------------------

### setErrorStyleId

    public void setErrorStyleId(String errorStyleId)

Sets the error style id attribute.

------------------------------------------------------------------------

### getAlt

    public String getAlt()

Returns the alternate text attribute.

------------------------------------------------------------------------

### setAlt

    public void setAlt(String alt)

Sets the alternate text attribute.

------------------------------------------------------------------------

### getAltKey

    public String getAltKey()

Returns the message resources key of the alternate text.

------------------------------------------------------------------------

### setAltKey

    public void setAltKey(String altKey)

Sets the message resources key of the alternate text.

------------------------------------------------------------------------

### getBundle

    public String getBundle()

Returns the name of the message resources bundle to use.

------------------------------------------------------------------------

### setBundle

    public void setBundle(String bundle)

Sets the name of the message resources bundle to use.

------------------------------------------------------------------------

### getLocale

    public String getLocale()

Returns the name of the session attribute for our locale.

------------------------------------------------------------------------

### setLocale

    public void setLocale(String locale)

Sets the name of the session attribute for our locale.

------------------------------------------------------------------------

### getTitle

    public String getTitle()

Returns the advisory title attribute.

------------------------------------------------------------------------

### setTitle

    public void setTitle(String title)

Sets the advisory title attribute.

------------------------------------------------------------------------

### getTitleKey

    public String getTitleKey()

Returns the message resources key of the advisory title.

------------------------------------------------------------------------

### setTitleKey

    public void setTitleKey(String titleKey)

Sets the message resources key of the advisory title.

------------------------------------------------------------------------

### getLang

    public String getLang()

Returns the language code of this element.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### setLang

    public void setLang(String lang)

Sets the language code of this element.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### getDir

    public String getDir()

Returns the direction for weak/neutral text this element.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### setDir

    public void setDir(String dir)

Sets the direction for weak/neutral text of this element.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `BodyTagSupport`

------------------------------------------------------------------------

### message

    protected String message(String literal,
                             String key)
                      throws JspException

Return the text specified by the literal value or the message resources key, if any; otherwise return `null`.

**Parameters:**  
`literal` - Literal text value or `null`

`key` - Message resources key or `null`

**Throws:**  
`JspException` - if both arguments are non-null

------------------------------------------------------------------------

### prepareIndex

    protected void prepareIndex(StringBuffer handlers,
                                String name)
                         throws JspException

Appends bean name with index in brackets for tags with 'true' value in 'indexed' attribute.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

**Throws:**  
`JspException` - if 'indexed' tag used outside of iterate tag.

------------------------------------------------------------------------

### getIndexValue

    protected int getIndexValue()
                         throws JspException

Returns the index value for tags with 'true' value in 'indexed' attribute.

**Returns:**  
the index value.

**Throws:**  
`JspException` - if 'indexed' tag used outside of iterate tag.

------------------------------------------------------------------------

### prepareStyles

    protected String prepareStyles()
                            throws JspException

Prepares the style attributes for inclusion in the component's HTML tag.

**Returns:**  
The prepared String for inclusion in the HTML tag.

**Throws:**  
`JspException` - if invalid attributes are specified

------------------------------------------------------------------------

### doErrorsExist

    protected boolean doErrorsExist()
                             throws JspException

Determine if there are errors for the component.

**Returns:**  
Whether errors exist.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### prepareName

    protected String prepareName()
                          throws JspException

Prepares the actual name of the component.

**Returns:**  
The actual component name.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### prepareEventHandlers

    protected String prepareEventHandlers()

Prepares the event handlers for inclusion in the component's HTML tag.

**Returns:**  
The prepared String for inclusion in the HTML tag.

------------------------------------------------------------------------

### prepareMouseEvents

    protected void prepareMouseEvents(StringBuffer handlers)

Prepares the mouse event handlers, appending them to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### prepareKeyEvents

    protected void prepareKeyEvents(StringBuffer handlers)

Prepares the keyboard event handlers, appending them to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### prepareTextEvents

    protected void prepareTextEvents(StringBuffer handlers)

Prepares the text event handlers, appending them to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### prepareFocusEvents

    protected void prepareFocusEvents(StringBuffer handlers)

Prepares the focus event handlers, appending them to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### prepareInternationalization

    protected void prepareInternationalization(StringBuffer handlers)

Prepares the internationalization attribtes, appending them to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### prepareOtherAttributes

    protected void prepareOtherAttributes(StringBuffer handlers)

'Hook' to enable tags to be extended and additional attributes added.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### prepareAttribute

    protected void prepareAttribute(StringBuffer handlers,
                                    String name,
                                    Object value)

Prepares an attribute if the value is not null, appending it to the the given StringBuffer.

**Parameters:**  
`handlers` - The StringBuffer that output will be appended to.

------------------------------------------------------------------------

### is.html.md

    protected boolean is.html.md()

Allows HTML tags to find out if they're nested within an %lt.html.md:html\> tag that has xhtml set to true.

**Returns:**  
true if the tag is nested within an.html.md tag with xhtml set to true, false otherwise.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getElementClose

    protected String getElementClose()

Returns the closing brace for an input element depending on .html.md status. The tag must be nested within an %lt;html:html\> tag that has xhtml set to true.

**Returns:**  
String - \> if .html.md is false, /\> if xhtml is true

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### lookupProperty

    protected String lookupProperty(String beanName,
                                    String property)
                             throws JspException

Searches all scopes for the bean and calls BeanUtils.getProperty() with the given arguments and converts any exceptions into JspException.

**Parameters:**  
`beanName` - The name of the object to get the property from.

`property` - The name of the property to get.

**Returns:**  
The value of the property.

**Throws:**  
`JspException`

**Since:**  
Struts 1.1

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
<td align="left"><a href="class-use/BaseHandlerTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/BaseFieldTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/BaseInputTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/BaseHandlerTag.html"><strong>FRAMES</strong></a>    <a href="BaseHandlerTag.html"><strong>NO FRAMES</strong></a>    
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
