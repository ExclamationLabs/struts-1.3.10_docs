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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionServlet.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionServlet.html"><strong>FRAMES</strong></a>    <a href="ActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionServlet**
-----------------------------------------

Packages that use [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Fields in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) declared as [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

`protected  ActionServlet`

`RequestProcessor.servlet`
           The servlet with which we are associated.

`protected  ActionServlet`

`ActionServletWrapper.servlet`
           The servlet instance to which we are attached.

`protected  ActionServlet`

`ActionForm.servlet`
           The servlet instance to which we are attached.

`protected  ActionServlet`

`Action.servlet`
           The servlet to which we are attached.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

`protected  ActionServlet`

`ActionForm.getServlet()`
           Return the servlet instance to which we are attached.

` ActionServlet`

`Action.getServlet()`
           Return the servlet instance to which we are attached.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`RequestProcessor.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

` void`

`PlugIn.init(ActionServlet servlet, ModuleConfig config)`
           Receive notification that the specified module is being started up.

` void`

`ActionForm.setServlet(ActionServlet servlet)`
           Set the servlet instance to which we are attached (if `servlet` is non-null).

` void`

`Action.setServlet(ActionServlet servlet)`
           Set the servlet instance to which we are attached (if `servlet` is non-null), or release any allocated resources (if `servlet` is null).

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action") |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionServletWrapper(ActionServlet servlet)`                                                                                                                                                                                                   
            Create object and set `servlet` property.                                                                                                                                                                                              |

 

<span id="org.apache.struts.chain"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html)

 

Methods in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`ComposableRequestProcessor.init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Initialize this request processor instance.

`protected  void`

`ComposableRequestProcessor.initCatalogFactory(ActionServlet servlet, ModuleConfig moduleConfig)`
            Establish the CatalogFactory which will be used to look up the catalog which has the request processing command.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` ActionServlet`

`ServletActionContext.getActionServlet()`
            Return the ActionServlet for this context.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`ServletActionContext.setActionServlet(ActionServlet servlet)`
            Set the ActionServlet instance for this context.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` ActionForm`

`FormBeanConfig.createActionForm(ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

 

<span id="org.apache.struts.mock"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

 

Subclasses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html)

` class`

`MockActionServlet`
           Mock **ActionServlet** object for low-level unit tests of Struts controller components.

 

Methods in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) that return [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` ActionServlet`

`MockMultipartRequestHandler.getServlet()`
           Get the mock ActionServlet instance.

 

Methods in [org.apache.struts.mock](../../../../../org/apache/struts/mock/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`MockMultipartRequestHandler.setServlet(ActionServlet servlet)`
           Convienience method to set a reference to a mock ActionServlet instance.

 

<span id="org.apache.struts.upload"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html)

 

Methods in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) that return [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` ActionServlet`

`MultipartRequestHandler.getServlet()`
            Get the ActionServlet instance

` ActionServlet`

`CommonsMultipartRequestHandler.getServlet()`
            Retrieves the servlet with which this handler is associated.

 

Methods in [org.apache.struts.upload](../../../../../org/apache/struts/upload/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`MultipartRequestHandler.setServlet(ActionServlet servlet)`
            Convienience method to set a reference to a working ActionServlet instance.

` void`

`CommonsMultipartRequestHandler.setServlet(ActionServlet servlet)`
            Sets the servlet with which this handler is associated.

 

<span id="org.apache.struts.util"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

`static String`

`RequestUtils.actionIdURL(ForwardConfig forward, HttpServletRequest request, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static String`

`RequestUtils.actionIdURL(String originalPath, ModuleConfig moduleConfig, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static ActionForm`

`RequestUtils.createActionForm(FormBeanConfig config, ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in `config`.

`static ActionForm`

`RequestUtils.createActionForm(HttpServletRequest request, ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet)`
           Create (if necessary) and return an `ActionForm` instance appropriate for this request.

`static String`

`RequestUtils.getServletMapping(ActionServlet servlet)`
           Retrieves the servlet mapping pattern for the specified [`ActionServlet`](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action").

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [ActionServlet](../../../../../org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action")

` void`

`ValidatorPlugIn.init(ActionServlet servlet, ModuleConfig config)`
           Initialize and load our resources.

 

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
<td align="left"><a href="../../../../../org/apache/struts/action/ActionServlet.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionServlet.html"><strong>FRAMES</strong></a>    <a href="ActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
