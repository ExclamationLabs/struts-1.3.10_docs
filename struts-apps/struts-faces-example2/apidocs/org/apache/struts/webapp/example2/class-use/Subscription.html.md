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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example2/Subscription.html.md" title="interface in org.apache.struts.webapp.example2"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example2//class-useSubscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.webapp.example2.Subscription**
-------------------------------------------------

Packages that use [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2")

[**org.apache.struts.webapp.example2**](#org.apache.struts.webapp.example2)

  

[**org.apache.struts.webapp.example2.memory**](#org.apache.struts.webapp.example2.memory)

  

 

<span id="org.apache.struts.webapp.example2"></span>

Uses of [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") in [org.apache.struts.webapp.example2](../../../../../../org/apache/struts/webapp/example2/package-summary.html)

 

Methods in [org.apache.struts.webapp.example2](../../../../../../org/apache/struts/webapp/example2/package-summary.html.md) that return [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")

` Subscription`

`User.createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") associated with this User, for the specified host name.

` Subscription`

`User.findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") associated with the specified host.

` Subscription[]`

`User.getSubscriptions()`
           Find and return all [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2")s associated with this user.

 

Methods in [org.apache.struts.webapp.example2](../../../../../../org/apache/struts/webapp/example2/package-summary.html.md) with parameters of type [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")

` void`

`User.removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") from being associated with this User.

 

<span id="org.apache.struts.webapp.example2.memory"></span>

Uses of [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") in [org.apache.struts.webapp.example2.memory](../../../../../../org/apache/struts/webapp/example2/memory/package-summary.html)

 

Classes in [org.apache.struts.webapp.example2.memory](../../../../../../org/apache/struts/webapp/example2/memory/package-summary.html.md) that implement [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")

` class`

`MemorySubscription`
           Concrete implementation of [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") for an in-memory database backed by an XML data file.

 

Methods in [org.apache.struts.webapp.example2.memory](../../../../../../org/apache/struts/webapp/example2/memory/package-summary.html.md) that return [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")

` Subscription`

`MemoryUser.createSubscription(String host)`
           Create and return a new [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") associated with this User, for the specified host name.

` Subscription`

`MemoryUser.findSubscription(String host)`
           Find and return the [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") associated with the specified host.

` Subscription[]`

`MemoryUser.getSubscriptions()`
           Find and return all [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2")s associated with this user.

 

Methods in [org.apache.struts.webapp.example2.memory](../../../../../../org/apache/struts/webapp/example2/memory/package-summary.html.md) with parameters of type [Subscription](../../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")

` void`

`MemoryUser.removeSubscription(Subscription subscription)`
           Remove the specified [`Subscription`](../../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2") from being associated with this User.

 

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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/example2/Subscription.html.md" title="interface in org.apache.struts.webapp.example2"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example2//class-useSubscription.html"><strong>FRAMES</strong></a>    <a href="Subscription.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
