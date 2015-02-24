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
<td align="left"><a href="class-use/FormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/FileTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/FrameTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/FormTag.html"><strong>FRAMES</strong></a>    <a href="FormTag.html"><strong>NO FRAMES</strong></a>    
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
 Class FormTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.html.md.FormTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELFormTag](../../../../../org/apache/strutsel/taglib.html.md/ELFormTag.html "class in org.apache.strutsel.taglib.html"), [NestedFormTag](../../../../../org/apache/struts/taglib/nested/html/NestedFormTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class FormTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that represents an input form, associated with a bean whose properties correspond to the various fields of the form.

**Version:**  
$Rev: 684382 $ $Date: 2008-08-09 19:11:59 -0500 (Sat, 09 Aug 2008) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.FormTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` acceptCharset`
           The list of character encodings for input data that the server should accept.

`protected  String`

`action`
           The action URL to which this form should be submitted, if any.

`protected  String`

` beanName`
           The name of the form bean to (create and) use.

`protected  String`

` beanScope`
           The scope of the form bean to (create and) use.

`protected  String`

` beanType`
           The type of the form bean to (create and) use.

`protected  String`

` enctype`
           The content encoding to be used on a POST submit.

`protected  String`

`focus`
           The name of the field to receive focus, if any.

`protected  String`

` focusIndex`
           The index in the focus field array to receive focus.

`protected static String`

` lineEnd`
           The line ending string.

`protected  ActionMapping`

` mapping`
           The ActionMapping defining where we will be submitting this form

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

`method`
           The request method used when submitting this form.

`protected  ModuleConfig`

` moduleConfig`
           The module configuration for our module.

`protected  String`

` onreset`
           The onReset event script.

`protected  String`

` onsubmit`
           The onSubmit event script.

`protected  boolean`

` readonly`
           Controls whether child controls should be 'readonly'.

`protected  boolean`

` scriptLanguage`
           Include language attribute in the focus script's \<script\> element.

`protected  ActionServlet`

` servlet`
           The ActionServlet instance we are associated with (so that we can initialize the `servlet` property on any form bean that we create).

`protected  String`

`style`
           The style attribute associated with this tag.

`protected  String`

` styleClass`
           The style class associated with this tag.

`protected  String`

` styleId`
           The identifier associated with this tag.

`protected  String`

`target`
           The window target.

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
| ` FormTag()`            
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Render the end of this form.

` int`

` doStartTag()`
           Render the beginning of this form.

` String`

` getAcceptCharset()`
           Return the list of character encodings accepted.

` String`

` getAction()`
           Return the action URL to which this form should be submitted.

` String`

` getAutocomplete()`
           Return autocomplete

` String`

` getBeanName()`
           Return the name of the form bean corresponding to this tag.

` String`

` getDir()`
           Returns the direction for weak/neutral text this element.

` String`

` getEnctype()`
           Return the content encoding used when submitting this form.

` String`

` getFocus()`
           Return the focus field name for this form.

` String`

` getFocusIndex()`
           Returns the focusIndex.

` String`

` getLang()`
           Returns the language code of this element.

` String`

` getMethod()`
           Return the request method used when submitting this form.

` String`

` getOnreset()`
           Return the onReset event script.

` String`

` getOnsubmit()`
           Return the onSubmit event script.

` boolean`

` getScriptLanguage()`
           Gets whether or not the focus script's \<script\> element will include the language attribute.

` String`

` getStyle()`
           Return the style attribute for this tag.

` String`

` getStyleClass()`
           Return the style class for this tag.

` String`

` getStyleId()`
           Return the style identifier for this tag.

` String`

` getTarget()`
           Return the window target.

`protected  void`

` initFormBean()`
           Locate or create the bean associated with our form.

` boolean`

` isDisabled()`
           Returns the disabled event handler.

` boolean`

` isReadonly()`
           Returns the readonly event handler.

`protected  void`

` lookup()`
           Look up values for the `name`, `scope`, and `type` properties if necessary.

` void`

` release()`
           Release any acquired resources.

`protected  void`

` renderAction(StringBuffer results)`
           Renders the action attribute

`protected  void`

` renderAttribute(StringBuffer results, String attribute, String value)`
           Renders attribute="value" if not null

`protected  String`

` renderFocusJavascript()`
           Generates javascript to set the initial focus to the form element given in the tag's "focus" attribute.

`protected  String`

` renderFormStartElement()`
           Generates the opening `<form>` element with appropriate attributes.

`protected  void`

` renderName(StringBuffer results)`
           Renders the name of the form.

`protected  void`

` renderOtherAttributes(StringBuffer results)`
           'Hook' to enable this tag to be extended and additional attributes added.

`protected  String`

` renderToken()`
           Generates a hidden input field with token information, if any.

` void`

` setAcceptCharset(String acceptCharset)`
           Set the list of character encodings accepted.

` void`

` setAction(String action)`
           Set the action URL to which this form should be submitted.

` void`

` setAutocomplete(String autocomplete)`
           Activate/disactivate autocompletion (on/off)

` void`

` setDir(String dir)`
           Sets the direction for weak/neutral text of this element.

` void`

` setDisabled(boolean disabled)`
           Sets the disabled event handler.

` void`

` setEnctype(String enctype)`
           Set the content encoding used when submitting this form.

` void`

` setFocus(String focus)`
           Set the focus field name for this form.

` void`

` setFocusIndex(String focusIndex)`
           Sets the focusIndex.

` void`

` setLang(String lang)`
           Sets the language code of this element.

` void`

` setMethod(String method)`
           Set the request method used when submitting this form.

` void`

` setOnreset(String onReset)`
           Set the onReset event script.

` void`

` setOnsubmit(String onSubmit)`
           Set the onSubmit event script.

` void`

` setReadonly(boolean readonly)`
           Sets the readonly event handler.

` void`

` setScriptLanguage(boolean scriptLanguage)`
           Sets whether or not the focus script's \<script\> element will include the language attribute.

` void`

` setStyle(String style)`
           Set the style attribute for this tag.

` void`

` setStyleClass(String styleClass)`
           Set the style class for this tag.

` void`

` setStyleId(String styleId)`
           Set the style identifier for this tag.

` void`

` setTarget(String target)`
           Set the window target.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="lineEnd"></span>

### lineEnd

    protected static String lineEnd

The line ending string.

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="action"></span>

### action

    protected String action

The action URL to which this form should be submitted, if any.

------------------------------------------------------------------------

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

The module configuration for our module.

------------------------------------------------------------------------

<span id="enctype"></span>

### enctype

    protected String enctype

The content encoding to be used on a POST submit.

------------------------------------------------------------------------

<span id="focus"></span>

### focus

    protected String focus

The name of the field to receive focus, if any.

------------------------------------------------------------------------

<span id="focusIndex"></span>

### focusIndex

    protected String focusIndex

The index in the focus field array to receive focus. This only applies if the field given in the focus attribute is actually an array of fields. This allows a specific field in a radio button array to receive focus while still allowing indexed field names like "myRadioButtonField[1]" to be passed in the focus attribute.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="mapping"></span>

### mapping

    protected ActionMapping mapping

The ActionMapping defining where we will be submitting this form

------------------------------------------------------------------------

<span id="method"></span>

### method

    protected String method

The request method used when submitting this form.

------------------------------------------------------------------------

<span id="onreset"></span>

### onreset

    protected String onreset

The onReset event script.

------------------------------------------------------------------------

<span id="onsubmit"></span>

### onsubmit

    protected String onsubmit

The onSubmit event script.

------------------------------------------------------------------------

<span id="scriptLanguage"></span>

### scriptLanguage

    protected boolean scriptLanguage

Include language attribute in the focus script's \<script\> element. This property is ignored in XHTML mode.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

<span id="servlet"></span>

### servlet

    protected ActionServlet servlet

The ActionServlet instance we are associated with (so that we can initialize the `servlet` property on any form bean that we create).

------------------------------------------------------------------------

<span id="style"></span>

### style

    protected String style

The style attribute associated with this tag.

------------------------------------------------------------------------

<span id="styleClass"></span>

### styleClass

    protected String styleClass

The style class associated with this tag.

------------------------------------------------------------------------

<span id="styleId"></span>

### styleId

    protected String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

<span id="target"></span>

### target

    protected String target

The window target.

------------------------------------------------------------------------

<span id="beanName"></span>

### beanName

    protected String beanName

The name of the form bean to (create and) use. This is either the same as the 'name' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

<span id="beanScope"></span>

### beanScope

    protected String beanScope

The scope of the form bean to (create and) use. This is either the same as the 'scope' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

<span id="beanType"></span>

### beanType

    protected String beanType

The type of the form bean to (create and) use. This is either the same as the 'type' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

<span id="acceptCharset"></span>

### acceptCharset

    protected String acceptCharset

The list of character encodings for input data that the server should accept.

------------------------------------------------------------------------

<span id="readonly"></span>

### readonly

    protected boolean readonly

Controls whether child controls should be 'readonly'.

<span id="constructor_detail"></span>

**Constructor Detail**

### FormTag

    public FormTag()

<span id="method_detail"></span>

**Method Detail**

### getBeanName

    public String getBeanName()

Return the name of the form bean corresponding to this tag. There is no corresponding setter method; this method exists so that the nested tag classes can obtain the actual bean name derived from other attributes of the tag.

------------------------------------------------------------------------

### getAction

    public String getAction()

Return the action URL to which this form should be submitted.

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

Set the action URL to which this form should be submitted.

**Parameters:**  
`action` - The new action URL

------------------------------------------------------------------------

### getAutocomplete

    public String getAutocomplete()

Return autocomplete

**Since:**  
1.3.10

------------------------------------------------------------------------

### setAutocomplete

    public void setAutocomplete(String autocomplete)

Activate/disactivate autocompletion (on/off)

**Since:**  
1.3.10

------------------------------------------------------------------------

### getEnctype

    public String getEnctype()

Return the content encoding used when submitting this form.

------------------------------------------------------------------------

### setEnctype

    public void setEnctype(String enctype)

Set the content encoding used when submitting this form.

**Parameters:**  
`enctype` - The new content encoding

------------------------------------------------------------------------

### getFocus

    public String getFocus()

Return the focus field name for this form.

------------------------------------------------------------------------

### setFocus

    public void setFocus(String focus)

Set the focus field name for this form.

**Parameters:**  
`focus` - The new focus field name

------------------------------------------------------------------------

### getMethod

    public String getMethod()

Return the request method used when submitting this form.

------------------------------------------------------------------------

### setMethod

    public void setMethod(String method)

Set the request method used when submitting this form.

**Parameters:**  
`method` - The new request method

------------------------------------------------------------------------

### getOnreset

    public String getOnreset()

Return the onReset event script.

------------------------------------------------------------------------

### setOnreset

    public void setOnreset(String onReset)

Set the onReset event script.

**Parameters:**  
`onReset` - The new event script

------------------------------------------------------------------------

### getOnsubmit

    public String getOnsubmit()

Return the onSubmit event script.

------------------------------------------------------------------------

### setOnsubmit

    public void setOnsubmit(String onSubmit)

Set the onSubmit event script.

**Parameters:**  
`onSubmit` - The new event script

------------------------------------------------------------------------

### getStyle

    public String getStyle()

Return the style attribute for this tag.

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

Set the style attribute for this tag.

**Parameters:**  
`style` - The new style attribute

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

Return the style class for this tag.

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

Set the style class for this tag.

**Parameters:**  
`styleClass` - The new style class

------------------------------------------------------------------------

### getStyleId

    public String getStyleId()

Return the style identifier for this tag.

------------------------------------------------------------------------

### setStyleId

    public void setStyleId(String styleId)

Set the style identifier for this tag.

**Parameters:**  
`styleId` - The new style identifier

------------------------------------------------------------------------

### getTarget

    public String getTarget()

Return the window target.

------------------------------------------------------------------------

### setTarget

    public void setTarget(String target)

Set the window target.

**Parameters:**  
`target` - The new window target

------------------------------------------------------------------------

### getAcceptCharset

    public String getAcceptCharset()

Return the list of character encodings accepted.

------------------------------------------------------------------------

### setAcceptCharset

    public void setAcceptCharset(String acceptCharset)

Set the list of character encodings accepted.

**Parameters:**  
`acceptCharset` - The list of character encodings

------------------------------------------------------------------------

### setDisabled

    public void setDisabled(boolean disabled)

Sets the disabled event handler.

------------------------------------------------------------------------

### isDisabled

    public boolean isDisabled()

Returns the disabled event handler.

------------------------------------------------------------------------

### setReadonly

    public void setReadonly(boolean readonly)

Sets the readonly event handler.

------------------------------------------------------------------------

### isReadonly

    public boolean isReadonly()

Returns the readonly event handler.

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

### doStartTag

    public int doStartTag()
                   throws JspException

Render the beginning of this form.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### initFormBean

    protected void initFormBean()
                         throws JspException

Locate or create the bean associated with our form.

**Throws:**  
`JspException`

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### renderFormStartElement

    protected String renderFormStartElement()
                                     throws JspException

Generates the opening `<form>` element with appropriate attributes.

**Throws:**  
`JspException`

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### renderName

    protected void renderName(StringBuffer results)
                       throws JspException

Renders the name of the form. If XHTML is set to true, the name will be rendered as an 'id' attribute, otherwise as a 'name' attribute.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### renderAction

    protected void renderAction(StringBuffer results)

Renders the action attribute

------------------------------------------------------------------------

### renderOtherAttributes

    protected void renderOtherAttributes(StringBuffer results)

'Hook' to enable this tag to be extended and additional attributes added.

------------------------------------------------------------------------

### renderToken

    protected String renderToken()

Generates a hidden input field with token information, if any. The field is added within a div element for HTML 4.01 Strict compliance.

**Returns:**  
A hidden input field containing the token.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### renderAttribute

    protected void renderAttribute(StringBuffer results,
                                   String attribute,
                                   String value)

Renders attribute="value" if not null

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Render the end of this form.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### renderFocusJavascript

    protected String renderFocusJavascript()

Generates javascript to set the initial focus to the form element given in the tag's "focus" attribute.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

------------------------------------------------------------------------

### lookup

    protected void lookup()
                   throws JspException

Look up values for the `name`, `scope`, and `type` properties if necessary.

**Throws:**  
`JspException` - if a required value cannot be looked up

------------------------------------------------------------------------

### getFocusIndex

    public String getFocusIndex()

Returns the focusIndex.

**Returns:**  
String

------------------------------------------------------------------------

### setFocusIndex

    public void setFocusIndex(String focusIndex)

Sets the focusIndex.

**Parameters:**  
`focusIndex` - The focusIndex to set

------------------------------------------------------------------------

### getScriptLanguage

    public boolean getScriptLanguage()

Gets whether or not the focus script's \<script\> element will include the language attribute.

**Returns:**  
true if language attribute will be included.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### setScriptLanguage

    public void setScriptLanguage(boolean scriptLanguage)

Sets whether or not the focus script's \<script\> element will include the language attribute.

**Since:**  
Struts 1.2

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
<td align="left"><a href="class-use/FormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/FileTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/FrameTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/FormTag.html"><strong>FRAMES</strong></a>    <a href="FormTag.html"><strong>NO FRAMES</strong></a>    
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
