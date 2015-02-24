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
<td align="left"><a href="class-use/ConfigRuleSet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigHelperInterface.html.md" title="interface in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ControllerConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigRuleSet.html"><strong>FRAMES</strong></a>    <a href="ConfigRuleSet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.commons.digester.RuleSetBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config
 Class ConfigRuleSet
------------------------

    java.lang.Object
      org.apache.commons.digester.RuleSetBase
          org.apache.struts.config.ConfigRuleSet

**All Implemented Interfaces:**  
org.apache.commons.digester.RuleSet

------------------------------------------------------------------------

    public class ConfigRuleSet

extends org.apache.commons.digester.RuleSetBase

The set of Digester rules required to parse a Struts configuration file (`struts-config.xml`).

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-08-16 15:53:27 -0400 (Tue, 16 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.digester.RuleSetBase"></span>

| **Fields inherited from class org.apache.commons.digester.RuleSetBase** |
|-------------------------------------------------------------------------|
| `namespaceURI`                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ConfigRuleSet()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addRuleInstances(org.apache.commons.digester.Digester digester)`
           Add the set of Rule instances defined in this RuleSet to the specified `Digester` instance, associating them with our namespace URI (if any).

 <span id="methods_inherited_from_class_org.apache.commons.digester.RuleSetBase"></span>

| **Methods inherited from class org.apache.commons.digester.RuleSetBase** |
|--------------------------------------------------------------------------|
| `getNamespaceURI`                                                        |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ConfigRuleSet

    public ConfigRuleSet()

<span id="method_detail"></span>

**Method Detail**

### addRuleInstances

    public void addRuleInstances(org.apache.commons.digester.Digester digester)

Add the set of Rule instances defined in this RuleSet to the specified `Digester` instance, associating them with our namespace URI (if any). This method should only be called by a Digester instance. These rules assume that an instance of `org.apache.struts.config.ModuleConfig` is pushed onto the evaluation stack before parsing begins.

**Specified by:**  
`addRuleInstances` in interface `org.apache.commons.digester.RuleSet`

**Specified by:**  
`addRuleInstances` in class `org.apache.commons.digester.RuleSetBase`

<!-- -->

**Parameters:**  
`digester` - Digester instance to which the new Rule instances should be added.

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
<td align="left"><a href="class-use/ConfigRuleSet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigHelperInterface.html.md" title="interface in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ControllerConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigRuleSet.html"><strong>FRAMES</strong></a>    <a href="ConfigRuleSet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.commons.digester.RuleSetBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
