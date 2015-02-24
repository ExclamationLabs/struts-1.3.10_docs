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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="javascript.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

html
 Tag javascript
---------------

------------------------------------------------------------------------

**Render JavaScript validation based on the validation rules loaded by the ValidatorPlugIn.**

Render JavaScript validation based on the validation rules loaded by the `ValidatorPlugIn`. The set of validation rules that should be generated is based on the formName attribute passed in, which should match the name attribute of the form element in the xml file.

The dynamicJavascript and staticJavascript attributes default to true, but if dynamicJavascript is set to `true` and staticJavascript is set to `false` then only the dynamic JavaScript will be rendered. If dynamicJavascript is set to `false` and staticJavascript is set to `true` then only the static JavaScript will be rendered which can then be put in separate JSP page so the browser can cache the static JavaScript.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.html.md.ELJavascriptValidatorTag

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

cdata

false

true

`java.lang.String`

If set to "true" and XHTML has been enabled, the JavaScript will be wrapped in a CDATA section to prevent XML parsing. The default is "true" to comply with the W3C's recommendation.

**Since:**  
Struts 1.1

dynamicJavascript

false

true

`java.lang.String`

Whether or not to render the dynamic JavaScript. Defaults to `true`.

formName

false

true

`java.lang.String`

The key (form name) to retrieve a specific set of validation rules. If "dynamicJavascript" is set to `true` and formName is missing or is not recognized by the `ValidatorPlugIn`, a JspException will be thrown.

method

false

true

`java.lang.String`

The alternate JavaScript method name to be used instead of the of the default. The default is 'validate' concatenated in front of the key (form name) passed in (ex: validateRegistrationForm).

page

false

true

`java.lang.String`

The current page of a set of validation rules if the page attribute for the field element in the xml file is in use.

scriptLanguage

false

true

`java.lang.String`

The `<script>` element will not contain a language attribute when this is set to false. The default is true but this property is ignored in XHTML mode.

**Since:**  
Struts 1.2

src

false

true

`java.lang.String`

The src attribute's value when defining the.html.md script element.

staticJavascript

false

true

`java.lang.String`

Whether or not to render the static JavaScript. Defaults to `true`.

htmlComment

false

true

`java.lang.String`

Whether or not to enclose the javascript with HTML comments. This attribute is ignored in XHTML mode because the script would be deleted by the XML parser. See the cdata attribute for details on hiding scripts from XML parsers. Defaults to `true`.

bundle

false

true

`java.lang.String`

The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.

**Since:**  
Struts 1.2.7

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="javascript.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
