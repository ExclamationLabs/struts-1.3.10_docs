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
<td align="left"><a href="class-use/TestActionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/CustomMappingTest.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestActionConfig.CustomActionConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestActionConfig.html"><strong>FRAMES</strong></a>    <a href="TestActionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config
 Class TestActionConfig
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.config.TestActionConfig

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestActionConfig

extends junit.framework.TestCase

Unit tests for the `org.apache.struts.config.ActionConfig` class. Currently only contains code to test the methods that support configuration inheritance.

**Version:**  
$Rev: 480593 $ $Date: 2005-05-25 19:35:00 -0400 (Wed, 25 May 2005) $

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

`static class`

`TestActionConfig.CustomActionConfig`
           Used to detect that ActionConfig is making the right calls.

  <span id="field_summary"></span>

**Field Summary**

`protected  ActionConfig`

` baseConfig`
           The common base we'll use.

`protected  ModuleConfig`

` config`
           The ModuleConfig we'll use.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` TestActionConfig(String name)`                       
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

` testCheckCircularInheritance()`
           Basic check that shouldn't detect circular inheritance.

` void`

` testCheckCircularInheritanceError()`
           Basic check that should detect circular inheritance.

` void`

` testInheritBoolean()`
           Make sure that correct exception is thrown if a base action can't be found.

` void`

` testInheritFrom()`
           Test a typical form bean configuration extension where various forwards and exception handlers should be inherited from a base form.

` void`

` testProcessExtendsActionExtends()`
           Test that processExtends() makes sure that a base action's own extension has been processed.

` void`

` testProcessExtendsMissingAction()`
           Make sure that correct exception is thrown if a base action can't be found.

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

The ModuleConfig we'll use.

------------------------------------------------------------------------

<span id="baseConfig"></span>

### baseConfig

    protected ActionConfig baseConfig

The common base we'll use.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestActionConfig

    public TestActionConfig(String name)

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

### testCheckCircularInheritance

    public void testCheckCircularInheritance()

Basic check that shouldn't detect circular inheritance.

------------------------------------------------------------------------

### testCheckCircularInheritanceError

    public void testCheckCircularInheritanceError()

Basic check that should detect circular inheritance.

------------------------------------------------------------------------

### testProcessExtendsActionExtends

    public void testProcessExtendsActionExtends()
                                         throws Exception

Test that processExtends() makes sure that a base action's own extension has been processed.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsMissingAction

    public void testProcessExtendsMissingAction()
                                         throws Exception

Make sure that correct exception is thrown if a base action can't be found.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInheritFrom

    public void testInheritFrom()
                         throws Exception

Test a typical form bean configuration extension where various forwards and exception handlers should be inherited from a base form. This method checks all the subelements.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInheritBoolean

    public void testInheritBoolean()
                            throws Exception

Make sure that correct exception is thrown if a base action can't be found.

**Throws:**  
`Exception`

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
<td align="left"><a href="class-use/TestActionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/CustomMappingTest.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestActionConfig.CustomActionConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestActionConfig.html"><strong>FRAMES</strong></a>    <a href="TestActionConfig.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
