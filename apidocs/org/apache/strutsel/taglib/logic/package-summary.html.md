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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/package-summary.html"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/tiles/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.strutsel.taglib.logic
----------------------------------------

The "struts-logic-el" tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management.

**See:**
           [**Description**](#package_description)

**Class Summary**

**[ELForwardTag](../../../../../org/apache/strutsel/taglib/logic/ELForwardTag.html.md "class in org.apache.strutsel.taglib.logic")**

Perform a forward or redirect to a page that is looked up in the configuration information associated with our application.

**[ELForwardTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELForwardTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELForwardTag` class.

**[ELIterateTag](../../../../../org/apache/strutsel/taglib/logic/ELIterateTag.html.md "class in org.apache.strutsel.taglib.logic")**

Custom tag that iterates the elements of a collection, which can be either an attribute or the property of an attribute.

**[ELIterateTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELIterateTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.bean.ELIterateTag` class.

**[ELMatchTag](../../../../../org/apache/strutsel/taglib/logic/ELMatchTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evalute the nested body content of this tag if the specified value is a substring of the specified variable.

**[ELMatchTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELMatchTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELMatchTag` class.

**[ELMessagesNotPresentTag](../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evalute to `false` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

**[ELMessagesNotPresentTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELMessagesNotPresentTag` class.

**[ELMessagesPresentTag](../../../../../org/apache/strutsel/taglib/logic/ELMessagesPresentTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evalute to `true` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

**[ELMessagesPresentTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELMessagesPresentTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELMessagesPresentTag` class.

**[ELNotMatchTag](../../../../../org/apache/strutsel/taglib/logic/ELNotMatchTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evalute the nested body content of this tag if the specified value is a substring of the specified variable.

**[ELNotMatchTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELNotMatchTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELNotMatchTag` class.

**[ELNotPresentTag](../../../../../org/apache/strutsel/taglib/logic/ELNotPresentTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evaluates the nested body content of this tag if the specified value is not present for this request.

**[ELNotPresentTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELNotPresentTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELNotPresentTag` class.

**[ELPresentTag](../../../../../org/apache/strutsel/taglib/logic/ELPresentTag.html.md "class in org.apache.strutsel.taglib.logic")**

Evaluates the nested body content of this tag if the specified value is present for this request.

**[ELPresentTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELPresentTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELPresentTag` class.

**[ELRedirectTag](../../../../../org/apache/strutsel/taglib/logic/ELRedirectTag.html.md "class in org.apache.strutsel.taglib.logic")**

Generate a URL-encoded redirect to the specified URI.

**[ELRedirectTagBeanInfo](../../../../../org/apache/strutsel/taglib/logic/ELRedirectTagBeanInfo.html.md "class in org.apache.strutsel.taglib.logic")**

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELRedirectTag` class.

 

<span id="package_description"></span>

Package org.apache.strutsel.taglib.logic Description
----------------------------------------------------

The "struts-logic-el" tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management.

 <span id="doc.Description"></span>

[[Introduction]](#doc.Intro) [[Logic-EL Functionality]](#doc.Functionality) [[Logic-EL Examples]](#doc.Examples)

------------------------------------------------------------------------

<span id="doc.Intro"></span>

### Introduction

The functionality of this tag library is entirely provided by the base "struts-logic" tag library in the Struts distribution. This derived tag library, "struts-logic-el", only provides a different way to evaluate attribute values, which is using the JavaServer Pages Standard Tag Library expression language engine, or the "JSTL EL" for short.

In general, the tags provided in the "struts-logic-el" library are a direct mapping from the "struts-logic" tag library. However, there are several tags in the base Struts tag library which were not "ported" to the "struts-logic-el" tag library, as it was determined that all of their functionality was provided by the JSTL. Information about these "non-ported" tags is provided in the information for the "org.apache.strutsel" package.

In addition, specific to the "struts-logic-el" library, two tags in this library have one additional attribute over their counterpart in the base Struts tag library. These tags are the `match` and `notMatch` tags, and the additional attribute is named `expr`, which is a value intended to be evaluated by the JSTL EL engine. More details about these tags and their attributes is provided in more detailed documentation about the package and its tags.

<span id="doc.Functionality"></span>

### Logic-EL Functionality

The functionality of the "logic-el" tags can be almost entirely understood from the documentation of the "struts-logic" base tag library. The only exception is the new attribute added to the `match` and `notMatch` tags, being the `expr` attribute.

The `match` and `notMatch` tags provide the ability to check to see whether a specific value is (or is not) a substring of a value obtained from either a cookie, request header, request parameter, or bean property. The addition of the `expr` attribute allows the obtained value to come from an arbitrary expression language value.

<span id="doc.Examples"></span>

### Logic-EL Examples

The following are discrete examples of uses of the "logic-el" tags, in no paticular order, but emphasizing the use of JSTL EL values as attribute values.

*Example:*

        <logic-el:forward name="${forwardName}"/>

*Example:*

        <%-- Iterates through all HTTP headers. --%>
        <logic-el:iterate id="item" collection="${header}">
        <tr>
        <td><c:out value="${item}.key"/></td>
        <td><c:out value="${item}.value"/></td>
        </tr>
        </logic-el:iterate>

*Example:*

        <logic-el:match cookie="${cookieName}" value="${cookieValue}">
        Match succeeded.
        </logic-el:match>

*Example:*

        <logic-el:match expr='${hash["foo"]}' value="${matchValue}">
        Match succeeded.
        </logic-el:match>

*Example:*

        <logic-el:messagesPresent property="${messageKey}">
        Message found.
        </logic-el:messagesPresent>

*Example:*

        <logic-el:redirect href="http://localhost:${portnum}/factory" />




------------------------------------------------------------------------





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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib.html.md/package-summary.html"><strong>PREV PACKAGE</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/tiles/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>




------------------------------------------------------------------------

    Copyright © 2000-2008 Apache Software Foundation. All Rights Reserved.


