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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/AbstractUser.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractSubscription.html.md" title="class in org.apache.struts.apps.mailreader.dao.impl"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html"><strong>FRAMES</strong></a>    <a href="AbstractUser.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader.dao.impl
 Class AbstractUser
------------------------------------------

    java.lang.Object
      org.apache.struts.apps.mailreader.dao.impl.AbstractUser

**All Implemented Interfaces:**  
[User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")

<!-- -->

**Direct Known Subclasses:**  
[MemoryUser](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/MemoryUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl.memory")

------------------------------------------------------------------------

    public abstract class AbstractUser

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [User](../../../../../../../org/apache/struts/apps/mailreader/dao/User.html.md "interface in org.apache.struts.apps.mailreader.dao")

Concrete implementation of [`AbstractUser`](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html.md "class in org.apache.struts.apps.mailreader.dao.impl").

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` AbstractUser(UserDatabase database, String username)`                                                                                                                                                            
            Construct a new User associated with the specified [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao").  |

  <span id="method_summary"></span>

**Method Summary**

` Subscription`

` createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with this User, for the specified host name.

` Subscription`

` findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with the specified host.

` UserDatabase`

` getDatabase()`
           The [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") with which we are associated.

` String`

` getFromAddress()`
           Return the from address.

` String`

` getFullName()`
           Return the full name.

` String`

` getPassword()`
           Return the password.

` String`

` getReplyToAddress()`
           Return the reply-to address.

` Subscription[]`

` getSubscriptions()`
           Find and return all [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s associated with this user.

` String`

` getUsername()`
           The username (must be unique).

` void`

` removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") from being associated with this User.

` void`

` setFromAddress(String fromAddress)`
           Set the from address.

` void`

` setFullName(String fullName)`
           Set the full name.

` void`

` setPassword(String password)`
           Set the password.

` void`

` setReplyToAddress(String replyToAddress)`
           Set the reply-to address.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### AbstractUser

    public AbstractUser(UserDatabase database,
                        String username)

Construct a new User associated with the specified [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao").

**Parameters:**  
`database` - The user database with which we are associated

`username` - The username of this user

<span id="method_detail"></span>

**Method Detail**

### getDatabase

    public UserDatabase getDatabase()

The [`UserDatabase`](../../../../../../../org/apache/struts/apps/mailreader/dao/UserDatabase.html.md "interface in org.apache.struts.apps.mailreader.dao") with which we are associated.

**Specified by:**  
` getDatabase` in interface `User`

------------------------------------------------------------------------

### getFromAddress

    public String getFromAddress()

**Description copied from interface: ` User`**

Return the from address.

**Specified by:**  
` getFromAddress` in interface `User`

------------------------------------------------------------------------

### setFromAddress

    public void setFromAddress(String fromAddress)

**Description copied from interface: ` User`**

Set the from address.

**Specified by:**  
` setFromAddress` in interface `User`

<!-- -->

**Parameters:**  
`fromAddress` - The new from address

------------------------------------------------------------------------

### getFullName

    public String getFullName()

**Description copied from interface: ` User`**

Return the full name.

**Specified by:**  
` getFullName` in interface `User`

------------------------------------------------------------------------

### setFullName

    public void setFullName(String fullName)

**Description copied from interface: ` User`**

Set the full name.

**Specified by:**  
` setFullName` in interface `User`

<!-- -->

**Parameters:**  
`fullName` - The new full name

------------------------------------------------------------------------

### getPassword

    public String getPassword()

**Description copied from interface: ` User`**

Return the password.

**Specified by:**  
` getPassword` in interface `User`

------------------------------------------------------------------------

### setPassword

    public void setPassword(String password)

**Description copied from interface: ` User`**

Set the password.

**Specified by:**  
` setPassword` in interface `User`

<!-- -->

**Parameters:**  
`password` - The new password

------------------------------------------------------------------------

### getReplyToAddress

    public String getReplyToAddress()

**Description copied from interface: ` User`**

Return the reply-to address.

**Specified by:**  
` getReplyToAddress` in interface `User`

------------------------------------------------------------------------

### setReplyToAddress

    public void setReplyToAddress(String replyToAddress)

**Description copied from interface: ` User`**

Set the reply-to address.

**Specified by:**  
` setReplyToAddress` in interface `User`

<!-- -->

**Parameters:**  
`replyToAddress` - The new reply-to address

------------------------------------------------------------------------

### getSubscriptions

    public Subscription[] getSubscriptions()

Find and return all [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s associated with this user. If there are none, a zero-length array is returned.

**Specified by:**  
` getSubscriptions` in interface `User`

------------------------------------------------------------------------

### getUsername

    public String getUsername()

The username (must be unique).

**Specified by:**  
` getUsername` in interface `User`

------------------------------------------------------------------------

### createSubscription

    public Subscription createSubscription(String host)

Create and return a new [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with this User, for the specified host name.

**Specified by:**  
` createSubscription` in interface `User`

<!-- -->

**Parameters:**  
`host` - Host name for which to create a subscription

**Throws:**  
`IllegalArgumentException` - if the host name is not unique for this user

------------------------------------------------------------------------

### findSubscription

    public Subscription findSubscription(String host)

Find and return the [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with the specified host. If none is found, return `null`.

**Specified by:**  
` findSubscription` in interface `User`

<!-- -->

**Parameters:**  
`host` - Host name to look up

------------------------------------------------------------------------

### removeSubscription

    public void removeSubscription(Subscription subscription)

Remove the specified [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") from being associated with this User.

**Specified by:**  
` removeSubscription` in interface `User`

<!-- -->

**Parameters:**  
`subscription` - Subscription to be removed

**Throws:**  
`IllegalArgumentException` - if the specified subscription is not associated with this User

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/AbstractUser.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractSubscription.html.md" title="class in org.apache.struts.apps.mailreader.dao.impl"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao/impl/AbstractUser.html"><strong>FRAMES</strong></a>    <a href="AbstractUser.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
