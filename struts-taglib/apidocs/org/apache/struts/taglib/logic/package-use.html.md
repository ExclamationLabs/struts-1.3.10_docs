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
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
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
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.taglib.logic**
---------------------------------

Packages that use [org.apache.struts.taglib.logic](../../../../../org/apache/struts/taglib/logic/package-summary.html.md)

[**org.apache.struts.taglib.logic**](#org.apache.struts.taglib.logic)

The "struts-logic" tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management. 

[**org.apache.struts.taglib.nested.bean**](#org.apache.struts.taglib.nested.bean)

The nested bean tags extend the `org.apache.struts.taglib.bean` tags to allow them to relate to each other in a nested nature. 

[**org.apache.struts.taglib.nested.logic**](#org.apache.struts.taglib.nested.logic)

The nested.html.md tags extend the `org.apache.struts.taglib.logic` tags to allow them to relate to each other in a nested nature. 

 

<span id="org.apache.struts.taglib.logic"></span>

| Classes in [org.apache.struts.taglib.logic](../../../../../org/apache/struts/taglib/logic/package-summary.html.md) used by [org.apache.struts.taglib.logic](../../../../../org/apache/struts/taglib/logic/package-summary.html)                      |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**CompareTagBase**](../../../../../org/apache/struts/taglib/logic/class-use/CompareTagBase.html.md#org.apache.struts.taglib.logic)**                                                                                                              
            Abstract base class for comparison tags.                                                                                                                                                                                                |
| **[**ConditionalTagBase**](../../../../../org/apache/struts/taglib/logic/class-use/ConditionalTagBase.html.md#org.apache.struts.taglib.logic)**                                                                                                      
            Abstract base class for the various conditional evaluation tags.                                                                                                                                                                        |
| **[**EmptyTag**](../../../../../org/apache/struts/taglib/logic/class-use/EmptyTag.html.md#org.apache.struts.taglib.logic)**                                                                                                                          
            Evalute the nested body content of this tag if the specified value is empty for this request.                                                                                                                                           |
| **[**MatchTag**](../../../../../org/apache/struts/taglib/logic/class-use/MatchTag.html.md#org.apache.struts.taglib.logic)**                                                                                                                          
            Evalute the nested body content of this tag if the specified value is a substring of the specified variable.                                                                                                                            |
| **[**MessagesPresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/MessagesPresentTag.html.md#org.apache.struts.taglib.logic)**                                                                                                      
            Evalute to `true` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.  |
| **[**PresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/PresentTag.html.md#org.apache.struts.taglib.logic)**                                                                                                                      
            Evalute the nested body content of this tag if the specified value is present for this request.                                                                                                                                         |

 

<span id="org.apache.struts.taglib.nested.bean"></span>

| Classes in [org.apache.struts.taglib.logic](../../../../../org/apache/struts/taglib/logic/package-summary.html.md) used by [org.apache.struts.taglib.nested.bean](../../../../../org/apache/struts/taglib/nested/bean/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**IterateTei**](../../../../../org/apache/struts/taglib/logic/class-use/IterateTei.html.md#org.apache.struts.taglib.nested.bean)**                                                                                                       
            Implementation of `TagExtraInfo` for the **iterate** tag, identifying the scripting object(s) to be made visible.                                                                                                              |

 

<span id="org.apache.struts.taglib.nested.logic"></span>

| Classes in [org.apache.struts.taglib.logic](../../../../../org/apache/struts/taglib/logic/package-summary.html.md) used by [org.apache.struts.taglib.nested.logic](../../../../../org/apache/struts/taglib/nested/logic/package-summary.html)        |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**CompareTagBase**](../../../../../org/apache/struts/taglib/logic/class-use/CompareTagBase.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                       
            Abstract base class for comparison tags.                                                                                                                                                                                                |
| **[**ConditionalTagBase**](../../../../../org/apache/struts/taglib/logic/class-use/ConditionalTagBase.html.md#org.apache.struts.taglib.nested.logic)**                                                                                               
            Abstract base class for the various conditional evaluation tags.                                                                                                                                                                        |
| **[**EmptyTag**](../../../../../org/apache/struts/taglib/logic/class-use/EmptyTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                                   
            Evalute the nested body content of this tag if the specified value is empty for this request.                                                                                                                                           |
| **[**EqualTag**](../../../../../org/apache/struts/taglib/logic/class-use/EqualTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                                   
            Evaluate the nested body content of this tag if the specified variable and value are equal.                                                                                                                                             |
| **[**GreaterEqualTag**](../../../../../org/apache/struts/taglib/logic/class-use/GreaterEqualTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                     
            Evaluate the nested body content of this tag if the specified variable is greater than or equal to the specified value.                                                                                                                 |
| **[**GreaterThanTag**](../../../../../org/apache/struts/taglib/logic/class-use/GreaterThanTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                       
            Evaluate the nested body content of this tag if the specified variable is greater than the specified value.                                                                                                                             |
| **[**IterateTag**](../../../../../org/apache/struts/taglib/logic/class-use/IterateTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                               
            Custom tag that iterates the elements of a collection, which can be either an attribute or the property of an attribute.                                                                                                                |
| **[**IterateTei**](../../../../../org/apache/struts/taglib/logic/class-use/IterateTei.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                               
            Implementation of `TagExtraInfo` for the **iterate** tag, identifying the scripting object(s) to be made visible.                                                                                                                       |
| **[**LessEqualTag**](../../../../../org/apache/struts/taglib/logic/class-use/LessEqualTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                           
            Evaluate the nested body content of this tag if the specified variable is less than or equal to the specified value.                                                                                                                    |
| **[**LessThanTag**](../../../../../org/apache/struts/taglib/logic/class-use/LessThanTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                             
            Evaluate the nested body content of this tag if the specified variable is less than the specified value.                                                                                                                                |
| **[**MatchTag**](../../../../../org/apache/struts/taglib/logic/class-use/MatchTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                                   
            Evalute the nested body content of this tag if the specified value is a substring of the specified variable.                                                                                                                            |
| **[**MessagesNotPresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/MessagesNotPresentTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                         
            Evalute the nested body content of this tag if the specified value is not present for this request.                                                                                                                                     |
| **[**MessagesPresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/MessagesPresentTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                               
            Evalute to `true` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.  |
| **[**NotEmptyTag**](../../../../../org/apache/struts/taglib/logic/class-use/NotEmptyTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                             
            Evalute the nested body content of this tag if the specified value is not empty for this request.                                                                                                                                       |
| **[**NotEqualTag**](../../../../../org/apache/struts/taglib/logic/class-use/NotEqualTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                             
            Evaluate the nested body content of this tag if the specified variable and value are not equal.                                                                                                                                         |
| **[**NotMatchTag**](../../../../../org/apache/struts/taglib/logic/class-use/NotMatchTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                             
            Evalute the nested body content of this tag if the specified value is not a substring of the specified variable.                                                                                                                        |
| **[**NotPresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/NotPresentTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                         
            Evalute the nested body content of this tag if the specified value is not present for this request.                                                                                                                                     |
| **[**PresentTag**](../../../../../org/apache/struts/taglib/logic/class-use/PresentTag.html.md#org.apache.struts.taglib.nested.logic)**                                                                                                               
            Evalute the nested body content of this tag if the specified value is present for this request.                                                                                                                                         |

 

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
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
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
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
