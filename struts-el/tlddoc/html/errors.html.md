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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="errors.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag errors
-----------

------------------------------------------------------------------------

**Conditionally display a set of accumulated error messages.**

Displays a set of error messages prepared by a business logic component and stored as an `ActionErrors` object, a String, or a String array in any scope. If such a bean is not found, nothing will be rendered.

In order to use this tag successfully, you must have defined an application scope `MessageResources` bean under the default attribute name, with optional definitions of message keys specified in the following attributes:

-   **header** - Text that will be rendered before the error messages list. Typically, this message text will end with `<ul>` to start the error messages list (default "errors.header").
-   **footer** - Text that will be rendered after the error messages list. Typically, this message text will begin with `</ul>` to end the error messages list (default "errors.footer").
-   **prefix** - Text that will be rendered before each individual error in the list (default "errors.prefix").
-   **suffix** - Text that will be rendered after each individual error in the list (default "errors.suffix").

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.html.md.ELErrorsTag

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

The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.

footer

false

true

`java.lang.String`

This value is an optional message resource key that will be printed after the iteration of error messages has finished. Defaults to "errors.footer" if not specified.

**Since:**  
Struts 1.2.5

header

false

true

`java.lang.String`

This value is an optional message resource key that will be printed before the iteration of error messages begins. Defaults to "errors.header" if not specified.

**Since:**  
Struts 1.2.5

locale

false

true

`java.lang.String`

The session attribute key for the Locale used to select messages to be displayed. If not specified, defaults to the Struts standard value.

name

false

true

`java.lang.String`

Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the `Globals.ERROR_KEY`

prefix

false

true

`java.lang.String`

This value is an optional message resource key that will be printed before an error message. Defaults to "errors.prefix" if not specified.

**Since:**  
Struts 1.2.5

property

false

true

`java.lang.String`

Name of the property for which error messages should be displayed. If not specified, all error messages (regardless of property) are displayed.

suffix

false

true

`java.lang.String`

This value is an optional message resource key that will be printed after an error message. Defaults to "errors.suffix" if not specified.

**Since:**  
Struts 1.2.5

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="errors.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
