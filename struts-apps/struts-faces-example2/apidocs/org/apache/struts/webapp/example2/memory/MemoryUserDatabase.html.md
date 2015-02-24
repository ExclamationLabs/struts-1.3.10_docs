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
<td align="left"><a href="class-use/MemoryUserDatabase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/example2/memory/MemoryUser.html.md" title="class in org.apache.struts.webapp.example2.memory"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example2/memory/MemoryUserDatabase.html"><strong>FRAMES</strong></a>    <a href="MemoryUserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example2.memory
 Class MemoryUserDatabase
----------------------------------------

    java.lang.Object
      org.apache.struts.webapp.example2.memory.MemoryUserDatabase

**All Implemented Interfaces:**  
[UserDatabase](../../../../../../org/apache/struts/webapp/example2/UserDatabase.html.md "interface in org.apache.struts.webapp.example2")

------------------------------------------------------------------------

    public final class MemoryUserDatabase

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [UserDatabase](../../../../../../org/apache/struts/webapp/example2/UserDatabase.html.md "interface in org.apache.struts.webapp.example2")

Concrete implementation of [`UserDatabase`](../../../../../../org/apache/struts/webapp/example2/UserDatabase.html.md "interface in org.apache.struts.webapp.example2") for an in-memory database backed by an XML data file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` MemoryUserDatabase()` 
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` close()`
           Finalize access to the underlying persistence layer.

` User`

` createUser(String username)`
           Create and return a new [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") defined in this user database.

` User`

` findUser(String username)`
           Return the existing [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") with the specified username, if any; otherwise return `null`.

` User[]`

` findUsers()`
           Return the set of [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2")s defined in this user database.

` String`

` getPathname()`
            

` void`

` open()`
           Initiate access to the underlying persistence layer.

` void`

` removeUser(User user)`
           Remove the specified [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") from this database.

` void`

` save()`
           Save any pending changes to the underlying persistence layer.

` void`

` setPathname(String pathname)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MemoryUserDatabase

    public MemoryUserDatabase()

<span id="method_detail"></span>

**Method Detail**

### getPathname

    public String getPathname()

------------------------------------------------------------------------

### setPathname

    public void setPathname(String pathname)

------------------------------------------------------------------------

### close

    public void close()
               throws Exception

Finalize access to the underlying persistence layer.

**Specified by:**  
` close` in interface `UserDatabase`

<!-- -->

**Throws:**  
`Exception` - if a database access error occurs

------------------------------------------------------------------------

### createUser

    public User createUser(String username)

Create and return a new [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") defined in this user database.

**Specified by:**  
` createUser` in interface `UserDatabase`

<!-- -->

**Parameters:**  
`username` - Username of the new user

**Throws:**  
`IllegalArgumentExceptionif` - the specified username is not unique

------------------------------------------------------------------------

### findUser

    public User findUser(String username)

Return the existing [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") with the specified username, if any; otherwise return `null`.

**Specified by:**  
` findUser` in interface `UserDatabase`

<!-- -->

**Parameters:**  
`username` - Username of the user to retrieve

------------------------------------------------------------------------

### findUsers

    public User[] findUsers()

Return the set of [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2")s defined in this user database.

**Specified by:**  
` findUsers` in interface `UserDatabase`

------------------------------------------------------------------------

### open

    public void open()
              throws Exception

Initiate access to the underlying persistence layer.

**Specified by:**  
` open` in interface `UserDatabase`

<!-- -->

**Throws:**  
`Exception` - if a database access error occurs

------------------------------------------------------------------------

### removeUser

    public void removeUser(User user)

Remove the specified [`User`](../../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") from this database.

**Specified by:**  
` removeUser` in interface `UserDatabase`

<!-- -->

**Parameters:**  
`user` - User to be removed

**Throws:**  
`IllegalArgumentException` - if the specified user is not associated with this database

------------------------------------------------------------------------

### save

    public void save()
              throws Exception

Save any pending changes to the underlying persistence layer.

**Specified by:**  
` save` in interface `UserDatabase`

<!-- -->

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
<td align="left"><a href="class-use/MemoryUserDatabase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/example2/memory/MemoryUser.html.md" title="class in org.apache.struts.webapp.example2.memory"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example2/memory/MemoryUserDatabase.html"><strong>FRAMES</strong></a>    <a href="MemoryUserDatabase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
