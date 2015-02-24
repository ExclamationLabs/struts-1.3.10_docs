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
<td align="left"><a href="class-use/ModuleConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/MessageResourcesConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ModuleConfigFactory.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ModuleConfig.html"><strong>FRAMES</strong></a>    <a href="ModuleConfig.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Interface ModuleConfig
------------------------

**All Known Implementing Classes:**  
[ModuleConfigImpl](../../../../org/apache/struts/config/impl/ModuleConfigImpl.html.md "class in org.apache.struts.config.impl")

------------------------------------------------------------------------

    public interface ModuleConfig

The collection of static configuration information that describes a Struts-based module. Multiple modules are identified by a *prefix* at the beginning of the context relative portion of the request URI. If no module prefix can be matched, the default configuration (with a prefix equal to a zero-length string) is selected, which is elegantly backwards compatible with the previous Struts behavior that only supported one module.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-08-06 04:12:10 -0400 (Sat, 06 Aug 2005) $

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` void`

` addActionConfig(ActionConfig config)`
            Add a new `ActionConfig` instance to the set associated with this module.

` void`

` addExceptionConfig(ExceptionConfig config)`
            Add a new `ExceptionConfig` instance to the set associated with this module.

` void`

` addFormBeanConfig(FormBeanConfig config)`
            Add a new `FormBeanConfig` instance to the set associated with this module.

` void`

` addForwardConfig(ForwardConfig config)`
            Add a new `ForwardConfig` instance to the set of global forwards associated with this module.

` void`

` addMessageResourcesConfig(MessageResourcesConfig config)`
            Add a new `MessageResourcesConfig` instance to the set associated with this module.

` void`

