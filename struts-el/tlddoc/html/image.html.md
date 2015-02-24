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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="image.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag image
----------

------------------------------------------------------------------------

**Render an input tag of type "image"**

Renders an HTML `<input>` tag of type "image". The base URL for this image is calculated directly based on the value specified in the `src` or `page` attributes, or indirectly by looking up a message resource string based on the `srcKey` or `pageKey` attributes. You **must** specify exactly one of these attributes.

If you would like to obtain the coordinates of the mouse click that submitted this request, see the information below on the `property` attribute.

This tag is only valid when nested inside a form tag body.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.html.md.ELImageTag

TagExtraInfo Class

*None*

Body Content

JSP

Display Name

*None*

**Attributes**

**Name**

**Required**

**Request-time**

**Type**

**Description**

accesskey

false

true

`java.lang.String`

The keyboard character used to move focus immediately to this element.

align

false

true

`java.lang.String`

The alignment option for this image.

alt

false

true

`java.lang.String`

The alternate text for this image.

altKey

false

true

`java.lang.String`

The message resources key of the alternate text for this image.

border

false

true

`java.lang.String`

The width (in pixels) of the border around this image.

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

disabled

false

true

`java.lang.String`

Set to `true`

indexed

false

true

`java.lang.String`

Valid only inside of `logic-el:iterate` `c:forEach` `true`

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

The session attribute key for the Locale used to select internationalized messages. If not specified, defaults to the Struts standard value.

module

false

true

`java.lang.String`

Prefix name of a `Module` that the `page` or `pageKey` attributes relate to.

onblur

false

true

`java.lang.String`

JavaScript event handler executed when this element loses input focus.

onchange

false

true

`java.lang.String`

JavaScript event handler executed when this element loses input focus and its value has changed.

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

onfocus

false

true

`java.lang.String`

JavaScript event handler executed when this element receives input focus.

onkeydown

false

true

`java.lang.String`

JavaScript event handler executed when this element has focus and a key is depressed.

onkeypress

false

true

`java.lang.String`

JavaScript event handler executed when this element has focus and a key is depressed and released.

onkeyup

false

true

`java.lang.String`

JavaScript event handler executed when this element has focus and a key is released.

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

page

false

true

`java.lang.String`

The module-relative path of the image for this input tag.

pageKey

false

true

`java.lang.String`

The key of the message resources string specifying the module-relative path of the image for this input tag.

property

false

true

`java.lang.String`

The property name of this image tag. The parameter names for the request will appear as "property.x" and "property.y", the x and y representing the coordinates of the mouse click for the image. A way of retrieving these values through a form bean is to define getX(), getY(), setX(), and setY() methods, and specify your property as a blank string (property="").

src

false

true

`java.lang.String`

The source URL of the image for this input tag.

srcKey

false

true

`java.lang.String`

The key of the message resources string specifying the source URL of the image for this input tag.

style

false

true

`java.lang.String`

CSS styles to be applied to this HTML element.

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

tabindex

false

true

`java.lang.String`

The tab order (ascending positive integers) for this element.

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

value

false

true

`java.lang.String`

The value that will be submitted if this image button is pressed.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="image.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
