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
<td align="left"><a href="class-use/MockHttpServletRequest.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockFormBean.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpServletResponse.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpServletRequest.html"><strong>FRAMES</strong></a>    <a href="MockHttpServletRequest.html"><strong>NO FRAMES</strong></a>    
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
 Class MockHttpServletRequest
-----------------------------

    java.lang.Object
      org.apache.struts.mock.MockHttpServletRequest

**All Implemented Interfaces:**  
[HttpServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequest.html.md?is-external=true "class or interface in javax.servlet.http"), [ServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletRequest.html?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class MockHttpServletRequest

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [HttpServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequest.html.md?is-external=true "class or interface in javax.servlet.http")

Mock **HttpServletRequest** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only the minimal set of methods needed to create unit tests is provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  HashMap`

` attributes`
            The set of request attributes.

`protected  String`

` contentType`
            The Content Type for this request.

`protected  String`

` contextPath`
            The context path for this request.

`protected  Locale`

` locale`
            The preferred locale for this request.

`protected  String`

` method`
            The HTTP request method.

`protected  HashMap`

` parameters`
            The set of arrays of parameter values, keyed by parameter name.

`protected  String`

` pathInfo`
            The extra path information for this request.

`protected  Principal`

` principal`
            The authenticated user for this request.

`protected  String`

` queryString`
            The query string for this request.

`protected  String`

` servletPath`
            The servlet path for this request.

`protected  HttpSession`

` session`
            The HttpSession with which we are associated.

 <span id="fields_inherited_from_class_javax.servlet.http.HttpServletRequest"></span>

| **Fields inherited from interface javax.servlet.http.[HttpServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequest.html.md?is-external=true "class or interface in javax.servlet.http")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `BASIC_AUTH, CLIENT_CERT_AUTH, DIGEST_AUTH, FORM_AUTH`                                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------|
| ` MockHttpServletRequest()`                                                                                                 
                                                                                                                              |
| ` MockHttpServletRequest(HttpSession session)`                                                                              
                                                                                                                              |
| ` MockHttpServletRequest(String contextPath, String servletPath, String pathInfo, String queryString)`                      
                                                                                                                              |
| ` MockHttpServletRequest(String contextPath, String servletPath, String pathInfo, String queryString, HttpSession session)` 
                                                                                                                              |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addParameter(String name, String value)`
            

` Object`

` getAttribute(String name)`
            

` Enumeration`

` getAttributeNames()`
            

` String`

` getAuthType()`
            

` String`

` getCharacterEncoding()`
            

` int`

` getContentLength()`
            

` String`

` getContentType()`
            

` String`

` getContextPath()`
            

` Cookie[]`

` getCookies()`
            

` long`

` getDateHeader(String name)`
            

` String`

` getHeader(String name)`
            

` Enumeration`

` getHeaderNames()`
            

` Enumeration`

` getHeaders(String name)`
            

` ServletInputStream`

` getInputStream()`
            

` int`

` getIntHeader(String name)`
            

` Locale`

` getLocale()`
            

` Enumeration`

` getLocales()`
            

` String`

` getMethod()`
            

` String`

` getParameter(String name)`
            

` Map`

` getParameterMap()`
            

` Enumeration`

` getParameterNames()`
            

` String[]`

` getParameterValues(String name)`
            

` String`

` getPathInfo()`
            

` String`

` getPathTranslated()`
            

` String`

` getProtocol()`
            

` String`

` getQueryString()`
            

` BufferedReader`

` getReader()`
            

` String`

` getRealPath(String path)`
            

` String`

` getRemoteAddr()`
            

` String`

` getRemoteHost()`
            

` String`

` getRemoteUser()`
            

` RequestDispatcher`

` getRequestDispatcher(String path)`
            

` String`

` getRequestedSessionId()`
            

` String`

` getRequestURI()`
            

` StringBuffer`

` getRequestURL()`
            

` String`

` getScheme()`
            

` String`

` getServerName()`
            

` int`

` getServerPort()`
            

` String`

` getServletPath()`
            

` HttpSession`

` getSession()`
            

` HttpSession`

` getSession(boolean create)`
            

` Principal`

` getUserPrincipal()`
            

` boolean`

` isRequestedSessionIdFromCookie()`
            

` boolean`

` isRequestedSessionIdFromUrl()`
            

` boolean`

` isRequestedSessionIdFromURL()`
            

` boolean`

` isRequestedSessionIdValid()`
            

` boolean`

` isSecure()`
            

` boolean`

` isUserInRole(String role)`
            

` void`

` removeAttribute(String name)`
            

` void`

` setAttribute(String name, Object value)`
            

` void`

` setCharacterEncoding(String name)`
            

` void`

` setContentType(String contentType)`
            

` void`

` setHttpSession(HttpSession session)`
            

` void`

` setLocale(Locale locale)`
            

` void`

` setMethod(String method)`
            

` void`

` setPathElements(String contextPath, String servletPath, String pathInfo, String queryString)`
            

` void`

` setUserPrincipal(Principal principal)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="attributes"></span>

### attributes

    protected HashMap attributes

The set of request attributes.

------------------------------------------------------------------------

<span id="contextPath"></span>

### contextPath

    protected String contextPath

The context path for this request.

------------------------------------------------------------------------

<span id="locale"></span>

### locale

    protected Locale locale

The preferred locale for this request.

------------------------------------------------------------------------

<span id="parameters"></span>

### parameters

    protected HashMap parameters

The set of arrays of parameter values, keyed by parameter name.

------------------------------------------------------------------------

<span id="pathInfo"></span>

### pathInfo

    protected String pathInfo

The extra path information for this request. v \*

------------------------------------------------------------------------

<span id="principal"></span>

### principal

    protected Principal principal

The authenticated user for this request.

------------------------------------------------------------------------

<span id="queryString"></span>

### queryString

    protected String queryString

The query string for this request.

------------------------------------------------------------------------

<span id="servletPath"></span>

### servletPath

    protected String servletPath

The servlet path for this request.

------------------------------------------------------------------------

<span id="session"></span>

### session

    protected HttpSession session

The HttpSession with which we are associated.

------------------------------------------------------------------------

<span id="method"></span>

### method

    protected String method

The HTTP request method.

------------------------------------------------------------------------

<span id="contentType"></span>

### contentType

    protected String contentType

The Content Type for this request.

<span id="constructor_detail"></span>

**Constructor Detail**

### MockHttpServletRequest

    public MockHttpServletRequest()

------------------------------------------------------------------------

### MockHttpServletRequest

    public MockHttpServletRequest(HttpSession session)

------------------------------------------------------------------------

### MockHttpServletRequest

    public MockHttpServletRequest(String contextPath,
                                  String servletPath,
                                  String pathInfo,
                                  String queryString)

------------------------------------------------------------------------

### MockHttpServletRequest

    public MockHttpServletRequest(String contextPath,
                                  String servletPath,
                                  String pathInfo,
                                  String queryString,
                                  HttpSession session)

<span id="method_detail"></span>

**Method Detail**

### addParameter

    public void addParameter(String name,
                             String value)

------------------------------------------------------------------------

### setHttpSession

    public void setHttpSession(HttpSession session)

------------------------------------------------------------------------

### setLocale

    public void setLocale(Locale locale)

------------------------------------------------------------------------

### setMethod

    public void setMethod(String method)

------------------------------------------------------------------------

### setContentType

    public void setContentType(String contentType)

------------------------------------------------------------------------

### setPathElements

    public void setPathElements(String contextPath,
                                String servletPath,
                                String pathInfo,
                                String queryString)

------------------------------------------------------------------------

### setUserPrincipal

    public void setUserPrincipal(Principal principal)

------------------------------------------------------------------------

### getAuthType

    public String getAuthType()

**Specified by:**  
`getAuthType` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getContextPath

    public String getContextPath()

**Specified by:**  
`getContextPath` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getCookies

    public Cookie[] getCookies()

**Specified by:**  
`getCookies` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getDateHeader

    public long getDateHeader(String name)

**Specified by:**  
`getDateHeader` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getHeader

    public String getHeader(String name)

**Specified by:**  
`getHeader` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getHeaderNames

    public Enumeration getHeaderNames()

**Specified by:**  
`getHeaderNames` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getHeaders

    public Enumeration getHeaders(String name)

**Specified by:**  
`getHeaders` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getIntHeader

    public int getIntHeader(String name)

**Specified by:**  
`getIntHeader` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getMethod

    public String getMethod()

**Specified by:**  
`getMethod` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getPathInfo

    public String getPathInfo()

**Specified by:**  
`getPathInfo` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getPathTranslated

    public String getPathTranslated()

**Specified by:**  
`getPathTranslated` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getQueryString

    public String getQueryString()

**Specified by:**  
`getQueryString` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getRemoteUser

    public String getRemoteUser()

**Specified by:**  
`getRemoteUser` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getRequestedSessionId

    public String getRequestedSessionId()

**Specified by:**  
`getRequestedSessionId` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getRequestURI

    public String getRequestURI()

**Specified by:**  
`getRequestURI` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getRequestURL

    public StringBuffer getRequestURL()

**Specified by:**  
`getRequestURL` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getServletPath

    public String getServletPath()

**Specified by:**  
`getServletPath` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getSession

    public HttpSession getSession()

**Specified by:**  
`getSession` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getSession

    public HttpSession getSession(boolean create)

**Specified by:**  
`getSession` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getUserPrincipal

    public Principal getUserPrincipal()

**Specified by:**  
`getUserPrincipal` in interface `HttpServletRequest`

------------------------------------------------------------------------

### isRequestedSessionIdFromCookie

    public boolean isRequestedSessionIdFromCookie()

**Specified by:**  
`isRequestedSessionIdFromCookie` in interface `HttpServletRequest`

------------------------------------------------------------------------

### isRequestedSessionIdFromUrl

    public boolean isRequestedSessionIdFromUrl()

**Specified by:**  
`isRequestedSessionIdFromUrl` in interface `HttpServletRequest`

------------------------------------------------------------------------

### isRequestedSessionIdFromURL

    public boolean isRequestedSessionIdFromURL()

**Specified by:**  
`isRequestedSessionIdFromURL` in interface `HttpServletRequest`

------------------------------------------------------------------------

### isRequestedSessionIdValid

    public boolean isRequestedSessionIdValid()

**Specified by:**  
`isRequestedSessionIdValid` in interface `HttpServletRequest`

------------------------------------------------------------------------

### isUserInRole

    public boolean isUserInRole(String role)

**Specified by:**  
`isUserInRole` in interface `HttpServletRequest`

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String name)

**Specified by:**  
`getAttribute` in interface `ServletRequest`

------------------------------------------------------------------------

### getAttributeNames

    public Enumeration getAttributeNames()

**Specified by:**  
`getAttributeNames` in interface `ServletRequest`

------------------------------------------------------------------------

### getCharacterEncoding

    public String getCharacterEncoding()

**Specified by:**  
`getCharacterEncoding` in interface `ServletRequest`

------------------------------------------------------------------------

### getContentLength

    public int getContentLength()

**Specified by:**  
`getContentLength` in interface `ServletRequest`

------------------------------------------------------------------------

### getContentType

    public String getContentType()

**Specified by:**  
`getContentType` in interface `ServletRequest`

------------------------------------------------------------------------

### getInputStream

    public ServletInputStream getInputStream()

**Specified by:**  
`getInputStream` in interface `ServletRequest`

------------------------------------------------------------------------

### getLocale

    public Locale getLocale()

**Specified by:**  
`getLocale` in interface `ServletRequest`

------------------------------------------------------------------------

### getLocales

    public Enumeration getLocales()

**Specified by:**  
`getLocales` in interface `ServletRequest`

------------------------------------------------------------------------

### getParameter

    public String getParameter(String name)

**Specified by:**  
`getParameter` in interface `ServletRequest`

------------------------------------------------------------------------

### getParameterMap

    public Map getParameterMap()

**Specified by:**  
`getParameterMap` in interface `ServletRequest`

------------------------------------------------------------------------

### getParameterNames

    public Enumeration getParameterNames()

**Specified by:**  
`getParameterNames` in interface `ServletRequest`

------------------------------------------------------------------------

### getParameterValues

    public String[] getParameterValues(String name)

**Specified by:**  
`getParameterValues` in interface `ServletRequest`

------------------------------------------------------------------------

### getProtocol

    public String getProtocol()

**Specified by:**  
`getProtocol` in interface `ServletRequest`

------------------------------------------------------------------------

### getReader

    public BufferedReader getReader()

**Specified by:**  
`getReader` in interface `ServletRequest`

------------------------------------------------------------------------

### getRealPath

    public String getRealPath(String path)

**Specified by:**  
`getRealPath` in interface `ServletRequest`

------------------------------------------------------------------------

### getRemoteAddr

    public String getRemoteAddr()

**Specified by:**  
`getRemoteAddr` in interface `ServletRequest`

------------------------------------------------------------------------

### getRemoteHost

    public String getRemoteHost()

**Specified by:**  
`getRemoteHost` in interface `ServletRequest`

------------------------------------------------------------------------

### getRequestDispatcher

    public RequestDispatcher getRequestDispatcher(String path)

**Specified by:**  
`getRequestDispatcher` in interface `ServletRequest`

------------------------------------------------------------------------

### getScheme

    public String getScheme()

**Specified by:**  
`getScheme` in interface `ServletRequest`

------------------------------------------------------------------------

### getServerName

    public String getServerName()

**Specified by:**  
`getServerName` in interface `ServletRequest`

------------------------------------------------------------------------

### getServerPort

    public int getServerPort()

**Specified by:**  
`getServerPort` in interface `ServletRequest`

------------------------------------------------------------------------

### isSecure

    public boolean isSecure()

**Specified by:**  
`isSecure` in interface `ServletRequest`

------------------------------------------------------------------------

### removeAttribute

    public void removeAttribute(String name)

**Specified by:**  
`removeAttribute` in interface `ServletRequest`

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String name,
                             Object value)

**Specified by:**  
`setAttribute` in interface `ServletRequest`

------------------------------------------------------------------------

### setCharacterEncoding

    public void setCharacterEncoding(String name)

**Specified by:**  
`setCharacterEncoding` in interface `ServletRequest`

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
<td align="left"><a href="class-use/MockHttpServletRequest.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockFormBean.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpServletResponse.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockHttpServletRequest.html"><strong>FRAMES</strong></a>    <a href="MockHttpServletRequest.html"><strong>NO FRAMES</strong></a>    
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
