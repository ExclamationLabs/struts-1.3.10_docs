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
<td align="left"><a href="class-use/ActionContextBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ActionContext.html.md" title="interface in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/ContextWrapper.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ActionContextBase.html"><strong>FRAMES</strong></a>    <a href="ActionContextBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.contexts
 Class ActionContextBase
--------------------------------

    java.lang.Object
      org.apache.struts.chain.contexts.ContextWrapper
          org.apache.struts.chain.contexts.ActionContextBase

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util"), org.apache.commons.chain.Context, [ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

<!-- -->

**Direct Known Subclasses:**  
[MockActionContext](../../../../../org/apache/struts/chain/contexts/MockActionContext.html.md "class in org.apache.struts.chain.contexts"), [WebActionContext](../../../../../org/apache/struts/chain/contexts/WebActionContext.html "class in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public abstract class ActionContextBase

extends [ContextWrapper](../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md "class in org.apache.struts.chain.contexts")

implements [ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")

Provide an abstract but semi-complete implementation of ActionContext to serve as the base for concrete implementations.

The abstract methods to implement are the accessors for the named states, `getApplicationScope`, `getRequestScope`, and `getSessionScope`.

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

` ACTION_CONFIG_KEY`
            

`static String`

` ACTION_FORM_KEY`
            

`static String`

` ACTION_KEY`
            

`static String`

` CANCEL_KEY`
            

`static String`

` ERROR_ACTION_MESSAGES_KEY`
            Provide the default context attribute under which to store the ActionMessage cache for errors.

`static String`

` EXCEPTION_KEY`
            

`static String`

` FORWARD_CONFIG_KEY`
            

`static String`

` INCLUDE_KEY`
            

`static String`

` LOCALE_KEY`
            

`static String`

` MESSAGE_ACTION_MESSAGES_KEY`
            Provide the default context attribute under which to store the ActionMessage cache.

`static String`

` MESSAGE_RESOURCES_KEY`
            

`static String`

` MODULE_CONFIG_KEY`
            

`protected  TokenProcessor`

` token`
           Store the TokenProcessor instance for this Context.

`static String`

` TOKEN_KEY`
           Provide the default context attribute under which to store the token key.

`static String`

` TRANSACTION_TOKEN_KEY`
           Provide the default context attribute under which to store the transaction token key.

`static String`

` VALID_KEY`
            

 <span id="fields_inherited_from_class_org.apache.struts.chain.contexts.ActionContext"></span>

| **Fields inherited from interface org.apache.struts.chain.contexts.[ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` APPLICATION_SCOPE,  REQUEST_SCOPE,  SESSION_SCOPE`                                                                                                                                                     |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                            |
|------------------------------------------------------------------------------------|
| ` ActionContextBase()`                                                             
            Instantiate ActionContextBase, wrapping a default ContextBase instance.  |
| ` ActionContextBase(org.apache.commons.chain.Context context)`                     
            Instantiate ActionContextBase, wrapping the given Context.               |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addActionMessages(String key, ActionMessages messages)`
            Add the given messages to a cache stored in this Context, under key.

` void`

` addErrors(ActionMessages errors)`
            Append the given errors keys to an internal cache, creating the cache if one is not already present.

` void`

` addMessages(ActionMessages messages)`
            Append the given messages keys to an internal cache, creating the cache if one is not already present.

` ActionForm`

` findOrCreateActionForm(String formName, String scopeName)`
            Using this `ActionContext`'s default `ModuleConfig`, return an existing `ActionForm` in the specified scope, or create a new one and add it to the specified scope.

` ActionForm`

` findOrCreateActionForm(String formName, String scopeName, ModuleConfig moduleConfig)`
            In the context of the given `ModuleConfig` and this `ActionContext`, look for an existing `ActionForm` in the specified scope.

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

`abstract  Map`

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

` Log`

` getLogger()`
            Provide the currently configured commons-logging `Log` instance.

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

`abstract  Map`

` getRequestScope()`
           Return a `Map` of request scoped values.

` Map`

` getScope(String scopeName)`
           Return the Map representing the scope identified by `scopeName`.

`abstract  Map`

` getSessionScope()`
           Return a `Map` of Session scoped values.

`protected  String`

` getTokenGeneratorId()`
            

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

` saveActionMessages(String key, ActionMessages messages)`
            Save the given ActionMessages into the request scope under the given key, clearing the attribute if the messages are empty or null.

` void`

` saveActionMessages(String scopeId, String key, ActionMessages messages)`
           Save the given `messages` into the map identified by the given `scopeId` under the given `key`.

` void`

` saveErrors(ActionMessages errors)`
            Save the given error messages to the internal cache, clearing any previous messages in the cache.

` void`

` saveMessages(ActionMessages messages)`
            Save the given messages to the internal cache, clearing any previous messages in the cache.

` void`

` saveMessages(String scope, ActionMessages messages)`
            Adapt a legacy form of SaveMessages to the ActionContext API by storing the ActoinMessages under the default scope.

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

` setLogger(Log logger)`
            Set the commons-logging `Log` instance which should be used to LOG messages.

` void`

` setMessageResources(MessageResources messageResources)`
           Set the default message resources for the current module.

` void`

` setModuleConfig(ModuleConfig config)`
            Set the ModuleConfig which is operative for the current request.

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ContextWrapper"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[ContextWrapper](../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md "class in org.apache.struts.chain.contexts")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` clear,  containsKey,  containsValue,  entrySet,  get,  getBaseContext,  isEmpty,  keySet,  put,  putAll,  remove,  size,  values`                                                                 |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ActionContext"></span>

| **Methods inherited from interface org.apache.struts.chain.contexts.[ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html.md "interface in org.apache.struts.chain.contexts")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getParameterMap`                                                                                                                                                                                        |

 <span id="methods_inherited_from_class_java.util.Map"></span>

| **Methods inherited from interface java.util.[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clear, containsKey, containsValue, entrySet, equals, get, hashCode, isEmpty, keySet, put, putAll, remove, size, values`                                            |

 

<span id="field_detail"></span>

**Field Detail**

<span id="ACTION_KEY"></span>

### ACTION\_KEY

    public static final String ACTION_KEY

**See Also:**  
`Constants.ACTION_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.ACTION_KEY)

------------------------------------------------------------------------

<span id="ACTION_CONFIG_KEY"></span>

### ACTION\_CONFIG\_KEY

    public static final String ACTION_CONFIG_KEY

**See Also:**  
, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.ACTION_CONFIG_KEY)

------------------------------------------------------------------------

<span id="ACTION_FORM_KEY"></span>

### ACTION\_FORM\_KEY

    public static final String ACTION_FORM_KEY

**See Also:**  
`Constants.ACTION_FORM_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.ACTION_FORM_KEY)

------------------------------------------------------------------------

<span id="FORWARD_CONFIG_KEY"></span>

### FORWARD\_CONFIG\_KEY

    public static final String FORWARD_CONFIG_KEY

**See Also:**  
`Constants.FORWARD_CONFIG_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.FORWARD_CONFIG_KEY)

------------------------------------------------------------------------

<span id="MODULE_CONFIG_KEY"></span>

### MODULE\_CONFIG\_KEY

    public static final String MODULE_CONFIG_KEY

**See Also:**  
`Constants.MODULE_CONFIG_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.MODULE_CONFIG_KEY)

------------------------------------------------------------------------

<span id="EXCEPTION_KEY"></span>

### EXCEPTION\_KEY

    public static final String EXCEPTION_KEY

**See Also:**  
`Constants.EXCEPTION_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.EXCEPTION_KEY)

