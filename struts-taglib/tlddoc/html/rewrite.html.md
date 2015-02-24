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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="rewrite.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag rewrite
------------

------------------------------------------------------------------------

**Render an URI**

Renders a request URI based on exactly the same rules as the `.html.md:link>` tag does, but without creating the `<a>` hyperlink. This value is useful when you want to generate a string constant for use by a JavaScript procedure.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.taglib.html.md.RewriteTag

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

Logical name of a `Action` that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `action` attribute, the `forward` attribute, the `href` attribute, or the `page` attribute.

Additionally, you can specify a `module` prefix for linking to other modules.

**Since:**  
Struts 1.2.0

module

false

true

`java.lang.String`

Prefix name of a `Module` that contains the action mapping for the `Action` that is specified by the `action` attribute. You **must** specify an `action` attribute for this to have an effect.

**Note:** Use "" to map to the default module.

anchor

false

true

`java.lang.String`

Optional anchor tag ("\#xxx") to be added to the generated hyperlink. Specify this value **without** any "\#" character.

forward

false

true

`java.lang.String`

Logical name of a global `ActionForward` that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `action` attribute, the `forward` attribute, the `href` attribute, or the `page` attribute.

href

false

true

`java.lang.String`

The URL to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `action` attribute, the `forward` attribute, the `href` attribute, or the `page` attribute.

name

false

true

`java.lang.String`

The name of a JSP bean that contains a `Map` representing the query parameters (if `property` is not specified), or a JSP bean whose property getter is called to return a `Map` (if `property` is specified).

page

false

true

`java.lang.String`

The module-relative path (beginning with a "/" character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `action` attribute, the `forward` attribute, the `href` attribute, or the `page` attribute.

paramId

false

true

`java.lang.String`

The name of the request parameter that will be dynamically added to the generated hyperlink. The corresponding value is defined by the `paramName` and (optional) `paramProperty` attributes, optionally scoped by the `paramScope` attribute

paramName

false

true

`java.lang.String`

The name of a JSP bean that is a String containing the value for the request parameter named by `paramId` (if `paramProperty` is not specified), or a JSP bean whose property getter is called to return a String (if `paramProperty` is specified). The JSP bean is constrained to the bean scope specified by the `paramScope` property, if it is specified.

paramProperty

false

true

`java.lang.String`

The name of a property of the bean specified by the `paramName` attribute, whose return value must be a String containing the value of the request parameter (named by the `paramId` attribute) that will be dynamically added to this hyperlink.

paramScope

false

true

`java.lang.String`

The scope within which to search for the bean specified by the `paramName` attribute. If not specified, all scopes are searched.

property

false

true

`java.lang.String`

The name of a property of the bean specified by the `name` attribute, whose return value must be a `java.util.Map` containing the query parameters to be added to the hyperlink. You **must** specify the `name` attribute if you specify this attribute.

scope

false

true

`java.lang.String`

The scope within which to search for the bean specified by the `name` attribute. If not specified, all scopes are searched.

transaction

false

true

`boolean`

If set to `true`, any current transaction control token will be included in the generated hyperlink, so that it will pass an `isTokenValid()` test in the receiving Action.

useLocalEncoding

false

true

`boolean`

If set to `true`, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="rewrite.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
