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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/AbstractAuthorizeAction.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html.md" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/AbstractAuthorizeAction.html"><strong>FRAMES</strong></a>    <a href="AbstractAuthorizeAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain.commands
 Class AbstractAuthorizeAction
--------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractAuthorizeAction

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

<!-- -->

**Direct Known Subclasses:**  
[AuthorizeAction](../../../../../org/apache/struts/chain/commands/servlet/AuthorizeAction.html.md "class in org.apache.struts.chain.commands.servlet")

------------------------------------------------------------------------

    public abstract class AbstractAuthorizeAction

extends [ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")

Determine whether the requested action is authorized for the current user. If not, abort chain processing and perferably, return an error message of some kind.

**Version:**  
$Rev: 481115 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` AbstractAuthorizeAction()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(ActionContext actionCtx)`
           Determine whether the requested action is authorized for the current user.

`protected abstract  String`

` getErrorMessage(ActionContext context, ActionConfig actionConfig)`
            Retrieve error message from context.

`protected  boolean`

` isAuthorizationRequired(ActionConfig actionConfig)`
           Must authorization rules be consulted? The base implementation returns `true` if the given `ActionConfig` has one or more roles defined.

`protected abstract  boolean`

` isAuthorized(ActionContext context, String[] roles, ActionConfig actionConfig)`
           Determine if the action is authorized for the given roles.

 <span id="methods_inherited_from_class_org.apache.struts.chain.commands.ActionCommandBase"></span>

| **Methods inherited from class org.apache.struts.chain.commands.[ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` execute`                                                                                                                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### AbstractAuthorizeAction

    public AbstractAuthorizeAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public boolean execute(ActionContext actionCtx)
                    throws Exception

Determine whether the requested action is authorized for the current user. If not, abort chain processing and perferably, return an error message of some kind.

**Specified by:**  
` execute` in interface `ActionCommand`

**Specified by:**  
` execute` in class `ActionCommandBase`

<!-- -->

**Parameters:**  
`actionCtx` - The `Context` for the current request

**Returns:**  
`false` if the user is authorized for the selected action, else `true` to abort processing.

**Throws:**  
`UnauthorizedActionException` - if authorization fails or if an error is encountered in the course of performing the authorization.

`Exception` - On any error

------------------------------------------------------------------------

### isAuthorizationRequired

    protected boolean isAuthorizationRequired(ActionConfig actionConfig)

Must authorization rules be consulted? The base implementation returns `true` if the given `ActionConfig` has one or more roles defined.

**Parameters:**  
`actionConfig` - the current ActionConfig object

**Returns:**  
true if the `isAuthorized` method should be consulted.

------------------------------------------------------------------------

### isAuthorized

    protected abstract boolean isAuthorized(ActionContext context,
                                            String[] roles,
                                            ActionConfig actionConfig)
                                     throws Exception

Determine if the action is authorized for the given roles.

**Parameters:**  
`context` - The `Context` for the current request

`roles` - An array of valid roles for this request

`actionConfig` - The current action mapping

**Returns:**  
`true` if the request is authorized, else `false`

**Throws:**  
`UnauthorizedActionException` - If the logic determines that the request is not authorized but does not wish to rely upon the default mechanism reporting the error.

`Exception` - If the action cannot be tested for authorization

------------------------------------------------------------------------

### getErrorMessage

    protected abstract String getErrorMessage(ActionContext context,
                                              ActionConfig actionConfig)

Retrieve error message from context.

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/AbstractAuthorizeAction.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/chain/commands/AbstractCreateAction.html.md" title="class in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/AbstractAuthorizeAction.html"><strong>FRAMES</strong></a>    <a href="AbstractAuthorizeAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
