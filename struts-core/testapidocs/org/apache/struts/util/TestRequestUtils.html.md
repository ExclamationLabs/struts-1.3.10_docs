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
<td align="left"><a href="class-use/TestRequestUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/TestPropertyMessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/TestRequestUtilsPopulate.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/TestRequestUtils.html"><strong>FRAMES</strong></a>    <a href="TestRequestUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.mock.TestMockBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class TestRequestUtils
-----------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.mock.TestMockBase
                  org.apache.struts.util.TestRequestUtils

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestRequestUtils

extends [TestMockBase](../../../../../apidocs/org/apache/struts/mock/TestMockBase.html.md?is-external=true "class or interface in org.apache.struts.mock")

Unit tests for `org.apache.struts.util.RequestUtils`.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.mock.TestMockBase"></span>

| **Fields inherited from class org.apache.struts.mock.[TestMockBase](../../../../../apidocs/org/apache/struts/mock/TestMockBase.html.md?is-external=true "class or interface in org.apache.struts.mock")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `config, context, moduleConfig, moduleConfig2, moduleConfig3, page, principal, request, response, session`                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**          |
|----------------------------------|
| ` TestRequestUtils(String name)` 
                                   |

  <span id="method_summary"></span>

**Method Summary**

`static void`

` main(String[] args)`
            

` void`

`setUp()`
            

`static junit.framework.Test`

`suite()`
            

` void`

` tearDown()`
            

` void`

` testAbsoluteURL()`
            

` void`

` testActionURL1()`
            

` void`

` testActionURL2()`
            

` void`

` testActionURL3()`
            

` void`

` testCreateActionForm1a()`
            

` void`

` testCreateActionForm1b()`
            

` void`

` testCreateActionForm2a()`
            

` void`

` testCreateActionForm2b()`
            

` void`

` testCreateActionForm3a()`
            

` void`

` testCreateActionForm3b()`
            

` void`

` testCreateActionForm4a()`
            

` void`

` testForwardURL1()`
            

` void`

` testForwardURL2()`
            

` void`

` testForwardURL3()`
            

` void`

` testForwardURLa()`
            

` void`

` testRequestURL()`
            

` void`

` testSelectApplication1a()`
            

` void`

` testSelectApplication1b()`
            

` void`

` testSelectApplication2a()`
            

` void`

` testSelectApplication2b()`
            

` void`

` testServerURL()`
            

 <span id="methods_inherited_from_class_org.apache.struts.mock.TestMockBase"></span>

| **Methods inherited from class org.apache.struts.mock.[TestMockBase](../../../../../apidocs/org/apache/struts/mock/TestMockBase.html.md?is-external=true "class or interface in org.apache.struts.mock")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `setUpDefaultApp, setUpSecondApp, setUpThirdApp, testUtilBaseEnvironment`                                                                                                                               |

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

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TestRequestUtils

    public TestRequestUtils(String name)

<span id="method_detail"></span>

**Method Detail**

### main

    public static void main(String[] args)

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

------------------------------------------------------------------------

### setUp

    public void setUp()

**Overrides:**  
`setUp` in class `TestMockBase`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
`tearDown` in class `TestMockBase`

------------------------------------------------------------------------

### testAbsoluteURL

    public void testAbsoluteURL()

------------------------------------------------------------------------

### testActionURL1

    public void testActionURL1()

------------------------------------------------------------------------

### testActionURL2

    public void testActionURL2()

------------------------------------------------------------------------

### testActionURL3

    public void testActionURL3()

------------------------------------------------------------------------

### testCreateActionForm1a

    public void testCreateActionForm1a()

------------------------------------------------------------------------

### testCreateActionForm1b

    public void testCreateActionForm1b()

------------------------------------------------------------------------

### testCreateActionForm2a

    public void testCreateActionForm2a()

------------------------------------------------------------------------

### testCreateActionForm2b

    public void testCreateActionForm2b()

------------------------------------------------------------------------

### testCreateActionForm3a

    public void testCreateActionForm3a()

------------------------------------------------------------------------

### testCreateActionForm3b

    public void testCreateActionForm3b()

------------------------------------------------------------------------

### testCreateActionForm4a

    public void testCreateActionForm4a()

------------------------------------------------------------------------

### testForwardURL1

    public void testForwardURL1()

------------------------------------------------------------------------

### testForwardURL2

    public void testForwardURL2()

------------------------------------------------------------------------

### testForwardURL3

    public void testForwardURL3()

------------------------------------------------------------------------

### testForwardURLa

    public void testForwardURLa()

------------------------------------------------------------------------

### testRequestURL

    public void testRequestURL()

------------------------------------------------------------------------

### testSelectApplication1a

    public void testSelectApplication1a()

------------------------------------------------------------------------

### testSelectApplication1b

    public void testSelectApplication1b()

------------------------------------------------------------------------

### testSelectApplication2a

    public void testSelectApplication2a()

------------------------------------------------------------------------

### testSelectApplication2b

    public void testSelectApplication2b()

------------------------------------------------------------------------

### testServerURL

    public void testServerURL()

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
<td align="left"><a href="class-use/TestRequestUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/TestPropertyMessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/TestRequestUtilsPopulate.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/TestRequestUtils.html"><strong>FRAMES</strong></a>    <a href="TestRequestUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.mock.TestMockBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
