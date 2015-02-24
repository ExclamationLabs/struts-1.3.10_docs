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
<td align="left"><a href="class-use/AbstractRenderer.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/renderer/BaseRenderer.html.md" title="class in org.apache.struts.faces.renderer"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/renderer/AbstractRenderer.html"><strong>FRAMES</strong></a>    <a href="AbstractRenderer.html"><strong>NO FRAMES</strong></a>    
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
 Class AbstractRenderer
--------------------------------

    java.lang.Object
      javax.faces.render.Renderer
          org.apache.struts.faces.renderer.AbstractRenderer

**Direct Known Subclasses:**  
[BaseRenderer](../../../../../org/apache/struts/faces/renderer/BaseRenderer.html.md "class in org.apache.struts.faces.renderer"), [CommandLinkRenderer](../../../../../org/apache/struts/faces/renderer/CommandLinkRenderer.html "class in org.apache.struts.faces.renderer"), [ErrorsRenderer](../../../../../org/apache/struts/faces/renderer/ErrorsRenderer.html "class in org.apache.struts.faces.renderer"), [FormRenderer](../../../../../org/apache/struts/faces/renderer/FormRenderer.html "class in org.apache.struts.faces.renderer"), [HtmlRenderer](../../../../../org/apache/struts/faces/renderer/HtmlRenderer.html "class in org.apache.struts.faces.renderer"), [StylesheetRenderer](../../../../../org/apache/struts/faces/renderer/StylesheetRenderer.html "class in org.apache.struts.faces.renderer"), [WriteRenderer](../../../../../org/apache/struts/faces/renderer/WriteRenderer.html "class in org.apache.struts.faces.renderer")

------------------------------------------------------------------------

    public abstract class AbstractRenderer

extends javax.faces.render.Renderer

