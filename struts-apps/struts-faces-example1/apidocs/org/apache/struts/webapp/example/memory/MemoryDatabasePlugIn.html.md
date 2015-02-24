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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MemoryDatabasePlugIn.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/webapp/example/memory/MemorySubscription.html.md" title="class in org.apache.struts.webapp.example.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example/memory/MemoryDatabasePlugIn.html"><strong>FRAMES</strong></a>    <a href="MemoryDatabasePlugIn.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.example.memory
 Class MemoryDatabasePlugIn
---------------------------------------

    java.lang.Object
      org.apache.struts.webapp.example.memory.MemoryDatabasePlugIn

**All Implemented Interfaces:**  
[PlugIn](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action")

------------------------------------------------------------------------

    public final class MemoryDatabasePlugIn

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [PlugIn](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action")

**MemoryDatabasePlugIn** initializes and finalizes the persistent storage of User and Subscription information for the Struts Demonstration Application, using an in-memory database backed by an XML file.

**IMPLEMENTATION WARNING** - If this web application is run from a WAR file, or in another environment where reading and writing of the web application resource is impossible, the initial contents will be copied to a file in the web application temporary directory provided by the container. This is for demonstration purposes only - you should **NOT** assume that files written here will survive a restart of your servlet container.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**   |
|---------------------------|
| ` MemoryDatabasePlugIn()` 
                            |

  <span id="method_summary"></span>

**Method Summary**

` void`

` destroy()`
           Gracefully shut down this database, releasing any resources that were allocated at initialization.

` String`

` getPathname()`
            

` void`

` init(ActionServlet servlet, ModuleConfig config)`
           Initialize and load our initial database from persistent storage.

` void`

` setPathname(String pathname)`
            

`protected  void`

` setupCache(ActionServlet servlet, ModuleConfig config)`
           Cache commonly required data as servlet context attributes.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### MemoryDatabasePlugIn

    public MemoryDatabasePlugIn()

<span id="method_detail"></span>

**Method Detail**

### getPathname

    public String getPathname()

------------------------------------------------------------------------

### setPathname

    public void setPathname(String pathname)

------------------------------------------------------------------------

### destroy

    public void destroy()

Gracefully shut down this database, releasing any resources that were allocated at initialization.

**Specified by:**  
`destroy` in interface `PlugIn`

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig config)
              throws ServletException

Initialize and load our initial database from persistent storage.

**Specified by:**  
`init` in interface `PlugIn`

<!-- -->

**Parameters:**  
`servlet` - The ActionServlet for this web application

`config` - The ApplicationConfig for our owning module

**Throws:**  
`ServletException` - if we cannot configure ourselves correctly

------------------------------------------------------------------------

### setupCache

    protected void setupCache(ActionServlet servlet,
                              ModuleConfig config)

Cache commonly required data as servlet context attributes.

**Parameters:**  
`servlet` - The `ActionServlet` instance running this webapp

`config` - The `ModuleConfig` for this application module

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/MemoryDatabasePlugIn.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../../org/apache/struts/webapp/example/memory/MemorySubscription.html.md" title="class in org.apache.struts.webapp.example.memory"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/example/memory/MemoryDatabasePlugIn.html"><strong>FRAMES</strong></a>    <a href="MemoryDatabasePlugIn.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
