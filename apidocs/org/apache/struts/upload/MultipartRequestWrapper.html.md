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
<td align="left"><a href="class-use/MultipartRequestWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/MultipartRequestHandler.html.md" title="interface in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/MultipartRequestWrapper.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestWrapper.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.upload
 Class MultipartRequestWrapper
------------------------------

    java.lang.Object
      javax.servlet.ServletRequestWrapper
          javax.servlet.http.HttpServletRequestWrapper
              org.apache.struts.upload.MultipartRequestWrapper

**All Implemented Interfaces:**  
[HttpServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequest.html.md?is-external=true "class or interface in javax.servlet.http"), [ServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletRequest.html?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class MultipartRequestWrapper

extends [HttpServletRequestWrapper](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequestWrapper.html.md?is-external=true "class or interface in javax.servlet.http")

This class functions as a wrapper around HttpServletRequest to provide working getParameter methods for multipart requests.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Map`

` parameters`
            The parameters for this multipart request

 <span id="fields_inherited_from_class_javax.servlet.http.HttpServletRequest"></span>

| **Fields inherited from interface javax.servlet.http.[HttpServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequest.html.md?is-external=true "class or interface in javax.servlet.http")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `BASIC_AUTH, CLIENT_CERT_AUTH, DIGEST_AUTH, FORM_AUTH`                                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` MultipartRequestWrapper(HttpServletRequest request)` 
                                                         |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getParameter(String name)`
            Attempts to get a parameter for this request.

` Map`

` getParameterMap()`
            Combines the parameters stored here with those in the underlying request.

` Enumeration`

` getParameterNames()`
            Returns the names of the parameters for this request.

` String[]`

` getParameterValues(String name)`
            Returns the values of a parameter in this request.

` void`

` setParameter(String name, String value)`
            Sets a parameter for this request.

 <span id="methods_inherited_from_class_javax.servlet.http.HttpServletRequestWrapper"></span>

| **Methods inherited from class javax.servlet.http.[HttpServletRequestWrapper](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServletRequestWrapper.html.md?is-external=true "class or interface in javax.servlet.http")**                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getAuthType, getContextPath, getCookies, getDateHeader, getHeader, getHeaderNames, getHeaders, getIntHeader, getMethod, getPathInfo, getPathTranslated, getQueryString, getRemoteUser, getRequestedSessionId, getRequestURI, getRequestURL, getServletPath, getSession, getSession, getUserPrincipal, isRequestedSessionIdFromCookie, isRequestedSessionIdFromUrl, isRequestedSessionIdFromURL, isRequestedSessionIdValid, isUserInRole` |

 <span id="methods_inherited_from_class_javax.servlet.ServletRequestWrapper"></span>

| **Methods inherited from class javax.servlet.[ServletRequestWrapper](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletRequestWrapper.html.md?is-external=true "class or interface in javax.servlet")**                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getAttribute, getAttributeNames, getCharacterEncoding, getContentLength, getContentType, getInputStream, getLocale, getLocales, getProtocol, getReader, getRealPath, getRemoteAddr, getRemoteHost, getRequest, getRequestDispatcher, getScheme, getServerName, getServerPort, isSecure, removeAttribute, setAttribute, setCharacterEncoding, setRequest` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_javax.servlet.ServletRequest"></span>

| **Methods inherited from interface javax.servlet.[ServletRequest](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletRequest.html.md?is-external=true "class or interface in javax.servlet")**                                                                                                                               |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getAttribute, getAttributeNames, getCharacterEncoding, getContentLength, getContentType, getInputStream, getLocale, getLocales, getProtocol, getReader, getRealPath, getRemoteAddr, getRemoteHost, getRequestDispatcher, getScheme, getServerName, getServerPort, isSecure, removeAttribute, setAttribute, setCharacterEncoding` |

 

<span id="field_detail"></span>

**Field Detail**

<span id="parameters"></span>

### parameters

    protected Map parameters

The parameters for this multipart request

<span id="constructor_detail"></span>

**Constructor Detail**

### MultipartRequestWrapper

    public MultipartRequestWrapper(HttpServletRequest request)

<span id="method_detail"></span>

**Method Detail**

### setParameter

    public void setParameter(String name,
                             String value)

Sets a parameter for this request. The parameter is actually separate from the request parameters, but calling on the getParameter() methods of this class will work as if they weren't.

------------------------------------------------------------------------

### getParameter

    public String getParameter(String name)

Attempts to get a parameter for this request. It first looks in the underlying HttpServletRequest object for the parameter, and if that doesn't exist it looks for the parameters retrieved from the multipart request

**Specified by:**  
`getParameter` in interface `ServletRequest`

**Overrides:**  
`getParameter` in class `ServletRequestWrapper`

------------------------------------------------------------------------

### getParameterNames

    public Enumeration getParameterNames()

Returns the names of the parameters for this request. The enumeration consists of the normal request parameter names plus the parameters read from the multipart request

**Specified by:**  
`getParameterNames` in interface `ServletRequest`

**Overrides:**  
`getParameterNames` in class `ServletRequestWrapper`

------------------------------------------------------------------------

### getParameterValues

    public String[] getParameterValues(String name)

Returns the values of a parameter in this request. It first looks in the underlying HttpServletRequest object for the parameter, and if that doesn't exist it looks for the parameter retrieved from the multipart request.

**Specified by:**  
`getParameterValues` in interface `ServletRequest`

**Overrides:**  
`getParameterValues` in class `ServletRequestWrapper`

------------------------------------------------------------------------

### getParameterMap

    public Map getParameterMap()

Combines the parameters stored here with those in the underlying request. If paramater values in the underlying request take precedence over those stored here.

**Specified by:**  
`getParameterMap` in interface `ServletRequest`

**Overrides:**  
`getParameterMap` in class `ServletRequestWrapper`

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
<td align="left"><a href="class-use/MultipartRequestWrapper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/upload/MultipartRequestHandler.html.md" title="interface in org.apache.struts.upload"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/upload/MultipartRequestWrapper.html"><strong>FRAMES</strong></a>    <a href="MultipartRequestWrapper.html"><strong>NO FRAMES</strong></a>    
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
