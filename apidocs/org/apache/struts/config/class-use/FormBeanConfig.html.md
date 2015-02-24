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
<td align="left"><a href="../../../../../org/apache/struts/config/FormBeanConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useFormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="FormBeanConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.config.FormBeanConfig**
------------------------------------------

Packages that use [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

Uses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionFormBean`
           An **ActionFormBean** is the definition of a form bean that is loaded from a `<form-bean>` element in the Struts configuration file.

 

Fields in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) declared as [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

`protected  FormBeanConfig`

`DynaActionFormClass.config`
           The form bean configuration information for this class.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

`protected  FormBeanConfig`

`ActionServlet.processFormBeanConfigClass(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Checks if the current beanConfig is using the correct class based on the class of its ancestor form bean config.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

`static DynaActionFormClass`

`DynaActionFormClass.createDynaActionFormClass(FormBeanConfig config)`
           Return the `DynaActionFormClass` instance for the specified form bean configuration instance.

` void`

`DynaActionForm.initialize(FormBeanConfig config)`
           Initialize the specified form bean.

`protected  void`

`DynaActionFormClass.introspect(FormBeanConfig config)`
           Introspect our form bean configuration to identify the supported properties.

`protected  FormBeanConfig`

`ActionServlet.processFormBeanConfigClass(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Checks if the current beanConfig is using the correct class based on the class of its ancestor form bean config.

`protected  void`

`ActionServlet.processFormBeanExtension(FormBeanConfig beanConfig, ModuleConfig moduleConfig)`
           Extend the form bean's configuration as necessary.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` DynaActionFormClass(FormBeanConfig config)`                                                                                                                                                                                                      
            Construct a new `DynaActionFormClass` for the specified form bean configuration.                                                                                                                                                         |

 

<span id="org.apache.struts.config"></span>

Uses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

` FormBeanConfig`

`ModuleConfig.findFormBeanConfig(String name)`
            Return the form bean configuration for the specified key, if any; otherwise return `null`.

` FormBeanConfig[]`

`ModuleConfig.findFormBeanConfigs()`
            Return the form bean configurations for this module.

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfig.addFormBeanConfig(FormBeanConfig config)`
            Add a new `FormBeanConfig` instance to the set associated with this module.

`protected  void`

`FormBeanConfig.inheritFormProperties(FormBeanConfig config)`
           Compare the form properties of this bean with that of the given and copy those that are not present.

` void`

`FormBeanConfig.inheritFrom(FormBeanConfig config)`
           Inherit values that have not been overridden from the provided config object.

` void`

`ModuleConfig.removeFormBeanConfig(FormBeanConfig config)`
            Remove the specified form bean configuration instance.

 

<span id="org.apache.struts.config.impl"></span>

Uses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html)

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) that return [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

` FormBeanConfig`

`ModuleConfigImpl.findFormBeanConfig(String name)`
            Return the form bean configuration for the specified key, if any; otherwise return `null`.

` FormBeanConfig[]`

`ModuleConfigImpl.findFormBeanConfigs()`
            Return the form bean configurations for this module.

 

Methods in [org.apache.struts.config.impl](../../../../../org/apache/struts/config/impl/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

` void`

`ModuleConfigImpl.addFormBeanConfig(FormBeanConfig config)`
            Add a new `FormBeanConfig` instance to the set associated with this module.

` void`

`ModuleConfigImpl.removeFormBeanConfig(FormBeanConfig config)`
            Remove the specified form bean configuration instance.

 

<span id="org.apache.struts.util"></span>

Uses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html)

 

Methods in [org.apache.struts.util](../../../../../org/apache/struts/util/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

`static ActionForm`

`RequestUtils.createActionForm(FormBeanConfig config, ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in `config`.

 

<span id="org.apache.struts.validator"></span>

Uses of [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [FormBeanConfig](../../../../../org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config")

` void`

`BeanValidatorForm.initialize(FormBeanConfig formBeanConfig)`
           Perform intialization of the ActionForm.

 

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
<td align="left"><a href="../../../../../org/apache/struts/config/FormBeanConfig.html.md" title="class in org.apache.struts.config"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config//class-useFormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="FormBeanConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
