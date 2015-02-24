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
<td align="left"><a href="class-use/ActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ActionContext.html"><strong>FRAMES</strong></a>    <a href="ActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.contexts
 Interface ActionContext
--------------------------------

**All Superinterfaces:**  
org.apache.commons.chain.Context, [Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")

<!-- -->

**All Known Implementing Classes:**  
[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts"), [MockActionContext](../../../../../org/apache/struts/chain/contexts/MockActionContext.html "class in org.apache.struts.chain.contexts"), [ServletActionContext](../../../../../org/apache/struts/chain/contexts/ServletActionContext.html "class in org.apache.struts.chain.contexts"), [WebActionContext](../../../../../org/apache/struts/chain/contexts/WebActionContext.html "class in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public interface ActionContext

extends org.apache.commons.chain.Context

An ActionContext represents a view of a commons-chain `Context` which encapsulates access to request and session-scoped resources and services

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_java.util.Map"></span>

| **Nested classes/interfaces inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Map.Entry<K,V>`                                                                                                                                                                      |

  <span id="field_summary"></span>

**Field Summary**

`static String`

` APPLICATION_SCOPE`
            

`static String`

` REQUEST_SCOPE`
            

`static String`

` SESSION_SCOPE`
            

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

` Action`

` getAction()`
            Get the action which has been identified to be executed as part of processing this request.

` ActionConfig`

` getActionConfig()`
            Get the ActionConfig which contains the details for processing this request.

` ActionForm`

` getActionForm()`
            Get the ActionForm instance which will carry any data submitted as part of this request.

` Map`

` getApplicationScope()`
           Return a `Map` of Application scoped values.

` Boolean`

` getCancelled()`
            Indicate if the "cancel event" state is set for for this context,

` ActionMessages`

` getErrors()`
            Retrieve error messages from an internal cache, creating an empty cache if one is not already present.

` Exception`

` getException()`
            Retrieve an exception which may have been caught by some code using this ActionContext, usually by an exception handler.

` Boolean`

` getFormValid()`
            Is the ActionForm for this context valid? This method *does not* actually perform form validation.

` ForwardConfig`

` getForwardConfig()`
            Get the ForwardConfig which has been identified as the basis for view-processing.

` String`

` getInclude()`
            Get the include path which should be processed as part of processing this request.

` Locale`

` getLocale()`
           Return the user's currently selected Locale.

` MessageResources`

` getMessageResources()`
           Return the default message resources for the current module.

` MessageResources`

` getMessageResources(String key)`
           Return the specified message resources for the current module.

` ActionMessages`

` getMessages()`
            Retrieve messages from an internal cache, creating an empty cache if one is not already present.

` ModuleConfig`

` getModuleConfig()`
            Get the ModuleConfig which is operative for the current request.

` Map`

` getParameterMap()`
           Return a `Map` of parameters submitted by the user as part of this request.

` Map`

` getRequestScope()`
           Return a `Map` of request scoped values.

` Map`

` getScope(String scopeName)`
           Return the Map representing the scope identified by `scopeName`.

` Map`

` getSessionScope()`
           Return a `Map` of Session scoped values.

` boolean`

` isTokenValid()`
            Indicate whether a transaction token for this context is valid.

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

` saveMessages(String scope, ActionMessages messages)`
            Save the given messages to the internal cache, clearing any previous messages in the cache, but only for the specified scope.

` void`

` saveToken()`
            Save a new transaction token in the "session" scope for this context, creating new resources, if needed.

` void`

` setAction(Action action)`
            Set the action which has been identified to be executed as part of processing this request.

` void`

` setActionConfig(ActionConfig config)`
            Set the ActionConfig class contains the details for processing this request.

` void`

` setActionForm(ActionForm form)`
            Set the ActionForm instance which will carry any data submitted as part of this request.

` void`

` setCancelled(Boolean cancelled)`
            Set the "cancel event" state for this context.

` void`

` setException(Exception e)`
            Store an exception in this context for use by other handling code.

` void`

` setFormValid(Boolean valid)`
            Store the result of the validation of the Context's ActionForm.

` void`

` setForwardConfig(ForwardConfig forward)`
            Set the ForwardConfig which should be used as the basis of the view segment of the overall processing.

` void`

` setInclude(String include)`
            Set the include path which should be processed as part of processing this request.

` void`

` setLocale(Locale locale)`
           Set the user's currently selected `Locale`.

` void`

` setMessageResources(MessageResources resources)`
           Set the default message resources for the current module.

` void`

` setModuleConfig(ModuleConfig config)`
            Set the ModuleConfig which is operative for the current request.

 <span id="methods_inherited_from_class_java.util.Map"></span>

| **Methods inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clear, containsKey, containsValue, entrySet, equals, get, hashCode, isEmpty, keySet, put, putAll, remove, size, values`                                            |

 

<span id="field_detail"></span>

**Field Detail**

<span id="APPLICATION_SCOPE"></span>

### APPLICATION\_SCOPE

    static final String APPLICATION_SCOPE

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContext.APPLICATION_SCOPE)

------------------------------------------------------------------------

<span id="SESSION_SCOPE"></span>

### SESSION\_SCOPE

    static final String SESSION_SCOPE

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContext.SESSION_SCOPE)

