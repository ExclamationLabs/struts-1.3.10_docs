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
<td align="left"><a href="class-use/PutListTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutListTag.html"><strong>FRAMES</strong></a>    <a href="PutListTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib
 Class PutListTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.PutListTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [AddTagParent](../../../../../org/apache/struts/tiles/taglib/AddTagParent.html "interface in org.apache.struts.tiles.taglib"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Direct Known Subclasses:**  
[ELPutListTag](../../../../../org/apache/strutsel/taglib/tiles/ELPutListTag.html.md "class in org.apache.strutsel.taglib.tiles")

------------------------------------------------------------------------

    public class PutListTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

implements [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib"), [AddTagParent](../../../../../org/apache/struts/tiles/taglib/AddTagParent.html "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib")

PutList tag implementation.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.PutListTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.ComponentConstants"></span>

| **Fields inherited from interface org.apache.struts.tiles.taglib.[ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` COMPONENT_CONTEXT,  COMPONENT_SCOPE,  EXCEPTION_KEY,  LOCALE_KEY`                                                                                                                                          |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.IterationTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_AGAIN`                                                                                                                                                                                                               |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` PutListTag()`                 
            Default constructor.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addElement(Object value)`
           Set property.

` int`

` doEndTag()`
           Do end tag.

` int`

` doStartTag()`
           Do start tag.

`protected  PutListTagParent`

` findEnclosingParent()`
           Find enclosing parent tag accepting this tag.

` List`

` getList()`
           Get list defined in tag.

` String`

` getName()`
           Get property.

` String`

` getRole()`
           Get role attribute.

` void`

` processNestedTag(AddTag nestedTag)`
           Process nested &lg;add\> tag.

` void`

` processNestedTag(PutListTag nestedTag)`
           Process nested &lg;putList\> tag.

` void`

` release()`
           Release all allocated resources.

`protected  void`

` releaseInternal()`
           Release all internal resources.

` void`

` setName(String name)`
           Set property.

` void`

` setRole(String role)`
           Set role attribute.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### PutListTag

    public PutListTag()

Default constructor.

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

------------------------------------------------------------------------

### releaseInternal

    protected void releaseInternal()

Release all internal resources.

------------------------------------------------------------------------

### setName

    public void setName(String name)

Set property.

------------------------------------------------------------------------

### getName

    public String getName()

Get property.

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Set role attribute.

**Parameters:**  
`role` - The role the user must be in to store content.

------------------------------------------------------------------------

### getRole

    public String getRole()

Get role attribute.

------------------------------------------------------------------------

### getList

    public List getList()

Get list defined in tag.

------------------------------------------------------------------------

### addElement

    public void addElement(Object value)

Set property.

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(PutListTag nestedTag)
                          throws JspException

Process nested &lg;putList\> tag. Method calls by nested &lg;putList\> tags. Nested list is added to current list. If role is defined, nested attribute is wrapped into an untypped definition containing attribute value and role.

**Specified by:**  
` processNestedTag` in interface `PutListTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested PutTag defining the attribute.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(AddTag nestedTag)
                          throws JspException

Process nested &lg;add\> tag. Method calls by nested &lg;add\> tags. Nested attribute is added to current list. If role is defined, nested attribute is wrapped into an untypped definition containing attribute value and role.

**Specified by:**  
` processNestedTag` in interface `AddTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested to process.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Do start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Do end tag.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### findEnclosingParent

    protected PutListTagParent findEnclosingParent()
                                            throws JspException

Find enclosing parent tag accepting this tag.

**Throws:**  
`JspException` - If we can't find an appropriate enclosing tag.

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
<td align="left"><a href="class-use/PutListTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.TagHandler.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutListTag.html"><strong>FRAMES</strong></a>    <a href="PutListTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
