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
<td align="left"><a href="class-use/RegistrationBacking.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/MainMenuBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/RegistrationForm.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/RegistrationBacking.html"><strong>FRAMES</strong></a>    <a href="RegistrationBacking.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example
 Class RegistrationBacking
--------------------------------

    java.lang.Object
      org.apache.struts.webapp.example.RegistrationBacking

------------------------------------------------------------------------

    public class RegistrationBacking

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Backing bean for the `registration.jsp` page.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` RegistrationBacking()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

`protected  StringBuffer`

` action(javax.faces.context.FacesContext context, String action)`
           Return the context relative path for the specified action.

` String`

` create()`
           Create a new subscription.

` String`

` delete()`
           Delete an existing subscription.

` String`

` edit()`
           Edit an existing subscription.

`protected  void`

` forward(javax.faces.context.FacesContext context, String url)`
           Forward to the specified URL and mark this response as having been completed.

` javax.faces.component.UIData`

` getTable()`
           Return the `UIData` instance we are bound to.

`protected  StringBuffer`

` logoff(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "logoff" action.

`protected  StringBuffer`

` logon(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "logon" action.

`protected  StringBuffer`

` registration(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "edit registration" action.

` void`

` setTable(javax.faces.component.UIData table)`
           Set the `UIData` instance we are bound to.

`protected  StringBuffer`

` subscription(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "edit subscriptions" action.

` String`

` update()`
           Update the subscriptions to reflect any revisions to the `type` and `autoConnect` properties.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### RegistrationBacking

    public RegistrationBacking()

<span id="method_detail"></span>

**Method Detail**

### getTable

    public javax.faces.component.UIData getTable()

Return the `UIData` instance we are bound to.

------------------------------------------------------------------------

### setTable

    public void setTable(javax.faces.component.UIData table)

Set the `UIData` instance we are bound to.

**Parameters:**  
`table` - The `UIData` instance

------------------------------------------------------------------------

### create

    public String create()

Create a new subscription.

------------------------------------------------------------------------

### delete

    public String delete()

Delete an existing subscription.

------------------------------------------------------------------------

### edit

    public String edit()

Edit an existing subscription.

------------------------------------------------------------------------

### update

    public String update()

Update the subscriptions to reflect any revisions to the `type` and `autoConnect` properties.

------------------------------------------------------------------------

### action

    protected StringBuffer action(javax.faces.context.FacesContext context,
                                  String action)

Return the context relative path for the specified action.

**Parameters:**  
`context` - `FacesContext` for the current request

`action` - Name of the requested action

------------------------------------------------------------------------

### forward

    protected void forward(javax.faces.context.FacesContext context,
                           String url)

Forward to the specified URL and mark this response as having been completed.

**Parameters:**  
`context` - `FacesContext` for the current request

`url` - Context-relative URL to forward to

**Throws:**  
`javax.faces.FacesException` - if any error occurs

------------------------------------------------------------------------

### logoff

    protected StringBuffer logoff(javax.faces.context.FacesContext context)

Return the context relative base URL for the "logoff" action.

**Parameters:**  
`context` - `FacesContext` for the current request

------------------------------------------------------------------------

### logon

    protected StringBuffer logon(javax.faces.context.FacesContext context)

Return the context relative base URL for the "logon" action.

**Parameters:**  
`context` - `FacesContext` for the current request

------------------------------------------------------------------------

### registration

    protected StringBuffer registration(javax.faces.context.FacesContext context)

Return the context relative base URL for the "edit registration" action.

**Parameters:**  
`context` - `FacesContext` for the current request

------------------------------------------------------------------------

### subscription

    protected StringBuffer subscription(javax.faces.context.FacesContext context)

Return the context relative base URL for the "edit subscriptions" action.

**Parameters:**  
`context` - `FacesContext` for the current request

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
<td align="left"><a href="class-use/RegistrationBacking.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/MainMenuBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/RegistrationForm.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/RegistrationBacking.html"><strong>FRAMES</strong></a>    <a href="RegistrationBacking.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
