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
<td align="left"><a href="class-use/ModuleUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ModuleException.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/PropertyMessageResources.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ModuleUtils.html"><strong>FRAMES</strong></a>    <a href="ModuleUtils.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.util
 Class ModuleUtils
----------------------

    java.lang.Object
      org.apache.struts.util.ModuleUtils

------------------------------------------------------------------------

    public class ModuleUtils

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

General purpose utility methods related to module processing.

**Since:**  
Struts 1.2

**Version:**  
$Rev: 471754 $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

**Constructor Summary**

`protected`

` ModuleUtils()`
           Constructor for ModuleUtils.

  <span id="method_summary"></span>

**Method Summary**

`static ModuleUtils`

` getInstance()`
           Returns the Singleton instance of TagUtils.

` ModuleConfig`

` getModuleConfig(HttpServletRequest request)`
           Return the current ModuleConfig object stored in request, if it exists, null otherwise.

` ModuleConfig`

` getModuleConfig(HttpServletRequest request, ServletContext context)`
           Return the ModuleConfig object is it exists, null otherwise.

` ModuleConfig`

` getModuleConfig(String prefix, HttpServletRequest request, ServletContext context)`
           Return the desired ModuleConfig object stored in context, if it exists, otherwise return the current ModuleConfig

` ModuleConfig`

` getModuleConfig(String prefix, ServletContext context)`
           Return the desired ModuleConfig object stored in context, if it exists, null otherwise.

` String`

` getModuleName(HttpServletRequest request, ServletContext context)`
           Get the module name to which the specified request belong.

` String`

` getModuleName(String matchPath, ServletContext context)`
           Get the module name to which the specified uri belong.

` String[]`

` getModulePrefixes(ServletContext context)`
           Return the list of module prefixes that are defined for this web application.

` void`

` selectModule(HttpServletRequest request, ServletContext context)`
           Select the module to which the specified request belongs, and add corresponding request attributes to this request.

` void`

` selectModule(String prefix, HttpServletRequest request, ServletContext context)`
           Select the module to which the specified request belongs, and add corresponding request attributes to this request.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ModuleUtils

    protected ModuleUtils()

Constructor for ModuleUtils.

<span id="method_detail"></span>

**Method Detail**

### getInstance

    public static ModuleUtils getInstance()

Returns the Singleton instance of TagUtils.

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(HttpServletRequest request)

Return the current ModuleConfig object stored in request, if it exists, null otherwise. This method can be used by plugin to retrieve the current module config object. If no moduleConfig is found, this means that the request haven't hit the server throught the struts servlet. The appropriate module config can be set and found with ` selectModule(HttpServletRequest, ServletContext)` .

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
the ModuleConfig object from request, or null if none is set in the request.

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(String prefix,
                                        ServletContext context)

Return the desired ModuleConfig object stored in context, if it exists, null otherwise.

**Parameters:**  
`prefix` - The module prefix of the desired module

`context` - The ServletContext for this web application

**Returns:**  
the ModuleConfig object specified, or null if not found in the context.

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(String prefix,
                                        HttpServletRequest request,
                                        ServletContext context)

Return the desired ModuleConfig object stored in context, if it exists, otherwise return the current ModuleConfig

**Parameters:**  
`prefix` - The module prefix of the desired module

`request` - The servlet request we are processing

`context` - The ServletContext for this web application

**Returns:**  
the ModuleConfig object specified, or null if not found in the context.

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(HttpServletRequest request,
                                        ServletContext context)

Return the ModuleConfig object is it exists, null otherwise.

**Parameters:**  
`request` - The servlet request we are processing

`context` - The ServletContext for this web application

**Returns:**  
the ModuleConfig object

------------------------------------------------------------------------

### getModuleName

    public String getModuleName(HttpServletRequest request,
                                ServletContext context)

Get the module name to which the specified request belong.

**Parameters:**  
`request` - The servlet request we are processing

`context` - The ServletContext for this web application

**Returns:**  
The module prefix or ""

------------------------------------------------------------------------

### getModuleName

    public String getModuleName(String matchPath,
                                ServletContext context)

Get the module name to which the specified uri belong.

**Parameters:**  
`matchPath` - The uri from which we want the module name.

`context` - The ServletContext for this web application

**Returns:**  
The module prefix or ""

------------------------------------------------------------------------

### getModulePrefixes

    public String[] getModulePrefixes(ServletContext context)

Return the list of module prefixes that are defined for this web application. **NOTE** - the "" prefix for the default module is not included in this list.

**Parameters:**  
`context` - The ServletContext for this web application.

**Returns:**  
An array of module prefixes.

------------------------------------------------------------------------

### selectModule

    public void selectModule(HttpServletRequest request,
                             ServletContext context)

Select the module to which the specified request belongs, and add corresponding request attributes to this request.

**Parameters:**  
`request` - The servlet request we are processing

`context` - The ServletContext for this web application

------------------------------------------------------------------------

### selectModule

    public void selectModule(String prefix,
                             HttpServletRequest request,
                             ServletContext context)

Select the module to which the specified request belongs, and add corresponding request attributes to this request.

**Parameters:**  
`prefix` - The module prefix of the desired module

`request` - The servlet request we are processing

`context` - The ServletContext for this web application

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
<td align="left"><a href="class-use/ModuleUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ModuleException.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/PropertyMessageResources.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ModuleUtils.html"><strong>FRAMES</strong></a>    <a href="ModuleUtils.html"><strong>NO FRAMES</strong></a>    
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
