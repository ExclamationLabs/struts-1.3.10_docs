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
<td align="left"><a href="../../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/actions//class-useBaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.actions.BaseAction**
---------------------------------------

Packages that use [BaseAction](../../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")

[**org.apache.struts.actions**](#org.apache.struts.actions)

The actions package provides special adapters between the incoming HTTP request and the corresponding business logic. 

 

<span id="org.apache.struts.actions"></span>

Uses of [BaseAction](../../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions") in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html)

 

Subclasses of [BaseAction](../../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions") in [org.apache.struts.actions](../../../../../org/apache/struts/actions/package-summary.html)

` class`

`DispatchAction`
           An abstract **Action** that dispatches to a public method that is named by the request parameter whose name is specified by the `parameter` property of the corresponding ActionMapping.

` class`

`DownloadAction`
           This is an abstract base class that minimizes the amount of special coding that needs to be written to download a file.

` class`

`EventDispatchAction`
           An **Action** that dispatches to to one of the public methods that are named in the `parameter` attribute of the corresponding ActionMapping and matches a submission parameter.

` class`

`ForwardAction`
           An **Action** that forwards to the context-relative URI specified by the `parameter` property of our associated `ActionMapping`.

` class`

`IncludeAction`
           An **Action** that includes the context-relative URI specified by the `parameter` property of our associated `ActionMapping`.

` class`

`LocaleAction`
           Implementation of **Action** that changes the user's [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") and forwards to a page, based on request level parameters that are set (language, country, & page).

` class`

`LookupDispatchAction`
            An abstract **Action** that dispatches to the subclass mapped `execute` method.

` class`

`MappingDispatchAction`
           An abstract **Action** that dispatches to a public method that is named by the `parameter` attribute of the corresponding ActionMapping.

` class`

`SwitchAction`
           A standard **Action** that switches to a new module and then forwards control to a URI (specified in a number of possible ways) within the new module.

 

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
<td align="left"><a href="../../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/actions//class-useBaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
