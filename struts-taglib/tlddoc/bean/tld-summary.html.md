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
 `     <%@ taglib prefix="bean" uri="http://struts.apache.org/tags-bean" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:bean="http://struts.apache.org/tags-bean" />`

------------------------------------------------------------------------


    Note: Some of the features in this taglib are also available in the JavaServer Pages Standard Tag Library (JSTL). The Struts team encourages the use of the standard tags over the Struts specific tags when possible. 
    This tag library contains tags useful in accessing beans and their properties, as well as defining new beans (based on these accesses) that are accessible to the remainder of the page via scripting variables and page scope attributes. Convenient mechanisms to create new beans based on the value of request cookies, headers, and parameters are also provided. 
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

bean

URI

http://struts.apache.org/tags-bean

 

**Tag Summary**

**[cookie](cookie.html.md)**

**Define a scripting variable based on the value(s) of the specified request cookie.**

Retrieve the value of the specified request cookie (as a single value or multiple values, depending on the `multiple` attribute), and define the result as a page scope attribute of type `Cookie` (if `multiple` is not specified) or `Cookie[]` (if `multiple` is specified).

If no cookie with the specified name can be located, and no default value is specified, a request time exception will be thrown.

**[define](define.html.md)**

**Define a scripting variable based on the value(s) of the specified bean property.**

Create a new attribute (in the scope specified by the `toScope` property, if any), and a corresponding scripting variable, both of which are named by the value of the `id` attribute. The corresponding value to which this new attribute (and scripting variable) is set are specified via use of exactly one of the following approaches (trying to use more than one will result in a JspException being thrown):

-   Specify a `name` attribute (plus optional `property` and `scope` attributes) - The created attribute and scripting variable will be of the type of the retrieved JavaBean property, unless it is a Java primitive type, in which case it will be wrapped in the appropriate wrapper class (i.e. int is wrapped by java.lang.Integer).
-   Specify a `value` attribute - The created attribute and scripting variable will be of type `java.lang.String`, set to the value of this attribute.
-   Specify nested body content - The created attribute and scripting variable will be of type `java.lang.String`, set to the value of the nested body content.

If a problem occurs while retrieving the specified bean property, a request time exception will be thrown.

The `<bean:define>` tag differs from `<jsp:useBean>` in several ways, including:

-   Unconditionally creates (or replaces) a bean under the specified identifier.
-   Can create a bean with the value returned by a property getter of a different bean (including properties referenced with a nested and/or indexed property name).
-   Can create a bean whose contents is a literal string (or the result of a runtime expression) specified by the `value` attribute.
-   Does not support nested content (such as `<jsp:setProperty>` tags) that are only executed if a bean was actually created.

**USAGE NOTE** - There is a restriction in the JSP 1.1 Specification that disallows using the same value for an `id` attribute more than once in a single JSP page. Therefore, you will not be able to use `<bean:define>` for the same bean name more than once in a single page.

**USAGE NOTE** - If you use another tag to create the body content (e.g. bean:write), that tag must return a non-empty String. An empty String equates to an empty body or a null String, and a new scripting variable cannot be defined as null. Your bean must return a non-empty String, or the define tag must be wrapped within a logic tag to test for an empty or null value.

**USAGE NOTE** - You cannot use bean:define to **instantiate** a DynaActionForm (type="org.apache.struts.action.DynaActionForm") with the properties specified in the struts-config. The mechanics of creating the dyna-properties is complex and cannot be handled by a no-argument constructor. If you need to create an ActionForm this way, you must use a conventional ActionForm.

See the Bean Developer's Guide section on [bean creation](../apidocs/org/apache/struts/taglib/bean/package-summary.html.md#doc.Creation) for more information about these differences, as well as alternative approaches to introducing beans into a JSP page.

**[header](header.html.md)**

**Define a scripting variable based on the value(s) of the specified request header.**

Retrieve the value of the specified request header (as a single value or multiple values, depending on the `multiple` attribute), and define the result as a page scope attribute of type `String` (if `multiple` is not specified) or `String[]` (if `multiple` is specified).

If no header with the specified name can be located, and no default value is specified, a request time exception will be thrown.

**[include](include.html.md)**

**Load the response from a dynamic application request and make it available as a bean.**

Perform an internal dispatch to the specified application component (or external URL) and make the response data from that request available as a bean of type `String`. This tag has a function similar to that of the standard `<jsp:include>` tag, except that the response data is stored in a page scope attribute instead of being written to the output stream. If the current request is part of a session, the generated request for the include will also include the session identifier (and thus be part of the same session).

The URL used to access the specified application component is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged (since this might link to a resource external to the application, the session identifier is **not** included.
-   *page* - Use the value of this attribute as an module-relative URI to the desired resource.

**[message](message.html.md)**

**Render an internationalized message string to the response.**

Retrieves an internationalized message for the specified locale, using the specified message key, and write it to the output stream. Up to five parametric replacements (such as "{0}") may be specified.

The message key may be specified directly, using the `key` attribute, or indirectly, using the `name` and `property` attributes to obtain it from a bean.

**JSTL**: The equivalent JSTL tag is \<fmt:message\>. For example,
 `<fmt:message key="my.msg.key"> <fmt:param value="replacement text"/> </fmt:message>`

**[page](page.html.md)**

**Expose a specified item from the page context as a bean.**

Retrieve the value of the specified item from the page context for this page, and define it as a scripting variable, and a page scope attribute accessible to the remainder of the current page.

If a problem occurs while retrieving the specified configuration object, a request time exception will be thrown.

**[parameter](parameter.html.md)**

**Define a scripting variable based on the value(s) of the specified request parameter.**

Retrieve the value of the specified request parameter (as a single value or multiple values, depending on the `multiple` attribute), and define the result as a page scope attribute of type `String` (if `multiple` is not specified) or `String[]` (if `multiple` is specified).

If no request parameter with the specified name can be located, and no default value is specified, a request time exception will be thrown.

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

**[write](write.html.md)**

**Render the value of the specified bean property to the current JspWriter.**

Retrieve the value of the specified bean property, and render it to the current JspWriter as a String by the ways:

-   If `format` attribute exists then value will be formatted on base of format string from `format` attribute and default system locale.
-   If in resources exists format string for value data type (view `format` attribute description) then value will be formatted on base of format string from resources. Resources bundle and target locale can be specified with `bundle` and `locale` attributes. If nothing specified then default resource bundle and current user locale will be used.
-   If there is a PropertyEditor configured for the property value's class, the `getAsText()` method will be called.
-   Otherwise, the usual `toString()` conversions will be applied.

When a format string is provided, numeric values are formatted using the `java.text.DecimalFormat` class; if the format string came from a resource, the `applyLocalisedPattern()` method is used, and `applyPattern()` is used otherwise. Dates are formatted using the `SimpleDateFormat` class. For details of the specific format patterns, please see the Javadocs for those classes.

If a problem occurs while retrieving the specified bean property, a request time exception will be thrown.

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
