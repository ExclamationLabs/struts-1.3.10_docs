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
<td align="left"><a href="class-use/AbstractValidateActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/AbstractSetOriginalURI.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ActionCommand.html" title="interface in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/AbstractValidateActionForm.html"><strong>FRAMES</strong></a>    <a href="AbstractValidateActionForm.html"><strong>NO FRAMES</strong></a>    
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
 Class AbstractValidateActionForm
---------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.AbstractValidateActionForm

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

<!-- -->

**Direct Known Subclasses:**  
[ValidateActionForm](../../../../../org/apache/struts/chain/commands/servlet/ValidateActionForm.html.md "class in org.apache.struts.chain.commands.servlet")

------------------------------------------------------------------------

    public abstract class AbstractValidateActionForm

extends [ActionCommandBase](../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")

Validate the properties of the form bean for this request. If there are any validation errors, execute the specified command; otherwise, proceed normally.

**Version:**  
$Rev: 481833 $ $Date: 2005-06-04 10:58:46 -0400 (Sat, 04 Jun 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` AbstractValidateActionForm()` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(ActionContext actionCtx)`
           Validate the properties of the form bean for this request.

`protected abstract  ActionErrors`

` validate(ActionContext context, ActionConfig actionConfig, ActionForm actionForm)`
           Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

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

### AbstractValidateActionForm

    public AbstractValidateActionForm()

<span id="method_detail"></span>

**Method Detail**

### execute

    public boolean execute(ActionContext actionCtx)
                    throws Exception

Validate the properties of the form bean for this request. If there are any validation errors, execute the child commands in our chain; otherwise, proceed normally.

**Specified by:**  
` execute` in interface `ActionCommand`

**Specified by:**  
` execute` in class `ActionCommandBase`

<!-- -->

**Parameters:**  
`actionCtx` - The `Context` for the current request

**Returns:**  
`false` so that processing continues, if there are no validation errors; otherwise `true`

**Throws:**  
`Exception` - if thrown by the Action class

------------------------------------------------------------------------

### validate

    protected abstract ActionErrors validate(ActionContext context,
                                             ActionConfig actionConfig,
                                             ActionForm actionForm)

Call the `validate()` method of the specified form bean, and return the resulting `ActionErrors` object.

**Parameters:**  
`context` - The context for this request

`actionConfig` - The `ActionConfig` for this request

`actionForm` - The form bean for this request

**Returns:**  
ActionErrors object, if any

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
<td align="left"><a href="class-use/AbstractValidateActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/chain/commands/AbstractSetOriginalURI.html.md" title="class in org.apache.struts.chain.commands"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/chain/commands/ActionCommand.html" title="interface in org.apache.struts.chain.commands"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/chain/commands/AbstractValidateActionForm.html"><strong>FRAMES</strong></a>    <a href="AbstractValidateActionForm.html"><strong>NO FRAMES</strong></a>    
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
