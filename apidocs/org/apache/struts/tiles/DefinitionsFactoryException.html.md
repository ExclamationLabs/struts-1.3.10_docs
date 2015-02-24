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
<td align="left"><a href="class-use/DefinitionsFactoryException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsUtil.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactoryException.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryException.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles
 Class DefinitionsFactoryException
----------------------------------

    java.lang.Object
      java.lang.Throwable
          java.lang.Exception
              org.apache.struts.tiles.TilesException
                  org.apache.struts.tiles.DefinitionsFactoryException

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[FactoryNotFoundException](../../../../org/apache/struts/tiles/FactoryNotFoundException.html.md "class in org.apache.struts.tiles"), [NoSuchDefinitionException](../../../../org/apache/struts/tiles/NoSuchDefinitionException.html "class in org.apache.struts.tiles")

------------------------------------------------------------------------

    public class DefinitionsFactoryException

extends [TilesException](../../../../org/apache/struts/tiles/TilesException.html.md "class in org.apache.struts.tiles")

Exception thrown when an error occurs while the factory tries to create a new instance mapper.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.DefinitionsFactoryException)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                               |
|---------------------------------------------------------------------------------------|
| ` DefinitionsFactoryException()`                                                      
            Constructor.                                                                |
| ` DefinitionsFactoryException(Exception e)`                                           
            Create a new `DefinitionsFactoryException` wrapping an existing exception.  |
| ` DefinitionsFactoryException(String message)`                                        
            Constructor.                                                                |
| ` DefinitionsFactoryException(String message, Exception e)`                           
            Create a new `DefinitionsFactoryException` from an existing exception.      |

  <span id="method_summary"></span>

**Method Summary**

` Exception`

` getException()`
           Return the embedded exception, if any.

` String`

` getMessage()`
           Return a detail message for this exception.

 <span id="methods_inherited_from_class_java.lang.Throwable"></span>

| **Methods inherited from class java.lang.[Throwable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Throwable.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `fillInStackTrace, getCause, getLocalizedMessage, getStackTrace, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString`                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### DefinitionsFactoryException

    public DefinitionsFactoryException()

Constructor.

------------------------------------------------------------------------

### DefinitionsFactoryException

    public DefinitionsFactoryException(String message)

Constructor.

**Parameters:**  
`message` - The error or warning message.

------------------------------------------------------------------------

### DefinitionsFactoryException

    public DefinitionsFactoryException(Exception e)

Create a new `DefinitionsFactoryException` wrapping an existing exception.

The existing exception will be embedded in the new one and its message will become the default message for the DefinitionsFactoryException.

**Parameters:**  
`e` - The exception to be wrapped.

------------------------------------------------------------------------

### DefinitionsFactoryException

    public DefinitionsFactoryException(String message,
                                       Exception e)

Create a new `DefinitionsFactoryException` from an existing exception.

The existing exception will be embedded in the new one, but the new exception will have its own message.

**Parameters:**  
`message` - The detail message.

`e` - The exception to be wrapped.

<span id="method_detail"></span>

**Method Detail**

### getMessage

    public String getMessage()

Return a detail message for this exception.

If there is a embedded exception, and if the DefinitionsFactoryException has no detail message of its own, this method will return the detail message from the embedded exception.

**Overrides:**  
` getMessage` in class `TilesException`

<!-- -->

**Returns:**  
The error or warning message.

------------------------------------------------------------------------

### getException

    public Exception getException()

Return the embedded exception, if any.

**Overrides:**  
` getException` in class `TilesException`

<!-- -->

**Returns:**  
The embedded exception, or `null` if there is none.

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
<td align="left"><a href="class-use/DefinitionsFactoryException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/DefinitionsFactoryConfig.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/DefinitionsUtil.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/DefinitionsFactoryException.html"><strong>FRAMES</strong></a>    <a href="DefinitionsFactoryException.html"><strong>NO FRAMES</strong></a>    
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
