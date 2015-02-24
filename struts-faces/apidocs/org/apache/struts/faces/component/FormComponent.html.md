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
<td align="left"><a href="class-use/FormComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/ErrorsComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/HtmlComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/FormComponent.html"><strong>FRAMES</strong></a>    <a href="FormComponent.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.component
 Class FormComponent
---------------------------------

    java.lang.Object
      javax.faces.component.UIComponent
          javax.faces.component.UIComponentBase
              javax.faces.component.UIForm
                  org.apache.struts.faces.component.FormComponent

**All Implemented Interfaces:**  
javax.faces.component.NamingContainer, javax.faces.component.StateHolder

------------------------------------------------------------------------

    public class FormComponent

extends javax.faces.component.UIForm

**FormComponent** is a specialized subclass of `javax.faces.component.UIForm` that supports automatic creation of form beans in request or session scope.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Log`

` log`
           The `Log` instance for this class.

 <span id="fields_inherited_from_class_javax.faces.component.UIForm"></span>

| **Fields inherited from class javax.faces.component.UIForm** |
|--------------------------------------------------------------|
| `COMPONENT_FAMILY, COMPONENT_TYPE`                           |

 <span id="fields_inherited_from_class_javax.faces.component.NamingContainer"></span>

| **Fields inherited from interface javax.faces.component.NamingContainer** |
|---------------------------------------------------------------------------|
| `SEPARATOR_CHAR`                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` FormComponent()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` createActionForm(javax.faces.context.FacesContext context)`
           Create an appropriate form bean in the appropriate scope, if one does not already exist.

` String`

` getAction()`
           Return the Struts action path to which this form should be submitted.

` String`

` getEnctype()`
           Return the encoding type for this form submit.

` String`

` getFamily()`
           Return the component family to which this component belongs.

` String`

` getFocus()`
           Return the focus element name.

` String`

` getFocusIndex()`
           Return the focus element index.

` String`

` getOnreset()`
           Return the JavaScript to execute on form reset.

` String`

` getOnsubmit()`
           Return the JavaScript to execute on form submit.

` String`

` getStyle()`
           Return the CSS style(s) to be rendered for this component.

` String`

` getStyleClass()`
           Return the CSS style class(es) to be rendered for this component.

` String`

` getTarget()`
           Return the target frame for the response to this form submit.

` ModuleConfig`

` lookupModuleConfig(javax.faces.context.FacesContext context)`
           Return the `ModuleConfig` for the application module this form is being processed for.

` void`

` processDecodes(javax.faces.context.FacesContext context)`
           Create an instance of the form bean (if necessary) before delegating to the standard decoding process.

` void`

` restoreState(javax.faces.context.FacesContext context, Object state)`
           Restore our state from the specified object.

` Object`

` saveState(javax.faces.context.FacesContext context)`
           Create and return an object representing our state to be saved.

` void`

` setAction(String action)`
           Set the Struts action to which this form should be submitted.

` void`

` setEnctype(String enctype)`
           Set the encoding type for this form submit.

` void`

` setFocus(String focus)`
           Set the focus element name.

` void`

` setFocusIndex(String focusIndex)`
           Set the focus element index.

` void`

` setOnreset(String onreset)`
           Set the JavaScript to execute on form reset.

` void`

` setOnsubmit(String onsubmit)`
           Set the JavaScript to execute on form submit.

` void`

` setStyle(String style)`
           Set the CSS style(s) to be rendered for this component.

` void`

` setStyleClass(String styleClass)`
           Set the CSS style class(es) to be rendered for this component.

` void`

` setTarget(String target)`
           Set the target frame for the response to this form submit.

 <span id="methods_inherited_from_class_javax.faces.component.UIForm"></span>

| **Methods inherited from class javax.faces.component.UIForm**  |
|----------------------------------------------------------------|
| `isSubmitted, processUpdates, processValidators, setSubmitted` |

 <span id="methods_inherited_from_class_javax.faces.component.UIComponentBase"></span>

