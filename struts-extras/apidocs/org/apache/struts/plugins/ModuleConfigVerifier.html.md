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
<td align="left"><a href="class-use/ModuleConfigVerifier.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/plugins/DigestingPlugIn.html.md" title="class in org.apache.struts.plugins"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/plugins/ModuleConfigVerifier.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigVerifier.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.plugins
 Class ModuleConfigVerifier
---------------------------

    java.lang.Object
      org.apache.struts.plugins.ModuleConfigVerifier

**All Implemented Interfaces:**  
[PlugIn](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action")

------------------------------------------------------------------------

    public class ModuleConfigVerifier

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [PlugIn](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action")

Convenient implementation of [`PlugIn`](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action") that performs as many verification tests on the information stored in the [`ModuleConfig`](http://struts.apache.org/apidocs/org/apache/struts/config/ModuleConfig.html?is-external=true "class or interface in org.apache.struts.config") for this module as is practical. Based on the setting of the `fatal` property (which defaults to `true`), the detection of any such errors will cause a `ServletException` to be thrown from the `init` method, which will ultimately cause the initialization of your Struts controller servlet to fail.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ModuleConfig`

` config`
           The [`ModuleConfig`](http://struts.apache.org/apidocs/org/apache/struts/config/ModuleConfig.html.md?is-external=true "class or interface in org.apache.struts.config") instance for our module.

`protected  ActionServlet`

` servlet`
           The [`ActionServlet`](http://struts.apache.org/apidocs/org/apache/struts/action/ActionServlet.html.md?is-external=true "class or interface in org.apache.struts.action") instance we are associated with.

  <span id="constructor_summary"></span>

| **Constructor Summary**   |
|---------------------------|
| ` ModuleConfigVerifier()` 
                            |

  <span id="method_summary"></span>

**Method Summary**

` void`

` destroy()`
           Receive notification that our owning module is being shut down.

` void`

` init(ActionServlet servlet, ModuleConfig config)`
            

` boolean`

` isFatal()`
           Return the "configuation errors are fatal" flag.

` void`

` setFatal(boolean fatal)`
           Set the "configuration errors are fatal" flag.

`protected  boolean`

` verifyActionMappingClass()`
           Return `true` if information returned by `config.getActionMappingClass` is all valid; otherwise, log error messages and return `false`.

`protected  boolean`

` verifyForwardConfigs()`
           Return `true` if information returned by `config.findForwardConfigs` is all valid; otherwise, log error messages and return `false`.

`protected  boolean`

` verifyMessageResourcesConfigs()`
           Return `true` if information returned by `config.findMessageResourcesConfigs` is all valid; otherwise, log error messages and return `false`.

`protected  boolean`

` verifyPlugInConfigs()`
           Return `true` if information returned by `config.findPluginConfigs` is all valid; otherwise, log error messages and return `false`.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="config"></span>

### config

    protected ModuleConfig config

The [`ModuleConfig`](http://struts.apache.org/apidocs/org/apache/struts/config/ModuleConfig.html.md?is-external=true "class or interface in org.apache.struts.config") instance for our module.

------------------------------------------------------------------------

<span id="servlet"></span>

### servlet

    protected ActionServlet servlet

The [`ActionServlet`](http://struts.apache.org/apidocs/org/apache/struts/action/ActionServlet.html.md?is-external=true "class or interface in org.apache.struts.action") instance we are associated with.

<span id="constructor_detail"></span>

**Constructor Detail**

### ModuleConfigVerifier

    public ModuleConfigVerifier()

<span id="method_detail"></span>

**Method Detail**

### isFatal

    public boolean isFatal()

Return the "configuation errors are fatal" flag.

------------------------------------------------------------------------

### setFatal

    public void setFatal(boolean fatal)

Set the "configuration errors are fatal" flag.

**Parameters:**  
`fatal` - The new flag value

------------------------------------------------------------------------

### destroy

    public void destroy()

Receive notification that our owning module is being shut down.

**Specified by:**  
`destroy` in interface `PlugIn`

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig config)
              throws ServletException

**Specified by:**  
`init` in interface `PlugIn`

<!-- -->

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### verifyActionMappingClass

    protected boolean verifyActionMappingClass()

Return `true` if information returned by `config.getActionMappingClass` is all valid; otherwise, log error messages and return `false`.

------------------------------------------------------------------------

### verifyForwardConfigs

    protected boolean verifyForwardConfigs()

Return `true` if information returned by `config.findForwardConfigs` is all valid; otherwise, log error messages and return `false`.

------------------------------------------------------------------------

### verifyMessageResourcesConfigs

    protected boolean verifyMessageResourcesConfigs()

Return `true` if information returned by `config.findMessageResourcesConfigs` is all valid; otherwise, log error messages and return `false`.

------------------------------------------------------------------------

### verifyPlugInConfigs

    protected boolean verifyPlugInConfigs()

Return `true` if information returned by `config.findPluginConfigs` is all valid; otherwise, log error messages and return `false`.

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
<td align="left"><a href="class-use/ModuleConfigVerifier.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/plugins/DigestingPlugIn.html.md" title="class in org.apache.struts.plugins"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/plugins/ModuleConfigVerifier.html"><strong>FRAMES</strong></a>    <a href="ModuleConfigVerifier.html"><strong>NO FRAMES</strong></a>    
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
