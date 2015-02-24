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
<td align="left"><a href="class-use/TestActionServlet.CustomExceptionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionServlet.CustomActionConfig.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.CustomFormBeanConfig.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionServlet.CustomExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="TestActionServlet.CustomExceptionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class TestActionServlet.CustomExceptionConfig
----------------------------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ExceptionConfig
              org.apache.struts.action.TestActionServlet.CustomExceptionConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Enclosing class:**  
[TestActionServlet](../../../../org/apache/struts/action/TestActionServlet.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

    public static class TestActionServlet.CustomExceptionConfig

extends [ExceptionConfig](../../../../../apidocs/org/apache/struts/config/ExceptionConfig.html.md?is-external=true "class or interface in org.apache.struts.config")

Used for testing custom ExceptionConfig classes.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.TestActionServlet.CustomExceptionConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

` boolean`

` processExtendsCalled`
            

 <span id="fields_inherited_from_class_org.apache.struts.config.ExceptionConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ExceptionConfig](../../../../../apidocs/org/apache/struts/config/ExceptionConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bundle, extensionProcessed, handler, inherit, key, path, scope, type`                                                                                                                                             |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../../apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**                      |
|----------------------------------------------|
| ` TestActionServlet.CustomExceptionConfig()` 
                                               |

  <span id="method_summary"></span>

**Method Summary**

` void`

` processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Set a flag so we know this method was called.

 <span id="methods_inherited_from_class_org.apache.struts.config.ExceptionConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ExceptionConfig](../../../../../apidocs/org/apache/struts/config/ExceptionConfig.html.md?is-external=true "class or interface in org.apache.struts.config")**   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `checkCircularInheritance, getBundle, getExtends, getHandler, getKey, getPath, getScope, getType, inheritFrom, isExtensionProcessed, setBundle, setExtends, setHandler, setKey, setPath, setScope, setType, toString` |

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../../apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `copyProperties, freeze, getProperties, getProperty, inheritProperties, setProperties, setProperty, throwIfConfigured`                                                                                    |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="processExtendsCalled"></span>

### processExtendsCalled

    public boolean processExtendsCalled

<span id="constructor_detail"></span>

**Constructor Detail**

### TestActionServlet.CustomExceptionConfig

    public TestActionServlet.CustomExceptionConfig()

<span id="method_detail"></span>

**Method Detail**

### processExtends

    public void processExtends(ModuleConfig moduleConfig,
                               ActionConfig actionConfig)
                        throws ClassNotFoundException,
                               IllegalAccessException,
                               InstantiationException

Set a flag so we know this method was called.

**Overrides:**  
`processExtends` in class `ExceptionConfig`

<!-- -->

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

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
<td align="left"><a href="class-use/TestActionServlet.CustomExceptionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionServlet.CustomActionConfig.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.CustomFormBeanConfig.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionServlet.CustomExceptionConfig.html"><strong>FRAMES</strong></a>    <a href="TestActionServlet.CustomExceptionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
