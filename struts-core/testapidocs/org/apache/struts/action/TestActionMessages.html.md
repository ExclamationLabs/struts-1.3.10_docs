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
<td align="left"><a href="class-use/TestActionMessages.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionMessage.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionRedirect.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionMessages.html"><strong>FRAMES</strong></a>    <a href="TestActionMessages.html"><strong>NO FRAMES</strong></a>    
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
 Class TestActionMessages
-------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.action.TestActionMessages

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestActionMessages

extends junit.framework.TestCase

Unit tests for the `org.apache.struts.action.ActionMessages` class.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:09:25 -0400 (Sat, 16 Oct 2004) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ActionMessages`

` aMsgs`
            

`protected  ActionMessages`

` anMsgs`
            

`protected  ActionMessage`

` msg1`
            

`protected  ActionMessage`

` msg2`
            

`protected  ActionMessage`

` msg3`
            

`protected  ActionMessage`

` msg4`
            

`protected  ActionMessage`

` msg5`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                         |
|-------------------------------------------------|
| ` TestActionMessages(String theName)`           
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

` testAddMessages()`
           Tests adding an ActionMessages object to an ActionMessages object.

` void`

` testEmpty()`
            

` void`

` testGetForAProperty()`
            

` void`

` testGetWithNoProperty()`
            

` void`

` testNotEmpty()`
            

` void`

` testSizeAndEmptyAfterClear()`
            

` void`

` testSizeWithManyProperties()`
            

` void`

` testSizeWithOneProperty()`
            

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

<span id="aMsgs"></span>

### aMsgs

    protected ActionMessages aMsgs

------------------------------------------------------------------------

<span id="anMsgs"></span>

### anMsgs

    protected ActionMessages anMsgs

------------------------------------------------------------------------

<span id="msg1"></span>

### msg1

    protected ActionMessage msg1

------------------------------------------------------------------------

<span id="msg2"></span>

### msg2

    protected ActionMessage msg2

------------------------------------------------------------------------

<span id="msg3"></span>

### msg3

    protected ActionMessage msg3

------------------------------------------------------------------------

<span id="msg4"></span>

### msg4

    protected ActionMessage msg4

------------------------------------------------------------------------

<span id="msg5"></span>

### msg5

    protected ActionMessage msg5

<span id="constructor_detail"></span>

**Constructor Detail**

### TestActionMessages

    public TestActionMessages(String theName)

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

### testEmpty

    public void testEmpty()

------------------------------------------------------------------------

### testNotEmpty

    public void testNotEmpty()

------------------------------------------------------------------------

### testSizeWithOneProperty

    public void testSizeWithOneProperty()

------------------------------------------------------------------------

### testSizeWithManyProperties

    public void testSizeWithManyProperties()

------------------------------------------------------------------------

### testSizeAndEmptyAfterClear

    public void testSizeAndEmptyAfterClear()

------------------------------------------------------------------------

### testGetWithNoProperty

    public void testGetWithNoProperty()

------------------------------------------------------------------------

### testGetForAProperty

    public void testGetForAProperty()

------------------------------------------------------------------------

### testAddMessages

    public void testAddMessages()

Tests adding an ActionMessages object to an ActionMessages object.

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
<td align="left"><a href="class-use/TestActionMessages.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionMessage.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionRedirect.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionMessages.html"><strong>FRAMES</strong></a>    <a href="TestActionMessages.html"><strong>NO FRAMES</strong></a>    
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
