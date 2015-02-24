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
<td align="left"><a href="../../../../org/apache/struts/scripting/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/StrutsInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/ScriptAction.html.md" title="class in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/TestFilter.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/StrutsInfo.html"><strong>FRAMES</strong></a>    <a href="StrutsInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.scripting
 Class StrutsInfo
---------------------------

    java.lang.Object
      org.apache.struts.scripting.StrutsInfo

------------------------------------------------------------------------

    public class StrutsInfo

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Holds Struts objects.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                          |
|--------------------------------------------------------------------------------------------------|
| ` StrutsInfo(ScriptAction action, ActionMapping mapping, ActionForm form, MessageResources res)` 
            Constructor.                                                                           |

  <span id="method_summary"></span>

**Method Summary**

` ScriptAction`

` getAction()`
           Gets the action instance.

` ActionForm`

` getForm()`
           Gets the action form.

` ActionForward`

` getForward()`
           Gets the forward object.

` ActionMapping`

` getMapping()`
           Gets the action mapping.

` MessageResources`

` getMessages()`
           Gets the message resources.

` void`

` setAction(ScriptAction action)`
           Sets the action instance.

` void`

` setForm(ActionForm form)`
           Sets the action form.

` void`

` setForward(ActionForward f)`
           Sets the action forward object.

` void`

` setForwardName(String f)`
           Sets the forward name.

` void`

` setMapping(ActionMapping mapping)`
           Sets the action mapping.

` void`

` setMessages(MessageResources res)`
           Sets the message resources.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### StrutsInfo

    public StrutsInfo(ScriptAction action,
                      ActionMapping mapping,
                      ActionForm form,
                      MessageResources res)

Constructor.

**Parameters:**  
`action` - The action instance

`mapping` - The action mapping

`form` - The action form

`res` - The message resources for the current locale

<span id="method_detail"></span>

**Method Detail**

### setForwardName

    public void setForwardName(String f)

Sets the forward name.

**Parameters:**  
`f` - The forward name

------------------------------------------------------------------------

### getForward

    public ActionForward getForward()

Gets the forward object. If none is set, it tries to find the set forward name.

**Returns:**  
The action forward

------------------------------------------------------------------------

### setForward

    public void setForward(ActionForward f)

Sets the action forward object.

**Parameters:**  
`f` - The action forward

------------------------------------------------------------------------

### setForm

    public void setForm(ActionForm form)

Sets the action form.

**Parameters:**  
`form` - The action form

------------------------------------------------------------------------

### setMapping

    public void setMapping(ActionMapping mapping)

Sets the action mapping.

**Parameters:**  
`mapping` - The action mapping

------------------------------------------------------------------------

### setAction

    public void setAction(ScriptAction action)

Sets the action instance.

**Parameters:**  
`action` - The Struts action

------------------------------------------------------------------------

### setMessages

    public void setMessages(MessageResources res)

Sets the message resources.

**Parameters:**  
`res` - The message resources

------------------------------------------------------------------------

### getForm

    public ActionForm getForm()

Gets the action form.

**Returns:**  
The action form

------------------------------------------------------------------------

### getMapping

    public ActionMapping getMapping()

Gets the action mapping.

**Returns:**  
The action mapping

------------------------------------------------------------------------

### getAction

    public ScriptAction getAction()

Gets the action instance.

**Returns:**  
The Struts action

------------------------------------------------------------------------

### getMessages

    public MessageResources getMessages()

Gets the message resources.

**Returns:**  
The message resources

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
<td align="left"><a href="../../../../org/apache/struts/scripting/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/StrutsInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/ScriptAction.html.md" title="class in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/TestFilter.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/StrutsInfo.html"><strong>FRAMES</strong></a>    <a href="StrutsInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
