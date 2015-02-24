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
<td align="left"><a href="class-use/MockServletConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockPrincipal.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockServletContext.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockServletConfig.html"><strong>FRAMES</strong></a>    <a href="MockServletConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class MockServletConfig
------------------------

    java.lang.Object
      org.apache.struts.mock.MockServletConfig

**All Implemented Interfaces:**  
[ServletConfig](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletConfig.html.md?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class MockServletConfig

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [ServletConfig](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletConfig.html.md?is-external=true "class or interface in javax.servlet")

Mock **ServletConfig** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ServletContext`

` context`
            

`protected  HashMap`

` parameters`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                      |
|----------------------------------------------|
| ` MockServletConfig()`                       
                                               |
| ` MockServletConfig(ServletContext context)` 
                                               |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addInitParameter(String name, String value)`
            

` String`

` getInitParameter(String name)`
            

` Enumeration`

` getInitParameterNames()`
            

` ServletContext`

` getServletContext()`
            

` String`

` getServletName()`
            

` void`

` setServletContext(ServletContext context)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="context"></span>

### context

    protected ServletContext context

------------------------------------------------------------------------

<span id="parameters"></span>

### parameters

    protected HashMap parameters

<span id="constructor_detail"></span>

**Constructor Detail**

### MockServletConfig

    public MockServletConfig()

------------------------------------------------------------------------

### MockServletConfig

    public MockServletConfig(ServletContext context)

<span id="method_detail"></span>

**Method Detail**

### addInitParameter

    public void addInitParameter(String name,
                                 String value)

------------------------------------------------------------------------

### setServletContext

    public void setServletContext(ServletContext context)

------------------------------------------------------------------------

### getInitParameter

    public String getInitParameter(String name)

**Specified by:**  
`getInitParameter` in interface `ServletConfig`

------------------------------------------------------------------------

### getInitParameterNames

    public Enumeration getInitParameterNames()

**Specified by:**  
`getInitParameterNames` in interface `ServletConfig`

------------------------------------------------------------------------

### getServletContext

    public ServletContext getServletContext()

**Specified by:**  
`getServletContext` in interface `ServletConfig`

------------------------------------------------------------------------

### getServletName

    public String getServletName()

**Specified by:**  
`getServletName` in interface `ServletConfig`

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
<td align="left"><a href="class-use/MockServletConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockPrincipal.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockServletContext.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockServletConfig.html"><strong>FRAMES</strong></a>    <a href="MockServletConfig.html"><strong>NO FRAMES</strong></a>    
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
