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
<td align="left"><a href="class-use/TestMockBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockServletContext.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/TestMockBase.html"><strong>FRAMES</strong></a>    <a href="TestMockBase.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.mock
 Class TestMockBase
----------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.mock.TestMockBase

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestMockBase

extends junit.framework.TestCase

Convenience base class for unit tests of the `org.apache.struts.util` package, and others that require a runtime environment similar to what the Struts controller servlet sets up. The `setUp()` method establishes a consistent basic environment for the various tests. The only tests included in this class are simple validations that the basic environment was set up correctly.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  MockServletConfig`

`config`
            

`protected  MockServletContext`

`context`
            

`protected  ModuleConfig`

` moduleConfig`
            

`protected  ModuleConfig`

` moduleConfig2`
            

`protected  ModuleConfig`

` moduleConfig3`
            

`protected  MockPageContext`

`page`
            

`protected  MockPrincipal`

`principal`
            

`protected  MockHttpServletRequest`

`request`
            

`protected  MockHttpServletResponse`

`response`
            

`protected  MockHttpSession`

`session`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` TestMockBase(String name)` 
                               |

  <span id="method_summary"></span>

**Method Summary**

`static void`

` main(String[] args)`
            

` void`

`setUp()`
            

`protected  void`

` setUpDefaultApp()`
            

`protected  void`

` setUpSecondApp()`
            

`protected  void`

` setUpThirdApp()`
            

`static junit.framework.Test`

`suite()`
            

` void`

`tearDown()`
            

` void`

` testUtilBaseEnvironment()`
            

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

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

------------------------------------------------------------------------

<span id="moduleConfig2"></span>

### moduleConfig2

    protected ModuleConfig moduleConfig2

------------------------------------------------------------------------

<span id="moduleConfig3"></span>

### moduleConfig3

    protected ModuleConfig moduleConfig3

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected MockServletConfig config

------------------------------------------------------------------------

<span id="context"></span>

### context

    protected MockServletContext context

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected MockPageContext page

------------------------------------------------------------------------

<span id="principal"></span>

### principal

    protected MockPrincipal principal

------------------------------------------------------------------------

<span id="request"></span>

### request

    protected MockHttpServletRequest request

------------------------------------------------------------------------

<span id="response"></span>

### response

    protected MockHttpServletResponse response

------------------------------------------------------------------------

<span id="session"></span>

### session

    protected MockHttpSession session

<span id="constructor_detail"></span>

**Constructor Detail**

### TestMockBase

    public TestMockBase(String name)

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
`setUp` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### setUpDefaultApp

    protected void setUpDefaultApp()

------------------------------------------------------------------------

### setUpSecondApp

    protected void setUpSecondApp()

------------------------------------------------------------------------

### setUpThirdApp

    protected void setUpThirdApp()

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### testUtilBaseEnvironment

    public void testUtilBaseEnvironment()

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
<td align="left"><a href="class-use/TestMockBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockServletContext.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/TestMockBase.html"><strong>FRAMES</strong></a>    <a href="TestMockBase.html"><strong>NO FRAMES</strong></a>    
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