------------------------------------------------------------------------

<span id="ERROR_ACTION_MESSAGES_KEY"></span>

### ERROR\_ACTION\_MESSAGES\_KEY

    public static final String ERROR_ACTION_MESSAGES_KEY

Provide the default context attribute under which to store the ActionMessage cache for errors.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.ERROR_ACTION_MESSAGES_KEY)

------------------------------------------------------------------------

<span id="MESSAGE_ACTION_MESSAGES_KEY"></span>

### MESSAGE\_ACTION\_MESSAGES\_KEY

    public static final String MESSAGE_ACTION_MESSAGES_KEY

Provide the default context attribute under which to store the ActionMessage cache.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.MESSAGE_ACTION_MESSAGES_KEY)

------------------------------------------------------------------------

<span id="MESSAGE_RESOURCES_KEY"></span>

### MESSAGE\_RESOURCES\_KEY

    public static final String MESSAGE_RESOURCES_KEY

**See Also:**  
`Constants.MESSAGE_RESOURCES_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.MESSAGE_RESOURCES_KEY)

------------------------------------------------------------------------

<span id="INCLUDE_KEY"></span>

### INCLUDE\_KEY

    public static final String INCLUDE_KEY

**See Also:**  
`Constants.INCLUDE_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.INCLUDE_KEY)

