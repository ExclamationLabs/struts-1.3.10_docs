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
<td align="left"><a href="class-use/WrappingLookupCommand.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/generic/CopyFormToContext.html.md" title="class in org.apache.struts.chain.commands.generic"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/generic/WrappingLookupCommand.html"><strong>FRAMES</strong></a>    <a href="WrappingLookupCommand.html"><strong>NO FRAMES</strong></a>    
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
 Class WrappingLookupCommand
----------------------------------------

    java.lang.Object
      org.apache.struts.chain.commands.generic.WrappingLookupCommand

**All Implemented Interfaces:**  
org.apache.commons.chain.Command, org.apache.commons.chain.Filter

------------------------------------------------------------------------

    public class WrappingLookupCommand

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements org.apache.commons.chain.Filter

Variant on chain LookupCommand which can optionally wrap the context it passes to the looked up command in an alternative class.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary**               |
|---------------------------------------|
| ` WrappingLookupCommand()`            
            Zero-argument constructor.  |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` execute(org.apache.commons.chain.Context context)`
           Invoke the Command for a Context, returning TRUE if processing should halt.

` String`

` getCatalogName()`
           Return CatalogName property.

`protected  org.apache.commons.chain.Command`

` getCommand(org.apache.commons.chain.Context context)`
           Return the Command to process for this Context.

`protected  org.apache.commons.chain.Context`

` getContext(org.apache.commons.chain.Context context)`
           If the wrapperClassName property is not null, return a Context of the type specified by wrapperClassName, instantiated using a single-arg constructor which takes the context passed as an argument to this method.

` String`

` getName()`
           Retrieve Name property.

` String`

` getNameKey()`
           Return NameKey property.

` String`

` getWrapperClassName()`
           Return the WrapperClass property.

` boolean`

` isOptional()`
           Test Optional property.

` boolean`

` postprocess(org.apache.commons.chain.Context context, Exception exception)`
           Process the Exception for any Command that is a filter.

` void`

` setCatalogName(String catalogName)`
           Set CatalogName property.

` void`

` setName(String name)`
           Set Name property.

` void`

` setNameKey(String nameKey)`
           Set NameKey property.

` void`

` setOptional(boolean optional)`
           Set Optional property.

` void`

` setWrapperClassName(String wrapperClassName)`
           Set WrappClassName property.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### WrappingLookupCommand

    public WrappingLookupCommand()

Zero-argument constructor.

<span id="method_detail"></span>

**Method Detail**

### getCatalogName

    public String getCatalogName()

Return CatalogName property.

**Returns:**  
Value of CatalogName property.

------------------------------------------------------------------------

### setCatalogName

    public void setCatalogName(String catalogName)

Set CatalogName property.

**Parameters:**  
`catalogName` - New value for CatalogName

------------------------------------------------------------------------

### getName

    public String getName()

Retrieve Name property.

**Returns:**  
Value of Name property

------------------------------------------------------------------------

### setName

    public void setName(String name)

Set Name property.

**Parameters:**  
`name` - New value for Name

------------------------------------------------------------------------

### getNameKey

    public String getNameKey()

Return NameKey property.

**Returns:**  
Value of NameKey property.

------------------------------------------------------------------------

### setNameKey

    public void setNameKey(String nameKey)

Set NameKey property.

**Parameters:**  
`nameKey` - New value for NameKey

------------------------------------------------------------------------

### isOptional

    public boolean isOptional()

Test Optional property.

**Returns:**  
TRUE if Optional is TRUE.

------------------------------------------------------------------------

### setOptional

    public void setOptional(boolean optional)

Set Optional property.

**Parameters:**  
`optional` - New value for Optional

------------------------------------------------------------------------

### getWrapperClassName

    public String getWrapperClassName()

Return the WrapperClass property.

**Returns:**  
The WrapperClass property

------------------------------------------------------------------------

### setWrapperClassName

    public void setWrapperClassName(String wrapperClassName)

Set WrappClassName property.

**Parameters:**  
`wrapperClassName` - The name of a WrapperClass

------------------------------------------------------------------------

### execute

    public boolean execute(org.apache.commons.chain.Context context)
                    throws Exception

Invoke the Command for a Context, returning TRUE if processing should halt.

**Specified by:**  
`execute` in interface `org.apache.commons.chain.Command`

<!-- -->

**Parameters:**  
`context` - Our ActionContext

**Returns:**  
TRUE if processing should halt

**Throws:**  
`Exception` - On any error

------------------------------------------------------------------------

### postprocess

    public boolean postprocess(org.apache.commons.chain.Context context,
                               Exception exception)

Process the Exception for any Command that is a filter.

**Specified by:**  
`postprocess` in interface `org.apache.commons.chain.Filter`

<!-- -->

**Parameters:**  
`context` - Our ActionContext

`exception` - The Exception thrown by another Comamnd in a Chain

**Returns:**  
TRUE if there is a Filter to process

------------------------------------------------------------------------

### getCommand

    protected org.apache.commons.chain.Command getCommand(org.apache.commons.chain.Context context)

Return the Command to process for this Context.

**Parameters:**  
`context` - The Context we are processing

**Returns:**  
The Command to process for this Context

------------------------------------------------------------------------

### getContext

    protected org.apache.commons.chain.Context getContext(org.apache.commons.chain.Context context)
                                                   throws ClassNotFoundException,
                                                          InstantiationException,
                                                          InvocationTargetException,
                                                          IllegalAccessException,
                                                          NoSuchMethodException

If the wrapperClassName property is not null, return a Context of the type specified by wrapperClassName, instantiated using a single-arg constructor which takes the context passed as an argument to this method.

This method throws an exception if the wrapperClass cannot be found, or if there are any errors instantiating the wrapping context.

**Parameters:**  
`context` - Context we are processing

**Returns:**  
Context wrapper

**Throws:**  
`ClassNotFoundException` - On failed instantiation

`InstantiationException` - On failed instantiation

`InvocationTargetException` - On failed instantiation

`IllegalAccessException` - On failed instantiation

`NoSuchMethodException` - On failed instantiation

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
<td align="left"><a href="class-use/WrappingLookupCommand.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/chain/commands/generic/CopyFormToContext.html.md" title="class in org.apache.struts.chain.commands.generic"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/chain/commands/generic/WrappingLookupCommand.html"><strong>FRAMES</strong></a>    <a href="WrappingLookupCommand.html"><strong>NO FRAMES</strong></a>    
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
