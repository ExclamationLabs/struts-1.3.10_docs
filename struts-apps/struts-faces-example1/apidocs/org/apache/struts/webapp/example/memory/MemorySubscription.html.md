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
<td align="left"><a href="class-use/MemorySubscription.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/example/memory/MemoryDatabasePlugIn.html.md" title="class in org.apache.struts.webapp.example.memory"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/webapp/example/memory/MemoryUser.html" title="class in org.apache.struts.webapp.example.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example/memory/MemorySubscription.html"><strong>FRAMES</strong></a>    <a href="MemorySubscription.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.webapp.example.memory
 Class MemorySubscription
---------------------------------------

    java.lang.Object
      org.apache.struts.webapp.example.memory.MemorySubscription

**All Implemented Interfaces:**  
[Subscription](../../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example")

------------------------------------------------------------------------

    public final class MemorySubscription

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Subscription](../../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example")

Concrete implementation of [`Subscription`](../../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") for an in-memory database backed by an XML data file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` MemorySubscription(MemoryUser user, String host)`                                                                                                                                           
            Construct a new Subscription associated with the specified [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example").  |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` getAutoConnect()`
           Return the auto-connect flag.

` String`

` getHost()`
           The mail host for this subscription.

` String`

` getPassword()`
           Return the password.

` String`

` getType()`
           Return the subscription type.

` User`

` getUser()`
           The User owning this Subscription.

` String`

` getUsername()`
           Return the username.

` void`

` setAutoConnect(boolean autoConnect)`
           Set the auto-connect flag.

` void`

` setPassword(String password)`
           Set the password.

` void`

` setType(String type)`
           Set the subscription type.

` void`

` setUsername(String username)`
           Set the username.

` String`

` toString()`
           Return a String representation of this object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MemorySubscription

    public MemorySubscription(MemoryUser user,
                              String host)

Construct a new Subscription associated with the specified [`User`](../../../../../../org/apache/struts/webapp/example/User.html.md "interface in org.apache.struts.webapp.example").

**Parameters:**  
`user` - The user with which we are associated

`host` - The mail host for this subscription

<span id="method_detail"></span>

**Method Detail**

### getAutoConnect

    public boolean getAutoConnect()

**Description copied from interface: ` Subscription`**

Return the auto-connect flag.

**Specified by:**  
` getAutoConnect` in interface `Subscription`

------------------------------------------------------------------------

### setAutoConnect

    public void setAutoConnect(boolean autoConnect)

**Description copied from interface: ` Subscription`**

Set the auto-connect flag.

**Specified by:**  
` setAutoConnect` in interface `Subscription`

<!-- -->

**Parameters:**  
`autoConnect` - The new auto-connect flag

------------------------------------------------------------------------

### getHost

    public String getHost()

The mail host for this subscription.

**Specified by:**  
` getHost` in interface `Subscription`

------------------------------------------------------------------------

### getPassword

    public String getPassword()

**Description copied from interface: ` Subscription`**

Return the password.

**Specified by:**  
` getPassword` in interface `Subscription`

------------------------------------------------------------------------

### setPassword

    public void setPassword(String password)

**Description copied from interface: ` Subscription`**

Set the password.

**Specified by:**  
` setPassword` in interface `Subscription`

<!-- -->

**Parameters:**  
`password` - The new password

------------------------------------------------------------------------

### getType

    public String getType()

**Description copied from interface: ` Subscription`**

Return the subscription type.

**Specified by:**  
` getType` in interface `Subscription`

------------------------------------------------------------------------

### setType

    public void setType(String type)

**Description copied from interface: ` Subscription`**

Set the subscription type.

**Specified by:**  
` setType` in interface `Subscription`

<!-- -->

**Parameters:**  
`type` - The new subscription type

------------------------------------------------------------------------

### getUser

    public User getUser()

The User owning this Subscription.

**Specified by:**  
` getUser` in interface `Subscription`

------------------------------------------------------------------------

### getUsername

    public String getUsername()

**Description copied from interface: ` Subscription`**

Return the username.

**Specified by:**  
` getUsername` in interface `Subscription`

------------------------------------------------------------------------

### setUsername

    public void setUsername(String username)

**Description copied from interface: ` Subscription`**

Set the username.

**Specified by:**  
` setUsername` in interface `Subscription`

<!-- -->

**Parameters:**  
`username` - The new username

------------------------------------------------------------------------

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MemorySubscription.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/example/memory/MemoryDatabasePlugIn.html.md" title="class in org.apache.struts.webapp.example.memory"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/webapp/example/memory/MemoryUser.html" title="class in org.apache.struts.webapp.example.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example/memory/MemorySubscription.html"><strong>FRAMES</strong></a>    <a href="MemorySubscription.html"><strong>NO FRAMES</strong></a>    
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
