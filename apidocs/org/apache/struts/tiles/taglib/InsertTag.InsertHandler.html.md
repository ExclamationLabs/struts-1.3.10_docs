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
<td align="left"><a href="class-use/InsertTag.InsertHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.DirectStringHandler.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html"><strong>FRAMES</strong></a>    <a href="InsertTag.InsertHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib
 Class InsertTag.InsertHandler
------------------------------

    java.lang.Object
      org.apache.struts.tiles.taglib.InsertTag.InsertHandler

**All Implemented Interfaces:**  
[InsertTag.TagHandler](../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html.md "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Enclosing class:**  
[InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    protected class InsertTag.InsertHandler

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [InsertTag.TagHandler](../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html.md "interface in org.apache.struts.tiles.taglib")

Real handler, after attribute resolution. Handle include sub-component.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Controller`

` controller`
            

`protected  ComponentContext`

` currentContext`
            

`protected  String`

` page`
            

`protected  String`

` role`
            

`protected  ComponentContext`

` subCompContext`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                     |
|---------------------------------------------------------------------------------------------|
| ` InsertTag.InsertHandler(Map attributes, String page, String role, Controller controller)` 
            Constructor.                                                                      |
| ` InsertTag.InsertHandler(String page, String role, Controller controller)`                 
            Constructor.                                                                      |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Include requested page.

` int`

` doStartTag()`
           Create a new empty context.

`protected  void`

` processException(Throwable ex, String msg)`
           **Deprecated.** *This method will be removed in a release after Struts 1.2.*

` void`

` putAttribute(String name, Object value)`
           Add attribute to sub context.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="page"></span>

### page

    protected String page

------------------------------------------------------------------------

<span id="currentContext"></span>

### currentContext

    protected ComponentContext currentContext

------------------------------------------------------------------------

<span id="subCompContext"></span>

### subCompContext

    protected ComponentContext subCompContext

------------------------------------------------------------------------

<span id="role"></span>

### role

    protected String role

------------------------------------------------------------------------

<span id="controller"></span>

### controller

    protected Controller controller

<span id="constructor_detail"></span>

**Constructor Detail**

### InsertTag.InsertHandler

    public InsertTag.InsertHandler(Map attributes,
                                   String page,
                                   String role,
                                   Controller controller)

Constructor. Create insert handler using Component definition.

------------------------------------------------------------------------

### InsertTag.InsertHandler

    public InsertTag.InsertHandler(String page,
                                   String role,
                                   Controller controller)

Constructor. Create insert handler to insert page at specified location.

<span id="method_detail"></span>

**Method Detail**

### doStartTag

    public int doStartTag()
                   throws JspException

Create a new empty context.

**Specified by:**  
` doStartTag` in interface `InsertTag.TagHandler`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(String name,
                             Object value)

Add attribute to sub context. Do nothing.

**Specified by:**  
` putAttribute` in interface `InsertTag.TagHandler`

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Include requested page.

**Specified by:**  
` doEndTag` in interface `InsertTag.TagHandler`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### processException

    protected void processException(Throwable ex,
                                    String msg)
                             throws JspException

**Deprecated.** *This method will be removed in a release after Struts 1.2.*

Process an exception. Depending of debug attribute, print full exception trace or only its message in output page.

**Parameters:**  
`ex` - Exception

`msg` - An additional message to show in console and to propagate if we can't output exception.

**Throws:**  
`JspException`

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
<td align="left"><a href="class-use/InsertTag.InsertHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.DirectStringHandler.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html"><strong>FRAMES</strong></a>    <a href="InsertTag.InsertHandler.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
