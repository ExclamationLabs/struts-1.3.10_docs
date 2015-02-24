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
<td align="left"><a href="class-use/CommandLinkComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/BaseComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/ErrorsComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/CommandLinkComponent.html"><strong>FRAMES</strong></a>    <a href="CommandLinkComponent.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.component.UICommand">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.component
 Class CommandLinkComponent
---------------------------------

    java.lang.Object
      javax.faces.component.UIComponent
          javax.faces.component.UIComponentBase
              javax.faces.component.UICommand
                  org.apache.struts.faces.component.CommandLinkComponent

**All Implemented Interfaces:**  
javax.faces.component.ActionSource, javax.faces.component.StateHolder

------------------------------------------------------------------------

    public class CommandLinkComponent

extends javax.faces.component.UICommand

Custom component that emulates the JSF standard component class `javax.faces.component.html.md.HtmlCommandLink` (and its corresponding renderer) but is not tied to a particular implementation of renderer for `javax.faces.component.UIForm`.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.faces.component.UICommand"></span>

| **Fields inherited from class javax.faces.component.UICommand** |
|-----------------------------------------------------------------|
| `COMPONENT_FAMILY, COMPONENT_TYPE`                              |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                            |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` CommandLinkComponent()`                                                                                                                                                                          
            Create a new [`CommandLinkComponent`](../../../../../org/apache/struts/faces/component/CommandLinkComponent.html.md "class in org.apache.struts.faces.component") with default properties.  |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getAccesskey()`
            

` String`

` getCharset()`
            

` String`

` getDir()`
            

` String`

` getFamily()`
           Return the component family to which this component belongs.

` String`

` getHreflang()`
            

` String`

` getLang()`
            

` String`

` getOnblur()`
            

` String`

` getOnclick()`
            

` String`

` getOndblclick()`
            

` String`

` getOnfocus()`
            

` String`

` getOnkeydown()`
            

` String`

` getOnkeypress()`
            

` String`

` getOnkeyup()`
            

` String`

` getOnmousedown()`
            

` String`

` getOnmousemove()`
            

` String`

` getOnmouseout()`
            

` String`

` getOnmouseover()`
            

` String`

` getOnmouseup()`
            

` String`

` getRel()`
            

` String`

` getRev()`
            

` String`

` getStyle()`
            

` String`

` getStyleClass()`
            

` String`

` getTabindex()`
            

` String`

` getTarget()`
            

` String`

` getTitle()`
            

` String`

` getType()`
            

` void`

` restoreState(javax.faces.context.FacesContext context, Object state)`
           Restore the state of this component.

` Object`

` saveState(javax.faces.context.FacesContext context)`
           Save the state of this component.

` void`

` setAccesskey(String accesskey)`
            

` void`

` setCharset(String charset)`
            

` void`

` setDir(String dir)`
            

` void`

` setHreflang(String hreflang)`
            

` void`

` setLang(String lang)`
            

` void`

` setOnblur(String onblur)`
            

` void`

` setOnclick(String onclick)`
            

` void`

` setOndblclick(String ondblclick)`
            

` void`

` setOnfocus(String onfocus)`
            

` void`

` setOnkeydown(String onkeydown)`
            

` void`

` setOnkeypress(String onkeypress)`
            

` void`

` setOnkeyup(String onkeyup)`
            

` void`

` setOnmousedown(String onmousedown)`
            

` void`

` setOnmousemove(String onmousemove)`
            

` void`

` setOnmouseout(String onmouseout)`
            

` void`

` setOnmouseover(String onmouseover)`
            

` void`

` setOnmouseup(String onmouseup)`
            

` void`

` setRel(String rel)`
            

` void`

` setRev(String rev)`
            

` void`

` setStyle(String style)`
            

` void`

` setStyleClass(String styleClass)`
            

` void`

` setTabindex(String tabindex)`
            

` void`

` setTarget(String target)`
            

` void`

` setTitle(String title)`
            

` void`

` setType(String type)`
            

 <span id="methods_inherited_from_class_javax.faces.component.UICommand"></span>

| **Methods inherited from class javax.faces.component.UICommand**                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addActionListener, broadcast, getAction, getActionListener, getActionListeners, getValue, isImmediate, queueEvent, removeActionListener, setAction, setActionListener, setImmediate, setValue` |

 <span id="methods_inherited_from_class_javax.faces.component.UIComponentBase"></span>

