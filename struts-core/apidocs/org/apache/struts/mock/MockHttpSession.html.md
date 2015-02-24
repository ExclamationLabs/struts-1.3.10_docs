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
<td align="left"><a href="class-use/MockHttpSession.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpServletResponse.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockMultipartRequestHandler.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpSession.html"><strong>FRAMES</strong></a>    <a href="MockHttpSession.html"><strong>NO FRAMES</strong></a>    
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
 Class MockHttpSession
----------------------

    java.lang.Object
      org.apache.struts.mock.MockHttpSession

**All Implemented Interfaces:**  
[HttpSession](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpSession.html.md?is-external=true "class or interface in javax.servlet.http")

------------------------------------------------------------------------

    public class MockHttpSession

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [HttpSession](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpSession.html.md?is-external=true "class or interface in javax.servlet.http")

Mock **HttpSession** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  HashMap`

` attributes`
            The set of session attributes.

`protected  ServletContext`

` servletContext`
            The ServletContext with which we are associated.

  <span id="constructor_summary"></span>

| **Constructor Summary**                           |
|---------------------------------------------------|
| ` MockHttpSession()`                              
                                                    |
| ` MockHttpSession(ServletContext servletContext)` 
                                                    |

  <span id="method_summary"></span>

**Method Summary**

` Object`

` getAttribute(String name)`
            

` Enumeration`

` getAttributeNames()`
            

` long`

` getCreationTime()`
            

` String`

`getId()`
            

` long`

` getLastAccessedTime()`
            

` int`

` getMaxInactiveInterval()`
            

` ServletContext`

` getServletContext()`
            

` HttpSessionContext`

` getSessionContext()`
            

` Object`

` getValue(String name)`
            

` String[]`

` getValueNames()`
            

` void`

` invalidate()`
            

` boolean`

`isNew()`
            

` void`

` putValue(String name, Object value)`
            

` void`

` removeAttribute(String name)`
            

` void`

` removeValue(String name)`
            

` void`

` setAttribute(String name, Object value)`
            

` void`

` setMaxInactiveInterval(int interval)`
            

` void`

` setServletContext(ServletContext servletContext)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="attributes"></span>

### attributes

    protected HashMap attributes

The set of session attributes.

------------------------------------------------------------------------

<span id="servletContext"></span>

### servletContext

    protected ServletContext servletContext

The ServletContext with which we are associated.

<span id="constructor_detail"></span>

**Constructor Detail**

### MockHttpSession

    public MockHttpSession()

------------------------------------------------------------------------

### MockHttpSession

    public MockHttpSession(ServletContext servletContext)

<span id="method_detail"></span>

**Method Detail**

### setServletContext

    public void setServletContext(ServletContext servletContext)

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name)

**Specified by:**  
`getAttribute` in interface `HttpSession`

------------------------------------------------------------------------

### getAttributeNames

    public Enumeration getAttributeNames()

**Specified by:**  
`getAttributeNames` in interface `HttpSession`

------------------------------------------------------------------------

### getCreationTime

    public long getCreationTime()

**Specified by:**  
`getCreationTime` in interface `HttpSession`

------------------------------------------------------------------------

### getId

    public String getId()

**Specified by:**  
`getId` in interface `HttpSession`

------------------------------------------------------------------------

### getLastAccessedTime

    public long getLastAccessedTime()

**Specified by:**  
`getLastAccessedTime` in interface `HttpSession`

------------------------------------------------------------------------

### getMaxInactiveInterval

    public int getMaxInactiveInterval()

**Specified by:**  
`getMaxInactiveInterval` in interface `HttpSession`

------------------------------------------------------------------------

### getServletContext

    public ServletContext getServletContext()

**Specified by:**  
`getServletContext` in interface `HttpSession`

------------------------------------------------------------------------

### getSessionContext

    public HttpSessionContext getSessionContext()

**Specified by:**  
`getSessionContext` in interface `HttpSession`

------------------------------------------------------------------------

### getValue

    public Object getValue(String name)

**Specified by:**  
`getValue` in interface `HttpSession`

------------------------------------------------------------------------

### getValueNames

    public String[] getValueNames()

**Specified by:**  
`getValueNames` in interface `HttpSession`

------------------------------------------------------------------------

### invalidate

    public void invalidate()

**Specified by:**  
`invalidate` in interface `HttpSession`

------------------------------------------------------------------------

### isNew

    public boolean isNew()

**Specified by:**  
`isNew` in interface `HttpSession`

------------------------------------------------------------------------

### putValue

    public void putValue(String name,
                         Object value)

**Specified by:**  
`putValue` in interface `HttpSession`

------------------------------------------------------------------------

### removeAttribute

    public void removeAttribute(String name)

**Specified by:**  
`removeAttribute` in interface `HttpSession`

------------------------------------------------------------------------

### removeValue

    public void removeValue(String name)

**Specified by:**  
`removeValue` in interface `HttpSession`

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String name,
                             Object value)

**Specified by:**  
`setAttribute` in interface `HttpSession`

------------------------------------------------------------------------

### setMaxInactiveInterval

    public void setMaxInactiveInterval(int interval)

**Specified by:**  
`setMaxInactiveInterval` in interface `HttpSession`

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
<td align="left"><a href="class-use/MockHttpSession.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpServletResponse.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockMultipartRequestHandler.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpSession.html"><strong>FRAMES</strong></a>    <a href="MockHttpSession.html"><strong>NO FRAMES</strong></a>    
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
