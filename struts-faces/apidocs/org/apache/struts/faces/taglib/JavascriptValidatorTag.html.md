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
<td align="left"><a href="class-use/JavascriptValidatorTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/taglib/HtmlTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/taglib/LoadMessagesTag.html" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/JavascriptValidatorTag.html"><strong>FRAMES</strong></a>    <a href="JavascriptValidatorTag.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.faces.taglib
 Class JavascriptValidatorTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          javax.servlet.jsp.tagext.BodyTagSupport
              org.apache.struts.faces.taglib.JavascriptValidatorTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [BodyTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext")

------------------------------------------------------------------------

    public class JavascriptValidatorTag

extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")

Custom tag that generates JavaScript for client side validation based on the validation rules loaded by the `ValidatorPlugIn` defined in the struts-config.xml file. This is based on the code in the corresponding class of the Struts HTML tag library, modified as needed to reflect differences in the way JavaServer Faces renders field identifiers.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.faces.taglib.JavascriptValidatorTag)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` bundle`
           The servlet context attribute key for our resources.

`protected  String`

` cdata`
           Hide JavaScript methods in a CDATA section for XHTML when "true".

`protected static Locale`

` defaultLocale`
           **Deprecated.** *This variable is no longer used.*

`protected  String`

` dynamicJavascript`
           The dynamic JavaScript objects will only be generated if this is set to "true".

`protected  String`

` formName`
           The name of the form that corresponds with the action name in struts-config.xml.

`protected  String`

`.html.mdComment`
           The JavaScript methods will enclosed with.html.md comments if this is set to "true".

`protected static String`

` lineEnd`
           The line ending string.

`protected  String`

` methodName`
           This will be used as is for the JavaScript validation method name if it has a value.

`protected  int`

` page`
           The current page number of a multi-part form.

`protected  String`

` src`
           The src attribute for.html.md script element (used to include an external script resource).

`protected  String`

` staticJavascript`
           The static JavaScript methods will only be printed if this is set to "true".

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bodyContent`                                                                                                                                                                                                                   |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id, pageContext`                                                                                                                                                                                                       |

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

| **Constructor Summary**     |
|-----------------------------|
| ` JavascriptValidatorTag()` 
                              |

  <span id="method_summary"></span>

**Method Summary**

` int`

` doStartTag()`
           Render the JavaScript for to perform validations based on the form name.

` String`

` getCdata()`
           Returns the cdata setting "true" or "false".

` String`

` getDynamicJavascript()`
           Gets whether or not to generate the dynamic JavaScript.

` String`

` getFormName()`
           Gets the key (form name) that will be used to retrieve a set of validation rules to be performed on the bean passed in for validation.

` String`

` getHtmlComment()`
           Gets whether or not to delimit the JavaScript with.html.md comments.

`protected  String`

` getJavascriptBegin(String methods)`
           Returns the opening script element and some initial javascript.

`protected  String`

` getJavascriptEnd()`
           Returns the closing script element.

`protected  String`

` getJavascriptStaticMethods(ValidatorResources resources)`
            

` String`

` getMethod()`
           Gets the method name that will be used for the Javascript validation method name if it has a value.

` int`

` getPage()`
           Gets the current page number of a multi-part form.

` String`

` getSrc()`
           Gets the src attribute's value when defining the.html.md script element.

` String`

` getStaticJavascript()`
           Gets whether or not to generate the static JavaScript.

` void`

` release()`
           Release any acquired resources.

` void`

` setCdata(String cdata)`
           Sets the cdata status.

` void`

` setDynamicJavascript(String dynamicJavascript)`
           Sets whether or not to generate the dynamic JavaScript.

` void`

` setFormName(String formName)`
           Sets the key (form name) that will be used to retrieve a set of validation rules to be performed on the bean passed in for validation.

` void`

` setHtmlComment(String�.html.mdComment)`
           Sets whether or not to delimit the JavaScript with.html.md comments.

` void`

` setMethod(String methodName)`
           Sets the method name that will be used for the Javascript validation method name if it has a value.

` void`

` setPage(int page)`
           Sets the current page number of a multi-part form.

` void`

` setSrc(String src)`
           Sets the src attribute's value when defining the.html.md script element.

` void`