` addPlugInConfig(PlugInConfig plugInConfig)`
            Add a newly configured [`PlugInConfig`](../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

` ActionConfig`

` findActionConfig(String path)`
            Return the action configuration for the specified path, if any; otherwise return `null`.

` ActionConfig`

` findActionConfigId(String actionId)`
           Returns the action configuration for the specifed action action identifier.

` ActionConfig[]`

` findActionConfigs()`
            Return the action configurations for this module.

` ExceptionConfig`

` findException(Class type)`
            Perform a recursive search for an ExceptionConfig registered for this class, or for any superclass.

` ExceptionConfig`

` findExceptionConfig(String type)`
            Return the exception configuration for the specified type, if any; otherwise return `null`.

` ExceptionConfig[]`

` findExceptionConfigs()`
            Return the exception configurations for this module.

` FormBeanConfig`

` findFormBeanConfig(String name)`
            Return the form bean configuration for the specified key, if any; otherwise return `null`.

` FormBeanConfig[]`

` findFormBeanConfigs()`
            Return the form bean configurations for this module.

` ForwardConfig`

` findForwardConfig(String name)`
            Return the forward configuration for the specified key, if any; otherwise return `null`.

` ForwardConfig[]`

` findForwardConfigs()`
            Return the form bean configurations for this module.

` MessageResourcesConfig`

` findMessageResourcesConfig(String key)`
            Return the message resources configuration for the specified key, if any; otherwise return `null`.

` MessageResourcesConfig[]`

` findMessageResourcesConfigs()`
            Return the message resources configurations for this module.

` PlugInConfig[]`

` findPlugInConfigs()`
            Return the configured plug-in actions for this module.

` void`

`freeze()`
            Freeze the configuration of this module.

` String`

` getActionFormBeanClass()`
            The default class name to be used when creating action form bean instances.

` String`

` getActionForwardClass()`
            The default class name to be used when creating action forward instances.

` String`

` getActionMappingClass()`
            The default class name to be used when creating action mapping instances.

` boolean`

` getConfigured()`
            Has this module been completely configured yet.

` ControllerConfig`

` getControllerConfig()`
            The controller configuration object for this module.

` String`

` getPrefix()`
            The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet.

` void`

` removeActionConfig(ActionConfig config)`
            Remove the specified action configuration instance.

` void`

` removeExceptionConfig(ExceptionConfig config)`
            Remove the specified exception configuration instance.

` void`

` removeFormBeanConfig(FormBeanConfig config)`
            Remove the specified form bean configuration instance.

` void`

` removeForwardConfig(ForwardConfig config)`
            Remove the specified forward configuration instance.

` void`

` removeMessageResourcesConfig(MessageResourcesConfig config)`
            Remove the specified message resources configuration instance.

` void`

` setActionFormBeanClass(String actionFormBeanClass)`
            The default class name to be used when creating action form bean instances.

` void`

` setActionForwardClass(String actionForwardClass)`
            The default class name to be used when creating action forward instances.

` void`

` setActionMappingClass(String actionMappingClass)`
            The default class name to be used when creating action mapping instances.

` void`

` setControllerConfig(ControllerConfig cc)`
            The controller configuration object for this module.

` void`

` setPrefix(String prefix)`
            The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet.

 

<span id="method_detail"></span>

**Method Detail**

### getConfigured

    boolean getConfigured()

Has this module been completely configured yet. Once this flag has been set, any attempt to modify the configuration will return an IllegalStateException.

------------------------------------------------------------------------

### getControllerConfig

    ControllerConfig getControllerConfig()

The controller configuration object for this module.

------------------------------------------------------------------------

### setControllerConfig

    void setControllerConfig(ControllerConfig cc)

The controller configuration object for this module.

**Parameters:**  
`cc` - The controller configuration object for this module.

------------------------------------------------------------------------

### getPrefix

    String getPrefix()

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

------------------------------------------------------------------------

### setPrefix

    void setPrefix(String prefix)

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

**Parameters:**  
`prefix` - The prefix of the context-relative portion of the request URI.

------------------------------------------------------------------------

### getActionFormBeanClass

    String getActionFormBeanClass()

The default class name to be used when creating action form bean instances.

------------------------------------------------------------------------

### setActionFormBeanClass

    void setActionFormBeanClass(String actionFormBeanClass)

The default class name to be used when creating action form bean instances.

**Parameters:**  
`actionFormBeanClass` - default class name to be used when creating action form bean instances.

------------------------------------------------------------------------

### getActionMappingClass

    String getActionMappingClass()

The default class name to be used when creating action mapping instances.

------------------------------------------------------------------------

### setActionMappingClass

    void setActionMappingClass(String actionMappingClass)

The default class name to be used when creating action mapping instances.

**Parameters:**  
`actionMappingClass` - default class name to be used when creating action mapping instances.

------------------------------------------------------------------------

### addActionConfig

    void addActionConfig(ActionConfig config)

Add a new `ActionConfig` instance to the set associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addExceptionConfig

    void addExceptionConfig(ExceptionConfig config)

Add a new `ExceptionConfig` instance to the set associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addFormBeanConfig

    void addFormBeanConfig(FormBeanConfig config)

Add a new `FormBeanConfig` instance to the set associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### getActionForwardClass

    String getActionForwardClass()

The default class name to be used when creating action forward instances.

------------------------------------------------------------------------

### setActionForwardClass

    void setActionForwardClass(String actionForwardClass)

The default class name to be used when creating action forward instances.

**Parameters:**  
`actionForwardClass` - default class name to be used when creating action forward instances.

------------------------------------------------------------------------

### addForwardConfig

    void addForwardConfig(ForwardConfig config)

Add a new `ForwardConfig` instance to the set of global forwards associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addMessageResourcesConfig

    void addMessageResourcesConfig(MessageResourcesConfig config)

Add a new `MessageResourcesConfig` instance to the set associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addPlugInConfig

    void addPlugInConfig(PlugInConfig plugInConfig)

Add a newly configured [`PlugInConfig`](../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

**Parameters:**  
`plugInConfig` - The new configuration instance to be added

------------------------------------------------------------------------

### findActionConfig

    ActionConfig findActionConfig(String path)

Return the action configuration for the specified path, if any; otherwise return `null`.

**Parameters:**  
`path` - Path of the action configuration to return

------------------------------------------------------------------------

### findActionConfigs

    ActionConfig[] findActionConfigs()

Return the action configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findActionConfigId

    ActionConfig findActionConfigId(String actionId)

Returns the action configuration for the specifed action action identifier.

**Parameters:**  
`actionId` - the action identifier

**Returns:**  
the action config if found; otherwise `null`

**Since:**  
Struts 1.3.6

**See Also:**  
[`ActionConfig.getActionId()`](../../../../org/apache/struts/config/ActionConfig.html.md#getActionId())

------------------------------------------------------------------------

### findExceptionConfig

    ExceptionConfig findExceptionConfig(String type)

Return the exception configuration for the specified type, if any; otherwise return `null`.

**Parameters:**  
`type` - Exception class name to find a configuration for

------------------------------------------------------------------------

### findException

    ExceptionConfig findException(Class type)

Perform a recursive search for an ExceptionConfig registered for this class, or for any superclass. This should only be used in the case when an `ActionConfig` is not available; otherwise, use `ActionConfig.findException(Class)` to preserve the search order.

**Parameters:**  
`type` - Exception class name to find a configuration for

**See Also:**  
[`findException(Class)`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")

------------------------------------------------------------------------

### findExceptionConfigs

    ExceptionConfig[] findExceptionConfigs()

Return the exception configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findFormBeanConfig

    FormBeanConfig findFormBeanConfig(String name)

Return the form bean configuration for the specified key, if any; otherwise return `null`.

**Parameters:**  
`name` - Name of the form bean configuration to return

------------------------------------------------------------------------

### findFormBeanConfigs

    FormBeanConfig[] findFormBeanConfigs()

Return the form bean configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findForwardConfig

    ForwardConfig findForwardConfig(String name)

Return the forward configuration for the specified key, if any; otherwise return `null`.

**Parameters:**  
`name` - Name of the forward configuration to return

------------------------------------------------------------------------

### findForwardConfigs

    ForwardConfig[] findForwardConfigs()

Return the form bean configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findMessageResourcesConfig

    MessageResourcesConfig findMessageResourcesConfig(String key)

Return the message resources configuration for the specified key, if any; otherwise return `null`.

**Parameters:**  
`key` - Key of the data source configuration to return

------------------------------------------------------------------------

### findMessageResourcesConfigs

    MessageResourcesConfig[] findMessageResourcesConfigs()

Return the message resources configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findPlugInConfigs

    PlugInConfig[] findPlugInConfigs()

Return the configured plug-in actions for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### freeze

    void freeze()

Freeze the configuration of this module. After this method returns, any attempt to modify the configuration will return an IllegalStateException.

------------------------------------------------------------------------

### removeActionConfig

    void removeActionConfig(ActionConfig config)

Remove the specified action configuration instance.

**Parameters:**  
`config` - ActionConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeExceptionConfig

    void removeExceptionConfig(ExceptionConfig config)

Remove the specified exception configuration instance.

**Parameters:**  
`config` - ActionConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeFormBeanConfig

    void removeFormBeanConfig(FormBeanConfig config)

Remove the specified form bean configuration instance.

**Parameters:**  
`config` - FormBeanConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeForwardConfig

    void removeForwardConfig(ForwardConfig config)

Remove the specified forward configuration instance.

**Parameters:**  
`config` - ForwardConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeMessageResourcesConfig

    void removeMessageResourcesConfig(MessageResourcesConfig config)

Remove the specified message resources configuration instance.

**Parameters:**  
`config` - MessageResourcesConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

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
<td align="left"><a href="class-use/ModuleConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/MessageResourcesConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ModuleConfigFactory.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ModuleConfig.html"><strong>FRAMES</strong></a>    <a href="ModuleConfig.html"><strong>NO FRAMES</strong></a>    
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
