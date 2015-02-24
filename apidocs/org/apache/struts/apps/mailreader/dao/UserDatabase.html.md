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
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/UserDatabase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/UserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader.dao
 Interface UserDatabase
-------------------------------------

**All Known Implementing Classes:**  
[MemoryUserDatabase](../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUserDatabase.html.md "class in org.apache.struts.apps.mailreader.dao.impl.memory")

------------------------------------------------------------------------

    public interface UserDatabase

A **Data Access Object** (DAO) interface describing the available operations for retrieving and storing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s (and their associated [`Subscription`](../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")s) in some persistence layer whose characteristics are not specified here. One or more implementations will be created to perform the actual I/O that is required.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

` close()`
           Finalize access to the underlying persistence layer.

` User`

` createUser(String username)`
           Create and return a new [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") defined in this user database.

` User`

` findUser(String username)`
           Return the existing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") with the specified username, if any; otherwise return `null`.

` User[]`

` findUsers()`
           Return the set of [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s defined in this user database.

` boolean`

` isOpen()`
           Return true if open() has been called.

` void`

` open()`
           Initiate access to the underlying persistence layer.

` void`

` removeUser(User user)`
           Remove the specified [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") from this database.

` void`

` save()`
           Save any pending changes to the underlying persistence layer.

 

<span id="method_detail"></span>

**Method Detail**

### createUser

    User createUser(String username)

Create and return a new [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") defined in this user database.

**Parameters:**  
`username` - Username of the new user

**Throws:**  
`IllegalArgumentException` - if the specified username is not unique

------------------------------------------------------------------------

### close

    void close()
               throws Exception

Finalize access to the underlying persistence layer.

**Throws:**  
`Exception` - if a database access error occurs

------------------------------------------------------------------------

### findUser

    User findUser(String username)
                  throws ExpiredPasswordException

Return the existing [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") with the specified username, if any; otherwise return `null`.

**Parameters:**  
`username` - Username of the user to retrieve

**Throws:**  
`ExpiredPasswordException` - if user password has expired and must be changed

------------------------------------------------------------------------

### findUsers

    User[] findUsers()

Return the set of [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")s defined in this user database.

------------------------------------------------------------------------

### isOpen

    boolean isOpen()

Return true if open() has been called.

**Throws:**  
`Exception` - if a database access error occurs

------------------------------------------------------------------------

### open

    void open()
              throws Exception

Initiate access to the underlying persistence layer.

**Throws:**  
`Exception` - if a database access error occurs

------------------------------------------------------------------------

### removeUser

    void removeUser(User user)

Remove the specified [`User`](../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao") from this database.

**Parameters:**  
`user` - User to be removed

**Throws:**  
`IllegalArgumentException` - if the specified user is not associated with this database

------------------------------------------------------------------------

### save

    void save()
              throws Exception

Save any pending changes to the underlying persistence layer.

**Throws:**  
`Exception` - if a database access error occurs

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
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/UserDatabase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/UserDatabase.html"><strong>FRAMES</strong></a>    <a href="UserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
