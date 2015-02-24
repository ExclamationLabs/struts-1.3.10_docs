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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="form.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag form
---------

------------------------------------------------------------------------

**Define An Input Form**

Renders an HTML `<form>` element whose contents are described by the body content of this tag. The form implicitly interacts with the specified request scope or session scope bean to populate the input fields with the current property values from the bean.

The form bean is located, and created if necessary, based on the form bean specification for the associated `ActionMapping`.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.html.md.ELFormTag

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

action

false

true

`java.lang.String`

The URL to which this form will be submitted. This value is also used to select the ActionMapping we are assumed to be processing, from which we can identify the appropriate form bean and scope. If a value is not provided, the original URI (servletPath) for the request is used.

If you are using extension mapping for selecting the controller servlet, this value should be equal to the `path` attribute of the corresponding `<action>` element, optionally followed by the correct extension suffix.

If you are using path mapping to select the controller servlet, this value should be exactly equal to the `path` attribute of the corresponding `<action>` element.

acceptCharset

false

true

`java.lang.String`

The list of character encodings for input data that the server should accept.

**Since:**  
Struts 1.2.2

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

Set to `true` if the Form's input fields should be read only.

**Since:**  
Struts 1.2.7

enctype

false

true

`java.lang.String`

The content encoding to be used to submit this form, if the method is POST. This must be set to "multipart/form-data" if you are using the file tag to enable file upload. If not specified, the browser default (normally "application/x-www-form-urlencoded") is used.

focus

false

true

`java.lang.String`

The field name (among the fields on this form) to which initial focus will be assigned with a JavaScript function. If not specified, no special JavaScript for this purpose will be rendered.

focusIndex

false

true

`java.lang.String`

If the focus field is a field array, such as a radio button group, you can specify the index in the array to receive focus.

**Since:**  
Struts 1.1

lang

false

true

`java.lang.String`

The language code for this element.

**Since:**  
Struts 1.3.6

method

false

true

`java.lang.String`

The HTTP method that will be used to submit this request (GET, POST). [POST]

onreset

false

true

`java.lang.String`

JavaScript event handler executed if the form is reset.

onsubmit

false

true

`java.lang.String`

JavaScript event handler executed if the form is submitted.

readonly

false

true

`java.lang.String`

Set to `true` if this input field should be read only.

**Since:**  
Struts 1.2.7

scriptLanguage

false

true

`java.lang.String`

The form's focus \<script\> element will not contain a language attribute when this is set to false. The default is true but this property is ignored in XHMTL mode.

**Since:**  
Struts 1.2

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

target

false

true

`java.lang.String`

Window target to which this form is submitted, such as for use in framed presentations.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="form.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
