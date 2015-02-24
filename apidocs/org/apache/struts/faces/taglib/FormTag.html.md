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
<td align="left"><a href="class-use/FormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/taglib/ErrorsTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/taglib/HtmlTag.html" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/FormTag.html"><strong>FRAMES</strong></a>    <a href="FormTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.taglib
 Class FormTag
------------------------------

    java.lang.Object
      javax.faces.webapp.UIComponentTag
          org.apache.struts.faces.taglib.AbstractFacesTag
              org.apache.struts.faces.taglib.FormTag

**All Implemented Interfaces:**  
[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class FormTag

extends [AbstractFacesTag](../../../../../org/apache/struts/faces/taglib/AbstractFacesTag.html.md "class in org.apache.struts.faces.taglib")

Render an input form that is submitted to a Struts `Action`, for the *Struts-Faces Integration Library*.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` action`
           The `path` of the Struts `Action` to which this form should be submitted.

`protected  String`

` enctype`
           The content encoding type to use.

`protected  String`

`focus`
           The name of the field to which focus should be set when this form is displayed.

`protected  String`

` focusIndex`
           The subscript of the focus field array to receive focus.

`protected  String`

` onreset`
           The JavaScript reset event handler.

`protected  String`

` onsubmit`
           The JavaScript submit event handler.

`protected  String`

` target`
           The window target for this submit.

 <span id="fields_inherited_from_class_org.apache.struts.faces.taglib.AbstractFacesTag"></span>

| **Fields inherited from class org.apache.struts.faces.taglib.[AbstractFacesTag](../../../../../org/apache/struts/faces/taglib/AbstractFacesTag.html.md "class in org.apache.struts.faces.taglib")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` bundle,  style,  styleClass,  value`                                                                                                                                                           |

 <span id="fields_inherited_from_class_javax.faces.webapp.UIComponentTag"></span>

| **Fields inherited from class javax.faces.webapp.UIComponentTag** |
|-------------------------------------------------------------------|
| `pageContext`                                                     |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` FormTag()`            
                          |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getComponentType()`
           Return the type of component to be created for this tag.

` String`

` getRendererType()`
           Return the `rendererType` to be used for rendering our component.

` void`

` release()`
           Release any allocated resources.

` void`

` setAction(String action)`
            

` void`

` setEnctype(String enctype)`
            

` void`

` setFocus(String focus)`
            

` void`

` setFocusIndex(String focusIndex)`
            

` void`

` setOnreset(String onreset)`
            

` void`

` setOnsubmit(String onsubmit)`
            

`protected  void`

` setProperties(javax.faces.component.UIComponent component)`
           Override attributes set on this tag instance.

` void`

` setTarget(String target)`
            

 <span id="methods_inherited_from_class_org.apache.struts.faces.taglib.AbstractFacesTag"></span>

| **Methods inherited from class org.apache.struts.faces.taglib.[AbstractFacesTag](../../../../../org/apache/struts/faces/taglib/AbstractFacesTag.html.md "class in org.apache.struts.faces.taglib")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` setBooleanAttribute,  setBundle,  setIntegerAttribute,  setStringAttribute,  setStyle,  setStyleClass,  setValue`                                                                               |

 <span id="methods_inherited_from_class_javax.faces.webapp.UIComponentTag"></span>

| **Methods inherited from class javax.faces.webapp.UIComponentTag**                                                                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, doStartTag, encodeBegin, encodeChildren, encodeEnd, findComponent, getComponentInstance, getCreated, getDoEndValue, getDoStartValue, getFacesContext, getFacetName, getId, getParent, getParentUIComponentTag, getPathToComponent, isSuppressed, isValueReference, setBinding, setId, setPageContext, setParent, setRendered, setupResponseWriter` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="action"></span>

### action

    protected String action

The `path` of the Struts `Action` to which this form should be submitted. This property is analogous to the `formName` property on the form tag in the standard HTML RenderKit.

------------------------------------------------------------------------

<span id="enctype"></span>

### enctype

    protected String enctype

The content encoding type to use.

------------------------------------------------------------------------

<span id="focus"></span>

### focus

    protected String focus

The name of the field to which focus should be set when this form is displayed.

------------------------------------------------------------------------

<span id="focusIndex"></span>

### focusIndex

    protected String focusIndex

The subscript of the focus field array to receive focus.

------------------------------------------------------------------------

<span id="onreset"></span>

### onreset

    protected String onreset

The JavaScript reset event handler.

------------------------------------------------------------------------

<span id="onsubmit"></span>

### onsubmit

    protected String onsubmit

The JavaScript submit event handler.

------------------------------------------------------------------------

<span id="target"></span>

### target

    protected String target

The window target for this submit.

<span id="constructor_detail"></span>

**Constructor Detail**

### FormTag

    public FormTag()

<span id="method_detail"></span>

**Method Detail**

### setAction

    public void setAction(String action)

------------------------------------------------------------------------

### setEnctype

    public void setEnctype(String enctype)

------------------------------------------------------------------------

### setFocus

    public void setFocus(String focus)

------------------------------------------------------------------------

### setFocusIndex

    public void setFocusIndex(String focusIndex)

------------------------------------------------------------------------

### setOnreset

    public void setOnreset(String onreset)

------------------------------------------------------------------------

### setOnsubmit

    public void setOnsubmit(String onsubmit)

------------------------------------------------------------------------

### setTarget

    public void setTarget(String target)

------------------------------------------------------------------------

### release

    public void release()

Release any allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `AbstractFacesTag`

------------------------------------------------------------------------

### getComponentType

    public String getComponentType()

Return the type of component to be created for this tag.

**Specified by:**  
` getComponentType` in class `AbstractFacesTag`

------------------------------------------------------------------------

### getRendererType

    public String getRendererType()

Return the `rendererType` to be used for rendering our component.

**Specified by:**  
` getRendererType` in class `AbstractFacesTag`

------------------------------------------------------------------------

### setProperties

    protected void setProperties(javax.faces.component.UIComponent component)

Override attributes set on this tag instance.

**Overrides:**  
` setProperties` in class `AbstractFacesTag`

<!-- -->

**Parameters:**  
`component` - Component whose attributes should be overridden

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
<td align="left"><a href="class-use/FormTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/taglib/ErrorsTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/taglib/HtmlTag.html" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/FormTag.html"><strong>FRAMES</strong></a>    <a href="FormTag.html"><strong>NO FRAMES</strong></a>    
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
