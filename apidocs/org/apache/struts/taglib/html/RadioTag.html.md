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
<td align="left"><a href="class-use/RadioTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/PasswordTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/ResetTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/RadioTag.html"><strong>FRAMES</strong></a>    <a href="RadioTag.html"><strong>NO FRAMES</strong></a>    
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
 Class RadioTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.RadioTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELRadioTag](../../../../../org/apache/strutsel/taglib.html.md/ELRadioTag.html "class in org.apache.strutsel.taglib.html"), [NestedRadioTag](../../../../../org/apache/struts/taglib/nested/html/NestedRadioTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class RadioTag

extends [BaseHandlerTag](../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html "class in org.apache.struts.taglib.html")

Tag for input fields of type "radio".

**Version:**  
$Rev: 471754 $ $Date: 2005-06-14 14:26:17 -0400 (Tue, 14 Jun 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.RadioTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` idName`
           Name of the bean (in some scope) that will return the value of the radio tag.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

`name`
           The name of the bean containing our underlying property.

`protected  String`

` property`
           The property name for this field.

`protected  String`

`text`
           The body content of this tag (if any).

`protected  String`

`value`
           The server value for this option.

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
| ` RadioTag()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doAfterBody()`
           Save the associated label from the body content.

` int`

` doEndTag()`
           Optionally render the associated label from the body content.

` int`

` doStartTag()`
           Generate the required input tag.

` String`

` getIdName()`
           Return the idName.

` String`

` getName()`
            

` String`

` getProperty()`
           Return the property name.

` String`

` getValue()`
           Return the server value.

`protected  String`

` prepareName()`
           Prepare the name element

` void`

` release()`
           Release any acquired resources.

`protected  String`

` renderRadioElement(String serverValue, String checkedValue)`
           Renders an HTML \<input type="radio"\> element.

` void`

` setIdName(String idName)`
           Set the idName.

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
           Set the property name.

` void`

` setValue(String value)`
           Set the server value.

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

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The property name for this field.

------------------------------------------------------------------------

<span id="text"></span>

### text

    protected String text

The body content of this tag (if any).

------------------------------------------------------------------------

<span id="value"></span>

### value

    protected String value

The server value for this option.

------------------------------------------------------------------------

<span id="idName"></span>

### idName

    protected String idName

Name of the bean (in some scope) that will return the value of the radio tag.

If an iterator is used to render a series of radio tags, this field may be used to specify the name of the bean exposed by the iterator. In this case, the value attribute is used as the name of a property on the `idName` bean that returns the value of the radio tag in this iteration.

<span id="constructor_detail"></span>

**Constructor Detail**

### RadioTag

    public RadioTag()

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getProperty

    public String getProperty()

Return the property name.

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

Set the property name.

**Parameters:**  
`property` - The new property name

------------------------------------------------------------------------

### getValue

    public String getValue()

Return the server value.

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

Set the server value.

**Parameters:**  
`value` - The new server value

------------------------------------------------------------------------

### getIdName

    public String getIdName()

Return the idName.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### setIdName

    public void setIdName(String idName)

Set the idName.

**Parameters:**  
`idName` - The new idName

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Generate the required input tag. [Indexed property since Struts 1.1]

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### renderRadioElement

    protected String renderRadioElement(String serverValue,
                                        String checkedValue)
                                 throws JspException

Renders an HTML \<input type="radio"\> element.

**Parameters:**  
`serverValue` - The data to be used in the tag's `value` attribute and sent to the server when the form is submitted.

`checkedValue` - If the serverValue equals this value the radio button will be checked.

**Returns:**  
A radio input element.

**Throws:**  
`JspException`

**Since:**  
Struts 1.1

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

Optionally render the associated label from the body content.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### prepareName

    protected String prepareName()
                          throws JspException

Prepare the name element

**Overrides:**  
` prepareName` in class `BaseHandlerTag`

<!-- -->

**Returns:**  
The element name.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `BaseHandlerTag`

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
<td align="left"><a href="class-use/RadioTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/PasswordTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/ResetTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/RadioTag.html"><strong>FRAMES</strong></a>    <a href="RadioTag.html"><strong>NO FRAMES</strong></a>    
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
