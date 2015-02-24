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
<td align="left"><a href="class-use/DownloadAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DispatchAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.FileStreamInfo.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.actions
 Class DownloadAction
-------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DownloadAction

------------------------------------------------------------------------

    public abstract class DownloadAction

extends [BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")

This is an abstract base class that minimizes the amount of special coding that needs to be written to download a file. All that is required to use this class is to extend it and implement the `getStreamInfo()` method so that it returns the relevant information for the file (or other stream) to be downloaded. Optionally, the `getBufferSize()` method may be overridden to customize the size of the buffer used to transfer the file.

**Since:**  
Struts 1.2.6

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

`static class`

`DownloadAction.FileStreamInfo`
           A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a file from the disk.

`static class`

`DownloadAction.ResourceStreamInfo`
           A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a web application resource.

`static interface`

`DownloadAction.StreamInfo`
           The information on a file, or other stream, to be downloaded by the `DownloadAction`.

  <span id="field_summary"></span>

**Field Summary**

`protected static int`

` DEFAULT_BUFFER_SIZE`
           If the `getBufferSize()` method is not overridden, this is the buffer size that will be used to transfer the data to the servlet output stream.

 <span id="fields_inherited_from_class_org.apache.struts.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.actions.[BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `messages`                                                                                                                                                         |

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                               |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` DownloadAction()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` copy(InputStream input, OutputStream output)`
           Copy bytes from an `InputStream` to an `OutputStream`.

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

`protected  int`

` getBufferSize()`
           Returns the size of the buffer to be used in transferring the data to the servlet output stream.

`protected abstract  DownloadAction.StreamInfo`

` getStreamInfo(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Returns the information on the file, or other stream, to be downloaded by this action.

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getLocale,  getMessages,  getResources,  getResources, getServlet,  isCancelled,  isTokenValid,  isTokenValid,  resetToken,  saveErrors,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="DEFAULT_BUFFER_SIZE"></span>

### DEFAULT\_BUFFER\_SIZE

    protected static final int DEFAULT_BUFFER_SIZE

If the `getBufferSize()` method is not overridden, this is the buffer size that will be used to transfer the data to the servlet output stream.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.actions.DownloadAction.DEFAULT_BUFFER_SIZE)

<span id="constructor_detail"></span>

**Constructor Detail**

### DownloadAction

    public DownloadAction()

<span id="method_detail"></span>

**Method Detail**

### getStreamInfo

    protected abstract DownloadAction.StreamInfo getStreamInfo(ActionMapping mapping,
                                                               ActionForm form,
                                                               HttpServletRequest request,
                                                               HttpServletResponse response)
                                                        throws Exception

Returns the information on the file, or other stream, to be downloaded by this action. This method must be implemented by an extending class.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance.

`form` - The optional ActionForm bean for this request (if any).

`request` - The HTTP request we are processing.

`response` - The HTTP response we are creating.

**Returns:**  
The information for the file to be downloaded.

**Throws:**  
`Exception` - if an exception occurs.

------------------------------------------------------------------------

### getBufferSize

    protected int getBufferSize()

Returns the size of the buffer to be used in transferring the data to the servlet output stream. This method may be overridden by an extending class in order to customize the buffer size.

**Returns:**  
The size of the transfer buffer, in bytes.

------------------------------------------------------------------------

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it). Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Overrides:**  
` execute` in class `Action`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance.

`form` - The optional ActionForm bean for this request (if any).

`request` - The HTTP request we are processing.

`response` - The HTTP response we are creating.

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if an exception occurs.

------------------------------------------------------------------------

### copy

    public int copy(InputStream input,
                    OutputStream output)
             throws IOException

Copy bytes from an `InputStream` to an `OutputStream`.

**Parameters:**  
`input` - The `InputStream` to read from.

`output` - The `OutputStream` to write to.

**Returns:**  
the number of bytes copied

**Throws:**  
`IOException` - In case of an I/O problem

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
<td align="left"><a href="class-use/DownloadAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DispatchAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.FileStreamInfo.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DownloadAction.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
