<span id="navbar_top"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
----

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix=.html.md" uri="http://struts.apache.org/tags-html" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns.html.md="http://struts.apache.org/tags-html" />`

------------------------------------------------------------------------


     This taglib contains tags used to create struts input forms, as well as other tags generally useful in the creation of HTML-based user interfaces.  
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

html

URI

http://struts.apache.org/tags.html.md

 

**Tag Summary**

**[base](base.html.md)**

**Render an HTML `<base>` Element**

Renders an HTML `<base>` element with an `href` attribute pointing to the absolute location of the enclosing JSP page. This tag is valid only when nested inside an HTML `<head>` element.

This tag is useful because it allows you to use relative URL references in the page that are calculated based on the URL of the page itself, rather than the URL to which the most recent submit took place (which is where the browser would normally resolve relative references against).

**[button](button.html.md)**

**Render A Button Input Field**

Renders an HTML \<input\> element of type `button`, populated from the specified value or the content of this tag body. This tag is only valid when nested inside a form tag body.

If a graphical button is needed (a button with an image), then the `.html.md:image>` tag is more appropriate.

**[cancel](cancel.html.md)**

**Render a Cancel Button**

Renders an HTML \<input\> element of type submit. This tag is only valid when nested inside a form tag body. Pressing of this submit button causes the action servlet to bypass calling the associated form bean validate() method. The action is called normally.

**[checkbox](checkbox.html.md)**

**Render A Checkbox Input Field**

Renders an HTML \<input\> element of type `checkbox`, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

**NOTE**: The underlying property value associated with this field should be of type `boolean`, and any `value` you specify should correspond to one of the Strings that indicate a true value ("true", "yes", or "on"). If you wish to utilize a set of related String values, consider using the `multibox` tag.

**WARNING**: In order to correctly recognize unchecked checkboxes, the `ActionForm` bean associated with this form must include a statement setting the corresponding boolean property to `false` in the `reset()` method.

**[errors](errors.html.md)**

**Conditionally display a set of accumulated error messages.**

Displays a set of error messages prepared by a business logic component and stored as an `ActionMessages` object, an `ActionErrors` object, a String, or a String array in any scope. If such a bean is not found, nothing will be rendered.

In order to use this tag successfully, you must have defined an application scope `MessageResources` bean under the default attribute name, with optional definitions of message keys specified in the following attributes:

-   **header** - Text that will be rendered before the error messages list. Typically, this message text will end with `<ul>` to start the error messages list (default "errors.header").
-   **footer** - Text that will be rendered after the error messages list. Typically, this message text will begin with `</ul>` to end the error messages list (default "errors.footer").
-   **prefix** - Text that will be rendered before each individual error in the list (default "errors.prefix").
-   **suffix** - Text that will be rendered after each individual error in the list (default "errors.suffix").

See the `messages` tag for an alternative to this tag that does not rely on HTML in your `MessageResources`.

**[file](file.html.md)**

**Render A File Select Input Field**

Renders an HTML \<input\> element of type file, defaulting to the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

As with the corresponding HTML \<input\> element, the enclosing form element must specify "POST" for the `method` attribute, and "multipart/form-data" for the `enctype` attribute. For example:

     .html.md:form method="POST" enctype="multipart/form-data"> <html:file property="theFile" /> </html:form>

WARNING: In order to correctly recognize uploaded files, the ActionForm bean associated with this form must include a statement setting the corresponding org.apache.struts.upload.FormFile property to null in the reset() method.

**[form](form.html.md)**

**Define An Input Form**

Renders an HTML \<form\> element whose contents are described by the body content of this tag. The form implicitly interacts with the specified request scope or session scope bean to populate the input fields with the current property values from the bean.

The form bean is located, and created if necessary, based on the form bean specification for the associated `ActionMapping`.

**[frame](frame.html.md)**

**Render an HTML frame element**

Renders an HTML `<frame>` element with processing for the `src` attribute that is identical to that performed by the `.html.md:link>` tag for the `href` attribute. URL rewriting will be applied automatically, to maintain session state in the absence of cookies.

