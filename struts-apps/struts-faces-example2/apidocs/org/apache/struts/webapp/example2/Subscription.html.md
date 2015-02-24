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
<td align="left"><a href="class-use/Subscription.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example2/SaveSubscriptionAction.html.md" title="class in org.apache.struts.webapp.example2"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example2/SubscriptionForm.html" title="class in org.apache.struts.webapp.example2"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example2/Subscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.webapp.example2
 Interface Subscription
---------------------------------

**All Known Implementing Classes:**  
[MemorySubscription](../../../../../org/apache/struts/webapp/example2/memory/MemorySubscription.html.md "class in org.apache.struts.webapp.example2.memory")

------------------------------------------------------------------------

    public interface Subscription

A **Subscription** which is stored, along with the associated [`User`](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2"), in a [`UserDatabase`](../../../../../org/apache/struts/webapp/example2/UserDatabase.html "interface in org.apache.struts.webapp.example2").

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` boolean`

` getAutoConnect()`
           Return the auto-connect flag.

` String`

` getHost()`
           Return the host name.

` String`

` getPassword()`
           Return the password.

` String`

` getType()`
           Return the subscription type.

` User`

` getUser()`
           Return the [`User`](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") owning this Subscription.

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

 

<span id="method_detail"></span>

**Method Detail**

### getAutoConnect

    boolean getAutoConnect()

Return the auto-connect flag.

------------------------------------------------------------------------

### setAutoConnect

    void setAutoConnect(boolean autoConnect)

Set the auto-connect flag.

**Parameters:**  
`autoConnect` - The new auto-connect flag

------------------------------------------------------------------------

### getHost

    String getHost()

Return the host name.

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

### getType

    String getType()

Return the subscription type.

------------------------------------------------------------------------

### setType

    void setType(String type)

Set the subscription type.

**Parameters:**  
`type` - The new subscription type

------------------------------------------------------------------------

### getUser

    User getUser()

Return the [`User`](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2") owning this Subscription.

------------------------------------------------------------------------

### getUsername

    String getUsername()

Return the username.

------------------------------------------------------------------------

### setUsername

    void setUsername(String username)

Set the username.

**Parameters:**  
`username` - The new username

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
<td align="left"><a href="class-use/Subscription.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example2/SaveSubscriptionAction.html.md" title="class in org.apache.struts.webapp.example2"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example2/SubscriptionForm.html" title="class in org.apache.struts.webapp.example2"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example2/Subscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
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