------------------------------------------------------------------------

<span id="REQUEST_SCOPE"></span>

### REQUEST\_SCOPE

    static final String REQUEST_SCOPE

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContext.REQUEST_SCOPE)

<span id="method_detail"></span>

**Method Detail**

### release

    void release()

Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

------------------------------------------------------------------------

### getApplicationScope

    Map getApplicationScope()

Return a `Map` of Application scoped values.

This is implemented in analogy with the Application scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "application scope" is an implementation detail left unspecified by Struts.

**Returns:**  
A Map of "application scope" attributes.

------------------------------------------------------------------------

### getSessionScope

    Map getSessionScope()

Return a `Map` of Session scoped values. A session is understood as a sequence of requests made by the same user.

This is implemented in analogy with the Session scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "session scope" is an implementation detail left unspecified by Struts.

**Returns:**  
A Map of "session scope" attributes.

------------------------------------------------------------------------

### getRequestScope

    Map getRequestScope()

Return a `Map` of request scoped values. A request is understood as the fundamental motivation for any particular instance of an `ActionContext`.

This is implemented in analogy with the Request Context in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "request scope" is an implementation detail left unspecified by Struts.

**Returns:**  
a Map of "request scope" attributes.

------------------------------------------------------------------------

### getScope

    Map getScope(String scopeName)

Return the Map representing the scope identified by `scopeName`. Implementations should support at minimum the names associated with the constants `APPLICATION_SCOPE`, `SESSION_SCOPE`, and `REQUEST_SCOPE`, but are permitted to support others as well.

**Parameters:**  
`scopeName` - A token identifying a scope, including but not limited to `APPLICATION_SCOPE`, `SESSION_SCOPE`, `REQUEST_SCOPE`.

**Returns:**  
A Map of attributes for the specified scope.

------------------------------------------------------------------------

### getParameterMap

    Map getParameterMap()

Return a `Map` of parameters submitted by the user as part of this request. The keys to this map will be request parameter names (of type `String`), and the values will be `String[]`.

This is implemented in analogy with the Request parameters of the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

**Returns:**  
A map of the request parameter attributes

------------------------------------------------------------------------

### setAction

    void setAction(Action action)

Set the action which has been identified to be executed as part of processing this request.

**Parameters:**  
`action` -

------------------------------------------------------------------------

### getAction

    Action getAction()

Get the action which has been identified to be executed as part of processing this request.

**Returns:**  
The action to be executed with this request

------------------------------------------------------------------------

### setActionForm

    void setActionForm(ActionForm form)

Set the ActionForm instance which will carry any data submitted as part of this request.

**Parameters:**  
`form` - The ActionForm instance to use with this request

------------------------------------------------------------------------

### getActionForm

    ActionForm getActionForm()

Get the ActionForm instance which will carry any data submitted as part of this request.

**Returns:**  
The ActionForm being used with this request

------------------------------------------------------------------------

### setActionConfig

    void setActionConfig(ActionConfig config)

Set the ActionConfig class contains the details for processing this request.

**Parameters:**  
`config` - The ActionConfig class to use with this request

------------------------------------------------------------------------

### getActionConfig

    ActionConfig getActionConfig()

Get the ActionConfig which contains the details for processing this request.

**Returns:**  
The ActionConfig class being used with this request

------------------------------------------------------------------------

### setForwardConfig

    void setForwardConfig(ForwardConfig forward)

Set the ForwardConfig which should be used as the basis of the view segment of the overall processing. This is the primary method of "communication" with the "view" sub-chain.

**Parameters:**  
`forward` - The ForwardConfig to use with this request

------------------------------------------------------------------------

### getForwardConfig

    ForwardConfig getForwardConfig()

Get the ForwardConfig which has been identified as the basis for view-processing.

**Returns:**  
The ForwardConfig being used with this request

------------------------------------------------------------------------

### setInclude

    void setInclude(String include)

Set the include path which should be processed as part of processing this request.

**Parameters:**  
`include` - The include path to be used with this request

------------------------------------------------------------------------

### getInclude

    String getInclude()

Get the include path which should be processed as part of processing this request.

**Returns:**  
The include path being used with this request

------------------------------------------------------------------------

### setModuleConfig

    void setModuleConfig(ModuleConfig config)

Set the ModuleConfig which is operative for the current request.

**Parameters:**  
`config` - The ModuleConfig to be used with this request

------------------------------------------------------------------------

### getModuleConfig

    ModuleConfig getModuleConfig()

Get the ModuleConfig which is operative for the current request.

**Returns:**  
The MooduleConfig being used with this request

------------------------------------------------------------------------

### getFormValid

    Boolean getFormValid()

Is the ActionForm for this context valid? This method *does not* actually perform form validation. It is simply a holder property where processes which perform validation can store the results of the validation for other processes' benefit.

