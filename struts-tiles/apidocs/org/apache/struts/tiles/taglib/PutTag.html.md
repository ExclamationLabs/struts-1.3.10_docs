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
<td align="left"><a href="class-use/PutTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutTagParent.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutTag.html"><strong>FRAMES</strong></a>    <a href="PutTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.taglib
 Class PutTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.tiles.taglib.PutTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Direct Known Subclasses:**  
[AddTag](../../../../../org/apache/struts/tiles/taglib/AddTag.html.md "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public class PutTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

implements [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")

Put an attribute in enclosing attribute container tag. Enclosing attribute container tag can be : \<insert\> or \<definition\>. Exception is thrown if no appropriate tag can be found. Put tag can have following atributes :

name : Name of the attribute

value | content : value to put as attribute

type : value type. Only valid if value is a String and is set by value="something" or by a bean. Possible type are : string (value is used as direct string), page | template (value is used as a page url to insert), definition (value is used as a definition name to insert)

direct : Specify if value is to be used as a direct string or as a page url to insert. This is another way to specify the type. It only apply if value is set as a string, and type is not present.

beanName : Name of a bean used for setting value. Only valid if value is not set. If property is specified, value come from bean's property. Otherwise, bean itself is used for value.

beanProperty : Name of the property used for retrieving value.

beanScope : Scope containing bean.

role : Role to check when 'insert' will be called. If enclosing tag is \<insert\>, role is checked immediately. If enclosing tag is \<definition\>, role will be checked when this definition will be inserted.

Value can also come from tag body. Tag body is taken into account only if value is not set by one of the tag attributes. In this case Attribute type is "string", unless tag body define another type.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.PutTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` attributeName`
           Name of attribute to put in component context.

`protected  String`

`body`
           The body content of this tag.

`protected  Object`

` realValue`
           Cached real value computed from tag attributes.

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bodyContent`                                                                                                                                                                                                                   |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.ComponentConstants"></span>

| **Fields inherited from interface org.apache.struts.tiles.taglib.[ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` COMPONENT_CONTEXT,  COMPONENT_SCOPE,  EXCEPTION_KEY,  LOCALE_KEY`                                                                                                                                          |

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

| **Constructor Summary**         |
|---------------------------------|
| ` PutTag()`                     
            Default constructor.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` callParent()`
           Find parent tag which must implement AttributeContainer.

`protected  void`

` computeRealValue()`
           Compute real value according to tag attributes.

` int`

` doAfterBody()`
           Save the body content of this tag (if any)

` int`

` doEndTag()`
           Do end tag.

` int`

` doStartTag()`
           Do start tag.

`protected  PutTagParent`

` findEnclosingPutTagParent()`
           Find parent tag which must implement AttributeContainer.

` String`

` getBeanName()`
           Get bean name.

` String`

` getBeanProperty()`
           Get bean property.

` String`

` getBeanScope()`
           Get bean scope.

` String`

` getContent()`
           Get content.

` String`

` getName()`
           Get name.

` Object`

` getRealValue()`
           Get real value according to tag attribute.

`protected  void`

` getRealValueFromBean()`
           Extract real value from specified bean.

` String`

` getRole()`
           Get role attribute

` String`

` getType()`
           Get type.

` String`

` getValue()`
           Get value.

` void`

` release()`
           Release all allocated resources.

`protected  void`

` releaseInternal()`
           Release internal properties.

` void`

` setBeanName(String value)`
           Set bean name.

` void`

` setBeanProperty(String value)`
           Set bean property.

` void`

` setBeanScope(String value)`
           Set bean scope.

` void`

` setContent(Object value)`
           Set content.

` void`

` setContent(String value)`
           Set content.

` void`

` setDirect(String isDirect)`
           Set direct.

` void`

` setName(String value)`
           Set name.

` void`

` setObjectValue(Object value)`
           Set property value as an object.

` void`

` setRole(String role)`
           Set role attribute.

` void`

` setType(String value)`
           Set type.

` void`

` setValue(Object value)`
           Set value.

` void`

` setValue(String value)`
           Set value.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                                                     |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                                                  |

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

<span id="attributeName"></span>

### attributeName

    protected String attributeName

Name of attribute to put in component context.

------------------------------------------------------------------------

<span id="realValue"></span>

### realValue

    protected Object realValue

Cached real value computed from tag attributes.

------------------------------------------------------------------------

<span id="body"></span>

### body

    protected String body

The body content of this tag.

<span id="constructor_detail"></span>

**Constructor Detail**

### PutTag

    public PutTag()

Default constructor.

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `BodyTagSupport`

------------------------------------------------------------------------

### releaseInternal

    protected void releaseInternal()

Release internal properties.

------------------------------------------------------------------------

### setName

    public void setName(String value)

Set name.

------------------------------------------------------------------------

### getName

    public String getName()

Get name.

------------------------------------------------------------------------

### setValue

    public void setValue(String value)

Set value. Method added to satisfy Tomcat (bug ?).

------------------------------------------------------------------------

### getValue

    public String getValue()

Get value. Method added to satisfy Tomcat (bug ?).

------------------------------------------------------------------------

### setValue

    public void setValue(Object value)

Set value.

------------------------------------------------------------------------

### setObjectValue

    public void setObjectValue(Object value)

Set property value as an object. Added because some web containers react badly to value as `Object`.

------------------------------------------------------------------------

### setContent

    public void setContent(String value)

Set content. Method added to satisfy Tomcat (bug ?).

------------------------------------------------------------------------

### getContent

    public String getContent()

Get content. Method added to satisfy Tomcat (bug ?).

------------------------------------------------------------------------

### setContent

    public void setContent(Object value)

Set content.

------------------------------------------------------------------------

### setDirect

    public void setDirect(String isDirect)

Set direct. Method added for compatibility with JSP1.1.

------------------------------------------------------------------------

### setType

    public void setType(String value)

Set type.

------------------------------------------------------------------------

### getType

    public String getType()

Get type.

------------------------------------------------------------------------

### setBeanName

    public void setBeanName(String value)

Set bean name.

------------------------------------------------------------------------

### getBeanName

    public String getBeanName()

Get bean name.

------------------------------------------------------------------------

### setBeanProperty

    public void setBeanProperty(String value)

Set bean property.

------------------------------------------------------------------------

### getBeanProperty

    public String getBeanProperty()

Get bean property.

------------------------------------------------------------------------

### setBeanScope

    public void setBeanScope(String value)

Set bean scope.

------------------------------------------------------------------------

### getBeanScope

    public String getBeanScope()

Get bean scope.

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Set role attribute.

**Parameters:**  
`role` - The role the user must be in to store content.

------------------------------------------------------------------------

### getRole

    public String getRole()

Get role attribute

**Returns:**  
The role defined in the tag or `null`.

------------------------------------------------------------------------

### getRealValue

    public Object getRealValue()
                        throws JspException

Get real value according to tag attribute. Real value is the value computed after attribute processing.

**Returns:**  
Real value.

**Throws:**  
`JspException` - If something goes wrong while getting value from bean.

------------------------------------------------------------------------

### computeRealValue

    protected void computeRealValue()
                             throws JspException

Compute real value according to tag attributes.

**Throws:**  
`JspException` - If something goes wrong while getting value from bean.

------------------------------------------------------------------------

### getRealValueFromBean

    protected void getRealValueFromBean()
                                 throws JspException

Extract real value from specified bean.

**Throws:**  
`JspException` - If something goes wrong while getting value from bean.

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Do start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doAfterBody

    public int doAfterBody()
                    throws JspException

Save the body content of this tag (if any)

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

Do end tag.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `BodyTagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### callParent

    protected void callParent()
                       throws JspException

Find parent tag which must implement AttributeContainer.

**Throws:**  
`JspException` - If we can't find an appropriate enclosing tag.

------------------------------------------------------------------------

### findEnclosingPutTagParent

    protected PutTagParent findEnclosingPutTagParent()
                                              throws JspException

Find parent tag which must implement AttributeContainer.

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
<td align="left"><a href="class-use/PutTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html.md" title="interface in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/PutTagParent.html" title="interface in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/PutTag.html"><strong>FRAMES</strong></a>    <a href="PutTag.html"><strong>NO FRAMES</strong></a>    
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
