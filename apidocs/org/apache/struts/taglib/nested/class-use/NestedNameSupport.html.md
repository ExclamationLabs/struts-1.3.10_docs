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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md" title="interface in org.apache.struts.taglib.nested"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested//class-useNestedNameSupport.html"><strong>FRAMES</strong></a>    <a href="NestedNameSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Interface
 org.apache.struts.taglib.nested.NestedNameSupport**
----------------------------------------------------

Packages that use [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested")

[**org.apache.struts.taglib.nested**](#org.apache.struts.taglib.nested)

Nested tags & supporting classes extend the base struts tags to allow them to relate to each other in a nested nature. 

[**org.apache.struts.taglib.nested.bean**](#org.apache.struts.taglib.nested.bean)

The nested bean tags extend the `org.apache.struts.taglib.bean` tags to allow them to relate to each other in a nested nature. 

[**org.apache.struts.taglib.nested.html.md**](#org.apache.struts.taglib.nested.html)

The nested.html.md tags extend the `org.apache.struts.taglib.html` tags to allow them to relate to each other in a nested nature. 

[**org.apache.struts.taglib.nested.logic**](#org.apache.struts.taglib.nested.logic)

The nested.html.md tags extend the `org.apache.struts.taglib.logic` tags to allow them to relate to each other in a nested nature. 

 

<span id="org.apache.struts.taglib.nested"></span>

Uses of [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested") in [org.apache.struts.taglib.nested](../../../../../../org/apache/struts/taglib/nested/package-summary.html)

 

Subinterfaces of [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested") in [org.apache.struts.taglib.nested](../../../../../../org/apache/struts/taglib/nested/package-summary.html)

` interface`

`NestedParentSupport`
           This interface is so managing classes of the nested tag can identify a tag as a parent tag that other tags retrieve nested properties from.

 

Classes in [org.apache.struts.taglib.nested](../../../../../../org/apache/struts/taglib/nested/package-summary.html.md) that implement [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested")

` class`

`NestedPropertyTag`
           NestedPropertyTag.

` class`

`NestedRootTag`
           NestedRootTag.

 

Methods in [org.apache.struts.taglib.nested](../../../../../../org/apache/struts/taglib/nested/package-summary.html.md) with parameters of type [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested")

`static String`

`NestedPropertyHelper.getCurrentName(HttpServletRequest request, NestedNameSupport nested)`
           Returns the bean name from the request object that the properties are nesting against.

 

<span id="org.apache.struts.taglib.nested.bean"></span>

Uses of [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested") in [org.apache.struts.taglib.nested.bean](../../../../../../org/apache/struts/taglib/nested/bean/package-summary.html)

 

Classes in [org.apache.struts.taglib.nested.bean](../../../../../../org/apache/struts/taglib/nested/bean/package-summary.html.md) that implement [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested")

` class`

`NestedDefineTag`
           NestedDefineTag.

` class`

`NestedMessageTag`
           NestedWriteTag.

` class`

`NestedSizeTag`
           NestedSizeTag.

` class`

`NestedWriteTag`
           NestedWriteTag.

 

<span id="org.apache.struts.taglib.nested.html.md"></span>

Uses of [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested") in [org.apache.struts.taglib.nested.html](../../../../../../org/apache/struts/taglib/nested/html/package-summary.html)

 

Classes in [org.apache.struts.taglib.nested.html.md](../../../../../../org/apache/struts/taglib/nested/html/package-summary.html) that implement [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested")

` class`

`NestedCheckboxTag`
           NestedCheckboxTag.

` class`

`NestedFileTag`
           NestedFileTag.

` class`

`NestedFormTag`
           NestedFormTag.

` class`

`NestedHiddenTag`
           NestedHiddenTag.

` class`

`NestedImgTag`
           NestedImgTag, renders the nested version of the tag.

` class`

`NestedLinkTag`
           NestedLinkTag.

` class`

`NestedMultiboxTag`
           NestedMultiboxTag.

` class`

`NestedOptionsCollectionTag`
           NestedOptionsCollectionTag.

` class`

`NestedOptionsTag`
           NestedOptionsTag.

` class`

`NestedPasswordTag`
           NestedPasswordTag.

` class`

`NestedRadioTag`
           NestedRadioTag.

` class`

`NestedSelectTag`
           NestedSelectTag.

` class`

`NestedTextareaTag`
           NestedTextareaTag.

` class`

`NestedTextTag`
           NestedTextTag.

 

<span id="org.apache.struts.taglib.nested.logic"></span>

Uses of [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md "interface in org.apache.struts.taglib.nested") in [org.apache.struts.taglib.nested.logic](../../../../../../org/apache/struts/taglib/nested/logic/package-summary.html)

 

Classes in [org.apache.struts.taglib.nested.logic](../../../../../../org/apache/struts/taglib/nested/logic/package-summary.html.md) that implement [NestedNameSupport](../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html "interface in org.apache.struts.taglib.nested")

` class`

`NestedEmptyTag`
           NestedEmptyTag.

` class`

`NestedEqualTag`
           NestedEqualTag.

` class`

`NestedGreaterEqualTag`
           NestedGreaterEqualTag.

` class`

`NestedGreaterThanTag`
           NestedGreaterThanTag.

` class`

`NestedIterateTag`
           NestedIterateTag.

` class`

`NestedLessEqualTag`
           NestedLessEqualTag.

` class`

`NestedLessThanTag`
           NestedLessThanTag.

` class`

`NestedMatchTag`
           NestedMatchTag.

` class`

`NestedNotEmptyTag`
           NestedNotEmptyTag.

` class`

`NestedNotEqualTag`
           NestedNotEqualTag.

` class`

`NestedNotMatchTag`
           NestedNotMatchTag.

` class`

`NestedNotPresentTag`
           NestedNotPresentTag.

` class`

`NestedPresentTag`
           NestedPresentTag.

 

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../../org/apache/struts/taglib/nested/NestedNameSupport.html.md" title="interface in org.apache.struts.taglib.nested"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested//class-useNestedNameSupport.html"><strong>FRAMES</strong></a>    <a href="NestedNameSupport.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
