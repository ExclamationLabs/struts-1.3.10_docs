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
<td align="left"><a href="class-use/CustomActionMapping.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/examples/CustomActionForward.html.md" title="class in org.apache.struts.webapp.examples"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/examples/CustomFormBean.html" title="class in org.apache.struts.webapp.examples"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/examples/CustomActionMapping.html"><strong>FRAMES</strong></a>    <a href="CustomActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ActionConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.examples
 Class CustomActionMapping
---------------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ActionConfig
              org.apache.struts.action.ActionMapping
                  org.apache.struts.webapp.examples.CustomActionMapping

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class CustomActionMapping

extends [ActionMapping](http://struts.apache.org/apidocs/org/apache/struts/action/ActionMapping.html.md?is-external=true "class or interface in org.apache.struts.action")

Custom ActionMapping to demonstrate usage.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.examples.CustomActionMapping)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.ActionConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ActionConfig](http://struts.apache.org/apidocs/org/apache/struts/config/ActionConfig.html.md?is-external=true "class or interface in org.apache.struts.config")**                                  |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `actionId, attribute, cancellable, catalog, command, exceptions, extensionProcessed, forward, forwards, include, inherit, input, moduleConfig, multipartClass, name, parameter, path, prefix, roleNames, roles, scope, suffix, type, unknown, validate` |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](http://struts.apache.org/apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                                                                       |

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` CustomActionMapping()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getExample()`
           Return the example String.

` void`

` setExample(String example)`
           Set the example String.

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionMapping"></span>

| **Methods inherited from class org.apache.struts.action.[ActionMapping](http://struts.apache.org/apidocs/org/apache/struts/action/ActionMapping.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `findForward, findForwards, getInputForward`                                                                                                                                                                              |

 <span id="methods_inherited_from_class_org.apache.struts.config.ActionConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ActionConfig](http://struts.apache.org/apidocs/org/apache/struts/config/ActionConfig.html.md?is-external=true "class or interface in org.apache.struts.config")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addExceptionConfig, addForwardConfig, checkCircularInheritance, findException, findExceptionConfig, findExceptionConfigs, findForwardConfig, findForwardConfigs, freeze, getActionId, getAttribute, getCancellable, getCatalog, getCommand, getExtends, getForward, getInclude, getInput, getModuleConfig, getMultipartClass, getName, getParameter, getPath, getPrefix, getRoleNames, getRoles, getScope, getSuffix, getType, getUnknown, getValidate, inheritExceptionHandlers, inheritForwards, inheritFrom, isExtensionProcessed, processExtends, removeExceptionConfig, removeForwardConfig, setActionId, setAttribute, setCancellable, setCatalog, setCommand, setExtends, setForward, setInclude, setInput, setModuleConfig, setMultipartClass, setName, setParameter, setPath, setPrefix, setRoles, setScope, setSuffix, setType, setUnknown, setValidate, toString` |

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](http://struts.apache.org/apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `copyProperties, getProperties, getProperty, inheritProperties, setProperties, setProperty, throwIfConfigured`                                                                                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### CustomActionMapping

    public CustomActionMapping()

<span id="method_detail"></span>

**Method Detail**

### getExample

    public String getExample()

Return the example String.

------------------------------------------------------------------------

### setExample

    public void setExample(String example)

Set the example String.

**Parameters:**  
`example` - The new example String.

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
<td align="left"><a href="class-use/CustomActionMapping.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/examples/CustomActionForward.html.md" title="class in org.apache.struts.webapp.examples"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/examples/CustomFormBean.html" title="class in org.apache.struts.webapp.examples"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/examples/CustomActionMapping.html"><strong>FRAMES</strong></a>    <a href="CustomActionMapping.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
