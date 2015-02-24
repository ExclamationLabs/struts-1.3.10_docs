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
<td align="left"><a href="class-use/Action.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/Action.html"><strong>FRAMES</strong></a>    <a href="Action.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class Action
------------------------

    java.lang.Object
      org.apache.struts.action.Action

**Direct Known Subclasses:**  
[MockAction](../../../../org/apache/struts/mock/MockAction.html.md "class in org.apache.struts.mock")

------------------------------------------------------------------------

    public class Action

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request. The controller (RequestProcessor) will select an appropriate Action for each request, create an instance (if necessary), and call the `execute` method.

Actions must be programmed in a thread-safe manner, because the controller will share the same instance for multiple simultaneous requests. This means you should design with the following items in mind:

-   Instance and static variables MUST NOT be used to store information related to the state of a particular request. They MAY be used to share global resources across requests for the same action.
-   Access to other resources (JavaBeans, session variables, etc.) MUST be synchronized if those resources require protection. (Generally, however, resource classes should be designed to provide their own protection where necessary.

When an `Action` instance is first created, the controller will call `setServlet` with a non-null argument to identify the servlet instance to which this Action is attached. When the servlet is to be shut down (or restarted), the `setServlet` method will be called with a `null` argument, which can be used to clean up any allocated resources in use by this Action.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-26 21:58:39 -0400 (Fri, 26 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ActionServlet`

`servlet`
           The servlet to which we are attached.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| `Action()`              
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` addErrors(HttpServletRequest request, ActionMessages errors)`
           Adds the specified errors keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required.

`protected  void`

` addMessages(HttpServletRequest request, ActionMessages messages)`
           Adds the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, ServletRequest request, ServletResponse response)`
           Process the specified non-HTTP request, and create the corresponding non-HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

`protected  String`

` generateToken(HttpServletRequest request)`
           Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

`protected  ActionMessages`

` getErrors(HttpServletRequest request)`
           Retrieves any existing errors placed in the request by previous actions.

`protected  Locale`

` getLocale(HttpServletRequest request)`
           Return the user's currently selected Locale.

`protected  ActionMessages`

` getMessages(HttpServletRequest request)`
            Retrieves any existing messages placed in the request by previous actions.

`protected  MessageResources`

` getResources(HttpServletRequest request)`
           Return the default message resources for the current module.

`protected  MessageResources`

` getResources(HttpServletRequest request, String key)`
           Return the specified message resources for the current module.

` ActionServlet`

`getServlet()`
           Return the servlet instance to which we are attached.

`protected  boolean`

` isCancelled(HttpServletRequest request)`
           Returns `true` if the current form's cancel button was pressed.

`protected  boolean`

` isTokenValid(HttpServletRequest request)`
           Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it.

`protected  boolean`

` isTokenValid(HttpServletRequest request, boolean reset)`
           Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it.

`protected  void`

` resetToken(HttpServletRequest request)`
           Reset the saved transaction token in the user's session.

`protected  void`

` saveErrors(HttpServletRequest request, ActionMessages errors)`
           Save the specified error messages keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required.

`protected  void`

` saveErrors(HttpSession session, ActionMessages errors)`
           Save the specified error messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="false") or \<html:errors\>, if any error messages are required.

`protected  void`

` saveMessages(HttpServletRequest request, ActionMessages messages)`
           Save the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

`protected  void`

` saveMessages(HttpSession session, ActionMessages messages)`
           Save the specified messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

`protected  void`

` saveToken(HttpServletRequest request)`
           Save a new transaction token in the user's current session, creating a new session if necessary.

`protected  void`

` setLocale(HttpServletRequest request, Locale locale)`
           Set the user's currently selected `Locale` into their `HttpSession`.

` void`

` setServlet(ActionServlet servlet)`
           Set the servlet instance to which we are attached (if `servlet` is non-null), or release any allocated resources (if `servlet` is null).

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="servlet"></span>

### servlet

    protected transient ActionServlet servlet

The servlet to which we are attached.

<span id="constructor_detail"></span>

**Constructor Detail**

### Action

    public Action()

<span id="method_detail"></span>

**Method Detail**

### getServlet

    public ActionServlet getServlet()

Return the servlet instance to which we are attached.

**Returns:**  
The servlet instance to which we are attached.

------------------------------------------------------------------------

### setServlet

    public void setServlet(ActionServlet servlet)

Set the servlet instance to which we are attached (if `servlet` is non-null), or release any allocated resources (if `servlet` is null).

**Parameters:**  
`servlet` - The new controller servlet, if any

------------------------------------------------------------------------

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 ServletRequest request,
                                 ServletResponse response)
                          throws Exception

