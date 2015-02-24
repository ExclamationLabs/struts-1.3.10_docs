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
<td align="left"><a href="class-use/ELMatchTagBeanInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELMatchTag.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELMatchTagBeanInfo.html"><strong>FRAMES</strong></a>    <a href="ELMatchTagBeanInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.logic
 Class ELMatchTagBeanInfo
--------------------------------

    java.lang.Object
      java.beans.SimpleBeanInfo
          org.apache.strutsel.taglib.logic.ELMatchTagBeanInfo

**All Implemented Interfaces:**  
[BeanInfo](http://java.sun.com/j2se/1.4.2/docs/api/java/beans/BeanInfo.html.md?is-external=true "class or interface in java.beans")

------------------------------------------------------------------------

    public class ELMatchTagBeanInfo

extends [SimpleBeanInfo](http://java.sun.com/j2se/1.4.2/docs/api/java/beans/SimpleBeanInfo.html.md?is-external=true "class or interface in java.beans")

This is the `BeanInfo` descriptor for the `org.apache.strutsel.taglib.logic.ELMatchTag` class. It is needed to override the default mapping of custom tag attribute names to class attribute names.

This is because the value of the unevaluated EL expression has to be kept separately from the evaluated value, which is stored in the base class. This is related to the fact that the JSP compiler can choose to reuse different tag instances if they received the same original attribute values, and the JSP compiler can choose to not re-call the setter methods, because it can assume the same values are already set.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_java.beans.BeanInfo"></span>

| **Fields inherited from interface java.beans.[BeanInfo](http://java.sun.com/j2se/1.4.2/docs/api/java/beans/BeanInfo.html.md?is-external=true "class or interface in java.beans")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ICON_COLOR_16x16, ICON_COLOR_32x32, ICON_MONO_16x16, ICON_MONO_32x32`                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ELMatchTagBeanInfo()` 
                          |

  <span id="method_summary"></span>

**Method Summary**

` PropertyDescriptor[]`

` getPropertyDescriptors()`
            

 <span id="methods_inherited_from_class_java.beans.SimpleBeanInfo"></span>

| **Methods inherited from class java.beans.[SimpleBeanInfo](http://java.sun.com/j2se/1.4.2/docs/api/java/beans/SimpleBeanInfo.html.md?is-external=true "class or interface in java.beans")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getAdditionalBeanInfo, getBeanDescriptor, getDefaultEventIndex, getDefaultPropertyIndex, getEventSetDescriptors, getIcon, getMethodDescriptors, loadImage`                              |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ELMatchTagBeanInfo

    public ELMatchTagBeanInfo()

<span id="method_detail"></span>

**Method Detail**

### getPropertyDescriptors

    public PropertyDescriptor[] getPropertyDescriptors()

**Specified by:**  
`getPropertyDescriptors` in interface `BeanInfo`

**Overrides:**  
`getPropertyDescriptors` in class `SimpleBeanInfo`

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
<td align="left"><a href="class-use/ELMatchTagBeanInfo.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELMatchTag.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELMatchTagBeanInfo.html"><strong>FRAMES</strong></a>    <a href="ELMatchTagBeanInfo.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
