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
<td align="left"><a href="../../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useUserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.apps.mailreader.dao.UserDatabase**
-----------------------------------------------------

Packages that use [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao")

[**org.apache.struts.apps.mailreader.dao**](#org.apache.struts.apps.mailreader.dao)

  

[**org.apache.struts.apps.mailreader.dao.impl**](#org.apache.struts.apps.mailreader.dao.impl)

  

[**org.apache.struts.apps.mailreader.dao.impl.memory**](#org.apache.struts.apps.mailreader.dao.impl.memory)

  

 

<span id="org.apache.struts.apps.mailreader.dao"></span>

Uses of [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html)

 

Methods in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) that return [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao")

` UserDatabase`

`User.getDatabase()`
           Return the [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") with which we are associated.

 

<span id="org.apache.struts.apps.mailreader.dao.impl"></span>

Uses of [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html)

 

Methods in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) that return [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao")

` UserDatabase`

`AbstractUser.getDatabase()`
           The [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") with which we are associated.

 

| Constructors in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) with parameters of type [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao") |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` AbstractUser(UserDatabase database, String username)`                                                                                                                                                                                                                                                                      
            Construct a new User associated with the specified [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao").                                                                                                            |

 

<span id="org.apache.struts.apps.mailreader.dao.impl.memory"></span>

Uses of [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html)

 

Classes in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) that implement [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao")

` class`

`MemoryUserDatabase`
           Concrete implementation of [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") for an in-memory database backed by an XML data file.

 

| Constructors in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) with parameters of type [UserDatabase](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` MemoryUser(UserDatabase database, String username)`                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                             |

 

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
<td align="left"><a href="../../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useUserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
