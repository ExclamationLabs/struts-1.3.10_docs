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
<td align="left"><a href="class-use/TagTestBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/taglib/TestTagUtils.html.md" title="class in org.apache.struts.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/taglib/TagTestBase.html"><strong>FRAMES</strong></a>    <a href="TagTestBase.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.taglib
 Class TagTestBase
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.taglib.TagTestBase

**All Implemented Interfaces:**  
junit.framework.Test

<!-- -->

**Direct Known Subclasses:**  
[TestTagUtils](../../../../org/apache/struts/taglib/TestTagUtils.html.md "class in org.apache.struts.taglib")

------------------------------------------------------------------------

    public class TagTestBase

extends junit.framework.TestCase

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ModuleConfig`

` moduleConfig`
            

`protected  ModuleConfig`

` moduleConfig2`
            

`protected  ModuleConfig`

` moduleConfig3`
            

`protected  org.apache.struts.mock.MockPageContext`

` pageContext`
            

`protected  org.apache.struts.mock.MockHttpServletRequest`

`request`
            

`protected  org.apache.struts.mock.MockServletConfig`

` servletConfig`
            

`protected  org.apache.struts.mock.MockServletContext`

` servletContext`
            

`protected  TagUtils`

`tagutils`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**        |
|--------------------------------|
| ` TagTestBase()`               
                                 |
| ` TagTestBase(String theName)` 
                                 |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` putBundleInScope(int scope, boolean returnNull)`
            

` void`

`setUp()`
           Helper method that creates/configures a basic configuration of Mock Objects.

` void`

`tearDown()`
            

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

<span id="tagutils"></span>

### tagutils

    protected TagUtils tagutils

------------------------------------------------------------------------

<span id="servletConfig"></span>

### servletConfig

    protected org.apache.struts.mock.MockServletConfig servletConfig

------------------------------------------------------------------------

<span id="servletContext"></span>

### servletContext

    protected org.apache.struts.mock.MockServletContext servletContext

------------------------------------------------------------------------

<span id="request"></span>

### request

    protected org.apache.struts.mock.MockHttpServletRequest request

------------------------------------------------------------------------

<span id="pageContext"></span>

### pageContext

    protected org.apache.struts.mock.MockPageContext pageContext

------------------------------------------------------------------------

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

<span id="constructor_detail"></span>

**Constructor Detail**

### TagTestBase

    public TagTestBase()

------------------------------------------------------------------------

### TagTestBase

    public TagTestBase(String theName)

<span id="method_detail"></span>

**Method Detail**

### setUp

    public void setUp()

Helper method that creates/configures a basic configuration of Mock Objects. PageContext ServletConfig ServletContext HttpServletRequest HttpSession HttpServletResponse "/myapp", "/foo", null, null,

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### putBundleInScope

    protected void putBundleInScope(int scope,
                                    boolean returnNull)

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
<td align="left"><a href="class-use/TagTestBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/taglib/TestTagUtils.html.md" title="class in org.apache.struts.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/taglib/TagTestBase.html"><strong>FRAMES</strong></a>    <a href="TagTestBase.html"><strong>NO FRAMES</strong></a>    
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
