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
<td align="left"><strong> Overview </strong></td>
<td align="left"> Library </td>
<td align="left"> Tag </td>
<td align="left"> <a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="index.html.md"><strong>FRAMES</strong></a>   <a href="overview-summary.html"><strong>NO FRAMES</strong></a> 
<a href="alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

Tag Library Documentation Generator - Generated Documentation
-------------------------------------------------------------

**Tag Libraries**

**[bean](bean/tld-summary.html.md)**

    This tag library contains tags useful in accessing beans and their properties, as well as defining new beans (based on these accesses) that are accessible to the remainder of the page via scripting variables and page scope attributes. Convenient mechanisms to create new beans based on the value of request cookies, headers, and parameters are also provided.Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.If you are viewing this page from within the Struts Documentation Application (or online at http://struts.apache.org), you can learn more about using these tags in the Bean Tags Developer's Guide.

**.html.md](html/tld-summary.html)**

    This taglib contains tags used to create struts input forms, as well as other tags generally useful in the creation of HTML-based user interfaces. Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**[logic](logic/tld-summary.html.md)**


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

**[tiles](tiles/tld-summary.html.md)**


    This tag library provides tiles tags. Tiles were previously called Components. For historical reasons, names, pages, components and templates are used indifferently to design a tile. Also, a lot of tags and attribute names are left for backward compatibility. To know more about tags defined in this library, check the associated documentation: tiles-doc.

------------------------------------------------------------------------

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
<td align="left"><strong> Overview </strong></td>
<td align="left"> Library </td>
<td align="left"> Tag </td>
<td align="left"> <a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="index.html.md"><strong>FRAMES</strong></a>   <a href="overview-summary.html"><strong>NO FRAMES</strong></a> 
<a href="alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
