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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/PlugIn.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/action/InvalidCancelException.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/RedirectingActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/PlugIn.html"><strong>FRAMES</strong></a>    <a href="PlugIn.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Interface PlugIn
------------------------

**All Known Implementing Classes:**  
[ValidatorPlugIn](../../../../org/apache/struts/validator/ValidatorPlugIn.html.md "class in org.apache.struts.validator")

------------------------------------------------------------------------

    public interface PlugIn

A **PlugIn** is a configuration wrapper for a module-specific resource or service that needs to be notified about application startup and application shutdown events (corresponding to when the container calls `init` and `destroy` on the corresponding [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") instance). `PlugIn` objects can be configured in the `struts-config.xml` file, without the need to subclass [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action") simply to perform application lifecycle activities.

Implementations of this interface must supply a zero-argument constructor for use by [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action"). Configuration can be accomplished by providing standard JavaBeans property setter methods, which will all have been called before the `init()` method is invoked.

This interface can be applied to any class, including an Action subclass.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005) $

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

`destroy()`
           Receive notification that our owning module is being shut down.

` void`

` init(ActionServlet servlet, ModuleConfig config)`
           Receive notification that the specified module is being started up.

 

<span id="method_detail"></span>

**Method Detail**

### destroy

    void destroy()

Receive notification that our owning module is being shut down.

------------------------------------------------------------------------

### init

    void init(ActionServlet servlet,
              ModuleConfig config)
              throws ServletException

Receive notification that the specified module is being started up.

**Parameters:**  
`servlet` - ActionServlet that is managing all the modules in this web application

`config` - ModuleConfig for the module with which this plug-in is associated

**Throws:**  
`ServletException` - if this `PlugIn` cannot be successfully initialized

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/PlugIn.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/action/InvalidCancelException.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/RedirectingActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/PlugIn.html"><strong>FRAMES</strong></a>    <a href="PlugIn.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
