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


    Note: Some of the features in this taglib are also available in the JavaServer Pages Standard Tag Library (JSTL). The Struts team encourages the use of the standard tags over the Struts specific tags when possible. 
    This tag library contains tags useful in accessing beans and their properties, as well as defining new beans (based on these accesses) that are accessible to the remainder of the page via scripting variables and page scope attributes. Convenient mechanisms to create new beans based on the value of request cookies, headers, and parameters are also provided. 
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**.html.md](html/tld-summary.html)**


     This taglib contains tags used to create struts input forms, as well as other tags generally useful in the creation of HTML-based user interfaces.  
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**[logic](logic/tld-summary.html.md)**


    Note: Some of the features in this taglib are also available in the JavaServer Pages Standard Tag Library (JSTL). The Struts team encourages the use of the standard tags over the Struts specific tags when possible. 
    This tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management. 
    For tags that do value comparisons (equal, greaterEqual, greaterThan, lessEqual, lessThan, notEqual), the following rules apply: 

-   The specified value is examined. If it can be converted successfully to a `double` or a `long`, it is assumed that the ultimate comparison will be numeric (either floating point or integer). Otherwise, a String comparison will be performed.
-   The variable to be compared to is retrieved, based on the selector attribute(s) (`cookie`, `header`, `name`, `parameter`, `property`) present on this tag. It will be converted to the appropriate type for the comparison, as determined above.
-   If the specified variable or property returns null, it will be coerced to a zero-length string before the comparison occurs.
-   The specific comparison for this tag will be performed, and the nested body content of this tag will be evaluated if the comparison returns a `true` result.

<!-- -->

     
    For tags that do substring matching (match, notMatch), the following rules apply: 

-   The specified variable is retrieved, based on the selector attribute(s) (`cookie`, `header`, `name`, `parameter`, `property`) present on this tag. The variable is converted to a String, if necessary.
-   A request time exception will be thrown if the specified variable cannot be retrieved, or has a null value.
-   The specified value is checked for existence as a substring of the variable, in the position specified by the `location` attribute, as follows: at the beginning (if location is set to `start`), at the end (if location is set to `end`), or anywhere (if location is not specified).

<!-- -->

     
    Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the <%@ page %> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

**[nested](nested/tld-summary.html.md)**


    [Since Struts 1.1] 
    This tag library brings a nested context to the functionality of the Struts custom tag library. 
    It's written in a layer that extends the current Struts tags, building on their logic and functionality. The layer enables the tags to be aware of the tags which surround them so they can correctly provide the nesting property reference to the Struts system.  
    It's all about nesting beans...
     A bean holds a reference to another bean internally, and all access to that bean is handled through the current bean. This act of having one bean's access go through another bean is known as "nesting beans". The first bean is known as the parent bean. The bean which it references, is known as a child bean. The terms "parent" and "child" are commonly used to describe the model's hierarchy.  
    A simple example... 
     Take an object which represents a monkey. The monkey's job is to pick bunches of bananas. On each bunch picked hangs many bananas. If this case was translated to bean objects, the monkey object would have a reference to the bunch objects he picked, and each bunch object would hold a reference to the bananas hanging in the bunch.  
    To describe this... 
     The monkey object is the parent to the bunch object, and the bunch object is a child of the monkey object. The bunch object is parent to its child banana objects, and the child banana objects children of the bunch object. The monkey is higher in the hierarchy than the bananas, and the bananas lower in the hierarchy to the bunches.  
    One special term to remember is for the most parent class, which is known as the "root" object which starts the hierarchy. 
    Nested tags are all about efficiently managing this style of hierarchy structure within your JSP markup. 
     Important Note: Nearly all these tags extend tags from other libraries to bring their functionality into the nested context. Nesting relies on the tags working against the one bean model, and managing the properties so that they become relative to the properties they are nested within. In doing so, the tags will set the "name" attribute internally (where applicable), and in many cases will rely on the "property" attribute being set so it can be updated internally to become nested. The original tags on occasion provide options that don't use the "name" and "property" attributes. These uses will then fall outside the nested context, and will most likely cause error. To take advantage of these options, markup using the original tag for these cases. For an example see the <nested:options> tag. 

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