| **Methods inherited from class javax.faces.component.UIComponentBase**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addFacesListener, decode, encodeBegin, encodeChildren, encodeEnd, findComponent, getAttributes, getChildCount, getChildren, getClientId, getFacesContext, getFacesListeners, getFacet, getFacets, getFacetsAndChildren, getId, getParent, getRenderer, getRendererType, getRendersChildren, getValueBinding, isRendered, isTransient, processDecodes, processRestoreState, processSaveState, processUpdates, processValidators, removeFacesListener, restoreAttachedState, saveAttachedState, setId, setParent, setRendered, setRendererType, setTransient, setValueBinding` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### CommandLinkComponent

    public CommandLinkComponent()

Create a new [`CommandLinkComponent`](../../../../../org/apache/struts/faces/component/CommandLinkComponent.html.md "class in org.apache.struts.faces.component") with default properties.

<span id="method_detail"></span>

**Method Detail**

### getAccesskey

    public String getAccesskey()

------------------------------------------------------------------------

### setAccesskey

    public void setAccesskey(String accesskey)

------------------------------------------------------------------------

### getCharset

    public String getCharset()

------------------------------------------------------------------------

### setCharset

    public void setCharset(String charset)

------------------------------------------------------------------------

### getDir

    public String getDir()

------------------------------------------------------------------------

### setDir

    public void setDir(String dir)

------------------------------------------------------------------------

### getFamily

    public String getFamily()

Return the component family to which this component belongs.

**Overrides:**  
`getFamily` in class `javax.faces.component.UICommand`

------------------------------------------------------------------------

### getHreflang

    public String getHreflang()

------------------------------------------------------------------------

### setHreflang

    public void setHreflang(String hreflang)

------------------------------------------------------------------------

### getLang

    public String getLang()

------------------------------------------------------------------------

### setLang

    public void setLang(String lang)

------------------------------------------------------------------------

### getOnblur

    public String getOnblur()

------------------------------------------------------------------------

### setOnblur

    public void setOnblur(String onblur)

------------------------------------------------------------------------

### getOnclick

    public String getOnclick()

------------------------------------------------------------------------

### setOnclick

    public void setOnclick(String onclick)

------------------------------------------------------------------------

### getOndblclick

    public String getOndblclick()

------------------------------------------------------------------------

### setOndblclick

    public void setOndblclick(String ondblclick)

------------------------------------------------------------------------

### getOnfocus

    public String getOnfocus()

------------------------------------------------------------------------

### setOnfocus

    public void setOnfocus(String onfocus)

------------------------------------------------------------------------

### getOnkeydown

    public String getOnkeydown()

------------------------------------------------------------------------

### setOnkeydown

    public void setOnkeydown(String onkeydown)

------------------------------------------------------------------------

### getOnkeypress

    public String getOnkeypress()

------------------------------------------------------------------------

### setOnkeypress

    public void setOnkeypress(String onkeypress)

------------------------------------------------------------------------

### getOnkeyup

    public String getOnkeyup()

------------------------------------------------------------------------

### setOnkeyup

    public void setOnkeyup(String onkeyup)

------------------------------------------------------------------------

### getOnmousedown

    public String getOnmousedown()

------------------------------------------------------------------------

### setOnmousedown

    public void setOnmousedown(String onmousedown)

------------------------------------------------------------------------

### getOnmousemove

    public String getOnmousemove()

------------------------------------------------------------------------

### setOnmousemove

    public void setOnmousemove(String onmousemove)

------------------------------------------------------------------------

### getOnmouseout

    public String getOnmouseout()

------------------------------------------------------------------------

### setOnmouseout

    public void setOnmouseout(String onmouseout)

------------------------------------------------------------------------

### getOnmouseover

    public String getOnmouseover()

------------------------------------------------------------------------

### setOnmouseover

    public void setOnmouseover(String onmouseover)

------------------------------------------------------------------------

### getOnmouseup

    public String getOnmouseup()

------------------------------------------------------------------------

### setOnmouseup

    public void setOnmouseup(String onmouseup)

------------------------------------------------------------------------

### getRel

    public String getRel()

------------------------------------------------------------------------

### setRel

    public void setRel(String rel)

------------------------------------------------------------------------

### getRev

    public String getRev()

------------------------------------------------------------------------

### setRev

    public void setRev(String rev)

------------------------------------------------------------------------

### getStyle

    public String getStyle()

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

------------------------------------------------------------------------

### getTabindex

    public String getTabindex()

------------------------------------------------------------------------

### setTabindex

    public void setTabindex(String tabindex)

------------------------------------------------------------------------

### getTarget

    public String getTarget()

------------------------------------------------------------------------

### setTarget

    public void setTarget(String target)

------------------------------------------------------------------------

### getTitle

    public String getTitle()

------------------------------------------------------------------------

### setTitle

    public void setTitle(String title)

------------------------------------------------------------------------

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### restoreState

    public void restoreState(javax.faces.context.FacesContext context,
                             Object state)

Restore the state of this component.

**Specified by:**  
`restoreState` in interface `javax.faces.component.StateHolder`

**Overrides:**  
`restoreState` in class `javax.faces.component.UICommand`

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
`saveState` in class `javax.faces.component.UICommand`

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
<td align="left"><a href="class-use/CommandLinkComponent.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/component/BaseComponent.html.md" title="class in org.apache.struts.faces.component"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/component/ErrorsComponent.html" title="class in org.apache.struts.faces.component"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/component/CommandLinkComponent.html"><strong>FRAMES</strong></a>    <a href="CommandLinkComponent.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.component.UICommand">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
