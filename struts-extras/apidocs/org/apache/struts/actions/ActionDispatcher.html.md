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
<td align="left"><a href="class-use/ActionDispatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/ActionDispatcher.html"><strong>FRAMES</strong></a>    <a href="ActionDispatcher.html"><strong>NO FRAMES</strong></a>    
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
 Class ActionDispatcher
-------------------------

    java.lang.Object
      org.apache.struts.actions.ActionDispatcher

**Direct Known Subclasses:**  
[EventActionDispatcher](../../../../org/apache/struts/actions/EventActionDispatcher.html.md "class in org.apache.struts.actions")

------------------------------------------------------------------------

    public class ActionDispatcher

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Action *helper* class that dispatches to a public method in an Action.

This class is provided as an alternative mechanism to using DispatchAction and its various flavours and means *Dispatch* behaviour can be easily implemented into any `Action` without having to inherit from a particular super `Action`.

To implement *dispatch* behaviour in an `Action` class, create your custom Action as follows, along with the methods you require (and optionally "cancelled" and "unspecified" methods):

       public class MyCustomAction extends Action {

           protected ActionDispatcher dispatcher
                    = new ActionDispatcher(this, ActionDispatcher.MAPPING_FLAVOR);

           public ActionForward execute(ActionMapping mapping,
                                        ActionForm form,
                                        HttpServletRequest request,
                                        HttpServletResponse response)
                               throws Exception {
               return dispatcher.execute(mapping, form, request, response);
           }
       }
     

It provides three flavours of determing the name of the method:

