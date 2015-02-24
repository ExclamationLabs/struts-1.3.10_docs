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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.apps.mailreader.dao**
----------------------------------------

Packages that use [org.apache.struts.apps.mailreader.dao](../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md)

[**org.apache.struts.apps.mailreader.dao**](#org.apache.struts.apps.mailreader.dao)

  

[**org.apache.struts.apps.mailreader.dao.impl**](#org.apache.struts.apps.mailreader.dao.impl)

  

[**org.apache.struts.apps.mailreader.dao.impl.memory**](#org.apache.struts.apps.mailreader.dao.impl.memory)

  

 

<span id="org.apache.struts.apps.mailreader.dao"></span>

| Classes in [org.apache.struts.apps.mailreader.dao](../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) used by [org.apache.struts.apps.mailreader.dao](../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html)                                                                                                                                                                                                                                        |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ExpiredPasswordException**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/ExpiredPasswordException.html.md#org.apache.struts.apps.mailreader.dao)**                                                                                                                                                                                                                                                                                                                             
            Example of an application-specific exception for which a handler can be configured.                                                                                                                                                                                                                                                                                                                                                                                                         |
| **[**Subscription**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/Subscription.html.md#org.apache.struts.apps.mailreader.dao)**                                                                                                                                                                                                                                                                                                                                                     
            A **Subscription** which is stored, along with the associated [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao"), in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                                      |
| **[**User**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/User.html.md#org.apache.struts.apps.mailreader.dao)**                                                                                                                                                                                                                                                                                                                                                                     
            A **User** which is stored, along with his or her associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s, in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                      |
| **[**UserDatabase**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/UserDatabase.html.md#org.apache.struts.apps.mailreader.dao)**                                                                                                                                                                                                                                                                                                                                                     
            A **Data Access Object** (DAO) interface describing the available operations for retrieving and storing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s (and their associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")s) in some persistence layer whose characteristics are not specified here.  |

 

<span id="org.apache.struts.apps.mailreader.dao.impl"></span>

| Classes in [org.apache.struts.apps.mailreader.dao](../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) used by [org.apache.struts.apps.mailreader.dao.impl](../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html)                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Subscription**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/Subscription.html.md#org.apache.struts.apps.mailreader.dao.impl)**                                                                                                                                                                                                                                                                                                                                                
            A **Subscription** which is stored, along with the associated [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao"), in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                                      |
| **[**User**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/User.html.md#org.apache.struts.apps.mailreader.dao.impl)**                                                                                                                                                                                                                                                                                                                                                                
            A **User** which is stored, along with his or her associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s, in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                      |
| **[**UserDatabase**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/UserDatabase.html.md#org.apache.struts.apps.mailreader.dao.impl)**                                                                                                                                                                                                                                                                                                                                                
            A **Data Access Object** (DAO) interface describing the available operations for retrieving and storing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s (and their associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")s) in some persistence layer whose characteristics are not specified here.  |

 

<span id="org.apache.struts.apps.mailreader.dao.impl.memory"></span>

| Classes in [org.apache.struts.apps.mailreader.dao](../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) used by [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html)                                                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Subscription**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/Subscription.html.md#org.apache.struts.apps.mailreader.dao.impl.memory)**                                                                                                                                                                                                                                                                                                                                         
            A **Subscription** which is stored, along with the associated [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao"), in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                                      |
| **[**User**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/User.html.md#org.apache.struts.apps.mailreader.dao.impl.memory)**                                                                                                                                                                                                                                                                                                                                                         
            A **User** which is stored, along with his or her associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s, in a [`UserDatabase`](../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html "interface in org.apache.struts.apps.mailreader.dao").                                                                                                                      |
| **[**UserDatabase**](../../../../../../org/apache/struts/apps/mailreader/dao/class-use/UserDatabase.html.md#org.apache.struts.apps.mailreader.dao.impl.memory)**                                                                                                                                                                                                                                                                                                                                         
            A **Data Access Object** (DAO) interface describing the available operations for retrieving and storing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s (and their associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")s) in some persistence layer whose characteristics are not specified here.  |

 

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.