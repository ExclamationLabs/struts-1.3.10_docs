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
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

bean
----

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix="bean" uri="http://struts.apache.org/tags-bean-el" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:bean="http://struts.apache.org/tags-bean-el" />`

------------------------------------------------------------------------

    This tag library contains tags useful in accessing beans and their properties, as well as defining new beans (based on these accesses) that are accessible to the remainder of the page via scripting variables and page scope attributes. Convenient mechanisms to create new beans based on the value of request cookies, headers, and parameters are also provided.Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.If you are viewing this page from within the Struts Documentation Application (or online at http://struts.apache.org), you can learn more about using these tags in the Bean Tags Developer's Guide.

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

bean

URI

http://struts.apache.org/tags-bean-el

 

**Tag Summary**

**[include](include.html.md)**

**Load the response from a dynamic application request and make it available as a bean.**

Perform an internal dispatch to the specified application component (or external URL) and make the response data from that request available as a scoped variable of type `String`. This tag has a function similar to that of the standard `<jsp:include>` tag, except that the response data is stored in a page scope attribute instead of being written to the output stream. If the current request is part of a session, the generated request for the include will also include the session identifier (and thus be part of the same session).

The URL used to access the specified application component is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged (since this might link to a resource external to the application, the session identifier is **not** included.
-   *page* - Use the value of this attribute as an module-relative URI to the desired resource.

**[message](message.html.md)**

**Render an internationalized message string to the response.**

Retrieves an internationalized message for the specified locale, using the specified message key, and write it to the output stream. Up to five parametric replacements (such as "{0}") may be specified.

The message key may be specified directly, using the `key` attribute, or indirectly, using the `name` and `property` attributes to obtain it from a bean.

**JSTL**: The equivalent JSTL tag is `<fmt:message>`. For example,
 `<fmt:message key="my.msg.key"> <fmt:param value="replacement text"/> </fmt:message>`

**[page](page.html.md)**

**Expose a specified item from the page context as a bean.**

Retrieve the value of the specified item from the page context for this page, and define it as a scripting variable, and a page scope attribute accessible to the remainder of the current page.

If a problem occurs while retrieving the specified configuration object, a request time exception will be thrown.

**[resource](resource.html.md)**

**Load a web application resource and make it available as a bean.**

Retrieve the value of the specified web application resource, and make it available as either a `InputStream` or a `String`, depending on the value of the `input` attribute.

If a problem occurs while retrieving the specified resource, a request time exception will be thrown.

**[size](size.html.md)**

**Define a bean containing the number of elements in a Collection or Map.**

Given a reference to an array, Collection or Map, creates a new bean, of type `java.lang.Integer`, whose value is the number of elements in that collection. You can specify the collection to be counted in any one of the following ways:

-   As a runtime expression specified as the value of the `collection` attribute.
-   As a JSP bean specified by the `name` attribute.
-   As the property, specified by the `property` attribute, of the JSP bean specified by the `name` attribute.

**[struts](struts.html.md)**

**Expose a named Struts internal configuration object as a bean.**

Retrieve the value of the specified Struts internal configuration object, and define it as a scripting variable and as a page scope attribute accessible to the remainder of the current page. You must specify exactly one of the `formBean`, `forward`, and `mapping` attributes to select the configuration object to be exposed.

If a problem occurs while retrieving the specified configuration object, a request time exception will be thrown.

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
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-3 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
