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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/User.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/SubscriptionForm.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/UserDatabase.html" title="interface in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/User.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example
 Interface User
--------------------------------

**All Known Implementing Classes:**  
[MemoryUser](../../../../../org/apache/struts/webapp/example/memory/MemoryUser.html.md "class in org.apache.struts.webapp.example.memory")

------------------------------------------------------------------------

    public interface User

A **User** which is stored, along with his or her associated [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example")s, in a [`UserDatabase`](../../../../../org/apache/struts/webapp/example/UserDatabase.html "interface in org.apache.struts.webapp.example").

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` Subscription`

` createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") associated with this User, for the specified host name.

` Subscription`

` findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") associated with the specified host.

` UserDatabase`

` getDatabase()`
           Return the [`UserDatabase`](../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") with which we are associated.

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
           Find and return all [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example")s associated with this user.

` String`

` getUsername()`
           Return the username.

` void`

` removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") from being associated with this User.

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

 

<span id="method_detail"></span>

**Method Detail**

### getDatabase

    UserDatabase getDatabase()

Return the [`UserDatabase`](../../../../../org/apache/struts/webapp/example/UserDatabase.html.md "interface in org.apache.struts.webapp.example") with which we are associated.

------------------------------------------------------------------------

### getFromAddress

    String getFromAddress()

Return the from address.

------------------------------------------------------------------------

### setFromAddress

    void setFromAddress(String fromAddress)

Set the from address.

**Parameters:**  
`fromAddress` - The new from address

------------------------------------------------------------------------

### getFullName

    String getFullName()

Return the full name.

------------------------------------------------------------------------

### setFullName

    void setFullName(String fullName)

Set the full name.

**Parameters:**  
`fullName` - The new full name

------------------------------------------------------------------------

### getPassword

    String getPassword()

Return the password.

------------------------------------------------------------------------

### setPassword

    void setPassword(String password)

Set the password.

**Parameters:**  
`password` - The new password

------------------------------------------------------------------------

### getReplyToAddress

    String getReplyToAddress()

Return the reply-to address.

------------------------------------------------------------------------

### setReplyToAddress

    void setReplyToAddress(String replyToAddress)

Set the reply-to address.

**Parameters:**  
`replyToAddress` - The new reply-to address

------------------------------------------------------------------------

### getSubscriptions

    Subscription[] getSubscriptions()

Find and return all [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example")s associated with this user. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### getUsername

    String getUsername()

Return the username.

------------------------------------------------------------------------

### createSubscription

    Subscription createSubscription(String host)

Create and return a new [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") associated with this User, for the specified host name.

**Parameters:**  
`host` - Host name for which to create a subscription

**Throws:**  
`IllegalArgumentException` - if the host name is not unique for this user

------------------------------------------------------------------------

### findSubscription

    Subscription findSubscription(String host)

Find and return the [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") associated with the specified host. If none is found, return `null`.

**Parameters:**  
`host` - Host name to look up

------------------------------------------------------------------------

### removeSubscription

    void removeSubscription(Subscription subscription)

Remove the specified [`Subscription`](../../../../../org/apache/struts/webapp/example/Subscription.html.md "interface in org.apache.struts.webapp.example") from being associated with this User.

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/User.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/SubscriptionForm.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/UserDatabase.html" title="interface in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/User.html"><strong>FRAMES</strong></a>    <a href="User.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
