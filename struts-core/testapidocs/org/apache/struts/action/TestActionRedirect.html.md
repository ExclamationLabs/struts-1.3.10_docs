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
<td align="left"><a href="class-use/TestActionRedirect.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionMessages.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionRedirect.html"><strong>FRAMES</strong></a>    <a href="TestActionRedirect.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class TestActionRedirect
-------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.action.TestActionRedirect

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestActionRedirect

extends junit.framework.TestCase

Unit tests for the [`ActionRedirect`](../../../../../apidocs/org/apache/struts/action/ActionRedirect.html.md?is-external=true "class or interface in org.apache.struts.action") class.

**Version:**  
$Rev: 514052 $ $Date: 2007-03-02 20:00:37 -0600 (Fri, 02 Mar 2007) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` TestActionRedirect(String s)` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

`static junit.framework.TestSuite`

` getSuite()`
            

`static void`

` main(String[] args)`
            

` void`

` testActionRedirectAddParameter()`
           Test all addParameter methods accepting different data types.

` void`

` testActionRedirectAddSameNameParameter()`
           Test adding parameters with the same name.

` void`

` testActionRedirectFromExistingForward()`
           Test creating an ActionRedirect which copies its configuration from an existing ActionForward (except for the "redirect" property).

` void`

` testActionRedirectRedirectFlag()`
           Check that the redirect flag is set.

` void`

` testActionRedirectWithAnchor()`
           Test redirect with anchor.

 <span id="methods_inherited_from_class_junit.framework.TestCase"></span>

| **Methods inherited from class junit.framework.TestCase**                                               |
|---------------------------------------------------------------------------------------------------------|
| `countTestCases, createResult, getName, run, run, runBare, runTest, setName, setUp, tearDown, toString` |

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

### TestActionRedirect

    public TestActionRedirect(String s)

<span id="method_detail"></span>

**Method Detail**

### getSuite

    public static junit.framework.TestSuite getSuite()

------------------------------------------------------------------------

### main

    public static void main(String[] args)

------------------------------------------------------------------------

### testActionRedirectRedirectFlag

    public void testActionRedirectRedirectFlag()

Check that the redirect flag is set.

------------------------------------------------------------------------

### testActionRedirectAddParameter

    public void testActionRedirectAddParameter()

Test all addParameter methods accepting different data types.

------------------------------------------------------------------------

### testActionRedirectWithAnchor

    public void testActionRedirectWithAnchor()

Test redirect with anchor.

------------------------------------------------------------------------

### testActionRedirectAddSameNameParameter

    public void testActionRedirectAddSameNameParameter()

Test adding parameters with the same name.

------------------------------------------------------------------------

### testActionRedirectFromExistingForward

    public void testActionRedirectFromExistingForward()

Test creating an ActionRedirect which copies its configuration from an existing ActionForward (except for the "redirect" property).

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
<td align="left"><a href="class-use/TestActionRedirect.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionMessages.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionRedirect.html"><strong>FRAMES</strong></a>    <a href="TestActionRedirect.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
