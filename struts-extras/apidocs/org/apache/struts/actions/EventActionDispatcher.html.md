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
<td align="left"><a href="class-use/EventActionDispatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md" title="interface in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/EventDispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/EventActionDispatcher.html"><strong>FRAMES</strong></a>    <a href="EventActionDispatcher.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.actions.ActionDispatcher">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.actions
 Class EventActionDispatcher
----------------------------

    java.lang.Object
      org.apache.struts.actions.ActionDispatcher
          org.apache.struts.actions.EventActionDispatcher

------------------------------------------------------------------------

    public class EventActionDispatcher

extends [ActionDispatcher](../../../../org/apache/struts/actions/ActionDispatcher.html.md "class in org.apache.struts.actions")

An Action helper class that dispatches to to one of the public methods that are named in the `parameter` attribute of the corresponding ActionMapping and matches a submission parameter. This is useful for developers who prefer to use many submit buttons, images, or submit links on a single form and whose related actions exist in a single Action class.

The method(s) in the associated `Action` must have the same signature (other than method name) of the standard Action.execute method.

To configure the use of this action in your `struts-config.xml` file, create an entry like this:


       <action path="/saveSubscription"
               type="org.example.SubscriptionAction"
               name="subscriptionForm"
              scope="request"
              input="/subscription.jsp"
          parameter="save,back,recalc=recalculate,default=save"/>
     

where `parameter` contains three possible methods and one default method if nothing matches (such as the user pressing the enter key).

For utility purposes, you can use the `key=value` notation to alias methods so that they are exposed as different form element names, in the event of a naming conflict or otherwise. In this example, the *recalc* button (via a request parameter) will invoke the `recalculate` method. The security-minded person may find this feature valuable to obfuscate and not expose the methods.

The *default* key is purely optional. If this is not specified and no parameters match the list of method keys, `null` is returned which means the `unspecified` method will be invoked.

The order of the parameters are guaranteed to be iterated in the order specified. If multiple buttons were accidently submitted, the first match in the list will be dispatched.

To implement this *dispatch* behaviour in an `Action`, class create your custom Action as follows, along with the methods you require (and optionally "cancelled" and "unspecified" methods):

       public class MyCustomAction extends Action {

           protected ActionDispatcher dispatcher = new EventActionDispatcher(this);

           public ActionForward execute(ActionMapping mapping,
                                        ActionForm form,
                                        HttpServletRequest request,
                                        HttpServletResponse response)
                               throws Exception {
               return dispatcher.execute(mapping, form, request, response);
           }
       }
     

**Since:**  
Struts 1.2.9

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.actions.ActionDispatcher"></span>

| **Fields inherited from class org.apache.struts.actions.[ActionDispatcher](../../../../org/apache/struts/actions/ActionDispatcher.html.md "class in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` actionInstance,  clazz,  DEFAULT_FLAVOR,  DISPATCH_FLAVOR,  flavor, log,  MAPPING_FLAVOR,  messages,  methods,  types`                                                       |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                      |
|--------------------------------------------------------------|
| ` EventActionDispatcher(Action action)`                      
            Constructs a new object for the specified action.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  String`

` getMethodName(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String parameter)`
           Returns the method name, given a parameter's value.

`protected  ActionForward`

` unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

 <span id="methods_inherited_from_class_org.apache.struts.actions.ActionDispatcher"></span>

| **Methods inherited from class org.apache.struts.actions.[ActionDispatcher](../../../../org/apache/struts/actions/ActionDispatcher.html.md "class in org.apache.struts.actions")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cancelled,  dispatchMethod,  dispatchMethod,  execute,  getMethod,  getParameter,  isCancelled`                                                                               |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### EventActionDispatcher

    public EventActionDispatcher(Action action)

Constructs a new object for the specified action.

**Parameters:**  
`action` - the action

<span id="method_detail"></span>

**Method Detail**

### unspecified

    protected ActionForward unspecified(ActionMapping mapping,
                                        ActionForm form,
                                        HttpServletRequest request,
                                        HttpServletResponse response)
                                 throws Exception

Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException. Classes utilizing `EventActionDispatcher` should provide an `unspecified` method if they wish to provide behavior different than throwing a ServletException.

**Overrides:**  
` unspecified` in class `ActionDispatcher`

<!-- -->

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

### getMethodName

    protected String getMethodName(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response,
                                   String parameter)
                            throws Exception

Returns the method name, given a parameter's value.

**Overrides:**  
` getMethodName` in class `ActionDispatcher`

<!-- -->

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
<td align="left"><a href="class-use/EventActionDispatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/DownloadAction.StreamInfo.html.md" title="interface in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/EventDispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/EventActionDispatcher.html"><strong>FRAMES</strong></a>    <a href="EventActionDispatcher.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.actions.ActionDispatcher">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
