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
<td align="left"><a href="class-use/CommonsMultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/upload/FormFile.html.md" title="interface in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/CommonsMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="CommonsMultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.upload
 Class CommonsMultipartRequestHandler
-------------------------------------

    java.lang.Object
      org.apache.struts.upload.CommonsMultipartRequestHandler

**All Implemented Interfaces:**  
[MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

    public class CommonsMultipartRequestHandler

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

This class implements the `MultipartRequestHandler` interface by providing a wrapper around the Jakarta Commons FileUpload library.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 524895 $ $Date: 2007-04-02 14:29:21 -0500 (Mon, 02 Apr 2007) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static long`

` DEFAULT_SIZE_MAX`
            The default value for the maximum allowable size, in bytes, of an uploaded file.

`static int`

` DEFAULT_SIZE_THRESHOLD`
            The default value for the threshold which determines whether an uploaded file will be written to disk or cached in memory.

`protected static Log`

` log`
            Commons Logging instance.

 <span id="fields_inherited_from_class_org.apache.struts.upload.MultipartRequestHandler"></span>

| **Fields inherited from interface org.apache.struts.upload.[MultipartRequestHandler](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ATTRIBUTE_MAX_LENGTH_EXCEEDED`                                                                                                                                                                  |

  <span id="constructor_summary"></span>

| **Constructor Summary**             |
|-------------------------------------|
| ` CommonsMultipartRequestHandler()` 
                                      |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` addFileParameter(org.apache.commons.fileupload.FileItem item)`
            Adds a file parameter to the set of file parameters for this request and also to the list of all parameters.

`protected  void`

` addTextParameter(HttpServletRequest request, org.apache.commons.fileupload.FileItem item)`
            Adds a regular text parameter to the set of text parameters for this request and also to the list of all parameters.

`protected  long`

` convertSizeToBytes(String sizeString, long defaultSize)`
            Converts a size value from a string representation to its numeric value.

` void`

` finish()`
            Cleans up at the end of a request.

` Hashtable`

` getAllElements()`
            Returns a hash table containing both text and file request parameters.

` Hashtable`

` getFileElements()`
            Returns a hash table containing the file (that is, non-text) request parameters.

` ActionMapping`

` getMapping()`
            Retrieves the action mapping with which this handler is associated.

`protected  String`

` getRepositoryPath(ModuleConfig mc)`
            Returns the path to the temporary directory to be used for uploaded files which are written to disk.

` ActionServlet`

` getServlet()`
            Retrieves the servlet with which this handler is associated.

`protected  long`

` getSizeMax(ModuleConfig mc)`
            Returns the maximum allowable size, in bytes, of an uploaded file.

`protected  long`

` getSizeThreshold(ModuleConfig mc)`
            Returns the size threshold which determines whether an uploaded file will be written to disk or cached in memory.

` Hashtable`

` getTextElements()`
            Returns a hash table containing the text (that is, non-file) request parameters.

` void`

` handleRequest(HttpServletRequest request)`
            Parses the input stream and partitions the parsed items into a set of form fields and a set of file items.

` void`

` rollback()`
            Cleans up when a problem occurs during request processing.

` void`

` setMapping(ActionMapping mapping)`
            Sets the action mapping with which this handler is associated.

` void`

` setServlet(ActionServlet servlet)`
            Sets the servlet with which this handler is associated.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="DEFAULT_SIZE_MAX"></span>

### DEFAULT\_SIZE\_MAX

    public static final long DEFAULT_SIZE_MAX

The default value for the maximum allowable size, in bytes, of an uploaded file. The value is equivalent to 250MB.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.upload.CommonsMultipartRequestHandler.DEFAULT_SIZE_MAX)

------------------------------------------------------------------------

<span id="DEFAULT_SIZE_THRESHOLD"></span>

### DEFAULT\_SIZE\_THRESHOLD

    public static final int DEFAULT_SIZE_THRESHOLD

The default value for the threshold which determines whether an uploaded file will be written to disk or cached in memory. The value is equivalent to 250KB.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.upload.CommonsMultipartRequestHandler.DEFAULT_SIZE_THRESHOLD)

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

<span id="constructor_detail"></span>

**Constructor Detail**

### CommonsMultipartRequestHandler

    public CommonsMultipartRequestHandler()

<span id="method_detail"></span>

**Method Detail**

### getServlet

    public ActionServlet getServlet()

Retrieves the servlet with which this handler is associated.

**Specified by:**  
` getServlet` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The associated servlet.

------------------------------------------------------------------------

### setServlet

    public void setServlet(ActionServlet servlet)

Sets the servlet with which this handler is associated.

**Specified by:**  
` setServlet` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`servlet` - The associated servlet.

------------------------------------------------------------------------

### getMapping

    public ActionMapping getMapping()

Retrieves the action mapping with which this handler is associated.

