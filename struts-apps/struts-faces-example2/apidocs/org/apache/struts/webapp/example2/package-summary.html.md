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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV PACKAGE   <a href="../../../../../org/apache/struts/webapp/example2/memory/package-summary.html.md"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example2/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.struts.webapp.example2
-----------------------------------------

**Interface Summary**

**[Subscription](../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2")**

A **Subscription** which is stored, along with the associated [`User`](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2"), in a [`UserDatabase`](../../../../../org/apache/struts/webapp/example2/UserDatabase.html "interface in org.apache.struts.webapp.example2").

**[User](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2")**

A **User** which is stored, along with his or her associated [`Subscription`](../../../../../org/apache/struts/webapp/example2/Subscription.html.md "interface in org.apache.struts.webapp.example2")s, in a [`UserDatabase`](../../../../../org/apache/struts/webapp/example2/UserDatabase.html "interface in org.apache.struts.webapp.example2").

**[UserDatabase](../../../../../org/apache/struts/webapp/example2/UserDatabase.html.md "interface in org.apache.struts.webapp.example2")**

A **Data Access Object** (DAO) interface describing the available operations for retrieving and storing [`User`](../../../../../org/apache/struts/webapp/example2/User.html.md "interface in org.apache.struts.webapp.example2")s (and their associated [`Subscription`](../../../../../org/apache/struts/webapp/example2/Subscription.html "interface in org.apache.struts.webapp.example2")s) in some persistence layer whose characteristics are not specified here.

 

**Class Summary**

**[ApplicationMapping](../../../../../org/apache/struts/webapp/example2/ApplicationMapping.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **ActionMapping** for the Struts example application.

**[CheckLogonTag](../../../../../org/apache/struts/webapp/example2/CheckLogonTag.html.md "class in org.apache.struts.webapp.example2")**

Check for a valid User logged on in the current session.

**[Constants](../../../../../org/apache/struts/webapp/example2/Constants.html.md "class in org.apache.struts.webapp.example2")**

Manifest constants for the example application.

**[EditRegistrationAction](../../../../../org/apache/struts/webapp/example2/EditRegistrationAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that populates an instance of `RegistrationForm` from the profile of the currently logged on User (if any).

**[EditSubscriptionAction](../../../../../org/apache/struts/webapp/example2/EditSubscriptionAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that populates an instance of `SubscriptionForm` from the currently specified subscription.

**[LinkSubscriptionTag](../../../../../org/apache/struts/webapp/example2/LinkSubscriptionTag.html.md "class in org.apache.struts.webapp.example2")**

Generate a URL-encoded hyperlink to the specified URI, with associated query parameters selecting a specified Subscription.

**[LinkUserTag](../../../../../org/apache/struts/webapp/example2/LinkUserTag.html.md "class in org.apache.struts.webapp.example2")**

Generate a URL-encoded hyperlink to the specified URI, with associated query parameters selecting a specified User.

**[LoggedOff](../../../../../org/apache/struts/webapp/example2/LoggedOff.html.md "class in org.apache.struts.webapp.example2")**

Backing bean for the `loggedoff.jsp` page.

**[LoggedOn](../../../../../org/apache/struts/webapp/example2/LoggedOn.html.md "class in org.apache.struts.webapp.example2")**

Backing bean for the `loggedon.jsp` page.

**[LogoffAction](../../../../../org/apache/struts/webapp/example2/LogoffAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that processes a user logoff.

**[LogonAction](../../../../../org/apache/struts/webapp/example2/LogonAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that validates a user logon.

**[LogonForm](../../../../../org/apache/struts/webapp/example2/LogonForm.html.md "class in org.apache.struts.webapp.example2")**

Form bean for the user profile page.

**[RegistrationBacking](../../../../../org/apache/struts/webapp/example2/RegistrationBacking.html.md "class in org.apache.struts.webapp.example2")**

Backing bean for the `registration.jsp` page.

**[RegistrationForm](../../../../../org/apache/struts/webapp/example2/RegistrationForm.html.md "class in org.apache.struts.webapp.example2")**

Form bean for the user registration page.

**[SaveRegistrationAction](../../../../../org/apache/struts/webapp/example2/SaveRegistrationAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that validates and creates or updates the user registration information entered by the user.

**[SaveSubscriptionAction](../../../../../org/apache/struts/webapp/example2/SaveSubscriptionAction.html.md "class in org.apache.struts.webapp.example2")**

Implementation of **Action** that validates and creates or updates the mail subscription entered by the user.

**[SubscriptionForm](../../../../../org/apache/struts/webapp/example2/SubscriptionForm.html.md "class in org.apache.struts.webapp.example2")**

Form bean for the user profile page.

 

**Exception Summary**

**[ExpiredPasswordException](../../../../../org/apache/struts/webapp/example2/ExpiredPasswordException.html.md "class in org.apache.struts.webapp.example2")**

Example of an application-specific exception for which a handler can be configured.

 

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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV PACKAGE   <a href="../../../../../org/apache/struts/webapp/example2/memory/package-summary.html.md"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example2/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