Process the specified non-HTTP request, and create the corresponding non-HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic. Return an [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") instance describing where and how control should be forwarded, or `null` if the response has already been completed.

The default implementation attempts to forward to the HTTP version of this method.

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
Struts 1.1

------------------------------------------------------------------------

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic. Return an [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### addMessages

    protected void addMessages(HttpServletRequest request,
                               ActionMessages messages)

Adds the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required. Initialize the attribute if it has not already been. Otherwise, ensure that the request attribute is not set.

**Parameters:**  
`request` - The servlet request we are processing

`messages` - Messages object

**Since:**  
Struts 1.2.1

------------------------------------------------------------------------

### addErrors

    protected void addErrors(HttpServletRequest request,
                             ActionMessages errors)

Adds the specified errors keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required. Initialize the attribute if it has not already been. Otherwise, ensure that the request attribute is not set.

**Parameters:**  
`request` - The servlet request we are processing

`errors` - Errors object

**Since:**  
Struts 1.2.1

------------------------------------------------------------------------

### generateToken

    protected String generateToken(HttpServletRequest request)

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

**Parameters:**  
`request` - The request we are processing

**Returns:**  
The new transaction token.

------------------------------------------------------------------------

### getErrors

    protected ActionMessages getErrors(HttpServletRequest request)

Retrieves any existing errors placed in the request by previous actions. This method could be called instead of creating a `new ActionMessages()` at the beginning of an `Action`. This will prevent saveErrors() from wiping out any existing Errors

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
the Errors that already exist in the request, or a new ActionMessages object if empty.

**Since:**  
Struts 1.2.1

------------------------------------------------------------------------

### getLocale

    protected Locale getLocale(HttpServletRequest request)

Return the user's currently selected Locale.

**Parameters:**  
`request` - The request we are processing

**Returns:**  
The user's currently selected Locale.

------------------------------------------------------------------------

### getMessages

    protected ActionMessages getMessages(HttpServletRequest request)

Retrieves any existing messages placed in the request by previous actions. This method could be called instead of creating a `new ActionMessages()` at the beginning of an `Action` This will prevent saveMessages() from wiping out any existing Messages

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
the Messages that already exist in the request, or a new ActionMessages object if empty.

**Since:**  
Struts 1.2.1

------------------------------------------------------------------------

### getResources

    protected MessageResources getResources(HttpServletRequest request)

Return the default message resources for the current module.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
The default message resources for the current module.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### getResources

    protected MessageResources getResources(HttpServletRequest request,
                                            String key)

Return the specified message resources for the current module.

**Parameters:**  
`request` - The servlet request we are processing

`key` - The key specified in the message-resources element for the requested bundle.

**Returns:**  
The specified message resource for the current module.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### isCancelled

    protected boolean isCancelled(HttpServletRequest request)

Returns `true` if the current form's cancel button was pressed. This method will check if the `Globals.CANCEL_KEY` request attribute has been set, which normally occurs if the cancel button generated by **CancelTag** was pressed by the user in the current request. If `true`, validation performed by an **ActionForm**'s `validate()` method will have been skipped by the controller servlet.

Since Action 1.3.0, the mapping for a cancellable Action must also have the new "cancellable" property set to true. If "cancellable" is not set, and the magic Cancel token is found in the request, the standard Composable Request Processor will throw an InvalidCancelException.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
`true` if the cancel button was pressed; `false` otherwise.

------------------------------------------------------------------------

### isTokenValid

    protected boolean isTokenValid(HttpServletRequest request)

Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it. Returns `false` under any of the following circumstances:

-   No session associated with this request
-   No transaction token saved in the session
-   No transaction token included as a request parameter
-   The included transaction token value does not match the transaction token in the user's session

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
`true` if there is a transaction token and it is valid; `false` otherwise.

------------------------------------------------------------------------

### isTokenValid

    protected boolean isTokenValid(HttpServletRequest request,
                                   boolean reset)

Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it. Returns `false` under any of the following circumstances:

-   No session associated with this request
-   No transaction token saved in the session
-   No transaction token included as a request parameter
-   The included transaction token value does not match the transaction token in the user's session

**Parameters:**  
`request` - The servlet request we are processing

`reset` - Should we reset the token after checking it?

**Returns:**  
`true` if there is a transaction token and it is valid; `false` otherwise.

------------------------------------------------------------------------

### resetToken

    protected void resetToken(HttpServletRequest request)

Reset the saved transaction token in the user's session. This indicates that transactional token checking will not be needed on the next request that is submitted.

**Parameters:**  
`request` - The servlet request we are processing

------------------------------------------------------------------------

### saveErrors

    protected void saveErrors(HttpServletRequest request,
                              ActionMessages errors)

Save the specified error messages keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required. Otherwise, ensure that the request attribute is not created.

**Parameters:**  
`request` - The servlet request we are processing

`errors` - Error messages object

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### saveMessages

    protected void saveMessages(HttpServletRequest request,
                                ActionMessages messages)

Save the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required. Otherwise, ensure that the request attribute is not created.

**Parameters:**  
`request` - The servlet request we are processing.

`messages` - The messages to save. `null` or empty messages removes any existing ActionMessages in the request.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### saveMessages

    protected void saveMessages(HttpSession session,
                                ActionMessages messages)

Save the specified messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required. Otherwise, ensure that the session attribute is not created.

**Parameters:**  
`session` - The session to save the messages in.

`messages` - The messages to save. `null` or empty messages removes any existing ActionMessages in the session.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### saveErrors

    protected void saveErrors(HttpSession session,
                              ActionMessages errors)

Save the specified error messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="false") or \<html:errors\>, if any error messages are required. Otherwise, ensure that the session attribute is empty.

**Parameters:**  
`session` - The session to save the error messages in.

`errors` - The error messages to save. `null` or empty messages removes any existing error ActionMessages in the session.

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### saveToken

    protected void saveToken(HttpServletRequest request)

Save a new transaction token in the user's current session, creating a new session if necessary.

**Parameters:**  
`request` - The servlet request we are processing

------------------------------------------------------------------------

### setLocale

    protected void setLocale(HttpServletRequest request,
                             Locale locale)

Set the user's currently selected `Locale` into their `HttpSession`.

**Parameters:**  
`request` - The request we are processing

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/Action.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/Action.html"><strong>FRAMES</strong></a>    <a href="Action.html"><strong>NO FRAMES</strong></a>    
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
