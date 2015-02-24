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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.bean**

<span id="org.apache.struts.taglib.bean.CookieTag"></span>

**Class [org.apache.struts.taglib.bean.CookieTag](org/apache/struts/taglib/bean/CookieTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of Cookies if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the cookie whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no cookie of the specified name is found.

<span id="org.apache.struts.taglib.bean.DefineTag"></span>

**Class [org.apache.struts.taglib.bean.DefineTag](org/apache/struts/taglib/bean/DefineTag.html.md "class in org.apache.struts.taglib.bean") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### body

    String body

The body content of this tag (if any).

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### name

    String name

The name of the bean owning the property to be exposed.

------------------------------------------------------------------------

### property

    String property

The name of the property to be retrieved.

------------------------------------------------------------------------

### scope

    String scope

The scope within which to search for the specified bean.

------------------------------------------------------------------------

### toScope

    String toScope

The scope within which the newly defined bean will be creatd.

------------------------------------------------------------------------

### type

    String type

The fully qualified Java class name of the value to be exposed.

------------------------------------------------------------------------

### value

    String value

The (String) value to which the defined bean will be set.

<span id="org.apache.struts.taglib.bean.HeaderTag"></span>

**Class [org.apache.struts.taglib.bean.HeaderTag](org/apache/struts/taglib/bean/HeaderTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of header values if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the header whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no header of the specified name is found.

<span id="org.apache.struts.taglib.bean.IncludeTag"></span>

**Class [org.apache.struts.taglib.bean.IncludeTag](org/apache/struts/taglib/bean/IncludeTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The name of the global `ActionForward` that contains a path to our requested resource.

------------------------------------------------------------------------

### href

    String href

The absolute URL to the resource to be included.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### page

    String page

The context-relative URI of the page or servlet to be included.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.bean.MessageTag"></span>

**Class [org.apache.struts.taglib.bean.MessageTag](org/apache/struts/taglib/bean/MessageTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### arg0

    String arg0

The first optional argument.

------------------------------------------------------------------------

### arg1

    String arg1

The second optional argument.

------------------------------------------------------------------------

### arg2

    String arg2

The third optional argument.

------------------------------------------------------------------------

### arg3

    String arg3

The fourth optional argument.

------------------------------------------------------------------------

### arg4

    String arg4

The fifth optional argument.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### key

    String key

The message key of the message to be retrieved.

------------------------------------------------------------------------

### name

    String name

Name of the bean that contains the message key.

------------------------------------------------------------------------

### property

    String property

Name of the property to be accessed on the specified bean.

------------------------------------------------------------------------

### scope

    String scope

The scope to be searched to retrieve the specified bean.

------------------------------------------------------------------------

### localeKey

    String localeKey

The session scope key under which our Locale is stored.

<span id="org.apache.struts.taglib.bean.PageTag"></span>

**Class [org.apache.struts.taglib.bean.PageTag](org/apache/struts/taglib/bean/PageTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### property

    String property

The name of the page context property to be retrieved.

<span id="org.apache.struts.taglib.bean.ParameterTag"></span>

**Class [org.apache.struts.taglib.bean.ParameterTag](org/apache/struts/taglib/bean/ParameterTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of parameter values if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the parameter whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no parameter of the specified name is found.

<span id="org.apache.struts.taglib.bean.ResourceTag"></span>

**Class [org.apache.struts.taglib.bean.ResourceTag](org/apache/struts/taglib/bean/ResourceTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### input

    String input

Return an InputStream to the specified resource if this is non-null.

------------------------------------------------------------------------

### name

    String name

The module-relative URI of the resource whose contents are to be exposed.

<span id="org.apache.struts.taglib.bean.SizeTag"></span>

**Class [org.apache.struts.taglib.bean.SizeTag](org/apache/struts/taglib/bean/SizeTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collection

    Object collection

The actual collection to be counted.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### name

    String name

The name of the bean owning the property to be counted.

------------------------------------------------------------------------

### property

    String property

The name of the property to be retrieved.

------------------------------------------------------------------------

### scope

    String scope

The scope within which to search for the specified bean.

<span id="org.apache.struts.taglib.bean.StrutsTag"></span>

**Class [org.apache.struts.taglib.bean.StrutsTag](org/apache/struts/taglib/bean/StrutsTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### formBean

    String formBean

The name of the `ActionFormBean` object to be exposed.

------------------------------------------------------------------------

### forward

    String forward

The name of the `ActionForward` object to be exposed.

------------------------------------------------------------------------

### mapping

    String mapping

The name of the `ActionMapping` object to be exposed.

<span id="org.apache.struts.taglib.bean.WriteTag"></span>

**Class [org.apache.struts.taglib.bean.WriteTag](org/apache/struts/taglib/bean/WriteTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

Filter the rendered output for characters that are sensitive in HTML?

------------------------------------------------------------------------

### ignore

    boolean ignore

Should we ignore missing beans and simply output nothing?

------------------------------------------------------------------------

### name

    String name

Name of the bean that contains the data we will be rendering.

------------------------------------------------------------------------

### property

    String property

Name of the property to be accessed on the specified bean.

------------------------------------------------------------------------

### scope

    String scope

The scope to be searched to retrieve the specified bean.

------------------------------------------------------------------------

### formatStr

    String formatStr

The format string to be used as format to convert value to String.

------------------------------------------------------------------------

### formatKey

    String formatKey

The key to search format string in applciation resources

------------------------------------------------------------------------

### localeKey

    String localeKey

The session scope key under which our Locale is stored.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.html.md**

<span id="org.apache.struts.taglib.html.md.BaseFieldTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") extends [BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accept

    String accept

Comma-delimited list of content types that a server processing this form will handle correctly. This property is defined only for the `file` tag, but is implemented here because it affects the rendered HTML of the corresponding \<input\> tag.

------------------------------------------------------------------------

### redisplay

    boolean redisplay

The "redisplay contents" flag (used only on `password`).

------------------------------------------------------------------------

### type

    String type

The type of input field represented by this tag (text, password, or hidden).

<span id="org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskey

    String accesskey

Access key character.

------------------------------------------------------------------------

### tabindex

    String tabindex

Tab index value.

------------------------------------------------------------------------

### indexed

    boolean indexed

Whether to created indexed names for fields

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### onclick

    String onclick

Mouse click event.

------------------------------------------------------------------------

### ondblclick

    String ondblclick

Mouse double click event.

------------------------------------------------------------------------

### onmouseover

    String onmouseover

Mouse over component event.

------------------------------------------------------------------------

### onmouseout

    String onmouseout

Mouse exit component event.

------------------------------------------------------------------------

### onmousemove

    String onmousemove

Mouse moved over component event.

------------------------------------------------------------------------

### onmousedown

    String onmousedown

Mouse pressed on component event.

------------------------------------------------------------------------

### onmouseup

    String onmouseup

Mouse released on component event.

------------------------------------------------------------------------

### onkeydown

    String onkeydown

Key down in component event.

------------------------------------------------------------------------

### onkeyup

    String onkeyup

Key released in component event.

------------------------------------------------------------------------

### onkeypress

    String onkeypress

Key down and up together in component event.

------------------------------------------------------------------------

### onselect

    String onselect

Text selected in component event.

------------------------------------------------------------------------

### onchange

    String onchange

Content changed after component lost focus event.

------------------------------------------------------------------------

### onblur

    String onblur

Component lost focus event.

------------------------------------------------------------------------

### onfocus

    String onfocus

Component has received focus event.

------------------------------------------------------------------------

### disabled

    boolean disabled

Component is disabled.

------------------------------------------------------------------------

### doDisabled

    boolean doDisabled

Indicates whether 'disabled' is a valid attribute

------------------------------------------------------------------------

### readonly

    boolean readonly

Component is readonly.

------------------------------------------------------------------------

### doReadonly

    boolean doReadonly

Indicates whether 'readonly' is a valid attribute.

According to the HTML 4.0 Specification \<readonly\> is valid for \<input type="text"\>, \<input type="password"\> and \<textarea"\> elements. Therefore, except for those tags this value is set to `false`.

------------------------------------------------------------------------

### style

    String style

Style attribute associated with component.

------------------------------------------------------------------------

### styleClass

    String styleClass

Named Style class associated with component.

------------------------------------------------------------------------

### styleId

    String styleId

Identifier associated with component.

------------------------------------------------------------------------

### errorKey

    String errorKey

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### errorStyle

    String errorStyle

Style attribute associated with component when errors exist.

------------------------------------------------------------------------

### errorStyleClass

    String errorStyleClass

Named Style class associated with component when errors exist.

------------------------------------------------------------------------

### errorStyleId

    String errorStyleId

Identifier associated with component when errors exist.

------------------------------------------------------------------------

### alt

    String alt

The alternate text of this element.

------------------------------------------------------------------------

### altKey

    String altKey

The message resources key of the alternate text.

------------------------------------------------------------------------

### bundle

    String bundle

The name of the message resources bundle for message lookups.

------------------------------------------------------------------------

### locale

    String locale

The name of the session attribute key for our locale.

------------------------------------------------------------------------

### title

    String title

The advisory title of this element.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

------------------------------------------------------------------------

### titleKey

    String titleKey

The message resources key of the advisory title.

------------------------------------------------------------------------

### loopTagClass

    Class<T> loopTagClass

------------------------------------------------------------------------

### loopTagGetStatus

    Method loopTagGetStatus

------------------------------------------------------------------------

### loopTagStatusClass

    Class<T> loopTagStatusClass

------------------------------------------------------------------------

### loopTagStatusGetIndex

    Method loopTagStatusGetIndex

------------------------------------------------------------------------

### triedJstlInit

    boolean triedJstlInit

------------------------------------------------------------------------

### triedJstlSuccess

    boolean triedJstlSuccess

<span id="org.apache.struts.taglib.html.md.BaseInputTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### autocomplete

    String autocomplete

Autocomplete non standard attribute

------------------------------------------------------------------------

### cols

    String cols

The number of character columns for this field, or negative for no limit.

------------------------------------------------------------------------

### maxlength

    String maxlength

The maximum number of characters allowed, or negative for no limit.

------------------------------------------------------------------------

### property

    String property

The name of the field (and associated property) being processed.

------------------------------------------------------------------------

### rows

    String rows

The number of rows for this field, or negative for no limit.

------------------------------------------------------------------------

### value

    String value

The value for this field, or `null` to retrieve the corresponding property from our associated bean.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

<span id="org.apache.struts.taglib.html.md.BaseTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseTag](org/apache/struts/taglib/html/BaseTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### REF\_SITE

    String REF_SITE

------------------------------------------------------------------------

### REF\_PAGE

    String REF_PAGE

------------------------------------------------------------------------

### server

    String server

The server name to use instead of request.getServerName().

------------------------------------------------------------------------

### target

    String target

The target window for this base reference.

------------------------------------------------------------------------

### ref

    String ref

The reference to which the base will created.

<span id="org.apache.struts.taglib.html.md.ButtonTag"></span>

**Class [org.apache.struts.taglib.html.md.ButtonTag](org/apache/struts/taglib/html/ButtonTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.CancelTag"></span>

**Class [org.apache.struts.taglib.html.md.CancelTag](org/apache/struts/taglib/html/CancelTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.CheckboxTag"></span>

**Class [org.apache.struts.taglib.html.md.CheckboxTag](org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The server value for this option.

<span id="org.apache.struts.taglib.html.md.ErrorsTag"></span>

**Class [org.apache.struts.taglib.html.md.ErrorsTag](org/apache/struts/taglib/html/ErrorsTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### locale

    String locale

The session attribute key for our locale.

------------------------------------------------------------------------

### name

    String name

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### property

    String property

The name of the property for which error messages should be returned, or `null` to return all errors.

------------------------------------------------------------------------

### header

    String header

The message resource key for errors header.

------------------------------------------------------------------------

### footer

    String footer

The message resource key for errors footer.

------------------------------------------------------------------------

### prefix

    String prefix

The message resource key for errors prefix.

------------------------------------------------------------------------

### suffix

    String suffix

The message resource key for errors suffix.

<span id="org.apache.struts.taglib.html.md.FileTag"></span>

**Class [org.apache.struts.taglib.html.md.FileTag](org/apache/struts/taglib/html/FileTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.FormTag"></span>

**Class [org.apache.struts.taglib.html.md.FormTag](org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### action

    String action

The action URL to which this form should be submitted, if any.

------------------------------------------------------------------------

### autocomplete

    String autocomplete

Autocomplete non standard attribute

------------------------------------------------------------------------

### postbackAction

    String postbackAction

A postback action URL to which this form should be submitted, if any.

------------------------------------------------------------------------

### moduleConfig

    ModuleConfig moduleConfig

The module configuration for our module.

------------------------------------------------------------------------

### enctype

    String enctype

The content encoding to be used on a POST submit.

------------------------------------------------------------------------

### focus

    String focus

The name of the field to receive focus, if any.

------------------------------------------------------------------------

### focusIndex

    String focusIndex

The index in the focus field array to receive focus. This only applies if the field given in the focus attribute is actually an array of fields. This allows a specific field in a radio button array to receive focus while still allowing indexed field names like "myRadioButtonField[1]" to be passed in the focus attribute.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### mapping

    ActionMapping mapping

The ActionMapping defining where we will be submitting this form

------------------------------------------------------------------------

### method

    String method

The request method used when submitting this form.

------------------------------------------------------------------------

### onreset

    String onreset

The onReset event script.

------------------------------------------------------------------------

### onsubmit

    String onsubmit

The onSubmit event script.

------------------------------------------------------------------------

### scriptLanguage

    boolean scriptLanguage

Include language attribute in the focus script's \<script\> element. This property is ignored in XHTML mode.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### servlet

    ActionServlet servlet

The ActionServlet instance we are associated with (so that we can initialize the `servlet` property on any form bean that we create).

------------------------------------------------------------------------

### style

    String style

The style attribute associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The style class associated with this tag.

------------------------------------------------------------------------

### styleId

    String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

### target

    String target

The window target.

------------------------------------------------------------------------

### beanName

    String beanName

The name of the form bean to (create and) use. This is either the same as the 'name' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### beanScope

    String beanScope

The scope of the form bean to (create and) use. This is either the same as the 'scope' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### beanType

    String beanType

The type of the form bean to (create and) use. This is either the same as the 'type' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### acceptCharset

    String acceptCharset

The list of character encodings for input data that the server should accept.

------------------------------------------------------------------------

### disabled

    boolean disabled

Controls whether child controls should be 'disabled'.

------------------------------------------------------------------------

### readonly

    boolean readonly

Controls whether child controls should be 'readonly'.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

<span id="org.apache.struts.taglib.html.md.FrameTag"></span>

**Class [org.apache.struts.taglib.html.md.FrameTag](org/apache/struts/taglib/html/FrameTag.html "class in org.apache.struts.taglib.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### frameborder

    String frameborder

The frameborder attribute that should be rendered (1, 0).

------------------------------------------------------------------------

### frameName

    String frameName

The `name` attribute that should be rendered for this frame.

------------------------------------------------------------------------

### longdesc

    String longdesc

URI of a long description of this frame (complements title).

------------------------------------------------------------------------

### marginheight

    Integer marginheight

The margin height in pixels, or zero for no setting.

------------------------------------------------------------------------

### marginwidth

    Integer marginwidth

The margin width in pixels, or null for no setting.

------------------------------------------------------------------------

### noresize

    boolean noresize

Should users be disallowed to resize the frame?

------------------------------------------------------------------------

### scrolling

    String scrolling

What type of scrolling should be supported (yes, no, auto)?

<span id="org.apache.struts.taglib.html.md.HiddenTag"></span>

**Class [org.apache.struts.taglib.html.md.HiddenTag](org/apache/struts/taglib/html/HiddenTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### write

    boolean write

Should the value of this field also be rendered to the response?

<span id="org.apache.struts.taglib.html.md.HtmlTag"></span>

**Class [org.apache.struts.taglib.html.md.HtmlTag](org/apache/struts/taglib/html/HtmlTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### .html.md

    boolean .html.md

Are we rendering an .html.md page?

------------------------------------------------------------------------

### lang

    boolean lang

Are we rendering a lang attribute?

**Since:**  
Struts 1.2

<span id="org.apache.struts.taglib.html.md.ImageTag"></span>

**Class [org.apache.struts.taglib.html.md.ImageTag](org/apache/struts/taglib/html/ImageTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### align

    String align

The alignment for this image.

------------------------------------------------------------------------

### border

    String border

The border size around the image.

------------------------------------------------------------------------

### page

    String page

The module-relative URI of the image.

------------------------------------------------------------------------

### pageKey

    String pageKey

The message resources key of the module-relative URI of the image.

------------------------------------------------------------------------

### src

    String src

The URL of this image.

------------------------------------------------------------------------

### srcKey

    String srcKey

The message resources key for the URL of this image.

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

<span id="org.apache.struts.taglib.html.md.ImgTag"></span>

**Class [org.apache.struts.taglib.html.md.ImgTag](org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### align

    String align

The property to specify where to align the image.

------------------------------------------------------------------------

### border

    String border

The border size around the image.

------------------------------------------------------------------------

### height

    String height

The image height.

------------------------------------------------------------------------

### hspace

    String hspace

The horizontal spacing around the image.

------------------------------------------------------------------------

### imageName

    String imageName

The image name for named images.

------------------------------------------------------------------------

### ismap

    String ismap

Server-side image map declaration.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative path, starting with a slash character, of the image to be displayed by this rendered tag.

------------------------------------------------------------------------

### pageKey

    String pageKey

The message resources key under which we should look up the `page` attribute for this generated tag, if any.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be used as the source for this image.

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

In situations where an image is dynamically generated (such as to create a chart graph), this specifies the single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### src

    String src

The image source URI.

------------------------------------------------------------------------

### srcKey

    String srcKey

The message resources key under which we should look up the `src` attribute for this generated tag, if any.

------------------------------------------------------------------------

### usemap

    String usemap

Client-side image map declaration.

------------------------------------------------------------------------

### vspace

    String vspace

The vertical spacing around the image.

------------------------------------------------------------------------

### width

    String width

The image width.

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.html.md.JavascriptValidatorTag"></span>

**Class [org.apache.struts.taglib.html.md.JavascriptValidatorTag](org/apache/struts/taglib/html/JavascriptValidatorTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### formName

    String formName

The name of the form that corresponds with the action name in struts-config.xml. Specifying a form name places a \<script\> \</script\> around the javascript.

------------------------------------------------------------------------

### jsFormName

    String jsFormName

formName is used for both Javascript and non-javascript validations. For the javascript validations, there is the possibility that we will be rewriting the formName (if it is a ValidatorActionForm instead of just a ValidatorForm) so we need another variable to hold the formName just for javascript usage.

------------------------------------------------------------------------

### page

    int page

The current page number of a multi-part form. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### methodName

    String methodName

This will be used as is for the JavaScript validation method name if it has a value. This is the method name of the main JavaScript method that the form calls to perform validations.

------------------------------------------------------------------------

### scriptLanguage

    boolean scriptLanguage

Include language attribute in the \<script\> element. This property is ignored in XHTML mode.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### staticJavascript

    String staticJavascript

The static JavaScript methods will only be printed if this is set to "true".

------------------------------------------------------------------------

### dynamicJavascript

    String dynamicJavascript

The dynamic JavaScript objects will only be generated if this is set to "true".

------------------------------------------------------------------------

### src

    String src

The src attribute for.html.md script element (used to include an external script resource). The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

###.html.mdComment

    String.html.mdComment

The JavaScript methods will enclosed with.html.md comments if this is set to "true".

------------------------------------------------------------------------

### cdata

    String cdata

Hide JavaScript methods in a CDATA section for XHTML when "true".

<span id="org.apache.struts.taglib.html.md.LinkTag"></span>

**Class [org.apache.struts.taglib.html.md.LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The logical forward name from which to retrieve the hyperlink URI.

Usage note: If a forward config is used in a hyperlink, and a module is specified, the path must lead to another action and not directly to a page. This is in keeping with rule that in a modular application all links must be to an action rather than a page.

------------------------------------------------------------------------

### href

    String href

The hyperlink URI.

------------------------------------------------------------------------

### linkName

    String linkName

The link name for named links.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative page URL (beginning with a slash) to which this hyperlink will be rendered.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

The single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### target

    String target

The window target.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

### parameters

    Map<K,V> parameters

Additional parameters included programatically.

------------------------------------------------------------------------

### indexId

    String indexId

Name of parameter to generate to hold index number

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.html.md.MessagesTag"></span>

**Class [org.apache.struts.taglib.html.md.MessagesTag](org/apache/struts/taglib/html/MessagesTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### iterator

    Iterator<E> iterator

Iterator of the elements of this error collection, while we are actually running.

------------------------------------------------------------------------

### processed

    boolean processed

Whether or not any error messages have been processed.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### locale

    String locale

The session attribute key for our locale.

------------------------------------------------------------------------

### name

    String name

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### property

    String property

The name of the property for which error messages should be returned, or `null` to return all errors.

------------------------------------------------------------------------

### header

    String header

The message resource key for errors header.

------------------------------------------------------------------------

### footer

    String footer

The message resource key for errors footer.

------------------------------------------------------------------------

### message

    String message

If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

<span id="org.apache.struts.taglib.html.md.MultiboxTag"></span>

**Class [org.apache.struts.taglib.html.md.MultiboxTag](org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### constant

    String constant

The constant String value to be returned when this checkbox is selected and the form is submitted.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### value

    String value

The value which will mark this checkbox as "checked" if present in the array returned by our property getter.

<span id="org.apache.struts.taglib.html.md.OptionsCollectionTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionsCollectionTag](org/apache/struts/taglib/html/OptionsCollectionTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

Should the label values be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### label

    String label

The name of the bean property containing the label.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing the values collection.

------------------------------------------------------------------------

### property

    String property

The name of the property to use to build the values collection.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

------------------------------------------------------------------------

### value

    String value

The name of the bean property containing the value.

<span id="org.apache.struts.taglib.html.md.OptionsTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionsTag](org/apache/struts/taglib/html/OptionsTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collection

    String collection

The name of the collection containing beans that have properties to provide both the values and the labels (identified by the `property` and `labelProperty` attributes).

------------------------------------------------------------------------

### filter

    boolean filter

Should the label values be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### labelName

    String labelName

The name of the bean containing the labels collection.

------------------------------------------------------------------------

### labelProperty

    String labelProperty

The bean property containing the labels collection.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing the values collection.

------------------------------------------------------------------------

### property

    String property

The name of the property to use to build the values collection.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

<span id="org.apache.struts.taglib.html.md.OptionTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionTag](org/apache/struts/taglib/html/OptionTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### text

    String text

The message text to be displayed to the user for this tag (if any)

------------------------------------------------------------------------

### bundle

    String bundle

The name of the servlet context attribute containing our message resources.

------------------------------------------------------------------------

### disabled

    boolean disabled

Is this option disabled?

------------------------------------------------------------------------

### filter

    boolean filter

Should the label be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### key

    String key

The key used to look up the text displayed to the user for this option, if any.

------------------------------------------------------------------------

### locale

    String locale

The name of the attribute containing the Locale to be used for looking up internationalized messages.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

------------------------------------------------------------------------

### styleId

    String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

------------------------------------------------------------------------

### value

    String value

The server value for this option, also used to match against the current property value to determine whether this option should be marked as selected.

<span id="org.apache.struts.taglib.html.md.ParamTag"></span>

**Class [org.apache.struts.taglib.html.md.ParamTag](org/apache/struts/taglib/html/ParamTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the query parameter.

------------------------------------------------------------------------

### value

    String value

The value of the query parameter or body content of this tag (if any).

<span id="org.apache.struts.taglib.html.md.PasswordTag"></span>

**Class [org.apache.struts.taglib.html.md.PasswordTag](org/apache/struts/taglib/html/PasswordTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.RadioTag"></span>

**Class [org.apache.struts.taglib.html.md.RadioTag](org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The server value for this option.

------------------------------------------------------------------------

### idName

    String idName

Name of the bean (in some scope) that will return the value of the radio tag.

If an iterator is used to render a series of radio tags, this field may be used to specify the name of the bean exposed by the iterator. In this case, the value attribute is used as the name of a property on the `idName` bean that returns the value of the radio tag in this iteration.

<span id="org.apache.struts.taglib.html.md.ResetTag"></span>

**Class [org.apache.struts.taglib.html.md.ResetTag](org/apache/struts/taglib/html/ResetTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.RewriteTag"></span>

**Class [org.apache.struts.taglib.html.md.RewriteTag](org/apache/struts/taglib/html/RewriteTag.html "class in org.apache.struts.taglib.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.SelectTag"></span>

**Class [org.apache.struts.taglib.html.md.SelectTag](org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### match

    String[] match

The actual values we will match against, calculated in doStartTag().

------------------------------------------------------------------------

### multiple

    String multiple

Should multiple selections be allowed. Any non-null value will trigger rendering this.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name we are associated with.

------------------------------------------------------------------------

### saveBody

    String saveBody

The saved body content of this tag.

------------------------------------------------------------------------

### size

    String size

How many available options should be displayed when this element is rendered?

------------------------------------------------------------------------

### value

    String value

The value to compare with for marking an option selected.

<span id="org.apache.struts.taglib.html.md.SubmitTag"></span>

**Class [org.apache.struts.taglib.html.md.SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

The name of the generated input field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The value of the button label.

<span id="org.apache.struts.taglib.html.md.TextareaTag"></span>

**Class [org.apache.struts.taglib.html.md.TextareaTag](org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html") extends [BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.TextTag"></span>

**Class [org.apache.struts.taglib.html.md.TextTag](org/apache/struts/taglib/html/TextTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.XhtmlTag"></span>

**Class [org.apache.struts.taglib.html.md.XhtmlTag](org/apache/struts/taglib/html/XhtmlTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.logic**

<span id="org.apache.struts.taglib.logic.CompareTagBase"></span>

**Class [org.apache.struts.taglib.logic.CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### value

    String value

The value to which the variable specified by other attributes of this tag will be compared.

<span id="org.apache.struts.taglib.logic.ConditionalTagBase"></span>

**Class [org.apache.struts.taglib.logic.ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookie

    String cookie

The name of the cookie to be used as a variable.

------------------------------------------------------------------------

### header

    String header

The name of the HTTP request header to be used as a variable.

------------------------------------------------------------------------

### name

    String name

The name of the JSP bean to be used as a variable (if `property` is not specified), or whose property is to be accessed (if `property` is specified).

------------------------------------------------------------------------

### parameter

    String parameter

The name of the HTTP request parameter to be used as a variable.

------------------------------------------------------------------------

### property

    String property

The name of the bean property to be used as a variable.

------------------------------------------------------------------------

### role

    String role

The name of the security role to be checked for.

------------------------------------------------------------------------

### scope

    String scope

The scope to search for the bean named by the name property, or "any scope" if null.

------------------------------------------------------------------------

### user

    String user

The user principal name to be checked for.

<span id="org.apache.struts.taglib.logic.EmptyTag"></span>

**Class [org.apache.struts.taglib.logic.EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.EqualTag"></span>

**Class [org.apache.struts.taglib.logic.EqualTag](org/apache/struts/taglib/logic/EqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.ForwardTag"></span>

**Class [org.apache.struts.taglib.logic.ForwardTag](org/apache/struts/taglib/logic/ForwardTag.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The logical name of the `ActionForward` entry to be looked up.

<span id="org.apache.struts.taglib.logic.GreaterEqualTag"></span>

**Class [org.apache.struts.taglib.logic.GreaterEqualTag](org/apache/struts/taglib/logic/GreaterEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.GreaterThanTag"></span>

**Class [org.apache.struts.taglib.logic.GreaterThanTag](org/apache/struts/taglib/logic/GreaterThanTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.IterateTag"></span>

**Class [org.apache.struts.taglib.logic.IterateTag](org/apache/struts/taglib/logic/IterateTag.html.md "class in org.apache.struts.taglib.logic") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### iterator

    Iterator<E> iterator

Iterator of the elements of this collection, while we are actually running.

------------------------------------------------------------------------

### lengthCount

    int lengthCount

The number of elements we have already rendered.

------------------------------------------------------------------------

### lengthValue

    int lengthValue

The actual length value (calculated in the start tag).

------------------------------------------------------------------------

### offsetValue

    int offsetValue

The actual offset value (calculated in the start tag).

------------------------------------------------------------------------

### started

    boolean started

Has this tag instance been started?

------------------------------------------------------------------------

### collection

    Object collection

The collection over which we will be iterating.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

### indexId

    String indexId

The name of the scripting variable to be exposed as the current index.

------------------------------------------------------------------------

### length

    String length

The length value or attribute name (\<=0 means no limit).

------------------------------------------------------------------------

### name

    String name

The name of the collection or owning bean.

------------------------------------------------------------------------

### offset

    String offset

The starting offset (zero relative).

------------------------------------------------------------------------

### property

    String property

The property name containing the collection.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### type

    String type

The Java class of each exposed element of the collection.

<span id="org.apache.struts.taglib.logic.LessEqualTag"></span>

**Class [org.apache.struts.taglib.logic.LessEqualTag](org/apache/struts/taglib/logic/LessEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.LessThanTag"></span>

**Class [org.apache.struts.taglib.logic.LessThanTag](org/apache/struts/taglib/logic/LessThanTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.MatchTag"></span>

**Class [org.apache.struts.taglib.logic.MatchTag](org/apache/struts/taglib/logic/MatchTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### location

    String location

The location where the match must exist (`start` or `end`), or `null` for anywhere.

------------------------------------------------------------------------

### value

    String value

The value to which the variable specified by other attributes of this tag will be matched.

<span id="org.apache.struts.taglib.logic.MessagesNotPresentTag"></span>

**Class [org.apache.struts.taglib.logic.MessagesNotPresentTag](org/apache/struts/taglib/logic/MessagesNotPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.MessagesPresentTag"></span>

**Class [org.apache.struts.taglib.logic.MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### message

    String message

If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

<span id="org.apache.struts.taglib.logic.NotEmptyTag"></span>

**Class [org.apache.struts.taglib.logic.NotEmptyTag](org/apache/struts/taglib/logic/NotEmptyTag.html.md "class in org.apache.struts.taglib.logic") extends [EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotEqualTag"></span>

**Class [org.apache.struts.taglib.logic.NotEqualTag](org/apache/struts/taglib/logic/NotEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotMatchTag"></span>

**Class [org.apache.struts.taglib.logic.NotMatchTag](org/apache/struts/taglib/logic/NotMatchTag.html.md "class in org.apache.struts.taglib.logic") extends [MatchTag](org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotPresentTag"></span>

**Class [org.apache.struts.taglib.logic.NotPresentTag](org/apache/struts/taglib/logic/NotPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [PresentTag](org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.PresentTag"></span>

**Class [org.apache.struts.taglib.logic.PresentTag](org/apache/struts/taglib/logic/PresentTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.RedirectTag"></span>

**Class [org.apache.struts.taglib.logic.RedirectTag](org/apache/struts/taglib/logic/RedirectTag.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The logical forward name from which to retrieve the redirect URI.

------------------------------------------------------------------------

### href

    String href

The redirect URI.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative page URL (beginning with a slash) to which this redirect will be rendered.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

The single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include our transaction control token?

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

Use character encoding from ServletResponse\#getCharacterEncoding to get bytes of the url string for urlencoding?

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested**

<span id="org.apache.struts.taglib.nested.NestedPropertyTag"></span>

**Class [org.apache.struts.taglib.nested.NestedPropertyTag](org/apache/struts/taglib/nested/NestedPropertyTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

------------------------------------------------------------------------

### originalNest

    String originalNest

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.NestedReference"></span>

**Class [org.apache.struts.taglib.nested.NestedReference](org/apache/struts/taglib/nested/NestedReference.html.md "class in org.apache.struts.taglib.nested") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### beanName

    String beanName

------------------------------------------------------------------------

### property

    String property

<span id="org.apache.struts.taglib.nested.NestedRootTag"></span>

**Class [org.apache.struts.taglib.nested.NestedRootTag](org/apache/struts/taglib/nested/NestedRootTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.NestedWriteNestingTag"></span>

**Class [org.apache.struts.taglib.nested.NestedWriteNestingTag](org/apache/struts/taglib/nested/NestedWriteNestingTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

------------------------------------------------------------------------

### property

    String property

------------------------------------------------------------------------

### id

    String id

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.bean**

<span id="org.apache.struts.taglib.nested.bean.NestedDefineTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedDefineTag](org/apache/struts/taglib/nested/bean/NestedDefineTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [DefineTag](org/apache/struts/taglib/bean/DefineTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedMessageTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedMessageTag](org/apache/struts/taglib/nested/bean/NestedMessageTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [MessageTag](org/apache/struts/taglib/bean/MessageTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedSizeTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedSizeTag](org/apache/struts/taglib/nested/bean/NestedSizeTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [SizeTag](org/apache/struts/taglib/bean/SizeTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedWriteTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedWriteTag](org/apache/struts/taglib/nested/bean/NestedWriteTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [WriteTag](org/apache/struts/taglib/bean/WriteTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.html.md**

<span id="org.apache.struts.taglib.nested.html.md.NestedCheckboxTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedCheckboxTag](org/apache/struts/taglib/nested/html/NestedCheckboxTag.html "class in org.apache.struts.taglib.nested.html") extends [CheckboxTag](org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedErrorsTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedErrorsTag](org/apache/struts/taglib/nested/html/NestedErrorsTag.html "class in org.apache.struts.taglib.nested.html") extends [ErrorsTag](org/apache/struts/taglib/html/ErrorsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedFileTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedFileTag](org/apache/struts/taglib/nested/html/NestedFileTag.html "class in org.apache.struts.taglib.nested.html") extends [FileTag](org/apache/struts/taglib/html/FileTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedFormTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedFormTag](org/apache/struts/taglib/nested/html/NestedFormTag.html "class in org.apache.struts.taglib.nested.html") extends [FormTag](org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.html.md.NestedHiddenTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedHiddenTag](org/apache/struts/taglib/nested/html/NestedHiddenTag.html "class in org.apache.struts.taglib.nested.html") extends [HiddenTag](org/apache/struts/taglib/html/HiddenTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedImageTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedImageTag](org/apache/struts/taglib/nested/html/NestedImageTag.html "class in org.apache.struts.taglib.nested.html") extends [ImageTag](org/apache/struts/taglib/html/ImageTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedImgTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedImgTag](org/apache/struts/taglib/nested/html/NestedImgTag.html "class in org.apache.struts.taglib.nested.html") extends [ImgTag](org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedLinkTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedLinkTag](org/apache/struts/taglib/nested/html/NestedLinkTag.html "class in org.apache.struts.taglib.nested.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### origName

    String origName

------------------------------------------------------------------------

### origProperty

    String origProperty

------------------------------------------------------------------------

### origParamProperty

    String origParamProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedMessagesTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedMessagesTag](org/apache/struts/taglib/nested/html/NestedMessagesTag.html "class in org.apache.struts.taglib.nested.html") extends [MessagesTag](org/apache/struts/taglib/html/MessagesTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedMultiboxTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedMultiboxTag](org/apache/struts/taglib/nested/html/NestedMultiboxTag.html "class in org.apache.struts.taglib.nested.html") extends [MultiboxTag](org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedOptionsCollectionTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedOptionsCollectionTag](org/apache/struts/taglib/nested/html/NestedOptionsCollectionTag.html "class in org.apache.struts.taglib.nested.html") extends [OptionsCollectionTag](org/apache/struts/taglib/html/OptionsCollectionTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedOptionsTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedOptionsTag](org/apache/struts/taglib/nested/html/NestedOptionsTag.html "class in org.apache.struts.taglib.nested.html") extends [OptionsTag](org/apache/struts/taglib/html/OptionsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

### originalLabelProperty

    String originalLabelProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedPasswordTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedPasswordTag](org/apache/struts/taglib/nested/html/NestedPasswordTag.html "class in org.apache.struts.taglib.nested.html") extends [PasswordTag](org/apache/struts/taglib/html/PasswordTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedRadioTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedRadioTag](org/apache/struts/taglib/nested/html/NestedRadioTag.html "class in org.apache.struts.taglib.nested.html") extends [RadioTag](org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedSelectTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedSelectTag](org/apache/struts/taglib/nested/html/NestedSelectTag.html "class in org.apache.struts.taglib.nested.html") extends [SelectTag](org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedSubmitTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedSubmitTag](org/apache/struts/taglib/nested/html/NestedSubmitTag.html "class in org.apache.struts.taglib.nested.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedTextareaTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedTextareaTag](org/apache/struts/taglib/nested/html/NestedTextareaTag.html "class in org.apache.struts.taglib.nested.html") extends [TextareaTag](org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedTextTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedTextTag](org/apache/struts/taglib/nested/html/NestedTextTag.html "class in org.apache.struts.taglib.nested.html") extends [TextTag](org/apache/struts/taglib/html/TextTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.logic**

<span id="org.apache.struts.taglib.nested.logic.NestedEmptyTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedEmptyTag](org/apache/struts/taglib/nested/logic/NestedEmptyTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedEqualTag](org/apache/struts/taglib/nested/logic/NestedEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [EqualTag](org/apache/struts/taglib/logic/EqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedGreaterEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedGreaterEqualTag](org/apache/struts/taglib/nested/logic/NestedGreaterEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [GreaterEqualTag](org/apache/struts/taglib/logic/GreaterEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedGreaterThanTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedGreaterThanTag](org/apache/struts/taglib/nested/logic/NestedGreaterThanTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [GreaterThanTag](org/apache/struts/taglib/logic/GreaterThanTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedIterateTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedIterateTag](org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [IterateTag](org/apache/struts/taglib/logic/IterateTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nesting

    String nesting

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.logic.NestedLessEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedLessEqualTag](org/apache/struts/taglib/nested/logic/NestedLessEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [LessEqualTag](org/apache/struts/taglib/logic/LessEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedLessThanTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedLessThanTag](org/apache/struts/taglib/nested/logic/NestedLessThanTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [LessThanTag](org/apache/struts/taglib/logic/LessThanTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMatchTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMatchTag](org/apache/struts/taglib/nested/logic/NestedMatchTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MatchTag](org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMessagesNotPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMessagesNotPresentTag](org/apache/struts/taglib/nested/logic/NestedMessagesNotPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MessagesNotPresentTag](org/apache/struts/taglib/logic/MessagesNotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMessagesPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMessagesPresentTag](org/apache/struts/taglib/nested/logic/NestedMessagesPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotEmptyTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotEmptyTag](org/apache/struts/taglib/nested/logic/NestedNotEmptyTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotEmptyTag](org/apache/struts/taglib/logic/NotEmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotEqualTag](org/apache/struts/taglib/nested/logic/NestedNotEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotEqualTag](org/apache/struts/taglib/logic/NotEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotMatchTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotMatchTag](org/apache/struts/taglib/nested/logic/NestedNotMatchTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotMatchTag](org/apache/struts/taglib/logic/NotMatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotPresentTag](org/apache/struts/taglib/nested/logic/NestedNotPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotPresentTag](org/apache/struts/taglib/logic/NotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedPresentTag](org/apache/struts/taglib/nested/logic/NestedPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [PresentTag](org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
