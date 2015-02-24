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
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useUser.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.apps.mailreader.dao.User**
---------------------------------------------

Packages that use [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")

[**org.apache.struts.apps.mailreader.dao**](#org.apache.struts.apps.mailreader.dao)

  

[**org.apache.struts.apps.mailreader.dao.impl**](#org.apache.struts.apps.mailreader.dao.impl)

  

[**org.apache.struts.apps.mailreader.dao.impl.memory**](#org.apache.struts.apps.mailreader.dao.impl.memory)

  

 

<span id="org.apache.struts.apps.mailreader.dao"></span>

Uses of [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html)

 

Methods in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) that return [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` User`

`UserDatabase.createUser(String username)`
           Create and return a new [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") defined in this user database.

` User`

`UserDatabase.findUser(String username)`
           Return the existing [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") with the specified username, if any; otherwise return `null`.

` User[]`

`UserDatabase.findUsers()`
           Return the set of [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s defined in this user database.

` User`

`Subscription.getUser()`
           Return the [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") owning this Subscription.

 

Methods in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) with parameters of type [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` void`

`UserDatabase.removeUser(User user)`
           Remove the specified [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") from this database.

 

<span id="org.apache.struts.apps.mailreader.dao.impl"></span>

Uses of [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html)

 

Classes in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) that implement [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` class`

`AbstractUser`
           Concrete implementation of [`AbstractUser`](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl").

 

Methods in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) that return [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` User`

`AbstractSubscription.getUser()`
           The User owning this Subscription.

 

| Constructors in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) with parameters of type [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` AbstractSubscription(User user, String host)`                                                                                                                                                                                                                                                              
            Construct a new Subscription associated with the specified [`User`](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao").                                                                                                    |

 

<span id="org.apache.struts.apps.mailreader.dao.impl.memory"></span>

Uses of [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html)

 

Classes in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) that implement [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` class`

`MemoryUser`
           Concrete implementation of [`AbstractUser`](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl") used for an in-memory database backed by an XML data file.

 

Methods in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) that return [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` User`

`MemoryUserDatabase.createUser(String username)`
            

` User`

`MemoryUserDatabase.findUser(String username)`
            

` User[]`

`MemoryUserDatabase.findUsers()`
            

 

Methods in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) with parameters of type [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao")

` void`

`MemoryUserDatabase.removeUser(User user)`
            

 

| Constructors in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) with parameters of type [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html "interface in org.apache.struts.apps.mailreader.dao") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` MemorySubscription(User user, String host)`                                                                                                                                                                                                                                                                              
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
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useUser.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
