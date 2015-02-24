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
<td align="left"><a href="class-use/WebActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ServletActionContext.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/WebActionContext.html"><strong>FRAMES</strong></a>    <a href="WebActionContext.html"><strong>NO FRAMES</strong></a>    
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
 Class WebActionContext
--------------------------------

    java.lang.Object
      org.apache.struts.chain.contexts.ContextWrapper
          org.apache.struts.chain.contexts.ActionContextBase
              org.apache.struts.chain.contexts.WebActionContext

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util"), org.apache.commons.chain.Context, [ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

<!-- -->

**Direct Known Subclasses:**  
[ServletActionContext](../../../../../org/apache/struts/chain/contexts/ServletActionContext.html.md "class in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public class WebActionContext

extends [ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")

Provide a Subclass of ActionContextBase which is understood to be wrapping an instance of `org.apache.commons.chain.web.WebContext`.

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

| **Constructor Summary**                                                      |
|------------------------------------------------------------------------------|
| ` WebActionContext(org.apache.commons.chain.web.WebContext context)`         
            Instantiate this composite by wrapping an instance of WebContext.  |

  <span id="method_summary"></span>

**Method Summary**

` Map`

` getApplicationScope()`
           Return a `Map` of Application scoped values.

` Boolean`

` getCancelled()`
            Indicate if the "cancel event" state is set for for this context,

` Map`

` getHeader()`
            Return an immutable Map that maps header names to the first (or only) header value (as a String).

` Map`

` getHeaderValues()`
            Return an immutable Map that maps header names to the set of all values specified in the request (as a String array).

` Map`

` getInitParam()`
            Return an immutable Map that maps context application initialization parameters to their values.

` ModuleConfig`

` getModuleConfig()`
            Get the ModuleConfig which is operative for the current request.

` Map`

` getParam()`
            Return a map whose keys are `String` request parameter names and whose values are `String` values.

` Map`

` getParameterMap()`
           Return a `Map` of parameters submitted by the user as part of this request.

` Map`

` getParamValues()`
            Return a map whose keys are `String` request parameter names and whose values are `String[]` values.

` Map`

` getRequestScope()`
           Return a `Map` of request scoped values.

` Map`

` getSessionScope()`
           Return a `Map` of Session scoped values.

` void`

` release()`
           Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

` void`

` setCancelled(Boolean cancelled)`
            Set the "cancel event" state for this context.

` void`

` setModuleConfig(ModuleConfig moduleConfig)`
            Set the ModuleConfig which is operative for the current request.

`protected  org.apache.commons.chain.web.WebContext`

` webContext()`
           Provide the wrapped WebContext for this composite.

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")**                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addActionMessages,  addErrors,  addMessages,  findOrCreateActionForm,  findOrCreateActionForm,  generateToken,  getAction,  getActionConfig,  getActionForm,  getErrors,  getException,  getFormValid,  getForwardConfig,  getInclude,  getLocale,  getLogger,  getMessageResources,  getMessageResources,  getMessages,  getScope,  getTokenGeneratorId,  isTokenValid,  isTokenValid,  resetToken,  saveActionMessages,  saveActionMessages,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setAction,  setActionConfig,  setActionForm,  setException,  setFormValid,  setForwardConfig,  setInclude,  setLocale,  setLogger,  setMessageResources` |

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

### WebActionContext

    public WebActionContext(org.apache.commons.chain.web.WebContext context)

Instantiate this composite by wrapping an instance of WebContext.

**Parameters:**  
`context` - The WebContext to wrap

<span id="method_detail"></span>

**Method Detail**

### webContext

    protected org.apache.commons.chain.web.WebContext webContext()

Provide the wrapped WebContext for this composite.

**Returns:**  
The wrapped WebContext

------------------------------------------------------------------------

### release

    public void release()

**Description copied from interface: ` ActionContext`**

Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

**Specified by:**  
` release` in interface `ActionContext`

**Overrides:**  
` release` in class `ActionContextBase`

------------------------------------------------------------------------

### getHeader

    public Map getHeader()

Return an immutable Map that maps header names to the first (or only) header value (as a String).

**Returns:**  
A immutable Map of web request header names

------------------------------------------------------------------------

### getHeaderValues

    public Map getHeaderValues()

Return an immutable Map that maps header names to the set of all values specified in the request (as a String array). Header names must be matched in a case-insensitive manner.

**Returns:**  
An immutable Map of web request header values

------------------------------------------------------------------------

### getInitParam

    public Map getInitParam()

Return an immutable Map that maps context application initialization parameters to their values.

**Returns:**  
An immutable Map of web context initialization parameters

------------------------------------------------------------------------

### getParam

    public Map getParam()

Return a map whose keys are `String` request parameter names and whose values are `String` values.

For parameters which were submitted with more than one value, only one value will be returned, as if one called `ServletRequest.getParameter(String)`

**Returns:**  
A map of web request parameters

------------------------------------------------------------------------

### getParamValues

    public Map getParamValues()

Return a map whose keys are `String` request parameter names and whose values are `String[]` values.

**Returns:**  
A map of web request parameter values (as an array)

------------------------------------------------------------------------

### getApplicationScope

    public Map getApplicationScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of Application scoped values.

This is implemented in analogy with the Application scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "application scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getApplicationScope` in interface `ActionContext`

**Specified by:**  
` getApplicationScope` in class `ActionContextBase`

<!-- -->

**Returns:**  
A Map of "application scope" attributes.

------------------------------------------------------------------------

### getRequestScope

    public Map getRequestScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of request scoped values. A request is understood as the fundamental motivation for any particular instance of an `ActionContext`.

This is implemented in analogy with the Request Context in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "request scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getRequestScope` in interface `ActionContext`

**Specified by:**  
` getRequestScope` in class `ActionContextBase`

<!-- -->

**Returns:**  
a Map of "request scope" attributes.

------------------------------------------------------------------------

### getParameterMap

    public Map getParameterMap()

**Description copied from interface: ` ActionContext`**

Return a `Map` of parameters submitted by the user as part of this request. The keys to this map will be request parameter names (of type `String`), and the values will be `String[]`.

This is implemented in analogy with the Request parameters of the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

**Returns:**  
A map of the request parameter attributes

------------------------------------------------------------------------

### getSessionScope

    public Map getSessionScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of Session scoped values. A session is understood as a sequence of requests made by the same user.

This is implemented in analogy with the Session scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "session scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getSessionScope` in interface `ActionContext`

**Specified by:**  
` getSessionScope` in class `ActionContextBase`

<!-- -->

**Returns:**  
A Map of "session scope" attributes.

------------------------------------------------------------------------

### setModuleConfig

    public void setModuleConfig(ModuleConfig moduleConfig)

**Description copied from interface: ` ActionContext`**

Set the ModuleConfig which is operative for the current request.

**Specified by:**  
` setModuleConfig` in interface `ActionContext`

**Overrides:**  
` setModuleConfig` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`moduleConfig` - The ModuleConfig to be used with this request

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig()

**Description copied from interface: ` ActionContext`**

Get the ModuleConfig which is operative for the current request.

**Specified by:**  
` getModuleConfig` in interface `ActionContext`

**Overrides:**  
` getModuleConfig` in class `ActionContextBase`

<!-- -->

**Returns:**  
The MooduleConfig being used with this request

**See Also:**  
[`ActionContext.getModuleConfig()`](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md#getModuleConfig())

------------------------------------------------------------------------

### setCancelled

    public void setCancelled(Boolean cancelled)

**Description copied from interface: ` ActionContext`**

Set the "cancel event" state for this context.

**Specified by:**  
` setCancelled` in interface `ActionContext`

**Overrides:**  
` setCancelled` in class `ActionContextBase`

<!-- -->

**Parameters:**  
`cancelled` - On true, set the cancel event state to true. On false, set the cancel event state to false.

**See Also:**  
`ActionContextBase.CANCEL_KEY`

------------------------------------------------------------------------

### getCancelled

    public Boolean getCancelled()

**Description copied from interface: ` ActionContext`**

Indicate if the "cancel event" state is set for for this context,

**Specified by:**  
` getCancelled` in interface `ActionContext`

**Overrides:**  
` getCancelled` in class `ActionContextBase`

<!-- -->

**See Also:**  
`ActionContextBase.CANCEL_KEY`

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
<td align="left"><a href="class-use/WebActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ServletActionContext.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/WebActionContext.html"><strong>FRAMES</strong></a>    <a href="WebActionContext.html"><strong>NO FRAMES</strong></a>    
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
