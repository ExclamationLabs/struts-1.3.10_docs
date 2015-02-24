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
<td align="left"><a href="class-use/ELMessagesNotPresentTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELMatchTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html"><strong>FRAMES</strong></a>    <a href="ELMessagesNotPresentTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.MessagesPresentTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.strutsel.taglib.logic
 Class ELMessagesNotPresentTag
--------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.ConditionalTagBase
              org.apache.struts.taglib.logic.MessagesPresentTag
                  org.apache.struts.taglib.logic.MessagesNotPresentTag
                      org.apache.strutsel.taglib.logic.ELMessagesNotPresentTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class ELMessagesNotPresentTag

extends [MessagesNotPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/MessagesNotPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")

Evalute to `false` if an `ActionMessages` class or a class that can be converted to an `ActionMessages` class is in request scope under the specified key and there is at least one message in the class or for the property specified.

This class is a subclass of the class `org.apache.struts.taglib.logic.MessagesNotPresentTag` which provides most of the described functionality. This subclass allows all attribute values to be specified as expressions utilizing the JavaServer Pages Standard Library expression language.

**Version:**  
$Rev: 471754 $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.strutsel.taglib.logic.ELMessagesNotPresentTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.MessagesPresentTag"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[MessagesPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/MessagesPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `message`                                                                                                                                                                                                                                            |

 <span id="fields_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Fields inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/ConditionalTagBase.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `cookie, header, messages, name, parameter, property, role, scope, user`                                                                                                                                                                             |

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

| **Constructor Summary**      |
|------------------------------|
| ` ELMessagesNotPresentTag()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getMessageExpr()`
           Getter method for "message" tag attribute.

` String`

` getNameExpr()`
           Getter method for "name" tag attribute.

` String`

` getPropertyExpr()`
           Getter method for "property" tag attribute.

` void`

` release()`
           Releases state of custom tag so this instance can be reused.

` void`

` setMessageExpr(String messageExpr)`
           Setter method for "message" tag attribute.

` void`

` setNameExpr(String nameExpr)`
           Setter method for "name" tag attribute.

` void`

` setPropertyExpr(String propertyExpr)`
           Setter method for "property" tag attribute.

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.MessagesNotPresentTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[MessagesNotPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/MessagesNotPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `condition`                                                                                                                                                                                                                                                 |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.MessagesPresentTag"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[MessagesPresentTag](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/MessagesPresentTag.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `condition, getMessage, setMessage`                                                                                                                                                                                                                   |

 <span id="methods_inherited_from_class_org.apache.struts.taglib.logic.ConditionalTagBase"></span>

| **Methods inherited from class org.apache.struts.taglib.logic.[ConditionalTagBase](http://struts.apache.org/apidocs/org/apache/struts/taglib/logic/ConditionalTagBase.html.md?is-external=true "class or interface in org.apache.struts.taglib.logic")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doEndTag, getCookie, getHeader, getName, getParameter, getProperty, getRole, getScope, getUser, setCookie, setHeader, setName, setParameter, setProperty, setRole, setScope, setUser`                                                                |

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

### ELMessagesNotPresentTag

    public ELMessagesNotPresentTag()

<span id="method_detail"></span>

**Method Detail**

### getNameExpr

    public String getNameExpr()

Getter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getPropertyExpr

    public String getPropertyExpr()

Getter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### getMessageExpr

    public String getMessageExpr()

Getter method for "message" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setNameExpr

    public void setNameExpr(String nameExpr)

Setter method for "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setPropertyExpr

    public void setPropertyExpr(String propertyExpr)

Setter method for "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### setMessageExpr

    public void setMessageExpr(String messageExpr)

Setter method for "message" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### release

    public void release()

Releases state of custom tag so this instance can be reused.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
`release` in class `MessagesPresentTag`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `ConditionalTagBase`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

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
<td align="left"><a href="class-use/ELMessagesNotPresentTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/strutsel/taglib/logic/ELMatchTagBeanInfo.html.md" title="class in org.apache.strutsel.taglib.logic"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/strutsel/taglib/logic/ELMessagesNotPresentTagBeanInfo.html" title="class in org.apache.strutsel.taglib.logic"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html"><strong>FRAMES</strong></a>    <a href="ELMessagesNotPresentTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.taglib.logic.MessagesPresentTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
