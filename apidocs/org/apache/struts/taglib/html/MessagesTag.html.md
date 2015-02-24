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
<td align="left"><a href="class-use/MessagesTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/LinkTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/MessagesTei.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/MessagesTag.html"><strong>FRAMES</strong></a>    <a href="MessagesTag.html"><strong>NO FRAMES</strong></a>    
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
 Class MessagesTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.taglib.html.md.MessagesTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELMessagesTag](../../../../../org/apache/strutsel/taglib.html.md/ELMessagesTag.html "class in org.apache.strutsel.taglib.html"), [NestedMessagesTag](../../../../../org/apache/struts/taglib/nested/html/NestedMessagesTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class MessagesTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that iterates the elements of a message collection. It defaults to retrieving the messages from `Globals.ERROR_KEY`, but if the message attribute is set to true then the messages will be retrieved from `Globals.MESSAGE_KEY`. This is an alternative to the default `ErrorsTag`.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-11-08 23:50:53 -0500 (Tue, 08 Nov 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.MessagesTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` bundle`
           The servlet context attribute key for our resources.

`protected  String`

` footer`
           The message resource key for errors footer.

`protected  String`

` header`
           The message resource key for errors header.

`protected  String`

`id`
           The name of the scripting variable to be exposed.

`protected  Iterator`

` iterator`
           Iterator of the elements of this error collection, while we are actually running.

`protected  String`

` locale`
           The session attribute key for our locale.

`protected  String`

` message`
           If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

`protected static MessageResources`

` messageResources`
           The message resources for this package.

`protected  String`

` name`
           The request attribute key for our error messages (if any).

`protected  boolean`

` processed`
           Whether or not any error messages have been processed.

`protected  String`

` property`
           The name of the property for which error messages should be returned, or `null` to return all errors.

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
| ` MessagesTag()`        
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

` String`

` getBundle()`
            

` String`

` getFooter()`
            

` String`

` getHeader()`
            

` String`

` getId()`
            

` String`

` getLocale()`
            

` String`

` getMessage()`
            

` String`

` getName()`
            

` String`

` getProperty()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setBundle(String bundle)`
            

` void`

` setFooter(String footer)`
            

` void`

` setHeader(String header)`
            

` void`

` setId(String id)`
            

` void`

` setLocale(String locale)`
            

` void`

` setMessage(String message)`
            

` void`

` setName(String name)`
            

` void`

` setProperty(String property)`
            

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

<span id="messageResources"></span>

### messageResources

    protected static MessageResources messageResources

The message resources for this package.

------------------------------------------------------------------------

<span id="iterator"></span>

### iterator

    protected Iterator iterator

Iterator of the elements of this error collection, while we are actually running.

------------------------------------------------------------------------

<span id="processed"></span>

### processed

    protected boolean processed

Whether or not any error messages have been processed.

------------------------------------------------------------------------

<span id="id"></span>

### id

    protected String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

<span id="bundle"></span>

### bundle

    protected String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

<span id="locale"></span>

### locale

    protected String locale

The session attribute key for our locale.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The name of the property for which error messages should be returned, or `null` to return all errors.

------------------------------------------------------------------------

<span id="header"></span>

### header

    protected String header

The message resource key for errors header.

------------------------------------------------------------------------

<span id="footer"></span>

### footer

    protected String footer

The message resource key for errors footer.

------------------------------------------------------------------------

<span id="message"></span>

### message

    protected String message

If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessagesTag

    public MessagesTag()

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

### getBundle

    public String getBundle()

------------------------------------------------------------------------

### setBundle

    public void setBundle(String bundle)

------------------------------------------------------------------------

### getLocale

    public String getLocale()

------------------------------------------------------------------------

### setLocale

    public void setLocale(String locale)

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

### getHeader

    public String getHeader()

------------------------------------------------------------------------

### setHeader

    public void setHeader(String header)

------------------------------------------------------------------------

### getFooter

    public String getFooter()

------------------------------------------------------------------------

### setFooter

    public void setFooter(String footer)

------------------------------------------------------------------------

### getMessage

    public String getMessage()

------------------------------------------------------------------------

### setMessage

    public void setMessage(String message)

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
<td align="left"><a href="class-use/MessagesTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/LinkTag.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/MessagesTei.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/MessagesTag.html"><strong>FRAMES</strong></a>    <a href="MessagesTag.html"><strong>NO FRAMES</strong></a>    
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
