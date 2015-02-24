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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionForward**
-----------------------------------------

Packages that use [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionRedirect`
            A subclass of [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.

` class`

`ForwardingActionForward`
           A subclass of `ActionForward` that defaults the `redirect` attribute to `false`.

` class`

`RedirectingActionForward`
           A subclass of **ActionForward** that defaults the `redirect` attribute to `true`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`Action.execute(ActionMapping mapping, ActionForm form, ServletRequest request, ServletResponse response)`
           Process the specified non-HTTP request, and create the corresponding non-HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

`ExceptionHandler.execute(Exception ex, ExceptionConfig ae, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response)`
            Handle the Exception.

` ActionForward`

`ActionMapping.findForward(String forwardName)`
           Find and return the `ForwardConfig` instance defining how forwarding to the specified logical name should be handled.

` ActionForward`

`ActionMapping.getInputForward()`
           Create (if necessary) and return an [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") that corresponds to the `input` property of this Action.

`protected  ActionForward`

`RequestProcessor.processActionPerform(HttpServletRequest request, HttpServletResponse response, Action action, ActionForm form, ActionMapping mapping)`
           Ask the specified `Action` instance to handle this request.

`protected  ActionForward`

`RequestProcessor.processException(HttpServletRequest request, HttpServletResponse response, Exception exception, ActionForm form, ActionMapping mapping)`
           Ask our exception handler to handle the exception.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

`protected  String`

`ExceptionHandler.determineIncludePath(ExceptionConfig config, ActionForward actionForward)`
           Return a path to which an include should be attempted in the case when the response was committed before the `ExceptionHandler` was invoked.

`protected  void`

`ExceptionHandler.handleCommittedResponse(Exception ex, ExceptionConfig config, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response, ActionForward actionForward)`
           Attempt to give good information when the response has already been committed when the exception was thrown.

`protected  void`

`ExceptionHandler.storeException(HttpServletRequest request, String property, ActionMessage error, ActionForward forward, String scope)`
           Default implementation for handling an `ActionMessage` generated from an `Exception` during `Action` delegation.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionForward(ActionForward copyMe)`                                                                                                                                                                                                           
            Construct a new instance based on the values of another ActionForward.                                                                                                                                                                 |

 

<span id="org.apache.struts.config"></span>

Uses of [ActionForward](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` ActionForward`

`ConfigHelperInterface.getActionForward(String name)`
            Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

` ActionForward`

`ConfigHelper.getActionForward(String name)`
            Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionForward](../../../../../org/apache/struts/action/ActionForward.html "class in org.apache.struts.action")

` void`

`ConfigHelper.setForward(ActionForward forward)`
           Set the forward associated with this instance.

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
