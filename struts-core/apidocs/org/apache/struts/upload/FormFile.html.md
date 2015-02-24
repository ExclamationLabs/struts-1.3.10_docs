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
<td align="left"><a href="class-use/FormFile.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/CommonsMultipartRequestHandler.html.md" title="class in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/upload/MultipartRequestHandler.html" title="interface in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/FormFile.html"><strong>FRAMES</strong></a>    <a href="FormFile.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.upload
 Interface FormFile
------------------------

------------------------------------------------------------------------

    public interface FormFile

This interface represents a file that has been uploaded by a client. It is the only interface or class in upload package which is typically referenced directly by a Struts application.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

`destroy()`
            Destroys all content for the uploaded file, including any underlying data files.

` String`

` getContentType()`
            Returns the content type for this file.

` byte[]`

`getFileData()`
            Returns the data for the entire file as byte array.

` String`

`getFileName()`
            Returns the file name of this file.

` int`

`getFileSize()`
            Returns the size of this file.

` InputStream`

` getInputStream()`
            Returns an input stream for this file.

` void`

` setContentType(String contentType)`
            Sets the content type for this file.

` void`

` setFileName(String fileName)`
            Sets the file name of this file.

` void`

` setFileSize(int fileSize)`
            Sets the file size.

 

<span id="method_detail"></span>

**Method Detail**

### getContentType

    String getContentType()

Returns the content type for this file.

**Returns:**  
A String representing content type.

------------------------------------------------------------------------

### setContentType

    void setContentType(String contentType)

Sets the content type for this file.

**Parameters:**  
`contentType` - The content type for the file.

------------------------------------------------------------------------

### getFileSize

    int getFileSize()

Returns the size of this file.

**Returns:**  
The size of the file, in bytes.

------------------------------------------------------------------------

### setFileSize

    void setFileSize(int fileSize)

Sets the file size.

**Parameters:**  
`fileSize` - The size of the file, in bytes,

------------------------------------------------------------------------

### getFileName

    String getFileName()

Returns the file name of this file. This is the base name of the file, as supplied by the user when the file was uploaded.

**Returns:**  
The base file name.

------------------------------------------------------------------------

### setFileName

    void setFileName(String fileName)

Sets the file name of this file.

**Parameters:**  
`fileName` - The base file name.

------------------------------------------------------------------------

### getFileData

    byte[] getFileData()
                       throws FileNotFoundException,
                              IOException

Returns the data for the entire file as byte array. Care is needed when using this method, since a large upload could easily exhaust available memory. The preferred method for accessing the file data is [`getInputStream`](../../../../org/apache/struts/upload/FormFile.html.md#getInputStream()).

**Returns:**  
The file data as a byte array.

**Throws:**  
`FileNotFoundException` - if the uploaded file is not found.

`IOException` - if an error occurred while reading the file.

------------------------------------------------------------------------

### getInputStream

    InputStream getInputStream()
                               throws FileNotFoundException,
                                      IOException

Returns an input stream for this file. The caller must close the stream when it is no longer needed.

**Throws:**  
`FileNotFoundException` - if the uploaded file is not found.

`IOException` - if an error occurred while reading the file.

------------------------------------------------------------------------

### destroy

    void destroy()

Destroys all content for the uploaded file, including any underlying data files.

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
<td align="left"><a href="class-use/FormFile.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/CommonsMultipartRequestHandler.html.md" title="class in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/upload/MultipartRequestHandler.html" title="interface in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/FormFile.html"><strong>FRAMES</strong></a>    <a href="FormFile.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