------------------------------------------------------------------------

<span id="LOCALE_KEY"></span>

### LOCALE\_KEY

    public static final String LOCALE_KEY

**See Also:**  
`Constants.LOCALE_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.LOCALE_KEY)

------------------------------------------------------------------------

<span id="CANCEL_KEY"></span>

### CANCEL\_KEY

    public static final String CANCEL_KEY

**See Also:**  
`Constants.CANCEL_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.CANCEL_KEY)

------------------------------------------------------------------------

<span id="VALID_KEY"></span>

### VALID\_KEY

    public static final String VALID_KEY

**See Also:**  
`Constants.VALID_KEY`, [Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.VALID_KEY)

------------------------------------------------------------------------

<span id="TRANSACTION_TOKEN_KEY"></span>

### TRANSACTION\_TOKEN\_KEY

    public static final String TRANSACTION_TOKEN_KEY

Provide the default context attribute under which to store the transaction token key.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.TRANSACTION_TOKEN_KEY)

------------------------------------------------------------------------

<span id="TOKEN_KEY"></span>

### TOKEN\_KEY

    public static final String TOKEN_KEY

Provide the default context attribute under which to store the token key.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.chain.contexts.ActionContextBase.TOKEN_KEY)

------------------------------------------------------------------------

<span id="token"></span>

### token

    protected TokenProcessor token

Store the TokenProcessor instance for this Context.

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionContextBase

    public ActionContextBase(org.apache.commons.chain.Context context)

Instantiate ActionContextBase, wrapping the given Context.

**Parameters:**  
`context` - Context to wrap

------------------------------------------------------------------------

### ActionContextBase

    public ActionContextBase()

Instantiate ActionContextBase, wrapping a default ContextBase instance.

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

**Description copied from interface: ` ActionContext`**

Signal to the instance that it will not be used any more, so that any resources which should be cleaned up can be cleaned up.

**Specified by:**  
` release` in interface `ActionContext`

------------------------------------------------------------------------

### getApplicationScope

    public abstract Map getApplicationScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of Application scoped values.

This is implemented in analogy with the Application scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "application scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getApplicationScope` in interface `ActionContext`

<!-- -->

**Returns:**  
A Map of "application scope" attributes.

------------------------------------------------------------------------

### getRequestScope

    public abstract Map getRequestScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of request scoped values. A request is understood as the fundamental motivation for any particular instance of an `ActionContext`.

This is implemented in analogy with the Request Context in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "request scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getRequestScope` in interface `ActionContext`

<!-- -->

**Returns:**  
a Map of "request scope" attributes.

------------------------------------------------------------------------

### getSessionScope

    public abstract Map getSessionScope()

**Description copied from interface: ` ActionContext`**

Return a `Map` of Session scoped values. A session is understood as a sequence of requests made by the same user.

This is implemented in analogy with the Session scope in the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

The ultimate meaning of "session scope" is an implementation detail left unspecified by Struts.

**Specified by:**  
` getSessionScope` in interface `ActionContext`

<!-- -->

**Returns:**  
A Map of "session scope" attributes.

------------------------------------------------------------------------

### getScope

    public Map getScope(String scopeName)

**Description copied from interface: ` ActionContext`**

Return the Map representing the scope identified by `scopeName`. Implementations should support at minimum the names associated with the constants `APPLICATION_SCOPE`, `SESSION_SCOPE`, and `REQUEST_SCOPE`, but are permitted to support others as well.

**Specified by:**  
` getScope` in interface `ActionContext`

<!-- -->

**Parameters:**  
`scopeName` - A token identifying a scope, including but not limited to `APPLICATION_SCOPE`, `SESSION_SCOPE`, `REQUEST_SCOPE`.

**Returns:**  
A Map of attributes for the specified scope.

------------------------------------------------------------------------

### setAction

    public void setAction(Action action)

**Description copied from interface: ` ActionContext`**

Set the action which has been identified to be executed as part of processing this request.

