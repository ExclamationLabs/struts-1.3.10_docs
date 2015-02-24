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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts.faces.taglib**

<span id="org.apache.struts.faces.taglib.JavascriptValidatorTag"></span>

**Class [org.apache.struts.faces.taglib.JavascriptValidatorTag](org/apache/struts/faces/taglib/JavascriptValidatorTag.html.md "class in org.apache.struts.faces.taglib") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### formName

    String formName

The name of the form that corresponds with the action name in struts-config.xml. Specifying a form name places a \<script\> \</script\> around the javascript.

------------------------------------------------------------------------

### page

    int page

The current page number of a multi-part form. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### methodName

    String methodName

This will be used as is for the JavaScript validation method name if it has a value. This is the method name of the main JavaScript method that the form calls to perform validations.

------------------------------------------------------------------------

### staticJavascript

    String staticJavascript

The static JavaScript methods will only be printed if this is set to "true".

------------------------------------------------------------------------

### dynamicJavascript

    String dynamicJavascript

The dynamic JavaScript objects will only be generated if this is set to "true".

------------------------------------------------------------------------

### src

    String src

The src attribute for.html.md script element (used to include an external script resource). The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

###.html.mdComment

    String.html.mdComment

The JavaScript methods will enclosed with.html.md comments if this is set to "true".

------------------------------------------------------------------------

### cdata

    String cdata

Hide JavaScript methods in a CDATA section for XHTML when "true".

------------------------------------------------------------------------

###.html.mdBeginComment

    String.html.mdBeginComment

------------------------------------------------------------------------

###.html.mdEndComment

    String.html.mdEndComment

------------------------------------------------------------------------

### formClientId

    String formClientId

<span id="org.apache.struts.faces.taglib.LoadMessagesTag"></span>

**Class [org.apache.struts.faces.taglib.LoadMessagesTag](org/apache/struts/faces/taglib/LoadMessagesTag.html.md "class in org.apache.struts.faces.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### messages

    String messages

The name of the `MessageResources` to expose, or `null` for the default `MessageResources` for this application module.

------------------------------------------------------------------------

### var

    String var

The request attribute key under which a `Map` will be exposed.

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
