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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="img.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag img
--------

------------------------------------------------------------------------

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

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.taglib.html.md.ImgTag

TagExtraInfo Class

*None*

Body Content

empty

Display Name

*None*

**Attributes**

**Name**

**Required**

**Request-time**

**Type**

**Description**

align

false

true

`java.lang.String`

Where the image is aligned to. Can be one of the following attributes:

-   left - left justify, wrapping text on right
-   right -right justify, wrapping test on left
-   top - aligns the image with the top of the text on the same row
-   middle - aligns the image's vertical center with the text base line
-   bottom - aligns the image with the bottom of the text's base line
-   texttop - aligns the image's top with that of the text font on the same line
-   absmiddle - aligns the image's vertical center with the absolute center of the text
-   absbottom - aligns the image with the absolute bottom of the text font on the same row

alt

false

true

`java.lang.String`

And alternative text to be displayed in browsers that don't support graphics. Also used often as type of context help over images.

altKey

false

true

`java.lang.String`

The message resources key of the alternate text for this element.

border

false

true

`java.lang.String`

The width of the border surrounding the image.

bundle

false

true

`java.lang.String`

The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.

dir

false

true

`java.lang.String`

The direction for weak/neutral text for this element.

**Since:**  
Struts 1.3.6

height

false

true

`java.lang.String`

The height of the image being displayed. This parameter is very nice to specify (along with `width`) to help the browser render the page faster.

hspace

false

true

`java.lang.String`

The amount of horizontal spacing between the icon and the text. The text may be in the same paragraph, or be wrapped around the image.

imageName

false

true

`java.lang.String`

The scriptable name to be defined within this page, so that you can reference it with intra-page scripts. In other words, the value specified here will render a "name" element in the generated image tag.

ismap

false

true

`java.lang.String`

The name of the server-side map that this image belongs to.

lang

false

true

`java.lang.String`

The language code for this element.

**Since:**  
Struts 1.3.6

locale

false

true

`java.lang.String`

The name of the request or session Locale attribute used to look up internationalized messages.

name

false

true

`java.lang.String`

The name of a JSP bean that contains a `Map` representing the query parameters (if `property` is not specified), or a JSP bean whose property getter is called to return a `Map` (if `property` is specified).

onclick

false

true

`java.lang.String`

JavaScript event handler executed when this element receives a mouse click.

ondblclick

false

true

`java.lang.String`

JavaScript event handler executed when this element receives a mouse double click.

onkeydown

false

true

`java.lang.String`

JavaScript event handler that is executed when this element receives a key down event.

onkeypress

false

true

`java.lang.String`

JavaScript event handler that is executed when this element receives a key press event.

onkeyup

false

true

`java.lang.String`

JavaScript event handler that is executed when this element receives a key up event.

onmousedown

false

true

`java.lang.String`

JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.

onmousemove

false

true

`java.lang.String`

JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.

onmouseout

false

true

`java.lang.String`

JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.

onmouseover

false

true

`java.lang.String`

JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.

onmouseup

false

true

`java.lang.String`

JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.

paramId

false

true

`java.lang.String`

The name of the request parameter that will be dynamically added to the generated src URL. The corresponding value is defined by the `paramName` and (optional) `paramProperty` attributes, optionally scoped by the `paramScope` attribute

page

false

true

`java.lang.String`

The module-relative path, starting with a slash, of the image to be displayed by this tag. The rendered URL for this image will automatically prepend the context path of this web application (in the same manner as the `page` attribute on the link tag works), in addition to any necessary URL rewriting. You **must** specify either the `page` attribute or the `src` attribute.

pageKey

false

true

`java.lang.String`

The message key, in the message resources bundle named by the `bundle` attribute, of the String to be used as the module-relative path for this image.

action

false

true

`java.lang.String`

The action, starting with a slash, that will render the image to be displayed by this tag. The rendered URL for this image will automatically prepend the context path of this web application (in the same manner as the `action` attribute on the link tag works), in addition to any necessary URL rewriting. You **must** specify the `action`, `page` attribute or the `src` attribute.

Additionally, you can specify a `module` prefix for linking to other modules.

module

false

true

`java.lang.String`

Prefix name of a `Module` that contains the action mapping for the `Action` that is specified by the `action` attribute. You **must** specify an `action` attribute for this to have an effect.

**Note:** Use "" to map to the default module.

paramName

false

true

`java.lang.String`

The name of a JSP bean that is a String containing the value for the request parameter named by `paramId` (if `paramProperty` is not specified), or a JSP bean whose property getter is called to return a String (if `paramProperty` is specified). The JSP bean is constrained to the bean scope specified by the `paramScope` property, if it is specified.

paramProperty

false

true

`java.lang.String`

The name of a property of the bean specified by the `paramName` attribute, whose return value must be a String containing the value of the request parameter (named by the `paramId` attribute) that will be dynamically added to this src URL.

paramScope

false

true

`java.lang.String`

The scope within which to search for the bean specified by the `paramName` attribute. If not specified, all scopes are searched.

property

false

true

`java.lang.String`

The name of a property of the bean specified by the `name` attribute, whose return value must be a `java.util.Map` containing the query parameters to be added to the src URL. You **must** specify the `name` attribute if you specify this attribute.

scope

false

true

`java.lang.String`

The scope within which to search for the bean specified by the `name` attribute. If not specified, all scopes are searched.

src

false

true

`java.lang.String`

The URL to which this image will be transferred from This image may be dynamically modified by the inclusion of query parameters, as described in the tag description. This value will be used unmodified (other than potential URL rewriting) as the value of the "src" attribute in the rendered tag. You **must** specify either the `page` attribute or the `src` attribute.

srcKey

false

true

`java.lang.String`

The message key, in the message resources bundle named by the `bundle` attribute, of the String to be used as the URL of this image.

style

false

true

`java.lang.String`

CSS styles to be applied to this element.

styleClass

false

true

`java.lang.String`

CSS stylesheet class to be applied to this HTML element (renders a "class" attribute).

styleId

false

true

`java.lang.String`

Identifier to be assigned to this HTML element (renders an "id" attribute).

title

false

true

`java.lang.String`

The advisory title for this element.

titleKey

false

true

`java.lang.String`

The message resources key for the advisory title for this element.

useLocalEncoding

false

true

`boolean`

If set to `true`, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.

usemap

false

true

`java.lang.String`

The name of the map as defined within this page for mapping hot-spot areas of this image.

vspace

false

true

`java.lang.String`

The amount of vertical spacing between the icon and the text, above and below.

width

false

true

`java.lang.String`

The width of the image being displayed. This parameter is very nice to specify (along with `height`) to help the browser render the page faster.

|-------------------------|
| **Variables**           |
| *No Variables Defined.* |

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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="img.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
