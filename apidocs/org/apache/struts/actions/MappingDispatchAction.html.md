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
<td align="left"><a href="class-use/MappingDispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/LookupDispatchAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/SwitchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/MappingDispatchAction.html"><strong>FRAMES</strong></a>    <a href="MappingDispatchAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.actions.DispatchAction">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.actions
 Class MappingDispatchAction
----------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.MappingDispatchAction

------------------------------------------------------------------------

    public class MappingDispatchAction

extends [DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")

An abstract **Action** that dispatches to a public method that is named by the `parameter` attribute of the corresponding ActionMapping. This is useful for developers who prefer to combine many related actions into a single Action class.

To configure the use of this action in your `struts-config.xml` file, create an entry like this:


       <action path="/saveSubscription"
               type="org.example.SubscriptionAction"
               name="subscriptionForm"
              scope="request"
              input="/subscription.jsp"
          parameter="method"/>
     

where 'method' is the name of a method in your subclass of MappingDispatchAction that has the same signature (other than method name) of the standard Action.execute method. For example, you might combine the methods for managing a subscription into a single MappingDispatchAction class using the following methods:

-   public ActionForward create(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward edit(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward save(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward delete(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception
-   public ActionForward list(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception

for which you would create corresponding \<action\> configurations that reference this class:


      <action path="/createSubscription"
              type="org.example.SubscriptionAction"
              parameter="create">
          <forward name="success" path="/editSubscription.jsp"/>
      </action>

      <action path="/editSubscription"
              type="org.example.SubscriptionAction"
              parameter="edit">
          <forward name="success" path="/editSubscription.jsp"/>
      </action>

      <action path="/saveSubscription"
              type="org.example.SubscriptionAction"
              parameter="save"
              name="subscriptionForm"
              validate="true"
              input="/editSubscription.jsp"
              scope="request">
          <forward name="success" path="/savedSubscription.jsp"/>
      </action>

      <action path="/deleteSubscription"
              type="org.example.SubscriptionAction"
              name="subscriptionForm"
              scope="request"
              input="/subscription.jsp"
              parameter="delete">
          <forward name="success" path="/deletedSubscription.jsp"/>
      </action>

      <action path="/listSubscriptions"
              type="org.example.SubscriptionAction"
              parameter="list">
          <forward name="success" path="/subscriptionList.jsp"/>
      </action>
     

**NOTE** - Unlike DispatchAction, mapping characteristics may differ between the various handlers, so you can combine actions in the same class that, for example, differ in their use of forms or validation. Also, a request parameter, which would be visible to the application user, is not required to enable selection of the handler method.

**Since:**  
Struts 1.2

**Version:**  
$Rev: 480570 $ $Date: 2006-11-29 07:39:37 -0600 (Wed, 29 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Fields inherited from class org.apache.struts.actions.[DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clazz,  methods, types`                                                                                                                                                   |

 <span id="fields_inherited_from_class_org.apache.struts.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.actions.[BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `messages`                                                                                                                                                         |

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                               |

  <span id="constructor_summary"></span>

| **Constructor Summary**    |
|----------------------------|
| ` MappingDispatchAction()` 
                             |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

`protected  String`

` getMethodName(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String parameter)`
           Returns the method name, given a parameter's value.

`protected  String`

` getParameter(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Returns the parameter value.

`protected  ActionForward`

` unspecified(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Method which is dispatched to when there is no value for the parameter in the ActionMapping.

 <span id="methods_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Methods inherited from class org.apache.struts.actions.[DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cancelled,  dispatchMethod,  getMethod`                                                                                                                                   |

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getLocale,  getMessages,  getResources,  getResources, getServlet,  isCancelled,  isTokenValid,  isTokenValid,  resetToken,  saveErrors,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MappingDispatchAction

    public MappingDispatchAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it). Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed. This method dispatches the request to other methods of `MappingDispatchAction` using the 'parameter' attribute of `ActionMapping` and Java Introspection.

**Overrides:**  
` execute` in class `DispatchAction`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Throws:**  
`Exception` - if an exception occurs

------------------------------------------------------------------------

### unspecified

    protected ActionForward unspecified(ActionMapping mapping,
                                        ActionForm form,
                                        HttpServletRequest request,
                                        HttpServletResponse response)
                                 throws Exception

Method which is dispatched to when there is no value for the parameter in the ActionMapping. Subclasses of `MappingDispatchAction` should override this method if they wish to provide default behavior different than throwing a ServletException.

**Overrides:**  
` unspecified` in class `DispatchAction`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Throws:**  
`Exception` - if an exception occurs

------------------------------------------------------------------------

### getParameter

    protected String getParameter(ActionMapping mapping,
                                  ActionForm form,
                                  HttpServletRequest request,
                                  HttpServletResponse response)
                           throws Exception

Returns the parameter value.

**Overrides:**  
` getParameter` in class `DispatchAction`

<!-- -->

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

### getMethodName

    protected String getMethodName(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response,
                                   String parameter)
                            throws Exception

Returns the method name, given a parameter's value.

**Overrides:**  
` getMethodName` in class `DispatchAction`

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
`Exception` - if an error occurs

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
<td align="left"><a href="class-use/MappingDispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/LookupDispatchAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/SwitchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/MappingDispatchAction.html"><strong>FRAMES</strong></a>    <a href="MappingDispatchAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.actions.DispatchAction">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
