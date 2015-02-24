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
<td align="left"><a href="class-use/RedeployableActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/PathAttribute.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesException.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/RedeployableActionServlet.html"><strong>FRAMES</strong></a>    <a href="RedeployableActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionServlet">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles
 Class RedeployableActionServlet
--------------------------------

    java.lang.Object
      javax.servlet.GenericServlet
          javax.servlet.http.HttpServlet
              org.apache.struts.action.ActionServlet
                  org.apache.struts.tiles.RedeployableActionServlet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [Servlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/Servlet.html?is-external=true "class or interface in javax.servlet"), [ServletConfig](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletConfig.html?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class RedeployableActionServlet

extends [ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")

WebLogic (at least v6 and v7) attempts to serialize the TilesRequestProcessor when re-deploying the Webapp in development mode. The TilesRequestProcessor is not serializable, and loses the Tiles definitions. This results in NullPointerException and/or NotSerializableException when using the app after automatic redeploy.

This bug report proposes a workaround for this problem, in the hope it will help others and maybe motivate an actual fix.

The attached class extends the Struts Action servlet and fixes the problem by reloading the Tiles definitions when they have disappeared.

For background discussion see http://issues.apache.org/bugzilla/show\_bug.cgi?id=26322

**Since:**  
1.2.1

**Version:**  
$Rev: 481833 $ $Date: 2006-12-03 11:32:52 -0600 (Sun, 03 Dec 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.RedeployableActionServlet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionServlet"></span>

| **Fields inherited from class org.apache.struts.action.[ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` chainConfig, config,  configDigester,  convertNull, internal,  internalName, log,  registrations,  servletMapping,  servletName`                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**        |
|--------------------------------|
| ` RedeployableActionServlet()` 
                                 |

  <span id="method_summary"></span>

**Method Summary**

`protected  RequestProcessor`

` getRequestProcessor(ModuleConfig config)`
           Look up and return the [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionServlet"></span>

| **Methods inherited from class org.apache.struts.action.[ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addServletMapping,  destroy,  destroyConfigDigester,  destroyInternal,  destroyModules,  doGet,  doPost,  getInternal,  getModuleConfig, init,  initChain,  initConfigDigester,  initInternal,  initModuleActions,  initModuleConfig,  initModuleConfigFactory,  initModuleExceptionConfigs,  initModuleFormBeans,  initModuleForwards,  initModuleMessageResources,  initModulePlugIns,  initModulePrefixes,  initOther,  initServlet,  parseModuleConfigFile,  parseModuleConfigFile,  process,  processActionConfigClass,  processActionConfigExtension,  processExceptionConfigClass,  processExceptionExtension,  processFormBeanConfigClass,  processFormBeanExtension,  processForwardConfigClass,  processForwardExtension,  splitAndResolvePaths` |

 <span id="methods_inherited_from_class_javax.servlet.http.HttpServlet"></span>

| **Methods inherited from class javax.servlet.http.[HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html.md?is-external=true "class or interface in javax.servlet.http")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doDelete, doHead, doOptions, doPut, doTrace, getLastModified, service, service`                                                                                                                         |

 <span id="methods_inherited_from_class_javax.servlet.GenericServlet"></span>

| **Methods inherited from class javax.servlet.[GenericServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/GenericServlet.html.md?is-external=true "class or interface in javax.servlet")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getInitParameter, getInitParameterNames, getServletConfig, getServletContext, getServletInfo, getServletName, init, log, log`                                                                  |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### RedeployableActionServlet

    public RedeployableActionServlet()

<span id="method_detail"></span>

**Method Detail**

### getRequestProcessor

    protected RequestProcessor getRequestProcessor(ModuleConfig config)
                                            throws ServletException

**Description copied from class: ` ActionServlet`**

Look up and return the [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

**Overrides:**  
` getRequestProcessor` in class `ActionServlet`

<!-- -->

**Parameters:**  
`config` - The module configuration for which to acquire and return a RequestProcessor.

**Returns:**  
The [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module,

**Throws:**  
`ServletException` - If we cannot instantiate a RequestProcessor instance a [`UnavailableException`](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/UnavailableException.html.md?is-external=true "class or interface in javax.servlet") is thrown, meaning your application is not loaded and will not be available.

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
<td align="left"><a href="class-use/RedeployableActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/PathAttribute.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesException.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/RedeployableActionServlet.html"><strong>FRAMES</strong></a>    <a href="RedeployableActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionServlet">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
