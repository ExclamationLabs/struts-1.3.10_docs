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
<td align="left"><a href="class-use/WriteRenderer.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/renderer/StylesheetRenderer.html.md" title="class in org.apache.struts.faces.renderer"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/renderer/WriteRenderer.html"><strong>FRAMES</strong></a>    <a href="WriteRenderer.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.renderer
 Class WriteRenderer
--------------------------------

    java.lang.Object
      javax.faces.render.Renderer
          org.apache.struts.faces.renderer.AbstractRenderer
              org.apache.struts.faces.renderer.WriteRenderer

**Direct Known Subclasses:**  
[MessageRenderer](../../../../../org/apache/struts/faces/renderer/MessageRenderer.html.md "class in org.apache.struts.faces.renderer")

------------------------------------------------------------------------

    public class WriteRenderer

extends [AbstractRenderer](../../../../../org/apache/struts/faces/renderer/AbstractRenderer.html.md "class in org.apache.struts.faces.renderer")

`Renderer` implementation for the `write` tag from the *Struts-Faces Integration Library*.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` WriteRenderer()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` encodeEnd(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Encode the specified text to our response.

`protected  String`

` getText(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Return the text to be rendered for this component, optionally filtered if requested.

 <span id="methods_inherited_from_class_org.apache.struts.faces.renderer.AbstractRenderer"></span>

| **Methods inherited from class org.apache.struts.faces.renderer.[AbstractRenderer](../../../../../org/apache/struts/faces/renderer/AbstractRenderer.html.md "class in org.apache.struts.faces.renderer")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` decode,  encodeBegin,  encodeChildren,  encodeRecursive,  getAsString,  isDisabled,  isReadOnly,  renderAttributes,  renderBoolean,  renderEnd,  renderPassThrough,  renderStart,  setSubmittedValue` |

 <span id="methods_inherited_from_class_javax.faces.render.Renderer"></span>

| **Methods inherited from class javax.faces.render.Renderer** |
|--------------------------------------------------------------|
| `convertClientId, getConvertedValue, getRendersChildren`     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### WriteRenderer

    public WriteRenderer()

<span id="method_detail"></span>

**Method Detail**

### encodeEnd

    public void encodeEnd(javax.faces.context.FacesContext context,
                          javax.faces.component.UIComponent component)
                   throws IOException

Encode the specified text to our response.

**Overrides:**  
` encodeEnd` in class `AbstractRenderer`

<!-- -->

**Parameters:**  
`context` - FacesContext for the response we are creating

`component` - Component to be rendered

**Throws:**  
`IOException` - if an input/output error occurs

`NullPointerException` - if `context` or `component` is `null`

------------------------------------------------------------------------

### getText

    protected String getText(javax.faces.context.FacesContext context,
                             javax.faces.component.UIComponent component)

Return the text to be rendered for this component, optionally filtered if requested.

**Parameters:**  
`context` - FacesContext for the response we are creating

`component` - Component to be rendered

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
<td align="left"><a href="class-use/WriteRenderer.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/renderer/StylesheetRenderer.html.md" title="class in org.apache.struts.faces.renderer"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/renderer/WriteRenderer.html"><strong>FRAMES</strong></a>    <a href="WriteRenderer.html"><strong>NO FRAMES</strong></a>    
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
