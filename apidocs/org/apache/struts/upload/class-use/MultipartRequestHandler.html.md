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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md" title="interface in org.apache.struts.upload"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/upload//class-useMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.upload.MultipartRequestHandler**
---------------------------------------------------

Packages that use [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

 

<span id="org.apache.struts.action"></span>

Uses of [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Fields in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) declared as [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html "interface in org.apache.struts.upload")

`protected  MultipartRequestHandler`

`ActionForm.multipartRequestHandler`
           The MultipartRequestHandler for this form, can be `null`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html "interface in org.apache.struts.upload")

` MultipartRequestHandler`

`ActionForm.getMultipartRequestHandler()`
           Return the `MultipartRequestHandler` for this form The reasoning behind this is to give form bean developers control over the lifecycle of their multipart requests through the use of the `finish` and/or `rollback` methods of `MultipartRequestHandler`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html "interface in org.apache.struts.upload")

` void`

`ActionForm.setMultipartRequestHandler(MultipartRequestHandler multipartRequestHandler)`
           Set the Handler provided for use in dealing with file uploads.

` void`

`ActionServletWrapper.setServletFor(MultipartRequestHandler object)`
           Set servlet to a `MultipartRequestHandler`.

 

<span id="org.apache.struts.mock"></span>

Uses of [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Classes in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) that implement [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html "interface in org.apache.struts.upload")

` class`

`MockMultipartRequestHandler`
           Mock **MultipartRequestHandler** object for unit tests.

 

<span id="org.apache.struts.upload"></span>

Uses of [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload") in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html)

 

Classes in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) that implement [MultipartRequestHandler](../../../../../org/apache/struts/upload/MultipartRequestHandler.html "interface in org.apache.struts.upload")

` class`

`CommonsMultipartRequestHandler`
            This class implements the `MultipartRequestHandler` interface by providing a wrapper around the Jakarta Commons FileUpload library.

 

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/upload/MultipartRequestHandler.html.md" title="interface in org.apache.struts.upload"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/upload//class-useMultipartRequestHandler.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
