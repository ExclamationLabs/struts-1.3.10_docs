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
<td align="left"><a href="class-use/RegistrationAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/MainMenuAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/SubscriptionAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/RegistrationAction.html"><strong>FRAMES</strong></a>    <a href="RegistrationAction.html"><strong>NO FRAMES</strong></a>    
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
 Class RegistrationAction
-----------------------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.MappingDispatchAction
                      org.apache.struts.apps.mailreader.actions.BaseAction
                          org.apache.struts.apps.mailreader.actions.RegistrationAction

------------------------------------------------------------------------

    public final class RegistrationAction

extends [BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")

Provide an Edit method for retrieving an existing user, and a Save method for updating or inserting a user.

Both methods utilize a RegistrationForm to obtain or expose User details. If Save is used to create a user, additional validations ensure input is nominal. When a user is created, Save also handles the initial logon.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` FROM_ADDRESS`
            Name of fromAddress field ["fromAddress"].

`static String`

` FULL_NAME`
            Name of fullName field ["fullName"].

`static String`

` PASSWORD2`
            Name of password confirmation field ["password2"].

`static String`

` REPLY_TO_ADDRESS`
            Name of replyToAddress field ["replyToAddress"].

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
| ` RegistrationAction()` 
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` Edit(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Retrieve the User object to edit or null if the User does not exist, and set an transactional token to later detect multiple Save commands.

` ActionForward`

` Save(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Insert or update a User object to the persistent store.

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

<span id="FROM_ADDRESS"></span>

### FROM\_ADDRESS

    public static final String FROM_ADDRESS

Name of fromAddress field ["fromAddress"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.RegistrationAction.FROM_ADDRESS)

------------------------------------------------------------------------

<span id="FULL_NAME"></span>

### FULL\_NAME

    public static final String FULL_NAME

Name of fullName field ["fullName"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.RegistrationAction.FULL_NAME)

------------------------------------------------------------------------

<span id="PASSWORD2"></span>

### PASSWORD2

    public static final String PASSWORD2

Name of password confirmation field ["password2"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.RegistrationAction.PASSWORD2)

------------------------------------------------------------------------

<span id="REPLY_TO_ADDRESS"></span>

### REPLY\_TO\_ADDRESS

    public static final String REPLY_TO_ADDRESS

Name of replyToAddress field ["replyToAddress"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.RegistrationAction.REPLY_TO_ADDRESS)

<span id="constructor_detail"></span>

**Constructor Detail**

### RegistrationAction

    public RegistrationAction()

<span id="method_detail"></span>

**Method Detail**

### Edit

    public ActionForward Edit(ActionMapping mapping,
                              ActionForm form,
                              HttpServletRequest request,
                              HttpServletResponse response)
                       throws Exception

Retrieve the User object to edit or null if the User does not exist, and set an transactional token to later detect multiple Save commands.

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

Insert or update a User object to the persistent store.

If a User is not logged in, then a new User is created and automatically logged in. Otherwise, the existing User is updated.

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
<td align="left"><a href="class-use/RegistrationAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/MainMenuAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/SubscriptionAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/RegistrationAction.html"><strong>FRAMES</strong></a>    <a href="RegistrationAction.html"><strong>NO FRAMES</strong></a>    
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
