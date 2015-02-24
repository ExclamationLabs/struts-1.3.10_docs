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
<td align="left"><a href="class-use/MessageTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/IncludeTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/PageTag.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/MessageTag.html"><strong>FRAMES</strong></a>    <a href="MessageTag.html"><strong>NO FRAMES</strong></a>    
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
 Class MessageTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.MessageTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELMessageTag](../../../../../org/apache/strutsel/taglib/bean/ELMessageTag.html.md "class in org.apache.strutsel.taglib.bean"), [NestedMessageTag](../../../../../org/apache/struts/taglib/nested/bean/NestedMessageTag.html "class in org.apache.struts.taglib.nested.bean")

------------------------------------------------------------------------

    public class MessageTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that retrieves an internationalized messages string (with optional parametric replacement) from the `ActionResources` object stored as a context attribute by our associated `ActionServlet` implementation.

**Version:**  
$Rev: 471754 $ $Date: 2005-09-16 09:38:33 -0400 (Fri, 16 Sep 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.bean.MessageTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` arg0`
           The first optional argument.

`protected  String`

` arg1`
           The second optional argument.

`protected  String`

` arg2`
           The third optional argument.

`protected  String`

` arg3`
           The fourth optional argument.

`protected  String`

` arg4`
           The fifth optional argument.

`protected  String`

` bundle`
           The servlet context attribute key for our resources.

`protected  String`

`key`
           The message key of the message to be retrieved.

`protected  String`

` localeKey`
           The session scope key under which our Locale is stored.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` name`
           Name of the bean that contains the message key.

`protected  String`

` property`
           Name of the property to be accessed on the specified bean.

`protected  String`

` scope`
           The scope to be searched to retrieve the specified bean.

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
| ` MessageTag()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Process the start tag.

` String`

` getArg0()`
            

` String`

` getArg1()`
            

` String`

` getArg2()`
            

` String`

` getArg3()`
            

` String`

` getArg4()`
            

` String`

` getBundle()`
            

` String`

` getKey()`
            

` String`

` getLocale()`
            

` String`

` getName()`
            

` String`

` getProperty()`
            

` String`

` getScope()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setArg0(String arg0)`
            

` void`

` setArg1(String arg1)`
            

` void`

` setArg2(String arg2)`
            

` void`

` setArg3(String arg3)`
            

` void`

` setArg4(String arg4)`
            

` void`

` setBundle(String bundle)`
            

` void`

` setKey(String key)`
            

` void`

` setLocale(String localeKey)`
            

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
            

` void`

` setScope(String scope)`
            

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setPageContext, setParent, setValue`                                                                           |

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

<span id="arg0"></span>

### arg0

    protected String arg0

The first optional argument.

------------------------------------------------------------------------

<span id="arg1"></span>

### arg1

    protected String arg1

The second optional argument.

------------------------------------------------------------------------

<span id="arg2"></span>

### arg2

    protected String arg2

The third optional argument.

------------------------------------------------------------------------

<span id="arg3"></span>

### arg3

    protected String arg3

The fourth optional argument.

------------------------------------------------------------------------

<span id="arg4"></span>

### arg4

    protected String arg4

The fifth optional argument.

------------------------------------------------------------------------

<span id="bundle"></span>

### bundle

    protected String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

<span id="key"></span>

### key

    protected String key

The message key of the message to be retrieved.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

Name of the bean that contains the message key.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

Name of the property to be accessed on the specified bean.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope to be searched to retrieve the specified bean.

------------------------------------------------------------------------

<span id="localeKey"></span>

### localeKey

    protected String localeKey

The session scope key under which our Locale is stored.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessageTag

    public MessageTag()

<span id="method_detail"></span>

**Method Detail**

### getArg0

    public String getArg0()

------------------------------------------------------------------------

### setArg0

    public void setArg0(String arg0)

------------------------------------------------------------------------

### getArg1

    public String getArg1()

------------------------------------------------------------------------

### setArg1

    public void setArg1(String arg1)

------------------------------------------------------------------------

### getArg2

    public String getArg2()

------------------------------------------------------------------------

### setArg2

    public void setArg2(String arg2)

------------------------------------------------------------------------

### getArg3

    public String getArg3()

------------------------------------------------------------------------

### setArg3

    public void setArg3(String arg3)

------------------------------------------------------------------------

### getArg4

    public String getArg4()

------------------------------------------------------------------------

### setArg4

    public void setArg4(String arg4)

------------------------------------------------------------------------

### getBundle

    public String getBundle()

------------------------------------------------------------------------

### setBundle

    public void setBundle(String bundle)

------------------------------------------------------------------------

### getKey

    public String getKey()

------------------------------------------------------------------------

### setKey

    public void setKey(String key)

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

### getLocale

    public String getLocale()

------------------------------------------------------------------------

### setLocale

    public void setLocale(String localeKey)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag.

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

Release any acquired resources.

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
<td align="left"><a href="class-use/MessageTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/IncludeTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/PageTag.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/MessageTag.html"><strong>FRAMES</strong></a>    <a href="MessageTag.html"><strong>NO FRAMES</strong></a>    
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
