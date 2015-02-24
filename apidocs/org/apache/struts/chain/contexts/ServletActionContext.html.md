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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ServletActionContext.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/MockActionContext.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/WebActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ServletActionContext.html"><strong>FRAMES</strong></a>    <a href="ServletActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.contexts
 Class ServletActionContext
--------------------------------

    java.lang.Object
      org.apache.struts.chain.contexts.ContextWrapper
          org.apache.struts.chain.contexts.ActionContextBase
              org.apache.struts.chain.contexts.WebActionContext
                  org.apache.struts.chain.contexts.ServletActionContext

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util"), org.apache.commons.chain.Context, [ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public class ServletActionContext

extends [WebActionContext](../../../../../org/apache/struts/chain/contexts/WebActionContext.html.md "class in org.apache.struts.chain.contexts")

Implement ActionContext interface while making Servlet API-specific values available.

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_java.util.Map"></span>

| **Nested classes/interfaces inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Map.Entry<K,V>`                                                                                                                                                                      |

  <span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase"></span>

| **Fields inherited from class org.apache.struts.chain.contexts.[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")**                                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ACTION_CONFIG_KEY,  ACTION_FORM_KEY,  ACTION_KEY,  CANCEL_KEY,  ERROR_ACTION_MESSAGES_KEY,  EXCEPTION_KEY,  FORWARD_CONFIG_KEY,  INCLUDE_KEY,  LOCALE_KEY,  MESSAGE_ACTION_MESSAGES_KEY,  MESSAGE_RESOURCES_KEY,  MODULE_CONFIG_KEY,  token,  TOKEN_KEY,  TRANSACTION_TOKEN_KEY,  VALID_KEY` |

 <span id="fields_inherited_from_class_org.apache.struts.chain.contexts.ActionContext"></span>

