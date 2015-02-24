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
<td align="left"><a href="class-use/TestActionMessage.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/action/TestActionMessages.html.md" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionMessage.html"><strong>FRAMES</strong></a>    <a href="TestActionMessage.html"><strong>NO FRAMES</strong></a>    
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
 Class TestActionMessage
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.action.TestActionMessage

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestActionMessage

extends junit.framework.TestCase

Unit tests for the `org.apache.struts.action.ActionMessage` class.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-19 23:50:06 -0400 (Thu, 19 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ActionMessage`

` amNoResource`
            

`protected  ActionMessage`

` amWithArrayValues`
            

`protected  ActionMessage`

` amWithFourValues`
            

`protected  ActionMessage`

` amWithNoValue`
            

`protected  ActionMessage`

` amWithOneValue`
            

`protected  ActionMessage`

` amWithThreeValues`
            

`protected  ActionMessage`

` amWithTwoIntegerValues`
            

`protected  ActionMessage`

` amWithTwoValues`
            

`protected  Object[]`

` test_values`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                         |
|-------------------------------------------------|
| ` TestActionMessage(String theName)`            
            Defines the testcase name for JUnit.  |

  <span id="method_summary"></span>

**Method Summary**

`static void`

` main(String[] theArgs)`
           Start the tests.

` void`

` setUp()`
            

`static junit.framework.Test`

` suite()`
            

` void`

` tearDown()`
            

` void`

` testActionMessageWithArrayValues()`
            

` void`

` testActionMessageWithAStringValue()`
            

` void`

` testActionMessageWithFourValues()`
            

` void`

` testActionMessageWithNoValue()`
            

` void`

` testActionMessageWithThreeValues()`
            

` void`

` testActionMessageWithTwoValues()`
            

` void`

` testActionNoResource()`
            

` void`

` testActionWithTwoIntegers()`
            

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

<span id="amWithNoValue"></span>

### amWithNoValue

    protected ActionMessage amWithNoValue

------------------------------------------------------------------------

<span id="amWithOneValue"></span>

### amWithOneValue

    protected ActionMessage amWithOneValue

------------------------------------------------------------------------

<span id="amWithTwoValues"></span>

### amWithTwoValues

    protected ActionMessage amWithTwoValues

------------------------------------------------------------------------

<span id="amWithThreeValues"></span>

### amWithThreeValues

    protected ActionMessage amWithThreeValues

------------------------------------------------------------------------

<span id="amWithFourValues"></span>

### amWithFourValues

    protected ActionMessage amWithFourValues

------------------------------------------------------------------------

<span id="amWithArrayValues"></span>

### amWithArrayValues

    protected ActionMessage amWithArrayValues

------------------------------------------------------------------------

<span id="amWithTwoIntegerValues"></span>

### amWithTwoIntegerValues

    protected ActionMessage amWithTwoIntegerValues

------------------------------------------------------------------------

<span id="amNoResource"></span>

### amNoResource

    protected ActionMessage amNoResource

------------------------------------------------------------------------

<span id="test_values"></span>

### test\_values

    protected Object[] test_values

<span id="constructor_detail"></span>

**Constructor Detail**

### TestActionMessage

    public TestActionMessage(String theName)

Defines the testcase name for JUnit.

**Parameters:**  
`theName` - the testcase's name.

<span id="method_detail"></span>

**Method Detail**

### main

    public static void main(String[] theArgs)

Start the tests.

**Parameters:**  
`theArgs` - the arguments. Not used

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

**Returns:**  
a test suite (`TestSuite`) that includes all methods starting with "test"

------------------------------------------------------------------------

### setUp

    public void setUp()

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### testActionMessageWithNoValue

    public void testActionMessageWithNoValue()

------------------------------------------------------------------------

### testActionMessageWithAStringValue

    public void testActionMessageWithAStringValue()

------------------------------------------------------------------------

### testActionMessageWithTwoValues

    public void testActionMessageWithTwoValues()

------------------------------------------------------------------------

### testActionMessageWithThreeValues

    public void testActionMessageWithThreeValues()

------------------------------------------------------------------------

### testActionMessageWithFourValues

    public void testActionMessageWithFourValues()

------------------------------------------------------------------------

### testActionMessageWithArrayValues

    public void testActionMessageWithArrayValues()

------------------------------------------------------------------------

### testActionWithTwoIntegers

    public void testActionWithTwoIntegers()

------------------------------------------------------------------------

### testActionNoResource

    public void testActionNoResource()

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
<td align="left"><a href="class-use/TestActionMessage.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/action/TestActionMessages.html.md" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionMessage.html"><strong>FRAMES</strong></a>    <a href="TestActionMessage.html"><strong>NO FRAMES</strong></a>    
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