The base URL for this frame is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as a module-relative URI, and generate a server-relative URI by including the context path and application prefix.
-   *action* - Use the value of this attribute as the logical name of a global Action that contains the actual content-relative URI of the destination of this transfer.

Normally, the hyperlink you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

Additionally, you can request that the current transaction control token, if any, be included in the generated hyperlink by setting the `transaction` attribute to `true`. You can also request that an anchor ("\#xxx") be added to the end of the URL that is created by any of the above mechanisms, by using the `anchor` attribute.

**[hidden](hidden.html.md)**

**Render A Hidden Field**

Renders an HTML \<input\> element of type hidden, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

**.html.md](html.html)**

**Render an HTML `.html.md>` Element**

Renders an HTML `.html.md>` element with language attributes extracted from the user's current Locale object, if there is one.

**[image](image.html.md)**

**Render an input tag of type "image"**

Renders an HTML `<input>` tag of type "image". The base URL for this image is calculated directly based on the value specified in the `src` or `page` attributes, or indirectly by looking up a message resource string based on the `srcKey` or `pageKey` attributes. You **must** specify exactly one of these attributes.

If you would like to obtain the coordinates of the mouse click that submitted this request, see the information below on the `property` attribute.

This tag is only valid when nested inside a form tag body.

**[img](img.html.md)**

**Render an HTML img tag**

Renders an HTML `<img>` element with the image at the specified URL. Like the link tag, URL rewriting will be applied automatically to the value specified in `src`, `page`, or `action` to maintain session state in the absence of cookies. This will allow dynamic generation of an image where the content displayed for this image will be taken from the attributes of this tag.

The base URL for this image is calculated directly based on the value specified in `src`, `page`, or `action` or `page`, or indirectly by looking up a message resource string based on the `srcKey` or `pageKey` attributes. You **must** specify exactly one of these attributes.

