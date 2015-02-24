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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example/User.html.md" title="interface in org.apache.struts.webapp.example"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example//class-useUser.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.webapp.example.User**
----------------------------------------

Packages that use [User](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example")

[**org.apache.struts.webapp.example**](#org.apache.struts.webapp.example)

  

[**org.apache.struts.webapp.example.memory**](#org.apache.struts.webapp.example.memory)

  

 

<span id="org.apache.struts.webapp.example"></span>

Uses of [User](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html)

 

Methods in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html.md) that return [User](../../../../../../org/apache/struts/webapp/example/User.html "interface in org.apache.struts.webapp.example")

` User`

`UserDatabase.createUser(String username)`
           Create and return a new [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") defined in this user database.

` User`

`UserDatabase.findUser(String username)`
           Return the existing [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") with the specified username, if any; otherwise return `null`.

` User[]`

`UserDatabase.findUsers()`
           Return the set of [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example")s defined in this user database.

` User`

`Subscription.getUser()`
           Return the [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") owning this Subscription.

` User`

`LogonAction.getUser(UserDatabase database, String username)`
           Look up the user, throwing an exception to simulate business logic rule exceptions.

 

Methods in [org.apache.struts.webapp.example](../../../../../../org/apache/struts/webapp/example/package-summary.html.md) with parameters of type [User](../../../../../../org/apache/struts/webapp/example/User.html "interface in org.apache.struts.webapp.example")

` void`

`UserDatabase.removeUser(User user)`
           Remove the specified [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") from this database.

 

<span id="org.apache.struts.webapp.example.memory"></span>

Uses of [User](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html)

 

Classes in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html.md) that implement [User](../../../../../../org/apache/struts/webapp/example/User.html "interface in org.apache.struts.webapp.example")

` class`

`MemoryUser`
           Concrete implementation of [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") for an in-memory database backed by an XML data file.

 

Methods in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html.md) that return [User](../../../../../../org/apache/struts/webapp/example/User.html "interface in org.apache.struts.webapp.example")

` User`

`MemoryUserDatabase.createUser(String username)`
           Create and return a new [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") defined in this user database.

` User`

`MemoryUserDatabase.findUser(String username)`
           Return the existing [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") with the specified username, if any; otherwise return `null`.

` User[]`

`MemoryUserDatabase.findUsers()`
           Return the set of [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example")s defined in this user database.

` User`

`MemorySubscription.getUser()`
           The User owning this Subscription.

 

Methods in [org.apache.struts.webapp.example.memory](../../../../../../org/apache/struts/webapp/example/memory/package-summary.html.md) with parameters of type [User](../../../../../../org/apache/struts/webapp/example/User.html "interface in org.apache.struts.webapp.example")

` void`

`MemoryUserDatabase.removeUser(User user)`
           Remove the specified [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example") from this database.

 

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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example/User.html.md" title="interface in org.apache.struts.webapp.example"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example//class-useUser.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
