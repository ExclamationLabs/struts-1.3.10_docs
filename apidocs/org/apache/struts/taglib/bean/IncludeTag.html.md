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
<td align="left"><a href="class-use/IncludeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/HeaderTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/IncludeTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/IncludeTag.html"><strong>FRAMES</strong></a>    <a href="IncludeTag.html"><strong>NO FRAMES</strong></a>    
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
 Class IncludeTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.bean.IncludeTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELIncludeTag](../../../../../org/apache/strutsel/taglib/bean/ELIncludeTag.html.md "class in org.apache.strutsel.taglib.bean")

------------------------------------------------------------------------

    public class IncludeTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Define the contents of a specified intra-application request as a page scope attribute of type `java.lang.String`. If the current request is part of a session, the session identifier will be included in the generated request, so it will be part of the same session.

**FIXME**: In a servlet 2.3 environment, we can use a wrapped response passed to RequestDispatcher.include().

**Version:**  
$Rev: 471754 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.bean.IncludeTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` anchor`
           The anchor to be added to the end of the generated hyperlink.

`protected static int`

` BUFFER_SIZE`
           Buffer size to use when reading the input stream.

`protected  String`

` forward`
           The name of the global `ActionForward` that contains a path to our requested resource.

`protected  String`

` href`
           The absolute URL to the resource to be included.

`protected  String`

`id`
           The name of the scripting variable that will be exposed as a page scope attribute.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` page`
           The context-relative URI of the page or servlet to be included.

`protected  boolean`

` transaction`
           Include transaction token (if any) in the hyperlink?

`protected  boolean`

` useLocalEncoding`
            

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
| ` IncludeTag()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` addCookie(URLConnection conn, String urlString, HttpServletRequest request)`
           Add a session id cookie if appropriate.

` int`

` doStartTag()`
           Define the contents returned for the specified resource as a page scope attribute.

` String`

` getAnchor()`
            

` String`

` getForward()`
            

` String`

` getHref()`
            

` String`

` getId()`
            

` String`

` getPage()`
            

` boolean`

` getTransaction()`
            

` boolean`

` isUseLocalEncoding()`
            

` void`

` release()`
           Release all allocated resources.

` void`

` setAnchor(String anchor)`
            

` void`

` setForward(String forward)`
            

` void`

` setHref(String href)`
            

` void`

` setId(String id)`
            

` void`

` setPage(String page)`
            

` void`

` setTransaction(boolean transaction)`
            

` void`

` setUseLocalEncoding(boolean b)`
            

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
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.taglib.bean.IncludeTag.BUFFER_SIZE)

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

------------------------------------------------------------------------

<span id="anchor"></span>

### anchor

    protected String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

<span id="forward"></span>

### forward

    protected String forward

The name of the global `ActionForward` that contains a path to our requested resource.

------------------------------------------------------------------------

<span id="href"></span>

### href

    protected String href

The absolute URL to the resource to be included.

------------------------------------------------------------------------

<span id="id"></span>

### id

    protected String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

The context-relative URI of the page or servlet to be included.

------------------------------------------------------------------------

<span id="transaction"></span>

### transaction

    protected boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

<span id="useLocalEncoding"></span>

### useLocalEncoding

    protected boolean useLocalEncoding

<span id="constructor_detail"></span>

**Constructor Detail**

### IncludeTag

    public IncludeTag()

<span id="method_detail"></span>

**Method Detail**

### getAnchor

    public String getAnchor()

------------------------------------------------------------------------

### setAnchor

    public void setAnchor(String anchor)

------------------------------------------------------------------------

### getForward

    public String getForward()

------------------------------------------------------------------------

### setForward

    public void setForward(String forward)

------------------------------------------------------------------------

### getHref

    public String getHref()

------------------------------------------------------------------------

### setHref

    public void setHref(String href)

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

### getPage

    public String getPage()

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

------------------------------------------------------------------------

### getTransaction

    public boolean getTransaction()

------------------------------------------------------------------------

### setTransaction

    public void setTransaction(boolean transaction)

------------------------------------------------------------------------

### isUseLocalEncoding

    public boolean isUseLocalEncoding()

------------------------------------------------------------------------

### setUseLocalEncoding

    public void setUseLocalEncoding(boolean b)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Define the contents returned for the specified resource as a page scope attribute.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP error occurs

------------------------------------------------------------------------

### addCookie

    protected void addCookie(URLConnection conn,
                             String urlString,
                             HttpServletRequest request)

Add a session id cookie if appropriate. Can be overloaded to support a cluster.

**Parameters:**  
`conn` -

`urlString` -

`request` -

**Since:**  
Struts 1.2.0

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
<td align="left"><a href="class-use/IncludeTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/bean/HeaderTei.html.md" title="class in org.apache.struts.taglib.bean"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/bean/IncludeTei.html" title="class in org.apache.struts.taglib.bean"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/bean/IncludeTag.html"><strong>FRAMES</strong></a>    <a href="IncludeTag.html"><strong>NO FRAMES</strong></a>    
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
