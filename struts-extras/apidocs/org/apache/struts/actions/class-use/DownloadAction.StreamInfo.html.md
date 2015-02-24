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
<td align="left"><a href="../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md" title="interface in org.apache.struts.actions"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/actions//class-useDownloadAction.StreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.StreamInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.actions.DownloadAction.StreamInfo**
------------------------------------------------------

Packages that use [DownloadAction.StreamInfo](../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md "interface in org.apache.struts.actions")

[**org.apache.struts.actions**](#org.apache.struts.actions)

The actions package provides special adapters between the incoming HTTP request and the corresponding business logic. 

 

<span id="org.apache.struts.actions"></span>

Uses of [DownloadAction.StreamInfo](../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md "interface in org.apache.struts.actions") in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html)

 

Classes in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html.md) that implement [DownloadAction.StreamInfo](../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html "interface in org.apache.struts.actions")

`static class`

`DownloadAction.FileStreamInfo`
           A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a file from the disk.

`static class`

`DownloadAction.ResourceStreamInfo`
           A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a web application resource.

 

Methods in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html.md) that return [DownloadAction.StreamInfo](../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html "interface in org.apache.struts.actions")

`protected abstract  DownloadAction.StreamInfo`

`DownloadAction.getStreamInfo(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Returns the information on the file, or other stream, to be downloaded by this action.

 

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
<td align="left"><a href="../../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md" title="interface in org.apache.struts.actions"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/actions//class-useDownloadAction.StreamInfo.html"><strong>FRAMES</strong></a>    <a href="DownloadAction.StreamInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
