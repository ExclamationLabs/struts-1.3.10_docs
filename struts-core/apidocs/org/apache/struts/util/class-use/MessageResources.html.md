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
<td align="left"><a href="../../../../../org/apache/struts/util/MessageResources.html.md" title="class in org.apache.struts.util"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/util//class-useMessageResources.html"><strong>FRAMES</strong></a>    <a href="MessageResources.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.util.MessageResources**
------------------------------------------

Packages that use [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Fields in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) declared as [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

`protected  MessageResources`

`ActionServlet.internal`
           The resources object for our internal resources.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

`protected  MessageResources`

`RequestProcessor.getInternal()`
           Return the `MessageResources` instance containing our internal message strings.

` MessageResources`

`ActionServlet.getInternal()`
           Return the `MessageResources` instance containing our internal message strings.

`protected  MessageResources`

`Action.getResources(HttpServletRequest request)`
           Return the default message resources for the current module.

`protected  MessageResources`

`Action.getResources(HttpServletRequest request, String key)`
           Return the specified message resources for the current module.

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

` MessageResources`

`ServletActionContext.getMessageResources()`
            

` MessageResources`

`ActionContextBase.getMessageResources()`
            

` MessageResources`

`ActionContext.getMessageResources()`
           Return the default message resources for the current module.

` MessageResources`

`ServletActionContext.getMessageResources(String key)`
            

` MessageResources`

`ActionContextBase.getMessageResources(String key)`
            

` MessageResources`

`ActionContext.getMessageResources(String key)`
           Return the specified message resources for the current module.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

` void`

`ServletActionContext.setMessageResources(MessageResources resources)`
            

` void`

`ActionContextBase.setMessageResources(MessageResources messageResources)`
            

` void`

`ActionContext.setMessageResources(MessageResources resources)`
           Set the default message resources for the current module.

` void`

`ServletActionContext.setMessageResources(String key, MessageResources resources)`
            Store the mesasage resources for the current module under the given request attribute key.

 

<span id="org.apache.struts.config"></span>

Uses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

` MessageResources`

`ConfigHelperInterface.getMessageResources()`
            The application resources for this application.

` MessageResources`

`ConfigHelper.getMessageResources()`
            The application resources for this application.

 

<span id="org.apache.struts.util"></span>

Uses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Subclasses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

` class`

`PropertyMessageResources`
           Concrete subclass of `MessageResources` that reads message keys and corresponding strings from named property resources in a ***similar*** manner (see *modes* below) that `java.util.PropertyResourceBundle` does.

 

Fields in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) declared as [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

`protected static MessageResources`

`ResponseUtils.messages`
           The message resources for this package.

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) that return [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

` MessageResources`

`PropertyMessageResourcesFactory.createResources(String config)`
           Create and return a newly instansiated `MessageResources`.

`abstract  MessageResources`

`MessageResourcesFactory.createResources(String config)`
           Create and return a newly instansiated `MessageResources`.

`static MessageResources`

`MessageResources.getMessageResources(String config)`
           Create and return an instance of `MessageResources` for the created by the default `MessageResourcesFactory`.

 

<span id="org.apache.struts.validator"></span>

Uses of [MessageResources](../../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) that return [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

`static MessageResources`

`Resources.getMessageResources(HttpServletRequest request)`
           Retrieve `MessageResources` for the module.

`static MessageResources`

`Resources.getMessageResources(ServletContext application, HttpServletRequest request, String bundle)`
           Retrieve `MessageResources` for the module and bundle.

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [MessageResources](../../../../../org/apache/struts/util/MessageResources.html "class in org.apache.struts.util")

`static String[]`

`Resources.getArgs(String actionName, MessageResources messages, Locale locale, Field field)`
           Gets the message arguments based on the current `ValidatorAction` and `Field`.

`static String`

`Resources.getMessage(MessageResources messages, Locale locale, String key)`
           Gets the `Locale` sensitive value based on the key passed in.

`static String`

`Resources.getMessage(MessageResources messages, Locale locale, ValidatorAction va, Field field)`
           Gets the locale sensitive message based on the `ValidatorAction` message and the `Field`'s arg objects.

`static String`

`Resources.getMessage(ServletContext application, HttpServletRequest request, MessageResources defaultMessages, Locale locale, ValidatorAction va, Field field)`
           Gets the `Locale` sensitive value based on the key passed in.

 

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
<td align="left"><a href="../../../../../org/apache/struts/util/MessageResources.html.md" title="class in org.apache.struts.util"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/util//class-useMessageResources.html"><strong>FRAMES</strong></a>    <a href="MessageResources.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