**Specified by:**  
` setAction` in interface `ActionContext`

------------------------------------------------------------------------

### getAction

    public Action getAction()

**Description copied from interface: ` ActionContext`**

Get the action which has been identified to be executed as part of processing this request.

**Specified by:**  
` getAction` in interface `ActionContext`

<!-- -->

**Returns:**  
The action to be executed with this request

------------------------------------------------------------------------

### setActionForm

    public void setActionForm(ActionForm form)

**Description copied from interface: ` ActionContext`**

Set the ActionForm instance which will carry any data submitted as part of this request.

**Specified by:**  
` setActionForm` in interface `ActionContext`

<!-- -->

**Parameters:**  
`form` - The ActionForm instance to use with this request

------------------------------------------------------------------------

### getActionForm

    public ActionForm getActionForm()

**Description copied from interface: ` ActionContext`**

Get the ActionForm instance which will carry any data submitted as part of this request.

**Specified by:**  
` getActionForm` in interface `ActionContext`

<!-- -->

**Returns:**  
The ActionForm being used with this request

------------------------------------------------------------------------

### setActionConfig

    public void setActionConfig(ActionConfig config)

**Description copied from interface: ` ActionContext`**

Set the ActionConfig class contains the details for processing this request.

**Specified by:**  
` setActionConfig` in interface `ActionContext`

<!-- -->

**Parameters:**  
`config` - The ActionConfig class to use with this request

------------------------------------------------------------------------

### getActionConfig

    public ActionConfig getActionConfig()

**Description copied from interface: ` ActionContext`**

Get the ActionConfig which contains the details for processing this request.

**Specified by:**  
` getActionConfig` in interface `ActionContext`

<!-- -->

**Returns:**  
The ActionConfig class being used with this request

------------------------------------------------------------------------

### setForwardConfig

    public void setForwardConfig(ForwardConfig forward)

**Description copied from interface: ` ActionContext`**

Set the ForwardConfig which should be used as the basis of the view segment of the overall processing. This is the primary method of "communication" with the "view" sub-chain.

**Specified by:**  
` setForwardConfig` in interface `ActionContext`

<!-- -->

**Parameters:**  
`forward` - The ForwardConfig to use with this request

------------------------------------------------------------------------

### getForwardConfig

    public ForwardConfig getForwardConfig()

**Description copied from interface: ` ActionContext`**

Get the ForwardConfig which has been identified as the basis for view-processing.

**Specified by:**  
` getForwardConfig` in interface `ActionContext`

<!-- -->

**Returns:**  
The ForwardConfig being used with this request

------------------------------------------------------------------------

### setInclude

    public void setInclude(String include)

**Description copied from interface: ` ActionContext`**

Set the include path which should be processed as part of processing this request.

**Specified by:**  
` setInclude` in interface `ActionContext`

<!-- -->

**Parameters:**  
`include` - The include path to be used with this request

------------------------------------------------------------------------

### getInclude

    public String getInclude()

**Description copied from interface: ` ActionContext`**

Get the include path which should be processed as part of processing this request.

**Specified by:**  
` getInclude` in interface `ActionContext`

<!-- -->

**Returns:**  
The include path being used with this request

------------------------------------------------------------------------

### getFormValid

    public Boolean getFormValid()

**Description copied from interface: ` ActionContext`**

Is the ActionForm for this context valid? This method *does not* actually perform form validation. It is simply a holder property where processes which perform validation can store the results of the validation for other processes' benefit.

**Specified by:**  
` getFormValid` in interface `ActionContext`

<!-- -->

**Returns:**  
`Boolean.TRUE` if the form passed validation; `Boolean.FALSE` if the form failed validation; null if the form has not yet been validated

------------------------------------------------------------------------

### setFormValid

    public void setFormValid(Boolean valid)

**Description copied from interface: ` ActionContext`**

Store the result of the validation of the Context's ActionForm.

**Specified by:**  
` setFormValid` in interface `ActionContext`

<!-- -->

**Parameters:**  
`valid` - Whether the ActionForm for this request passes validation

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig()

**Description copied from interface: ` ActionContext`**

Get the ModuleConfig which is operative for the current request.

**Specified by:**  
` getModuleConfig` in interface `ActionContext`

<!-- -->

**Returns:**  
The MooduleConfig being used with this request

