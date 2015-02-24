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
<td align="left"><a href="class-use/SizeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/ResourceTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/SizeTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/SizeTag.html"><strong>FRAMES</strong></a>    <a href="SizeTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib.bean
 Class SizeTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.SizeTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedSizeTag](../../../../../org/apache/struts/taglib/nested/bean/NestedSizeTag.html.md "class in org.apache.struts.taglib.nested.bean")

------------------------------------------------------------------------

    public class SizeTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Define a scripting variable that will contain the number of elements found in a specified array, Collection, or Map.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.bean.SizeTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Object`

` collection`
           The actual collection to be counted.

`protected  String`

`id`
           The name of the scripting variable that will be exposed as a page scope attribute.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

`name`
           The name of the bean owning the property to be counted.

`protected  String`

` property`
           The name of the property to be retrieved.

`protected  String`

`scope`
           The scope within which to search for the specified bean.

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pageContext`                                                                                                                                                                                                           |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.IterationTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_AGAIN`                                                                                                                                                                                                               |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` SizeTag()`            
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Retrieve the required property and expose it as a scripting variable.

` Object`

` getCollection()`
            

` String`

` getId()`
            

` String`

` getName()`
            

` String`

` getProperty()`
            

` String`

` getScope()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setCollection(Object collection)`
            

` void`

` setId(String id)`
            

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
            

` void`

` setScope(String scope)`
            

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, findAncestorWithClass, getParent, getValue, getValues, removeValue, setPageContext, setParent, setValue`                                                                                         |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="collection"></span>

### collection

    protected Object collection

The actual collection to be counted.

------------------------------------------------------------------------

<span id="id"></span>

### id

    protected String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the bean owning the property to be counted.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The name of the property to be retrieved.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope within which to search for the specified bean.

<span id="constructor_detail"></span>

**Constructor Detail**

### SizeTag

    public SizeTag()

<span id="method_detail"></span>

**Method Detail**

### getCollection

    public Object getCollection()

------------------------------------------------------------------------

### setCollection

    public void setCollection(Object collection)

------------------------------------------------------------------------

### getId

    public String getId()

**Overrides:**  
`getId` in class `TagSupport`

------------------------------------------------------------------------

### setId

    public void setId(String id)

**Overrides:**  
`setId` in class `TagSupport`

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getProperty

    public String getProperty()

------------------------------------------------------------------------

### setProperty

    public void setProperty(String property)

------------------------------------------------------------------------

### getScope

    public String getScope()

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Retrieve the required property and expose it as a scripting variable.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

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
<td align="left"><a href="class-use/SizeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/ResourceTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/SizeTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/SizeTag.html"><strong>FRAMES</strong></a>    <a href="SizeTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