Abstract base class for concrete implementations of `javax.faces.render.Renderer` for the *Struts-Faces Integration Library*.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` AbstractRenderer()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` decode(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Decode any new state of the specified `UIComponent` from the request contained in the specified `FacesContext`, and store that state on the `UIComponent`.

` void`

` encodeBegin(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Render the beginning of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

` void`

` encodeChildren(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Render the children of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

` void`

` encodeEnd(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Render the ending of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

`protected  void`

` encodeRecursive(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           Render nested child components by invoking the encode methods on those components, but only when the `rendered` property is `true`.

`protected  String`

` getAsString(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, Object value)`
           Convert the Object representation of this component's value to the corresponding String representation.

`protected  boolean`

` isDisabled(javax.faces.component.UIComponent component)`
           Return `true` if the specified component is disabled.

`protected  boolean`

` isReadOnly(javax.faces.component.UIComponent component)`
           Return `true` if the specified component is read only.

`protected  void`

` renderAttributes(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, javax.faces.context.ResponseWriter writer)`
           Render the element attributes for the generated markup related to this component.

`protected  void`

` renderBoolean(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, javax.faces.context.ResponseWriter writer, String[] names)`
           Render any boolean attributes on the specified list that have `true` values on the corresponding attribute of the specified `UIComponent`.

`protected  void`

` renderEnd(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, javax.faces.context.ResponseWriter writer)`
           Render the element end for the generated markup related to this component.

`protected  void`

` renderPassThrough(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, javax.faces.context.ResponseWriter writer, String[] names)`
           Render any attributes on the specified list directly to the specified `ResponseWriter` for which the specified `UIComponent` has a non-`null` attribute value.

`protected  void`

` renderStart(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component, javax.faces.context.ResponseWriter writer)`
           Render the element start for the generated markup related to this component.

`protected  void`

` setSubmittedValue(javax.faces.context.FacesContext context, javax.faces.component.UIComponent component)`
           If a submitted value was included on this request, store it in the component as appropriate.

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

### AbstractRenderer

    public AbstractRenderer()

<span id="method_detail"></span>

**Method Detail**

### decode

    public void decode(javax.faces.context.FacesContext context,
                       javax.faces.component.UIComponent component)

Decode any new state of the specified `UIComponent` from the request contained in the specified `FacesContext`, and store that state on the `UIComponent`.

The default implementation calls `setSubmittedValue()` unless this component has a boolean `disabled` or `readonly` attribute that is set to `true`.

**Overrides:**  
`decode` in class `javax.faces.render.Renderer`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `UIComponent` to be decoded

**Throws:**  
`NullPointerException` - if `context` or `component` is `null`

------------------------------------------------------------------------

### encodeBegin

    public void encodeBegin(javax.faces.context.FacesContext context,
                            javax.faces.component.UIComponent component)
                     throws IOException

Render the beginning of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

The default implementation calls `renderStart()` and `renderAttributes()`.

**Overrides:**  
`encodeBegin` in class `javax.faces.render.Renderer`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `UIComponent` to be decoded

**Throws:**  
`NullPointerException` - if `context` or `component` is `null`

`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### encodeChildren

    public void encodeChildren(javax.faces.context.FacesContext context,
                               javax.faces.component.UIComponent component)
                        throws IOException

Render the children of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

The default implementation iterates through the children of this component and renders them.

**Overrides:**  
`encodeChildren` in class `javax.faces.render.Renderer`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `UIComponent` to be decoded

**Throws:**  
`NullPointerException` - if `context` or `component` is `null`

`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### encodeEnd

    public void encodeEnd(javax.faces.context.FacesContext context,
                          javax.faces.component.UIComponent component)
                   throws IOException

Render the ending of the specified `UIComponent` to the output stream or writer associated with the response we are creating.

The default implementation calls `renderEnd()`.

**Overrides:**  
`encodeEnd` in class `javax.faces.render.Renderer`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `UIComponent` to be decoded

**Throws:**  
`NullPointerException` - if `context` or `component` is `null`

`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### encodeRecursive

    protected void encodeRecursive(javax.faces.context.FacesContext context,
                                   javax.faces.component.UIComponent component)
                            throws IOException

Render nested child components by invoking the encode methods on those components, but only when the `rendered` property is `true`.

**Throws:**  
`IOException`

------------------------------------------------------------------------

### isDisabled

    protected boolean isDisabled(javax.faces.component.UIComponent component)

Return `true` if the specified component is disabled.

**Parameters:**  
`component` - `UIComponent` to be checked

------------------------------------------------------------------------

### isReadOnly

    protected boolean isReadOnly(javax.faces.component.UIComponent component)

Return `true` if the specified component is read only.

**Parameters:**  
`component` - `UIComponent` to be checked

------------------------------------------------------------------------

### renderAttributes

    protected void renderAttributes(javax.faces.context.FacesContext context,
                                    javax.faces.component.UIComponent component,
                                    javax.faces.context.ResponseWriter writer)
                             throws IOException

Render the element attributes for the generated markup related to this component. Simple renderers that create a single markup element for this component should override this method and include calls to to `writeAttribute()` and `writeURIAttribute` on the specified `ResponseWriter`.

The default implementation does nothing.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

`writer` - `ResponseWriter` to which the element start should be rendered

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### renderEnd

    protected void renderEnd(javax.faces.context.FacesContext context,
                             javax.faces.component.UIComponent component,
                             javax.faces.context.ResponseWriter writer)
                      throws IOException

Render the element end for the generated markup related to this component. Simple renderers that create a single markup element for this component should override this method and include a call to `endElement()` on the specified `ResponseWriter`.

The default implementation does nothing.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

`writer` - `ResponseWriter` to which the element start should be rendered

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### renderBoolean

    protected void renderBoolean(javax.faces.context.FacesContext context,
                                 javax.faces.component.UIComponent component,
                                 javax.faces.context.ResponseWriter writer,
                                 String[] names)
                          throws IOException

Render any boolean attributes on the specified list that have `true` values on the corresponding attribute of the specified `UIComponent`.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

`writer` - `ResponseWriter` to which the element start should be rendered

`names` - List of attribute names to be passed through

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### renderPassThrough

    protected void renderPassThrough(javax.faces.context.FacesContext context,
                                     javax.faces.component.UIComponent component,
                                     javax.faces.context.ResponseWriter writer,
                                     String[] names)
                              throws IOException

Render any attributes on the specified list directly to the specified `ResponseWriter` for which the specified `UIComponent` has a non-`null` attribute value. This method may be used to "pass through" commonly used attribute name/value pairs with a minimum of code.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

`writer` - `ResponseWriter` to which the element start should be rendered

`names` - List of attribute names to be passed through

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### renderStart

    protected void renderStart(javax.faces.context.FacesContext context,
                               javax.faces.component.UIComponent component,
                               javax.faces.context.ResponseWriter writer)
                        throws IOException

Render the element start for the generated markup related to this component. Simple renderers that create a single markup element for this component should override this method and include a call to `startElement()` on the specified `ResponseWriter`.

The default implementation does nothing.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

`writer` - `ResponseWriter` to which the element start should be rendered

**Throws:**  
`IOException` - if an input/output error occurs

------------------------------------------------------------------------

### setSubmittedValue

    protected void setSubmittedValue(javax.faces.context.FacesContext context,
                                     javax.faces.component.UIComponent component)

If a submitted value was included on this request, store it in the component as appropriate.

The default implementation determines whether this component implements `EditableValueHolder`. If so, it checks for a request parameter with the same name as the `clientId` of this `UIComponent`. If there is such a parameter, its value is passed (as a String) to the `setSubmittedValue()` method on the `EditableValueHolder` component.

**Parameters:**  
`context` - `FacesContext` for the current request

`component` - `EditableValueHolder` component whose submitted value is to be stored

------------------------------------------------------------------------

### getAsString

    protected String getAsString(javax.faces.context.FacesContext context,
                                 javax.faces.component.UIComponent component,
                                 Object value)
                          throws javax.faces.convert.ConverterException

Convert the Object representation of this component's value to the corresponding String representation. The default implementation utilizes the `getAsString()` method of any associated `Converter`.

**Parameters:**  
`context` - The `FacesContext` for this request

`component` - The `UIComponent` whose value is being converted

`value` - The Object representation to be converted

**Throws:**  
`javax.faces.convert.ConverterException` - if conversion fails

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
<td align="left"><a href="class-use/AbstractRenderer.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/renderer/BaseRenderer.html.md" title="class in org.apache.struts.faces.renderer"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/renderer/AbstractRenderer.html"><strong>FRAMES</strong></a>    <a href="AbstractRenderer.html"><strong>NO FRAMES</strong></a>    
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
