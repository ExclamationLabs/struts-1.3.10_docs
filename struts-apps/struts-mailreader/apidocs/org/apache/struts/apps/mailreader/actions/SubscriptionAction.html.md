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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/SubscriptionAction.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/RegistrationAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/WelcomeAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/SubscriptionAction.html"><strong>FRAMES</strong></a>    <a href="SubscriptionAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader.actions
 Class SubscriptionAction
-----------------------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.MappingDispatchAction
                      org.apache.struts.apps.mailreader.actions.BaseAction
                          org.apache.struts.apps.mailreader.actions.SubscriptionAction

------------------------------------------------------------------------

    public final class SubscriptionAction

extends [BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")

Provide an Edit method for retrieving an existing subscription, and a Save method for updating or inserting a subscription.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` AUTO_CONNECT`
            Name of autoConnect field ["autoConnect"].

`static String`

` HOST`
            Name of host field ["host"].

`static String`

` TYPE`
            Name of type field ["type"].

 <span id="fields_inherited_from_class_org.apache.struts.apps.mailreader.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.apps.mailreader.actions.[BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` log,  PASSWORD,  TASK,  USERNAME`                                                                                                                                                                                      |

 <span id="fields_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Fields inherited from class org.apache.struts.actions.[DispatchAction](http://struts.apache.org/apidocs/org/apache/struts/actions/DispatchAction.html.md?is-external=true "class or interface in org.apache.struts.actions")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clazz, methods, types`                                                                                                                                                                                                       |

 <span id="fields_inherited_from_class_org.apache.struts.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.actions.[BaseAction](http://struts.apache.org/apidocs/org/apache/struts/actions/BaseAction.html.md?is-external=true "class or interface in org.apache.struts.actions")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `messages`                                                                                                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](http://struts.apache.org/apidocs/org/apache/struts/action/Action.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                                                                                  |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` SubscriptionAction()` 
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` Delete(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Prepare for a Delete operation by populating the form and seting the action to Delete.

` ActionForward`

` Edit(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Retrieve the Subscription object to edit or null if the Subscription does not exist.

` ActionForward`

` Save(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Insert or update a Subscription object to the persistent store.

 <span id="methods_inherited_from_class_org.apache.struts.apps.mailreader.actions.BaseAction"></span>

| **Methods inherited from class org.apache.struts.apps.mailreader.actions.[BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doCancel,  doFindFailure,  doFindLogon,  doFindSuccess,  doGet,  doGetSubscription,  doGetSubscription,  doGetUser,  doGetUser,  doGetUserDatabase,  doInputForward,  doLogProcess,  doSaveToken,  doSaveUser,  doSet`  |

 <span id="methods_inherited_from_class_org.apache.struts.actions.MappingDispatchAction"></span>

| **Methods inherited from class org.apache.struts.actions.[MappingDispatchAction](http://struts.apache.org/apidocs/org/apache/struts/actions/MappingDispatchAction.html.md?is-external=true "class or interface in org.apache.struts.actions")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `execute, getMethodName, getParameter, unspecified`                                                                                                                                                                                          |

 <span id="methods_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Methods inherited from class org.apache.struts.actions.[DispatchAction](http://struts.apache.org/apidocs/org/apache/struts/actions/DispatchAction.html.md?is-external=true "class or interface in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `cancelled, dispatchMethod, getMethod`                                                                                                                                                                                         |

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](http://struts.apache.org/apidocs/org/apache/struts/action/Action.html.md?is-external=true "class or interface in org.apache.struts.action")**                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addErrors, addMessages, execute, generateToken, getErrors, getLocale, getMessages, getResources, getResources, getServlet, isCancelled, isTokenValid, isTokenValid, resetToken, saveErrors, saveErrors, saveMessages, saveMessages, saveToken, setLocale, setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="AUTO_CONNECT"></span>

### AUTO\_CONNECT

    public static final String AUTO_CONNECT

Name of autoConnect field ["autoConnect"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.SubscriptionAction.AUTO_CONNECT)

------------------------------------------------------------------------

<span id="HOST"></span>

### HOST

    public static final String HOST

Name of host field ["host"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.SubscriptionAction.HOST)

------------------------------------------------------------------------

<span id="TYPE"></span>

### TYPE

    public static final String TYPE

Name of type field ["type"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.SubscriptionAction.TYPE)

<span id="constructor_detail"></span>

**Constructor Detail**

### SubscriptionAction

    public SubscriptionAction()

<span id="method_detail"></span>

**Method Detail**

### Delete

    public ActionForward Delete(ActionMapping mapping,
                                ActionForm form,
                                HttpServletRequest request,
                                HttpServletResponse response)
                         throws Exception

Prepare for a Delete operation by populating the form and seting the action to Delete.

**Parameters:**  
`mapping` - Our ActionMapping

`form` - Our ActionForm

`request` - Our HttpServletRequest

`response` - Our HttpServletResponse

**Returns:**  
The "Success" result for this mapping

**Throws:**  
`Exception` - on any error

------------------------------------------------------------------------

### Edit

    public ActionForward Edit(ActionMapping mapping,
                              ActionForm form,
                              HttpServletRequest request,
                              HttpServletResponse response)
                       throws Exception

Retrieve the Subscription object to edit or null if the Subscription does not exist.

The Subscription object is bound to the User, and so if the User is not logged in, control is forwarded to the Logon result.

**Parameters:**  
`mapping` - Our ActionMapping

`form` - Our ActionForm

`request` - Our HttpServletRequest

`response` - Our HttpServletResponse

**Returns:**  
The "Success" result for this mapping

**Throws:**  
`Exception` - on any error

------------------------------------------------------------------------

### Save

    public ActionForward Save(ActionMapping mapping,
                              ActionForm form,
                              HttpServletRequest request,
                              HttpServletResponse response)
                       throws Exception

Insert or update a Subscription object to the persistent store.

**Parameters:**  
`mapping` - Our ActionMapping

`form` - Our ActionForm

`request` - Our HttpServletRequest

`response` - Our HttpServletResponse

**Returns:**  
The "Success" result for this mapping

**Throws:**  
`Exception` - on any error

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/SubscriptionAction.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/RegistrationAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/WelcomeAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/SubscriptionAction.html"><strong>FRAMES</strong></a>    <a href="SubscriptionAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
