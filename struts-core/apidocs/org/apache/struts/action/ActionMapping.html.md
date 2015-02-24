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
<td align="left"><a href="class-use/ActionMapping.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMessage.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMapping.html"><strong>FRAMES</strong></a>    <a href="ActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ActionConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class ActionMapping
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ActionConfig
              org.apache.struts.action.ActionMapping

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[RequestActionMapping](../../../../org/apache/struts/action/RequestActionMapping.html.md "class in org.apache.struts.action"), [SessionActionMapping](../../../../org/apache/struts/action/SessionActionMapping.html "class in org.apache.struts.action")

------------------------------------------------------------------------

    public class ActionMapping

extends [ActionConfig](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")

An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class. The `ActionMapping` instance used to select a particular `Action` is passed on to that `Action`, thereby providing access to any custom configuration information included with the `ActionMapping` object.

Since Struts 1.1 this class extends `ActionConfig`.

**NOTE** - This class would have been deprecated and replaced by `org.apache.struts.config.ActionConfig` except for the fact that it is part of the public API that existing applications are using.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-26 21:58:39 -0400 (Fri, 26 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionMapping)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.ActionConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ActionConfig](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")**                                                                                          |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `actionId, attribute,  cancellable, catalog, command,  exceptions,  extensionProcessed, forward, forwards, include, inherit, input,  moduleConfig,  multipartClass, name, parameter, path, prefix, roleNames, roles, scope, suffix, type, unknown, validate` |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ActionMapping()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` findForward(String forwardName)`
           Find and return the `ForwardConfig` instance defining how forwarding to the specified logical name should be handled.

` String[]`

` findForwards()`
           Return the logical names of all locally defined forwards for this mapping.

` ActionForward`

` getInputForward()`
           Create (if necessary) and return an [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") that corresponds to the `input` property of this Action.

 <span id="methods_inherited_from_class_org.apache.struts.config.ActionConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ActionConfig](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addExceptionConfig,  addForwardConfig,  checkCircularInheritance,  findException,  findExceptionConfig,  findExceptionConfigs,  findForwardConfig,  findForwardConfigs, freeze,  getActionId,  getAttribute,  getCancellable,  getCatalog,  getCommand,  getExtends,  getForward,  getInclude,  getInput,  getModuleConfig,  getMultipartClass, getName,  getParameter, getPath,  getPrefix,  getRoleNames,  getRoles,  getScope,  getSuffix, getType,  getUnknown,  getValidate,  inheritExceptionHandlers,  inheritForwards,  inheritFrom,  isExtensionProcessed,  processExtends,  removeExceptionConfig,  removeForwardConfig,  setActionId,  setAttribute,  setCancellable,  setCatalog,  setCommand,  setExtends,  setForward,  setInclude,  setInput,  setModuleConfig,  setMultipartClass,  setName,  setParameter,  setPath,  setPrefix,  setRoles,  setScope,  setSuffix,  setType,  setUnknown,  setValidate,  toString` |

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                            |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionMapping

    public ActionMapping()

<span id="method_detail"></span>

**Method Detail**

### findForward

    public ActionForward findForward(String forwardName)

Find and return the `ForwardConfig` instance defining how forwarding to the specified logical name should be handled. This is performed by checking local and then global configurations for the specified forwarding configuration. If no forwarding configuration can be found, return `null`.

**Parameters:**  
`forwardName` - Logical name of the forwarding instance to be returned

**Returns:**  
The local or global forward with the specified name.

------------------------------------------------------------------------

### findForwards

    public String[] findForwards()

Return the logical names of all locally defined forwards for this mapping. If there are no such forwards, a zero-length array is returned.

**Returns:**  
The forward names for this action mapping.

------------------------------------------------------------------------

### getInputForward

    public ActionForward getInputForward()

Create (if necessary) and return an [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") that corresponds to the `input` property of this Action.

**Returns:**  
The input forward for this action mapping.

**Since:**  
Struts 1.1

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
<td align="left"><a href="class-use/ActionMapping.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionForward.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMessage.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionMapping.html"><strong>FRAMES</strong></a>    <a href="ActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ActionConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
