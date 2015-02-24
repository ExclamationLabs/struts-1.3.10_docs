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
<td align="left"><a href="class-use/IndexBacking.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/ExpiredPasswordException.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/LinkSubscriptionTag.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/IndexBacking.html"><strong>FRAMES</strong></a>    <a href="IndexBacking.html"><strong>NO FRAMES</strong></a>    
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
 Class IndexBacking
--------------------------------

    java.lang.Object
      org.apache.struts.webapp.example.IndexBacking

------------------------------------------------------------------------

    public class IndexBacking

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Backing bean for the `index.jsp` page.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` IndexBacking()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  StringBuffer`

` action(javax.faces.context.FacesContext context, String action)`
           Return the context relative path for the specified action.

` String`

` create()`
           Forward to the *Create Registration* action.

`protected  void`

` forward(javax.faces.context.FacesContext context, String url)`
           Forward to the specified URL and mark this response as having been completed.

`protected  StringBuffer`

` logoff(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "logoff" action.

` String`

` logon()`
           Forward to the *Logon* page.

`protected  StringBuffer`

` logon(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "logon" action.

`protected  StringBuffer`

` registration(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "edit registration" action.

`protected  StringBuffer`

` subscription(javax.faces.context.FacesContext context)`
           Return the context relative base URL for the "edit subscriptions" action.

` void`

` testListener(javax.faces.event.ActionEvent actionEvent)`
           Testing actionListener call

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### IndexBacking

    public IndexBacking()

<span id="method_detail"></span>

**Method Detail**

### create

    public String create()

Forward to the *Create Registration* action.

------------------------------------------------------------------------

### testListener

    public void testListener(javax.faces.event.ActionEvent actionEvent)

Testing actionListener call

**Parameters:**  
`actionEvent` -

------------------------------------------------------------------------

### logon

    public String logon()

Forward to the *Logon* page.

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
<td align="left"><a href="class-use/IndexBacking.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/ExpiredPasswordException.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/LinkSubscriptionTag.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/IndexBacking.html"><strong>FRAMES</strong></a>    <a href="IndexBacking.html"><strong>NO FRAMES</strong></a>    
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
