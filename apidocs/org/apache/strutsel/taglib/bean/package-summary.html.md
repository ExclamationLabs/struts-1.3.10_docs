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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.strutsel.taglib.bean
---------------------------------------

The "struts-bean-el" tag library contains JSP custom tags useful in defining new beans (in any desired scope) from a variety of possible sources, as well as a tag to render a particular bean (or bean property) to the output response.

**See:**
           [**Description**](#package_description)

**Class Summary**

**[ELIncludeTag](../../../../../org/apache/strutsel/taglib/bean/ELIncludeTag.html.md "class in org.apache.strutsel.taglib.bean")**

Generate a URL-encoded include to the specified URI.

**[ELIncludeTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELIncludeTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELIncludeTag` class.

**[ELMessageTag](../../../../../org/apache/strutsel/taglib/bean/ELMessageTag.html.md "class in org.apache.strutsel.taglib.bean")**

Custom tag that retrieves an internationalized messages string (with optional parametric replacement) from the `ActionResources` object stored as a context attribute by our associated `ActionServlet` implementation.

**[ELMessageTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELMessageTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELMessageTag` class.

**[ELPageTag](../../../../../org/apache/strutsel/taglib/bean/ELPageTag.html.md "class in org.apache.strutsel.taglib.bean")**

Define a scripting variable that exposes the requested page context item as a scripting variable and a page scope bean.

**[ELPageTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELPageTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELPageTag` class.

**[ELResourceTag](../../../../../org/apache/strutsel/taglib/bean/ELResourceTag.html.md "class in org.apache.strutsel.taglib.bean")**

Define a scripting variable based on the contents of the specified web application resource.

**[ELResourceTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELResourceTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELResourceTag` class.

**[ELSizeTag](../../../../../org/apache/strutsel/taglib/bean/ELSizeTag.html.md "class in org.apache.strutsel.taglib.bean")**

Define a scripting variable that will contain the number of elements found in a specified array, Collection, or Map.

**[ELSizeTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELSizeTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELSizeTag` class.

**[ELStrutsTag](../../../../../org/apache/strutsel/taglib/bean/ELStrutsTag.html.md "class in org.apache.strutsel.taglib.bean")**

Define a scripting variable that exposes the requested Struts internal configuraton object.

**[ELStrutsTagBeanInfo](../../../../../org/apache/strutsel/taglib/bean/ELStrutsTagBeanInfo.html.md "class in org.apache.strutsel.taglib.bean")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELStrutsTag` class.

 

<span id="package_description"></span>

Package org.apache.strutsel.taglib.bean Description
---------------------------------------------------

The "struts-bean-el" tag library contains JSP custom tags useful in defining new beans (in any desired scope) from a variety of possible sources, as well as a tag to render a particular bean (or bean property) to the output response.

 <span id="doc.Description"></span>

[[Introduction]](#doc.Intro) [[Bean-EL Functionality]](#doc.Functionality) [[Bean-EL Examples]](#doc.Examples)

------------------------------------------------------------------------

<span id="doc.Intro"></span>

### Introduction

The functionality of this tag library is entirely provided by the base "struts-bean" tag library in the Struts distribution. This derived tag library, "struts-bean-el", only provides a different way to evaluate attribute values, which is using the JavaServer Pages Standard Tag Library expression language engine, or the "JSTL EL" for short.

In general, the tags provided in the "struts-bean-el" library are a direct mapping from the "struts-bean" tag library. However, there are several tags in the base Struts tag library which were not "ported" to the "struts-bean-el" tag library, as it was determined that all of their functionality was provided by the JSTL. Information about these "non-ported" tags is provided in the information for the "org.apache.strutsel" package.

<span id="doc.Functionality"></span>

### Bean-EL Functionality

The functionality of the "bean-el" tags can be almost entirely understood from the documentation of the "struts-bean" base tag library.

<span id="doc.Examples"></span>

### Bean-EL Examples

The following are discrete examples of uses of the "bean-el" tags, in no paticular order, but emphasizing the use of JSTL EL values as attribute values.

*Example:*

        <bean-el:message key="${messKey}" arg0="${arg}"/>

*Example:*

        <bean-el:resource id="var" name="${filename}" />

*Example:*

        <%-- Size of pagescope hash table --%>
        <bean-el:size id="pageScopeSize" collection="${pageScope}" />

*Example:*

        <bean-el:struts id="mapping" mapping="${actionName}" />

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
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/html/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/bean/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
