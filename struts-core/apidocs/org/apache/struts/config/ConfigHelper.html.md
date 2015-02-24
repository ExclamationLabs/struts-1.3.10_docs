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
<td align="left"><a href="class-use/ConfigHelper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/BaseConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigHelperInterface.html" title="interface in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigHelper.html"><strong>FRAMES</strong></a>    <a href="ConfigHelper.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class ConfigHelper
------------------------

    java.lang.Object
      org.apache.struts.config.ConfigHelper

**All Implemented Interfaces:**  
[ConfigHelperInterface](../../../../org/apache/struts/config/ConfigHelperInterface.html.md "interface in org.apache.struts.config")

------------------------------------------------------------------------

    public class ConfigHelper

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [ConfigHelperInterface](../../../../org/apache/struts/config/ConfigHelperInterface.html.md "interface in org.apache.struts.config")

NOTE: THIS CLASS IS UNDER ACTIVE DEVELOPMENT. THE CURRENT CODE IS WRITTEN FOR CLARITY NOT EFFICIENCY. NOT EVERY API FUNCTION HAS BEEN IMPLEMENTED YET.

A helper object to expose the Struts shared resources, which are be stored in the application, session, or request contexts, as appropriate.

An instance should be created for each request processed. The methods which return resources from the request or session contexts are not thread-safe.

Provided for use by other servlets in the application so they can easily access the Struts shared resources.

The resources are stored under attributes in the application, session, or request contexts.

The ActionConfig methods simply return the resources from under the context and key used by the Struts ActionServlet when the resources are created.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-14 02:09:06 -0400 (Sat, 14 May 2005) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                               |
|-------------------------------------------------------------------------------------------------------|
| ` ConfigHelper()`                                                                                     
                                                                                                        |
| ` ConfigHelper(ServletContext application, HttpServletRequest request, HttpServletResponse response)` 
                                                                                                        |

  <span id="method_summary"></span>

**Method Summary**

` String`

` action(String path)`
            Wrapper for getAction(String)

` String`

` getAction(String path)`
            Return the URL for the specified ActionMapping, otherwise return `null`.

` ActionForm`

` getActionForm()`
            Retrieve and return the `ActionForm` bean associated with this mapping, creating and stashing one if necessary.

` ActionForward`

` getActionForward(String name)`
            Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

` ActionMapping`

` getActionMapping(String path)`
            Return the mapping associated with the specified request path, if any; otherwise return `null`.

` String`

` getActionMappingName(String action)`
            Return the form action converted into an action mapping path.

` String`

` getActionMappingURL(String action)`
            Return the form action converted into a server-relative URL.

` ActionMessages`

` getActionMessages()`
            The `org.apache.struts.action.ActionFormBeans` collection for this application.

` String`

` getBaseRef()`
            Renders the reference for a HTML element.

` String`

` getEncodeURL(String url)`
            Return the url encoded to maintain the user session, if any.

` Throwable`

` getException()`
            The runtime JspException that may be been thrown by a Struts tag extension, or compatible presentation extension, and placed in the request.

` ActionFormBean`

` getFormBean(String name)`
            Return the form bean definition associated with the specified logical name, if any; otherwise return `null`.

` String`

` getLink(String name)`
            Return the path for the specified forward, otherwise return `null`.

` ActionMapping`

` getMapping()`
            The `org.apache.struts.ActionMapping` instance for this request.

` String`

` getMessage(String key)`
            Return the localized message for the specified key, otherwise return `null`.

` String`

` getMessage(String key, Object[] args)`
            Look up and return a message string, based on the specified parameters.

` MessageResources`

` getMessageResources()`
            The application resources for this application.

` MultipartRequestWrapper`

` getMultipartRequestWrapper()`
            The multipart object for this request.

` String`

` getOrigRef()`
            Renders the reference for a HTML element

` String`

