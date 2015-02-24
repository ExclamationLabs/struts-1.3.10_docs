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
<td align="left"><a href="class-use/TestModuleConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestForwardConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestModuleConfig.html"><strong>FRAMES</strong></a>    <a href="TestModuleConfig.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class TestModuleConfig
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.config.TestModuleConfig

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestModuleConfig

extends junit.framework.TestCase

Unit tests for the `org.apache.struts.config` package.

**Version:**  
$Rev: 471754 $ $Date: 2005-03-01 20:26:14 -0500 (Tue, 01 Mar 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ModuleConfig`

` config`
           The ModuleConfig we are testing.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` TestModuleConfig(String name)`                       
            Construct a new instance of this test case.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` setUp()`
           Set up instance variables required by this test case.

`static junit.framework.Test`

` suite()`
           Return the tests included in this test suite.

` void`

` tearDown()`
           Tear down instance variables required by this test case.

` void`

` testCustomMappingParse()`
           Tests a struts-config.xml that contains a custom mapping and property.

` void`

` testCustomMappingParse1_1()`
           Tests a struts-config.xml that contains a custom mapping and property.

` void`

` testParse()`
           Test parsing of a struts-config.xml file.

` void`

` testParse1_1()`
            

` void`

` testParseBase(String publicId, String entityURL, String strutsConfig)`
            

` void`

` testPreserveActionMappingsOrder()`
           Test order of action mappings defined perserved.

 <span id="methods_inherited_from_class_junit.framework.TestCase"></span>

| **Methods inherited from class junit.framework.TestCase**                              |
|----------------------------------------------------------------------------------------|
| `countTestCases, createResult, getName, run, run, runBare, runTest, setName, toString` |

 <span id="methods_inherited_from_class_junit.framework.Assert"></span>

| **Methods inherited from class junit.framework.Assert**                                                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertFalse, assertFalse, assertNotNull, assertNotNull, assertNotSame, assertNotSame, assertNull, assertNull, assertSame, assertSame, assertTrue, assertTrue, fail, fail` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="config"></span>

### config

    protected ModuleConfig config

The ModuleConfig we are testing.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestModuleConfig

    public TestModuleConfig(String name)

Construct a new instance of this test case.

**Parameters:**  
`name` - Name of the test case

<span id="method_detail"></span>

**Method Detail**

### setUp

    public void setUp()

Set up instance variables required by this test case.

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

Return the tests included in this test suite.

------------------------------------------------------------------------

### tearDown

    public void tearDown()

Tear down instance variables required by this test case.

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### testParse

    public void testParse()

Test parsing of a struts-config.xml file.

------------------------------------------------------------------------

### testParse1\_1

    public void testParse1_1()

------------------------------------------------------------------------

### testParseBase

    public void testParseBase(String publicId,
                              String entityURL,
                              String strutsConfig)

------------------------------------------------------------------------

### testCustomMappingParse

    public void testCustomMappingParse()

Tests a struts-config.xml that contains a custom mapping and property.

------------------------------------------------------------------------

### testCustomMappingParse1\_1

    public void testCustomMappingParse1_1()

Tests a struts-config.xml that contains a custom mapping and property.

------------------------------------------------------------------------

### testPreserveActionMappingsOrder

    public void testPreserveActionMappingsOrder()

Test order of action mappings defined perserved.

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
<td align="left"><a href="class-use/TestModuleConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestForwardConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestModuleConfig.html"><strong>FRAMES</strong></a>    <a href="TestModuleConfig.html"><strong>NO FRAMES</strong></a>    
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
