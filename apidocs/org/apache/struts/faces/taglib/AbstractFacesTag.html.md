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
<td align="left"><a href="class-use/AbstractFacesTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/taglib/BaseTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/AbstractFacesTag.html"><strong>FRAMES</strong></a>    <a href="AbstractFacesTag.html"><strong>NO FRAMES</strong></a>    
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
 Class AbstractFacesTag
------------------------------

    java.lang.Object
      javax.faces.webapp.UIComponentTag
          org.apache.struts.faces.taglib.AbstractFacesTag

**All Implemented Interfaces:**  
[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[BaseTag](../../../../../org/apache/struts/faces/taglib/BaseTag.html.md "class in org.apache.struts.faces.taglib"), [CommandLinkTag](../../../../../org/apache/struts/faces/taglib/CommandLinkTag.html "class in org.apache.struts.faces.taglib"), [ErrorsTag](../../../../../org/apache/struts/faces/taglib/ErrorsTag.html "class in org.apache.struts.faces.taglib"), [FormTag](../../../../../org/apache/struts/faces/taglib/FormTag.html "class in org.apache.struts.faces.taglib"), [HtmlTag](../../../../../org/apache/struts/faces/taglib/HtmlTag.html "class in org.apache.struts.faces.taglib"), [MessageTag](../../../../../org/apache/struts/faces/taglib/MessageTag.html "class in org.apache.struts.faces.taglib"), [StylesheetTag](../../../../../org/apache/struts/faces/taglib/StylesheetTag.html "class in org.apache.struts.faces.taglib"), [WriteTag](../../../../../org/apache/struts/faces/taglib/WriteTag.html "class in org.apache.struts.faces.taglib")

------------------------------------------------------------------------

    public abstract class AbstractFacesTag

extends javax.faces.webapp.UIComponentTag

Abstract base class for custom component tags for the *Struts-Faces Integration Library*.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` bundle`
           The servlet context attribute under which our `MessageResources` bundle is stored.

`protected  String`

` style`
           The CSS style(s) used to render this component.

`protected  String`

` styleClass`
           The CSS style class(es) used to render this component.

`protected  String`

` value`
           The literal value to be rendered.

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
| ` AbstractFacesTag()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

`abstract  String`

` getComponentType()`
           Return the component type of the component to be created for this tag.

`abstract  String`

` getRendererType()`
           Return the `rendererType` to be used for rendering our component.

` void`

` release()`
           Release any variables allocated during use of this tag instance.

`protected  void`

` setBooleanAttribute(javax.faces.component.UIComponent component, String name, String value)`
           If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

` void`

` setBundle(String bundle)`
            

`protected  void`

` setIntegerAttribute(javax.faces.component.UIComponent component, String name, String value)`
           If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

`protected  void`

` setProperties(javax.faces.component.UIComponent component)`
           Override attributes set on this tag instance.

`protected  void`

` setStringAttribute(javax.faces.component.UIComponent component, String name, String value)`
           If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

` void`

` setStyle(String style)`
            

` void`

` setStyleClass(String styleClass)`
            

` void`

` setValue(String value)`
            

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

<span id="bundle"></span>

### bundle

    protected String bundle

The servlet context attribute under which our `MessageResources` bundle is stored.

------------------------------------------------------------------------

<span id="style"></span>

### style

    protected String style

The CSS style(s) used to render this component.

------------------------------------------------------------------------

<span id="styleClass"></span>

### styleClass

    protected String styleClass

The CSS style class(es) used to render this component.

------------------------------------------------------------------------

<span id="value"></span>

### value

    protected String value

The literal value to be rendered.

<span id="constructor_detail"></span>

**Constructor Detail**

### AbstractFacesTag

    public AbstractFacesTag()

<span id="method_detail"></span>

**Method Detail**

### setBundle

    public void setBundle(String bundle)

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

------------------------------------------------------------------------

### getComponentType

    public abstract String getComponentType()

Return the component type of the component to be created for this tag.

**Specified by:**  
`getComponentType` in class `javax.faces.webapp.UIComponentTag`

------------------------------------------------------------------------

### getRendererType

    public abstract String getRendererType()

Return the `rendererType` to be used for rendering our component.

**Specified by:**  
`getRendererType` in class `javax.faces.webapp.UIComponentTag`

------------------------------------------------------------------------

### release

    public void release()

Release any variables allocated during use of this tag instance.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `javax.faces.webapp.UIComponentTag`

------------------------------------------------------------------------

### setProperties

    protected void setProperties(javax.faces.component.UIComponent component)

Override attributes set on this tag instance.

**Overrides:**  
`setProperties` in class `javax.faces.webapp.UIComponentTag`

<!-- -->

**Parameters:**  
`component` - Component whose attributes should be overridden

------------------------------------------------------------------------

### setBooleanAttribute

    protected void setBooleanAttribute(javax.faces.component.UIComponent component,
                                       String name,
                                       String value)

If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

**Parameters:**  
`component` - `UIComponent` whose attribute is to be set

`name` - Attribute name

`value` - Attribute value (or `null`)

**Throws:**  
`NumberFormatException` - if the value does not contain a parsable integer

`ReferenceSyntaxException` - if the expression has invalid syntax

------------------------------------------------------------------------

### setIntegerAttribute

    protected void setIntegerAttribute(javax.faces.component.UIComponent component,
                                       String name,
                                       String value)

If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

**Parameters:**  
`component` - `UIComponent` whose attribute is to be set

`name` - Attribute name

`value` - Attribute value (or `null`)

**Throws:**  
`NumberFormatException` - if the value does not contain a parsable integer

`ReferenceSyntaxException` - if the expression has invalid syntax

------------------------------------------------------------------------

### setStringAttribute

    protected void setStringAttribute(javax.faces.component.UIComponent component,
                                      String name,
                                      String value)

If the specified attribute value is not `null` use it to either store a value binding expression for the specified attribute name, or store it as the literal value of the attribute.

**Parameters:**  
`component` - `UIComponent` whose attribute is to be set

`name` - Attribute name

`value` - Attribute value (or `null`)

**Throws:**  
`ReferenceSyntaxException` - if the expression has invalid syntax

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
<td align="left"><a href="class-use/AbstractFacesTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../../org/apache/struts/faces/taglib/BaseTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/AbstractFacesTag.html"><strong>FRAMES</strong></a>    <a href="AbstractFacesTag.html"><strong>NO FRAMES</strong></a>    
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
