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
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useSubscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.apps.mailreader.dao.Subscription**
-----------------------------------------------------

Packages that use [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")

[**org.apache.struts.apps.mailreader.dao**](#org.apache.struts.apps.mailreader.dao)

  

[**org.apache.struts.apps.mailreader.dao.impl**](#org.apache.struts.apps.mailreader.dao.impl)

  

[**org.apache.struts.apps.mailreader.dao.impl.memory**](#org.apache.struts.apps.mailreader.dao.impl.memory)

  

 

<span id="org.apache.struts.apps.mailreader.dao"></span>

Uses of [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html)

 

Methods in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) that return [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` Subscription`

`User.createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with this User, for the specified host name.

` Subscription`

`User.findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with the specified host.

` Subscription[]`

`User.getSubscriptions()`
           Find and return all [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s associated with this user.

 

Methods in [org.apache.struts.apps.mailreader.dao](../../../../../../../org/apache/struts/apps/mailreader/dao/package-summary.html.md) with parameters of type [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` void`

`User.removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") from being associated with this User.

 

<span id="org.apache.struts.apps.mailreader.dao.impl"></span>

Uses of [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html)

 

Classes in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) that implement [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` class`

`AbstractSubscription`
           Concrete implementation of [`AbstractSubscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/AbstractSubscription.html.md "class in org.apache.struts.apps.mailreader.dao.impl").

 

Methods in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) that return [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` Subscription`

`AbstractUser.createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with this User, for the specified host name.

` Subscription`

`AbstractUser.findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") associated with the specified host.

` Subscription[]`

`AbstractUser.getSubscriptions()`
           Find and return all [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao")s associated with this user.

 

Methods in [org.apache.struts.apps.mailreader.dao.impl](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/package-summary.html.md) with parameters of type [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` void`

`AbstractUser.removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") from being associated with this User.

 

<span id="org.apache.struts.apps.mailreader.dao.impl.memory"></span>

Uses of [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md "interface in org.apache.struts.apps.mailreader.dao") in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html)

 

Classes in [org.apache.struts.apps.mailreader.dao.impl.memory](../../../../../../../org/apache/struts/apps/mailreader/dao/impl/memory/package-summary.html.md) that implement [Subscription](../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html "interface in org.apache.struts.apps.mailreader.dao")

` class`

`MemorySubscription`
            

 

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
<td align="left"><a href="../../../../../../../org/apache/struts/apps/mailreader/dao/Subscription.html.md" title="interface in org.apache.struts.apps.mailreader.dao"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../../index.html.md?org/apache/struts/apps/mailreader/dao//class-useSubscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