Normally, the `src`, `page`, or `action` that you specify will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the `src` URL -- specify a single parameter with the `paramId` attribute (at its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the `src` URL. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

You can specify the alternate text for this image (which most browsers display as pop-up text block when the user hovers the mouse over this image) either directly, through the `alt` attribute, or indirectly from a message resources bundle, using the `bundle` and `altKey` attributes.

**[javascript](javascript.html.md)**

**Render JavaScript validation based on the validation rules loaded by the ValidatorPlugIn.**

Render JavaScript validation based on the validation rules loaded by the `ValidatorPlugIn`. The set of validation rules that should be generated is based on the formName attribute passed in, which should match the name attribute of the form element in the xml file.

The dynamicJavascript and staticJavascript attributes default to true, but if dynamicJavascript is set to `true` and staticJavascript is set to `false` then only the dynamic JavaScript will be rendered. If dynamicJavascript is set to `false` and staticJavascript is set to `true` then only the static JavaScript will be rendered which can then be put in separate JSP page so the browser can cache the static JavaScript.

**[link](link.html.md)**

**Render an HTML anchor or hyperlink**

Renders an HTML `<a>` element as an anchor definition (if "linkName" is specified) or as a hyperlink to the specified URL. URL rewriting will be applied automatically, to maintain session state in the absence of cookies. The content displayed for this hyperlink will be taken from the body of this tag.

The base URL for this hyperlink is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there. If the forward is module-relative then it must point to an action and NOT to a page.
-   *action* - Use the value of this attribute as the name of a `Action` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as a module-relative URI, and generate a server-relative URI by including the context path and module prefix.

Normally, the hyperlink you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are three ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values, or nest one or more \.html.md:param\> tags in the tag body.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

Supplmenting these two methods, you can nest one or more \.html.md:param\> tags to dynamically add parameters in a logic-friendly way (such as executing a for loop that assigns the name/value pairs at runtime). This method does not compete with the aforementioned; it will adds its parameters *in addition* to whatever parameters are already specified.

Additionally, you can request that the current transaction control token, if any, be included in the generated hyperlink by setting the `transaction` attribute to `true`. You can also request that an anchor ("\#xxx") be added to the end of the URL that is created by any of the above mechanisms, by using the `anchor` attribute.

**[param](param.html.md)**

Adds a parameter to the following tags:

1.  \.html.md:frame\>
2.  \.html.md:link\>
3.  \.html.md:rewrite\>

**Since:**  
Struts 1.3.6

**[messages](messages.html.md)**

**Conditionally display a set of accumulated messages.**

Displays a set of messages prepared by a business logic component and stored as an `ActionMessages` object, `ActionErrors` object, a String, or a String array in any scope. If such a bean is not found, nothing will be rendered. The messages are placed into the page scope in the body of this tag where they can be displayed by standard JSP methods. (For example: `<bean:write>`,`<c:out>`)

In order to use this tag successfully, you must have defined an application scope `MessageResources` bean under the default attribute name.

**[multibox](multibox.html.md)**

**Render A Checkbox Input Field**

Renders an HTML \<input\> element of type `checkbox`, whose "checked" status is initialized based on whether the specified value matches one of the elements of the underlying property's array of current values. This element is useful when you have large numbers of checkboxes, and prefer to combine the values into a single array-valued property instead of multiple boolean properties. This tag is only valid when nested inside a form tag body.

**WARNING**: In order to correctly recognize cases where none of the associated checkboxes are selected, the `ActionForm` bean associated with this form must include a statement setting the corresponding array to zero length in the `reset()` method.

The value to be returned to the server, if this checkbox is selected, must be defined by one of the following methods:

-   Specify a `value` attribute, whose contents will be used literally as the value to be returned.
-   Specify no `value` attribute, and the nested body content of this tag will be used as the value to be returned.

Also note that a map backed attribute cannot be used to hold a the String[] for a group of multibox tags.

**[option](option.html.md)**

**Render A Select Option**

Render an HTML `<option>` element, representing one of the choices for an enclosing `<select>` element. The text displayed to the user comes from either the body of this tag, or from a message string looked up based on the `bundle`, `locale`, and `key` attributes.

If the value of the corresponding bean property matches the specified value, this option will be marked selected. This tag is only valid when nested inside a `.html.md:select>` tag body.

**[options](options.html.md)**

**Render a Collection of Select Options**

Renders a set of HTML `<option>` elements, representing possible choices for a `<select>` element. This tag can be used multiple times within a single `.html.md:select>` element, either in conjunction with or instead of one or more `<html:option>` or `<html:optionsCollection>` elements.

This tag operates in one of two major modes, depending on whether or not the `collection` attribute is specified. If the `collection` attribute is included, the following rules apply:

-   The **collection** attribute is interpreted as the name of a JSP bean, in some scope, that itself represents a collection of individual beans, one per option value to be rendered.
-   The **property** attribute is interpreted as the name of a property of the individual beans included in the collection, and is used to retrieve the value that will be returned to the server if this option is selected.
-   The **labelProperty** attribute is interpreted as the name of a property of the individual beans included in the collection, and is used to retrieve the label that will be displayed to the user for this option. If the `labelProperty` attribute is not specified, the property named by the `property` attribute will be used to select both the value returned to the server and the label displayed to the user for this option.

If the `collection` attribute is not specified, the rules described in the remainder of this section apply.

The collection of values actually selected depends on the presence or absence of the `name` and `property` attributes. The following combinations are allowed:

-   *Only `name` is specified* - The value of this attribute is the name of a JSP bean in some scope that is the collection.
-   *Only `property` is specified* - The value of this attribute is the name of a property of the ActionForm bean associated with our form, which will return the collection.
-   *Both `name` and `property` are specified* - The value of the `name` attribute identifies a JSP bean in some scope. The value of the `property` attribute is the name of some property of that bean which will return the collection.

The collection of labels displayed to the user can be the same as the option values themselves, or can be different, depending on the presence or absence of the `labelName` and `labelProperty` attributes. If this feature is used, the collection of labels must contain the same number of elements as the corresponding collection of values. The following combinations are allowed:

-   *Neither `labelName` nor `labelProperty` is specified* - The labels will be the same as the option values themselves.
-   *Only `labelName` is specified* - The value of this attribute is the name of a JSP bean in some scope that is the collection.
-   *Only `labelProperty` is specified* - The value of this attribute is the name of a property of the ActionForm bean associated with our form, which will return the collection.
-   *Both `labelName` and `labelProperty` are specified* - The value of the `labelName` attribute identifies a JSP bean in some scope. The value of the `labelProperty` attribute is the name of some property of that bean which will return the collection.

Note that this tag does not support a `styleId` attribute, as it would have to apply the value to all the `option` elements created by this element, which would mean that more than one `id` element might have the same value, which the HTML specification says is illegal.

**[optionsCollection](optionsCollection.html.md)**

**Render a Collection of Select Options**

Renders a set of HTML `<option>` elements, representing possible choices for a `<select>` element. This tag can be used multiple times within a single `.html.md:select>` element, either in conjunction with or instead of one or more `<html:option>` or `<html:options>` elements.

This tag operates on a collection of beans, where each bean has a **label** property and a **value** property. The actual names of these properties can be configured using the `label` and `value` attributes of this tag.

This tag differs from the `.html.md:options>` tag in that it makes more consistent use of the `name` and `property` attributes, and allows the collection to be more easily obtained from the enclosing form bean.

Note that this tag does not support a `styleId` attribute, as it would have to apply the value to all the `option` elements created by this element, which would mean that more than one `id` element might have the same value, which the HTML specification says is illegal.

**[password](password.html.md)**

**Render A Password Input Field**

Renders an HTML \<input\> element of type password, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

**[radio](radio.html.md)**

**Render A Radio Button Input Field**

Renders an HTML \<input\> element of type radio, populated from the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

If an iterator is used to render a series of radio tags, the idName attribute may be used to specify the name of the bean exposed by the iterator. In this case, the value attribute is used as the name of a property on the idName bean that returns the value of the radio tag in this iteration.

**[reset](reset.html.md)**

**Render A Reset Button Input Field**

Renders an HTML \<input\> element of type reset.

**[rewrite](rewrite.html.md)**

**Render an URI**

Renders a request URI based on exactly the same rules as the `.html.md:link>` tag does, but without creating the `<a>` hyperlink. This value is useful when you want to generate a string constant for use by a JavaScript procedure.

**[select](select.html.md)**

**Render A Select Element**

Renders an HTML \<select\> element, associated with a bean property specified by our attributes. This tag is only valid when nested inside a form tag body.

This tag operates in two modes, depending upon the state of the `multiple` attribute, which affects the data type of the associated property you should use:

-   *multiple="true" IS NOT selected* - The corresponding property should be a scalar value of any supported data type.
-   *multiple="true" IS selected* - The corresponding property should be an array of any supported data type.

**WARNING**: In order to correctly recognize cases where no selection at all is made, the `ActionForm` bean associated with this form must include a statement resetting the scalar property to a default value (if `multiple` is not set), or the array property to zero length (if `multiple` is set) in the `reset()` method.

**[submit](submit.html.md)**

**Render A Submit Button**

Renders an HTML \<input\> element of type `submit`.

If a graphical button is needed (a button with an image), then the `.html.md:image>` tag is more appropriate.

**[text](text.html.md)**

**Render An Input Field of Type text**

Render an input field of type text. This tag is only valid when nested inside a form tag body.

**[textarea](textarea.html.md)**

**Render A Textarea**

Render a textarea element. This tag is only valid when nested inside a form tag body.

**[.html.md](xhtml.html)**

**Render HTML tags as XHTML**

Using this tag in a page tells all other.html.md taglib tags to render themselves as XHTML 1.0. This is useful when composing pages with JSP includes or Tiles. \<html:html xhtml="true"\> has a similar effect. This tag has no attributes; you use it like this: \<html:xhtml/\>.

**Note**: Included pages do not inherit the rendering style of the including page. Each JSP fragment or Tile must use this tag to render as XHTML.

  <span id="navbar_bottom"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-3 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
