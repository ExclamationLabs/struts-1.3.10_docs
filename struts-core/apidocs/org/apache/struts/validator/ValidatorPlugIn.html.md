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
<td align="left"><a href="class-use/ValidatorPlugIn.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/ValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorPlugIn.html"><strong>FRAMES</strong></a>    <a href="ValidatorPlugIn.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.validator
 Class ValidatorPlugIn
---------------------------

    java.lang.Object
      org.apache.struts.validator.ValidatorPlugIn

**All Implemented Interfaces:**  
[PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

------------------------------------------------------------------------

    public class ValidatorPlugIn

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

Loads `ValidatorResources` based on configuration in the struts-config.xml file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 483039 $ $Date: 2005-08-30 00:22:27 -0400 (Tue, 30 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ValidatorResources`

` resources`
           The set of Form instances that have been created and initialized, keyed by the struts form name.

`static String`

` STOP_ON_ERROR_KEY`
           Application scope key that `StopOnError` is stored under.

`static String`

` VALIDATOR_KEY`
           Application scope key that `ValidatorResources` is stored under.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ValidatorPlugIn()`    
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` destroy()`
           Gracefully shut down, releasing any resources that were allocated at initialization.

`protected  void`

` destroyResources()`
           Destroy `ValidatorResources`.

` String`

` getPathnames()`
           Gets a comma delimitted list of Validator resources.

` void`

` init(ActionServlet servlet, ModuleConfig config)`
           Initialize and load our resources.

`protected  void`

` initResources()`
           Initialize the validator resources for this module.

` boolean`

` isStopOnFirstError()`
           Gets the value for stopOnFirstError.

` void`

` setPathnames(String pathnames)`
           Sets a comma delimitted list of Validator resources.

` void`

` setStopOnFirstError(boolean stopOnFirstError)`
           Sets the value for stopOnFirstError.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="VALIDATOR_KEY"></span>

### VALIDATOR\_KEY

    public static final String VALIDATOR_KEY

Application scope key that `ValidatorResources` is stored under.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.validator.ValidatorPlugIn.VALIDATOR_KEY)

------------------------------------------------------------------------

<span id="STOP_ON_ERROR_KEY"></span>

### STOP\_ON\_ERROR\_KEY

    public static final String STOP_ON_ERROR_KEY

Application scope key that `StopOnError` is stored under.

**Since:**  
Struts 1.2

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.validator.ValidatorPlugIn.STOP_ON_ERROR_KEY)

------------------------------------------------------------------------

<span id="resources"></span>

### resources

    protected ValidatorResources resources

The set of Form instances that have been created and initialized, keyed by the struts form name.

<span id="constructor_detail"></span>

**Constructor Detail**

### ValidatorPlugIn

    public ValidatorPlugIn()

<span id="method_detail"></span>

**Method Detail**

### getPathnames

    public String getPathnames()

Gets a comma delimitted list of Validator resources.

**Returns:**  
comma delimited list of Validator resource path names

------------------------------------------------------------------------

### setPathnames

    public void setPathnames(String pathnames)

Sets a comma delimitted list of Validator resources.

**Parameters:**  
`pathnames` - delimited list of Validator resource path names

------------------------------------------------------------------------

### isStopOnFirstError

    public boolean isStopOnFirstError()

Gets the value for stopOnFirstError.

**Returns:**  
A boolean indicating whether JavaScript validation should stop when it finds the first error (Struts 1.1 behaviour) or continue validation.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### setStopOnFirstError

    public void setStopOnFirstError(boolean stopOnFirstError)

Sets the value for stopOnFirstError.

**Parameters:**  
`stopOnFirstError` - A boolean indicating whether JavaScript validation should stop when it finds the first error (Struts 1.1 behaviour) or continue validation.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig config)
              throws ServletException

Initialize and load our resources.

**Specified by:**  
` init` in interface `PlugIn`

<!-- -->

**Parameters:**  
`servlet` - The ActionServlet for our application

`config` - The ModuleConfig for our owning module

**Throws:**  
`ServletException` - if we cannot configure ourselves correctly

------------------------------------------------------------------------

### destroy

    public void destroy()

Gracefully shut down, releasing any resources that were allocated at initialization.

**Specified by:**  
`destroy` in interface `PlugIn`

------------------------------------------------------------------------

### initResources

    protected void initResources()
                          throws IOException,
                                 ServletException

Initialize the validator resources for this module.

**Throws:**  
`IOException` - if an input/output error is encountered

`ServletException` - if we cannot initialize these resources

------------------------------------------------------------------------

### destroyResources

    protected void destroyResources()

Destroy `ValidatorResources`.

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
<td align="left"><a href="class-use/ValidatorPlugIn.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/ValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/ValidatorPlugIn.html"><strong>FRAMES</strong></a>    <a href="ValidatorPlugIn.html"><strong>NO FRAMES</strong></a>    
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
