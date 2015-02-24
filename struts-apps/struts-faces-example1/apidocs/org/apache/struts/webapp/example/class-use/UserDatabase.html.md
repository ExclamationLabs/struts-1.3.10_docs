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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md" title="interface in org.apache.struts.webapp.example"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example//class-useUserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.webapp.example.UserDatabase**
------------------------------------------------

Packages that use [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example")

[**org.apache.struts.webapp.example**](#org.apache.struts.webapp.example)

  

[**org.apache.struts.webapp.example.memory**](#org.apache.struts.webapp.example.memory)

  

 

<span id="org.apache.struts.webapp.example"></span>

Uses of [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html)

 

Methods in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html.md) that return [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html "interface in org.apache.struts.webapp.example")

` UserDatabase`

`User.getDatabase()`
           Return the [`UserDatabase`](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") with which we are associated.

 

Methods in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html.md) with parameters of type [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html "interface in org.apache.struts.webapp.example")

` User`

`LogonAction.getUser(UserDatabase database, String username)`
           Look up the user, throwing an exception to simulate business logic rule exceptions.

 

<span id="org.apache.struts.webapp.example.memory"></span>

Uses of [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html)

 

Classes in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html.md) that implement [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html "interface in org.apache.struts.webapp.example")

` class`

`MemoryUserDatabase`
           Concrete implementation of [`UserDatabase`](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") for an in-memory database backed by an XML data file.

 

Methods in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html.md) that return [UserDatabase](../../../../../../org/apache/struts/webapp/example/UserDatabase.html "interface in org.apache.struts.webapp.example")

` UserDatabase`

`MemoryUser.getDatabase()`
           The [`UserDatabase`](../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") with which we are associated.

 

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example/UserDatabase.html.md" title="interface in org.apache.struts.webapp.example"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example//class-useUserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
