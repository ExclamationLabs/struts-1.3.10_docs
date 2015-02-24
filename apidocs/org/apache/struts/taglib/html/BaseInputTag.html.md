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
<td align="left"><a href="class-use/BaseInputTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/BaseTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/BaseInputTag.html"><strong>FRAMES</strong></a>    <a href="BaseInputTag.html"><strong>NO FRAMES</strong></a>    
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
 Class BaseInputTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.BaseHandlerTag
                  org.apache.struts.taglib.html.md.BaseInputTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[BaseFieldTag](../../../../../org/apache/struts/taglib.html.md/BaseFieldTag.html "class in org.apache.struts.taglib.html"), [TextareaTag](../../../../../org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html")

------------------------------------------------------------------------

    public abstract class BaseInputTag

extends [BaseHandlerTag](../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html "class in org.apache.struts.taglib.html")

Abstract base class for the various input tags.

**Version:**  
$Rev: 684382 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.BaseInputTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` cols`
           The number of character columns for this field, or negative for no limit.

`protected  String`

` maxlength`
           The maximum number of characters allowed, or negative for no limit.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           The name of the bean containing our underlying property.

`protected  String`

` property`
           The name of the field (and associated property) being processed.

`protected  String`

` rows`
           The number of rows for this field, or negative for no limit.

`protected  String`

` value`
           The value for this field, or `null` to retrieve the corresponding property from our associated bean.

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
| ` BaseInputTag()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Process the end of this tag.

` int`

` doStartTag()`
           Process the start of this tag.

` String`

` getAutocomplete()`
           Return autocomplete

` String`

` getCols()`
           Return the number of columns for this field.

` String`

` getMaxlength()`
           Return the maximum length allowed.

` String`

` getName()`
            

` String`

` getProperty()`
           Return the property name.

` String`

` getRows()`
           Return the number of rows for this field.

` String`

` getSize()`
           Return the size of this field (synonym for `getCols()`).

` String`

` getValue()`
           Return the field value (if any).

`protected  String`

` prepareName()`
           Prepare the name element

` void`

` release()`
           Release any acquired resources.

` void`

` setAutocomplete(String autocomplete)`
           Activate/disactivate autocompletion (on/off)

` void`

` setCols(String cols)`
           Set the number of columns for this field.

` void`

` setMaxlength(String maxlength)`
           Set the maximum length allowed.

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
           Set the property name.

` void`

` setRows(String rows)`
           Set the number of rows for this field.

` void`

` setSize(String size)`
           Set the size of this field (synonym for `setCols()`).

` void`

` setValue(String value)`
           Set the field value (if any).

 <span id="methods_inherited_from_class_org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

| **Methods inherited from class org.apache.struts.taglib.html.md.[BaseHandlerTag](../../../../../org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doErrorsExist,  getAccesskey,  getAlt,  getAltKey,  getBundle,  getDir,  getDisabled,  getElementClose,  getErrorKey,  getErrorStyle,  getErrorStyleClass,  getErrorStyleId,  getIndexed,  getIndexValue,  getLang,  getLocale,  getOnblur,  getOnchange,  getOnclick,  getOndblclick,  getOnfocus,  getOnkeydown,  getOnkeypress,  getOnkeyup,  getOnmousedown,  getOnmousemove,  getOnmouseout,  getOnmouseover,  getOnmouseup,  getOnselect,  getReadonly,  getStyle,  getStyleClass,  getStyleId,  getTabindex,  getTitle,  getTitleKey,  is.html.md,  lookupProperty,  message,  prepareAttribute,  prepareEventHandlers,  prepareFocusEvents,  prepareIndex,  prepareInternationalization,  prepareKeyEvents,  prepareMouseEvents,  prepareOtherAttributes,  prepareStyles,  prepareTextEvents,  setAccesskey,  setAlt,  setAltKey,  setBundle,  setDir,  setDisabled,  setErrorKey,  setErrorStyle,  setErrorStyleClass,  setErrorStyleId,  setIndexed,  setLang,  setLocale,  setOnblur,  setOnchange,  setOnclick,  setOndblclick,  setOnfocus,  setOnkeydown,  setOnkeypress,  setOnkeyup,  setOnmousedown,  setOnmousemove,  setOnmouseout,  setOnmouseover,  setOnmouseup,  setOnselect,  setReadonly,  setStyle,  setStyleClass,  setStyleId,  setTabindex,  setTitle,  setTitleKey` |

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

<span id="cols"></span>

### cols

    protected String cols

The number of character columns for this field, or negative for no limit.

------------------------------------------------------------------------

<span id="maxlength"></span>

### maxlength

    protected String maxlength

The maximum number of characters allowed, or negative for no limit.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The name of the field (and associated property) being processed.

------------------------------------------------------------------------

<span id="rows"></span>

### rows

    protected String rows

The number of rows for this field, or negative for no limit.

------------------------------------------------------------------------

<span id="value"></span>

### value

    protected String value

The value for this field, or `null` to retrieve the corresponding property from our associated bean.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the bean containing our underlying property.

<span id="constructor_detail"></span>

**Constructor Detail**

### BaseInputTag

    public BaseInputTag()

<span id="method_detail"></span>

**Method Detail**

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

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getCols

    public String getCols()

Return the number of columns for this field.

------------------------------------------------------------------------

### setCols

    public void setCols(String cols)

Set the number of columns for this field.

**Parameters:**  
`cols` - The new number of columns

------------------------------------------------------------------------

### getMaxlength

    public String getMaxlength()

Return the maximum length allowed.

------------------------------------------------------------------------

### setMaxlength

    public void setMaxlength(String maxlength)

Set the maximum length allowed.

**Parameters:**  
`maxlength` - The new maximum length

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

### getRows

    public String getRows()

Return the number of rows for this field.

------------------------------------------------------------------------

### setRows

    public void setRows(String rows)

Set the number of rows for this field.

**Parameters:**  
`rows` - The new number of rows

------------------------------------------------------------------------

### getSize

    public String getSize()

Return the size of this field (synonym for `getCols()`).

------------------------------------------------------------------------

### setSize

    public void setSize(String size)

Set the size of this field (synonym for `setCols()`).

**Parameters:**  
`size` - The new size

------------------------------------------------------------------------

### getValue

    public String getValue()

Return the field value (if any).

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

Set the field value (if any).

**Parameters:**  
`value` - The new field value, or `null` to retrieve the corresponding property from the bean

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start of this tag. The default implementation does nothing.

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

Process the end of this tag. The default implementation does nothing.

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
<td align="left"><a href="class-use/BaseInputTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/BaseHandlerTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/BaseTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/BaseInputTag.html"><strong>FRAMES</strong></a>    <a href="BaseInputTag.html"><strong>NO FRAMES</strong></a>    
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
