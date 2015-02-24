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
<td align="left"><a href="class-use/DownloadAction.StreamInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/EventActionDispatcher.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.StreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.StreamInfo.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.actions
 Interface DownloadAction.StreamInfo
------------------------------------

**All Known Implementing Classes:**  
[DownloadAction.FileStreamInfo](../../../../org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md "class in org.apache.struts.actions"), [DownloadAction.ResourceStreamInfo](../../../../org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html "class in org.apache.struts.actions")

<!-- -->

**Enclosing class:**  
[DownloadAction](../../../../org/apache/struts/actions/DownloadAction.html.md "class in org.apache.struts.actions")

------------------------------------------------------------------------

    public static interface DownloadAction.StreamInfo

The information on a file, or other stream, to be downloaded by the `DownloadAction`.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` String`

` getContentType()`
           Returns the content type of the stream to be downloaded.

` InputStream`

` getInputStream()`
           Returns an input stream on the content to be downloaded.

 

<span id="method_detail"></span>

**Method Detail**

### getContentType

    String getContentType()

Returns the content type of the stream to be downloaded.

**Returns:**  
The content type of the stream.

------------------------------------------------------------------------

### getInputStream

    InputStream getInputStream()
                               throws IOException

Returns an input stream on the content to be downloaded. This stream will be closed by the `DownloadAction`.

**Returns:**  
The input stream for the content to be downloaded.

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
<td align="left"><a href="class-use/DownloadAction.StreamInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/EventActionDispatcher.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.StreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.StreamInfo.html"><strong>NO FRAMES</strong></a>    
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
