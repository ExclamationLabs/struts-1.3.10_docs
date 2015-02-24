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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/RequestProcessor.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="RequestProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.RequestProcessor**
--------------------------------------------

Packages that use [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

[**org.apache.struts.faces.application**](#org.apache.struts.faces.application)

  

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

 

<span id="org.apache.struts.action"></span>

Uses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html "class in org.apache.struts.action")

`protected  RequestProcessor`

`ActionServlet.getRequestProcessor(ModuleConfig config)`
           Look up and return the [`RequestProcessor`](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") responsible for the specified module, creating a new one if necessary.

 

<span id="org.apache.struts.chain"></span>

Uses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html)

 

Subclasses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.chain](../../../../../org/apache/struts/chain/package-summary.html)

` class`

`ComposableRequestProcessor`
            ComposableRequestProcessor uses the Chain Of Resposibility design pattern (as implemented by the commons-chain package in Jakarta Commons) to support external configuration of command chains to be used.

 

<span id="org.apache.struts.faces.application"></span>

Uses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html)

 

Subclasses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html)

` class`

`FacesRequestProcessor`
           Concrete implementation of `RequestProcessor` that implements the standard Struts request processing lifecycle on a request that was received as an `ActionEvent` by our associated `ActionListener`.

` class`

`FacesTilesRequestProcessor`
           Concrete implementation of `RequestProcessor` that implements the standard Struts request processing lifecycle on a request that was received as an `ActionEvent` by our associated `ActionListener`.

 

Methods in [org.apache.struts.faces.application](../../../../../org/apache/struts/faces/application/package-summary.html.md) that return [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html "class in org.apache.struts.action")

`protected  RequestProcessor`

`ActionListenerImpl.getRequestProcessor(ModuleConfig config, ServletContext context)`
           Look up and return the `RequestProcessor` responsible for the specified module, creating a new one if necessary.

 

<span id="org.apache.struts.tiles"></span>

Uses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

 

Subclasses of [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action") in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html)

` class`

`TilesRequestProcessor`
           **RequestProcessor** contains the processing logic that the Struts controller servlet performs as it receives each servlet request from the container.

 

Methods in [org.apache.struts.tiles](../../../../../org/apache/struts/tiles/package-summary.html.md) that return [RequestProcessor](../../../../../org/apache/struts/action/RequestProcessor.html "class in org.apache.struts.action")

`protected  RequestProcessor`

`RedeployableActionServlet.getRequestProcessor(ModuleConfig config)`
            

 

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
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/RequestProcessor.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useRequestProcessor.html"><strong>FRAMES</strong></a>    <a href="RequestProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
