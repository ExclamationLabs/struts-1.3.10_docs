<span id="navbar_top"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

Struts-Faces
------------

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix="Struts-Faces" uri="http://struts.apache.org/tags-faces" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:Struts-Faces="http://struts.apache.org/tags-faces" />`

------------------------------------------------------------------------


    This tag library provides custom action functionality that is similar to that provided by the Struts 1.1 tag libraries, but is built on top of the JavaServer Faces rendering architecture. 
    This tag library includes the following tags:

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

Struts-Faces

URI

http://struts.apache.org/tags-faces

 

**Tag Summary**

**[base](base.html.md)**

Renders an HTML `<base>` element with an `href` attribute pointing to the absolute location of the enclosing JSP page. This tag is valid only when nested inside an HTML `<head>` element. This tag is useful because it allows you to use relative URL references that are based on the URL of the page itself, rather than the URL to which the most recent submit took place.

**[commandLink](commandLink.html.md)**

Renders an HTML `<a>` element defining a hyperlink that submits the current form. This component is required because the JSF 1.0 and 1.1 specifications require interoperability between the renderers for the form element and the command link element, without providing a portable mechanism to allow intermixed libraries.

**[errors](errors.html.md)**

Displays a list of error messages prepared by form bean or business logic validation processing.

In order to use this component successfully, you must have defined an application scope `MessageResources` bean under the specified attribute name, with optinal definitions for the following message keys:

**[form](form.html.md)**

Render an HTML form element containing the nested components to present the appropriate label and input field elements. This tag is distinguished from the tag in the standard HTML RenderKit because it accepts a Struts `<action>` path as a parameter, and triggers the creation of a Struts form bean if needed.

**.html.md](html.html)**

Renders an HTML `.html.md>` element with language attributes extracted from the user's current Locale object, if there is one.

**[javascript](javascript.html.md)**

**IMPLEMENTATION NOTE** - Unlike other tags in this tag library, this does not correspond to a JavaServer Faces user interface component. It is based on the tag implementation class used in the `struts.html.md` tag library.

Render JavaScript validation based on the validation rules loaded by the `ValidatorPlugIn`. The set of validation rules that should be generated is based on the formName attribute passed in, which should match the name attribute of the form element in the xml file.

The dynamicJavascript and staticJavascript attributes default to true, but if dynamicJavascript is set to `true` and staticJavascript is set to `false` then only the dynamic JavaScript will be rendered. If dynamicJavascript is set to `false` and staticJavascript is set to `true` then only the static JavaScript will be rendered which can then be put in separate JSP page so the browser can cache the static JavaScript.

**[loadMessages](loadMessages.html.md)**

Create a Map wrapping the specified MessageResources instance, which will return localized messages based on the Locale stored in the view root component of the current view.

**[message](message.html.md)**

Render the message text looked up from a message resources bundle, based on our current locale. The message key must be specified by exactly one of the following attributes:

The `MessageResources` bundle to be used is specified by the `bundle` attribute, as follows:

Substitution parameters for the message may be nested inside this tag by using the `parameter` tag from the standard HTML RenderKit tag library.

Additional control over the rendering process is specified by the following optional attributes, with default values as indicated:

**[stylesheet](stylesheet.html.md)**

Renders an HTML `<link>` element with a relative reference to a `text/css` stylesheet at the specified context-relative path.

**[write](write.html.md)**

Render the text associated with the specified model object or text string, optionally performing filtering and formatting tasks described by the optional attributes described below. The text to be rendered is specified in exactly one of the following attributes:

Additional control over the rendering process is specified by the following optional attributes, with default values as indicated:

  <span id="navbar_bottom"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-3 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
