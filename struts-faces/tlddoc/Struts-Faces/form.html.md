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

Struts-Faces
 Tag form
------------

------------------------------------------------------------------------

Render an HTML form element containing the nested components to present the appropriate label and input field elements. This tag is distinguished from the tag in the standard HTML RenderKit because it accepts a Struts `<action>` path as a parameter, and triggers the creation of a Struts form bean if needed.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.faces.taglib.FormTag

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

true

false

`java.lang.String`

Struts `Action` to which this form should be submitted. This value must exactly match the `path` attribute of the corresponding `<action>` element in the `struts-config.xml` configuration file for this application module.

binding

false

false

`java.lang.String`

Value binding expression to bind this component to a backing bean property.

enctype

false

false

`java.lang.String`

The content encoding to be used to submit this form, if the method is `POST`. This must be set to "`multipart/form-data`" if your form includes file upload field(s). If not specified, the browser default ("`application/x-www-form-urlencoded`") is used.

focus

false

false

`java.lang.String`

The identifier of the form field that should receive focus when this form is rendered.

focusIndex

false

false

`java.lang.String`

If the focus field is an array, such as a radio button group, you can specify the index of the array element to receive focus.

id

false

false

`java.lang.String`

Component id of this component.

onreset

false

false

`java.lang.String`

JavaScript event handler executed if this form is reset.

onsubmit

false

false

`java.lang.String`

JavaScript event handler executed if this form is submitted.

rendered

false

false

`java.lang.String`

Boolean attribute indicating whether this component should be rendered or not.

style

false

false

`java.lang.String`

CSS styles to be applied to this HTML element.

styleClass

false

false

`java.lang.String`

CSS style class to use when rendering this component.

target

false

false

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
