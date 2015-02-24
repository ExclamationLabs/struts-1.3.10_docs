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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedIterateTei.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md" title="class in org.apache.struts.taglib.nested.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/logic/NestedLessEqualTag.html" title="class in org.apache.struts.taglib.nested.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/logic/NestedIterateTei.html"><strong>FRAMES</strong></a>    <a href="NestedIterateTei.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.nested.logic
 Class NestedIterateTei
-------------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagExtraInfo
          org.apache.struts.taglib.logic.IterateTei
              org.apache.struts.taglib.nested.logic.NestedIterateTei

------------------------------------------------------------------------

    public class NestedIterateTei

extends [IterateTei](../../../../../../org/apache/struts/taglib/logic/IterateTei.html.md "class in org.apache.struts.taglib.logic")

NestedIterateTei Extending the original tag's tei class, so that we can make the "id" attribute optional, so that those who want to script can add it if they need it otherwise we can maintain the nice lean tag markup. TODO - Look at deleting this class. Potentially a pointless existance now that the super class is towing the line. Left alone because it's not hurting anything as-is. Note: When done, it requires pointing the tei reference in the struts-nested.tld to org.apache.struts.taglib.logic.IterateTei

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` NestedIterateTei()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` VariableInfo[]`

` getVariableInfo(TagData data)`
           Return information about the scripting variables to be created.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagExtraInfo"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagExtraInfo](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagExtraInfo.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getTagInfo, isValid, setTagInfo`                                                                                                                                                                                            |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### NestedIterateTei

    public NestedIterateTei()

<span id="method_detail"></span>

**Method Detail**

### getVariableInfo

    public VariableInfo[] getVariableInfo(TagData data)

Return information about the scripting variables to be created.

**Overrides:**  
` getVariableInfo` in class `IterateTei`

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/NestedIterateTei.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../../org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md" title="class in org.apache.struts.taglib.nested.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../../org/apache/struts/taglib/nested/logic/NestedLessEqualTag.html" title="class in org.apache.struts.taglib.nested.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/taglib/nested/logic/NestedIterateTei.html"><strong>FRAMES</strong></a>    <a href="NestedIterateTei.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
