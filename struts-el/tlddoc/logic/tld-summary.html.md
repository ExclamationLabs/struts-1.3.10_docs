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

logic
-----

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix="logic" uri="http://struts.apache.org/tags-logic-el" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:logic="http://struts.apache.org/tags-logic-el" />`

------------------------------------------------------------------------


    This tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management. 
    For tags that do value comparisons (equal, greaterEqual, greaterThan, lessEqual, lessThan, notEqual), the following rules apply: 

-   The specified value is examined. If it can be converted successfully to a double or a long, it is assumed that the ultimate comparison will be numeric (either floating point or integer). Otherwise, a String comparison will be performed.
-   The variable to be compared to is retrieved, based on the selector attribute(s) (cookie, header, name, parameter, property) present on this tag. It will be converted to the appropriate type for the comparison, as determined above.
-   If the specified variable or property returns null, it will be coerced to a zero-length string before the comparison occurs.
-   The specific comparison for this tag will be performed, and the nested body content of this tag will be evaluated if the comparison returns a true result.

<!-- -->

     
     For tags that do substring matching (match, notMatch), the following rules apply: 

-   The specified variable is retrieved, based on the selector attribute(s) (cookie, header, name, parameter, property) present on this tag.
-   The variable is converted to a String, if necessary.A request time exception will be thrown if the specified variable cannot be retrieved, or has a null value.
-   The specified value is checked for existence as a substring of the variable, in the position specified by the location attribute, as follows: at the beginning (if location is set to start), at the end (if location is set to end), or anywhere (if location is not specified).

<!-- -->

     
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION. 
    Struts-logic tags NOT implemented. 
    This library, a derivation of the normal "struts-logic" library, provides the functionality of the Struts logic tags, but assumes the presence of the JavaServer Pages Standard Library (JSTL), and uses the JSTL expression engine (hereafter abbreviated in many places as just "el") to evaluate attribute values instead of using JSP runtime expressions (sometimes called "rtexprvalues"). 
    Because it is assumed this library will be used with the JSTL and the new EL engine, there are some tags in the struts-logic library which provide functionality which is entirely subsumed by the JSTL. This section lists each struts-logic tag which is NOT implemented in the struts-logic-el library, and describes the JSTL tag which can be used instead of the Struts tag.Struts-Logic TagJSTL Tag 
    <logic:empty> 
    This functionality is subsumed by the JSTL <c:if>, <c:when> tags and the empty function in the JSTL EL. 
    Example: <c:if test="${empty var}">CONTENT</c:if>

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

logic

URI

http://struts.apache.org/tags-logic-el

 

**Tag Summary**

**[forward](forward.html.md)**

**Forward control to the page specified by the specified ActionForward entry.**

Performs a `PageContext.forward()` or `HttpServletResponse.sendRedirect()` call for the global `ActionForward` entry for the specified name. URL rewriting will occur automatically if a redirect is performed.

**[iterate](iterate.html.md)**

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

**[match](match.html.md)**

**Evaluate the nested body content of this tag if the specified value is an appropriate substring of the requested variable.**

Matches the variable specified by one of the selector attributes (as a String) against the specified constant value. If the value is a substring (appropriately limited by the `location` attribute), the nested body content of this tag is evaluated.

**[messagesNotPresent](messagesNotPresent.html.md)**

**Generate the nested body content of this tag if the specified message is not present in this request.**

Evaluates the nested body content of this tag if an `ActionMessages` object, `ActionErrors` object, a String, or a String array is not in request scope. If such a bean is not found, nothing will be rendered.

**Since:**  
Struts 1.1

**[messagesPresent](messagesPresent.html.md)**

**Generate the nested body content of this tag if the specified message is present in this request.**

Evaluates the nested body content of this tag if an `ActionMessages` object, `ActionErrors` object, a String, or a String array is in request scope. If such a bean is not found, nothing will be rendered.

**Since:**  
Struts 1.1

**[notMatch](notMatch.html.md)**

**Evaluate the nested body content of this tag if the specified value is not an appropriate substring of the requested variable.**

Matches the variable specified by one of the selector attributes (as a String) against the specified constant value. If the value is not a substring (appropriately limited by the `location` attribute), the nested body content of this tag is evaluated.

**[notPresent](notPresent.html.md)**

**Generate the nested body content of this tag if the specified value is not present in this request.**

Depending on which attribute is specified, this tag checks the current request, and evaluates the nested body content of this tag only if the specified value **is not** present. Only one of the attributes may be used in one occurrence of this tag, unless you use the `property` attribute, in which case the `name` attribute is also required.

**[present](present.html.md)**

**Generate the nested body content of this tag if the specified value is present in this request.**

Depending on which attribute is specified, this tag checks the current request, and evaluates the nested body content of this tag only if the specified value **is** present. Only one of the attributes may be used in one occurrence of this tag, unless you use the `property` attribute, in which case the `name` attribute is also required.

**[redirect](redirect.html.md)**

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
