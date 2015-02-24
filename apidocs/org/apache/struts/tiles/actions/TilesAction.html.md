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
<td align="left"><a href="class-use/TilesAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/actions/ReloadDefinitionsAction.html.md" title="class in org.apache.struts.tiles.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/actions/ViewDefinitionsAction.html" title="class in org.apache.struts.tiles.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/actions/TilesAction.html"><strong>FRAMES</strong></a>    <a href="TilesAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.Action">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.actions
 Class TilesAction
-------------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.tiles.actions.TilesAction

------------------------------------------------------------------------

    public abstract class TilesAction

extends [Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")

Base class for Tiles Actions. This class has the same role as Struts Action. It provides a method execute(...) called when action is invoked. The difference is, that the execute() method takes an additional parameter : tile context. This class extends Struts Action. Subclasses should override execute(ComponentContext ...) method instead of Struts execute(ActionMapping ...) method.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                                  |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TilesAction()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Original Struts Action's method.

` ActionForward`

` execute(ComponentContext context, ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                                                                                                |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getLocale,  getMessages,  getResources,  getResources, getServlet,  isCancelled,  isTokenValid,  isTokenValid,  resetToken,  saveErrors,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesAction

    public TilesAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Original Struts Action's method. Retrieve current Tile context and call TilesAction execute method. Do not overload this method!

**Overrides:**  
` execute` in class `Action`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance.

`form` - The optional ActionForm bean for this request (if any).

`request` - The HTTP request we are processing.

`response` - The HTTP response we are creating.

**Returns:**  
The forward to which control should be transferred, or `null` if the response has been completed.

**Throws:**  
`Exception` - if the application business logic throws an exception

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### execute

    public ActionForward execute(ComponentContext context,
                                 ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request and create the corresponding HTTP response (or forward to another web component that will create it), with provision for handling exceptions thrown by the business logic.
 Override this method to provide functionality.

**Parameters:**  
`context` - The current Tile context, containing Tile attributes.

`mapping` - The ActionMapping used to select this instance.

`form` - The optional ActionForm bean for this request (if any).

`request` - The HTTP request we are processing.

`response` - The HTTP response we are creating.

**Throws:**  
`Exception` - if the application business logic throws an exception

**Since:**  
Struts 1.1

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
<td align="left"><a href="class-use/TilesAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/actions/ReloadDefinitionsAction.html.md" title="class in org.apache.struts.tiles.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/actions/ViewDefinitionsAction.html" title="class in org.apache.struts.tiles.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/actions/TilesAction.html"><strong>FRAMES</strong></a>    <a href="TilesAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.Action">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
