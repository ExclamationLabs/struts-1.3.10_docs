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
<td align="left"><a href="class-use/ResourceTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/ParameterTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/ResourceTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/ResourceTag.html"><strong>FRAMES</strong></a>    <a href="ResourceTag.html"><strong>NO FRAMES</strong></a>    
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
 Class ResourceTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.ResourceTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELResourceTag](../../../../../org/apache/strutsel/taglib/bean/ELResourceTag.html.md "class in org.apache.strutsel.taglib.bean")

------------------------------------------------------------------------

    public class ResourceTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Define a scripting variable based on the contents of the specified web application resource.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.bean.ResourceTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static int`

` BUFFER_SIZE`
           Buffer size to use when reading the input stream.

`protected  String`

`id`
           The name of the scripting variable that will be exposed as a page scope attribute.

`protected  String`

` input`
           Return an InputStream to the specified resource if this is non-null.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           The module-relative URI of the resource whose contents are to be exposed.

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
| ` ResourceTag()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Retrieve the required property and expose it as a scripting variable.

` String`

` getId()`
            

` String`

` getInput()`
            

` String`

` getName()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setId(String id)`
            

` void`

` setInput(String input)`
            

` void`

` setName(String name)`
            

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

<span id="BUFFER_SIZE"></span>

### BUFFER\_SIZE

    protected static final int BUFFER_SIZE

Buffer size to use when reading the input stream.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.taglib.bean.ResourceTag.BUFFER_SIZE)

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="id"></span>

### id

    protected String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

<span id="input"></span>

### input

    protected String input

Return an InputStream to the specified resource if this is non-null.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The module-relative URI of the resource whose contents are to be exposed.

<span id="constructor_detail"></span>

**Constructor Detail**

### ResourceTag

    public ResourceTag()

<span id="method_detail"></span>

**Method Detail**

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

### getInput

    public String getInput()

------------------------------------------------------------------------

### setInput

    public void setInput(String input)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

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
<td align="left"><a href="class-use/ResourceTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/ParameterTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/ResourceTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/ResourceTag.html"><strong>FRAMES</strong></a>    <a href="ResourceTag.html"><strong>NO FRAMES</strong></a>    
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
