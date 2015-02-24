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
<td align="left"><a href="../../../../../org/apache/struts/config/BaseConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useBaseConfig.html"><strong>FRAMES</strong></a>    <a href="BaseConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.BaseConfig**
--------------------------------------

Packages that use [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

 

<span id="org.apache.struts.action"></span>

Uses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionFormBean`
           An **ActionFormBean** is the definition of a form bean that is loaded from a `<form-bean>` element in the Struts configuration file.

` class`

`ActionForward`
           An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.

` class`

`ActionMapping`
           An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.

` class`

`ActionRedirect`
            A subclass of [`ActionForward`](../../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.

` class`

`ForwardingActionForward`
           A subclass of `ActionForward` that defaults the `redirect` attribute to `false`.

` class`

`RedirectingActionForward`
           A subclass of **ActionForward** that defaults the `redirect` attribute to `true`.

` class`

`RequestActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `request`.

` class`

`SessionActionMapping`
           Subclass of `ActionMapping` that defaults the form bean scope to `session`.

 

<span id="org.apache.struts.config"></span>

Uses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Subclasses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

` class`

`ActionConfig`
           A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.

` class`

`ControllerConfig`
           A JavaBean representing the configuration information of a `<controller>` element in a Struts configuration file.

` class`

`ExceptionConfig`
           A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.

` class`

`FormBeanConfig`
           A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.

` class`

`FormPropertyConfig`
           A JavaBean representing the configuration information of a `<form-property>` element in a Struts configuration file.

` class`

`ForwardConfig`
           A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.

` class`

`MessageResourcesConfig`
           A JavaBean representing the configuration information of a `<message-resources>` element in a Struts configuration file.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config")

`protected  void`

`BaseConfig.inheritProperties(BaseConfig baseConfig)`
           Compare the properties of this config with that of the given and copy those that are not present.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Subclasses of [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

` class`

`ModuleConfigImpl`
           The collection of static configuration information that describes a Struts-based module.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/BaseConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useBaseConfig.html"><strong>FRAMES</strong></a>    <a href="BaseConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
