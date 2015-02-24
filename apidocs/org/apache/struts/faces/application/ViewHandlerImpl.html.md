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
<td align="left"><a href="class-use/ViewHandlerImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/PropertyResolverImpl.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/ViewHandlerImpl.html"><strong>FRAMES</strong></a>    <a href="ViewHandlerImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.application.ViewHandler">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.faces.application
 Class ViewHandlerImpl
-----------------------------------

    java.lang.Object
      javax.faces.application.ViewHandler
          org.apache.struts.faces.application.ViewHandlerImpl

------------------------------------------------------------------------

    public class ViewHandlerImpl

extends javax.faces.application.ViewHandler

Custom `ViewHandler` implementation that adds features specific to the Struts-Faces Integration Library. It leverages the "decorator pattern" customization strategy that JSF supports, by delegating most processing to the `ViewHandler` instance handed to our constructor.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.faces.application.ViewHandler"></span>

| **Fields inherited from class javax.faces.application.ViewHandler** |
|---------------------------------------------------------------------|
| `CHARACTER_ENCODING_KEY, DEFAULT_SUFFIX, DEFAULT_SUFFIX_PARAM_NAME` |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                   |
|-------------------------------------------------------------------------------------------|
| ` ViewHandlerImpl(javax.faces.application.ViewHandler handler)`                           
            Construct a `ViewHandlerImpl` decorating the specified `ViewHandler` instance.  |

  <span id="method_summary"></span>

**Method Summary**

` Locale`

` calculateLocale(javax.faces.context.FacesContext context)`
            

` String`

` calculateRenderKitId(javax.faces.context.FacesContext context)`
            

` javax.faces.component.UIViewRoot`

` createView(javax.faces.context.FacesContext context, String viewId)`
            

` String`

` getActionURL(javax.faces.context.FacesContext context, String viewId)`
            

` javax.faces.application.ViewHandler`

` getHandler()`
           Return the `ViewHandler` instance we are decorating.

` String`

` getResourceURL(javax.faces.context.FacesContext context, String viewId)`
            

` void`

` renderView(javax.faces.context.FacesContext context, javax.faces.component.UIViewRoot view)`
           If the Struts application has set a `Locale`, pass it on to JSF prior to delegating the actual rendering.

` javax.faces.component.UIViewRoot`

` restoreView(javax.faces.context.FacesContext context, String viewId)`
            

` void`

` setHandler(javax.faces.application.ViewHandler handler)`
           Set the `ViewHandler` instance we are decorating.

` void`

` writeState(javax.faces.context.FacesContext context)`
            

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ViewHandlerImpl

    public ViewHandlerImpl(javax.faces.application.ViewHandler handler)

Construct a `ViewHandlerImpl` decorating the specified `ViewHandler` instance.

**Parameters:**  
`handler` - `ViewHandler` to be decorated

<span id="method_detail"></span>

**Method Detail**

### getHandler

    public javax.faces.application.ViewHandler getHandler()

Return the `ViewHandler` instance we are decorating.

------------------------------------------------------------------------

### setHandler

    public void setHandler(javax.faces.application.ViewHandler handler)

Set the `ViewHandler` instance we are decorating.

**Parameters:**  
`handler` - `ViewHandler` instance to decorate

------------------------------------------------------------------------

### renderView

    public void renderView(javax.faces.context.FacesContext context,
                           javax.faces.component.UIViewRoot view)
                    throws IOException,
                           javax.faces.FacesException

If the Struts application has set a `Locale`, pass it on to JSF prior to delegating the actual rendering.

**Specified by:**  
`renderView` in class `javax.faces.application.ViewHandler`

<!-- -->

**Parameters:**  
`context` - `FacesContext` for the current request

`view` - `UIViewRoot` to be rendered

**Throws:**  
`IOException`

`javax.faces.FacesException`

------------------------------------------------------------------------

### calculateLocale

    public Locale calculateLocale(javax.faces.context.FacesContext context)

**Specified by:**  
`calculateLocale` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### calculateRenderKitId

    public String calculateRenderKitId(javax.faces.context.FacesContext context)

**Specified by:**  
`calculateRenderKitId` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### createView

    public javax.faces.component.UIViewRoot createView(javax.faces.context.FacesContext context,
                                                       String viewId)

**Specified by:**  
`createView` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### getActionURL

    public String getActionURL(javax.faces.context.FacesContext context,
                               String viewId)

**Specified by:**  
`getActionURL` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### getResourceURL

    public String getResourceURL(javax.faces.context.FacesContext context,
                                 String viewId)

**Specified by:**  
`getResourceURL` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### restoreView

    public javax.faces.component.UIViewRoot restoreView(javax.faces.context.FacesContext context,
                                                        String viewId)

**Specified by:**  
`restoreView` in class `javax.faces.application.ViewHandler`

------------------------------------------------------------------------

### writeState

    public void writeState(javax.faces.context.FacesContext context)
                    throws IOException

**Specified by:**  
`writeState` in class `javax.faces.application.ViewHandler`

<!-- -->

**Throws:**  
`IOException`

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
<td align="left"><a href="class-use/ViewHandlerImpl.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/application/PropertyResolverImpl.html.md" title="class in org.apache.struts.faces.application"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/application/ViewHandlerImpl.html"><strong>FRAMES</strong></a>    <a href="ViewHandlerImpl.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.faces.application.ViewHandler">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
