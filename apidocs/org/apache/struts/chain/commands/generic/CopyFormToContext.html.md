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
<td align="left"><a href="class-use/CopyFormToContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/chain/commands/generic/WrappingLookupCommand.html.md" title="class in org.apache.struts.chain.commands.generic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/generic/CopyFormToContext.html"><strong>FRAMES</strong></a>    <a href="CopyFormToContext.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.chain.commands.generic
 Class CopyFormToContext
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.ActionCommandBase
          org.apache.struts.chain.commands.generic.CopyFormToContext

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, [ActionCommand](../../../../../../org/apache/struts/chain/commands/ActionCommand.html.md "interface in org.apache.struts.chain.commands")

------------------------------------------------------------------------

    public class CopyFormToContext

extends [ActionCommandBase](../../../../../../org/apache/struts/chain/commands/ActionCommandBase.html.md "class in org.apache.struts.chain.commands")

Subclass this command and configure it as part of a per-forward chain to perform any necessary pre-population or other preparation for a form before control is dispatched to the view layer.

**Version:**  
$Id: CopyFormToContext.java 471754 2006-11-06 14:55:09Z husted $

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
| ` CopyFormToContext()`  
                          |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(ActionContext actionContext)`
           Look up an ActionForm instance based on the configured properties of this command and copy it into the `Context`.

`protected  ActionForm`

` findOrCreateForm(ActionContext context)`
           Based on the properties of this command and the given `ActionContext`, find or create an ActionForm instance for preparation.

`protected  ActionForm`

` findOrCreateForm(ActionContext ctx, String effectiveFormName, String effectiveScope)`
           Actually find or create an instance of ActionForm configured under the form-bean-name `effectiveFormName`, looking in in the `ActionContext's` scope as identified by `effectiveScope`.

` String`

` getActionPath()`
           Return ActionPath property.

` String`

` getFormName()`
           Return FormName property.

` String`

` getScope()`
           Return Scope property.

` String`

` getToKey()`
           Return ToKey property.

` void`

` setActionPath(String actionPath)`
           Set ActionPath property.

` void`

` setFormName(String formName)`
           Set FormName property.

` void`

` setScope(String scope)`
           Set Scope property.

` void`

` setToKey(String toKey)`
           Set ToKey property.

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

### CopyFormToContext

    public CopyFormToContext()

<span id="method_detail"></span>

**Method Detail**

### getActionPath

    public String getActionPath()

Return ActionPath property.

**Returns:**  
ActionPath property

------------------------------------------------------------------------

### setActionPath

    public void setActionPath(String actionPath)

Set ActionPath property.

**Parameters:**  
`actionPath` - New valuefor ActionPath

------------------------------------------------------------------------

### getFormName

    public String getFormName()

Return FormName property.

**Returns:**  
FormName property

------------------------------------------------------------------------

### setFormName

    public void setFormName(String formName)

Set FormName property.

**Parameters:**  
`formName` - New valuefor FormName

------------------------------------------------------------------------

### getScope

    public String getScope()

Return Scope property.

**Returns:**  
Scope property

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

Set Scope property.

**Parameters:**  
`scope` - New valuefor Scope

------------------------------------------------------------------------

### getToKey

    public String getToKey()

Return ToKey property.

**Returns:**  
ToKey property

------------------------------------------------------------------------

### setToKey

    public void setToKey(String toKey)

Set ToKey property.

**Parameters:**  
`toKey` - New valuefor FormName

------------------------------------------------------------------------

### execute

    public boolean execute(ActionContext actionContext)
                    throws Exception

Look up an ActionForm instance based on the configured properties of this command and copy it into the `Context`. After this command successfully executes, an ActionForm instance will exist in the specified scope and will be available, for example for backing fields in an HTML form. It will also be in the `ActionContext` available for another command to do prepopulation of values or other preparation.

**Specified by:**  
` execute` in interface `ActionCommand`

**Specified by:**  
` execute` in class `ActionCommandBase`

<!-- -->

**Parameters:**  
`actionContext` - Our ActionContext

**Returns:**  
TRUE if processing should halt

**Throws:**  
`Exception` - on any error

------------------------------------------------------------------------

### findOrCreateForm

    protected ActionForm findOrCreateForm(ActionContext context)
                                   throws IllegalAccessException,
                                          InstantiationException

Based on the properties of this command and the given `ActionContext`, find or create an ActionForm instance for preparation.

**Parameters:**  
`context` - ActionContextBase class that we are processing

**Returns:**  
ActionForm instance

**Throws:**  
`IllegalArgumentException` - On ActionConfig not found

`IllegalStateException` - On undefined scope and formbean

`IllegalAccessException` - On failed instantiation

`InstantiationException` - If ActionContext is not subsclass of ActionContextBase

------------------------------------------------------------------------

### findOrCreateForm

    protected ActionForm findOrCreateForm(ActionContext ctx,
                                          String effectiveFormName,
                                          String effectiveScope)
                                   throws IllegalAccessException,
                                          InstantiationException

Actually find or create an instance of ActionForm configured under the form-bean-name `effectiveFormName`, looking in in the `ActionContext's` scope as identified by `effectiveScope`. If a form is created, it will also be stored in that scope.

**NOTE:** This specific method depends on the instance of `ActionContext` which is passed being a subclass of `ActionContextBase`, which implements the utility method `findOrCreateActionForm`.

**Parameters:**  
`ctx` - The ActionContext we are processing

`effectiveFormName` - the target form name

`effectiveScope` - The target scope

**Returns:**  
ActionForm instnace, storing in scope if created

**Throws:**  
`InstantiationException` - If ActionContext is not subsclass of ActionContextBase

`InstantiationException` - If object cannot be created

`IllegalArgumentException` - On form not found in/ scope

`IllegalAccessException` - On failed instantiation

`IllegalStateException` - If ActionContext is not a subclass of ActionBase

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
<td align="left"><a href="class-use/CopyFormToContext.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/chain/commands/generic/WrappingLookupCommand.html.md" title="class in org.apache.struts.chain.commands.generic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/generic/CopyFormToContext.html"><strong>FRAMES</strong></a>    <a href="CopyFormToContext.html"><strong>NO FRAMES</strong></a>    
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