------------------------------------------------------------------------

### setModuleConfig

    public void setModuleConfig(ModuleConfig config)

**Description copied from interface: ` ActionContext`**

Set the ModuleConfig which is operative for the current request.

**Specified by:**  
` setModuleConfig` in interface `ActionContext`

<!-- -->

**Parameters:**  
`config` - The ModuleConfig to be used with this request

------------------------------------------------------------------------

### getException

    public Exception getException()

**Description copied from interface: ` ActionContext`**

Retrieve an exception which may have been caught by some code using this ActionContext, usually by an exception handler.

**Specified by:**  
` getException` in interface `ActionContext`

<!-- -->

**Returns:**  
Any exception that may have been caught by this ActionContext

------------------------------------------------------------------------

### setException

    public void setException(Exception e)

**Description copied from interface: ` ActionContext`**

Store an exception in this context for use by other handling code.

**Specified by:**  
` setException` in interface `ActionContext`

<!-- -->

**Parameters:**  
`e` - An exception to be stored for handling by another member

------------------------------------------------------------------------

### addMessages

    public void addMessages(ActionMessages messages)

**Description copied from interface: ` ActionContext`**

Append the given messages keys to an internal cache, creating the cache if one is not already present.

**Specified by:**  
` addMessages` in interface `ActionContext`

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

<!-- -->

**Returns:**  
The ActionMessage cache for errors

------------------------------------------------------------------------

### saveErrors

    public void saveErrors(ActionMessages errors)

**Description copied from interface: ` ActionContext`**

Save the given error messages to the internal cache, clearing any previous messages in the cache.

If the parameter is null or empty, the internal cache is removed.

**Specified by:**  
` saveErrors` in interface `ActionContext`

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

<!-- -->

**Parameters:**  
`messages` - ActionMesssages to cache

------------------------------------------------------------------------

### addActionMessages

    public void addActionMessages(String key,
                                  ActionMessages messages)

Add the given messages to a cache stored in this Context, under key.

**Parameters:**  
`key` - The attribute name for the message cache

`messages` - The ActionMessages to add

------------------------------------------------------------------------

### saveActionMessages

    public void saveActionMessages(String key,
                                   ActionMessages messages)

Save the given ActionMessages into the request scope under the given key, clearing the attribute if the messages are empty or null.

**Parameters:**  
`key` - The attribute name for the message cache

`messages` - The ActionMessages to add

------------------------------------------------------------------------

### saveActionMessages

    public void saveActionMessages(String scopeId,
                                   String key,
                                   ActionMessages messages)

Save the given `messages` into the map identified by the given `scopeId` under the given `key`.

**Parameters:**  
`scopeId` -

`key` -

`messages` -

------------------------------------------------------------------------

### saveMessages

    public void saveMessages(String scope,
                             ActionMessages messages)

Adapt a legacy form of SaveMessages to the ActionContext API by storing the ActoinMessages under the default scope.

**Specified by:**  
` saveMessages` in interface `ActionContext`

<!-- -->

**Parameters:**  
`scope` - The scope for the internal cache

`messages` - ActionMesssages to cache

------------------------------------------------------------------------

### saveToken

    public void saveToken()

**Description copied from interface: ` ActionContext`**

Save a new transaction token in the "session" scope for this context, creating new resources, if needed.

**Specified by:**  
` saveToken` in interface `ActionContext`

------------------------------------------------------------------------

### generateToken

    public String generateToken()

**Description copied from interface: ` ActionContext`**

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

**Specified by:**  
` generateToken` in interface `ActionContext`

------------------------------------------------------------------------

### getTokenGeneratorId

    protected String getTokenGeneratorId()

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid()

**Description copied from interface: ` ActionContext`**

Indicate whether a transaction token for this context is valid.

A typical implementation will place a transaction token in the session" scope Map and a matching value in the "parameter" Map. If the "session" token does not match the "parameter" attribute, or the session token is missing, then the transactional token is deemed invalid.

**Specified by:**  
` isTokenValid` in interface `ActionContext`

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid(boolean reset)

**Description copied from interface: ` ActionContext`**

Indicate whether a transaction token is stored in the "session" scope for this context, optionally clearing the token, so that the next check would return false.

**Specified by:**  
` isTokenValid` in interface `ActionContext`

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

------------------------------------------------------------------------

