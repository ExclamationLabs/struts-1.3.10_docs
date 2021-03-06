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
<td align="left"><a href="class-use/MockActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockAction.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockEnumeration.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockActionServlet.html"><strong>FRAMES</strong></a>    <a href="MockActionServlet.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.mock
 Class MockActionServlet
------------------------

    java.lang.Object
      javax.servlet.GenericServlet
          javax.servlet.http.HttpServlet
              org.apache.struts.action.ActionServlet
                  org.apache.struts.mock.MockActionServlet

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [Servlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/Servlet.html?is-external=true "class or interface in javax.servlet"), [ServletConfig](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/ServletConfig.html?is-external=true "class or interface in javax.servlet")

------------------------------------------------------------------------

    public class MockActionServlet

extends [ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")

Mock **ActionServlet** object for low-level unit tests of Struts controller components. Coarser grained tests should be implemented in terms of the Cactus framework, instead of the mock object classes.

**WARNING** - Only getter methods for servletContext and servletConfig are provided, plus additional methods to configure this object as necessary. Methods for unsupported operations will throw `UnsupportedOperationException`.

**WARNING** - Because unit tests operate in a single threaded environment, no synchronization is performed.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-14 02:09:06 -0400 (Sat, 14 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.mock.MockActionServlet)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ServletConfig`

` servletConfig`
            

`protected  ServletContext`

` servletContext`
            

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionServlet"></span>

| **Fields inherited from class org.apache.struts.action.[ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` chainConfig, config,  configDigester,  convertNull, internal,  internalName, log,  registrations,  servletMapping,  servletName`                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                          |
|----------------------------------------------------------------------------------|
| ` MockActionServlet()`                                                           
            Constructor.                                                           |
| ` MockActionServlet(ServletContext servletContext, ServletConfig servletConfig)` 
            Constructor.                                                           |

  <span id="method_summary"></span>

**Method Summary**

` ServletConfig`

` getServletConfig()`
            Get property

` ServletContext`

` getServletContext()`
            Get property

` void`

` initInternal()`
            Expose as public so that test classes can exercise things which retrieve messages.

` void`

` setServletConfig(ServletConfig servletConfig)`
            Set property

` void`

` setServletContext(ServletContext servletContext)`
            Set property

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionServlet"></span>

| **Methods inherited from class org.apache.struts.action.[ActionServlet](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action")**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addServletMapping,  destroy,  destroyConfigDigester,  destroyInternal,  destroyModules,  doGet,  doPost,  getInternal,  getModuleConfig,  getRequestProcessor, init,  initChain,  initConfigDigester,  initModuleActions,  initModuleConfig,  initModuleConfigFactory,  initModuleExceptionConfigs,  initModuleFormBeans,  initModuleForwards,  initModuleMessageResources,  initModulePlugIns,  initModulePrefixes,  initOther,  initServlet,  parseModuleConfigFile,  parseModuleConfigFile,  process,  processActionConfigClass,  processActionConfigExtension,  processExceptionConfigClass,  processExceptionExtension,  processFormBeanConfigClass,  processFormBeanExtension,  processForwardConfigClass,  processForwardExtension,  splitAndResolvePaths` |

 <span id="methods_inherited_from_class_javax.servlet.http.HttpServlet"></span>

| **Methods inherited from class javax.servlet.http.[HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html.md?is-external=true "class or interface in javax.servlet.http")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doDelete, doHead, doOptions, doPut, doTrace, getLastModified, service, service`                                                                                                                         |

 <span id="methods_inherited_from_class_javax.servlet.GenericServlet"></span>

| **Methods inherited from class javax.servlet.[GenericServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/GenericServlet.html.md?is-external=true "class or interface in javax.servlet")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getInitParameter, getInitParameterNames, getServletInfo, getServletName, init, log, log`                                                                                                       |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="servletContext"></span>

### servletContext

    protected ServletContext servletContext

------------------------------------------------------------------------

<span id="servletConfig"></span>

### servletConfig

    protected ServletConfig servletConfig

<span id="constructor_detail"></span>

**Constructor Detail**

### MockActionServlet

    public MockActionServlet(ServletContext servletContext,
                             ServletConfig servletConfig)

Constructor.

------------------------------------------------------------------------

### MockActionServlet

    public MockActionServlet()

Constructor.

<span id="method_detail"></span>

**Method Detail**

### setServletContext

    public void setServletContext(ServletContext servletContext)

Set property

**Parameters:**  
`servletContext` -

------------------------------------------------------------------------

### getServletContext

    public ServletContext getServletContext()

Get property

**Specified by:**  
`getServletContext` in interface `ServletConfig`

**Overrides:**  
`getServletContext` in class `GenericServlet`

**Returns:**

------------------------------------------------------------------------

### setServletConfig

    public void setServletConfig(ServletConfig servletConfig)

Set property

**Parameters:**  
`servletConfig` -

------------------------------------------------------------------------

### getServletConfig

    public ServletConfig getServletConfig()

Get property

**Specified by:**  
`getServletConfig` in interface `Servlet`

**Overrides:**  
`getServletConfig` in class `GenericServlet`

**Returns:**

------------------------------------------------------------------------

### initInternal

    public void initInternal()
                      throws ServletException

Expose as public so that test classes can exercise things which retrieve messages.

**Overrides:**  
` initInternal` in class `ActionServlet`

<!-- -->

**Throws:**  
`ServletException` - if we cannot initialize these resources

`UnavailableException` - if we cannot load resources

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
<td align="left"><a href="class-use/MockActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockAction.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockEnumeration.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockActionServlet.html"><strong>FRAMES</strong></a>    <a href="MockActionServlet.html"><strong>NO FRAMES</strong></a>    
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
