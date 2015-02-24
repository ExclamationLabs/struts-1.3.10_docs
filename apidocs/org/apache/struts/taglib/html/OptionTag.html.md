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
<td align="left"><a href="class-use/OptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/OptionsTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/ParamTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/OptionTag.html"><strong>FRAMES</strong></a>    <a href="OptionTag.html"><strong>NO FRAMES</strong></a>    
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
 Class OptionTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.OptionTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELOptionTag](../../../../../org/apache/strutsel/taglib.html.md/ELOptionTag.html "class in org.apache.strutsel.taglib.html")

------------------------------------------------------------------------

    public class OptionTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Tag for select options. The body of this tag is presented to the user in the option list, while the value attribute is the value returned to the server if this option is selected.

**Version:**  
$Rev: 479633 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.OptionTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` bundle`
           The name of the servlet context attribute containing our message resources.

`protected  boolean`

` disabled`
           Is this option disabled?

`protected  boolean`

` filter`
           Should the label be filtered for HTML sensitive characters?

`protected  String`

`key`
           The key used to look up the text displayed to the user for this option, if any.

`protected  String`

` locale`
           The name of the attribute containing the Locale to be used for looking up internationalized messages.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` styleId`
           The identifier associated with this tag.

`protected  String`

`text`
           The message text to be displayed to the user for this tag (if any)

`protected  String`

` value`
           The server value for this option, also used to match against the current property value to determine whether this option should be marked as selected.

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
| ` OptionTag()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doAfterBody()`
           Process the body text of this tag (if any).

` int`

` doEndTag()`
           Process the end of this tag.

` int`

` doStartTag()`
           Process the start of this tag.

` String`

` getBundle()`
            

` String`

` getDir()`
           Returns the direction for weak/neutral text this element.

` boolean`

` getDisabled()`
            

` boolean`

` getFilter()`
            

` String`

` getKey()`
            

` String`

` getLang()`
           Returns the language code of this element.

` String`

` getLocale()`
            

` String`

` getStyle()`
            

` String`

` getStyleClass()`
            

` String`

` getStyleId()`
           Return the style identifier for this tag.

` String`

` getValue()`
            

` void`

` release()`
           Release any acquired resources.

`protected  String`

` renderOptionElement()`
           Generate an HTML %lt;option\> element.

` void`

` setBundle(String bundle)`
            

` void`

` setDir(String dir)`
           Sets the direction for weak/neutral text of this element.

` void`

` setDisabled(boolean disabled)`
            

` void`

` setFilter(boolean filter)`
            

` void`

` setKey(String key)`
            

` void`

` setLang(String lang)`
           Sets the language code of this element.

` void`

` setLocale(String locale)`
            

` void`

` setStyle(String style)`
            

` void`

` setStyleClass(String styleClass)`
            

` void`

` setStyleId(String styleId)`
           Set the style identifier for this tag.

` void`

` setValue(String value)`
            

`protected  String`

` text()`
           Return the text to be displayed to the user for this option (if any).

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

The message text to be displayed to the user for this tag (if any)

------------------------------------------------------------------------

<span id="bundle"></span>

### bundle

    protected String bundle

The name of the servlet context attribute containing our message resources.

------------------------------------------------------------------------

<span id="disabled"></span>

### disabled

    protected boolean disabled

Is this option disabled?

------------------------------------------------------------------------

<span id="filter"></span>

### filter

    protected boolean filter

Should the label be filtered for HTML sensitive characters?

------------------------------------------------------------------------

<span id="key"></span>

### key

    protected String key

The key used to look up the text displayed to the user for this option, if any.

------------------------------------------------------------------------

<span id="locale"></span>

### locale

    protected String locale

The name of the attribute containing the Locale to be used for looking up internationalized messages.

------------------------------------------------------------------------

<span id="styleId"></span>

### styleId

    protected String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

<span id="value"></span>

### value

    protected String value

The server value for this option, also used to match against the current property value to determine whether this option should be marked as selected.

<span id="constructor_detail"></span>

**Constructor Detail**

### OptionTag

    public OptionTag()

<span id="method_detail"></span>

**Method Detail**

### getBundle

    public String getBundle()

------------------------------------------------------------------------

### setBundle

    public void setBundle(String bundle)

------------------------------------------------------------------------

### getDisabled

    public boolean getDisabled()

------------------------------------------------------------------------

### setDisabled

    public void setDisabled(boolean disabled)

------------------------------------------------------------------------

### getFilter

    public boolean getFilter()

------------------------------------------------------------------------

### setFilter

    public void setFilter(boolean filter)

------------------------------------------------------------------------

### getKey

    public String getKey()

------------------------------------------------------------------------

### setKey

    public void setKey(String key)

------------------------------------------------------------------------

### getLocale

    public String getLocale()

------------------------------------------------------------------------

### setLocale

    public void setLocale(String locale)

------------------------------------------------------------------------

### getStyle

    public String getStyle()

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

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

### getValue

    public String getValue()

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

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

Process the start of this tag.

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

Process the body text of this tag (if any).

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

Process the end of this tag.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### renderOptionElement

    protected String renderOptionElement()
                                  throws JspException

Generate an HTML %lt;option\> element.

**Throws:**  
`JspException`

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `BodyTagSupport`

------------------------------------------------------------------------

### text

    protected String text()
                   throws JspException

Return the text to be displayed to the user for this option (if any).

**Throws:**  
`JspException` - if an error occurs

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
<td align="left"><a href="class-use/OptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/OptionsTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/ParamTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/OptionTag.html"><strong>FRAMES</strong></a>    <a href="OptionTag.html"><strong>NO FRAMES</strong></a>    
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
