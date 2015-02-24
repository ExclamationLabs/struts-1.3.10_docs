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
<td align="left"><a href="class-use/MockActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/ServletActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/MockActionContext.html"><strong>FRAMES</strong></a>    <a href="MockActionContext.html"><strong>NO FRAMES</strong></a>    
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
 Class MockActionContext
--------------------------------

    java.lang.Object
      org.apache.struts.chain.contexts.ContextWrapper
          org.apache.struts.chain.contexts.ActionContextBase
              org.apache.struts.chain.contexts.MockActionContext

**All Implemented Interfaces:**  
[Map](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Map.html.md?is-external=true "class or interface in java.util"), org.apache.commons.chain.Context, [ActionContext](../../../../../org/apache/struts/chain/contexts/ActionContext.html "interface in org.apache.struts.chain.contexts")

------------------------------------------------------------------------

    public class MockActionContext

extends [ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")

Implement `ActionContext` with empty maps for `applicationScope`, `sessionScope`, `requestScope`, and `parameterMap` properties.

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

| **Constructor Summary** |
|-------------------------|
| ` MockActionContext()`  
                          |

  <span id="method_summary"></span>

**Method Summary**

` Map`

` getApplicationScope()`
           Return a `Map` of Application scoped values.

` Map`

` getParameterMap()`
           Return a `Map` of parameters submitted by the user as part of this request.

` Map`

` getRequestScope()`
           Return a `Map` of request scoped values.

` Map`

` getSessionScope()`
           Return a `Map` of Session scoped values.

` void`

` setApplicationScope(Map applicationScope)`
            

` void`

` setParameterMap(Map parameterMap)`
            

` void`

` setRequestScope(Map requestScope)`
            

` void`

` setSessionScope(Map sessionScope)`
            

 <span id="methods_inherited_from_class_org.apache.struts.chain.contexts.ActionContextBase"></span>

| **Methods inherited from class org.apache.struts.chain.contexts.[ActionContextBase](../../../../../org/apache/struts/chain/contexts/ActionContextBase.html.md "class in org.apache.struts.chain.contexts")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addActionMessages,  addErrors,  addMessages,  findOrCreateActionForm,  findOrCreateActionForm,  generateToken,  getAction,  getActionConfig,  getActionForm,  getCancelled,  getErrors,  getException,  getFormValid,  getForwardConfig,  getInclude,  getLocale,  getLogger,  getMessageResources,  getMessageResources,  getMessages,  getModuleConfig,  getScope,  getTokenGeneratorId,  isTokenValid,  isTokenValid,  release,  resetToken,  saveActionMessages,  saveActionMessages,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setAction,  setActionConfig,  setActionForm,  setCancelled,  setException,  setFormValid,  setForwardConfig,  setInclude,  setLocale,  setLogger,  setMessageResources,  setModuleConfig` |

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

### MockActionContext

    public MockActionContext()

<span id="method_detail"></span>

**Method Detail**

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

### setApplicationScope

    public void setApplicationScope(Map applicationScope)

------------------------------------------------------------------------

### getParameterMap

    public Map getParameterMap()

**Description copied from interface: ` ActionContext`**

Return a `Map` of parameters submitted by the user as part of this request. The keys to this map will be request parameter names (of type `String`), and the values will be `String[]`.

This is implemented in analogy with the Request parameters of the Servlet API, but it seems reasonable to expect that any Struts implementation will have an equivalent concept.

**Returns:**  
A map of the request parameter attributes

------------------------------------------------------------------------

### setParameterMap

    public void setParameterMap(Map parameterMap)

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

### setRequestScope

    public void setRequestScope(Map requestScope)

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

### setSessionScope

    public void setSessionScope(Map sessionScope)

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
<td align="left"><a href="class-use/MockActionContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/contexts/ContextWrapper.html.md" title="class in org.apache.struts.chain.contexts"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/contexts/ServletActionContext.html" title="class in org.apache.struts.chain.contexts"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/contexts/MockActionContext.html"><strong>FRAMES</strong></a>    <a href="MockActionContext.html"><strong>NO FRAMES</strong></a>    
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