**Specified by:**  
` getMapping` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The associated action mapping.

------------------------------------------------------------------------

### setMapping

    public void setMapping(ActionMapping mapping)

Sets the action mapping with which this handler is associated.

**Specified by:**  
` setMapping` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`mapping` - The associated action mapping.

------------------------------------------------------------------------

### handleRequest

    public void handleRequest(HttpServletRequest request)
                       throws ServletException

Parses the input stream and partitions the parsed items into a set of form fields and a set of file items. In the process, the parsed items are translated from Commons FileUpload `FileItem` instances to Struts `FormFile` instances.

**Specified by:**  
` handleRequest` in interface `MultipartRequestHandler`

<!-- -->

**Parameters:**  
`request` - The multipart request to be processed.

**Throws:**  
`ServletException` - if an unrecoverable error occurs.

------------------------------------------------------------------------

### getTextElements

    public Hashtable getTextElements()

Returns a hash table containing the text (that is, non-file) request parameters.

**Specified by:**  
` getTextElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The text request parameters.

------------------------------------------------------------------------

### getFileElements

    public Hashtable getFileElements()

Returns a hash table containing the file (that is, non-text) request parameters.

**Specified by:**  
` getFileElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The file request parameters.

**See Also:**  
[`FormFile`](../../../../org/apache/struts/upload/FormFile.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

### getAllElements

    public Hashtable getAllElements()

Returns a hash table containing both text and file request parameters.

**Specified by:**  
` getAllElements` in interface `MultipartRequestHandler`

<!-- -->

**Returns:**  
The text and file request parameters.

------------------------------------------------------------------------

### rollback

    public void rollback()

Cleans up when a problem occurs during request processing.

**Specified by:**  
` rollback` in interface `MultipartRequestHandler`

------------------------------------------------------------------------

### finish

    public void finish()

Cleans up at the end of a request.

**Specified by:**  
` finish` in interface `MultipartRequestHandler`

------------------------------------------------------------------------

### getSizeMax

    protected long getSizeMax(ModuleConfig mc)

Returns the maximum allowable size, in bytes, of an uploaded file. The value is obtained from the current module's controller configuration.

**Parameters:**  
`mc` - The current module's configuration.

**Returns:**  
The maximum allowable file size, in bytes.

------------------------------------------------------------------------

### getSizeThreshold

    protected long getSizeThreshold(ModuleConfig mc)

Returns the size threshold which determines whether an uploaded file will be written to disk or cached in memory.

**Parameters:**  
`mc` - The current module's configuration.

**Returns:**  
The size threshold, in bytes.

------------------------------------------------------------------------

### convertSizeToBytes

    protected long convertSizeToBytes(String sizeString,
                                      long defaultSize)

Converts a size value from a string representation to its numeric value. The string must be of the form nnnm, where nnn is an arbitrary decimal value, and m is a multiplier. The multiplier must be one of 'K', 'M' and 'G', representing kilobytes, megabytes and gigabytes respectively.

If the size value cannot be converted, for example due to invalid syntax, the supplied default is returned instead.

**Parameters:**  
`sizeString` - The string representation of the size to be converted.

`defaultSize` - The value to be returned if the string is invalid.

**Returns:**  
The actual size in bytes.

------------------------------------------------------------------------

### getRepositoryPath

    protected String getRepositoryPath(ModuleConfig mc)

Returns the path to the temporary directory to be used for uploaded files which are written to disk. The directory used is determined from the first of the following to be non-empty.

A temp dir explicitly defined either using the `tempDir` servlet init param, or the `tempDir` attribute of the \<controller\> element in the Struts config file.

The container-specified temp dir, obtained from the `javax.servlet.context.tempdir` servlet context attribute.

The temp dir specified by the `java.io.tmpdir` system property.

(/ol\>

**Parameters:**  
`mc` - The module config instance for which the path should be determined.

**Returns:**  
The path to the directory to be used to store uploaded files.

------------------------------------------------------------------------

### addTextParameter

    protected void addTextParameter(HttpServletRequest request,
                                    org.apache.commons.fileupload.FileItem item)

Adds a regular text parameter to the set of text parameters for this request and also to the list of all parameters. Handles the case of multiple values for the same parameter by using an array for the parameter value.

**Parameters:**  
`request` - The request in which the parameter was specified.

`item` - The file item for the parameter to add.

------------------------------------------------------------------------

### addFileParameter

    protected void addFileParameter(org.apache.commons.fileupload.FileItem item)

Adds a file parameter to the set of file parameters for this request and also to the list of all parameters.

**Parameters:**  
`item` - The file item for the parameter to add.

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
<td align="left"><a href="class-use/CommonsMultipartRequestHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/upload/FormFile.html.md" title="interface in org.apache.struts.upload"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/CommonsMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="CommonsMultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
