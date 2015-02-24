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
<td align="left"><a href="class-use/OptionsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/OptionsCollectionTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/OptionTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/OptionsTag.html"><strong>FRAMES</strong></a>    <a href="OptionsTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.taglib.html.md
 Class OptionsTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.html.md.OptionsTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedOptionsTag](../../../../../org/apache/struts/taglib/nested.html.md/NestedOptionsTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class OptionsTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Tag for creating multiple \<select\> options from a collection. The associated values displayed to the user may optionally be specified by a second collection, or will be the same as the values themselves. Each collection may be an array of objects, a Collection, an Enumeration, an Iterator, or a Map. **NOTE** - This tag requires a Java2 (JDK 1.2 or later) platform.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.OptionsTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` collection`
           The name of the collection containing beans that have properties to provide both the values and the labels (identified by the `property` and `labelProperty` attributes).

`protected  boolean`

` filter`
           Should the label values be filtered for HTML sensitive characters?

`protected  String`

` labelName`
           The name of the bean containing the labels collection.

`protected  String`

` labelProperty`
           The bean property containing the labels collection.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           The name of the bean containing the values collection.

`protected  String`

` property`
           The name of the property to use to build the values collection.

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

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
| ` OptionsTag()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` addOption(StringBuffer sb, String value, String label, boolean matched)`
           Add an option element to the specified StringBuffer based on the specified parameters.

` int`

` doEndTag()`
           Process the end of this tag.

` int`

` doStartTag()`
           Process the start of this tag.

` String`

` getCollection()`
            

` boolean`

` getFilter()`
            

`protected  Iterator`

` getIterator(String name, String property)`
           Return an iterator for the option labels or values, based on our configured properties.

` String`

` getLabelName()`
            

` String`

` getLabelProperty()`
            

` String`

` getName()`
            

` String`

` getProperty()`
            

` String`

` getStyle()`
            

` String`

` getStyleClass()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setCollection(String collection)`
            

` void`

` setFilter(boolean filter)`
            

` void`

` setLabelName(String labelName)`
            

` void`

` setLabelProperty(String labelProperty)`
            

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
            

` void`

` setStyle(String style)`
            

` void`

` setStyleClass(String styleClass)`
            

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                     |

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

    protected String collection

The name of the collection containing beans that have properties to provide both the values and the labels (identified by the `property` and `labelProperty` attributes).

------------------------------------------------------------------------

<span id="filter"></span>

### filter

    protected boolean filter

Should the label values be filtered for HTML sensitive characters?

------------------------------------------------------------------------

<span id="labelName"></span>

### labelName

    protected String labelName

The name of the bean containing the labels collection.

------------------------------------------------------------------------

<span id="labelProperty"></span>

### labelProperty

    protected String labelProperty

The bean property containing the labels collection.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The name of the bean containing the values collection.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The name of the property to use to build the values collection.

<span id="constructor_detail"></span>

**Constructor Detail**

### OptionsTag

    public OptionsTag()

<span id="method_detail"></span>

**Method Detail**

### getCollection

    public String getCollection()

------------------------------------------------------------------------

### setCollection

    public void setCollection(String collection)

------------------------------------------------------------------------

### getFilter

    public boolean getFilter()

------------------------------------------------------------------------

### setFilter

    public void setFilter(boolean filter)

------------------------------------------------------------------------

### getLabelName

    public String getLabelName()

------------------------------------------------------------------------

### setLabelName

    public void setLabelName(String labelName)

------------------------------------------------------------------------

### getLabelProperty

    public String getLabelProperty()

------------------------------------------------------------------------

### setLabelProperty

    public void setLabelProperty(String labelProperty)

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

### getStyle

    public String getStyle()

------------------------------------------------------------------------

### setStyle

    public void setStyle(String style)

------------------------------------------------------------------------

### getStyleClass

    public String getStyleClass()

------------------------------------------------------------------------

### setStyleClass

    public void setStyleClass(String styleClass)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start of this tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Process the end of this tag.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### release

    public void release()

Release any acquired resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `TagSupport`

------------------------------------------------------------------------

### addOption

    protected void addOption(StringBuffer sb,
                             String value,
                             String label,
                             boolean matched)

Add an option element to the specified StringBuffer based on the specified parameters.

Note that this tag specifically does not support the `styleId` tag attribute, which causes the HTML `id` attribute to be emitted. This is because the HTML specification states that all "id" attributes in a document have to be unique. This tag will likely generate more than one `option` element element, but it cannot use the same `id` value. It's conceivable some sort of mechanism to supply an array of `id` values could be devised, but that doesn't seem to be worth the trouble.

**Parameters:**  
`sb` - StringBuffer accumulating our results

`value` - Value to be returned to the server for this option

`label` - Value to be shown to the user for this option

`matched` - Should this value be marked as selected?

------------------------------------------------------------------------

### getIterator

    protected Iterator getIterator(String name,
                                   String property)
                            throws JspException

Return an iterator for the option labels or values, based on our configured properties.

**Parameters:**  
`name` - Name of the bean attribute (if any)

`property` - Name of the bean property (if any)

**Throws:**  
`JspException` - if an error occurs

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
<td align="left"><a href="class-use/OptionsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/OptionsCollectionTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/OptionTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/OptionsTag.html"><strong>FRAMES</strong></a>    <a href="OptionsTag.html"><strong>NO FRAMES</strong></a>    
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