### getCancelled

    public Boolean getCancelled()

**Description copied from interface: ` ActionContext`**

Indicate if the "cancel event" state is set for for this context,

**Specified by:**  
` getCancelled` in interface `ActionContext`

<!-- -->

**See Also:**  
`ActionContextBase.CANCEL_KEY`

------------------------------------------------------------------------

### setCancelled

    public void setCancelled(Boolean cancelled)

**Description copied from interface: ` ActionContext`**

Set the "cancel event" state for this context.

**Specified by:**  
` setCancelled` in interface `ActionContext`

<!-- -->

**Parameters:**  
`cancelled` - On true, set the cancel event state to true. On false, set the cancel event state to false.

**See Also:**  
`ActionContextBase.CANCEL_KEY`

------------------------------------------------------------------------

### setMessageResources

    public void setMessageResources(MessageResources messageResources)

**Description copied from interface: ` ActionContext`**

Set the default message resources for the current module.

**Specified by:**  
` setMessageResources` in interface `ActionContext`

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources()

**Description copied from interface: ` ActionContext`**

Return the default message resources for the current module.

**Specified by:**  
` getMessageResources` in interface `ActionContext`

------------------------------------------------------------------------

### getMessageResources

    public MessageResources getMessageResources(String key)

**Description copied from interface: ` ActionContext`**

Return the specified message resources for the current module.

**Specified by:**  
` getMessageResources` in interface `ActionContext`

<!-- -->

**Parameters:**  
`key` - The key specified in the `<message-resources>` element for the requested bundle

------------------------------------------------------------------------

### setLocale

    public void setLocale(Locale locale)

**Description copied from interface: ` ActionContext`**

Set the user's currently selected `Locale`.

**Specified by:**  
` setLocale` in interface `ActionContext`

<!-- -->

**Parameters:**  
`locale` - The user's selected Locale to be set, or null to select the server's default Locale

------------------------------------------------------------------------

### getLocale

    public Locale getLocale()

**Description copied from interface: ` ActionContext`**

Return the user's currently selected Locale.

**Specified by:**  
` getLocale` in interface `ActionContext`

------------------------------------------------------------------------

### getLogger

    public Log getLogger()

Provide the currently configured commons-logging `Log` instance.

**Returns:**  
Log instance for this context

------------------------------------------------------------------------

### setLogger

    public void setLogger(Log logger)

Set the commons-logging `Log` instance which should be used to LOG messages. This is initialized at instantiation time but may be overridden. Be advised not to set the value to null, as `ActionContextBase` uses the logger for some of its own operations.

------------------------------------------------------------------------

### findOrCreateActionForm

    public ActionForm findOrCreateActionForm(String formName,
                                             String scopeName)
                                      throws IllegalAccessException,
                                             InstantiationException

Using this `ActionContext`'s default `ModuleConfig`, return an existing `ActionForm` in the specified scope, or create a new one and add it to the specified scope.

**Parameters:**  
`formName` - The name attribute of our ActionForm

`scopeName` - The scope identier (request, session)

**Returns:**  
The ActionForm for this request

**Throws:**  
`IllegalAccessException` - If object cannot be created

`InstantiationException` - If object cannot be created

**See Also:**  
`this.findOrCreateActionForm(String, String, ModuleConfig)`

------------------------------------------------------------------------

### findOrCreateActionForm

    public ActionForm findOrCreateActionForm(String formName,
                                             String scopeName,
                                             ModuleConfig moduleConfig)
                                      throws IllegalAccessException,
                                             InstantiationException

In the context of the given `ModuleConfig` and this `ActionContext`, look for an existing `ActionForm` in the specified scope. If one is found, return it; otherwise, create a new instance, add it to that scope, and then return it.

**Parameters:**  
`formName` - The name attribute of our ActionForm

`scopeName` - The scope identier (request, session)

**Returns:**  
The ActionForm for this request

**Throws:**  
`IllegalAccessException` - If object cannot be created

`InstantiationException` - If object cannot be created

`IllegalArgumentException` - If form config is missing from module or scopeName is invalid

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
<td align="left"><a href="class-use/ActionContextBase.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ActionContext.html.md" title="interface in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/ContextWrapper.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/ActionContextBase.html"><strong>FRAMES</strong></a>    <a href="ActionContextBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
