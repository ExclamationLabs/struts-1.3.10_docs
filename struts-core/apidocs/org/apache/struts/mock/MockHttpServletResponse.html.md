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
<td align="left"><a href="class-use/MockHttpServletResponse.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpServletRequest.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpSession.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpServletResponse.html"><strong>FRAMES</strong></a>    <a href="MockHttpServletResponse.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.mock
 Class MockHttpServletResponse
------------------------------

    java.lang.Object
      org.apache.struts.mock.MockHttpServletResponse

**All Implemented Interfaces:**  
[HttpServletResponse](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletResponse.html.md?is-external=true "class or interface in javax.servlet.http"), [ServletResponse](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletResponse.html?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class MockHttpServletResponse

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [HttpServletResponse](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletResponse.html.md?is-external=true "class or interface in javax.servlet.http")

Mock **HttpServletResponse** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.servlet.http.HttpServletResponse"></span>

| **Fields inherited from interface javax.servlet.http.[HttpServletResponse](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletResponse.html.md?is-external=true "class or interface in javax.servlet.http")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `SC_ACCEPTED, SC_BAD_GATEWAY, SC_BAD_REQUEST, SC_CONFLICT, SC_CONTINUE, SC_CREATED, SC_EXPECTATION_FAILED, SC_FORBIDDEN, SC_GATEWAY_TIMEOUT, SC_GONE, SC_HTTP_VERSION_NOT_SUPPORTED, SC_INTERNAL_SERVER_ERROR, SC_LENGTH_REQUIRED, SC_METHOD_NOT_ALLOWED, SC_MOVED_PERMANENTLY, SC_MOVED_TEMPORARILY, SC_MULTIPLE_CHOICES, SC_NO_CONTENT, SC_NON_AUTHORITATIVE_INFORMATION, SC_NOT_ACCEPTABLE, SC_NOT_FOUND, SC_NOT_IMPLEMENTED, SC_NOT_MODIFIED, SC_OK, SC_PARTIAL_CONTENT, SC_PAYMENT_REQUIRED, SC_PRECONDITION_FAILED, SC_PROXY_AUTHENTICATION_REQUIRED, SC_REQUEST_ENTITY_TOO_LARGE, SC_REQUEST_TIMEOUT, SC_REQUEST_URI_TOO_LONG, SC_REQUESTED_RANGE_NOT_SATISFIABLE, SC_RESET_CONTENT, SC_SEE_OTHER, SC_SERVICE_UNAVAILABLE, SC_SWITCHING_PROTOCOLS, SC_TEMPORARY_REDIRECT, SC_UNAUTHORIZED, SC_UNSUPPORTED_MEDIA_TYPE, SC_USE_PROXY` |

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` MockHttpServletResponse()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addCookie(Cookie cookie)`
            

` void`

` addDateHeader(String name, long value)`
            

` void`

` addHeader(String name, String value)`
            

` void`

` addIntHeader(String name, int value)`
            

` boolean`

` containsHeader(String name)`
            

` String`

` encodeRedirectUrl(String url)`
            

` String`

` encodeRedirectURL(String url)`
            

` String`

` encodeUrl(String url)`
            

` String`

` encodeURL(String url)`
            

` void`

` flushBuffer()`
            

` int`

` getBufferSize()`
            

` String`

` getCharacterEncoding()`
            

` Locale`

` getLocale()`
            

` ServletOutputStream`

` getOutputStream()`
            

` PrintWriter`

` getWriter()`
            

` boolean`

` isCommitted()`
            

` void`

` reset()`
            

` void`

` resetBuffer()`
            

` void`

` sendError(int status)`
            

` void`

` sendError(int status, String message)`
            

` void`

` sendRedirect(String location)`
            

` void`

` setBufferSize(int size)`
            

` void`

` setContentLength(int length)`
            

` void`

` setContentType(String type)`
            

` void`

` setDateHeader(String name, long value)`
            

` void`

` setHeader(String name, String value)`
            

` void`

` setIntHeader(String name, int value)`
            

` void`

` setLocale(Locale locale)`
            

` void`

` setStatus(int status)`
            

` void`

` setStatus(int status, String message)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MockHttpServletResponse

    public MockHttpServletResponse()

<span id="method_detail"></span>

**Method Detail**

### addCookie

    public void addCookie(Cookie cookie)

**Specified by:**  
`addCookie` in interface `HttpServletResponse`

------------------------------------------------------------------------

### addDateHeader

    public void addDateHeader(String name,
                              long value)

**Specified by:**  
`addDateHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### addHeader

    public void addHeader(String name,
                          String value)

**Specified by:**  
`addHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### addIntHeader

    public void addIntHeader(String name,
                             int value)

**Specified by:**  
`addIntHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### containsHeader

    public boolean containsHeader(String name)

**Specified by:**  
`containsHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### encodeRedirectUrl

    public String encodeRedirectUrl(String url)

**Specified by:**  
`encodeRedirectUrl` in interface `HttpServletResponse`

------------------------------------------------------------------------

### encodeRedirectURL

    public String encodeRedirectURL(String url)

**Specified by:**  
`encodeRedirectURL` in interface `HttpServletResponse`

------------------------------------------------------------------------

### encodeUrl

    public String encodeUrl(String url)

**Specified by:**  
`encodeUrl` in interface `HttpServletResponse`

------------------------------------------------------------------------

### encodeURL

    public String encodeURL(String url)

**Specified by:**  
`encodeURL` in interface `HttpServletResponse`

------------------------------------------------------------------------

### sendError

    public void sendError(int status)

**Specified by:**  
`sendError` in interface `HttpServletResponse`

------------------------------------------------------------------------

### sendError

    public void sendError(int status,
                          String message)

**Specified by:**  
`sendError` in interface `HttpServletResponse`

------------------------------------------------------------------------

### sendRedirect

    public void sendRedirect(String location)

**Specified by:**  
`sendRedirect` in interface `HttpServletResponse`

------------------------------------------------------------------------

### setDateHeader

    public void setDateHeader(String name,
                              long value)

**Specified by:**  
`setDateHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### setHeader

    public void setHeader(String name,
                          String value)

**Specified by:**  
`setHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### setIntHeader

    public void setIntHeader(String name,
                             int value)

**Specified by:**  
`setIntHeader` in interface `HttpServletResponse`

------------------------------------------------------------------------

### setStatus

    public void setStatus(int status)

**Specified by:**  
`setStatus` in interface `HttpServletResponse`

------------------------------------------------------------------------

### setStatus

    public void setStatus(int status,
                          String message)

**Specified by:**  
`setStatus` in interface `HttpServletResponse`

------------------------------------------------------------------------

### flushBuffer

    public void flushBuffer()

**Specified by:**  
`flushBuffer` in interface `ServletResponse`

------------------------------------------------------------------------

### getBufferSize

    public int getBufferSize()

**Specified by:**  
`getBufferSize` in interface `ServletResponse`

------------------------------------------------------------------------

### getCharacterEncoding

    public String getCharacterEncoding()

**Specified by:**  
`getCharacterEncoding` in interface `ServletResponse`

------------------------------------------------------------------------

### getLocale

    public Locale getLocale()

**Specified by:**  
`getLocale` in interface `ServletResponse`

------------------------------------------------------------------------

### getOutputStream

    public ServletOutputStream getOutputStream()
                                        throws IOException

**Specified by:**  
`getOutputStream` in interface `ServletResponse`

<!-- -->

**Throws:**  
`IOException`

------------------------------------------------------------------------

### getWriter

    public PrintWriter getWriter()
                          throws IOException

**Specified by:**  
`getWriter` in interface `ServletResponse`

<!-- -->

**Throws:**  
`IOException`

------------------------------------------------------------------------

### isCommitted

    public boolean isCommitted()

**Specified by:**  
`isCommitted` in interface `ServletResponse`

------------------------------------------------------------------------

### reset

    public void reset()

**Specified by:**  
`reset` in interface `ServletResponse`

------------------------------------------------------------------------

### resetBuffer

    public void resetBuffer()

**Specified by:**  
`resetBuffer` in interface `ServletResponse`

------------------------------------------------------------------------

### setBufferSize

    public void setBufferSize(int size)

**Specified by:**  
`setBufferSize` in interface `ServletResponse`

------------------------------------------------------------------------

### setContentLength

    public void setContentLength(int length)

**Specified by:**  
`setContentLength` in interface `ServletResponse`

------------------------------------------------------------------------

### setContentType

    public void setContentType(String type)

**Specified by:**  
`setContentType` in interface `ServletResponse`

------------------------------------------------------------------------

### setLocale

    public void setLocale(Locale locale)

**Specified by:**  
`setLocale` in interface `ServletResponse`

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
<td align="left"><a href="class-use/MockHttpServletResponse.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockHttpServletRequest.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpSession.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpServletResponse.html"><strong>FRAMES</strong></a>    <a href="MockHttpServletResponse.html"><strong>NO FRAMES</strong></a>    
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
