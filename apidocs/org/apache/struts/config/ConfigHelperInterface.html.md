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
<td align="left"><a href="class-use/ConfigHelperInterface.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigHelper.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigRuleSet.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigHelperInterface.html"><strong>FRAMES</strong></a>    <a href="ConfigHelperInterface.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config
 Interface ConfigHelperInterface
--------------------------------

**All Known Implementing Classes:**  
[ConfigHelper](../../../../org/apache/struts/config/ConfigHelper.html.md "class in org.apache.struts.config")

------------------------------------------------------------------------

    public interface ConfigHelperInterface

NOTE: THIS CLASS IS UNDER ACTIVE DEVELOPMENT. THE CURRENT CODE IS WRITTEN FOR CLARITY NOT EFFICIENCY. NOT EVERY API FUNCTION HAS BEEN IMPLEMENTED YET.

A helper object to expose the Struts shared resources, which are be stored in the application, session, or request contexts, as appropriate.

An instance should be created for each request processed. The methods which return resources from the request or session contexts are not thread-safe.

Provided for use by other servlets in the application so they can easily access the Struts shared resources.

The resources are stored under attributes in the application, session, or request contexts.

The ActionConfig methods simply return the resources from under the context and key used by the Struts ActionServlet when the resources are created.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

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
            Renders the reference for a HTML element

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

 

<span id="method_detail"></span>

**Method Detail**

### getActionMessages

    ActionMessages getActionMessages()

The `org.apache.struts.action.ActionFormBeans` collection for this application.

------------------------------------------------------------------------

### getMessageResources

    MessageResources getMessageResources()

The application resources for this application.

------------------------------------------------------------------------

### getServletMapping

    String getServletMapping()

The path-mapped pattern (`/action/*`) or extension mapped pattern ((`*.do`) used to determine our Action URIs in this application.

------------------------------------------------------------------------

### getToken

    String getToken()

The transaction token stored in this session, if it is used.

------------------------------------------------------------------------

### getException

    Throwable getException()

The runtime JspException that may be been thrown by a Struts tag extension, or compatible presentation extension, and placed in the request.

------------------------------------------------------------------------

### getMultipartRequestWrapper

    MultipartRequestWrapper getMultipartRequestWrapper()

The multipart object for this request.

------------------------------------------------------------------------

### getMapping

    ActionMapping getMapping()

The `org.apache.struts.ActionMapping` instance for this request.

------------------------------------------------------------------------

### isMessage

    boolean isMessage(String key)

Return true if a message string for the specified message key is present for the user's Locale.

**Parameters:**  
`key` - Message key

------------------------------------------------------------------------

### getActionForm

    ActionForm getActionForm()

Retrieve and return the `ActionForm` bean associated with this mapping, creating and stashing one if necessary. If there is no form bean associated with this mapping, return `null`.

------------------------------------------------------------------------

### getFormBean

    ActionFormBean getFormBean(String name)

Return the form bean definition associated with the specified logical name, if any; otherwise return `null`.

**Parameters:**  
`name` - Logical name of the requested form bean definition

------------------------------------------------------------------------

### getActionForward

    ActionForward getActionForward(String name)

Return the forwarding associated with the specified logical name, if any; otherwise return `null`.

**Parameters:**  
`name` - Logical name of the requested forwarding

------------------------------------------------------------------------

### getActionMapping

    ActionMapping getActionMapping(String path)

Return the mapping associated with the specified request path, if any; otherwise return `null`.

**Parameters:**  
`path` - Request path for which a mapping is requested

------------------------------------------------------------------------

### getActionMappingName

    String getActionMappingName(String action)

Return the form action converted into an action mapping path. The value of the `action` property is manipulated as follows in computing the name of the requested mapping:

-   Any filename extension is removed (on the theory that extension mapping is being used to select the controller servlet).
-   If the resulting value does not start with a slash, then a slash is prepended.

:FIXME: Bad assumption =:o)

------------------------------------------------------------------------

### getActionMappingURL

    String getActionMappingURL(String action)

Return the form action converted into a server-relative URL.

------------------------------------------------------------------------

### getEncodeURL

    String getEncodeURL(String url)

Return the url encoded to maintain the user session, if any.

------------------------------------------------------------------------

### getOrigRef

    String getOrigRef()

Renders the reference for a HTML element

------------------------------------------------------------------------

### getBaseRef

    String getBaseRef()

Renders the reference for a HTML element

------------------------------------------------------------------------

### getLink

    String getLink(String name)

Return the path for the specified forward, otherwise return `null`.

**Parameters:**  
`name` - Name given to local or global forward.

------------------------------------------------------------------------

### getMessage

    String getMessage(String key)

Return the localized message for the specified key, otherwise return `null`.

**Parameters:**  
`key` - Message key

------------------------------------------------------------------------

### getMessage

    String getMessage(String key,
                      Object[] args)

Look up and return a message string, based on the specified parameters.

**Parameters:**  
`key` - Message key to be looked up and returned

`args` - Replacement parameters for this message

------------------------------------------------------------------------

### getAction

    String getAction(String path)

Return the URL for the specified ActionMapping, otherwise return `null`.

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
<td align="left"><a href="class-use/ConfigHelperInterface.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigHelper.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ConfigRuleSet.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ConfigHelperInterface.html"><strong>FRAMES</strong></a>    <a href="ConfigHelperInterface.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
