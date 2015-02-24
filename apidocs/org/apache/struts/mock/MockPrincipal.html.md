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
<td align="left"><a href="class-use/MockPrincipal.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockPageContext.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockServletConfig.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockPrincipal.html"><strong>FRAMES</strong></a>    <a href="MockPrincipal.html"><strong>NO FRAMES</strong></a>    
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
 Class MockPrincipal
----------------------

    java.lang.Object
      org.apache.struts.mock.MockPrincipal

**All Implemented Interfaces:**  
[Principal](http://java.sun.com/j2se/1.4.2/docs/api/java/security/Principal.html.md?is-external=true "class or interface in java.security")

------------------------------------------------------------------------

    public class MockPrincipal

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Principal](http://java.sun.com/j2se/1.4.2/docs/api/java/security/Principal.html.md?is-external=true "class or interface in java.security")

Mock **Principal** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`name`
            

`protected  String[]`

`roles`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                       |
|-----------------------------------------------|
| ` MockPrincipal()`                            
                                                |
| ` MockPrincipal(String name)`                 
                                                |
| ` MockPrincipal(String name, String[] roles)` 
                                                |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` equals(Object o)`
            

` String`

`getName()`
            

` int`

`hashCode()`
            

` boolean`

` isUserInRole(String role)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, finalize, getClass, notify, notifyAll, toString, wait, wait, wait`                                                                                            |

 <span id="methods_inherited_from_class_java.security.Principal"></span>

| **Methods inherited from interface java.security.[Principal](http://java.sun.com/j2se/1.4.2/docs/api/java/security/Principal.html.md?is-external=true "class or interface in java.security")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `toString`                                                                                                                                                                                  |

 

<span id="field_detail"></span>

**Field Detail**

<span id="name"></span>

### name

    protected String name

------------------------------------------------------------------------

<span id="roles"></span>

### roles

    protected String[] roles

<span id="constructor_detail"></span>

**Constructor Detail**

### MockPrincipal

    public MockPrincipal()

------------------------------------------------------------------------

### MockPrincipal

    public MockPrincipal(String name)

------------------------------------------------------------------------

### MockPrincipal

    public MockPrincipal(String name,
                         String[] roles)

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

**Specified by:**  
`getName` in interface `Principal`

------------------------------------------------------------------------

### isUserInRole

    public boolean isUserInRole(String role)

------------------------------------------------------------------------

### equals

    public boolean equals(Object o)

**Specified by:**  
`equals` in interface `Principal`

**Overrides:**  
`equals` in class `Object`

------------------------------------------------------------------------

### hashCode

    public int hashCode()

**Specified by:**  
`hashCode` in interface `Principal`

**Overrides:**  
`hashCode` in class `Object`

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
<td align="left"><a href="class-use/MockPrincipal.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockPageContext.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockServletConfig.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockPrincipal.html"><strong>FRAMES</strong></a>    <a href="MockPrincipal.html"><strong>NO FRAMES</strong></a>    
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
