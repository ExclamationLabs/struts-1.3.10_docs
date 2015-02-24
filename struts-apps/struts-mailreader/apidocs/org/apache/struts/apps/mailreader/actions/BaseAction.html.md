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
<td align="left"><a href="class-use/BaseAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/LocaleAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/BaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
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
 Class BaseAction
-----------------------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.MappingDispatchAction
                      org.apache.struts.apps.mailreader.actions.BaseAction

**Direct Known Subclasses:**  
[LocaleAction](../../../../../../org/apache/struts/apps/mailreader/actions/LocaleAction.html.md "class in org.apache.struts.apps.mailreader.actions"), [LogoffAction](../../../../../../org/apache/struts/apps/mailreader/actions/LogoffAction.html "class in org.apache.struts.apps.mailreader.actions"), [LogonAction](../../../../../../org/apache/struts/apps/mailreader/actions/LogonAction.html "class in org.apache.struts.apps.mailreader.actions"), [MainMenuAction](../../../../../../org/apache/struts/apps/mailreader/actions/MainMenuAction.html "class in org.apache.struts.apps.mailreader.actions"), [RegistrationAction](../../../../../../org/apache/struts/apps/mailreader/actions/RegistrationAction.html "class in org.apache.struts.apps.mailreader.actions"), [SubscriptionAction](../../../../../../org/apache/struts/apps/mailreader/actions/SubscriptionAction.html "class in org.apache.struts.apps.mailreader.actions"), [WelcomeAction](../../../../../../org/apache/struts/apps/mailreader/actions/WelcomeAction.html "class in org.apache.struts.apps.mailreader.actions")

------------------------------------------------------------------------

    public abstract class BaseAction

extends [MappingDispatchAction](http://struts.apache.org/apidocs/org/apache/struts/actions/MappingDispatchAction.html.md?is-external=true "class or interface in org.apache.struts.actions")

Base Action for MailReader application.

All the BaseAction helper methods are prefixed with "do" so that they can be easily distinguished from Struts and Servlet API methods. BaseAction subclasses may also have prive "do" helpers of their own.

Methods are kept in alphabetical order, to make them easier to find.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Log`

` log`
            The `Log` instance for this application.

`static String`

` PASSWORD`
            Name of password field ["password"].

`static String`

` TASK`
            Name of task field ["task"].

`static String`

` USERNAME`
            Name of username field ["username"].

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
| ` BaseAction()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` doCancel(HttpSession session, String method, String key)`
            Helper method to log event and cancel transaction.

`protected  ActionForward`

` doFindFailure(ActionMapping mapping)`
            Return the local or global forward named "failure" or null if there is no such forward.

`protected  ActionForward`

` doFindLogon(ActionMapping mapping)`
            Return the local or global forward named "logon" or null if there is no such forward.

`protected  ActionForward`

` doFindSuccess(ActionMapping mapping)`
            Return the mapping labeled "success" or null if there is no such mapping.

`protected  String`

` doGet(ActionForm form, String property)`
            Helper method to fetch a String property from a DynaActionForm.

`protected  Subscription`

` doGetSubscription(HttpServletRequest request)`
            Obtain the cached Subscription object, if any.

`protected  Subscription`

` doGetSubscription(HttpSession session)`
            Obtain the cached Subscription object, if any.

`protected  User`

` doGetUser(HttpServletRequest request)`
            Helper method to obtain User form session (if any).

`protected  User`

` doGetUser(HttpSession session)`
            Helper method to obtain User form session (if any).

`protected  UserDatabase`

` doGetUserDatabase()`
            Return a reference to the UserDatabase or null if the database is not available.

`protected  ActionForward`

` doInputForward(ActionMapping mapping, HttpServletRequest request, ActionMessages errors)`
            Save any errors and the transactioonal token, and forward to the InputForard result.

`protected  void`

` doLogProcess(ActionMapping mapping, String method)`
            Log a "processing" message for an Action.

`protected  void`

` doSaveToken(HttpServletRequest request)`
            Helper method to log event and save token.

`protected  void`

` doSaveUser(User user)`
            Persist the User object, including subscriptions, to the database.

`protected  boolean`

` doSet(ActionForm form, String property, String value)`
            Helper method to inject a String property into a DynaActionForm.

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

<span id="USERNAME"></span>

### USERNAME

    public static String USERNAME

Name of username field ["username"].

------------------------------------------------------------------------

<span id="PASSWORD"></span>

### PASSWORD

    public static String PASSWORD

Name of password field ["password"].

------------------------------------------------------------------------

<span id="TASK"></span>

### TASK

    public static final String TASK

Name of task field ["task"].

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.actions.BaseAction.TASK)

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected Log log

