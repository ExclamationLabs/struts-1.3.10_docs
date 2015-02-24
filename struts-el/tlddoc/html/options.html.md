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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="options.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag options
------------

------------------------------------------------------------------------

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

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.html.md.ELOptionsTag

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

collection

false

true

`java.lang.String`

Name of the JSP bean (in some scope) which is itself a Collection of other beans, each of which has properties named by the "property" and "labelProperty" attributes that are used to retrieve the value and label for each option, respectively.

filter

false

true

`java.lang.String`

Set to `false`

labelName

false

true

`java.lang.String`

Name of the JSP bean (in some scope) containing the collection of labels to be displayed to the user for these options.

labelProperty

false

true

`java.lang.String`

Property of the form bean, or the bean specified by the labelName attribute, that will return the collection of labels to be displayed to the user for these options.

name

false

true

`java.lang.String`

Name of the JSP bean (in some scope) containing the collection of values to be returned to the server for these options. If not specified, the form bean associated with our form is assumed.

property

false

true

`java.lang.String`

Property of the form bean, or the bean specified by the name attribute, that will return the collection of values to returned to the server for these options.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="options.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
