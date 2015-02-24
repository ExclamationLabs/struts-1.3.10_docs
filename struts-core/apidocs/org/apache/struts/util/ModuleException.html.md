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
<td align="left"><a href="class-use/ModuleException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/MessageResourcesFactory.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ModuleUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ModuleException.html"><strong>FRAMES</strong></a>    <a href="ModuleException.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.util
 Class ModuleException
----------------------

    java.lang.Object
      java.lang.Throwable
          java.lang.Exception
              org.apache.struts.util.ModuleException

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ModuleException

extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html.md?is-external=true "class or interface in java.lang")

Used for specialized exception handling.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.ModuleException)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ActionMessage`

`message`
           The ActionMessage associated with this exception.

`protected  String`

`property`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                    |
|--------------------------------------------------------------------------------------------|
| ` ModuleException(String key)`                                                             
            Construct an module exception with no replacement values.                        |
| ` ModuleException(String key, Object value)`                                               
            Construct an module exception with the specified replacement values.             |
| ` ModuleException(String key, Object[] values)`                                            
            Construct an error with the specified replacement values.                        |
| ` ModuleException(String key, Object value0, Object value1)`                               
            Construct an module exception with the specified replacement values.             |
| ` ModuleException(String key, Object value0, Object value1, Object value2)`                
            Construct an module exception with the specified replacement values.             |
| ` ModuleException(String key, Object value0, Object value1, Object value2, Object value3)` 
            Construct an module exception with the specified replacement values.             |

  <span id="method_summary"></span>

**Method Summary**

` ActionMessage`

` getActionMessage()`
           Returns the error associated with the exception.

` String`

` getProperty()`
           Returns the property associated with the exception.

` void`

` setProperty(String property)`
           Set the property associated with the exception.

 <span id="methods_inherited_from_class_java.lang.Throwable"></span>

| **Methods inherited from class java.lang.[Throwable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Throwable.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString`         |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="property"></span>

### property

    protected String property

------------------------------------------------------------------------

<span id="message"></span>

### message

    protected ActionMessage message

The ActionMessage associated with this exception.

**Since:**  
Struts 1.2

<span id="constructor_detail"></span>

**Constructor Detail**

### ModuleException

    public ModuleException(String key)

Construct an module exception with no replacement values.

**Parameters:**  
`key` - Message key for this error message

------------------------------------------------------------------------

### ModuleException

    public ModuleException(String key,
                           Object value)

Construct an module exception with the specified replacement values.

**Parameters:**  
`key` - Message key for this error message

`value` - First replacement value

------------------------------------------------------------------------

### ModuleException

    public ModuleException(String key,
                           Object value0,
                           Object value1)

Construct an module exception with the specified replacement values.

**Parameters:**  
`key` - Message key for this error message

`value0` - First replacement value

`value1` - Second replacement value

------------------------------------------------------------------------

### ModuleException

    public ModuleException(String key,
                           Object value0,
                           Object value1,
                           Object value2)

Construct an module exception with the specified replacement values.

**Parameters:**  
`key` - Message key for this error message

`value0` - First replacement value

`value1` - Second replacement value

`value2` - Third replacement value

------------------------------------------------------------------------

### ModuleException

    public ModuleException(String key,
                           Object value0,
                           Object value1,
                           Object value2,
                           Object value3)

Construct an module exception with the specified replacement values.

**Parameters:**  
`key` - Message key for this error message

`value0` - First replacement value

`value1` - Second replacement value

`value2` - Third replacement value

`value3` - Fourth replacement value

------------------------------------------------------------------------

### ModuleException

    public ModuleException(String key,
                           Object[] values)

Construct an error with the specified replacement values.

**Parameters:**  
`key` - Message key for this message

`values` - Array of replacement values

<span id="method_detail"></span>

**Method Detail**

### getProperty

    public String getProperty()

Returns the property associated with the exception.

**Returns:**  
Value of property.

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

Set the property associated with the exception. It can be a name of the edit field, which 'caused' the exception.

------------------------------------------------------------------------

### getActionMessage

    public ActionMessage getActionMessage()

Returns the error associated with the exception.

**Returns:**  
Value of property error.

**Since:**  
Struts 1.2

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
<td align="left"><a href="class-use/ModuleException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/MessageResourcesFactory.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ModuleUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ModuleException.html"><strong>FRAMES</strong></a>    <a href="ModuleException.html"><strong>NO FRAMES</strong></a>    
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
