------------------------------------------------------------------------

<span id="navbar_top"></span> [](#skip-navbar_top "Skip navigation links")

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MockMultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpSession.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockPageContext.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MockMultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.mock
 Class MockMultipartRequestHandler
----------------------------------

    java.lang.Object
      org.apache.struts.mock.MockMultipartRequestHandler

**All Implemented Interfaces:**  
[MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

    public class MockMultipartRequestHandler

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

Mock **MultipartRequestHandler** object for unit tests.

**Version:**  
$Rev: 471754 $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.upload.MultipartRequestHandler"></span>

| **Fields inherited from interface org.apache.struts.upload.[MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ATTRIBUTE_MAX_LENGTH_EXCEEDED`                                                                                                                                                                  |

  <span id="constructor_summary"></span>

| **Constructor Summary**          |
|----------------------------------|
| ` MockMultipartRequestHandler()` 
                                   |

  <span id="method_summary"></span>

**Method Summary**

` void`

` finish()`
           Mock `finish()` method does nothing.

` Hashtable`

` getAllElements()`
           This method returns all elements of a multipart request.

` Hashtable`

` getFileElements()`
           This method is called on to retrieve all the FormFile input elements of the request.

` ActionMapping`

` getMapping()`
           Get the ActionMapping instance for this mock request.

` ActionServlet`

` getServlet()`
           Get the mock ActionServlet instance.

` Hashtable`

` getTextElements()`
           This method is called on to retrieve all the text input elements of the request.

` void`

` handleRequest(HttpServletRequest request)`
           Mock parsing of the ServletInputStream.

` void`

` rollback()`
           Mock `rollback()` method does nothing.

` void`

` setMapping(ActionMapping mapping)`
           Convienience method to set a reference to a mock ActionMapping instance.

` void`

` setServlet(ActionServlet servlet)`
           Convienience method to set a reference to a mock ActionServlet instance.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MockMultipartRequestHandler

    public MockMultipartRequestHandler()

<span id="method_detail"></span>

**Method Detail**

### setServlet

    public void setServlet(ActionServlet servlet)

Convienience method to set a reference to a mock ActionServlet instance.

**Specified by:**  
` setServlet` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`servlet` - Mock servlet instance.

------------------------------------------------------------------------

### setMapping

    public void setMapping(ActionMapping mapping)

Convienience method to set a reference to a mock ActionMapping instance.

**Specified by:**  
` setMapping` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`mapping` - Mock action mapping instance.

------------------------------------------------------------------------

### getServlet

    public ActionServlet getServlet()

Get the mock ActionServlet instance.

**Specified by:**  
` getServlet` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The mock servlet instance.

------------------------------------------------------------------------

### getMapping

    public ActionMapping getMapping()

Get the ActionMapping instance for this mock request.

**Specified by:**  
` getMapping` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The mock action mapping instance.

------------------------------------------------------------------------

### handleRequest

    public void handleRequest(HttpServletRequest request)
                       throws ServletException

Mock parsing of the ServletInputStream.

Constructs a `Hashtable` of elements from the HttpServletRequest's parameters - no `FormFile` elements are created.

**Specified by:**  
` handleRequest` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`request` - Mock request instance.

**Throws:**  
`ServletException` - If there is a problem with processing the request.

------------------------------------------------------------------------

### getTextElements

    public Hashtable getTextElements()

This method is called on to retrieve all the text input elements of the request.

**Specified by:**  
` getTextElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
A Hashtable where the keys and values are the names and values of the request input parameters

------------------------------------------------------------------------

### getFileElements

    public Hashtable getFileElements()

This method is called on to retrieve all the FormFile input elements of the request.

**Specified by:**  
` getFileElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
This mock implementation returns an empty `Hashtable`

**See Also:**  
[`FormFile`](../../../../org/apache/struts/upload/FormFile.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

### getAllElements

    public Hashtable getAllElements()

This method returns all elements of a multipart request.

**Specified by:**  
` getAllElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
This mock implementation returns a Hashtable where the keys are input names and values are either Strings (no FormFile elements)

------------------------------------------------------------------------

### rollback

    public void rollback()

Mock `rollback()` method does nothing.

**Specified by:**  
` rollback` in interface `MultipartRequestHandler`

------------------------------------------------------------------------

### finish

    public void finish()

Mock `finish()` method does nothing.

**Specified by:**  
` finish` in interface `MultipartRequestHandler`

------------------------------------------------------------------------

<span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MockMultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpSession.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockPageContext.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MockMultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
