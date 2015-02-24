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
<td align="left"><a href="class-use/ErrorsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/Constants.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/FileTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/ErrorsTag.html"><strong>FRAMES</strong></a>    <a href="ErrorsTag.html"><strong>NO FRAMES</strong></a>    
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
 Class ErrorsTag
-----------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.html.md.ErrorsTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[NestedErrorsTag](../../../../../org/apache/struts/taglib/nested.html.md/NestedErrorsTag.html "class in org.apache.struts.taglib.nested.html")

------------------------------------------------------------------------

    public class ErrorsTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that renders error messages if an appropriate request attribute has been created. The tag looks for a request attribute with a reserved key, and assumes that it is either a String, a String array, containing message keys to be looked up in the module's MessageResources, or an object of type `org.apache.struts.action.ActionErrors`.

The following optional message keys will be utilized if corresponding messages exist for them in the application resources:

-   **errors.header** - If present, the corresponding message will be rendered prior to the individual list of error messages.
-   **errors.footer** - If present, the corresponding message will be rendered following the individual list of error messages.
-   **errors.prefix** - If present, the corresponding message will be rendered before each individual error message.
-   **errors.suffix** - If present, the corresponding message will be rendered after each individual error message.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.html.ErrorsTag)

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

` locale`
           The session attribute key for our locale.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

`name`
           The request attribute key for our error messages (if any).

`protected  String`

` prefix`
           The message resource key for errors prefix.

`protected  String`

` property`
           The name of the property for which error messages should be returned, or `null` to return all errors.

`protected  String`

` suffix`
           The message resource key for errors suffix.

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
| ` ErrorsTag()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Render the specified error messages if there are any.

` String`

` getBundle()`
            

` String`

` getFooter()`
            

` String`

` getHeader()`
            

` String`

` getLocale()`
            

` String`

` getName()`
            

` String`

` getPrefix()`
            

` String`

` getProperty()`
            

` String`

` getSuffix()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setBundle(String bundle)`
            

` void`

` setFooter(String footer)`
            

` void`

` setHeader(String header)`
            

` void`

` setLocale(String locale)`
            

` void`

` setName(String name)`
            

` void`

` setPrefix(String prefix)`
            

` void`

` setProperty(String property)`
            

` void`

` setSuffix(String suffix)`
            

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

<span id="prefix"></span>

### prefix

    protected String prefix

The message resource key for errors prefix.

------------------------------------------------------------------------

<span id="suffix"></span>

### suffix

    protected String suffix

The message resource key for errors suffix.

<span id="constructor_detail"></span>

**Constructor Detail**

### ErrorsTag

    public ErrorsTag()

<span id="method_detail"></span>

**Method Detail**

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

### getPrefix

    public String getPrefix()

------------------------------------------------------------------------

### setPrefix

    public void setPrefix(String prefix)

------------------------------------------------------------------------

### getSuffix

    public String getSuffix()

------------------------------------------------------------------------

### setSuffix

    public void setSuffix(String suffix)

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Render the specified error messages if there are any.

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
<td align="left"><a href="class-use/ErrorsTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib.html.md/Constants.html" title="class in org.apache.struts.taglib.html"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/taglib/html/FileTag.html" title="class in org.apache.struts.taglib.html"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/html/ErrorsTag.html"><strong>FRAMES</strong></a>    <a href="ErrorsTag.html"><strong>NO FRAMES</strong></a>    
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
