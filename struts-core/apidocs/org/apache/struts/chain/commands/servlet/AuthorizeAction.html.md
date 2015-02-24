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
<td align="left"><a href="class-use/AuthorizeAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/AuthorizeAction.html"><strong>FRAMES</strong></a>    <a href="AuthorizeAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.commands.servlet
 Class AuthorizeAction
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractAuthorizeAction
              org.apache.struts.chain.commands.servlet.AuthorizeAction

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class AuthorizeAction

extends [AbstractAuthorizeAction](../../../../../../org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md "class in org.apache.struts.chain.commands")

Determine if the action is authorized for the given roles.

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` AuthorizeAction()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  String`

` getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            Retrieve error message from context.

`protected  boolean`

` isAuthorized(ActionContext context, String[] roles, ActionConfig mapping)`
           Determine if the action is authorized for the given roles.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.AbstractAuthorizeAction"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[AbstractAuthorizeAction](../../../../../../org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md "class in org.apache.struts.chain.commands")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute,  isAuthorizationRequired`                                                                                                                                                                                     |

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.ActionCommandBase"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### AuthorizeAction

    public AuthorizeAction()

<span id="method_detail"></span>

**Method Detail**

### isAuthorized

    protected boolean isAuthorized(ActionContext context,
                                   String[] roles,
                                   ActionConfig mapping)
                            throws Exception

**Description copied from class: ` AbstractAuthorizeAction`**

Determine if the action is authorized for the given roles.

**Specified by:**  
` isAuthorized` in class `AbstractAuthorizeAction`

<!-- -->

**Parameters:**  
`context` - The `Context` for the current request

`roles` - An array of valid roles for this request

`mapping` - The current action mapping

**Returns:**  
`true` if the request is authorized, else `false`

**Throws:**  
`UnauthorizedActionException` - If the logic determines that the request is not authorized but does not wish to rely upon the default mechanism reporting the error.

`Exception` - If the action cannot be tested for authorization

------------------------------------------------------------------------

### getErrorMessage

    protected String getErrorMessage(ActionContext context,
                                     ActionConfig actionConfig)

**Description copied from class: ` AbstractAuthorizeAction`**

Retrieve error message from context.

**Specified by:**  
` getErrorMessage` in class `AbstractAuthorizeAction`

<!-- -->

**Parameters:**  
`context` - The `Context` for the current request

`actionConfig` - The current action mapping

**Returns:**  
error message

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
<td align="left"><a href="class-use/AuthorizeAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/chain/commands/servlet/CreateAction.html.md" title="class in org.apache.struts.chain.commands.servlet"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/servlet/AuthorizeAction.html"><strong>FRAMES</strong></a>    <a href="AuthorizeAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
