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
<td align="left"><a href="class-use/EvalHelper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/utils/EvalHelper.html"><strong>FRAMES</strong></a>    <a href="EvalHelper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.utils
 Class EvalHelper
--------------------------------

    java.lang.Object
      org.apache.strutsel.taglib.utils.EvalHelper

------------------------------------------------------------------------

    public final class EvalHelper

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

This class is used in the `evaluateExpressions` method of each Tag class. It is used to process the original attribute value through the JSTL EL engine to produce an evaluated value. It provides functions to evaluate the expression assuming it is an Object, String, Integer, or Boolean result.

------------------------------------------------------------------------

<span id="method_summary"></span>

**Method Summary**

`static Object`

` eval(String attrName, String attrValue, Tag tagObject, PageContext pageContext)`
           Evaluates the attribute value in the JSTL EL engine, returning the raw Object value of the evaluated expression.

`static Boolean`

` evalBoolean(String attrName, String attrValue, Tag tagObject, PageContext pageContext)`
           Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is an Boolean object.

`static Integer`

` evalInteger(String attrName, String attrValue, Tag tagObject, PageContext pageContext)`
           Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is an Integer object.

`static String`

` evalString(String attrName, String attrValue, Tag tagObject, PageContext pageContext)`
           Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is a String object.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="method_detail"></span>

**Method Detail**

### eval

    public static Object eval(String attrName,
                              String attrValue,
                              Tag tagObject,
                              PageContext pageContext)
                       throws JspException

Evaluates the attribute value in the JSTL EL engine, returning the raw Object value of the evaluated expression. If the original expression is null, or the resulting value is null, it will return null.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### evalString

    public static String evalString(String attrName,
                                    String attrValue,
                                    Tag tagObject,
                                    PageContext pageContext)
                             throws JspException

Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is a String object. If the original expression is null, or the resulting value is null, it will return null.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### evalInteger

    public static Integer evalInteger(String attrName,
                                      String attrValue,
                                      Tag tagObject,
                                      PageContext pageContext)
                               throws JspException

Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is an Integer object. If the original expression is null, or the resulting value is null, it will return null.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### evalBoolean

    public static Boolean evalBoolean(String attrName,
                                      String attrValue,
                                      Tag tagObject,
                                      PageContext pageContext)
                               throws JspException

Evaluates the attribute value in the JSTL EL engine, assuming the resulting value is an Boolean object. If the original expression is null, or the resulting value is null, it will return null.

**Throws:**  
`JspException`

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
<td align="left"><a href="class-use/EvalHelper.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/utils/EvalHelper.html"><strong>FRAMES</strong></a>    <a href="EvalHelper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | CONSTR | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | CONSTR | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
