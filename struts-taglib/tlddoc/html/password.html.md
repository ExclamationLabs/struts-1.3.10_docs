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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="password.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag password
-------------

------------------------------------------------------------------------

**Render A Password Input Field**

Renders an HTML \<input\> element of type password, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.taglib.html.md.PasswordTag

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

alt

false

true

`java.lang.String`

The alternate text for this element.

altKey

false

true

`java.lang.String`

The message resources key of the alternate text for this element.

bundle

false

true

`java.lang.String`

The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.

**Since:**  
Struts 1.2.5

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

`boolean`

Set to `true` if this input field should be disabled.

errorKey

false

true

`java.lang.String`

Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the `Globals.ERROR_KEY` constant string will be used.

**N.B.** This is used in conjunction with the `errorStyle`, `errorStyleClass` and `errorStyleId` attributes and should be set to the same value as the `name` attribute on the \.html.md:errors/\> tag.

**Since:**  
Struts 1.2.5

errorStyle

false

true

`java.lang.String`

CSS styles to be applied to this HTML element if an error exists for it.

**N.B.** If present, this overrides the `style` attribute in the event of an error.

**Since:**  
Struts 1.2.5

errorStyleClass

false

true

`java.lang.String`

CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a "class" attribute).

**N.B.** If present, this overrides the `styleClass` attribute in the event of an error.

**Since:**  
Struts 1.2.5

errorStyleId

false

true

`java.lang.String`

Identifier to be assigned to this HTML element if an error exists for it (renders an "id" attribute).

**N.B.** If present, this overrides the `styleId` attribute in the event of an error.

**Since:**  
Struts 1.2.5

indexed

false

true

`boolean`

Valid only inside of logic:iterate tag. If `true` then name of the.html.md tag will be rendered as "id[34].propertyName". Number in brackets will be generated for every iteration and taken from ancestor logic:iterate tag.

lang

false

true

`java.lang.String`

The language code for this element.

**Since:**  
Struts 1.3.6

maxlength

false

true

`java.lang.String`

Maximum number of input characters to accept. [No limit]

name

false

true

`java.lang.String`

The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.

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

onselect

false

true

`java.lang.String`

JavaScript event handler executed when a when a user selects some text in a text field.

**Since:**  
Struts 1.3.10

property

true

true

`java.lang.String`

Name of the request parameter that will be included with this submission, set to the specified value.

readonly

false

true

`boolean`

Set to `true` if this input field should be read only.

redisplay

false

true

`boolean`

Boolean flag indicating whether or not existing values will be redisplayed if they exist. Even though the redisplayed value will be shown as asterisks on the visible HTML page, the cleartext of the actual password value will be visible though the "Show Page Source" menu option of the client browser. You may wish to set this value to `false` on login pages. Defaults to `true` for consistency with all other form tags that redisplay their contents.

style

false

true

`java.lang.String`

CSS styles to be applied to this HTML element.

**N.B.** If present, the `errorStyle` overrides this attribute in the event of an error for the element.

styleClass

false

true

`java.lang.String`

CSS stylesheet class to be applied to this HTML element (renders a "class" attribute).

**N.B.** If present, the `errorStyleClass` overrides this attribute in the event of an error for the element.

styleId

false

true

`java.lang.String`

Identifier to be assigned to this HTML element (renders an "id" attribute).

**N.B.** If present, the `errorStyleId` overrides this attribute in the event of an error for the element.

size

false

true

`java.lang.String`

Number of character positions to allocate. [Browser default]

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

Value of the label to be placed on this button. This value will also be submitted as the value of the specified request parameter. [Body of this tag (if any)]

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="password.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
