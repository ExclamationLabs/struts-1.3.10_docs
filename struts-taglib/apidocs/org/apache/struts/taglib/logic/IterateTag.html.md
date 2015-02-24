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
<td align="left"><a href="class-use/IterateTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/GreaterThanTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/IterateTei.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/IterateTag.html"><strong>FRAMES</strong></a>    <a href="IterateTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.taglib.logic
 Class IterateTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.logic.IterateTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedIterateTag](../../../../../org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md "class in org.apache.struts.taglib.nested.logic")

------------------------------------------------------------------------

    public class IterateTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that iterates the elements of a collection, which can be either an attribute or the property of an attribute. The collection can be any of the following: an array of objects, an Enumeration, an Iterator, a Collection (which includes Lists, Sets and Vectors), or a Map (which includes Hashtables) whose elements will be iterated over.

**Version:**  
$Rev: 471754 $ $Date: 2004-11-03 14:20:47 -0500 (Wed, 03 Nov 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.logic.IterateTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Object`

` collection`
           The collection over which we will be iterating.

`protected  String`

`id`
           The name of the scripting variable to be exposed.

`protected  String`

` indexId`
           The name of the scripting variable to be exposed as the current index.

`protected  Iterator`

` iterator`
           Iterator of the elements of this collection, while we are actually running.

`protected  String`

` length`
           The length value or attribute name (\<=0 means no limit).

`protected  int`

` lengthCount`
           The number of elements we have already rendered.

`protected  int`

` lengthValue`
           The actual length value (calculated in the start tag).

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           The name of the collection or owning bean.

`protected  String`

` offset`
           The starting offset (zero relative).

`protected  int`

` offsetValue`
           The actual offset value (calculated in the start tag).

`protected  String`

` property`
           The property name containing the collection.

`protected  String`

` scope`
           The scope of the bean specified by the name property, if any.

`protected  boolean`

` started`
           Has this tag instance been started?

`protected  String`

` type`
           The Java class of each exposed element of the collection.

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bodyContent`                                                                                                                                                                                                                   |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pageContext`                                                                                                                                                                                                           |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_BUFFERED, EVAL_BODY_TAG`                                                                                                                                                                                   |

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
| ` IterateTag()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doAfterBody()`
           Make the next collection element available and loop, or finish the iterations if there are no more elements.

` int`

` doEndTag()`
           Clean up after processing this enumeration.

` int`

` doStartTag()`
           Construct an iterator for the specified collection, and begin looping through the body once per element.

` Object`

` getCollection()`
            

` String`

` getId()`
            

` int`

` getIndex()`
           Return the zero-relative index of the current iteration through the loop.

` String`

` getIndexId()`
            

` String`

` getLength()`
            

` String`

` getName()`
            

` String`

` getOffset()`
            

` String`

` getProperty()`
            

` String`

` getScope()`
            

` String`

` getType()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setCollection(Object collection)`
            

` void`

` setId(String id)`
            

` void`

` setIndexId(String indexId)`
            

` void`

` setLength(String length)`
            

` void`

` setName(String name)`
            

` void`

` setOffset(String offset)`
            

` void`

` setProperty(String property)`
            

` void`

` setScope(String scope)`
            

` void`

` setType(String type)`
            

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                                                     |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `findAncestorWithClass, getParent, getValue, getValues, removeValue, setPageContext, setParent, setValue`                                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Methods inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getParent, setPageContext, setParent`                                                                                                                                                                         |

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="iterator"></span>

### iterator

    protected Iterator iterator

Iterator of the elements of this collection, while we are actually running.

------------------------------------------------------------------------

<span id="lengthCount"></span>

### lengthCount

    protected int lengthCount

The number of elements we have already rendered.

------------------------------------------------------------------------

<span id="lengthValue"></span>

### lengthValue

    protected int lengthValue

The actual length value (calculated in the start tag).

------------------------------------------------------------------------

<span id="offsetValue"></span>

### offsetValue

    protected int offsetValue

The actual offset value (calculated in the start tag).

------------------------------------------------------------------------

<span id="started"></span>

### started

    protected boolean started

Has this tag instance been started?

------------------------------------------------------------------------

<span id="collection"></span>

### collection

    protected Object collection

The collection over which we will be iterating.

------------------------------------------------------------------------

<span id="id"></span>

### id

    protected String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

<span id="indexId"></span>

### indexId

    protected String indexId

The name of the scripting variable to be exposed as the current index.

------------------------------------------------------------------------

<span id="length"></span>

### length

    protected String length

The length value or attribute name (\<=0 means no limit).

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the collection or owning bean.

------------------------------------------------------------------------

<span id="offset"></span>

### offset

    protected String offset

The starting offset (zero relative).

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The property name containing the collection.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

<span id="type"></span>

### type

    protected String type

The Java class of each exposed element of the collection.

<span id="constructor_detail"></span>

**Constructor Detail**

### IterateTag

    public IterateTag()

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

### getIndex

    public int getIndex()

Return the zero-relative index of the current iteration through the loop. If you specify an `offset`, the first iteration through the loop will have that value; otherwise, the first iteration will return zero.

This property is read-only, and gives nested custom tags access to this information. Therefore, it is **only** valid in between calls to `doStartTag()` and `doEndTag()`.

------------------------------------------------------------------------

### getIndexId

    public String getIndexId()

------------------------------------------------------------------------

### setIndexId

    public void setIndexId(String indexId)

------------------------------------------------------------------------

### getLength

    public String getLength()

------------------------------------------------------------------------

### setLength

    public void setLength(String length)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getOffset

    public String getOffset()

------------------------------------------------------------------------

### setOffset

    public void setOffset(String offset)

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

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Construct an iterator for the specified collection, and begin looping through the body once per element.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doAfterBody

    public int doAfterBody()
                    throws JspException

Make the next collection element available and loop, or finish the iterations if there are no more elements.

**Specified by:**  
`doAfterBody` in interface `IterationTag`

**Overrides:**  
`doAfterBody` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Clean up after processing this enumeration.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

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
`release` in class `BodyTagSupport`

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
<td align="left"><a href="class-use/IterateTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/GreaterThanTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/logic/IterateTei.html" title="class in org.apache.struts.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/IterateTag.html"><strong>FRAMES</strong></a>    <a href="IterateTag.html"><strong>NO FRAMES</strong></a>    
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
