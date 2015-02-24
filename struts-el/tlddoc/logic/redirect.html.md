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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="redirect.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

logic
 Tag redirect
-------------

------------------------------------------------------------------------

**Render an HTTP Redirect**

Performs an `HttpServletResponse.sendRedirect()` call to the hyperlink specified by the attributes to this tag. URL rewriting will be applied automatically, to maintain session state in the absence of cookies.

The base URL for this redirect is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as an module-relative URI, and generate a server-relative URI by including the context path.

Normally, the redirect you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s). If a String array is specified, more than one value for the same query parameter name will be created.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.logic.ELRedirectTag

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

Logical name of a global `Action` that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `action` attribute, the `forward` attribute, the `href` attribute, or the `page` attribute.

anchor

false

true

`java.lang.String`

Optional anchor tag ("\#xxx") to be added to the generated hyperlink. Specify this value **without** any "\#" character.

forward

false

true

`java.lang.String`

Logical name of a global `ActionForward` that contains the actual content-relative URI of the destination of this redirect. This URI may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `forward` attribute, the `href` attribute, the `linkName` attribute, or the `page` attribute.

href

false

true

`java.lang.String`

The URL to which this redirect will transfer control. This URL may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `forward` attribute, the `href` attribute, the `linkName` attribute, or the `page` attribute.

name

false

true

`java.lang.String`

The name of a JSP bean that contains a `Map` representing the query parameters (if `property` is not specified), or a JSP bean whose property getter is called to return a `Map` (if `property` is specified).

page

false

true

`java.lang.String`

The context-relative path (beginning with a "/" character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You **must** specify exactly one of the `forward` attribute, the `href` attribute, the `linkName` attribute, or the `page` attribute.

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

`java.lang.String`

Set to `true` if you want the current transaction control token included in the generated URL for this redirect.

useLocalEncoding

false

true

`java.lang.String`

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="redirect.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
