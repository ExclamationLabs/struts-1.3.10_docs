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
<td align="left"><a href="class-use/TilesPreProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/commands/TilesPreProcessor.html"><strong>FRAMES</strong></a>    <a href="TilesPreProcessor.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.commands
 Class TilesPreProcessor
--------------------------------

    java.lang.Object
      org.apache.struts.tiles.commands.TilesPreProcessor

**All Implemented Interfaces:**  
org.apache.commons.chain.Command

------------------------------------------------------------------------

    public class TilesPreProcessor

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements org.apache.commons.chain.Command

Command class intended to perform responsibilities of the TilesRequestProcessor in Struts 1.1. Does not actually dispatch requests, but simply prepares the chain context for a later forward as appropriate. Should be added to a chain before something which would handle a conventional ForwardConfig.

This class will never have any effect on the chain unless a `TilesDefinitionFactory` can be found; however it does not consider the absence of a definition factory to be a fatal error; the command simply returns false and lets the chain continue.

To initialize the `TilesDefinitionFactory`, use `org.apache.struts.chain.commands.legacy.TilesPlugin`. This class is a simple extension to `org.apache.struts.tiles.TilesPlugin` which simply does not interfere with your choice of `RequestProcessor` implementation.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.commons.chain.Command"></span>

| **Fields inherited from interface org.apache.commons.chain.Command** |
|----------------------------------------------------------------------|
| `CONTINUE_PROCESSING, PROCESSING_COMPLETE`                           |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TilesPreProcessor()`  
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` doForward(ServletActionContext context, String uri)`
           Do an include of specified URI using a `RequestDispatcher`.

`protected  void`

` doInclude(ServletActionContext context, String uri)`
           Do an include of specified URI using a `RequestDispatcher`.

` boolean`

` execute(org.apache.commons.chain.Context context)`
           If the current `ForwardConfig` is using "tiles", perform necessary pre-processing to set up the `TilesContext` and substitute a new `ForwardConfig` which is understandable to a `RequestDispatcher`.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesPreProcessor

    public TilesPreProcessor()

<span id="method_detail"></span>

**Method Detail**

### execute

    public boolean execute(org.apache.commons.chain.Context context)
                    throws Exception

If the current `ForwardConfig` is using "tiles", perform necessary pre-processing to set up the `TilesContext` and substitute a new `ForwardConfig` which is understandable to a `RequestDispatcher`.

Note that if the command finds a previously existing `ComponentContext` in the request, then it infers that it has been called from within another tile, so instead of changing the `ForwardConfig` in the chain `Context`, the command uses `RequestDispatcher` to *include* the tile, and returns true, indicating that the processing chain is complete.

**Specified by:**  
`execute` in interface `org.apache.commons.chain.Command`

<!-- -->

**Parameters:**  
`context` - The `Context` for the current request

**Returns:**  
`false` in most cases, but true if we determine that we're processing in "include" mode.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### doInclude

    protected void doInclude(ServletActionContext context,
                             String uri)
                      throws IOException,
                             ServletException

Do an include of specified URI using a `RequestDispatcher`.

**Parameters:**  
`context` - a chain servlet/web context

`uri` - Context-relative URI to include

**Throws:**  
`IOException`

`ServletException`

------------------------------------------------------------------------

### doForward

    protected void doForward(ServletActionContext context,
                             String uri)
                      throws IOException,
                             ServletException

Do an include of specified URI using a `RequestDispatcher`.

**Parameters:**  
`context` - a chain servlet/web context

`uri` - Context-relative URI to include

**Throws:**  
`IOException`

`ServletException`

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
<td align="left"><a href="class-use/TilesPreProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/commands/TilesPreProcessor.html"><strong>FRAMES</strong></a>    <a href="TilesPreProcessor.html"><strong>NO FRAMES</strong></a>    
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
