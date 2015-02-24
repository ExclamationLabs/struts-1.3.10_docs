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
<td align="left"><a href="class-use/TestFormBeanConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestFormBeanConfig.CustomFormBeanConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestFormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="TestFormBeanConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class TestFormBeanConfig
-------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.config.TestFormBeanConfig

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestFormBeanConfig

extends junit.framework.TestCase

Unit tests for the `org.apache.struts.config.FormBeanConfig` class. Currently only contains code to test the methods that support configuration inheritance.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-25 19:35:00 -0400 (Wed, 25 May 2005) $

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

`static class`

`TestFormBeanConfig.CustomFormBeanConfig`
           Used to detect that FormBeanConfig is making the right calls.

  <span id="field_summary"></span>

**Field Summary**

`protected  FormBeanConfig`

` baseForm`
           The common base we'll use.

`protected  ModuleConfig`

` config`
           The ModuleConfig we'll use.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` TestFormBeanConfig(String name)`                     
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
           Basic check that shouldn't detect an error.

` void`

` testCheckCircularInheritanceError()`
           Basic check that SHOULD detect an error.

` void`

` testInheritFrom()`
           Test a typical form bean configuration extension where various properties should be inherited from a base form.

` void`

` testProcessExtendsBaseFormExtends()`
           Test that processExtends() makes sure that a base form's own extension has been processed.

` void`

` testProcessExtendsMissingBaseForm()`
           Make sure that correct exception is thrown if a base form can't be found.

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

<span id="baseForm"></span>

### baseForm

    protected FormBeanConfig baseForm

The common base we'll use.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestFormBeanConfig

    public TestFormBeanConfig(String name)

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

Basic check that shouldn't detect an error.

------------------------------------------------------------------------

### testCheckCircularInheritanceError

    public void testCheckCircularInheritanceError()

Basic check that SHOULD detect an error.

------------------------------------------------------------------------

### testProcessExtendsBaseFormExtends

    public void testProcessExtendsBaseFormExtends()
                                           throws Exception

Test that processExtends() makes sure that a base form's own extension has been processed.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsMissingBaseForm

    public void testProcessExtendsMissingBaseForm()
                                           throws Exception

Make sure that correct exception is thrown if a base form can't be found.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInheritFrom

    public void testInheritFrom()
                         throws Exception

Test a typical form bean configuration extension where various properties should be inherited from a base form. This method checks all the properties.

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
<td align="left"><a href="class-use/TestFormBeanConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestFormBeanConfig.CustomFormBeanConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestFormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="TestFormBeanConfig.html"><strong>NO FRAMES</strong></a>    
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
