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
<td align="left"><a href="class-use/BSFManagerFilter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/scripting/RequestToVariableFilter.html.md" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/BSFManagerFilter.html"><strong>FRAMES</strong></a>    <a href="BSFManagerFilter.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.scripting
 Interface BSFManagerFilter
---------------------------

**All Known Implementing Classes:**  
[RequestToVariableFilter](../../../../org/apache/struts/scripting/RequestToVariableFilter.html.md "class in org.apache.struts.scripting"), [TestFilter](../../../../org/apache/struts/scripting/TestFilter.html "class in org.apache.struts.scripting")

------------------------------------------------------------------------

    public interface BSFManagerFilter

Defines a class that wants to manipulate the contents of the scripting context before the script is executed. An example would be a class that puts business facade classes in the context.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

` org.apache.bsf.BSFManager`

` apply(org.apache.bsf.BSFManager mgr)`
           Applies the filter.

` void`

` init(String name, Properties props)`
           Initializes the filter.

 

<span id="method_detail"></span>

**Method Detail**

### init

    void init(String name,
              Properties props)

Initializes the filter. Properties can be retrieved as: `struts-scripting.filters.FILTER_NAME.PROPERTY_NAME=PROPERTY_VALUE` where FILTER\_NAME is the "name" parameter.

**Parameters:**  
`name` - The name of the filter

`props` - The properties

------------------------------------------------------------------------

### apply

    org.apache.bsf.BSFManager apply(org.apache.bsf.BSFManager mgr)

Applies the filter.

**Parameters:**  
`mgr` - The scripting manager

**Returns:**  
The scripting manager

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
<td align="left"><a href="class-use/BSFManagerFilter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/scripting/RequestToVariableFilter.html.md" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/BSFManagerFilter.html"><strong>FRAMES</strong></a>    <a href="BSFManagerFilter.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
