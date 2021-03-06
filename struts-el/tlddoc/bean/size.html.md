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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="size.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

bean
 Tag size
---------

------------------------------------------------------------------------

**Define a bean containing the number of elements in a Collection or Map.**

Given a reference to an array, Collection or Map, creates a new bean, of type `java.lang.Integer`, whose value is the number of elements in that collection. You can specify the collection to be counted in any one of the following ways:

-   As a runtime expression specified as the value of the `collection` attribute.
-   As a JSP bean specified by the `name` attribute.
-   As the property, specified by the `property` attribute, of the JSP bean specified by the `name` attribute.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.bean.ELSizeTag

TagExtraInfo Class

org.apache.struts.taglib.bean.SizeTei

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

A runtime expression that evaluates to an array, a Collection, or a Map.

id

true

false

`java.lang.String`

The name of a page scope JSP bean, of type `java.lang.Integer`, that will be created to contain the size of the underlying collection being counted.

name

false

true

`java.lang.String`

The name of the JSP bean (optionally constrained to the scope specified by the `scope` attribute) that contains the collection to be counted (if `property` is not specified), or whose property getter is called to return the collection to be counted (if `property` is specified.

property

false

true

`java.lang.String`

The name of the property, of the bean specified by the `name` attribute, whose getter method will return the collection to be counted.

scope

false

true

`java.lang.String`

The bean scope within which to search for the JSP bean specified by the `name` attribute. If not specified, the available scopes are searched in ascending sequence.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="size.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
