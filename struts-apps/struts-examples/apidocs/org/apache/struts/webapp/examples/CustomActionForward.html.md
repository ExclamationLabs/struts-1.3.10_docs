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
<td align="left"><a href="class-use/CustomActionForward.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/examples/CustomActionForm.html.md" title="class in org.apache.struts.webapp.examples"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/examples/CustomActionMapping.html" title="class in org.apache.struts.webapp.examples"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/examples/CustomActionForward.html"><strong>FRAMES</strong></a>    <a href="CustomActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ForwardConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.examples
 Class CustomActionForward
---------------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ForwardConfig
              org.apache.struts.action.ActionForward
                  org.apache.struts.webapp.examples.CustomActionForward

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class CustomActionForward

extends [ActionForward](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForward.html.md?is-external=true "class or interface in org.apache.struts.action")

Custom ActionForward to demonstrate usage.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.examples.CustomActionForward)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ForwardConfig](http://struts.apache.org/apidocs/org/apache/struts/config/ForwardConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `catalog, command, extensionProcessed, inherit, module, name, path, redirect`                                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](http://struts.apache.org/apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                                                                       |

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` CustomActionForward()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getExample()`
           Return the example String.

` void`

` setExample(String example)`
           Set the example String.

 <span id="methods_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ForwardConfig](http://struts.apache.org/apidocs/org/apache/struts/config/ForwardConfig.html.md?is-external=true "class or interface in org.apache.struts.config")**                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `checkCircularInheritance, getCatalog, getCommand, getExtends, getModule, getName, getPath, getRedirect, inheritFrom, isExtensionProcessed, processExtends, setCatalog, setCommand, setExtends, setModule, setName, setPath, setRedirect, toString` |

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](http://struts.apache.org/apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `copyProperties, freeze, getProperties, getProperty, inheritProperties, setProperties, setProperty, throwIfConfigured`                                                                                              |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### CustomActionForward

    public CustomActionForward()

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
<td align="left"><a href="class-use/CustomActionForward.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/examples/CustomActionForm.html.md" title="class in org.apache.struts.webapp.examples"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/examples/CustomActionMapping.html" title="class in org.apache.struts.webapp.examples"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/examples/CustomActionForward.html"><strong>FRAMES</strong></a>    <a href="CustomActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ForwardConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