` getServletMapping()`
            The path-mapped pattern (`/action/*`) or extension mapped pattern ((`*.do`) used to determine our Action URIs in this application.

` String`

` getToken()`
            The transaction token stored in this session, if it is used.

` boolean`

` isMessage(String key)`
            Return true if a message string for the specified message key is present for the user's Locale.

` String`

` link(String name)`
            Wrapper for getLink(String)

` String`

` message(String key)`
            Wrapper for getMessage(String)

` String`

` message(String key, Object[] args)`
            Wrapper for getMessage(String,Object[])

` void`

` setApplication(ServletContext application)`
            Set the application associated with this instance.

` void`

` setForward(ActionForward forward)`
           Set the forward associated with this instance.

` void`

` setRequest(HttpServletRequest request)`
            Set the request associated with this object.

` void`

` setResources(ServletContext application, HttpServletRequest request, HttpServletResponse response)`
            Set the application and request for this object instance.

` void`

` setResponse(HttpServletResponse response)`
            Set the response associated with this isntance.

` void`

` setSession(HttpSession session)`
            Set the session associated with this instance.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ConfigHelper

    public ConfigHelper()

------------------------------------------------------------------------

### ConfigHelper

    public ConfigHelper(ServletContext application,
                        HttpServletRequest request,
                        HttpServletResponse response)

<span id="method_detail"></span>

**Method Detail**

### setApplication

    public void setApplication(ServletContext application)

Set the application associated with this instance. [servlet.getServletContext()]

------------------------------------------------------------------------

### setSession

    public void setSession(HttpSession session)

Set the session associated with this instance.

------------------------------------------------------------------------

### setRequest

    public void setRequest(HttpServletRequest request)

Set the request associated with this object. Session object is also set or cleared.

------------------------------------------------------------------------

### setResponse

    public void setResponse(HttpServletResponse response)

Set the response associated with this isntance. Session object is also set or cleared.

------------------------------------------------------------------------

### setForward

    public void setForward(ActionForward forward)

Set the forward associated with this instance.

------------------------------------------------------------------------

### setResources

    public void setResources(ServletContext application,
                             HttpServletRequest request,
                             HttpServletResponse response)

Set the application and request for this object instance. The ServletContext can be set by any servlet in the application. The request should be the instant request. Most of the other methods retrieve their own objects by reference to the application, request, or session attributes. Do not call other methods without setting these first! This is also called by the convenience constructor.

**Parameters:**  
`application` - - The associated ServletContext.

`request` - - The associated HTTP request.

`response` - - The associated HTTP response.

------------------------------------------------------------------------

### getActionMessages

    public ActionMessages getActionMessages()

**Description copied from interface: ` ConfigHelperInterface`**

The `org.apache.struts.action.ActionFormBeans` collection for this application.

**Specified by:**  
` getActionMessages` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources()

The application resources for this application.

**Specified by:**  
` getMessageResources` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getServletMapping

    public String getServletMapping()

The path-mapped pattern (`/action/*`) or extension mapped pattern ((`*.do`) used to determine our Action URIs in this application.

**Specified by:**  
` getServletMapping` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getToken

    public String getToken()

The transaction token stored in this session, if it is used.

**Specified by:**  
` getToken` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getException

    public Throwable getException()

The runtime JspException that may be been thrown by a Struts tag extension, or compatible presentation extension, and placed in the request.

**Specified by:**  
` getException` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getMultipartRequestWrapper

    public MultipartRequestWrapper getMultipartRequestWrapper()

The multipart object for this request.

**Specified by:**  
` getMultipartRequestWrapper` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getMapping

    public ActionMapping getMapping()

The `org.apache.struts.ActionMapping` instance for this request.

**Specified by:**  
` getMapping` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### isMessage

    public boolean isMessage(String key)

Return true if a message string for the specified message key is present for the user's Locale.

**Specified by:**  
` isMessage` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`key` - Message key

------------------------------------------------------------------------

### getActionForm

    public ActionForm getActionForm()

**Description copied from interface: ` ConfigHelperInterface`**

Retrieve and return the `ActionForm` bean associated with this mapping, creating and stashing one if necessary. If there is no form bean associated with this mapping, return `null`.

**Specified by:**  
` getActionForm` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getFormBean

    public ActionFormBean getFormBean(String name)

Return the form bean definition associated with the specified logical name, if any; otherwise return `null`.

**Specified by:**  
` getFormBean` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`name` - Logical name of the requested form bean definition

------------------------------------------------------------------------

### getActionForward

    public ActionForward getActionForward(String name)

Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

**Specified by:**  
` getActionForward` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`name` - Logical name of the requested forwarding

------------------------------------------------------------------------

### getActionMapping

    public ActionMapping getActionMapping(String path)

Return the mapping associated with the specified request path, if any; otherwise return `null`.

**Specified by:**  
` getActionMapping` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`path` - Request path for which a mapping is requested

------------------------------------------------------------------------

### getActionMappingName

    public String getActionMappingName(String action)

Return the form action converted into an action mapping path. The value of the `action` property is manipulated as follows in computing the name of the requested mapping:

-   Any filename extension is removed (on the theory that extension mapping is being used to select the controller servlet).
-   If the resulting value does not start with a slash, then a slash is prepended.

**Specified by:**  
` getActionMappingName` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getActionMappingURL

    public String getActionMappingURL(String action)

Return the form action converted into a server-relative URL.

**Specified by:**  
` getActionMappingURL` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getEncodeURL

    public String getEncodeURL(String url)

Return the url encoded to maintain the user session, if any.

**Specified by:**  
` getEncodeURL` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getOrigRef

    public String getOrigRef()

Renders the reference for a HTML element

**Specified by:**  
` getOrigRef` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getBaseRef

    public String getBaseRef()

Renders the reference for a HTML element.

**Specified by:**  
` getBaseRef` in interface `ConfigHelperInterface`

------------------------------------------------------------------------

### getLink

    public String getLink(String name)

Return the path for the specified forward, otherwise return `null`.

**Specified by:**  
` getLink` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`name` - Name given to local or global forward.

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key)

Return the localized message for the specified key, otherwise return `null`.

**Specified by:**  
` getMessage` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`key` - Message key

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object[] args)

Look up and return a message string, based on the specified parameters.

**Specified by:**  
` getMessage` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`key` - Message key to be looked up and returned

`args` - Replacement parameters for this message

------------------------------------------------------------------------

### getAction

    public String getAction(String path)

Return the URL for the specified ActionMapping, otherwise return `null`.

**Specified by:**  
` getAction` in interface `ConfigHelperInterface`

<!-- -->

**Parameters:**  
`path` - Name given to local or global forward.

------------------------------------------------------------------------

### link

    public String link(String name)

Wrapper for getLink(String)

**Parameters:**  
`name` - Name given to local or global forward.

------------------------------------------------------------------------

### message

    public String message(String key)

Wrapper for getMessage(String)

**Parameters:**  
`key` - Message key

------------------------------------------------------------------------

### message

    public String message(String key,
                          Object[] args)

Wrapper for getMessage(String,Object[])

**Parameters:**  
`key` - Message key to be looked up and returned

`args` - Replacement parameters for this message

------------------------------------------------------------------------

### action

    public String action(String path)

Wrapper for getAction(String)

**Parameters:**  
`path` - Name given to local or global forward.

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
<td align="left"><a href="class-use/ConfigHelper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/BaseConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigHelperInterface.html" title="interface in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigHelper.html"><strong>FRAMES</strong></a>    <a href="ConfigHelper.html"><strong>NO FRAMES</strong></a>    
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
