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
<td align="left"><a href="../../../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MemoryUser.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemorySubscription.html.md" title="class in org.apache.struts.apps.mailreader.dao.impl.memory"><strong>PREV CLASS</strong></a>   <a href="../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUserDatabase.html" title="class in org.apache.struts.apps.mailreader.dao.impl.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUser.html"><strong>FRAMES</strong></a>    <a href="MemoryUser.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader.dao.impl.memory
 Class MemoryUser
-------------------------------------------------

    java.lang.Object
      org.apache.struts.apps.mailreader.dao.impl.AbstractUser
          org.apache.struts.apps.mailreader.dao.impl.memory.MemoryUser

**All Implemented Interfaces:**  
[User](../../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")

------------------------------------------------------------------------

    public class MemoryUser

extends [AbstractUser](../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl")

Concrete implementation of [`AbstractUser`](../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl") used for an in-memory database backed by an XML data file.

**Version:**  
$Rev$

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                               |
|-------------------------------------------------------|
| ` MemoryUser(UserDatabase database, String username)` 
                                                        |

  <span id="method_summary"></span>

**Method Summary**

` String`

` toString()`
           Return a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.apps.mailreader.dao.impl.AbstractUser"></span>

| **Methods inherited from class org.apache.struts.apps.mailreader.dao.impl.[AbstractUser](../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl")**         |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createSubscription,  findSubscription,  getDatabase,  getFromAddress,  getFullName,  getPassword,  getReplyToAddress,  getSubscriptions,  getUsername,  removeSubscription,  setFromAddress,  setFullName,  setPassword,  setReplyToAddress` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MemoryUser

    public MemoryUser(UserDatabase database,
                      String username)

<span id="method_detail"></span>

**Method Detail**

### toString

    public String toString()

Return a String representation of this object.

**Overrides:**  
`toString` in class `Object`

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
<td align="left"><a href="../../../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MemoryUser.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemorySubscription.html.md" title="class in org.apache.struts.apps.mailreader.dao.impl.memory"><strong>PREV CLASS</strong></a>   <a href="../../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUserDatabase.html" title="class in org.apache.struts.apps.mailreader.dao.impl.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUser.html"><strong>FRAMES</strong></a>    <a href="MemoryUser.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
