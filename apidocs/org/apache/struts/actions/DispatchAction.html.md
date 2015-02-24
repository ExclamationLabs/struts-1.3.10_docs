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
<td align="left"><a href="class-use/DispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DispatchAction.html"><strong>FRAMES</strong></a>    <a href="DispatchAction.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.actions
 Class DispatchAction
-------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction

**Direct Known Subclasses:**  
[EventDispatchAction](../../../../org/apache/struts/actions/EventDispatchAction.html.md "class in org.apache.struts.actions"), [LookupDispatchAction](../../../../org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions"), [MappingDispatchAction](../../../../org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")

------------------------------------------------------------------------

    public abstract class DispatchAction

extends [BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")

An abstract **Action** that dispatches to a public method that is named by the request parameter whose name is specified by the `parameter` property of the corresponding ActionMapping. This Action is useful for developers who prefer to combine many similar actions into a single Action class, in order to simplify their application design.

To configure the use of this action in your `struts-config.xml` file, create an entry like this:

`<action path="/saveSubscription" type="org.apache.struts.actions.DispatchAction" name="subscriptionForm" scope="request" input="/subscription.jsp" parameter="method"/>`

which will use the value of the request parameter named "method" to pick the appropriate "execute" method, which must have the same signature (other than method name) of the standard Action.execute method. For example, you might have the following three methods in the same action:

-   public ActionForward delete(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward insert(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward update(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception

and call one of the methods with a URL like this:

`http://localhost:8080/myapp/saveSubscription.do?method=update`

**NOTE** - All of the other mapping characteristics of this action must be shared by the various handlers. This places some constraints over what types of handlers may reasonably be packaged into the same `DispatchAction` subclass.

**NOTE** - If the value of the request parameter is empty, a method named `unspecified` is called. The default action is to throw an exception. If the request was cancelled (a .html.md:cancel` button was pressed), the custom handler `cancelled` will be used instead. You can also override the `getMethodName` method to override the action's default handler selection.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Class`

`clazz`
           The Class instance of this `DispatchAction` class.

`protected static Log`

`log`
           Commons Logging instance.

`protected  HashMap`

` methods`
           The set of Method objects we have introspected for this class, keyed by method name.

`protected  Class[]`

`types`
           The set of argument type classes for the reflected method call.

 <span id="fields_inherited_from_class_org.apache.struts.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.actions.[BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `messages`                                                                                                                                                         |

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                               |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` DispatchAction()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  ActionForward`

` cancelled(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when the request is a cancel button submit.

`protected  ActionForward`

` dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name)`
           Dispatch to the specified method.

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

`protected  Method`

` getMethod(String name)`
           Introspect the current class to identify a method of the specified name that accepts the same parameter types as the `execute` method does.

`protected  String`

` getMethodName(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String parameter)`
           Returns the method name, given a parameter's value.

`protected  String`

` getParameter(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Returns the parameter value.

`protected  ActionForward`

` unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when there is no value for specified request parameter included in the request.

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getLocale,  getMessages,  getResources,  getResources, getServlet,  isCancelled,  isTokenValid,  isTokenValid,  resetToken,  saveErrors,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="clazz"></span>

### clazz

    protected Class clazz

The Class instance of this `DispatchAction` class.

------------------------------------------------------------------------

<span id="methods"></span>

### methods

    protected HashMap methods

The set of Method objects we have introspected for this class, keyed by method name. This collection is populated as different methods are called, so that introspection needs to occur only once per method name.

------------------------------------------------------------------------

<span id="types"></span>

### types

    protected Class[] types

The set of argument type classes for the reflected method call. These are the same for all calls, so calculate them only once.

<span id="constructor_detail"></span>

**Constructor Detail**

### DispatchAction

    public DispatchAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it). Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Overrides:**  
` execute` in class `Action`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if an exception occurs

------------------------------------------------------------------------

### unspecified

    protected ActionForward unspecified(ActionMapping mapping,
                                        ActionForm form,
                                        HttpServletRequest request,
                                        HttpServletResponse response)
                                 throws Exception

Method which is dispatched to when there is no value for specified request parameter included in the request. Subclasses of `DispatchAction` should override this method if they wish to provide default behavior different than throwing a ServletException.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The non-HTTP request we are processing

`response` - The non-HTTP response we are creating

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception.

------------------------------------------------------------------------

### cancelled

    protected ActionForward cancelled(ActionMapping mapping,
                                      ActionForm form,
                                      HttpServletRequest request,
                                      HttpServletResponse response)
                               throws Exception

Method which is dispatched to when the request is a cancel button submit. Subclasses of `DispatchAction` should override this method if they wish to provide default behavior different than returning null.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The non-HTTP request we are processing

`response` - The non-HTTP response we are creating

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception.

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### dispatchMethod

    protected ActionForward dispatchMethod(ActionMapping mapping,
                                           ActionForm form,
                                           HttpServletRequest request,
                                           HttpServletResponse response,
                                           String name)
                                    throws Exception

Dispatch to the specified method.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The non-HTTP request we are processing

`response` - The non-HTTP response we are creating

`name` - The name of the method to invoke

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getParameter

    protected String getParameter(ActionMapping mapping,
                                  ActionForm form,
                                  HttpServletRequest request,
                                  HttpServletResponse response)
                           throws Exception

Returns the parameter value.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
The `ActionMapping` parameter's value

**Throws:**  
`Exception` - if the parameter is missing.

------------------------------------------------------------------------

### getMethod

    protected Method getMethod(String name)
                        throws NoSuchMethodException

Introspect the current class to identify a method of the specified name that accepts the same parameter types as the `execute` method does.

**Parameters:**  
`name` - Name of the method to be introspected

**Returns:**  
The method with the specified name.

**Throws:**  
`NoSuchMethodException` - if no such method can be found

------------------------------------------------------------------------

### getMethodName

    protected String getMethodName(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response,
                                   String parameter)
                            throws Exception

Returns the method name, given a parameter's value.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

`parameter` - The `ActionMapping` parameter's name

**Returns:**  
The method's name.

**Throws:**  
`Exception` - if an error occurs.

**Since:**  
Struts 1.2.0

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
<td align="left"><a href="class-use/DispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DownloadAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/DispatchAction.html"><strong>FRAMES</strong></a>    <a href="DispatchAction.html"><strong>NO FRAMES</strong></a>    
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
