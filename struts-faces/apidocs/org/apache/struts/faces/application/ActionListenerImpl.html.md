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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionListenerImpl.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/application/FacesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/ActionListenerImpl.html"><strong>FRAMES</strong></a>    <a href="ActionListenerImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.application
 Class ActionListenerImpl
-----------------------------------

    java.lang.Object
      org.apache.struts.faces.application.ActionListenerImpl

**All Implemented Interfaces:**  
[EventListener](http://java.sun.com/j2se/1.4.2/docs/api/java/util/EventListener.html.md?is-external=true "class or interface in java.util"), javax.faces.event.ActionListener, javax.faces.event.FacesListener

------------------------------------------------------------------------

    public final class ActionListenerImpl

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements javax.faces.event.ActionListener

Concrete implementation of `ActionListener` that replaces the default provided implementation. It converts application-level events into execution of the corresponding Struts request processing lifecycle.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                                 |
|---------------------------------------------------------------------------------------------------------|
| ` ActionListenerImpl(javax.faces.event.ActionListener original)`                                        
            Construct a new default `ActionListener` instance, passing it the previously configured one.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  RequestProcessor`

` getRequestProcessor(ModuleConfig config, ServletContext context)`
           Look up and return the `RequestProcessor` responsible for the specified module, creating a new one if necessary.

` void`

` processAction(javax.faces.event.ActionEvent event)`
           Process the specified `ActionEvent`.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionListenerImpl

    public ActionListenerImpl(javax.faces.event.ActionListener original)

Construct a new default `ActionListener` instance, passing it the previously configured one.

**Parameters:**  
`original` - Original default `ActionListener`

**Throws:**  
`NullPointerException` - if `original` is `null`

<span id="method_detail"></span>

**Method Detail**

### processAction

    public void processAction(javax.faces.event.ActionEvent event)
                       throws javax.faces.event.AbortProcessingException

Process the specified `ActionEvent`.

**Specified by:**  
`processAction` in interface `javax.faces.event.ActionListener`

<!-- -->

**Parameters:**  
`event` - The `ActionEvent` to be processed

**Throws:**  
`javax.faces.event.AbortProcessingException` - to signal that no further event processing should be performed

------------------------------------------------------------------------

### getRequestProcessor

    protected RequestProcessor getRequestProcessor(ModuleConfig config,
                                                   ServletContext context)

Look up and return the `RequestProcessor` responsible for the specified module, creating a new one if necessary. This method is based on the corresponding code in `ActionServlet`, which cannot be used directly because it is a protected method.

**Parameters:**  
`config` - The module configuration for which to acquire and return a RequestProcessor

`context` - The `ServletContext` instance for this web application

**Throws:**  
`IllegalStateException` - if we cannot instantiate a RequestProcessor instance

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ActionListenerImpl.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/application/FacesRequestProcessor.html.md" title="class in org.apache.struts.faces.application"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/ActionListenerImpl.html"><strong>FRAMES</strong></a>    <a href="ActionListenerImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
