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
<td align="left"><a href="class-use/MockPageContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockMultipartRequestHandler.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockPrincipal.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockPageContext.html"><strong>FRAMES</strong></a>    <a href="MockPageContext.html"><strong>NO FRAMES</strong></a>    
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
 Class MockPageContext
----------------------

    java.lang.Object
      javax.servlet.jsp.PageContext
          org.apache.struts.mock.MockPageContext

------------------------------------------------------------------------

    public class MockPageContext

extends [PageContext](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/PageContext.html.md?is-external=true "class or interface in javax.servlet.jsp")

Mock **ServletContext** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:45:39 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ServletContext`

` application`
            

`protected  HashMap`

` attributes`
            

`protected  ServletConfig`

`config`
            

`protected  ServletRequest`

`request`
            

`protected  ServletResponse`

`response`
            

`protected  HttpSession`

`session`
            

 <span id="fields_inherited_from_class_javax.servlet.jsp.PageContext"></span>

| **Fields inherited from class javax.servlet.jsp.[PageContext](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/PageContext.html.md?is-external=true "class or interface in javax.servlet.jsp")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `APPLICATION, APPLICATION_SCOPE, CONFIG, EXCEPTION, OUT, PAGE, PAGE_SCOPE, PAGECONTEXT, REQUEST, REQUEST_SCOPE, RESPONSE, SESSION, SESSION_SCOPE`                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                    |
|--------------------------------------------------------------------------------------------|
| ` MockPageContext()`                                                                       
                                                                                             |
| ` MockPageContext(boolean throwIOException, boolean returnBody)`                           
             Construct a new PageContext impl.                                               |
| ` MockPageContext(ServletConfig config, ServletRequest request, ServletResponse response)` 
                                                                                             |

  <span id="method_summary"></span>

**Method Summary**

` Object`

` findAttribute(String name)`
            

` void`

` forward(String path)`
            

` Object`

` getAttribute(String name)`
            

` Object`

` getAttribute(String name, int scope)`
            

` Enumeration`

` getAttributeNamesInScope(int scope)`
            

` int`

` getAttributesScope(String name)`
            

` Exception`

` getException()`
            

` JspWriter`

`getOut()`
            Custom JspWriter that throws the specified exception (supplied on the constructor...if any), else it simply returns.

` Object`

` getPage()`
            

` ServletRequest`

` getRequest()`
            

` ServletResponse`

` getResponse()`
            

` ServletConfig`

` getServletConfig()`
            

` ServletContext`

` getServletContext()`
            

` HttpSession`

` getSession()`
            

` void`

` handlePageException(Exception e)`
            

` void`

` handlePageException(Throwable t)`
            

` void`

` include(String path)`
            

` void`

` initialize(Servlet servlet, ServletRequest request, ServletResponse response, String errorPageURL, boolean needsSession, int bufferSize, boolean autoFlush)`
            

` JspWriter`

` popBody()`
            

` BodyContent`

` pushBody()`
            

` void`

` release()`
            

` void`

` removeAttribute(String name)`
            

` void`

` removeAttribute(String name, int scope)`
            

` void`

` setAttribute(String name, Object value)`
            

` void`

` setAttribute(String name, Object value, int scope)`
            

` void`

` setValues(ServletConfig config, ServletRequest request, ServletResponse response)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="application"></span>

### application

    protected ServletContext application

------------------------------------------------------------------------

<span id="attributes"></span>

### attributes

    protected HashMap attributes

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected ServletConfig config

------------------------------------------------------------------------

<span id="request"></span>

### request

    protected ServletRequest request

------------------------------------------------------------------------

<span id="response"></span>

### response

    protected ServletResponse response

------------------------------------------------------------------------

<span id="session"></span>

### session

    protected HttpSession session

<span id="constructor_detail"></span>

**Constructor Detail**

### MockPageContext

    public MockPageContext()

------------------------------------------------------------------------

### MockPageContext

    public MockPageContext(ServletConfig config,
                           ServletRequest request,
                           ServletResponse response)

------------------------------------------------------------------------

### MockPageContext

    public MockPageContext(boolean throwIOException,
                           boolean returnBody)

Construct a new PageContext impl.

