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
<td align="left"><a href="../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/logic//class-useConditionalTagBase.html"><strong>FRAMES</strong></a>    <a href="ConditionalTagBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.taglib.logic.ConditionalTagBase**
----------------------------------------------------

Packages that use [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic")

[**org.apache.struts.taglib.logic**](#org.apache.struts.taglib.logic)

The "struts-logic" tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management. 

[**org.apache.struts.taglib.nested.logic**](#org.apache.struts.taglib.nested.logic)

The nested.html.md tags extend the `org.apache.struts.taglib.logic` tags to allow them to relate to each other in a nested nature. 

[**org.apache.strutsel.taglib.logic**](#org.apache.strutsel.taglib.logic)

The "struts-logic-el" tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management. 

 

<span id="org.apache.struts.taglib.logic"></span>

Uses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.struts.taglib.logic](../../../../../../org/apache/struts/taglib/logic/package-summary.html)

 

Subclasses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.struts.taglib.logic](../../../../../../org/apache/struts/taglib/logic/package-summary.html)

` class`

`CompareTagBase`
           Abstract base class for comparison tags.

` class`

`EmptyTag`
           Evalute the nested body content of this tag if the specified value is empty for this request.

` class`

`EqualTag`
           Evaluate the nested body content of this tag if the specified variable and value are equal.

` class`

`GreaterEqualTag`
           Evaluate the nested body content of this tag if the specified variable is greater than or equal to the specified value.

` class`

`GreaterThanTag`
           Evaluate the nested body content of this tag if the specified variable is greater than the specified value.

` class`

`LessEqualTag`
           Evaluate the nested body content of this tag if the specified variable is less than or equal to the specified value.

` class`

`LessThanTag`
           Evaluate the nested body content of this tag if the specified variable is less than the specified value.

` class`

`MatchTag`
           Evalute the nested body content of this tag if the specified value is a substring of the specified variable.

` class`

`MessagesNotPresentTag`
           Evalute the nested body content of this tag if the specified value is not present for this request.

` class`

`MessagesPresentTag`
           Evalute to `true` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

` class`

`NotEmptyTag`
           Evalute the nested body content of this tag if the specified value is not empty for this request.

` class`

`NotEqualTag`
           Evaluate the nested body content of this tag if the specified variable and value are not equal.

` class`

`NotMatchTag`
           Evalute the nested body content of this tag if the specified value is not a substring of the specified variable.

` class`

`NotPresentTag`
           Evalute the nested body content of this tag if the specified value is not present for this request.

` class`

`PresentTag`
           Evalute the nested body content of this tag if the specified value is present for this request.

 

<span id="org.apache.struts.taglib.nested.logic"></span>

Uses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.struts.taglib.nested.logic](../../../../../../org/apache/struts/taglib/nested/logic/package-summary.html)

 

Subclasses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.struts.taglib.nested.logic](../../../../../../org/apache/struts/taglib/nested/logic/package-summary.html)

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

`NestedLessEqualTag`
           NestedLessEqualTag.

` class`

`NestedLessThanTag`
           NestedLessThanTag.

` class`

`NestedMatchTag`
           NestedMatchTag.

` class`

`NestedMessagesNotPresentTag`
           NestedMessagesNotPresentTag.

` class`

`NestedMessagesPresentTag`
           NestedMessagesPresentTag.

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

 

<span id="org.apache.strutsel.taglib.logic"></span>

Uses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.strutsel.taglib.logic](../../../../../../org/apache/strutsel/taglib/logic/package-summary.html)

 

Subclasses of [ConditionalTagBase](../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") in [org.apache.strutsel.taglib.logic](../../../../../../org/apache/strutsel/taglib/logic/package-summary.html)

` class`

`ELMatchTag`
           Evalute the nested body content of this tag if the specified value is a substring of the specified variable.

` class`

`ELMessagesNotPresentTag`
           Evalute to `false` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

` class`

`ELMessagesPresentTag`
           Evalute to `true` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

` class`

`ELNotMatchTag`
           Evalute the nested body content of this tag if the specified value is a substring of the specified variable.

` class`

`ELNotPresentTag`
           Evaluates the nested body content of this tag if the specified value is not present for this request.

` class`

`ELPresentTag`
           Evaluates the nested body content of this tag if the specified value is present for this request.

 

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
<td align="left"><a href="../../../../../../org/apache/struts/taglib/logic/ConditionalTagBase.html.md" title="class in org.apache.struts.taglib.logic"><strong>Class</strong></a> </td>
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
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/logic//class-useConditionalTagBase.html"><strong>FRAMES</strong></a>    <a href="ConditionalTagBase.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
