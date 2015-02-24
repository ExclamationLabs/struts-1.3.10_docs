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
<td align="left"><a href="class-use/DownloadAction.ResourceStreamInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html" title="interface in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.ResourceStreamInfo.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.actions
 Class DownloadAction.ResourceStreamInfo
----------------------------------------

    java.lang.Object
      org.apache.struts.actions.DownloadAction.ResourceStreamInfo

**All Implemented Interfaces:**  
[DownloadAction.StreamInfo](../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md "interface in org.apache.struts.actions")

<!-- -->

**Enclosing class:**  
[DownloadAction](../../../../org/apache/struts/actions/DownloadAction.html.md "class in org.apache.struts.actions")

------------------------------------------------------------------------

    public static class DownloadAction.ResourceStreamInfo

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [DownloadAction.StreamInfo](../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md "interface in org.apache.struts.actions")

A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a web application resource.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                       |
|-----------------------------------------------------------------------------------------------|
| ` DownloadAction.ResourceStreamInfo(String contentType, ServletContext context, String path)` 
            Constructs an instance of this class, based on the supplied parameters.             |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getContentType()`
           Returns the content type of the stream to be downloaded.

` InputStream`

` getInputStream()`
           Returns an input stream on the resource to be downloaded.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### DownloadAction.ResourceStreamInfo

    public DownloadAction.ResourceStreamInfo(String contentType,
                                             ServletContext context,
                                             String path)

Constructs an instance of this class, based on the supplied parameters.

**Parameters:**  
`contentType` - The content type of the file.

`context` - The servlet context for the resource.

`path` - The path to the resource to be downloaded.

<span id="method_detail"></span>

**Method Detail**

### getContentType

    public String getContentType()

Returns the content type of the stream to be downloaded.

**Specified by:**  
` getContentType` in interface `DownloadAction.StreamInfo`

<!-- -->

**Returns:**  
The content type of the stream.

------------------------------------------------------------------------

### getInputStream

    public InputStream getInputStream()
                               throws IOException

Returns an input stream on the resource to be downloaded. This stream will be closed by the `DownloadAction`.

**Specified by:**  
` getInputStream` in interface `DownloadAction.StreamInfo`

<!-- -->

**Returns:**  
The input stream for the resource to be downloaded.

**Throws:**  
`IOException` - if an error occurs

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
<td align="left"><a href="class-use/DownloadAction.ResourceStreamInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html" title="interface in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.ResourceStreamInfo.html"><strong>NO FRAMES</strong></a>    
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