| **Methods inherited from class javax.faces.component.UIComponentBase**                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addFacesListener, broadcast, decode, encodeBegin, encodeChildren, encodeEnd, findComponent, getAttributes, getChildCount, getChildren, getClientId, getFacesContext, getFacesListeners, getFacet, getFacets, getFacetsAndChildren, getId, getParent, getRenderer, getRendererType, getRendersChildren, getValueBinding, isRendered, isTransient, processRestoreState, processSaveState, queueEvent, removeFacesListener, restoreAttachedState, saveAttachedState, setId, setParent, setRendered, setRendererType, setTransient, setValueBinding` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

The `Log` instance for this class.

<span id="constructor_detail"></span>

**Constructor Detail**

### FormComponent

    public FormComponent()

<span id="method_detail"></span>

**Method Detail**

### getAction

    public String getAction()

Return the Struts action path to which this form should be submitted.

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

Set the Struts action to which this form should be submitted.

**Parameters:**  
`action` - The new action path

------------------------------------------------------------------------

### getEnctype

    public String getEnctype()

Return the encoding type for this form submit.

------------------------------------------------------------------------

### setEnctype

    public void setEnctype(String enctype)

Set the encoding type for this form submit.

**Parameters:**  
`enctype` - The new enctype path

------------------------------------------------------------------------

### getFamily

    public String getFamily()

Return the component family to which this component belongs.

**Overrides:**  
`getFamily` in class `javax.faces.component.UIForm`

------------------------------------------------------------------------

### getFocus

    public String getFocus()

Return the focus element name.

------------------------------------------------------------------------

### setFocus

    public void setFocus(String focus)

Set the focus element name.

**Parameters:**  
`focus` - The new focus path

------------------------------------------------------------------------

### getFocusIndex

    public String getFocusIndex()

Return the focus element index.

------------------------------------------------------------------------

### setFocusIndex

    public void setFocusIndex(String focusIndex)

Set the focus element index.

**Parameters:**  
`focusIndex` - The new focusIndex path

------------------------------------------------------------------------

### getOnreset

    public String getOnreset()

Return the JavaScript to execute on form reset.

------------------------------------------------------------------------

### setOnreset

    public void setOnreset(String onreset)

Set the JavaScript to execute on form reset.

**Parameters:**  
`onreset` - The new onreset path

------------------------------------------------------------------------

### getOnsubmit

    public String getOnsubmit()

Return the JavaScript to execute on form submit.

------------------------------------------------------------------------

### setOnsubmit

    public void setOnsubmit(String onsubmit)

Set the JavaScript to execute on form submit.

**Parameters:**  
`onsubmit` - The new onsubmit path

------------------------------------------------------------------------

### getStyle

    public String getStyle()

Return the CSS style(s) to be rendered for this component.

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

Set the CSS style(s) to be rendered for this component.

**Parameters:**  
`style` - The new CSS style(s)

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

Return the CSS style class(es) to be rendered for this component.

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

Set the CSS style class(es) to be rendered for this component.

**Parameters:**  
`styleClass` - The new CSS style class(es)

------------------------------------------------------------------------

### getTarget

    public String getTarget()

Return the target frame for the response to this form submit.

------------------------------------------------------------------------

### setTarget

    public void setTarget(String target)

Set the target frame for the response to this form submit.

**Parameters:**  
`target` - The new CSS target(s)

------------------------------------------------------------------------

### processDecodes

    public void processDecodes(javax.faces.context.FacesContext context)

Create an instance of the form bean (if necessary) before delegating to the standard decoding process.

**Overrides:**  
`processDecodes` in class `javax.faces.component.UIForm`

<!-- -->

**Parameters:**  
`context` - FacesContext for the request we are processing

------------------------------------------------------------------------

### restoreState

    public void restoreState(javax.faces.context.FacesContext context,
                             Object state)

Restore our state from the specified object.

**Specified by:**  
`restoreState` in interface `javax.faces.component.StateHolder`

**Overrides:**  
`restoreState` in class `javax.faces.component.UIComponentBase`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`state` - Object containing our saved state

------------------------------------------------------------------------

### saveState

    public Object saveState(javax.faces.context.FacesContext context)

Create and return an object representing our state to be saved.

**Specified by:**  
`saveState` in interface `javax.faces.component.StateHolder`

**Overrides:**  
`saveState` in class `javax.faces.component.UIForm`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

------------------------------------------------------------------------

### createActionForm

    public void createActionForm(javax.faces.context.FacesContext context)

Create an appropriate form bean in the appropriate scope, if one does not already exist.

**Parameters:**  
`context` - FacesContext for the current request

**Throws:**  
`IllegalArgumentException` - if no ActionConfig for the specified action attribute can be located

`IllegalArgumentException` - if no FormBeanConfig for the specified form bean can be located

`IllegalArgumentException` - if no ModuleConfig can be located for this application module

------------------------------------------------------------------------

### lookupModuleConfig

    public ModuleConfig lookupModuleConfig(javax.faces.context.FacesContext context)

Return the `ModuleConfig` for the application module this form is being processed for.

**Parameters:**  
`context` - The `FacesContext` for the current request

**Throws:**  
`IllegalArgumentException` - if no `ModuleConfig` can be found

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
<td align="left"><a href="class-use/FormComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/ErrorsComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/HtmlComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/FormComponent.html"><strong>FRAMES</strong></a>    <a href="FormComponent.html"><strong>NO FRAMES</strong></a>    
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
