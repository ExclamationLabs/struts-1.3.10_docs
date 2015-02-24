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
<td align="left"><a href="class-use/BaseAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/ActionDispatcher.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/BaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.action.Action">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.actions
 Class BaseAction
-------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction

**Direct Known Subclasses:**  
[DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions"), [DownloadAction](../../../../org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions"), [ForwardAction](../../../../org/apache/struts/actions/ForwardAction.html "class in org.apache.struts.actions"), [IncludeAction](../../../../org/apache/struts/actions/IncludeAction.html "class in org.apache.struts.actions"), [LocaleAction](../../../../org/apache/struts/actions/LocaleAction.html "class in org.apache.struts.actions"), [SwitchAction](../../../../org/apache/struts/actions/SwitchAction.html "class in org.apache.struts.actions")

------------------------------------------------------------------------

    public abstract class BaseAction

extends [Action](http://struts.apache.org/apidocs/org/apache/struts/action/Action.html.md?is-external=true "class or interface in org.apache.struts.action")

BaseAction is provided as an intermediate class for shared funtionality between `Action` and any stock implementation provided in this package.

**Since:**  
Struts 1.3

**Version:**  
$Rev$ $Date$

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static MessageResources`

`messages`
           The message resources for this package.

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

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](http://struts.apache.org/apidocs/org/apache/struts/action/Action.html.md?is-external=true "class or interface in org.apache.struts.action")**                                                                     |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addErrors, addMessages, execute, execute, generateToken, getErrors, getLocale, getMessages, getResources, getResources, getServlet, isCancelled, isTokenValid, isTokenValid, resetToken, saveErrors, saveErrors, saveMessages, saveMessages, saveToken, setLocale, setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

<span id="constructor_detail"></span>

**Constructor Detail**

### BaseAction

    public BaseAction()

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
<td align="left"><a href="class-use/BaseAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/ActionDispatcher.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/DispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/BaseAction.html"><strong>FRAMES</strong></a>    <a href="BaseAction.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.action.Action">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
