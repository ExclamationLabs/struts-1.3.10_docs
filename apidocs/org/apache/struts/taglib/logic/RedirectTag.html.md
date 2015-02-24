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
<td align="left"><a href="class-use/RedirectTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/PresentTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/RedirectTag.html"><strong>FRAMES</strong></a>    <a href="RedirectTag.html"><strong>NO FRAMES</strong></a>    
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
 Class RedirectTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.taglib.logic.RedirectTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

<!-- -->

**Direct Known Subclasses:**  
[ELRedirectTag](../../../../../org/apache/strutsel/taglib/logic/ELRedirectTag.html.md "class in org.apache.strutsel.taglib.logic")

------------------------------------------------------------------------

    public class RedirectTag

extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Generate a URL-encoded redirect to the specified URI.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.taglib.logic.RedirectTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` action`
           The module-relative action (beginning with a slash) which will be called by this link

`protected  String`

` anchor`
           The anchor to be added to the end of the generated hyperlink.

`protected  String`

` forward`
           The logical forward name from which to retrieve the redirect URI.

`protected  String`

` href`
           The redirect URI.

`protected static MessageResources`

` messages`
           The message resources for this package.

`protected  String`

` module`
           The module prefix (beginning with a slash) which will be used to find the action for this link.

`protected  String`

` name`
           The JSP bean name for query parameters.

`protected  String`

` page`
           The module-relative page URL (beginning with a slash) to which this redirect will be rendered.

`protected  String`

` paramId`
           The single-parameter request parameter name to generate.

`protected  String`

` paramName`
           The single-parameter JSP bean name.

`protected  String`

` paramProperty`
           The single-parameter JSP bean property.

`protected  String`

` paramScope`
           The single-parameter JSP bean scope.

`protected  String`

` property`
           The JSP bean property name for query parameters.

`protected  String`

` scope`
           The scope of the bean specified by the name property, if any.

`protected  boolean`

` transaction`
           Include our transaction control token?

`protected  boolean`

` useLocalEncoding`
           Use character encoding from ServletResponse\#getCharacterEncoding to get bytes of the url string for urlencoding?

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
| ` RedirectTag()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doEndTag()`
           Render the redirect and skip the remainder of this page.

`protected  void`

` doRedirect(String url)`
           Redirect to the given url converting exceptions to JspException.

` int`

` doStartTag()`
           Defer generation until the end of this tag is encountered.

`protected  String`

` generateRedirectURL()`
           Calculate the url to redirect to.

` String`

` getAction()`
            

` String`

` getAnchor()`
            

` String`

` getForward()`
            

` String`

` getHref()`
            

` String`

` getModule()`
            

` String`

` getName()`
            

` String`

` getPage()`
            

` String`

` getParamId()`
            

` String`

` getParamName()`
            

` String`

` getParamProperty()`
            

` String`

` getParamScope()`
            

` String`

` getProperty()`
            

` String`

` getScope()`
            

` boolean`

` getTransaction()`
            

` boolean`

` isUseLocalEncoding()`
            

` void`

` release()`
           Release any acquired resources.

` void`

` setAction(String action)`
            

` void`

` setAnchor(String anchor)`
            

` void`

` setForward(String forward)`
            

` void`

` setHref(String href)`
            

` void`

` setModule(String module)`
            

` void`

` setName(String name)`
            

` void`

` setPage(String page)`
            

` void`

` setParamId(String paramId)`
            

` void`

` setParamName(String paramName)`
            

` void`

` setParamProperty(String paramProperty)`
            

` void`

` setParamScope(String paramScope)`
            

` void`

` setProperty(String property)`
            

` void`

` setScope(String scope)`
            

` void`

` setTransaction(boolean transaction)`
            

` void`

` setUseLocalEncoding(boolean b)`
            

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

<span id="anchor"></span>

### anchor

    protected String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

<span id="forward"></span>

### forward

    protected String forward

The logical forward name from which to retrieve the redirect URI.

------------------------------------------------------------------------

<span id="href"></span>

### href

    protected String href

The redirect URI.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected String page

The module-relative page URL (beginning with a slash) to which this redirect will be rendered.

------------------------------------------------------------------------

<span id="action"></span>

### action

    protected String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

<span id="module"></span>

### module

    protected String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

<span id="paramId"></span>

### paramId

    protected String paramId

The single-parameter request parameter name to generate.

------------------------------------------------------------------------

<span id="paramName"></span>

### paramName

    protected String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

<span id="paramProperty"></span>

### paramProperty

    protected String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

<span id="paramScope"></span>

### paramScope

    protected String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

<span id="property"></span>

### property

    protected String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

<span id="transaction"></span>

### transaction

    protected boolean transaction

Include our transaction control token?

------------------------------------------------------------------------

<span id="useLocalEncoding"></span>

### useLocalEncoding

    protected boolean useLocalEncoding

Use character encoding from ServletResponse\#getCharacterEncoding to get bytes of the url string for urlencoding?

<span id="constructor_detail"></span>

**Constructor Detail**

### RedirectTag

    public RedirectTag()

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

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getPage

    public String getPage()

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

------------------------------------------------------------------------

### getAction

    public String getAction()

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

------------------------------------------------------------------------

### getModule

    public String getModule()

------------------------------------------------------------------------

### setModule

    public void setModule(String module)

------------------------------------------------------------------------

### getParamId

    public String getParamId()

------------------------------------------------------------------------

### setParamId

    public void setParamId(String paramId)

------------------------------------------------------------------------

### getParamName

    public String getParamName()

------------------------------------------------------------------------

### setParamName

    public void setParamName(String paramName)

------------------------------------------------------------------------

### getParamProperty

    public String getParamProperty()

------------------------------------------------------------------------

### setParamProperty

    public void setParamProperty(String paramProperty)

------------------------------------------------------------------------

### getParamScope

    public String getParamScope()

------------------------------------------------------------------------

### setParamScope

    public void setParamScope(String paramScope)

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

Defer generation until the end of this tag is encountered.

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

Render the redirect and skip the remainder of this page.

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException` - if a JSP exception has occurred

------------------------------------------------------------------------

### generateRedirectURL

    protected String generateRedirectURL()
                                  throws JspException

Calculate the url to redirect to.

**Throws:**  
`JspException`

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### doRedirect

    protected void doRedirect(String url)
                       throws JspException

Redirect to the given url converting exceptions to JspException.

**Parameters:**  
`url` - The path to redirect to.

**Throws:**  
`JspException`

**Since:**  
Struts 1.2

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
<td align="left"><a href="class-use/RedirectTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/taglib/logic/PresentTag.html.md" title="class in org.apache.struts.taglib.logic"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/taglib/logic/RedirectTag.html"><strong>FRAMES</strong></a>    <a href="RedirectTag.html"><strong>NO FRAMES</strong></a>    
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
