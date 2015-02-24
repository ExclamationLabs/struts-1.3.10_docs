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
<td align="left"><a href="class-use/StylesheetComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/MessageComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/WriteComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/StylesheetComponent.html"><strong>FRAMES</strong></a>    <a href="StylesheetComponent.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.component.UIOutput">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.component
 Class StylesheetComponent
---------------------------------

    java.lang.Object
      javax.faces.component.UIComponent
          javax.faces.component.UIComponentBase
              javax.faces.component.UIOutput
                  org.apache.struts.faces.component.StylesheetComponent

**All Implemented Interfaces:**  
javax.faces.component.StateHolder, javax.faces.component.ValueHolder

------------------------------------------------------------------------

    public class StylesheetComponent

extends javax.faces.component.UIOutput

Custom component that replaces the Struts `.html.md:stylesheet>` tag.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.faces.component.UIOutput"></span>

| **Fields inherited from class javax.faces.component.UIOutput** |
|----------------------------------------------------------------|
| `COMPONENT_FAMILY, COMPONENT_TYPE`                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` StylesheetComponent()`                                                                                                                                                                         
            Create a new [`StylesheetComponent`](../../../../../org/apache/struts/faces/component/StylesheetComponent.html.md "class in org.apache.struts.faces.component") with default properties.  |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getFamily()`
           Return the component family to which this component belongs.

` String`

` getPath()`
           Return the context-relative stylesheet path.

` void`

` restoreState(javax.faces.context.FacesContext context, Object state)`
           Restore the state of this component.

` Object`

` saveState(javax.faces.context.FacesContext context)`
           Save the state of this component.

` void`

` setPath(String path)`
           Set the context-relative stylesheet path.

 <span id="methods_inherited_from_class_javax.faces.component.UIOutput"></span>

| **Methods inherited from class javax.faces.component.UIOutput** |
|-----------------------------------------------------------------|
| `getConverter, getLocalValue, getValue, setConverter, setValue` |

 <span id="methods_inherited_from_class_javax.faces.component.UIComponentBase"></span>

| **Methods inherited from class javax.faces.component.UIComponentBase**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addFacesListener, broadcast, decode, encodeBegin, encodeChildren, encodeEnd, findComponent, getAttributes, getChildCount, getChildren, getClientId, getFacesContext, getFacesListeners, getFacet, getFacets, getFacetsAndChildren, getId, getParent, getRenderer, getRendererType, getRendersChildren, getValueBinding, isRendered, isTransient, processDecodes, processRestoreState, processSaveState, processUpdates, processValidators, queueEvent, removeFacesListener, restoreAttachedState, saveAttachedState, setId, setParent, setRendered, setRendererType, setTransient, setValueBinding` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### StylesheetComponent

    public StylesheetComponent()

Create a new [`StylesheetComponent`](../../../../../org/apache/struts/faces/component/StylesheetComponent.html.md "class in org.apache.struts.faces.component") with default properties.

<span id="method_detail"></span>

**Method Detail**

### getFamily

    public String getFamily()

Return the component family to which this component belongs.

**Overrides:**  
`getFamily` in class `javax.faces.component.UIOutput`

------------------------------------------------------------------------

### getPath

    public String getPath()

Return the context-relative stylesheet path.

------------------------------------------------------------------------

### setPath

    public void setPath(String path)

Set the context-relative stylesheet path.

**Parameters:**  
`path` - The new path

------------------------------------------------------------------------

### restoreState

    public void restoreState(javax.faces.context.FacesContext context,
                             Object state)

Restore the state of this component.

**Specified by:**  
`restoreState` in interface `javax.faces.component.StateHolder`

**Overrides:**  
`restoreState` in class `javax.faces.component.UIOutput`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`state` - State object from which to restore our state

------------------------------------------------------------------------

### saveState

    public Object saveState(javax.faces.context.FacesContext context)

Save the state of this component.

**Specified by:**  
`saveState` in interface `javax.faces.component.StateHolder`

**Overrides:**  
`saveState` in class `javax.faces.component.UIOutput`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

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
<td align="left"><a href="class-use/StylesheetComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/MessageComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/WriteComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/StylesheetComponent.html"><strong>FRAMES</strong></a>    <a href="StylesheetComponent.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.component.UIOutput">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
