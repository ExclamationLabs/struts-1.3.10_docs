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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="iterate.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

logic
 Tag iterate
------------

------------------------------------------------------------------------

**Repeat the nested body content of this tag over a specified collection.**

Repeats the nested body content of this tag once for every element of the specified collection, which must be an `Iterator`, a `Collection`, a `Map` (whose values are to be iterated over), or an array. The collection to be iterated over must be specified in one of the following ways:

-   As a runtime expression specified as the value of the `collection` attribute.
-   As a JSP bean specified by the `name` attribute.
-   As the property, specified by the `property`, of the JSP bean specified by the `name` attribute.

The collection to be iterated over MUST conform to one of the following requirements in order for iteration to be successful:

-   An array of Java objects or primitives.
-   An implementation of `java.util.Collection`, including `ArrayList` and `Vector`.
-   An implementation of `java.util.Enumeration`.
-   An implementation of `java.util.Iterator`.
-   An implementation of `java.util.Map`, including `HashMap`, `Hashtable`, and `TreeMap`. **NOTE** - See below for additional information about accessing Maps.

Normally, each object exposed by the iterate tag is an element of the underlying collection you are iterating over. However, if you iterate over a `Map`, the exposed object is of type `Map.Entry` that has two properties:

-   `key` - The key under which this item is stored in the underlying Map.
-   `value` - The value that corresponds to this key.

So, if you wish to iterate over the values of a Hashtable, you would implement code like the following:

`<logic-el:iterate id="element" name="myhashtable"> Next element is <bean:write name="element" property="value"/> </logic-el:iterate>`

If the collection you are iterating over can contain `null` values, the loop will still be performed but no page scope attribute (named by the `id` attribute) will be created for that loop iteration. You can use the `<logic-el:present;gt;` and `<logic-el:notPresent>` tags to test for this case.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.logic.ELIterateTag

TagExtraInfo Class

org.apache.struts.taglib.logic.IterateTei

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

collection

false

true

`java.lang.String`

A runtime expression that evaluates to a collection (conforming to the requirements listed above) to be iterated over.

id

true

false

`java.lang.String`

The name of a page scope JSP bean that will contain the current element of the collection on each iteration, if it is not `null`.

indexId

false

false

`java.lang.String`

The name of a page scope JSP bean that will contain the current index of the collection on each iteration.

length

false

true

`java.lang.String`

The maximum number of entries (from the underlying collection) to be iterated through on this page. This can be either an integer that directly expresses the desired value, or the name of a JSP bean (in any scope) of type `java.lang.Integer` that defines the desired value. If not present, there will be no limit on the number of iterations performed.

name

false

true

`java.lang.String`

The name of the JSP bean containing the collection to be iterated (if `property` is not specified), or the JSP bean whose property getter returns the collection to be iterated (if `property` is specified).

offset

false

true

`java.lang.String`

The zero-relative index of the starting point at which entries from the underlying collection will be iterated through. This can be either an integer that directly expresses the desired value, or the name of a JSP bean (in any scope) of type `java.lang.Integer` that defines the desired value. If not present, zero is assumed (meaning that the collection will be iterated from the beginning.

property

false

true

`java.lang.String`

Name of the property, of the JSP bean specified by `name`, whose getter returns the collection to be iterated.

scope

false

true

`java.lang.String`

The bean scope within which to search for the bean named by the `name` property, or "any scope" if not specified.

type

false

true

`java.lang.String`

Fully qualified Java class name of the element to be exposed through the JSP bean named from the `id` attribute. If not present, no type conversions will be performed. NOTE: The actual elements of the collection must be assignment-compatible with this class, or a request time ClassCastException will occur.

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
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="iterate.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