**Parameters:**  
`throwIOException` - Determines if the returned JspWriter should throw an IOException on any method call.

`returnBody` - Determines if getOut() should return a new `JspWriter` or a `BodyContent`.

<span id="method_detail"></span>

**Method Detail**

### setValues

    public void setValues(ServletConfig config,
                          ServletRequest request,
                          ServletResponse response)

------------------------------------------------------------------------

### findAttribute

    public Object findAttribute(String name)

**Specified by:**  
`findAttribute` in class `PageContext`

------------------------------------------------------------------------

### forward

    public void forward(String path)

**Specified by:**  
`forward` in class `PageContext`

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name)

**Specified by:**  
`getAttribute` in class `PageContext`

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name,
                               int scope)

**Specified by:**  
`getAttribute` in class `PageContext`

------------------------------------------------------------------------

### getAttributeNamesInScope

    public Enumeration getAttributeNamesInScope(int scope)

**Specified by:**  
`getAttributeNamesInScope` in class `PageContext`

------------------------------------------------------------------------

### getAttributesScope

    public int getAttributesScope(String name)

**Specified by:**  
`getAttributesScope` in class `PageContext`

------------------------------------------------------------------------

### getException

    public Exception getException()

**Specified by:**  
`getException` in class `PageContext`

------------------------------------------------------------------------

### getOut

    public JspWriter getOut()

Custom JspWriter that throws the specified exception (supplied on the constructor...if any), else it simply returns.

**Specified by:**  
`getOut` in class `PageContext`

------------------------------------------------------------------------

### getPage

    public Object getPage()

**Specified by:**  
`getPage` in class `PageContext`

------------------------------------------------------------------------

### getRequest

    public ServletRequest getRequest()

**Specified by:**  
`getRequest` in class `PageContext`

------------------------------------------------------------------------

### getResponse

    public ServletResponse getResponse()

**Specified by:**  
`getResponse` in class `PageContext`

------------------------------------------------------------------------

### getServletConfig

    public ServletConfig getServletConfig()

**Specified by:**  
`getServletConfig` in class `PageContext`

------------------------------------------------------------------------

### getServletContext

    public ServletContext getServletContext()

**Specified by:**  
`getServletContext` in class `PageContext`

------------------------------------------------------------------------

### getSession

    public HttpSession getSession()

**Specified by:**  
`getSession` in class `PageContext`

------------------------------------------------------------------------

### handlePageException

    public void handlePageException(Exception e)

**Specified by:**  
`handlePageException` in class `PageContext`

------------------------------------------------------------------------

### handlePageException

    public void handlePageException(Throwable t)

**Specified by:**  
`handlePageException` in class `PageContext`

------------------------------------------------------------------------

### include

    public void include(String path)

**Specified by:**  
`include` in class `PageContext`

------------------------------------------------------------------------

### initialize

    public void initialize(Servlet servlet,
                           ServletRequest request,
                           ServletResponse response,
                           String errorPageURL,
                           boolean needsSession,
                           int bufferSize,
                           boolean autoFlush)

**Specified by:**  
`initialize` in class `PageContext`

------------------------------------------------------------------------

### popBody

    public JspWriter popBody()

**Overrides:**  
`popBody` in class `PageContext`

------------------------------------------------------------------------

### pushBody

    public BodyContent pushBody()

**Overrides:**  
`pushBody` in class `PageContext`

------------------------------------------------------------------------

### release

    public void release()

**Specified by:**  
`release` in class `PageContext`

------------------------------------------------------------------------

### removeAttribute

    public void removeAttribute(String name)

**Specified by:**  
`removeAttribute` in class `PageContext`

------------------------------------------------------------------------

### removeAttribute

    public void removeAttribute(String name,
                                int scope)

**Specified by:**  
`removeAttribute` in class `PageContext`

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String name,
                             Object value)

**Specified by:**  
`setAttribute` in class `PageContext`

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String name,
                             Object value,
                             int scope)

**Specified by:**  
`setAttribute` in class `PageContext`

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
<td align="left"><a href="class-use/MockPageContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockMultipartRequestHandler.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockPrincipal.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockPageContext.html"><strong>FRAMES</strong></a>    <a href="MockPageContext.html"><strong>NO FRAMES</strong></a>    
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
