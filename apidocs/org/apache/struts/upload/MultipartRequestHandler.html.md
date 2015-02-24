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
<td align="left"><a href="class-use/MultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/FormFile.html.md" title="interface in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/upload/MultipartRequestWrapper.html" title="class in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/MultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.upload
 Interface MultipartRequestHandler
----------------------------------

**All Known Implementing Classes:**  
[CommonsMultipartRequestHandler](../../../../org/apache/struts/upload/CommonsMultipartRequestHandler.html.md "class in org.apache.struts.upload"), [MockMultipartRequestHandler](../../../../org/apache/struts/mock/MockMultipartRequestHandler.html "class in org.apache.struts.mock")

------------------------------------------------------------------------

    public interface MultipartRequestHandler

MultipartRequestHandler provides an standard interface for struts to deal with file uploads from forms with enctypes of "multipart/form-data". Providers must provide a no-argument constructor for initialization.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` ATTRIBUTE_MAX_LENGTH_EXCEEDED`
            This is the ServletRequest attribute that should be set when a multipart request is being read and the maximum length is exceeded.

  <span id="method_summary"></span>

**Method Summary**

` void`

` finish()`
            This method is called on when a successful form post has been made.

` Hashtable`

` getAllElements()`
            This method returns all elements of a multipart request.

` Hashtable`

` getFileElements()`
            This method is called on to retrieve all the FormFile input elements of the request.

` ActionMapping`

` getMapping()`
            Get the ActionMapping instance for this request

` ActionServlet`

` getServlet()`
            Get the ActionServlet instance

` Hashtable`

` getTextElements()`
            This method is called on to retrieve all the text input elements of the request.

` void`

` handleRequest(HttpServletRequest request)`
            After constructed, this is the first method called on by ActionServlet.

` void`

` rollback()`
            This method is called on when there's some sort of problem and the form post needs to be rolled back.

` void`

` setMapping(ActionMapping mapping)`
            Convienience method to set a reference to a working ActionMapping instance.

` void`

` setServlet(ActionServlet servlet)`
            Convienience method to set a reference to a working ActionServlet instance.

 

<span id="field_detail"></span>

**Field Detail**

<span id="ATTRIBUTE_MAX_LENGTH_EXCEEDED"></span>

### ATTRIBUTE\_MAX\_LENGTH\_EXCEEDED

    static final String ATTRIBUTE_MAX_LENGTH_EXCEEDED

This is the ServletRequest attribute that should be set when a multipart request is being read and the maximum length is exceeded. The value is a Boolean. If the maximum length isn't exceeded, this attribute shouldn't be put in the ServletRequest. It's the job of the implementation to put this attribute in the request if the maximum length is exceeded; in the handleRequest(HttpServletRequest) method.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.upload.MultipartRequestHandler.ATTRIBUTE_MAX_LENGTH_EXCEEDED)

<span id="method_detail"></span>

**Method Detail**

### setServlet

    void setServlet(ActionServlet servlet)

Convienience method to set a reference to a working ActionServlet instance.

------------------------------------------------------------------------

### setMapping

    void setMapping(ActionMapping mapping)

Convienience method to set a reference to a working ActionMapping instance.

------------------------------------------------------------------------

### getServlet

    ActionServlet getServlet()

Get the ActionServlet instance

------------------------------------------------------------------------

### getMapping

    ActionMapping getMapping()

Get the ActionMapping instance for this request

------------------------------------------------------------------------

### handleRequest

    void handleRequest(HttpServletRequest request)
                       throws ServletException

After constructed, this is the first method called on by ActionServlet. Use this method for all your data-parsing of the ServletInputStream in the request

**Throws:**  
`ServletException` - thrown if something goes wrong

------------------------------------------------------------------------

### getTextElements

    Hashtable getTextElements()

This method is called on to retrieve all the text input elements of the request.

**Returns:**  
A Hashtable where the keys and values are the names and values of the request input parameters

------------------------------------------------------------------------

### getFileElements

    Hashtable getFileElements()

This method is called on to retrieve all the FormFile input elements of the request.

**Returns:**  
A Hashtable where the keys are the input names of the files and the values are FormFile objects

**See Also:**  
[`FormFile`](../../../../org/apache/struts/upload/FormFile.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

### getAllElements

    Hashtable getAllElements()

This method returns all elements of a multipart request.

**Returns:**  
A Hashtable where the keys are input names and values are either String arrays or FormFiles

------------------------------------------------------------------------

### rollback

    void rollback()

This method is called on when there's some sort of problem and the form post needs to be rolled back. Providers should remove any FormFiles used to hold information by setting them to null and also physically delete them if the implementation calls for writing directly to disk. NOTE: Currently implemented but not automatically supported, ActionForm implementors must call rollback() manually for rolling back file uploads.

------------------------------------------------------------------------

### finish

    void finish()

This method is called on when a successful form post has been made. Some implementations will use this to destroy temporary files or write to a database or something of that nature.

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
<td align="left"><a href="class-use/MultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/FormFile.html.md" title="interface in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/upload/MultipartRequestWrapper.html" title="class in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/MultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
