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
<td align="left"><a href="class-use/ActionFormBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionForm.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionFormBean.html"><strong>FRAMES</strong></a>    <a href="ActionFormBean.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.FormBeanConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.config.FormBeanConfig">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class ActionFormBean
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.FormBeanConfig
              org.apache.struts.action.ActionFormBean

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ActionFormBean

extends [FormBeanConfig](../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config")

An **ActionFormBean** is the definition of a form bean that is loaded from a `<form-bean>` element in the Struts configuration file. It can be subclassed as necessary to add additional properties.

Since Struts 1.1 `ActionFormBean` extends `FormBeanConfig`.

**NOTE** - This class would have been deprecated and replaced by `org.apache.struts.config.FormBeanConfig` except for the fact that it is part of the public API that existing applications are using.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionFormBean)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.FormBeanConfig"></span>

| **Fields inherited from class org.apache.struts.config.[FormBeanConfig](../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` dynaActionFormClass, dynamic,  extensionProcessed,  formProperties, inherit, lock, name,  restricted, type`                                                           |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                     |
|-------------------------------------------------------------|
| ` ActionFormBean()`                                         
            Construct an instance with default vaslues.       |
| ` ActionFormBean(String name, String type)`                 
            Construct an instance with the specified values.  |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_org.apache.struts.config.FormBeanConfig"></span>

| **Methods inherited from class org.apache.struts.config.[FormBeanConfig](../../../../org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config")**                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addFormPropertyConfig,  canReuse,  checkCircularInheritance,  createActionForm,  createActionForm,  findFormPropertyConfig,  findFormPropertyConfigs,  formBeanClass,  freeze,  getDynaActionFormClass,  getDynamic,  getExtends,  getName,  getType,  inheritFormProperties,  inheritFrom,  isExtensionProcessed,  isRestricted,  processExtends,  removeFormPropertyConfig,  setExtends,  setName,  setRestricted,  setType,  toString` |

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

### ActionFormBean

    public ActionFormBean()

Construct an instance with default vaslues.

------------------------------------------------------------------------

### ActionFormBean

    public ActionFormBean(String name,
                          String type)

Construct an instance with the specified values.

**Parameters:**  
`name` - Form bean name

`type` - Fully qualified class name

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
<td align="left"><a href="class-use/ActionFormBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionForm.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionFormBean.html"><strong>FRAMES</strong></a>    <a href="ActionFormBean.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.FormBeanConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.config.FormBeanConfig">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
