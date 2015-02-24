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
<td align="left"><a href="class-use/InvalidCancelException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ForwardingActionForward.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/PlugIn.html" title="interface in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/InvalidCancelException.html"><strong>FRAMES</strong></a>    <a href="InvalidCancelException.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Throwable">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class InvalidCancelException
-----------------------------

    java.lang.Object
      java.lang.Throwable
          java.lang.Exception
              org.apache.struts.action.InvalidCancelException

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class InvalidCancelException

extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html.md?is-external=true "class or interface in java.lang")

Thrown when a token generated by the Cancel tag is found in the request, but the cancellable property for the Action Mapping is not set.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.InvalidCancelException)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                        |
|----------------------------------------------------------------|
| ` InvalidCancelException()`                                    
            Default constructor.                                 |
| ` InvalidCancelException(String message)`                      
            Construct the exception with the specified message.  |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_java.lang.Throwable"></span>

| **Methods inherited from class java.lang.[Throwable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Throwable.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `fillInStackTrace, getCause, getLocalizedMessage, getMessage, getStackTrace, initCause, printStackTrace, printStackTrace, printStackTrace, setStackTrace, toString`         |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### InvalidCancelException

    public InvalidCancelException()

Default constructor.

------------------------------------------------------------------------

### InvalidCancelException

    public InvalidCancelException(String message)

Construct the exception with the specified message.

**Parameters:**  
`message` - the message

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
<td align="left"><a href="class-use/InvalidCancelException.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ForwardingActionForward.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/PlugIn.html" title="interface in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/InvalidCancelException.html"><strong>FRAMES</strong></a>    <a href="InvalidCancelException.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Throwable">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.