-   **[`DEFAULT_FLAVOR`](../../../../org/apache/struts/actions/ActionDispatcher.html.md#DEFAULT_FLAVOR)** - uses the parameter specified in the struts-config.xml to get the method name from the Request (equivalent to `DispatchAction` **except** uses "method" as a default if the `parameter` is not specified in the struts-config.xml).
-   **[`DISPATCH_FLAVOR`](../../../../org/apache/struts/actions/ActionDispatcher.html.md#DISPATCH_FLAVOR)** - uses the parameter specified in the struts-config.xml to get the method name from the Request (equivalent to `DispatchAction`).
-   **[`MAPPING_FLAVOR`](../../../../org/apache/struts/actions/ActionDispatcher.html.md#MAPPING_FLAVOR)** - uses the parameter specified in the struts-config.xml as the method name (equivalent to `MappingDispatchAction`).

**Since:**  
Struts 1.2.7

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Action`

` actionInstance`
           The associated Action to dispatch to.

`protected  Class`

` clazz`
           The Class instance of this `DispatchAction` class.

`static int`

` DEFAULT_FLAVOR`
           Indicates "default" dispatch flavor.

`static int`

` DISPATCH_FLAVOR`
           Indicates flavor compatible with DispatchAction.

`protected  int`

` flavor`
           Indicates dispatch *flavor*.

`protected static Log`

`log`
           Commons Logging instance.

`static int`

` MAPPING_FLAVOR`
           Indicates "mapping" dispatch flavor.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  HashMap`

` methods`
           The set of Method objects we have introspected for this class, keyed by method name.

`protected  Class[]`

` types`
           The set of argument type classes for the reflected method call.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                      |
|------------------------------------------------------------------------------|
| ` ActionDispatcher(Action actionInstance)`                                   
            Construct an instance of this class from the supplied parameters.  |
| ` ActionDispatcher(Action actionInstance, int flavor)`                       
            Construct an instance of this class from the supplied parameters.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  ActionForward`

` cancelled(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' cancelled method, if present, otherwise returns null.

`protected  ActionForward`

` dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name)`
           Dispatch to the specified method.

`protected  ActionForward`

` dispatchMethod(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String name, Method method)`
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
           Returns the parameter value as influenced by the selected [`flavor`](../../../../org/apache/struts/actions/ActionDispatcher.html.md#flavor) specified for this `ActionDispatcher`.

`protected  boolean`

` isCancelled(HttpServletRequest request)`
           Returns `true` if the current form's cancel button was pressed.

`protected  ActionForward`

` unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="DEFAULT_FLAVOR"></span>

### DEFAULT\_FLAVOR

    public static final int DEFAULT_FLAVOR

Indicates "default" dispatch flavor.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.actions.ActionDispatcher.DEFAULT_FLAVOR)

------------------------------------------------------------------------

<span id="MAPPING_FLAVOR"></span>

### MAPPING\_FLAVOR

    public static final int MAPPING_FLAVOR

Indicates "mapping" dispatch flavor.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.actions.ActionDispatcher.MAPPING_FLAVOR)

------------------------------------------------------------------------

<span id="DISPATCH_FLAVOR"></span>

### DISPATCH\_FLAVOR

    public static final int DISPATCH_FLAVOR

Indicates flavor compatible with DispatchAction.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.actions.ActionDispatcher.DISPATCH_FLAVOR)

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="actionInstance"></span>

### actionInstance

    protected Action actionInstance

The associated Action to dispatch to.

------------------------------------------------------------------------

<span id="flavor"></span>

### flavor

    protected int flavor

Indicates dispatch *flavor*.

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

### ActionDispatcher

    public ActionDispatcher(Action actionInstance)

Construct an instance of this class from the supplied parameters.

**Parameters:**  
`actionInstance` - The action instance to be invoked.

------------------------------------------------------------------------

### ActionDispatcher

    public ActionDispatcher(Action actionInstance,
                            int flavor)

Construct an instance of this class from the supplied parameters.

**Parameters:**  
`actionInstance` - The action instance to be invoked.

`flavor` - The flavor of dispatch to use.

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it). Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

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

Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException. Classes utilizing `ActionDispatcher` should provide an `unspecified` method if they wish to provide behavior different than throwing a ServletException.

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

Dispatches to the target class' cancelled method, if present, otherwise returns null. Classes utilizing `ActionDispatcher` should provide a `cancelled` method if they wish to provide behavior different than returning null.

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

------------------------------------------------------------------------

### dispatchMethod

    protected ActionForward dispatchMethod(ActionMapping mapping,
                                           ActionForm form,
                                           HttpServletRequest request,
                                           HttpServletResponse response,
                                           String name,
                                           Method method)
                                    throws Exception

Dispatch to the specified method.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The non-HTTP request we are processing

`response` - The non-HTTP response we are creating

`name` - The name of the method to invoke

`method` - The method to invoke

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception.

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

### getParameter

    protected String getParameter(ActionMapping mapping,
                                  ActionForm form,
                                  HttpServletRequest request,
                                  HttpServletResponse response)
                           throws Exception

Returns the parameter value as influenced by the selected [`flavor`](../../../../org/apache/struts/actions/ActionDispatcher.html.md#flavor) specified for this `ActionDispatcher`.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
The `ActionMapping` parameter's value

**Throws:**  
`Exception` - if an error occurs.

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

------------------------------------------------------------------------

### isCancelled

    protected boolean isCancelled(HttpServletRequest request)

Returns `true` if the current form's cancel button was pressed. This method will check if the `Globals.CANCEL_KEY` request attribute has been set, which normally occurs if the cancel button generated by **CancelTag** was pressed by the user in the current request. If `true`, validation performed by an **ActionForm**'s `validate()` method will have been skipped by the controller servlet.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
`true` if the current form's cancel button was pressed; `false` otherwise.

**See Also:**  
[`CancelTag`](http://struts.apache.org/apidocs/org/apache/struts/taglib.html.md/CancelTag.html?is-external=true "class or interface in org.apache.struts.taglib.html")

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
<td align="left"><a href="class-use/ActionDispatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/actions/BaseAction.html.md" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/ActionDispatcher.html"><strong>FRAMES</strong></a>    <a href="ActionDispatcher.html"><strong>NO FRAMES</strong></a>    
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
