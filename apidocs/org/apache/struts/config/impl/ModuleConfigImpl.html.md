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
<td align="left"><a href="class-use/ModuleConfigImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/config/impl/DefaultModuleConfigFactory.html.md" title="class in org.apache.struts.config.impl"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config/impl/ModuleConfigImpl.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config.impl
 Class ModuleConfigImpl
-----------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.impl.ModuleConfigImpl

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

------------------------------------------------------------------------

    public class ModuleConfigImpl

extends [BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [ModuleConfig](../../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config")

The collection of static configuration information that describes a Struts-based module. Multiple modules are identified by a *prefix* at the beginning of the context relative portion of the request URI. If no module prefix can be matched, the default configuration (with a prefix equal to a zero-length string) is selected, which is elegantly backwards compatible with the previous Struts behavior that only supported one module.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-12-31 03:57:16 -0500 (Sat, 31 Dec 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.config.impl.ModuleConfigImpl)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  HashMap`

` actionConfigIds`
           The set of action configuration for this module, if any, keyed by the `actionId` property.

`protected  List`

` actionConfigList`
           The set of action configurations for this module, if any, listed in the order in which they are added.

`protected  HashMap`

` actionConfigs`
           The set of action configurations for this module, if any, keyed by the `path` property.

`protected  String`

` actionFormBeanClass`
           The default class name to be used when creating action form bean instances.

`protected  String`

` actionForwardClass`
           The default class name to be used when creating action forward instances.

`protected  String`

` actionMappingClass`
           The default class name to be used when creating action mapping instances.

`protected  ControllerConfig`

` controllerConfig`
           The controller configuration object for this module.

`protected  HashMap`

` exceptions`
           The set of exception handling configurations for this module, if any, keyed by the `type` property.

`protected  HashMap`

` formBeans`
           The set of form bean configurations for this module, if any, keyed by the `name` property.

`protected  HashMap`

` forwards`
           The set of global forward configurations for this module, if any, keyed by the `name` property.

`protected static Log`

` log`
           Commons Logging instance.

`protected  ActionConfigMatcher`

` matcher`
           Matches action config paths against compiled wildcard patterns

`protected  HashMap`

` messageResources`
           The set of message resources configurations for this module, if any, keyed by the `key` property.

`protected  ArrayList`

` plugIns`
           The set of configured plug-in Actions for this module, if any, in the order they were declared and configured.

`protected  String`

` prefix`
           The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` configured`                                                                                                                                                      |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                      |
|----------------------------------------------------------------------------------------------|
| ` ModuleConfigImpl()`                                                                        
            Constructor for ModuleConfigImpl.                                                  |
| ` ModuleConfigImpl(String prefix)`                                                           
            Construct an ModuleConfigImpl object according to the specified parameter values.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addActionConfig(ActionConfig config)`
            Ad d a new `ActionConfig` instance to the set associated with this module.

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
            Add a newly configured [`PlugInConfig`](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

` ActionConfig`

` findActionConfig(String path)`
            Return the action configuration for the specified path, first looking a direct match, then if none found, a wildcard pattern match; otherwise return `null`.

` ActionConfig`

` findActionConfigId(String actionId)`
           Returns the action configuration for the specifed action action identifier.

` ActionConfig[]`

` findActionConfigs()`
            Return the action configurations for this module.

` ExceptionConfig`

` findException(Class type)`
           Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled.

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

` freeze()`
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

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                               |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="actionConfigs"></span>

### actionConfigs

    protected HashMap actionConfigs

The set of action configurations for this module, if any, keyed by the `path` property.

------------------------------------------------------------------------

<span id="actionConfigIds"></span>

### actionConfigIds

    protected HashMap actionConfigIds

The set of action configuration for this module, if any, keyed by the `actionId` property.

------------------------------------------------------------------------

<span id="actionConfigList"></span>

### actionConfigList

    protected List actionConfigList

The set of action configurations for this module, if any, listed in the order in which they are added.

------------------------------------------------------------------------

<span id="exceptions"></span>

### exceptions

    protected HashMap exceptions

The set of exception handling configurations for this module, if any, keyed by the `type` property.

------------------------------------------------------------------------

<span id="formBeans"></span>

### formBeans

    protected HashMap formBeans

The set of form bean configurations for this module, if any, keyed by the `name` property.

------------------------------------------------------------------------

<span id="forwards"></span>

### forwards

    protected HashMap forwards

The set of global forward configurations for this module, if any, keyed by the `name` property.

------------------------------------------------------------------------

<span id="messageResources"></span>

### messageResources

    protected HashMap messageResources

The set of message resources configurations for this module, if any, keyed by the `key` property.

------------------------------------------------------------------------

<span id="plugIns"></span>

### plugIns

    protected ArrayList plugIns

The set of configured plug-in Actions for this module, if any, in the order they were declared and configured.

------------------------------------------------------------------------

<span id="controllerConfig"></span>

### controllerConfig

    protected ControllerConfig controllerConfig

The controller configuration object for this module.

------------------------------------------------------------------------

<span id="prefix"></span>

### prefix

    protected String prefix

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

------------------------------------------------------------------------

<span id="actionFormBeanClass"></span>

### actionFormBeanClass

    protected String actionFormBeanClass

The default class name to be used when creating action form bean instances.

------------------------------------------------------------------------

<span id="actionMappingClass"></span>

### actionMappingClass

    protected String actionMappingClass

The default class name to be used when creating action mapping instances.

------------------------------------------------------------------------

<span id="actionForwardClass"></span>

### actionForwardClass

    protected String actionForwardClass

The default class name to be used when creating action forward instances.

------------------------------------------------------------------------

<span id="matcher"></span>

### matcher

    protected ActionConfigMatcher matcher

Matches action config paths against compiled wildcard patterns

<span id="constructor_detail"></span>

**Constructor Detail**

### ModuleConfigImpl

    public ModuleConfigImpl()

Constructor for ModuleConfigImpl. Assumes default configuration.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### ModuleConfigImpl

    public ModuleConfigImpl(String prefix)

Construct an ModuleConfigImpl object according to the specified parameter values.

**Parameters:**  
`prefix` - Context-relative URI prefix for this module

<span id="method_detail"></span>

**Method Detail**

### getConfigured

    public boolean getConfigured()

Has this module been completely configured yet. Once this flag has been set, any attempt to modify the configuration will return an IllegalStateException.

**Specified by:**  
` getConfigured` in interface `ModuleConfig`

------------------------------------------------------------------------

### getControllerConfig

    public ControllerConfig getControllerConfig()

The controller configuration object for this module.

**Specified by:**  
` getControllerConfig` in interface `ModuleConfig`

------------------------------------------------------------------------

### setControllerConfig

    public void setControllerConfig(ControllerConfig cc)

The controller configuration object for this module.

**Specified by:**  
` setControllerConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`cc` - The controller configuration object for this module.

------------------------------------------------------------------------

### getPrefix

    public String getPrefix()

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

**Specified by:**  
` getPrefix` in interface `ModuleConfig`

------------------------------------------------------------------------

### setPrefix

    public void setPrefix(String prefix)

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

**Specified by:**  
` setPrefix` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`prefix` - The prefix of the context-relative portion of the request URI.

------------------------------------------------------------------------

### getActionFormBeanClass

    public String getActionFormBeanClass()

The default class name to be used when creating action form bean instances.

**Specified by:**  
` getActionFormBeanClass` in interface `ModuleConfig`

------------------------------------------------------------------------

### setActionFormBeanClass

    public void setActionFormBeanClass(String actionFormBeanClass)

The default class name to be used when creating action form bean instances.

**Specified by:**  
` setActionFormBeanClass` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`actionFormBeanClass` - default class name to be used when creating action form bean instances.

------------------------------------------------------------------------

### getActionMappingClass

    public String getActionMappingClass()

The default class name to be used when creating action mapping instances.

**Specified by:**  
` getActionMappingClass` in interface `ModuleConfig`

------------------------------------------------------------------------

### setActionMappingClass

    public void setActionMappingClass(String actionMappingClass)

The default class name to be used when creating action mapping instances.

**Specified by:**  
` setActionMappingClass` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`actionMappingClass` - default class name to be used when creating action mapping instances.

------------------------------------------------------------------------

### addActionConfig

    public void addActionConfig(ActionConfig config)

Ad d a new `ActionConfig` instance to the set associated with this module.

**Specified by:**  
` addActionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addExceptionConfig

    public void addExceptionConfig(ExceptionConfig config)

Add a new `ExceptionConfig` instance to the set associated with this module.

**Specified by:**  
` addExceptionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addFormBeanConfig

    public void addFormBeanConfig(FormBeanConfig config)

Add a new `FormBeanConfig` instance to the set associated with this module.

**Specified by:**  
` addFormBeanConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### getActionForwardClass

    public String getActionForwardClass()

The default class name to be used when creating action forward instances.

**Specified by:**  
` getActionForwardClass` in interface `ModuleConfig`

------------------------------------------------------------------------

### setActionForwardClass

    public void setActionForwardClass(String actionForwardClass)

The default class name to be used when creating action forward instances.

**Specified by:**  
` setActionForwardClass` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`actionForwardClass` - default class name to be used when creating action forward instances.

------------------------------------------------------------------------

### addForwardConfig

    public void addForwardConfig(ForwardConfig config)

Add a new `ForwardConfig` instance to the set of global forwards associated with this module.

**Specified by:**  
` addForwardConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addMessageResourcesConfig

    public void addMessageResourcesConfig(MessageResourcesConfig config)

Add a new `MessageResourcesConfig` instance to the set associated with this module.

**Specified by:**  
` addMessageResourcesConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addPlugInConfig

    public void addPlugInConfig(PlugInConfig plugInConfig)

Add a newly configured [`PlugInConfig`](../../../../../org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") instance to the set of plug-in Actions for this module.

**Specified by:**  
` addPlugInConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`plugInConfig` - The new configuration instance to be added

------------------------------------------------------------------------

### findActionConfig

    public ActionConfig findActionConfig(String path)

Return the action configuration for the specified path, first looking a direct match, then if none found, a wildcard pattern match; otherwise return `null`.

**Specified by:**  
` findActionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`path` - Path of the action configuration to return

------------------------------------------------------------------------

### findActionConfigId

    public ActionConfig findActionConfigId(String actionId)

Returns the action configuration for the specifed action action identifier.

**Specified by:**  
` findActionConfigId` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`actionId` - the action identifier

**Returns:**  
the action config if found; otherwise `null`

**Since:**  
Struts 1.3.6

**See Also:**  
[`ActionConfig.getActionId()`](../../../../../org/apache/struts/config/ActionConfig.html.md#getActionId())

------------------------------------------------------------------------

### findActionConfigs

    public ActionConfig[] findActionConfigs()

Return the action configurations for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findActionConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### findExceptionConfig

    public ExceptionConfig findExceptionConfig(String type)

Return the exception configuration for the specified type, if any; otherwise return `null`.

**Specified by:**  
` findExceptionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`type` - Exception class name to find a configuration for

------------------------------------------------------------------------

### findException

    public ExceptionConfig findException(Class type)

Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled.

In original Struts usage, this was only available in `ActionConfig`, but there are cases when an exception could be thrown before an `ActionConfig` has been identified, where global exception handlers may still be pertinent.

TODO: Look for a way to share this logic with `ActionConfig`, although there are subtle differences, and it certainly doesn't seem like it should be done with inheritance.

**Specified by:**  
` findException` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`type` - Exception class for which to find a handler

**Since:**  
Struts 1.3.0

**See Also:**  
[`findException(Class)`](../../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")

------------------------------------------------------------------------

### findExceptionConfigs

    public ExceptionConfig[] findExceptionConfigs()

Return the exception configurations for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findExceptionConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### findFormBeanConfig

    public FormBeanConfig findFormBeanConfig(String name)

Return the form bean configuration for the specified key, if any; otherwise return `null`.

**Specified by:**  
` findFormBeanConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`name` - Name of the form bean configuration to return

------------------------------------------------------------------------

### findFormBeanConfigs

    public FormBeanConfig[] findFormBeanConfigs()

Return the form bean configurations for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findFormBeanConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### findForwardConfig

    public ForwardConfig findForwardConfig(String name)

Return the forward configuration for the specified key, if any; otherwise return `null`.

**Specified by:**  
` findForwardConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`name` - Name of the forward configuration to return

------------------------------------------------------------------------

### findForwardConfigs

    public ForwardConfig[] findForwardConfigs()

Return the form bean configurations for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findForwardConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### findMessageResourcesConfig

    public MessageResourcesConfig findMessageResourcesConfig(String key)

Return the message resources configuration for the specified key, if any; otherwise return `null`.

**Specified by:**  
` findMessageResourcesConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`key` - Key of the data source configuration to return

------------------------------------------------------------------------

### findMessageResourcesConfigs

    public MessageResourcesConfig[] findMessageResourcesConfigs()

Return the message resources configurations for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findMessageResourcesConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### findPlugInConfigs

    public PlugInConfig[] findPlugInConfigs()

Return the configured plug-in actions for this module. If there are none, a zero-length array is returned.

**Specified by:**  
` findPlugInConfigs` in interface `ModuleConfig`

------------------------------------------------------------------------

### freeze

    public void freeze()

Freeze the configuration of this module. After this method returns, any attempt to modify the configuration will return an IllegalStateException.

**Specified by:**  
` freeze` in interface `ModuleConfig`

**Overrides:**  
`freeze` in class `BaseConfig`

------------------------------------------------------------------------

### removeActionConfig

    public void removeActionConfig(ActionConfig config)

Remove the specified action configuration instance.

**Specified by:**  
` removeActionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - ActionConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeExceptionConfig

    public void removeExceptionConfig(ExceptionConfig config)

Remove the specified exception configuration instance.

**Specified by:**  
` removeExceptionConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - ActionConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeFormBeanConfig

    public void removeFormBeanConfig(FormBeanConfig config)

Remove the specified form bean configuration instance.

**Specified by:**  
` removeFormBeanConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - FormBeanConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeForwardConfig

    public void removeForwardConfig(ForwardConfig config)

Remove the specified forward configuration instance.

**Specified by:**  
` removeForwardConfig` in interface `ModuleConfig`

<!-- -->

**Parameters:**  
`config` - ForwardConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeMessageResourcesConfig

    public void removeMessageResourcesConfig(MessageResourcesConfig config)

Remove the specified message resources configuration instance.

**Specified by:**  
` removeMessageResourcesConfig` in interface `ModuleConfig`

<!-- -->

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ModuleConfigImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/config/impl/DefaultModuleConfigFactory.html.md" title="class in org.apache.struts.config.impl"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/config/impl/ModuleConfigImpl.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
