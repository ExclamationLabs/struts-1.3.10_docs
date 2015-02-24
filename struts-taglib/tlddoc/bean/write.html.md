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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="write.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

bean
 Tag write
----------

------------------------------------------------------------------------

**Render the value of the specified bean property to the current JspWriter.**

Retrieve the value of the specified bean property, and render it to the current JspWriter as a String by the ways:

-   If `format` attribute exists then value will be formatted on base of format string from `format` attribute and default system locale.
-   If in resources exists format string for value data type (view `format` attribute description) then value will be formatted on base of format string from resources. Resources bundle and target locale can be specified with `bundle` and `locale` attributes. If nothing specified then default resource bundle and current user locale will be used.
-   If there is a PropertyEditor configured for the property value's class, the `getAsText()` method will be called.
-   Otherwise, the usual `toString()` conversions will be applied.

When a format string is provided, numeric values are formatted using the `java.text.DecimalFormat` class; if the format string came from a resource, the `applyLocalisedPattern()` method is used, and `applyPattern()` is used otherwise. Dates are formatted using the `SimpleDateFormat` class. For details of the specific format patterns, please see the Javadocs for those classes.

If a problem occurs while retrieving the specified bean property, a request time exception will be thrown.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.taglib.bean.WriteTag

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

bundle

false

true

`java.lang.String`

The name of the application scope bean under which the `MessageResources` object containing our messages is stored.

filter

false

true

`boolean`

If this attribute is set to `true`, the rendered property value will be filtered for characters that are sensitive in HTML, and any such characters will be replaced by their entity equivalents.

format

false

true

`java.lang.String`

Specifies the format string to use to convert bean or property value to the `String`. If nothing specified, then default format string for value data type will be searched in message resources by according key.

formatKey

false

true

`java.lang.String`

Specifies the key to search format string in application resources.

ignore

false

true

`boolean`

If this attribute is set to `true`, and the bean specified by the `name` and `scope` attributes does not exist, simply return without writing anything. If this attribute is set to `false`, a runtime exception to be thrown, consistent with the other tags in this tag library.

locale

false

true

`java.lang.String`

The name of the session scope bean under which our currently selected `Locale` object is stored.

name

true

true

`java.lang.String`

Specifies the attribute name of the bean whose property is accessed to retrieve the value specified by `property` (if specified). If `property` is not specified, the value of this bean itself will be rendered.

property

false

true

`java.lang.String`

Specifies the name of the property to be accessed on the bean specified by `name`. This value may be a simple, indexed, or nested property reference expression. If not specified, the bean identified by `name` will itself be rendered. If the specified property returns null, no output will be rendered.

scope

false

true

`java.lang.String`

Specifies the variable scope searched to retrieve the bean specified by `name`. If not specified, the default rules applied by `PageContext.findAttribute()` are applied.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="write.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
