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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts.webapp.example2**

<span id="org.apache.struts.webapp.example2.ApplicationMapping"></span>

**Class [org.apache.struts.webapp.example2.ApplicationMapping](org/apache/struts/webapp/example2/ApplicationMapping.html.md "class in org.apache.struts.webapp.example2") extends [ActionMapping](http://struts.apache.org/apidocs/org/apache/struts/action/ActionMapping.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### failure

    String failure

The failure URI for this mapping.

------------------------------------------------------------------------

### success

    String success

The success URI for this mapping.

<span id="org.apache.struts.webapp.example2.CheckLogonTag"></span>

**Class [org.apache.struts.webapp.example2.CheckLogonTag](org/apache/struts/webapp/example2/CheckLogonTag.html.md "class in org.apache.struts.webapp.example2") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The key of the session-scope bean we look for.

------------------------------------------------------------------------

### page

    String page

The page to which we should forward for the user to log on.

<span id="org.apache.struts.webapp.example2.ExpiredPasswordException"></span>

**Class [org.apache.struts.webapp.example2.ExpiredPasswordException](org/apache/struts/webapp/example2/ExpiredPasswordException.html.md "class in org.apache.struts.webapp.example2") extends [ModuleException](http://struts.apache.org/apidocs/org/apache/struts/util/ModuleException.html?is-external=true "class or interface in org.apache.struts.util") implements Serializable**

<span id="org.apache.struts.webapp.example2.LinkUserTag"></span>

**Class [org.apache.struts.webapp.example2.LinkUserTag](org/apache/struts/webapp/example2/LinkUserTag.html.md "class in org.apache.struts.webapp.example2") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### page

    String page

The hyperlink URI.

------------------------------------------------------------------------

### name

    String name

The attribute name.

<span id="org.apache.struts.webapp.example2.LogonForm"></span>

**Class [org.apache.struts.webapp.example2.LogonForm](org/apache/struts/webapp/example2/LogonForm.html.md "class in org.apache.struts.webapp.example2") extends [ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### password

    String password

The password.

------------------------------------------------------------------------

### username

    String username

The username.

<span id="org.apache.struts.webapp.example2.RegistrationForm"></span>

**Class [org.apache.struts.webapp.example2.RegistrationForm](org/apache/struts/webapp/example2/RegistrationForm.html.md "class in org.apache.struts.webapp.example2") extends [ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html?is-external=true "class or interface in org.apache.struts.validator") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### action

    String action

The maintenance action we are performing (Create or Edit).

------------------------------------------------------------------------

### fromAddress

    String fromAddress

The from address.

------------------------------------------------------------------------

### fullName

    String fullName

The full name.

------------------------------------------------------------------------

### password

    String password

The password.

------------------------------------------------------------------------

### password2

    String password2

The confirmation password.

------------------------------------------------------------------------

### replyToAddress

    String replyToAddress

The reply to address.

------------------------------------------------------------------------

### username

    String username

The username.

<span id="org.apache.struts.webapp.example2.SubscriptionForm"></span>

**Class [org.apache.struts.webapp.example2.SubscriptionForm](org/apache/struts/webapp/example2/SubscriptionForm.html.md "class in org.apache.struts.webapp.example2") extends [ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### action

    String action

The maintenance action we are performing (Create or Edit).

------------------------------------------------------------------------

### autoConnect

    boolean autoConnect

Should we auto-connect at startup time?

------------------------------------------------------------------------

### host

    String host

The host name.

------------------------------------------------------------------------

### password

    String password

The password.

------------------------------------------------------------------------

### type

    String type

The subscription type.

------------------------------------------------------------------------

### username

    String username

The username.

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