| **Fields inherited from interface org.apache.struts.chain.contexts.[ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` APPLICATION_SCOPE,  REQUEST_SCOPE,  SESSION_SCOPE`                                                                                                                                                     |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                       |
|---------------------------------------------------------------------------------------------------------------|
| ` ServletActionContext(ServletContext context, HttpServletRequest request, HttpServletResponse response)`     
             Instantiate this Context for a given ServletContext, HttpServletRequest, and HttpServletResponse.  |
| ` ServletActionContext(org.apache.commons.chain.web.servlet.ServletWebContext context)`                       
             Instantiate this composite by wrapping a ServletWebContext.                                        |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addErrors(ActionMessages errors)`
            Append the given errors keys to an internal cache, creating the cache if one is not already present.

` void`

` addMessages(ActionMessages messages)`
            Append the given messages keys to an internal cache, creating the cache if one is not already present.

` String`

` generateToken()`
           Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

` ActionServlet`

` getActionServlet()`
            Return the ActionServlet for this context.

` ServletContext`

` getContext()`
            Return the ServletContext for this context.

` ActionMessages`

` getErrors()`
            Retrieve error messages from an internal cache, creating an empty cache if one is not already present.

` MessageResources`

` getMessageResources()`
           Return the default message resources for the current module.

` MessageResources`

` getMessageResources(String key)`
           Return the specified message resources for the current module.

` ActionMessages`

` getMessages()`
            Retrieve messages from an internal cache, creating an empty cache if one is not already present.

` HttpServletRequest`

` getRequest()`
            Return the HttpServletRequest for this context.

` HttpServletResponse`

` getResponse()`
            Return the HttpServletResponse for this context.

` boolean`

` isTokenValid(boolean reset)`
            Indicate whether a transaction token is stored in the "session" scope for this context, optionally clearing the token, so that the next check would return false.

` void`

` release()`
           Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

` void`

` resetToken()`
            Clear any transactional token stored in the "session" scope for this context, so that the next check would return false.

` void`

` saveErrors(ActionMessages errors)`
            Save the given error messages to the internal cache, clearing any previous messages in the cache.

` void`

` saveMessages(ActionMessages messages)`
            Save the given messages to the internal cache, clearing any previous messages in the cache.

` void`

` saveToken()`
            Save a new transaction token in the "session" scope for this context, creating new resources, if needed.

`protected  org.apache.commons.chain.web.servlet.ServletWebContext`

` servletWebContext()`
            Provide the ServletWebContext for this composite.

` void`

` setActionConfig(ActionConfig actionConfig)`
            Set the ActionConfig class contains the details for processing this request.

` void`

` setActionServlet(ActionServlet servlet)`
            Set the ActionServlet instance for this context.

` void`

` setMessageResources(MessageResources resources)`
           Set the default message resources for the current module.

` void`

` setMessageResources(String key, MessageResources resources)`
            Store the mesasage resources for the current module under the given request attribute key.

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.WebActionContext"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[WebActionContext](../../../../../org/apache/struts/chain/contexts/WebActionContext.html.md "class in org.apache.struts.chain.contexts")**                              |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getApplicationScope,  getCancelled,  getHeader,  getHeaderValues,  getInitParam,  getModuleConfig,  getParam,  getParameterMap,  getParamValues,  getRequestScope,  getSessionScope,  setCancelled,  setModuleConfig,  webContext` |

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")**                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addActionMessages,  findOrCreateActionForm,  findOrCreateActionForm,  getAction,  getActionConfig,  getActionForm,  getException,  getFormValid,  getForwardConfig,  getInclude,  getLocale,  getLogger,  getScope,  getTokenGeneratorId,  isTokenValid,  saveActionMessages,  saveActionMessages,  saveMessages,  setAction,  setActionForm,  setException,  setFormValid,  setForwardConfig,  setInclude,  setLocale,  setLogger` |

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ContextWrapper"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[ContextWrapper](../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md "class in org.apache.struts.chain.contexts")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` clear,  containsKey,  containsValue,  entrySet,  get,  getBaseContext,  isEmpty,  keySet,  put,  putAll,  remove,  size,  values`                                                                 |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_java.util.Map"></span>

| **Methods inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clear, containsKey, containsValue, entrySet, equals, get, hashCode, isEmpty, keySet, put, putAll, remove, size, values`                                            |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ServletActionContext

    public ServletActionContext(org.apache.commons.chain.web.servlet.ServletWebContext context)

Instantiate this composite by wrapping a ServletWebContext.

**Parameters:**  
`context` - The ServletWebContext to wrap

------------------------------------------------------------------------

### ServletActionContext

    public ServletActionContext(ServletContext context,
                                HttpServletRequest request,
                                HttpServletResponse response)

Instantiate this Context for a given ServletContext, HttpServletRequest, and HttpServletResponse.

**Parameters:**  
`context` - The instant ServletContext

`request` - The instant HttpServletRequest

`response` - The instant HttpServletResponse

<span id="method_detail"></span>

**Method Detail**

### servletWebContext

    protected org.apache.commons.chain.web.servlet.ServletWebContext servletWebContext()

Provide the ServletWebContext for this composite.

**Returns:**  
Our ServletWebContext

------------------------------------------------------------------------

### release

    public void release()

**Description copied from interface: ` ActionContext`**

Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

**Specified by:**  
` release` in interface `ActionContext`

**Overrides:**  
` release` in class `WebActionContext`

------------------------------------------------------------------------

### getContext

    public ServletContext getContext()

Return the ServletContext for this context.

**Returns:**  
Our ServletContext

------------------------------------------------------------------------

### getRequest

    public HttpServletRequest getRequest()

Return the HttpServletRequest for this context.

**Returns:**  
Our HttpServletRequest

------------------------------------------------------------------------

### getResponse

    public HttpServletResponse getResponse()

Return the HttpServletResponse for this context.

**Returns:**  
Our HttpServletResponse

------------------------------------------------------------------------

### getActionServlet

    public ActionServlet getActionServlet()

Return the ActionServlet for this context.

**Returns:**  
Our ActionServlet

------------------------------------------------------------------------

### setActionServlet

    public void setActionServlet(ActionServlet servlet)

Set the ActionServlet instance for this context.

**Parameters:**  
`servlet` - Our ActionServlet instance

------------------------------------------------------------------------

### setActionConfig

    public void setActionConfig(ActionConfig actionConfig)

**Description copied from interface: ` ActionContext`**

Set the ActionConfig class contains the details for processing this request.

**Specified by:**  
` setActionConfig` in interface `ActionContext`

**Overrides:**  
` setActionConfig` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`actionConfig` - The ActionConfig class to use with this request

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources()

**Description copied from interface: ` ActionContext`**

Return the default message resources for the current module.

**Specified by:**  
` getMessageResources` in interface `ActionContext`

**Overrides:**  
` getMessageResources` in class `ActionContextBase`

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources(String key)

**Description copied from interface: ` ActionContext`**

Return the specified message resources for the current module.

**Specified by:**  
` getMessageResources` in interface `ActionContext`

**Overrides:**  
` getMessageResources` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`key` - The key specified in the `<message-resources>` element for the requested bundle

------------------------------------------------------------------------

### setMessageResources

    public void setMessageResources(MessageResources resources)

**Description copied from interface: ` ActionContext`**

Set the default message resources for the current module.

**Specified by:**  
` setMessageResources` in interface `ActionContext`

**Overrides:**  
` setMessageResources` in class `ActionContextBase`

------------------------------------------------------------------------

### setMessageResources

    public void setMessageResources(String key,
                                    MessageResources resources)

Store the mesasage resources for the current module under the given request attribute key.

**Parameters:**  
`key` - Request attribute key

`resources` - Message resouces to store

------------------------------------------------------------------------

### saveErrors

    public void saveErrors(ActionMessages errors)

**Description copied from interface: ` ActionContext`**

Save the given error messages to the internal cache, clearing any previous messages in the cache.

If the parameter is null or empty, the internal cache is removed.

**Specified by:**  
` saveErrors` in interface `ActionContext`

**Overrides:**  
` saveErrors` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`errors` - ActionMesssages to cache as errors

------------------------------------------------------------------------

### saveMessages

    public void saveMessages(ActionMessages messages)

**Description copied from interface: ` ActionContext`**

Save the given messages to the internal cache, clearing any previous messages in the cache.

If the parameter is null or empty, the internal cache is removed.

**Specified by:**  
` saveMessages` in interface `ActionContext`

**Overrides:**  
` saveMessages` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`messages` - ActionMesssages to cache

------------------------------------------------------------------------

### addMessages

    public void addMessages(ActionMessages messages)

**Description copied from interface: ` ActionContext`**

Append the given messages keys to an internal cache, creating the cache if one is not already present.

**Specified by:**  
` addMessages` in interface `ActionContext`

**Overrides:**  
` addMessages` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`messages` - New ActionMessages to cache

------------------------------------------------------------------------

### addErrors

    public void addErrors(ActionMessages errors)

**Description copied from interface: ` ActionContext`**

Append the given errors keys to an internal cache, creating the cache if one is not already present.

**Specified by:**  
` addErrors` in interface `ActionContext`

**Overrides:**  
` addErrors` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`errors` - New ActionMessages to cache as errors

------------------------------------------------------------------------

### getErrors

    public ActionMessages getErrors()

**Description copied from interface: ` ActionContext`**

Retrieve error messages from an internal cache, creating an empty cache if one is not already present.

**Specified by:**  
` getErrors` in interface `ActionContext`

**Overrides:**  
` getErrors` in class `ActionContextBase`

<!-- -->

**Returns:**  
The ActionMessage cache for errors

------------------------------------------------------------------------

### getMessages

    public ActionMessages getMessages()

**Description copied from interface: ` ActionContext`**

Retrieve messages from an internal cache, creating an empty cache if one is not already present.

**Specified by:**  
` getMessages` in interface `ActionContext`

**Overrides:**  
` getMessages` in class `ActionContextBase`

<!-- -->

**Returns:**  
The ActionMessage cache for errors

------------------------------------------------------------------------

### saveToken

    public void saveToken()

**Description copied from interface: ` ActionContext`**

Save a new transaction token in the "session" scope for this context, creating new resources, if needed.

**Specified by:**  
` saveToken` in interface `ActionContext`

**Overrides:**  
` saveToken` in class `ActionContextBase`

------------------------------------------------------------------------

### generateToken

    public String generateToken()

**Description copied from interface: ` ActionContext`**

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

**Specified by:**  
` generateToken` in interface `ActionContext`

**Overrides:**  
` generateToken` in class `ActionContextBase`

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid(boolean reset)

**Description copied from interface: ` ActionContext`**

Indicate whether a transaction token is stored in the "session" scope for this context, optionally clearing the token, so that the next check would return false.

**Specified by:**  
` isTokenValid` in interface `ActionContext`

**Overrides:**  
` isTokenValid` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`reset` - On true, clear the transactional token

------------------------------------------------------------------------

### resetToken

    public void resetToken()

**Description copied from interface: ` ActionContext`**

Clear any transactional token stored in the "session" scope for this context, so that the next check would return false.

**Specified by:**  
` resetToken` in interface `ActionContext`

**Overrides:**  
` resetToken` in class `ActionContextBase`

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ServletActionContext.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/MockActionContext.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/WebActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ServletActionContext.html"><strong>FRAMES</strong></a>    <a href="ServletActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