**Returns:**  
`Boolean.TRUE` if the form passed validation; `Boolean.FALSE` if the form failed validation; null if the form has not yet been validated

------------------------------------------------------------------------

### setFormValid

    void setFormValid(Boolean valid)

Store the result of the validation of the Context's ActionForm.

**Parameters:**  
`valid` - Whether the ActionForm for this request passes validation

------------------------------------------------------------------------

### getException

    Exception getException()

Retrieve an exception which may have been caught by some code using this ActionContext, usually by an exception handler.

**Returns:**  
Any exception that may have been caught by this ActionContext

------------------------------------------------------------------------

### setException

    void setException(Exception e)

Store an exception in this context for use by other handling code.

**Parameters:**  
`e` - An exception to be stored for handling by another member

------------------------------------------------------------------------

### addMessages

    void addMessages(ActionMessages messages)

Append the given messages keys to an internal cache, creating the cache if one is not already present.

**Parameters:**  
`messages` - New ActionMessages to cache

------------------------------------------------------------------------

### addErrors

    void addErrors(ActionMessages errors)

Append the given errors keys to an internal cache, creating the cache if one is not already present.

**Parameters:**  
`errors` - New ActionMessages to cache as errors

------------------------------------------------------------------------

### getErrors

    ActionMessages getErrors()

Retrieve error messages from an internal cache, creating an empty cache if one is not already present.

**Returns:**  
The ActionMessage cache for errors

------------------------------------------------------------------------

### getMessages

    ActionMessages getMessages()

Retrieve messages from an internal cache, creating an empty cache if one is not already present.

**Returns:**  
The ActionMessage cache for errors

------------------------------------------------------------------------

### saveErrors

    void saveErrors(ActionMessages errors)

Save the given error messages to the internal cache, clearing any previous messages in the cache.

If the parameter is null or empty, the internal cache is removed.

**Parameters:**  
`errors` - ActionMesssages to cache as errors

------------------------------------------------------------------------

### saveMessages

    void saveMessages(ActionMessages messages)

Save the given messages to the internal cache, clearing any previous messages in the cache.

If the parameter is null or empty, the internal cache is removed.

**Parameters:**  
`messages` - ActionMesssages to cache

------------------------------------------------------------------------

### saveMessages

    void saveMessages(String scope,
                      ActionMessages messages)

Save the given messages to the internal cache, clearing any previous messages in the cache, but only for the specified scope.

If the parameter is null or empty, the internal cache is removed.

**Parameters:**  
`scope` - The scope for the internal cache

`messages` - ActionMesssages to cache

------------------------------------------------------------------------

### generateToken

    String generateToken()

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

------------------------------------------------------------------------

### isTokenValid

    boolean isTokenValid()

Indicate whether a transaction token for this context is valid.

A typical implementation will place a transaction token in the session" scope Map and a matching value in the "parameter" Map. If the "session" token does not match the "parameter" attribute, or the session token is missing, then the transactional token is deemed invalid.

------------------------------------------------------------------------

### isTokenValid

    boolean isTokenValid(boolean reset)

Indicate whether a transaction token is stored in the "session" scope for this context, optionally clearing the token, so that the next check would return false.

**Parameters:**  
`reset` - On true, clear the transactional token

------------------------------------------------------------------------

### resetToken

    void resetToken()

Clear any transactional token stored in the "session" scope for this context, so that the next check would return false.

------------------------------------------------------------------------

### saveToken

    void saveToken()

Save a new transaction token in the "session" scope for this context, creating new resources, if needed.

------------------------------------------------------------------------

### getCancelled

    Boolean getCancelled()

Indicate if the "cancel event" state is set for for this context,

**See Also:**  
`ActionContextBase.CANCEL_KEY`

------------------------------------------------------------------------

### setCancelled

    void setCancelled(Boolean cancelled)

Set the "cancel event" state for this context.

**Parameters:**  
`cancelled` - On true, set the cancel event state to true. On false, set the cancel event state to false.

**See Also:**  
`ActionContextBase.CANCEL_KEY`

------------------------------------------------------------------------

### getMessageResources

    MessageResources getMessageResources()

Return the default message resources for the current module.

------------------------------------------------------------------------

### setMessageResources

    void setMessageResources(MessageResources resources)

Set the default message resources for the current module.

------------------------------------------------------------------------

### getMessageResources

    MessageResources getMessageResources(String key)

Return the specified message resources for the current module.

**Parameters:**  
`key` - The key specified in the `<message-resources>` element for the requested bundle

------------------------------------------------------------------------

### getLocale

    Locale getLocale()

Return the user's currently selected Locale.

------------------------------------------------------------------------

### setLocale

    void setLocale(Locale locale)

Set the user's currently selected `Locale`.

**Parameters:**  
`locale` - The user's selected Locale to be set, or null to select the server's default Locale

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
<td align="left"><a href="class-use/ActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ActionContext.html"><strong>FRAMES</strong></a>    <a href="ActionContext.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