The `Log` instance for this application.

<span id="constructor_detail"></span>

**Constructor Detail**

### BaseAction

    public BaseAction()

<span id="method_detail"></span>

**Method Detail**

### doCancel

    protected void doCancel(HttpSession session,
                            String method,
                            String key)

Helper method to log event and cancel transaction.

**Parameters:**  
`session` - Our HttpSession

`method` - Method being processed

`key` - Attrkibute to remove from session, if any

------------------------------------------------------------------------

### doFindFailure

    protected ActionForward doFindFailure(ActionMapping mapping)

Return the local or global forward named "failure" or null if there is no such forward.

**Parameters:**  
`mapping` - Our ActionMapping

**Returns:**  
Return the mapping named "failure" or null if there is no such mapping.

------------------------------------------------------------------------

### doFindLogon

    protected ActionForward doFindLogon(ActionMapping mapping)

Return the local or global forward named "logon" or null if there is no such forward.

**Parameters:**  
`mapping` - Our ActionMapping

**Returns:**  
Return the mapping named "logon" or null if there is no such mapping.

------------------------------------------------------------------------

### doFindSuccess

    protected ActionForward doFindSuccess(ActionMapping mapping)

Return the mapping labeled "success" or null if there is no such mapping.

**Parameters:**  
`mapping` - Our ActionMapping

**Returns:**  
Return the mapping named "success" or null if there is no such mapping.

------------------------------------------------------------------------

### doGet

    protected String doGet(ActionForm form,
                           String property)

Helper method to fetch a String property from a DynaActionForm.

Values are returned trimmed of leading and trailing whitespace. Zero-length strings are returned as null.

**Parameters:**  
`form` - Our DynaActionForm

`property` - The name of the property

**Returns:**  
The value or null if an error occurs

------------------------------------------------------------------------

### doGetSubscription

    protected Subscription doGetSubscription(HttpSession session)

Obtain the cached Subscription object, if any.

**Parameters:**  
`session` - Our HttpSession

**Returns:**  
Cached Subscription object or null

------------------------------------------------------------------------

### doGetSubscription

    protected Subscription doGetSubscription(HttpServletRequest request)

Obtain the cached Subscription object, if any.

**Parameters:**  
`request` - Our HttpServletRequest

**Returns:**  
Cached Subscription object or null

------------------------------------------------------------------------

### doGetUserDatabase

    protected UserDatabase doGetUserDatabase()

Return a reference to the UserDatabase or null if the database is not available.

**Returns:**  
a reference to the UserDatabase or null if the database is not available

------------------------------------------------------------------------

### doGetUser

    protected User doGetUser(HttpSession session)

Helper method to obtain User form session (if any).

**Parameters:**  
`session` - Our HttpSession

**Returns:**  
User object, or null if there is no user.

------------------------------------------------------------------------

### doGetUser

    protected User doGetUser(HttpServletRequest request)

Helper method to obtain User form session (if any).

**Parameters:**  
`request` - Our HttpServletRequest

**Returns:**  
User object, or null if there is no user.

------------------------------------------------------------------------

### doInputForward

    protected ActionForward doInputForward(ActionMapping mapping,
                                           HttpServletRequest request,
                                           ActionMessages errors)

Save any errors and the transactioonal token, and forward to the InputForard result.

**Parameters:**  
`mapping` - Our ActionMapping

`request` - Our HttpServletRequest

`errors` - Our ActionMessages collectoin

**Returns:**  
The InputForward for this mappintg

------------------------------------------------------------------------

### doLogProcess

    protected void doLogProcess(ActionMapping mapping,
                                String method)

Log a "processing" message for an Action.

**Parameters:**  
`mapping` - Our ActionMapping

`method` - Name of method being processed

------------------------------------------------------------------------

### doSaveToken

    protected void doSaveToken(HttpServletRequest request)

Helper method to log event and save token.

**Parameters:**  
`request` - Our HttpServletRequest

------------------------------------------------------------------------

### doSaveUser

    protected void doSaveUser(User user)
                       throws ServletException

Persist the User object, including subscriptions, to the database.

**Parameters:**  
`user` - Our User object

**Throws:**  
`ServletException` - On any error

------------------------------------------------------------------------

### doSet

    protected boolean doSet(ActionForm form,
                            String property,
                            String value)

Helper method to inject a String property into a DynaActionForm.

**Parameters:**  
`form` - Our DynaActionForm

`property` - The name of the property

`value` - The value for the property

**Returns:**  
True if the assignment succeeds

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
<td align="left"><a href="class-use/BaseAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/LocaleAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/BaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
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