` setStaticJavascript(String staticJavascript)`
           Sets whether or not to generate the static JavaScript.

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.BodyTagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, doEndTag, doInitBody, getBodyContent, getPreviousOut, setBodyContent`                                                                                                                                              |

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

<span id="bundle"></span>

### bundle

    protected String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

<span id="defaultLocale"></span>

### defaultLocale

    protected static Locale defaultLocale

**Deprecated.** *This variable is no longer used.*

The default locale on our server.

------------------------------------------------------------------------

<span id="formName"></span>

### formName

    protected String formName

The name of the form that corresponds with the action name in struts-config.xml. Specifying a form name places a \<script\> \</script\> around the javascript.

------------------------------------------------------------------------

<span id="lineEnd"></span>

### lineEnd

    protected static String lineEnd

The line ending string.

------------------------------------------------------------------------

<span id="page"></span>

### page

    protected int page

The current page number of a multi-part form. Only valid when the formName attribute is set.

------------------------------------------------------------------------

<span id="methodName"></span>

### methodName

    protected String methodName

This will be used as is for the JavaScript validation method name if it has a value. This is the method name of the main JavaScript method that the form calls to perform validations.

------------------------------------------------------------------------

<span id="staticJavascript"></span>

### staticJavascript

    protected String staticJavascript

The static JavaScript methods will only be printed if this is set to "true".

------------------------------------------------------------------------

<span id="dynamicJavascript"></span>

### dynamicJavascript

    protected String dynamicJavascript

The dynamic JavaScript objects will only be generated if this is set to "true".

------------------------------------------------------------------------

<span id="src"></span>

### src

    protected String src

The src attribute for.html.md script element (used to include an external script resource). The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

<span id=.html.mdComment"></span>

###.html.mdComment

    protected String.html.mdComment

The JavaScript methods will enclosed with.html.md comments if this is set to "true".

------------------------------------------------------------------------

<span id="cdata"></span>

### cdata

    protected String cdata

Hide JavaScript methods in a CDATA section for XHTML when "true".

<span id="constructor_detail"></span>

**Constructor Detail**

### JavascriptValidatorTag

    public JavascriptValidatorTag()

<span id="method_detail"></span>

**Method Detail**

### getFormName

    public String getFormName()

Gets the key (form name) that will be used to retrieve a set of validation rules to be performed on the bean passed in for validation.

------------------------------------------------------------------------

### setFormName

    public void setFormName(String formName)

Sets the key (form name) that will be used to retrieve a set of validation rules to be performed on the bean passed in for validation. Specifying a form name places a \<script\> \</script\> tag around the javascript.

------------------------------------------------------------------------

### getPage

    public int getPage()

Gets the current page number of a multi-part form. Only field validations with a matching page numer will be generated that match the current page number. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### setPage

    public void setPage(int page)

Sets the current page number of a multi-part form. Only field validations with a matching page numer will be generated that match the current page number. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### getMethod

    public String getMethod()

Gets the method name that will be used for the Javascript validation method name if it has a value. This overrides the auto-generated method name based on the key (form name) passed in.

------------------------------------------------------------------------

### setMethod

    public void setMethod(String methodName)

Sets the method name that will be used for the Javascript validation method name if it has a value. This overrides the auto-generated method name based on the key (form name) passed in.

------------------------------------------------------------------------

### getStaticJavascript

    public String getStaticJavascript()

Gets whether or not to generate the static JavaScript. If this is set to 'true', which is the default, the static JavaScript will be generated.

------------------------------------------------------------------------

### setStaticJavascript

    public void setStaticJavascript(String staticJavascript)

Sets whether or not to generate the static JavaScript. If this is set to 'true', which is the default, the static JavaScript will be generated.

------------------------------------------------------------------------

### getDynamicJavascript

    public String getDynamicJavascript()

Gets whether or not to generate the dynamic JavaScript. If this is set to 'true', which is the default, the dynamic JavaScript will be generated.

------------------------------------------------------------------------

### setDynamicJavascript

    public void setDynamicJavascript(String dynamicJavascript)

Sets whether or not to generate the dynamic JavaScript. If this is set to 'true', which is the default, the dynamic JavaScript will be generated.

------------------------------------------------------------------------

### getHtmlComment

    public String getHtmlComment()

Gets whether or not to delimit the JavaScript with.html.md comments. If this is set to 'true', which is the default, the htmlComment will be surround the JavaScript.

------------------------------------------------------------------------

### setHtmlComment

    public void setHtmlComment(String.html.mdComment)

Sets whether or not to delimit the JavaScript with.html.md comments. If this is set to 'true', which is the default, the htmlComment will be surround the JavaScript.

------------------------------------------------------------------------

### getSrc

    public String getSrc()

Gets the src attribute's value when defining the.html.md script element.

------------------------------------------------------------------------

### setSrc

    public void setSrc(String src)

Sets the src attribute's value when defining the.html.md script element. The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Render the JavaScript for to perform validations based on the form name.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `BodyTagSupport`

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
`release` in class `BodyTagSupport`

------------------------------------------------------------------------

### getJavascriptBegin

    protected String getJavascriptBegin(String methods)

Returns the opening script element and some initial javascript.

------------------------------------------------------------------------

### getJavascriptStaticMethods

    protected String getJavascriptStaticMethods(ValidatorResources resources)

------------------------------------------------------------------------

### getJavascriptEnd

    protected String getJavascriptEnd()

Returns the closing script element.

------------------------------------------------------------------------

### getCdata

    public String getCdata()

Returns the cdata setting "true" or "false".

**Returns:**  
String - "true" if JavaScript will be hidden in a CDATA section

------------------------------------------------------------------------

### setCdata

    public void setCdata(String cdata)

Sets the cdata status.

**Parameters:**  
`cdata` - The cdata to set

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
<td align="left"><a href="class-use/JavascriptValidatorTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/faces/taglib/HtmlTag.html.md" title="class in org.apache.struts.faces.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/faces/taglib/LoadMessagesTag.html" title="class in org.apache.struts.faces.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/faces/taglib/JavascriptValidatorTag.html"><strong>FRAMES</strong></a>    <a href="JavascriptValidatorTag.html"><strong>NO FRAMES</strong></a>    
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
