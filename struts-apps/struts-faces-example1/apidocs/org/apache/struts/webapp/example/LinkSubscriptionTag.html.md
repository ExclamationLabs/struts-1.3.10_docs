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
<td align="left"><a href="class-use/LinkSubscriptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/IndexBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/LinkUserTag.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/LinkSubscriptionTag.html"><strong>FRAMES</strong></a>    <a href="LinkSubscriptionTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.webapp.example
 Class LinkSubscriptionTag
--------------------------------

    java.lang.Object
      javax.faces.webapp.UIComponentTag
          org.apache.struts.webapp.example.LinkSubscriptionTag

**All Implemented Interfaces:**  
[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class LinkSubscriptionTag

extends javax.faces.webapp.UIComponentTag

Generate a URL-encoded hyperlink to the specified URI, with associated query parameters selecting a specified Subscription.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**Author:**  
Craig R. McClanahan

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` name`
           The attribute name.

`protected  String`

` page`
           The context-relative URI.

 <span id="fields_inherited_from_class_javax.faces.webapp.UIComponentTag"></span>

| **Fields inherited from class javax.faces.webapp.UIComponentTag** |
|-------------------------------------------------------------------|
| `pageContext`                                                     |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary**  |
|--------------------------|
| ` LinkSubscriptionTag()` 
                           |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getComponentType()`
           Return the component type for this tag.

` String`

` getRendererType()`
           Return the renderer type associated with this tag.

` void`

` release()`
           Release resources allocated to this tag instance.

` void`

` setName(String name)`
            

` void`

` setPage(String page)`
            

`protected  void`

` setProperties(javax.faces.component.UIComponent component)`
           Override attributes set on this tag instance.

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

<span id="name"></span>

### name

    protected String name

The attribute name.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

The context-relative URI.

<span id="constructor_detail"></span>

**Constructor Detail**

### LinkSubscriptionTag

    public LinkSubscriptionTag()

<span id="method_detail"></span>

**Method Detail**

### setName

    public void setName(String name)

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

------------------------------------------------------------------------

### getComponentType

    public String getComponentType()

Return the component type for this tag.

**Specified by:**  
`getComponentType` in class `javax.faces.webapp.UIComponentTag`

------------------------------------------------------------------------

### getRendererType

    public String getRendererType()

Return the renderer type associated with this tag.

**Specified by:**  
`getRendererType` in class `javax.faces.webapp.UIComponentTag`

------------------------------------------------------------------------

### release

    public void release()

Release resources allocated to this tag instance.

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
<td align="left"><a href="class-use/LinkSubscriptionTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/example/IndexBacking.html.md" title="class in org.apache.struts.webapp.example"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/webapp/example/LinkUserTag.html" title="class in org.apache.struts.webapp.example"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/example/LinkSubscriptionTag.html"><strong>FRAMES</strong></a>    <a href="LinkSubscriptionTag.html"><strong>NO FRAMES</strong></a>    
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
