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
<td align="left"><a href="class-use/LocaleAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/LogoffAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/LocaleAction.html"><strong>FRAMES</strong></a>    <a href="LocaleAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.apps.mailreader.actions.BaseAction">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader.actions
 Class LocaleAction
-----------------------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.MappingDispatchAction
                      org.apache.struts.apps.mailreader.actions.BaseAction
                          org.apache.struts.apps.mailreader.actions.LocaleAction

------------------------------------------------------------------------

    public final class LocaleAction

extends [BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")

Change user's Struts [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util").

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

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
| ` LocaleAction()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
            Change the user's Struts [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") based on request parameters for "language", "country".

 <span id="methods_inherited_from_class_org.apache.struts.apps.mailreader.actions.BaseAction"></span>

| **Methods inherited from class org.apache.struts.apps.mailreader.actions.[BaseAction](../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md "class in org.apache.struts.apps.mailreader.actions")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` doCancel,  doFindFailure,  doFindLogon,  doFindSuccess,  doGet,  doGetSubscription,  doGetSubscription,  doGetUser,  doGetUser,  doGetUserDatabase,  doInputForward,  doLogProcess,  doSaveToken,  doSaveUser,  doSet`  |

 <span id="methods_inherited_from_class_org.apache.struts.actions.MappingDispatchAction"></span>

| **Methods inherited from class org.apache.struts.actions.[MappingDispatchAction](http://struts.apache.org/apidocs/org/apache/struts/actions/MappingDispatchAction.html.md?is-external=true "class or interface in org.apache.struts.actions")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMethodName, getParameter, unspecified`                                                                                                                                                                                                   |

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

 

<span id="constructor_detail"></span>

**Constructor Detail**

### LocaleAction

    public LocaleAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Change the user's Struts [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") based on request parameters for "language", "country". After setting the Locale, control is forwarded to an URI path indicated by a "page" parameter, or a forward indicated by a "forward" parameter, or to a forward given as the mappings "parameter" property. The response location must be specified one of these ways.

**Overrides:**  
`execute` in class `MappingDispatchAction`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

**Returns:**  
An ActionForward indicate the resources that will render the response

**Throws:**  
`Exception` - if an input/output error or servlet exception occurs

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
<td align="left"><a href="class-use/LocaleAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/apps/mailreader/actions/BaseAction.html.md" title="class in org.apache.struts.apps.mailreader.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/apps/mailreader/actions/LogoffAction.html" title="class in org.apache.struts.apps.mailreader.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/apps/mailreader/actions/LocaleAction.html"><strong>FRAMES</strong></a>    <a href="LocaleAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.apps.mailreader.actions.BaseAction">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
