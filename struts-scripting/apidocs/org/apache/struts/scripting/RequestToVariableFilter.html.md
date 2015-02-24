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
<td align="left"><a href="class-use/RequestToVariableFilter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/BSFManagerFilter.html.md" title="interface in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/ScriptAction.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/RequestToVariableFilter.html"><strong>FRAMES</strong></a>    <a href="RequestToVariableFilter.html"><strong>NO FRAMES</strong></a>    
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
 Class RequestToVariableFilter
------------------------------

    java.lang.Object
      org.apache.struts.scripting.RequestToVariableFilter

**All Implemented Interfaces:**  
[BSFManagerFilter](../../../../org/apache/struts/scripting/BSFManagerFilter.html.md "interface in org.apache.struts.scripting")

------------------------------------------------------------------------

    public class RequestToVariableFilter

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [BSFManagerFilter](../../../../org/apache/struts/scripting/BSFManagerFilter.html.md "interface in org.apache.struts.scripting")

Takes request parameters and declares variables with them. If a variable is already exists with that name, a "\_" is prepended to the name. Both Strings and arrays are recognized.

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` RequestToVariableFilter()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

` org.apache.bsf.BSFManager`

` apply(org.apache.bsf.BSFManager mgr)`
           Applies the filter.

` void`

` init(String name, Properties props)`
           Initializes the filter.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### RequestToVariableFilter

    public RequestToVariableFilter()

<span id="method_detail"></span>

**Method Detail**

### init

    public void init(String name,
                     Properties props)

Initializes the filter.

**Specified by:**  
` init` in interface `BSFManagerFilter`

<!-- -->

**Parameters:**  
`name` - The name of the filter

`props` - The properties

------------------------------------------------------------------------

### apply

    public org.apache.bsf.BSFManager apply(org.apache.bsf.BSFManager mgr)

Applies the filter.

**Specified by:**  
` apply` in interface `BSFManagerFilter`

<!-- -->

**Parameters:**  
`mgr` - The bsf manager

**Returns:**  
The bsf manager

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
<td align="left"><a href="class-use/RequestToVariableFilter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/BSFManagerFilter.html.md" title="interface in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/ScriptAction.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/RequestToVariableFilter.html"><strong>FRAMES</strong></a>    <a href="RequestToVariableFilter.html"><strong>NO FRAMES</strong></a>    
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
