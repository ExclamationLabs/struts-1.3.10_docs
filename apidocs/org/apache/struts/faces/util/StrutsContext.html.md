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
<td align="left"><a href="class-use/StrutsContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/util/MessagesMap.html.md" title="class in org.apache.struts.faces.util"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/StrutsContext.html"><strong>FRAMES</strong></a>    <a href="StrutsContext.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.util
 Class StrutsContext
----------------------------

    java.lang.Object
      org.apache.struts.faces.util.StrutsContext

------------------------------------------------------------------------

    public class StrutsContext

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Context bean providing accessors for the Struts related request, session, and application scope objects reated to this request. Note that this bean's methods will trigger exceptions unless there is a `FacesContext` instance for this request.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` StrutsContext()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` javax.faces.event.ActionEvent`

` getActionEvent()`
           Return the `ActionEvent` for the current request (if any).

` ActionMapping`

` getActionMapping()`
           Return the `ActionMapping` for the current request (if any).

` ActionMessages`

` getActionMessages()`
           Return the `ActionMessages` instance containing application error messages for this request (if any).

` ActionServlet`

` getActionServlet()`
           Return the `ActionServlet` instance for this web application.

` Throwable`

` getException()`
           Return the exception that caused one of the Struts custom tags to report a JspException (if any).

` javax.faces.context.ExternalContext`

` getExternalContext()`
           Return the `ExternalContext` for the current request.

` javax.faces.context.FacesContext`

` getFacesContext()`
           Return the `FacesContext` for the current request.

` Locale`

` getLocale()`
           Return the `Locale` stored in the current user's session (if any) for Struts based localization.

` MessageResources`

` getMessageResources()`
           Return the `MessageResources` instance for the application module that is processing this request (if any).

` ModuleConfig`

` getModuleConfig()`
           Return the `ModuleConfig` for the application module to which this request has been assigned (if any).

` boolean`

` isCancelled()`
           Return `true` if a Boolean true value has been stored in the request attribute indicating that this request has been cancelled.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### StrutsContext

    public StrutsContext()

<span id="method_detail"></span>

**Method Detail**

### getActionEvent

    public javax.faces.event.ActionEvent getActionEvent()

Return the `ActionEvent` for the current request (if any).

------------------------------------------------------------------------

### getActionMapping

    public ActionMapping getActionMapping()

Return the `ActionMapping` for the current request (if any).

------------------------------------------------------------------------

### getActionMessages

    public ActionMessages getActionMessages()

Return the `ActionMessages` instance containing application error messages for this request (if any).

------------------------------------------------------------------------

### getActionServlet

    public ActionServlet getActionServlet()

Return the `ActionServlet` instance for this web application.

------------------------------------------------------------------------

### isCancelled

    public boolean isCancelled()

Return `true` if a Boolean true value has been stored in the request attribute indicating that this request has been cancelled.

------------------------------------------------------------------------

### getException

    public Throwable getException()

Return the exception that caused one of the Struts custom tags to report a JspException (if any).

------------------------------------------------------------------------

### getExternalContext

    public javax.faces.context.ExternalContext getExternalContext()

Return the `ExternalContext` for the current request.

------------------------------------------------------------------------

### getFacesContext

    public javax.faces.context.FacesContext getFacesContext()

Return the `FacesContext` for the current request.

------------------------------------------------------------------------

### getLocale

    public Locale getLocale()

Return the `Locale` stored in the current user's session (if any) for Struts based localization.

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources()

Return the `MessageResources` instance for the application module that is processing this request (if any).

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig()

Return the `ModuleConfig` for the application module to which this request has been assigned (if any).

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
<td align="left"><a href="class-use/StrutsContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/util/MessagesMap.html.md" title="class in org.apache.struts.faces.util"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/StrutsContext.html"><strong>FRAMES</strong></a>    <a href="StrutsContext.html"><strong>NO FRAMES</strong></a>    
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
