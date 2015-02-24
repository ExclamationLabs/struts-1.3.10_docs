<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Faces

-   [Welcome](index.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)
    -   [Checkstyle](checkstyle.html.md)
    -   [CPD Report](cpd.html.md)
    -   [JavaDocs](apidocs/index.html.md)
    -   [PMD Report](pmd.html.md)
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)
    -   [Taglibdoc documentation](tlddoc/index.html.md)
    -   [Tag library validation](taglibvalidation.html.md)
    -   **Tag reference**
    -   [Test JavaDocs](testapidocs/index.html.md)
    -   [Test Source Xref](xref-test/index.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Tag reference sheet
-------------------

Tag library reference for the following tag libraries:

-   [Struts-Faces (struts-faces.tld)](#struts-faces.tld) - uri: http://struts.apache.org/tags-faces

<span id="struts-faces.tld"></span>
Struts-Faces
------------

This tag library provides custom action functionality that is similar to that provided by the Struts 1.1 tag libraries, but is built on top of the JavaServer Faces rendering architecture.

This tag library includes the following tags:

This is version 1.3.

-   [base](#Struts-Faces:base) Renders an HTML &lt;base&gt; element with an href attribute pointing to the absolute location of the enclosing JSP page
-   [commandLink](#Struts-Faces:commandLink) Renders an HTML &lt;a&gt; element defining a hyperlink that submits the current form
-   [errors](#Struts-Faces:errors) Displays a list of error messages prepared by form bean or business logic validation processing
-   [form](#Struts-Faces:form) Render an HTML form element containing the nested components to present the appropriate label and input field elements
-   .html.md](#Struts-Faces:html) Renders an HTML &lt;html&gt; element with language attributes extracted from the user's current Locale object, if there is one
-   [javascript](#Struts-Faces:javascript) IMPLEMENTATION NOTE - Unlike other tags in this tag library, this does not correspond to a JavaServer Faces user interface component
-   [loadMessages](#Struts-Faces:loadMessages) Create a Map wrapping the specified MessageResources instance, which will return localized messages based on the Locale stored in the view root component of the current view
-   [message](#Struts-Faces:message) Render the message text looked up from a message resources bundle, based on our current locale
-   [stylesheet](#Struts-Faces:stylesheet) Renders an HTML &lt;link&gt; element with a relative reference to a text/css stylesheet at the specified context-relative path
-   [write](#Struts-Faces:write) Render the text associated with the specified model object or text string, optionally performing filtering and formatting tasks described by the optional attributes described below

Required attributes are marked with a **\***

<span id="Struts-Faces:base"></span>
### \<Struts-Faces:base\>

Renders an HTML `<base>` element with an `href` attribute pointing to the absolute location of the enclosing JSP page. This tag is valid only when nested inside an HTML `<head>` element. This tag is useful because it allows you to use relative URL references that are based on the URL of the page itself, rather than the URL to which the most recent submit took place.

Can contain:

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left">Component id of this component.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">target</td>
<td align="left">Target frame for this base reference.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:commandLink"></span>
### \<Struts-Faces:commandLink\>

Renders an HTML `<a>` element defining a hyperlink that submits the current form. This component is required because the JSF 1.0 and 1.1 specifications require interoperability between the renderers for the form element and the command link element, without providing a portable mechanism to allow intermixed libraries.

Can contain:

#### Attributes

| Name           | Description | Type   |
|----------------|-------------|--------|
| accesskey      | null        | String |
| action         | null        | String |
| actionListener | null        | String |
| charset        | null        | String |
| dir            | null        | String |
| hreflang       | null        | String |
| id             | null        | String |
| immediate      | null        | String |
| lang           | null        | String |
| onblur         | null        | String |
| onclick        | null        | String |
| ondblclick     | null        | String |
| onfocus        | null        | String |
| onkeydown      | null        | String |
| onkeypress     | null        | String |
| onkeyup        | null        | String |
| onmousedown    | null        | String |
| onmousemove    | null        | String |
| onmouseout     | null        | String |
| onmouseover    | null        | String |
| onmouseup      | null        | String |
| rel            | null        | String |
| rendered       | null        | String |
| rev            | null        | String |
| style          | null        | String |
| styleClass     | null        | String |
| tabindex       | null        | String |
| target         | null        | String |
| title          | null        | String |
| type           | null        | String |
| value          | null        | String |

<span id="Struts-Faces:errors"></span>
### \<Struts-Faces:errors\>

Displays a list of error messages prepared by form bean or business logic validation processing.

In order to use this component successfully, you must have defined an application scope `MessageResources` bean under the specified attribute name, with optinal definitions for the following message keys:

Can contain:

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left"><p>Name of the servlet context attribute under which the desired <code>MessageResources</code> bundle is stored. If not specified, the default bundle for this sub-application will be used.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">id</td>
<td align="left">Component id of this component.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left">Component of the component for which to render errors. If not specified, all messages (regardless of property) are displayed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:form"></span>
### \<Struts-Faces:form\>

Render an HTML form element containing the nested components to present the appropriate label and input field elements. This tag is distinguished from the tag in the standard HTML RenderKit because it accepts a Struts `<action>` path as a parameter, and triggers the creation of a Struts form bean if needed.

Can contain:

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>action*</strong></td>
<td align="left"><p>Struts <code>Action</code> to which this form should be submitted. This value must exactly match the <code>path</code> attribute of the corresponding <code>&lt;action&gt;</code> element in the <code>struts-config.xml</code> configuration file for this application module.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">enctype</td>
<td align="left"><p>The content encoding to be used to submit this form, if the method is <code>POST</code>. This must be set to &quot;<code>multipart/form-data</code>&quot; if your form includes file upload field(s). If not specified, the browser default (&quot;<code>application/x-www-form-urlencoded</code>&quot;) is used.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">focus</td>
<td align="left"><p>The identifier of the form field that should receive focus when this form is rendered.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">focusIndex</td>
<td align="left"><p>If the focus field is an array, such as a radio button group, you can specify the index of the array element to receive focus.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left">Component id of this component.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onreset</td>
<td align="left"><p>JavaScript event handler executed if this form is reset.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onsubmit</td>
<td align="left"><p>JavaScript event handler executed if this form is submitted.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS style class to use when rendering this component.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">target</td>
<td align="left"><p>Window target to which this form is submitted, such as for use in framed presentations.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces.html.md"></span>
### \<Struts-Faces.html.md\>

Renders an HTML `.html.md>` element with language attributes extracted from the user's current Locale object, if there is one.

Can contain: JSP

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left">Component id of this component.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">locale</td>
<td align="left"><p>Set to <code>true</code> in order to record a <code>Locale</code> based on the current request's <code>Accept-Language</code> header (if any), if none has currently been set.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">.html.md</td>
<td align="left"><p>Set to <code>true</code> to render an <code>xml:lang</code> element on the generated <code.html.md</code> element. It also causes nested Struts HTML tags (although not JavaServer Faces component tags) to render themselves as xhtml.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:javascript"></span>
### \<Struts-Faces:javascript\>

**IMPLEMENTATION NOTE** - Unlike other tags in this tag library, this does not correspond to a JavaServer Faces user interface component. It is based on the tag implementation class used in the `struts.html.md` tag library.

Render JavaScript validation based on the validation rules loaded by the `ValidatorPlugIn`. The set of validation rules that should be generated is based on the formName attribute passed in, which should match the name attribute of the form element in the xml file.

The dynamicJavascript and staticJavascript attributes default to true, but if dynamicJavascript is set to `true` and staticJavascript is set to `false` then only the dynamic JavaScript will be rendered. If dynamicJavascript is set to `false` and staticJavascript is set to `true` then only the static JavaScript will be rendered which can then be put in separate JSP page so the browser can cache the static JavaScript.

Can contain:

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">cdata</td>
<td align="left"><p>If set to &quot;true&quot; and XHTML has been enabled, the JavaScript will be wrapped in a CDATA section to prevent XML parsing. The default is &quot;true&quot; to comply with the W3C's recommendation.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">dynamicJavascript</td>
<td align="left"><p>Whether or not to render the dynamic JavaScript. Defaults to <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">formName</td>
<td align="left"><p>The key (form name) to retrieve a specific set of validation rules.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left".html.mdComment</td>
<td align="left"><p>Whether or not to enclose the javascript with HTML comments. This attribute is ignored in XHTML mode because the script would be deleted by the XML parser. See the cdata attribute for details on hiding scripts from XML parsers. Defaults to <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left"><p>The alternate JavaScript method name to be used instead of the of the default. The default is 'validate' concatenated in front of the key (form name) passed in (ex: validateRegistrationForm).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The current page of a set of validation rules if the page attribute for the field element in the xml file is in use.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">src</td>
<td align="left"><p>The src attribute's value when defining the.html.md script element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">staticJavascript</td>
<td align="left"><p>Whether or not to render the static JavaScript. Defaults to <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:loadMessages"></span>
### \<Struts-Faces:loadMessages\>

Create a Map wrapping the specified MessageResources instance, which will return localized messages based on the Locale stored in the view root component of the current view.

Can contain: empty

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">messages</td>
<td align="left"><p>Application scope key containing the MessageResources instance to be exposed. If not specified, the default MessageResources instance for the current application module is exposed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>var*</strong></td>
<td align="left"><p>Request scope key under which the Map will be stored.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:message"></span>
### \<Struts-Faces:message\>

Render the message text looked up from a message resources bundle, based on our current locale. The message key must be specified by exactly one of the following attributes:

The `MessageResources` bundle to be used is specified by the `bundle` attribute, as follows:

Substitution parameters for the message may be nested inside this tag by using the `parameter` tag from the standard HTML RenderKit tag library.

Additional control over the rendering process is specified by the following optional attributes, with default values as indicated:

Can contain: JSP

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left"><p>Name of the servlet context attribute under which the desired <code>MessageResources</code> bundle is stored. If not specified, the default bundle for this sub-application will be used.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">filter</td>
<td align="left"><p>Should we filter the output for characters that are sensitive in HTML? The default value is <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left"><p>Component identifier of the component corresponding to this tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">key</td>
<td align="left"><p>Literal value of the message key to look up. Exactly one of <code>key</code> and <code>value</code> must be specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles used to render this component.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>Name of the CSS style class used to render this component.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left"><p>Value reference expression used to retrieve a dynamic value for the message key to look up. Exactly one of <code>key</code> and <code>value</code> must be specified.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:stylesheet"></span>
### \<Struts-Faces:stylesheet\>

Renders an HTML `<link>` element with a relative reference to a `text/css` stylesheet at the specified context-relative path.

Can contain:

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left">Component id of this component.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>path*</strong></td>
<td align="left">Context-relative path to the resource for this relative link.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="Struts-Faces:write"></span>
### \<Struts-Faces:write\>

Render the text associated with the specified model object or text string, optionally performing filtering and formatting tasks described by the optional attributes described below. The text to be rendered is specified in exactly one of the following attributes:

Additional control over the rendering process is specified by the following optional attributes, with default values as indicated:

Can contain: empty

#### Attributes

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Description</th>
<th align="left">Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">binding</td>
<td align="left"><p>Value binding expression to bind this component to a backing bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">filter</td>
<td align="left"><p>Should we filter the output for characters that are sensitive in HTML? The default value is <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">id</td>
<td align="left"><p>Component identifier of the component corresponding to this tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">rendered</td>
<td align="left">Boolean attribute indicating whether this component should be rendered or not.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles used to render this component.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>Name of the CSS style class used to render this component.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left"><p>Literal text to be rendered, or value reference expression to retrieve the text to be rendered.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


