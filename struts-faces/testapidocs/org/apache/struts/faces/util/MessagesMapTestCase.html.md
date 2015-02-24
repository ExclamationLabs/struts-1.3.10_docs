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
<td align="left"><a href="../../../../../org/apache/struts/faces/util/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MessagesMapTestCase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/MessagesMapTestCase.html"><strong>FRAMES</strong></a>    <a href="MessagesMapTestCase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.util
 Class MessagesMapTestCase
----------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.faces.util.MessagesMapTestCase

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class MessagesMapTestCase

extends junit.framework.TestCase

Unit tests for `MessagesMap`.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  org.apache.struts.faces.util.MessagesMap`

` map`
           The `MessagesMap` instance to be tested.

`protected  MessageResources`

` resources`
           The `MessageResources` instance containing the messages used for testing.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` MessagesMapTestCase(String name)`                    
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

` teaDown()`
           Tear down instance variables required by this test case.

` void`

` testContainsKey()`
           Test the `containsKey()` method.

` void`

` testGet()`
           Test the `get()` method.

` void`

` testPristine()`
           Test a pristine instance, and all unsupported methods.

 <span id="methods_inherited_from_class_junit.framework.TestCase"></span>

| **Methods inherited from class junit.framework.TestCase**                                        |
|--------------------------------------------------------------------------------------------------|
| `countTestCases, createResult, getName, run, run, runBare, runTest, setName, tearDown, toString` |

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

<span id="map"></span>

### map

    protected org.apache.struts.faces.util.MessagesMap map

The `MessagesMap` instance to be tested.

------------------------------------------------------------------------

<span id="resources"></span>

### resources

    protected MessageResources resources

The `MessageResources` instance containing the messages used for testing.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessagesMapTestCase

    public MessagesMapTestCase(String name)

Construct a new instance of this test case.

**Parameters:**  
`name` - Name of the test case

<span id="method_detail"></span>

**Method Detail**

### setUp

    public void setUp()
               throws Exception

Set up instance variables required by this test case.

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

<!-- -->

**Throws:**  
`Exception`

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

Return the tests included in this test suite.

------------------------------------------------------------------------

### teaDown

    public void teaDown()
                 throws Exception

Tear down instance variables required by this test case.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testContainsKey

    public void testContainsKey()
                         throws Exception

Test the `containsKey()` method.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testGet

    public void testGet()
                 throws Exception

Test the `get()` method.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testPristine

    public void testPristine()
                      throws Exception

Test a pristine instance, and all unsupported methods.

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
<td align="left"><a href="../../../../../org/apache/struts/faces/util/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MessagesMapTestCase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/util/MessagesMapTestCase.html"><strong>FRAMES</strong></a>    <a href="MessagesMapTestCase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
