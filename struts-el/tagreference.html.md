<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts EL

-   [Welcome](index.html.md)

##### Reference

-   [Bean EL](tagreference.html.md#struts-bean-el.tld)
-   [HTML EL](tagreference.html.md#struts-html-el.tld)
-   [Logic EL](tagreference.html.md#struts-logic-el.tld)
-   [Tiles EL](tagreference.html.md#struts-tiles-el.tld)
-   [Javadoc](apidocs/index.html.md)

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

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Tag reference sheet
-------------------

Tag library reference for the following tag libraries:

-   [bean (struts-bean-el.tld)](#struts-bean-el.tld) - uri: http://struts.apache.org/tags-bean-el
-   .html.md (struts-html-el.tld)](#struts-html-el.tld) - uri: http://struts.apache.org/tags-html-el
-   [logic (struts-logic-el.tld)](#struts-logic-el.tld) - uri: http://struts.apache.org/tags-logic-el
-   [tiles (struts-tiles-el.tld)](#struts-tiles-el.tld) - uri: http://struts.apache.org/tags-tiles-el

<span id="struts-bean-el.tld"></span>
bean
----

This tag library contains tags useful in accessing beans and their properties, as well as defining new beans (based on these accesses) that are accessible to the remainder of the page via scripting variables and page scope attributes. Convenient mechanisms to create new beans based on the value of request cookies, headers, and parameters are also provided.Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the `<%@ page %>` directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.If you are viewing this page from within the Struts Documentation Application (or online at http://struts.apache.org), you can learn more about using these tags in the Bean Tags Developer's Guide.

This is version 1.3.

-   [include](#bean:include) Load the response from a dynamic application request and make it available as a bean
-   [message](#bean:message) Render an internationalized message string to the response
-   [page](#bean:page) Expose a specified item from the page context as a bean
-   [resource](#bean:resource) Load a web application resource and make it available as a bean
-   [size](#bean:size) Define a bean containing the number of elements in a Collection or Map
-   [struts](#bean:struts) Expose a named Struts internal configuration object as a bean

Required attributes are marked with a **\***

<span id="bean:include"></span>
### \<bean:include\>

**Load the response from a dynamic application request and make it available as a bean.**

Perform an internal dispatch to the specified application component (or external URL) and make the response data from that request available as a scoped variable of type `String`. This tag has a function similar to that of the standard `<jsp:include>` tag, except that the response data is stored in a page scope attribute instead of being written to the output stream. If the current request is part of a session, the generated request for the include will also include the session identifier (and thus be part of the same session).

The URL used to access the specified application component is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged (since this might link to a resource external to the application, the session identifier is **not** included.
-   *page* - Use the value of this attribute as an module-relative URI to the desired resource.

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
<td align="left">anchor</td>
<td align="left"><p>Optional anchor tag (&quot;#xxx&quot;) to be added to the generated hyperlink. Specify this value <strong>without</strong> any &quot;#&quot; character.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">forward</td>
<td align="left"><p>Logical name of a global <code>ActionForward</code> that contains the actual content-relative URI of the resource to be included.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">href</td>
<td align="left"><p>Absolute URL (including the appropriate protocol prefix such as &quot;http:&quot;) of the resource to be included. Because this URL could be external to the current web application, the session identifier will <strong>not</strong> be included in the request.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>id*</strong></td>
<td align="left"><p>Specifies the name of the scripting variable (and associated page scope attribute) that will be made available with the value of the specified web application resource.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">page</td>
<td align="left"><p>Module-relative URI (starting with a '/') of the web application resource to be included.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">transaction</td>
<td align="left"><p>Set to <code>true</code> if you want the current transaction control token included in the generated URL for this include.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="bean:message"></span>
### \<bean:message\>

**Render an internationalized message string to the response.**

Retrieves an internationalized message for the specified locale, using the specified message key, and write it to the output stream. Up to five parametric replacements (such as "{0}") may be specified.

The message key may be specified directly, using the `key` attribute, or indirectly, using the `name` and `property` attributes to obtain it from a bean.

**JSTL**: The equivalent JSTL tag is `<fmt:message>`. For example, `<fmt:message key="my.msg.key"> <fmt:param value="replacement text"/> </fmt:message>`

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
<td align="left">arg0</td>
<td align="left"><p>First parametric replacement value, if any.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">arg1</td>
<td align="left"><p>Second parametric replacement value, if any.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">arg2</td>
<td align="left"><p>Third parametric replacement value, if any.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">arg3</td>
<td align="left"><p>Fourth parametric replacement value, if any.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">arg4</td>
<td align="left"><p>Fifth parametric replacement value, if any.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left"><p>The name of the application scope bean under which the <code>MessageResources</code> object containing our messages is stored.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">key</td>
<td align="left"><p>The message key of the requested message, which must have a corresponding value in the message resources. If not specified, the key is obtained from the <code>name</code> and <code>property</code> attributes.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">locale</td>
<td align="left"><p>The name of the session scope bean under which our currently selected <code>Locale</code> object is stored.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>Specifies the attribute name of the bean whose property is accessed to retrieve the value specified by <code>property</code> (if specified). If <code>property</code> is not specified, the value of this bean itself will be used as the message resource key.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left"><p>Specifies the name of the property to be accessed on the bean specified by <code>name</code>. This value may be a simple, indexed, or nested property reference expression. If not specified, the value of the bean identified by <code>name</code> will itself be used as the message resource key.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>Specifies the variable scope searched to retrieve the bean specified by <code>name</code>. If not specified, the default rules applied by <code>PageContext.findAttribute()</code> are applied.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="bean:page"></span>
### \<bean:page\>

**Expose a specified item from the page context as a bean.**

Retrieve the value of the specified item from the page context for this page, and define it as a scripting variable, and a page scope attribute accessible to the remainder of the current page.

If a problem occurs while retrieving the specified configuration object, a request time exception will be thrown.

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
<td align="left"><strong>id*</strong></td>
<td align="left"><p>Specifies the name of the scripting variable (and associated page scope attribute) that will be made available with the value of the specified page context property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>property*</strong></td>
<td align="left"><p>Name of the property from our page context to be retrieved and exposed. Must be one of <code>application</code>, <code>config</code>, <code>request</code>, <code>response</code>, or <code>session</code>.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="bean:resource"></span>
### \<bean:resource\>

**Load a web application resource and make it available as a bean.**

Retrieve the value of the specified web application resource, and make it available as either a `InputStream` or a `String`, depending on the value of the `input` attribute.

If a problem occurs while retrieving the specified resource, a request time exception will be thrown.

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
<td align="left"><strong>id*</strong></td>
<td align="left"><p>Specifies the name of the scripting variable (and associated page scope attribute) that will be made available with the value of the specified web application resource.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">input</td>
<td align="left"><p>If any arbitrary value for this attribute is specified, the resource will be made available as an <code>InputStream</code>. If this attribute is not specified, the resource will be made available as a <code>String</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>name*</strong></td>
<td align="left"><p>Module-relative name (starting with a '/') of the web application resource to be loaded and made available.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="bean:size"></span>
### \<bean:size\>

**Define a bean containing the number of elements in a Collection or Map.**

Given a reference to an array, Collection or Map, creates a new bean, of type `java.lang.Integer`, whose value is the number of elements in that collection. You can specify the collection to be counted in any one of the following ways:

-   As a runtime expression specified as the value of the `collection` attribute.
-   As a JSP bean specified by the `name` attribute.
-   As the property, specified by the `property` attribute, of the JSP bean specified by the `name` attribute.

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
<td align="left">collection</td>
<td align="left"><p>A runtime expression that evaluates to an array, a Collection, or a Map.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>id*</strong></td>
<td align="left"><p>The name of a page scope JSP bean, of type <code>java.lang.Integer</code>, that will be created to contain the size of the underlying collection being counted.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The name of the JSP bean (optionally constrained to the scope specified by the <code>scope</code> attribute) that contains the collection to be counted (if <code>property</code> is not specified), or whose property getter is called to return the collection to be counted (if <code>property</code> is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left"><p>The name of the property, of the bean specified by the <code>name</code> attribute, whose getter method will return the collection to be counted.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the JSP bean specified by the <code>name</code> attribute. If not specified, the available scopes are searched in ascending sequence.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="bean:struts"></span>
### \<bean:struts\>

**Expose a named Struts internal configuration object as a bean.**

Retrieve the value of the specified Struts internal configuration object, and define it as a scripting variable and as a page scope attribute accessible to the remainder of the current page. You must specify exactly one of the `formBean`, `forward`, and `mapping` attributes to select the configuration object to be exposed.

If a problem occurs while retrieving the specified configuration object, a request time exception will be thrown.

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
<td align="left">formBean</td>
<td align="left"><p>Specifies the name of the Struts <code>ActionFormBean</code> definition object to be exposed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">forward</td>
<td align="left"><p>Specifies the name of the global Struts <code>ActionForward</code> definition object to be exposed.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>id*</strong></td>
<td align="left"><p>Specifies the name of the scripting variable (and associated page scope attribute) that will be made available with the value of the specified Struts internal configuration object.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">mapping</td>
<td align="left"><p>Specifies the matching path of the Struts <code>ActionMapping</code> definition object to be exposed.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="struts.html.md-el.tld"></span>
html
----

This taglib contains tags used to create struts input forms, as well as other tags generally useful in the creation of HTML-based user interfaces. Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the \<%@ page %\> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

This is version 1.3.

-   [base](.html.md:base) Render an HTML &lt;base&gt; Element Renders an HTML &lt;base&gt; element with an href attribute pointing to the absolute location of the enclosing JSP page
-   [button](.html.md:button) Render A Button Input Field Renders an HTML &lt;input&gt; element of type button, populated from the specified value or the content of this tag body
-   [cancel](.html.md:cancel) Render a Cancel Button Renders an HTML &lt;input&gt; element of type submit
-   [checkbox](.html.md:checkbox) Render A Checkbox Input Field Renders an HTML &lt;input&gt; element of type checkbox, populated from the specified value or the specified property of the bean associated with our current form
-   [errors](.html.md:errors) Conditionally display a set of accumulated error messages
-   [file](.html.md:file) Render A File Select Input Field Renders an HTML &lt;input&gt; element of type file, defaulting to the specified value or the specified property of the bean associated with our current form
-   [form](.html.md:form) Define An Input Form Renders an HTML &lt;form&gt; element whose contents are described by the body content of this tag
-   [frame](.html.md:frame) Render an HTML frame element Renders an HTML &lt;frame&gt; element with processing for the src attribute that is identical to that performed by the &lt;html:link&gt; tag for the href attribute
-   [hidden](.html.md:hidden) Render A Hidden Field Renders an HTML &lt;input&gt; element of type hidden, populated from the specified value or the specified property of the bean associated with our current form
-   .html.md](#html:html) Render an HTML &lt;html&gt; Element Renders an HTML &lt;html&gt; element with language attributes extracted from the user's current Locale object, if there is one
-   [image](.html.md:image) Render an input tag of type "image" Renders an HTML &lt;input&gt; tag of type "image"
-   [img](.html.md:img) Render an HTML img tag Renders an HTML &lt;img&gt; element with the image at the specified URL
-   [javascript](.html.md:javascript) Render JavaScript validation based on the validation rules loaded by the ValidatorPlugIn
-   [link](.html.md:link) Render an HTML anchor or hyperlink Renders an HTML &lt;a&gt; element as an anchor definition (if "linkName" is specified) or as a hyperlink to the specified URL
-   [messages](.html.md:messages) Conditionally display a set of accumulated messages
-   [multibox](.html.md:multibox) Render A Checkbox Input Field Renders an HTML &lt;input&gt; element of type checkbox, whose "checked" status is initialized based on whether the specified value matches one of the elements of the underlying property's array of current values
-   [option](.html.md:option) Render A Select Option Render an HTML &lt;option&gt; element, representing one of the choices for an enclosing &lt;select&gt; element
-   [options](.html.md:options) Render a Collection of Select Options Renders a set of HTML &lt;option&gt; elements, representing possible choices for a &lt;select&gt; element
-   [optionsCollection](.html.md:optionsCollection) Render a Collection of Select Options Renders a set of HTML &lt;option&gt; elements, representing possible choices for a &lt;select&gt; element
-   [param](.html.md:param) Adds a parameter to the following tags: &lt;html:frame&gt; &lt;html:link&gt; &lt;html:rewrite&gt; Since: Struts 1
-   [password](.html.md:password) Render A Password Input Field Renders an HTML &lt;input&gt; element of type password, populated from the specified value or the specified property of the bean associated with our current form
-   [radio](.html.md:radio) Render A Radio Button Input Field Renders an HTML &lt;input&gt; element of type radio, populated from the specified property of the bean associated with our current form
-   [reset](.html.md:reset) Render A Reset Button Input Field Renders an HTML &lt;input&gt; element of type reset
-   [rewrite](.html.md:rewrite) Render an URI Renders a request URI based on exactly the same rules as the link tag does, but without creating the &lt;a&gt; hyperlink
-   [select](.html.md:select) Render A Select Element Renders an HTML &lt;select&gt; element, associated with a bean property specified by our attributes
-   [submit](.html.md:submit) Render A Submit Button Renders an HTML &lt;input&gt; element of type submit If a graphical button is needed (a button with an image), then the image tag is more appropriate
-   [text](.html.md:text) Render An Input Field of Type text Render an input button of type text
-   [textarea](.html.md:textarea) Render A Textarea Render a textarea element
-   [.html.md](#html:xhtml) Render HTML tags as XHTML Using this tag in a page tells all other html taglib tags to render themselves as XHTML 1

Required attributes are marked with a **\***

<span id=.html.md:base"></span>
### \.html.md:base\>

**Render an HTML `<base>` Element**

Renders an HTML `<base>` element with an `href` attribute pointing to the absolute location of the enclosing JSP page. This tag is valid only when nested inside an HTML `<head>` element.

This tag is useful because it allows you to use relative URL references in the page that are calculated based on the URL of the page itself, rather than the URL to which the most recent submit took place (which is where the browser would normally resolve relative references against).

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
<td align="left">ref</td>
<td align="left"><p>The reference from which the base uri will created. Possible values are:</p>
<ul>
<li><code>page</code> - The base uri will be the jsp page location. (default)</li>
<li><code>site</code> - The base uri will be the application context path.</li>
</ul></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">server</td>
<td align="left"><p>The server name to use instead of request.getServerName().</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">target</td>
<td align="left"><p>The window target for this base reference.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:button"></span>
### \.html.md:button\>

**Render A Button Input Field**

Renders an HTML `<input>` element of type `button`, populated from the specified value or the content of this tag body. This tag is only valid when nested inside a form tag body.

If a graphical button is needed (a button with an image), then the [`image`](#image) tag is more appropriate.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">Value of the label to be placed on this button. This value will also be submitted as the value of the specified request parameter. [Body of this tag (if any), or &quot;Click&quot;]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:cancel"></span>
### \.html.md:cancel\>

**Render a Cancel Button**

Renders an HTML `<input>` element of type submit. This tag is only valid when nested inside a form tag body. Pressing of this submit button causes the action servlet to bypass calling the associated form bean validate() method. The action is called normally.

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
<td align="left">accesskey</td>
<td align="left"><p>The keyboard character used to move focus immediately to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left"><p>Set to <code>true</code></p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value. <strong>WARNING</strong> <em>NOT</em> <code>Action.isCancelled()</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left">Value of the label to be placed on this button. This value will also be submitted as the value of the specified request parameter. [Body of this tag (if any), or &quot;Cancel&quot;]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:checkbox"></span>
### \.html.md:checkbox\>

**Render A Checkbox Input Field**

Renders an HTML `<input>` element of type `checkbox`, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

**NOTE**: The underlying property value associated with this field should be of type `boolean`, and any `value` you specify should correspond to one of the Strings that indicate a true value ("true", "yes", or "on"). If you wish to utilize a set of related String values, consider using the `multibox` tag.

**WARNING**: In order to correctly recognize unchecked checkboxes, the `ActionForm` bean associated with this form must include a statement setting the corresponding boolean property to `false` in the `reset()` method.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left"><p>Set to <code>true</code></p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic:iterate</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left">The value to be transmitted if this checkbox is checked when the form is submitted. If not specified, the value &quot;on&quot; will be returned.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:errors"></span>
### \.html.md:errors\>

**Conditionally display a set of accumulated error messages.**

Displays a set of error messages prepared by a business logic component and stored as an `ActionErrors` object, a String, or a String array in any scope. If such a bean is not found, nothing will be rendered.

In order to use this tag successfully, you must have defined an application scope `MessageResources` bean under the default attribute name, with optional definitions of message keys specified in the following attributes:

-   **header** - Text that will be rendered before the error messages list. Typically, this message text will end with `<ul>` to start the error messages list (default "errors.header").
-   **footer** - Text that will be rendered after the error messages list. Typically, this message text will begin with `</ul>` to end the error messages list (default "errors.footer").
-   **prefix** - Text that will be rendered before each individual error in the list (default "errors.prefix").
-   **suffix** - Text that will be rendered after each individual error in the list (default "errors.suffix").

Can contain: empty

#### Attributes

| Name     | Description                                                                                                                                                                                   | Type   |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| bundle   | The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.                        | String |
| footer   | This value is an optional message resource key that will be printed after the iteration of error messages has finished. Defaults to "errors.footer" if not specified. **Since:** Struts 1.2.5 | String |
| header   | This value is an optional message resource key that will be printed before the iteration of error messages begins. Defaults to "errors.header" if not specified. **Since:** Struts 1.2.5      | String |
| locale   | The session attribute key for the Locale used to select messages to be displayed. If not specified, defaults to the Struts standard value.                                                    | String |
| name     | Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the `Globals.ERROR_KEY`                                                | String |
| prefix   | This value is an optional message resource key that will be printed before an error message. Defaults to "errors.prefix" if not specified. **Since:** Struts 1.2.5                            | String |
| property | Name of the property for which error messages should be displayed. If not specified, all error messages (regardless of property) are displayed.                                               | String |
| suffix   | This value is an optional message resource key that will be printed after an error message. Defaults to "errors.suffix" if not specified. **Since:** Struts 1.2.5                             | String |

<span id=.html.md:file"></span>
### \.html.md:file\>

**Render A File Select Input Field**

Renders an HTML `<input>` element of type file, defaulting to the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

As with the corresponding HTML `<input>` element, the enclosing form element must specify "POST" for the `method` attribute, and "multipart/form-data" for the `enctype` attribute. For example:

        .html.md:form method="POST" enctype="multipart/form-data">
            .html.md:file property="theFile" />
        <.html.md:form>

WARNING: In order to correctly recognize uploaded files, the ActionForm bean associated with this form must include a statement setting the corresponding org.apache.struts.upload.FormFile property to null in the reset() method.

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
<td align="left">accept</td>
<td align="left">Comma-delimited set of content types that the server you submit to knows how to process. This list can be used by the client browser to limit the set of file options that is made available for selection. If not specified, no content type list will be sent.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the &lt.html.md:errors/&gt; tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">maxlength</td>
<td align="left">Maximum number of input characters to accept. This is ignored by most browsers. [No limit]</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">size</td>
<td align="left">Size of the file selection box to be displayed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left"><p>Value to which this field should be initialized. [Use the corresponding bean property value or body content (if any) if property is not specified]</p>
<p><strong>NOTE</strong>: When setting this to some value, whether intentional or as the result (for example) of validation errors forcing the user back to the original jsp, this value is ignored by most browsers (for security reasons). This means that your users will have to re-select any previously selected files when submitting the form. Opera web browser will prompt the user so they have a chance to abort the submit.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:form"></span>
### \.html.md:form\>

**Define An Input Form**

Renders an HTML `<form>` element whose contents are described by the body content of this tag. The form implicitly interacts with the specified request scope or session scope bean to populate the input fields with the current property values from the bean.

The form bean is located, and created if necessary, based on the form bean specification for the associated `ActionMapping`.

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
<td align="left">acceptCharset</td>
<td align="left">The list of character encodings for input data that the server should accept. <strong>Since:</strong> Struts 1.2.2</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">action</td>
<td align="left"><p>The URL to which this form will be submitted. This value is also used to select the ActionMapping we are assumed to be processing, from which we can identify the appropriate form bean and scope. If a value is not provided, the original URI (servletPath) for the request is used.</p>
<p>If you are using extension mapping for selecting the controller servlet, this value should be equal to the <code>path</code> attribute of the corresponding <code>&lt;action&gt;</code> element, optionally followed by the correct extension suffix.</p>
<p>If you are using path mapping to select the controller servlet, this value should be exactly equal to the <code>path</code> attribute of the corresponding <code>&lt;action&gt;</code> element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code> if the Form's input fields should be read only. <strong>Since:</strong> Struts 1.2.7</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">enctype</td>
<td align="left">The content encoding to be used to submit this form, if the method is POST. This must be set to &quot;multipart/form-data&quot; if you are using the file tag to enable file upload. If not specified, the browser default (normally &quot;application/x-www-form-urlencoded&quot;) is used.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">focus</td>
<td align="left">The field name (among the fields on this form) to which initial focus will be assigned with a JavaScript function. If not specified, no special JavaScript for this purpose will be rendered.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">focusIndex</td>
<td align="left">If the focus field is a field array, such as a radio button group, you can specify the index in the array to receive focus. <strong>Since:</strong> Struts 1.1</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">The HTTP method that will be used to submit this request (GET, POST). [POST]</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onreset</td>
<td align="left">JavaScript event handler executed if the form is reset.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onsubmit</td>
<td align="left">JavaScript event handler executed if the form is submitted.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">readonly</td>
<td align="left">Set to <code>true</code> if this input field should be read only. <strong>Since:</strong> Struts 1.2.7</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scriptLanguage</td>
<td align="left">The form's focus &lt;script&gt; element will not contain a language attribute when this is set to false. The default is true but this property is ignored in XHMTL mode. <strong>Since:</strong> Struts 1.2</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">target</td>
<td align="left">Window target to which this form is submitted, such as for use in framed presentations.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:frame"></span>
### \.html.md:frame\>

**Render an HTML frame element**

Renders an HTML `<frame>` element with processing for the `src` attribute that is identical to that performed by the `.html.md:link>` tag for the `href` attribute. URL rewriting will be applied automatically, to maintain session state in the absence of cookies.

The base URL for this frame is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as a module-relative URI, and generate a server-relative URI by including the context path and application prefix.
-   *action* - Use the value of this attribute as the logical name of a global Action that contains the actual content-relative URI of the destination of this transfer.

Normally, the hyperlink you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

Additionally, you can request that the current transaction control token, if any, be included in the generated hyperlink by setting the `transaction` attribute to `true`. You can also request that an anchor ("\#xxx") be added to the end of the URL that is created by any of the above mechanisms, by using the `anchor` attribute.

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
<td align="left">action</td>
<td align="left"><p>Logical name of a global <code>Action</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p>
<p>Additionally, you can specify a <code>module</code> prefix for linking to other modules.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">anchor</td>
<td align="left"><p>Optional anchor tag (&quot;#xxx&quot;) to be added to the generated hyperlink. Specify this value <strong>without</strong> any &quot;#&quot; character.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">forward</td>
<td align="left"><p>Logical name of a global <code>ActionForward</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">frameName</td>
<td align="left"><p>Value for the <code>name</code> attribute of the rendered <code>&lt;frame&gt;</code> element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">frameborder</td>
<td align="left"><p>Should a frame border be generated around this frame (1) or not (0)?</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">href</td>
<td align="left"><p>The URL to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">longdesc</td>
<td align="left"><p>URI of a long description of the frame. This description should supplement the short description provided by the <code>title</code> attribute, and may be particularly useful for non-visual user agents.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">marginheight</td>
<td align="left"><p>The amount of space (in pixels) to be left between the frame's contents and its top and bottom margins.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">marginwidth</td>
<td align="left"><p>The amount of space (in pixels) to be left between the frame's contents and its left and right margins.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">module</td>
<td align="left"><p>Prefix name of a <code>Module</code> that contains the action mapping for the <code>Action</code> that is specified by the <code>action</code> attribute. You <strong>must</strong> specify an <code>action</code> attribute for this to have an effect.</p>
<p><strong>Note:</strong> Use &quot;&quot; to map to the default module.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>The name of a JSP bean that contains a <code>Map</code> representing the query parameters (if <code>property</code> is not specified), or a JSP bean whose property getter is called to return a <code>Map</code> (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">noresize</td>
<td align="left"><p>Should users be disallowed from resizing the frame? (true, false).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The module-relative path (beginning with a &quot;/&quot; character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramId</td>
<td align="left"><p>The name of the request parameter that will be dynamically added to the generated hyperlink. The corresponding value is defined by the <code>paramName</code> and (optional) <code>paramProperty</code> attributes, optionally scoped by the <code>paramScope</code> attribute</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramName</td>
<td align="left"><p>The name of a JSP bean that is a String containing the value for the request parameter named by <code>paramId</code> (if <code>paramProperty</code> is not specified), or a JSP bean whose property getter is called to return a String (if <code>paramProperty</code> is specified). The JSP bean is constrained to the bean scope specified by the <code>paramScope</code> property, if it is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramProperty</td>
<td align="left"><p>The name of a property of the bean specified by the <code>paramName</code> attribute, whose return value must be a String containing the value of the request parameter (named by the <code>paramId</code> attribute) that will be dynamically added to this hyperlink.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramScope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>paramName</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>The name of a property of the bean specified by the <code>name</code> attribute, whose return value must be a <code>java.util.Map</code> containing the query parameters to be added to the hyperlink. You <strong>must</strong> specify the <code>name</code> attribute if you specify this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>name</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scrolling</td>
<td align="left"><p>Should scroll bars be created unconditionally (yes), never (no), or only when needed (auto)?</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">transaction</td>
<td align="left"><p>If set to <code>true</code>, any current transaction control token will be included in the generated hyperlink, so that it will pass an <code>isTokenValid()</code> test in the receiving Action.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:hidden"></span>
### \.html.md:hidden\>

**Render A Hidden Field**

Renders an HTML `<input>` element of type hidden, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of this input field, and the name of the corresponding bean property if value is not specified. The corresponding bean property (if any) must be of type String.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">Value to which this field should be initialized. [Use the corresponding bean property value]</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">write</td>
<td align="left">Should the value of this field also be rendered to the response page to make it visible, in addition to creating an HTML type=&quot;hidden&quot; element? By default, only the hidden element is created.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:html"></span>
### \.html.md:html\>

**Render an HTML `.html.md>` Element**

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
<td align="left">lang</td>
<td align="left">Renders a lang attribute with the locale stored in the user's session. If not found in the session, the language from the <code>Accept-Language</code> <strong>Since:</strong> Struts 1.2</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">.html.md</td>
<td align="left"><p>Set to <code>true</code> in order to render <code>xml:lang</code> and <code>xmlns</code> attributes on the generated <code.html.md</code> element. This also causes all other html tags to render as XHTML 1.0 (the <code>&lt;html:xhtml/&gt;</code> tag has a similar purpose).</p>
<strong>Since:</strong> Struts 1.1</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:image"></span>
### \.html.md:image\>

**Render an input tag of type "image"**

Renders an HTML `<input>` tag of type "image". The base URL for this image is calculated directly based on the value specified in the `src` or `page` attributes, or indirectly by looking up a message resource string based on the `srcKey` or `pageKey` attributes. You **must** specify exactly one of these attributes.

If you would like to obtain the coordinates of the mouse click that submitted this request, see the information below on the `property` attribute.

This tag is only valid when nested inside a form tag body.

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
<td align="left">accesskey</td>
<td align="left"><p>The keyboard character used to move focus immediately to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">align</td>
<td align="left"><p>The alignment option for this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">border</td>
<td align="left"><p>The width (in pixels) of the border around this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left"><p>The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">locale</td>
<td align="left"><p>The session attribute key for the Locale used to select internationalized messages. If not specified, defaults to the Struts standard value.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">module</td>
<td align="left"><p>Prefix name of a <code>Module</code> that the <code>page</code> or <code>pageKey</code> attributes relate to.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The module-relative path of the image for this input tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">pageKey</td>
<td align="left"><p>The key of the message resources string specifying the module-relative path of the image for this input tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left"><p>The property name of this image tag. The parameter names for the request will appear as &quot;property.x&quot; and &quot;property.y&quot;, the x and y representing the coordinates of the mouse click for the image. A way of retrieving these values through a form bean is to define getX(), getY(), setX(), and setY() methods, and specify your property as a blank string (property=&quot;&quot;).</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">src</td>
<td align="left"><p>The source URL of the image for this input tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">srcKey</td>
<td align="left"><p>The key of the message resources string specifying the source URL of the image for this input tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left"><p>The value that will be submitted if this image button is pressed.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:img"></span>
### \.html.md:img\>

**Render an HTML img tag**

Renders an HTML `<img>` element with the image at the specified URL. Like the link tag, URL rewriting will be applied automatically to the value specified in `src`, `page`, or `action` to maintain session state in the absence of cookies. This will allow dynamic generation of an image where the content displayed for this image will be taken from the attributes of this tag.

The base URL for this image is calculated directly based on the value specified in `src`, `page`, or `action` or `page`, or indirectly by looking up a message resource string based on the `srcKey` or `pageKey` attributes. You **must** specify exactly one of these attributes.

Normally, the `src`, `page`, or `action` that you specify will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the `src` URL -- specify a single parameter with the `paramId` attribute (at its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the `src` URL. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

You can specify the alternate text for this image (which most browsers display as pop-up text block when the user hovers the mouse over this image) either directly, through the `alt` attribute, or indirectly from a message resources bundle, using the `bundle` and `altKey` attributes.

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
<td align="left">action</td>
<td align="left"><p>The action, starting with a slash, that will render the image to be displayed by this tag. The rendered URL for this image will automatically prepend the context path of this web application (in the same manner as the <code>action</code> attribute on the link tag works), in addition to any necessary URL rewriting. You <strong>must</strong> specify the <code>action</code>, <code>page</code> attribute or the <code>src</code> attribute.</p>
<p>Additionally, you can specify a <code>module</code> prefix for linking to other modules.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">align</td>
<td align="left"><p>Where the image is aligned to. Can be one of the following attributes:</p>
<ul>
<li>left - left justify, wrapping text on right</li>
<li>right -right justify, wrapping test on left</li>
<li>top - aligns the image with the top of the text on the same row</li>
<li>middle - aligns the image's vertical center with the text base line</li>
<li>bottom - aligns the image with the bottom of the text's base line</li>
<li>texttop - aligns the image's top with that of the text font on the same line</li>
<li>absmiddle - aligns the image's vertical center with the absolute center of the text</li>
<li>absbottom - aligns the image with the absolute bottom of the text font on the same row</li>
</ul></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">alt</td>
<td align="left"><p>And alternative text to be displayed in browsers that don't support graphics. Also used often as type of context help over images.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">border</td>
<td align="left"><p>The width of the border surrounding the image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left"><p>The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">height</td>
<td align="left"><p>The height of the image being displayed. This parameter is very nice to specify (along with <code>width</code>) to help the browser render the page faster.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">hspace</td>
<td align="left"><p>The amount of horizontal spacing between the icon and the text. The text may be in the same paragraph, or be wrapped around the image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">imageName</td>
<td align="left"><p>The scriptable name to be defined within this page, so that you can reference it with intra-page scripts. In other words, the value specified here will render a &quot;name&quot; element in the generated image tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ismap</td>
<td align="left"><p>The name of the server-side map that this image belongs to.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">locale</td>
<td align="left"><p>The name of the request or session Locale attribute used to look up internationalized messages.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">module</td>
<td align="left"><p>Prefix name of a <code>Module</code> that contains the action mapping for the <code>Action</code> that is specified by the <code>action</code> attribute. You <strong>must</strong> specify an <code>action</code> attribute for this to have an effect.</p>
<p><strong>Note:</strong> Use &quot;&quot; to map to the default module.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The name of a JSP bean that contains a <code>Map</code> representing the query parameters (if <code>property</code> is not specified), or a JSP bean whose property getter is called to return a <code>Map</code> (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key down event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key press event.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key up event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The module-relative path, starting with a slash, of the image to be displayed by this tag. The rendered URL for this image will automatically prepend the context path of this web application (in the same manner as the <code>page</code> attribute on the link tag works), in addition to any necessary URL rewriting. You <strong>must</strong> specify either the <code>page</code> attribute or the <code>src</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">pageKey</td>
<td align="left"><p>The message key, in the message resources bundle named by the <code>bundle</code> attribute, of the String to be used as the module-relative path for this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramId</td>
<td align="left"><p>The name of the request parameter that will be dynamically added to the generated src URL. The corresponding value is defined by the <code>paramName</code> and (optional) <code>paramProperty</code> attributes, optionally scoped by the <code>paramScope</code> attribute</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramName</td>
<td align="left"><p>The name of a JSP bean that is a String containing the value for the request parameter named by <code>paramId</code> (if <code>paramProperty</code> is not specified), or a JSP bean whose property getter is called to return a String (if <code>paramProperty</code> is specified). The JSP bean is constrained to the bean scope specified by the <code>paramScope</code> property, if it is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramProperty</td>
<td align="left"><p>The name of a property of the bean specified by the <code>paramName</code> attribute, whose return value must be a String containing the value of the request parameter (named by the <code>paramId</code> attribute) that will be dynamically added to this src URL.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramScope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>paramName</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left"><p>The name of a property of the bean specified by the <code>name</code> attribute, whose return value must be a <code>java.util.Map</code> containing the query parameters to be added to the src URL. You <strong>must</strong> specify the <code>name</code> attribute if you specify this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>name</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">src</td>
<td align="left"><p>The URL to which this image will be transferred from This image may be dynamically modified by the inclusion of query parameters, as described in the tag description. This value will be used unmodified (other than potential URL rewriting) as the value of the &quot;src&quot; attribute in the rendered tag. You <strong>must</strong> specify either the <code>page</code> attribute or the <code>src</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">srcKey</td>
<td align="left"><p>The message key, in the message resources bundle named by the <code>bundle</code> attribute, of the String to be used as the URL of this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">useLocalEncoding</td>
<td align="left"><p>If set to <code>true</code>, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">usemap</td>
<td align="left"><p>The name of the map as defined within this page for mapping hot-spot areas of this image.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">vspace</td>
<td align="left"><p>The amount of vertical spacing between the icon and the text, above and below.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">width</td>
<td align="left"><p>The width of the image being displayed. This parameter is very nice to specify (along with <code>height</code>) to help the browser render the page faster.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:javascript"></span>
### \.html.md:javascript\>

**Render JavaScript validation based on the validation rules loaded by the ValidatorPlugIn.**

Render JavaScript validation based on the validation rules loaded by the `ValidatorPlugIn`. The set of validation rules that should be generated is based on the formName attribute passed in, which should match the name attribute of the form element in the xml file.

The dynamicJavascript and staticJavascript attributes default to true, but if dynamicJavascript is set to `true` and staticJavascript is set to `false` then only the dynamic JavaScript will be rendered. If dynamicJavascript is set to `false` and staticJavascript is set to `true` then only the static JavaScript will be rendered which can then be put in separate JSP page so the browser can cache the static JavaScript.

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
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.7</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">cdata</td>
<td align="left"><p>If set to &quot;true&quot; and XHTML has been enabled, the JavaScript will be wrapped in a CDATA section to prevent XML parsing. The default is &quot;true&quot; to comply with the W3C's recommendation.</p>
<strong>Since:</strong> Struts 1.1</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dynamicJavascript</td>
<td align="left"><p>Whether or not to render the dynamic JavaScript. Defaults to <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">formName</td>
<td align="left"><p>The key (form name) to retrieve a specific set of validation rules. If &quot;dynamicJavascript&quot; is set to <code>true</code> and formName is missing or is not recognized by the <code>ValidatorPlugIn</code>, a JspException will be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left".html.mdComment</td>
<td align="left"><p>Whether or not to enclose the javascript with HTML comments. This attribute is ignored in XHTML mode because the script would be deleted by the XML parser. See the cdata attribute for details on hiding scripts from XML parsers. Defaults to <code>true</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left"><p>The alternate JavaScript method name to be used instead of the of the default. The default is 'validate' concatenated in front of the key (form name) passed in (ex: validateRegistrationForm).</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">page</td>
<td align="left"><p>The current page of a set of validation rules if the page attribute for the field element in the xml file is in use.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scriptLanguage</td>
<td align="left"><p>The <code>&lt;script&gt;</code> element will not contain a language attribute when this is set to false. The default is true but this property is ignored in XHTML mode.</p>
<strong>Since:</strong> Struts 1.2</td>
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

<span id=.html.md:link"></span>
### \.html.md:link\>

**Render an HTML anchor or hyperlink**

Renders an HTML `<a>` element as an anchor definition (if "linkName" is specified) or as a hyperlink to the specified URL. URL rewriting will be applied automatically, to maintain session state in the absence of cookies. The content displayed for this hyperlink will be taken from the body of this tag.

The base URL for this hyperlink is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there. If the forward is module-relative then it must point to an action and NOT to a page.
-   *action* - Use the value of this attribute as the name of a `Action` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as a module-relative URI, and generate a server-relative URI by including the context path and module prefix.

Normally, the hyperlink you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s), or an object whose toString() method will be called. If a String array is specified, more than one value for the same query parameter name will be created.

Additionally, you can request that the current transaction control token, if any, be included in the generated hyperlink by setting the `transaction` attribute to `true`. You can also request that an anchor ("\#xxx") be added to the end of the URL that is created by any of the above mechanisms, by using the `anchor` attribute.

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
<td align="left">accesskey</td>
<td align="left"><p>The keyboard character used to move focus immediately to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">action</td>
<td align="left"><p>Logical name of a <code>Action</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p>
<p>Additionally, you can specify a <code>module</code> prefix for linking to other modules.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">anchor</td>
<td align="left"><p>Optional anchor tag (&quot;#xxx&quot;) to be added to the generated hyperlink. Specify this value <strong>without</strong> any &quot;#&quot; character.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">forward</td>
<td align="left"><p>Logical name of a global <code>ActionForward</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">href</td>
<td align="left"><p>The URL to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">indexId</td>
<td align="left">By this attribute different name for the indexed parameter can be specified. Take a look to the &quot;indexed&quot; attribute for details.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">linkName</td>
<td align="left"><p>The anchor name to be defined within this page, so that you can reference it with intra-page hyperlinks. In other words, the value specified here will render a &quot;name&quot; element in the generated anchor tag.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">module</td>
<td align="left"><p>Prefix name of a <code>Module</code> that contains the action mapping for the <code>Action</code> that is specified by the <code>action</code> attribute. You <strong>must</strong> specify an <code>action</code> attribute for this to have an effect.</p>
<p><strong>Note:</strong> Use &quot;&quot; to map to the default module.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The name of a JSP bean that contains a <code>Map</code> representing the query parameters (if <code>property</code> is not specified), or a JSP bean whose property getter is called to return a <code>Map</code> (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left"><p>JavaScript event handler that is executed when this element loses input focus.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse click.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse double click.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives input focus.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key down event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key press event.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a key up event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse down event.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse move event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse out event.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse over event.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left"><p>JavaScript event handler that is executed when this element receives a mouse up event.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The module-relative path (beginning with a &quot;/&quot; character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramId</td>
<td align="left"><p>The name of the request parameter that will be dynamically added to the generated hyperlink. The corresponding value is defined by the <code>paramName</code> and (optional) <code>paramProperty</code> attributes, optionally scoped by the <code>paramScope</code> attribute</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramName</td>
<td align="left"><p>The name of a JSP bean that is a String containing the value for the request parameter named by <code>paramId</code> (if <code>paramProperty</code> is not specified), or a JSP bean whose property getter is called to return a String (if <code>paramProperty</code> is specified). The JSP bean is constrained to the bean scope specified by the <code>paramScope</code> property, if it is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramProperty</td>
<td align="left"><p>The name of a property of the bean specified by the <code>paramName</code> attribute, whose return value must be a String containing the value of the request parameter (named by the <code>paramId</code> attribute) that will be dynamically added to this hyperlink.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramScope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>paramName</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>The name of a property of the bean specified by the <code>name</code> attribute, whose return value must be a <code>java.util.Map</code> containing the query parameters to be added to the hyperlink. You <strong>must</strong> specify the <code>name</code> attribute if you specify this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>name</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left"><p>The tab order (ascending positive integers) for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">target</td>
<td align="left"><p>The window target in which the resource requested by this hyperlink will be displayed, for example in a framed presentation.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this hyperlink.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">transaction</td>
<td align="left"><p>If set to <code>true</code>, any current transaction control token will be included in the generated hyperlink, so that it will pass an <code>isTokenValid()</code> test in the receiving Action.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">useLocalEncoding</td>
<td align="left"><p>If set to <code>true</code>, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:messages"></span>
### \.html.md:messages\>

**Conditionally display a set of accumulated messages.**

Displays a set of messages prepared by a business logic component and stored as an `ActionMessages` object, `ActionErrors` object, a String, or a String array in any scope. If such a bean is not found, nothing will be rendered.

In order to use this tag successfully, you must have defined an application scope `MessageResources` bean under the default attribute name.

Can contain: JSP

#### Attributes

| Name     | Description                                                                                                                                                            | Type   |
|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| bundle   | The servlet context attribute key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. | String |
| footer   | This value is an optional message resource key that will be printed after the iteration of messages has finished.                                                      | String |
| header   | This value is an optional message resource key that will be printed before the iteration of messages begins.                                                           | String |
| **id\*** | The name of a page scope JSP bean that will contain the current element of the collection of messages on each iteration, if it is not `null`                           | String |
| locale   | The session attribute key for the Locale used to select messages to be displayed. If not specified, defaults to the Struts standard value.                             | String |
| message  | By default the tag will retrieve the bean it will iterate over from the `Globals.ERROR_KEY` `Globals.MESSAGE_KEY`                                                      | String |
| name     | Name of the bean in any scope under which our messages have been stored. If not present, the name specified by the `Globals.ERROR_KEY`                                 | String |
| property | Name of the property for which messages should be displayed. If not specified, all messages (regardless of property) are displayed.                                    | String |

<span id=.html.md:multibox"></span>
### \.html.md:multibox\>

**Render A Checkbox Input Field**

Renders an HTML `<input>` element of type `checkbox`, whose "checked" status is initialized based on whether the specified value matches one of the elements of the underlying property's array of current values. This element is useful when you have large numbers of checkboxes, and prefer to combine the values into a single array-valued property instead of multiple boolean properties. This tag is only valid when nested inside a form tag body.

**WARNING**: In order to correctly recognize cases where none of the associated checkboxes are selected, the `ActionForm` bean associated with this form must include a statement setting the corresponding array to zero length in the `reset()` method.

The value to be returned to the server, if this checkbox is selected, must be defined by one of the following methods:

-   Specify a `value` attribute, whose contents will be used literally as the value to be returned.
-   Specify no `value` attribute, and the nested body content of this tag will be used as the value to be returned.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">The value to be transmitted if this checkbox is checked when the form is submitted.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:option"></span>
### \.html.md:option\>

**Render A Select Option**

Render an HTML `<option>` element, representing one of the choices for an enclosing `<select>` element. The text displayed to the user comes from either the body of this tag, or from a message string looked up based on the `bundle`, `locale`, and `key` attributes.

If the value of the corresponding bean property matches the specified value, this option will be marked selected. This tag is only valid when nested inside a `.html.md:select>` tag body.

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
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">filter</td>
<td align="left">Set to <code>true</code> if you want the option label to be filtered for sensitive characters in HTML. By default, such a value is NOT filtered.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">key</td>
<td align="left">If specified, defines the message key to be looked up in the resource bundle specified by <code>bundle</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">locale</td>
<td align="left">The session attributes key for the Locale instance to use for looking up the message specified by the <code>key</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>value*</strong></td>
<td align="left">Value to be submitted for this field if this option is selected by the user.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:options"></span>
### \.html.md:options\>

**Render a Collection of Select Options**

Renders a set of HTML `<option>` elements, representing possible choices for a `<select>` element. This tag can be used multiple times within a single `.html.md:select>` element, either in conjunction with or instead of one or more `<html:option>` or `<html:optionsCollection>` elements.

This tag operates in one of two major modes, depending on whether or not the `collection` attribute is specified. If the `collection` attribute is included, the following rules apply:

-   The **collection** attribute is interpreted as the name of a JSP bean, in some scope, that itself represents a collection of individual beans, one per option value to be rendered.
-   The **property** attribute is interpreted as the name of a property of the individual beans included in the collection, and is used to retrieve the value that will be returned to the server if this option is selected.
-   The **labelProperty** attribute is interpreted as the name of a property of the individual beans included in the collection, and is used to retrieve the label that will be displayed to the user for this option. If the `labelProperty` attribute is not specified, the property named by the `property` attribute will be used to select both the value returned to the server and the label displayed to the user for this option.

If the `collection` attribute is not specified, the rules described in the remainder of this section apply.

The collection of values actually selected depends on the presence or absence of the `name` and `property` attributes. The following combinations are allowed:

-   *Only `name` is specified* - The value of this attribute is the name of a JSP bean in some scope that is the collection.
-   *Only `property` is specified* - The value of this attribute is the name of a property of the ActionForm bean associated with our form, which will return the collection.
-   *Both `name` and `property` are specified* - The value of the `name` attribute identifies a JSP bean in some scope. The value of the `property` attribute is the name of some property of that bean which will return the collection.

The collection of labels displayed to the user can be the same as the option values themselves, or can be different, depending on the presence or absence of the `labelName` and `labelProperty` attributes. If this feature is used, the collection of labels must contain the same number of elements as the corresponding collection of values. The following combinations are allowed:

-   *Neither `labelName` nor `labelProperty` is specified* - The labels will be the same as the option values themselves.
-   *Only `labelName` is specified* - The value of this attribute is the name of a JSP bean in some scope that is the collection.
-   *Only `labelProperty` is specified* - The value of this attribute is the name of a property of the ActionForm bean associated with our form, which will return the collection.
-   *Both `labelName` and `labelProperty` are specified* - The value of the `labelName` attribute identifies a JSP bean in some scope. The value of the `labelProperty` attribute is the name of some property of that bean which will return the collection.

Note that this tag does not support a `styleId` attribute, as it would have to apply the value to all the `option` elements created by this element, which would mean that more than one `id` element might have the same value, which the HTML specification says is illegal.

Can contain: empty

#### Attributes

| Name          | Description                                                                                                                                                                                                                                        | Type   |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| collection    | Name of the JSP bean (in some scope) which is itself a Collection of other beans, each of which has properties named by the "property" and "labelProperty" attributes that are used to retrieve the value and label for each option, respectively. | String |
| filter        | Set to `false`                                                                                                                                                                                                                                     | String |
| labelName     | Name of the JSP bean (in some scope) containing the collection of labels to be displayed to the user for these options.                                                                                                                            | String |
| labelProperty | Property of the form bean, or the bean specified by the labelName attribute, that will return the collection of labels to be displayed to the user for these options.                                                                              | String |
| name          | Name of the JSP bean (in some scope) containing the collection of values to be returned to the server for these options. If not specified, the form bean associated with our form is assumed.                                                      | String |
| property      | Property of the form bean, or the bean specified by the name attribute, that will return the collection of values to returned to the server for these options.                                                                                     | String |
| style         | CSS styles to be applied to this HTML element.                                                                                                                                                                                                     | String |
| styleClass    | CSS stylesheet class to be applied to this HTML element (renders a "class" attribute).                                                                                                                                                             | String |

<span id=.html.md:optionsCollection"></span>
### \.html.md:optionsCollection\>

**Render a Collection of Select Options**

Renders a set of HTML `<option>` elements, representing possible choices for a `<select>` element. This tag can be used multiple times within a single `.html.md:select>` element, either in conjunction with or instead of one or more `<html:option>` or `<html:options>` elements.

This tag operates on a collection of beans, where each bean has a **label** property and a **value** property. The actual names of these properties can be configured using the `label` and `value` attributes of this tag.

This tag differs from the `.html.md:options>` tag in that it makes more consistent use of the `name` and `property` attributes, and allows the collection to be more easily obtained from the enclosing form bean.

Note that this tag does not support a `styleId` attribute, as it would have to apply the value to all the `option` elements created by this element, which would mean that more than one `id` element might have the same value, which the HTML specification says is illegal.

Can contain: empty

#### Attributes

| Name       | Description                                                                                                                                                                                                   | Type   |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| filter     | Set to `false`                                                                                                                                                                                                | String |
| label      | The property of the bean within the collection which represents the label to be rendered for each option. Defaults to "label".                                                                                | String |
| name       | The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized. | String |
| property   | The property of the form bean, or the bean specified by the name attribute, that will return the collection of objects to be rendered for these options.                                                      | String |
| style      | CSS styles to be applied to this HTML element.                                                                                                                                                                | String |
| styleClass | CSS stylesheet class to be applied to this HTML element (renders a "class" attribute).                                                                                                                        | String |
| value      | The property of the bean within the collection which represents the value to be rendered for each option. Defaults to "value".                                                                                | String |

<span id=.html.md:param"></span>
### \.html.md:param\>

Adds a parameter to the following tags:

1.  `.html.md:frame>`
2.  `.html.md:link>`
3.  `.html.md:rewrite>`

**Since:** Struts 1.3.6
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
<td align="left"><strong>name*</strong></td>
<td align="left"><p>The String containing the name of the request parameter.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left"><p>The value of the request parameter specified by the <code>name</code> attribute, whose return value must be a String or String[] that will be dynamically added to this hyperlink.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:password"></span>
### \.html.md:password\>

**Render A Password Input Field**

Renders an HTML `<input>` element of type password, populated from the specified value or the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.
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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">maxlength</td>
<td align="left">Maximum number of input characters to accept. [No limit]</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onselect</td>
<td align="left">JavaScript event handler executed when a when a user selects some text in a text field. <strong>Since:</strong> Struts 1.3.10</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">readonly</td>
<td align="left">Set to <code>true</code> if this input field should be read only.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">redisplay</td>
<td align="left">Boolean flag indicating whether or not existing values will be redisplayed if they exist. Even though the redisplayed value will be shown as asterisks on the visible HTML page, the cleartext of the actual password value will be visible though the &quot;Show Page Source&quot; menu option of the client browser. You may wish to set this value to <code>false</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">size</td>
<td align="left">Number of character positions to allocate. [Browser default]</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">Value of the label to be placed on this button. This value will also be submitted as the value of the specified request parameter. [Body of this tag (if any)]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:radio"></span>
### \.html.md:radio\>

**Render A Radio Button Input Field**

Renders an HTML `<input>` element of type radio, populated from the specified property of the bean associated with our current form. This tag is only valid when nested inside a form tag body.

If an iterator is used to render a series of radio tags, the idName attribute may be used to specify the name of the bean exposed by the iterator. In this case, the value attribute is used as the name of a property on the idName bean that returns the value of the radio tag in this iteration.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">idName</td>
<td align="left"><p>Name of the bean (in some scope) that will return the value of the radio tag. Usually exposed by an iterator. When the idName attribute is present, the value attribute is used as the name of the property on the idName bean that will return the value of the radio tag for this iteration.</p>
<strong>Since:</strong> Struts 1.1</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>property*</strong></td>
<td align="left">The corresponding bean property for this radio tag.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>value*</strong></td>
<td align="left">The value of the radio tag.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:reset"></span>
### \.html.md:reset\>

**Render A Reset Button Input Field**

Renders an HTML `<input>` element of type reset.
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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left">Name of the input field that will be generated.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left">Value of the label to be placed on this button. [Body of this tag (if any), or &quot;Reset&quot;]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:rewrite"></span>
### \.html.md:rewrite\>

**Render an URI**

Renders a request URI based on exactly the same rules as the `link` tag does, but without creating the `<a>` hyperlink. This value is useful when you want to generate a string constant for use by a JavaScript procedure.

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
<td align="left">action</td>
<td align="left"><p>Logical name of a <code>Action</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p>
<p>Additionally, you can specify a <code>module</code> prefix for linking to other modules.</p>
<strong>Since:</strong> Struts 1.2.0</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">anchor</td>
<td align="left"><p>Optional anchor tag (&quot;#xxx&quot;) to be added to the generated hyperlink. Specify this value <strong>without</strong> any &quot;#&quot; character.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">forward</td>
<td align="left"><p>Logical name of a global <code>ActionForward</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">href</td>
<td align="left"><p>The URL to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">module</td>
<td align="left"><p>Prefix name of a <code>Module</code> that contains the action mapping for the <code>Action</code> that is specified by the <code>action</code> attribute. You <strong>must</strong> specify an <code>action</code> attribute for this to have an effect.</p>
<p><strong>Note:</strong> Use &quot;&quot; to map to the default module.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>The name of a JSP bean that contains a <code>Map</code> representing the query parameters (if <code>property</code> is not specified), or a JSP bean whose property getter is called to return a <code>Map</code> (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">page</td>
<td align="left"><p>The module-relative path (beginning with a &quot;/&quot; character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramId</td>
<td align="left"><p>The name of the request parameter that will be dynamically added to the generated hyperlink. The corresponding value is defined by the <code>paramName</code> and (optional) <code>paramProperty</code> attributes, optionally scoped by the <code>paramScope</code> attribute</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramName</td>
<td align="left"><p>The name of a JSP bean that is a String containing the value for the request parameter named by <code>paramId</code> (if <code>paramProperty</code> is not specified), or a JSP bean whose property getter is called to return a String (if <code>paramProperty</code> is specified). The JSP bean is constrained to the bean scope specified by the <code>paramScope</code> property, if it is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramProperty</td>
<td align="left"><p>The name of a property of the bean specified by the <code>paramName</code> attribute, whose return value must be a String containing the value of the request parameter (named by the <code>paramId</code> attribute) that will be dynamically added to this hyperlink.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramScope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>paramName</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left"><p>The name of a property of the bean specified by the <code>name</code> attribute, whose return value must be a <code>java.util.Map</code> containing the query parameters to be added to the hyperlink. You <strong>must</strong> specify the <code>name</code> attribute if you specify this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>name</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">transaction</td>
<td align="left"><p>If set to <code>true</code>, any current transaction control token will be included in the generated hyperlink, so that it will pass an <code>isTokenValid()</code> test in the receiving Action.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">useLocalEncoding</td>
<td align="left"><p>If set to <code>true</code>, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:select"></span>
### \.html.md:select\>

**Render A Select Element**

Renders an HTML `<select>` element, associated with a bean property specified by our attributes. This tag is only valid when nested inside a form tag body.

This tag operates in two modes, depending upon the state of the `multiple` attribute, which affects the data type of the associated property you should use:

-   *multiple="true" IS NOT selected* - The corresponding property should be a scalar value of any supported data type.
-   *multiple="true" IS selected* - The corresponding property should be an array of any supported data type.

**WARNING**: In order to correctly recognize cases where no selection at all is made, the `ActionForm` bean associated with this form must include a statement resetting the scalar property to a default value (if `multiple` is not set), or the array property to zero length (if `multiple` is set) in the `reset()` method.

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
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">multiple</td>
<td align="left">If set to any arbitrary value, the rendered select element will support multiple selections.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted to determine which option should be pre-selected when rendering this input field. If not specified, the bean associated with the enclosing <code>&lt.html.md:form&gt;</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">size</td>
<td align="left">The number of available options displayed at one time.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">The value to compare with for marking an option selected.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:submit"></span>
### \.html.md:submit\>

**Render A Submit Button**

Renders an HTML `<input>` element of type `submit`
If a graphical button is needed (a button with an image), then the [`image`](#image) tag is more appropriate.

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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">property</td>
<td align="left">Name of the request parameter that will be included with this submission, set to the specified value.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">style</td>
<td align="left">CSS styles to be applied to this HTML element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleClass</td>
<td align="left">CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleId</td>
<td align="left">Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left">The value of the button label.</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:text"></span>
### \.html.md:text\>

**Render An Input Field of Type text**

Render an input button of type text. This tag is only valid when nested inside a form tag body.
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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">maxlength</td>
<td align="left">Maximum number of input characters to accept. [No limit]</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onselect</td>
<td align="left">JavaScript event handler executed when a when a user selects some text in a text field.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of this input field, and the name of the corresponding bean property if value is not specified. The corresponding bean property (if any) must be of type String.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">readonly</td>
<td align="left">Set to <code>true</code> if this input field should be read only.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">size</td>
<td align="left">Number of character positions to allocate. [Browser default]</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left">Value to which this field should be initialized. [Use the corresponding bean property value]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:textarea"></span>
### \.html.md:textarea\>

**Render A Textarea**

Render a textarea element. This tag is only valid when nested inside a form tag body.
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
<td align="left">accesskey</td>
<td align="left">The keyboard character used to move focus immediately to this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">alt</td>
<td align="left"><p>The alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">altKey</td>
<td align="left"><p>The message resources key of the alternate text for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">bundle</td>
<td align="left">The servlet context attributes key for the MessageResources instance to use. If not specified, defaults to the application resources configured for our action servlet. <strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">cols</td>
<td align="left">The number of columns to display.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">dir</td>
<td align="left"><p>The direction for weak/neutral text for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">disabled</td>
<td align="left">Set to <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorKey</td>
<td align="left"><p>Name of the bean (in any scope) under which our error messages have been stored. If not present, the name specified by the <code>Globals.ERROR_KEY</code> constant string will be used.</p>
<p><strong>N.B.</strong> This is used in conjunction with the <code>errorStyle</code>, <code>errorStyleClass</code> and <code>errorStyleId</code> attributes and should be set to the same value as the <code>name</code> attribute on the <code>&lt.html.md:errors/&gt;</code> tag.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyle</td>
<td align="left"><p>CSS styles to be applied to this HTML element if an error exists for it.</p>
<p><strong>N.B.</strong> If present, this overrides the <code>style</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">errorStyleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element if an error exists for it (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleClass</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">errorStyleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element if an error exists for it (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, this overrides the <code>styleId</code> attribute in the event of an error.</p>
<strong>Since:</strong> Struts 1.2.5</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">indexed</td>
<td align="left">Valid only inside of <code>logic-el:iterate</code> <code>c:forEach</code> <code>true</code></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">lang</td>
<td align="left"><p>The language code for this element.</p>
<strong>Since:</strong> Struts 1.3.6</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">The attribute name of the bean whose properties are consulted when rendering the current value of this input field. If not specified, the bean associated with the form tag we are nested within is utilized.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onblur</td>
<td align="left">JavaScript event handler executed when this element loses input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onchange</td>
<td align="left">JavaScript event handler executed when this element loses input focus and its value has changed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse click.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ondblclick</td>
<td align="left">JavaScript event handler executed when this element receives a mouse double click.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onfocus</td>
<td align="left">JavaScript event handler executed when this element receives input focus.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeydown</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onkeypress</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is depressed and released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onkeyup</td>
<td align="left">JavaScript event handler executed when this element has focus and a key is released.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmousedown</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is depressed.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmousemove</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and the pointer is moved.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseout</td>
<td align="left">JavaScript event handler executed when this element was under the mouse pointer but the pointer was moved outside the element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onmouseover</td>
<td align="left">JavaScript event handler executed when this element was not under the mouse pointer but the pointer is moved inside the element.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">onmouseup</td>
<td align="left">JavaScript event handler executed when this element is under the mouse pointer and a mouse button is released.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">onselect</td>
<td align="left">JavaScript event handler executed when a when a user selects some text in a text field.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>property*</strong></td>
<td align="left">Name of this input field, and the name of the corresponding bean property if value is not specified. The corresponding bean property (if any) must be of type String.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">readonly</td>
<td align="left">Set to <code>true</code> if this input field should be read only.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">rows</td>
<td align="left">The number of rows to display.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">style</td>
<td align="left"><p>CSS styles to be applied to this HTML element.</p>
<p><strong>N.B.</strong> If present, the <code>errorStyle</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">styleClass</td>
<td align="left"><p>CSS stylesheet class to be applied to this HTML element (renders a &quot;class&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleClass</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">styleId</td>
<td align="left"><p>Identifier to be assigned to this HTML element (renders an &quot;id&quot; attribute).</p>
<p><strong>N.B.</strong> If present, the <code>errorStyleId</code> overrides this attribute in the event of an error for the element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">tabindex</td>
<td align="left">The tab order (ascending positive integers) for this element.</td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">title</td>
<td align="left"><p>The advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">titleKey</td>
<td align="left"><p>The message resources key for the advisory title for this element.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left">Value to which this field should be initialized. [Use the corresponding bean property value]</td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id=.html.md:xhtml"></span>
### \.html.md:xhtml\>

**Render HTML tags as XHTML**

Using this tag in a page tells all other.html.md taglib tags to render themselves as XHTML 1.0. This is useful when composing pages with JSP includes or Tiles. `<html:html xhtml="true">` has a similar effect. This tag has no attributes; you use it like this: `<html:xhtml/>`.

**Note**: Included pages do not inherit the rendering style of the including page. Each JSP fragment or Tile must use this tag to render as XHTML.

Can contain: empty

This tag has no attributes.

<span id="struts-logic-el.tld"></span>
logic
-----

This tag library contains tags that are useful in managing conditional generation of output text, looping over object collections for repetitive generation of output text, and application flow management.

For tags that do value comparisons (equal, greaterEqual, greaterThan, lessEqual, lessThan, notEqual), the following rules apply:

-   The specified value is examined. If it can be converted successfully to a double or a long, it is assumed that the ultimate comparison will be numeric (either floating point or integer). Otherwise, a String comparison will be performed.
-   The variable to be compared to is retrieved, based on the selector attribute(s) (cookie, header, name, parameter, property) present on this tag. It will be converted to the appropriate type for the comparison, as determined above.
-   If the specified variable or property returns null, it will be coerced to a zero-length string before the comparison occurs.
-   The specific comparison for this tag will be performed, and the nested body content of this tag will be evaluated if the comparison returns a true result.

For tags that do substring matching (match, notMatch), the following rules apply:

-   The specified variable is retrieved, based on the selector attribute(s) (cookie, header, name, parameter, property) present on this tag.
-   The variable is converted to a String, if necessary.A request time exception will be thrown if the specified variable cannot be retrieved, or has a null value.
-   The specified value is checked for existence as a substring of the variable, in the position specified by the location attribute, as follows: at the beginning (if location is set to start), at the end (if location is set to end), or anywhere (if location is not specified).

Many of the tags in this tag library will throw a JspException at runtime when they are utilized incorrectly (such as when you specify an invalid combination of tag attributes). JSP allows you to declare an "error page" in the \<%@ page %\> directive. If you wish to process the actual exception that caused the problem, it is passed to the error page as a request attribute under key org.apache.struts.action.EXCEPTION.

Struts-logic tags NOT implemented.

This library, a derivation of the normal "struts-logic" library, provides the functionality of the Struts logic tags, but assumes the presence of the JavaServer Pages Standard Library (JSTL), and uses the JSTL expression engine (hereafter abbreviated in many places as just "el") to evaluate attribute values instead of using JSP runtime expressions (sometimes called "rtexprvalues").

Because it is assumed this library will be used with the JSTL and the new EL engine, there are some tags in the struts-logic library which provide functionality which is entirely subsumed by the JSTL. This section lists each struts-logic tag which is NOT implemented in the struts-logic-el library, and describes the JSTL tag which can be used instead of the Struts tag.Struts-Logic TagJSTL Tag

`<logic:empty>`

This functionality is subsumed by the JSTL \<c:if\>, \<c:when\> tags and the empty function in the JSTL EL.

Example: \<c:if test="${empty var}"\>CONTENT\</c:if\>

This is version 1.3.

-   [forward](#logic:forward) Forward control to the page specified by the specified ActionForward entry
-   [iterate](#logic:iterate) Repeat the nested body content of this tag over a specified collection
-   [match](#logic:match) Evaluate the nested body content of this tag if the specified value is an appropriate substring of the requested variable
-   [messagesNotPresent](#logic:messagesNotPresent) Generate the nested body content of this tag if the specified message is not present in this request
-   [messagesPresent](#logic:messagesPresent) Generate the nested body content of this tag if the specified message is present in this request
-   [notMatch](#logic:notMatch) Evaluate the nested body content of this tag if the specified value is not an appropriate substring of the requested variable
-   [notPresent](#logic:notPresent) Generate the nested body content of this tag if the specified value is not present in this request
-   [present](#logic:present) Generate the nested body content of this tag if the specified value is present in this request
-   [redirect](#logic:redirect) Render an HTTP Redirect Performs an HttpServletResponse

Required attributes are marked with a **\***

<span id="logic:forward"></span>
### \<logic:forward\>

**Forward control to the page specified by the specified ActionForward entry.**

Performs a `PageContext.forward()` or `HttpServletResponse.sendRedirect()` call for the global `ActionForward` entry for the specified name. URL rewriting will occur automatically if a redirect is performed.

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
<td align="left"><strong>name*</strong></td>
<td align="left"><p>The logical name of the global <code>ActionForward</code> entry that identifies the destination, and forwarding approach, to be used. <strong>Note</strong>: forwarding to Tiles definitions is not supported from this tag. You should forward to them from an Action subclass.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:iterate"></span>
### \<logic:iterate\>

**Repeat the nested body content of this tag over a specified collection.**

Repeats the nested body content of this tag once for every element of the specified collection, which must be an `Iterator`, a `Collection`, a `Map` (whose values are to be iterated over), or an array. The collection to be iterated over must be specified in one of the following ways:

-   As a runtime expression specified as the value of the `collection` attribute.
-   As a JSP bean specified by the `name` attribute.
-   As the property, specified by the `property`, of the JSP bean specified by the `name` attribute.

The collection to be iterated over MUST conform to one of the following requirements in order for iteration to be successful:

-   An array of Java objects or primitives.
-   An implementation of `java.util.Collection`, including `ArrayList` and `Vector`.
-   An implementation of `java.util.Enumeration`.
-   An implementation of `java.util.Iterator`.
-   An implementation of `java.util.Map`, including `HashMap`, `Hashtable`, and `TreeMap`. **NOTE** - See below for additional information about accessing Maps.

Normally, each object exposed by the iterate tag is an element of the underlying collection you are iterating over. However, if you iterate over a `Map`, the exposed object is of type `Map.Entry` that has two properties:

-   `key` - The key under which this item is stored in the underlying Map.
-   `value` - The value that corresponds to this key.

So, if you wish to iterate over the values of a Hashtable, you would implement code like the following:

`<logic-el:iterate id="element" name="myhashtable"> Next element is <bean:write name="element" property="value"/> </logic-el:iterate>`
If the collection you are iterating over can contain `null` values, the loop will still be performed but no page scope attribute (named by the `id` attribute) will be created for that loop iteration. You can use the `<logic-el:present;gt;` and `<logic-el:notPresent>` tags to test for this case.

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
<td align="left">collection</td>
<td align="left"><p>A runtime expression that evaluates to a collection (conforming to the requirements listed above) to be iterated over.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>id*</strong></td>
<td align="left"><p>The name of a page scope JSP bean that will contain the current element of the collection on each iteration, if it is not <code>null</code>.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">indexId</td>
<td align="left"><p>The name of a page scope JSP bean that will contain the current index of the collection on each iteration.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">length</td>
<td align="left"><p>The maximum number of entries (from the underlying collection) to be iterated through on this page. This can be either an integer that directly expresses the desired value, or the name of a JSP bean (in any scope) of type <code>java.lang.Integer</code> that defines the desired value. If not present, there will be no limit on the number of iterations performed.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The name of the JSP bean containing the collection to be iterated (if <code>property</code> is not specified), or the JSP bean whose property getter returns the collection to be iterated (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">offset</td>
<td align="left"><p>The zero-relative index of the starting point at which entries from the underlying collection will be iterated through. This can be either an integer that directly expresses the desired value, or the name of a JSP bean (in any scope) of type <code>java.lang.Integer</code> that defines the desired value. If not present, zero is assumed (meaning that the collection will be iterated from the beginning.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>Name of the property, of the JSP bean specified by <code>name</code>, whose getter returns the collection to be iterated.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the bean named by the <code>name</code> property, or &quot;any scope&quot; if not specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">type</td>
<td align="left"><p>Fully qualified Java class name of the element to be exposed through the JSP bean named from the <code>id</code> attribute. If not present, no type conversions will be performed. NOTE: The actual elements of the collection must be assignment-compatible with this class, or a request time ClassCastException will occur.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:match"></span>
### \<logic:match\>

**Evaluate the nested body content of this tag if the specified value is an appropriate substring of the requested variable.**

Matches the variable specified by one of the selector attributes (as a String) against the specified constant value. If the value is a substring (appropriately limited by the `location` attribute), the nested body content of this tag is evaluated.

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
<td align="left">cookie</td>
<td align="left"><p>The variable to be matched is the value of the cookie whose name is specified by this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">expr</td>
<td align="left"><p>A specific value to be compared with, either a static value, or an EL value.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">header</td>
<td align="left"><p>The variable to be matched is the value of the header whose name is specified by this attribute. The name match is performed in a case insensitive manner.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">location</td>
<td align="left"><p>If not specified, a match between the variable and the value may occur at any position within the variable string. If specified, the match must occur at the specified location (either <code>start</code> or <code>end</code>) of the variable string.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The variable to be matched is the JSP bean specified by this attribute, if <code>property</code> is not specified, or the value of the specified property of this bean, if <code>property</code> is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">parameter</td>
<td align="left"><p>The variable to be matched is the first, or only, value of the request parameter specified by this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>The variable to be matched is the property (of the bean specified by the <code>name</code> attribute) specified by this attribute. The property reference can be simple, nested, and/or indexed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the bean named by the <code>name</code> property, or &quot;any scope&quot; if not specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>value*</strong></td>
<td align="left"><p>The constant value which is checked for existence as a substring of the specified variable.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:messagesNotPresent"></span>
### \<logic:messagesNotPresent\>

**Generate the nested body content of this tag if the specified message is not present in this request.**

Evaluates the nested body content of this tag if an `ActionMessages` object, `ActionErrors` object, a String, or a String array is not in request scope. If such a bean is not found, nothing will be rendered.

**Since:** Struts 1.1
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
<td align="left">message</td>
<td align="left"><p>By default the tag will retrieve the request scope bean it will iterate over from the <code>Action.ERROR_KEY</code> constant string, but if this attribute is set to 'true' the request scope bean will be retrieved from the <code>Action.MESSAGE_KEY</code> constant string. Also if this is set to 'true', any value assigned to the name attribute will be ignored.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>The parameter key to retrieve the message from request scope.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>Name of the property for which messages should be retrieved. If not specified, all messages (regardless of property) are retrieved.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:messagesPresent"></span>
### \<logic:messagesPresent\>

**Generate the nested body content of this tag if the specified message is present in this request.**

Evaluates the nested body content of this tag if an `ActionMessages` object, `ActionErrors` object, a String, or a String array is in request scope. If such a bean is not found, nothing will be rendered.

**Since:** Struts 1.1
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
<td align="left">message</td>
<td align="left"><p>By default the tag will retrieve the request scope bean it will iterate over from the <code>Action.ERROR_KEY</code> constant string, but if this attribute is set to 'true' the request scope bean will be retrieved from the <code>Action.MESSAGE_KEY</code> constant string. Also if this is set to 'true', any value assigned to the name attribute will be ignored.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>The parameter key to retrieve the message from request scope.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>Name of the property for which messages should be retrieved. If not specified, all messages (regardless of property) are retrieved.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:notMatch"></span>
### \<logic:notMatch\>

**Evaluate the nested body content of this tag if the specified value is not an appropriate substring of the requested variable.**

Matches the variable specified by one of the selector attributes (as a String) against the specified constant value. If the value is not a substring (appropriately limited by the `location` attribute), the nested body content of this tag is evaluated.

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
<td align="left">cookie</td>
<td align="left"><p>The variable to be matched is the value of the cookie whose name is specified by this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">expr</td>
<td align="left"><p>A specific value to be compared with, either a static value, or an EL value.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">header</td>
<td align="left"><p>The variable to be matched is the value of the header whose name is specified by this attribute. The name match is performed in a case insensitive manner.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">location</td>
<td align="left"><p>If not specified, a match between the variable and the value may occur at any position within the variable string. If specified, the match must occur at the specified location (either <code>start</code> or <code>end</code>) of the variable string.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The variable to be matched is the JSP bean specified by this attribute, if <code>property</code> is not specified, or the value of the specified property of this bean, if <code>property</code> is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">parameter</td>
<td align="left"><p>The variable to be matched is the first, or only, value of the request parameter specified by this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>The variable to be matched is the property (of the bean specified by the <code>name</code> attribute) specified by this attribute. The property reference can be simple, nested, and/or indexed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the bean named by the <code>name</code> property, or &quot;any scope&quot; if not specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>value*</strong></td>
<td align="left"><p>The constant value which is checked for existence as a substring of the specified variable.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:notPresent"></span>
### \<logic:notPresent\>

**Generate the nested body content of this tag if the specified value is not present in this request.**

Depending on which attribute is specified, this tag checks the current request, and evaluates the nested body content of this tag only if the specified value **is not** present. Only one of the attributes may be used in one occurrence of this tag, unless you use the `property` attribute, in which case the `name` attribute is also required.

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
<td align="left">cookie</td>
<td align="left"><p>Checks for the existence of a cookie with the specified name.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">header</td>
<td align="left"><p>Checks for the existence of an HTTP header with the specified name. The name match is performed in a case insensitive manner.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>Checks for the existence of a JSP bean, in any scope, with the specified name. If <code>property</code> is also specified, checks for a non-null property value for the specified property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">parameter</td>
<td align="left"><p>Checks for the existence of at least one occurrence of the specified request parameter on this request, even if the parameter value is a zero-length string.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>Checks for the existence of a non-null property value, returned by a property getter method on the JSP bean (in any scope) that is specified by the <code>name</code> attribute. Property references can be simple, nested, and/or indexed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">role</td>
<td align="left"><p>Checks whether the currently authenticated user (if any) has been associated with the specified security role.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the bean named by the <code>name</code> property, or &quot;any scope&quot; if not specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left"><p>Checks whether the currently authenticated user principal has the specified name.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:present"></span>
### \<logic:present\>

**Generate the nested body content of this tag if the specified value is present in this request.**

Depending on which attribute is specified, this tag checks the current request, and evaluates the nested body content of this tag only if the specified value **is** present. Only one of the attributes may be used in one occurrence of this tag, unless you use the `property` attribute, in which case the `name` attribute is also required.

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
<td align="left">cookie</td>
<td align="left"><p>Checks for the existence of a cookie with the specified name.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">header</td>
<td align="left"><p>Checks for the existence of an HTTP header with the specified name. The name match is performed in a case insensitive manner.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>Checks for the existence of a JSP bean, in any scope, with the specified name. If <code>property</code> is also specified, checks for a non-null property value for the specified property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">parameter</td>
<td align="left"><p>Checks for the existence of at least one occurrence of the specified request parameter on this request, even if the parameter value is a zero-length string.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>Checks for the existence of a non-null property value, returned by a property getter method on the JSP bean (in any scope) that is specified by the <code>name</code> attribute. Property references can be simple, nested, and/or indexed.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">role</td>
<td align="left"><p>Checks whether the currently authenticated user (if any) has been associated with any of the specified security roles. Use a comma-delimited list to check for multiple roles. Example: <code>&lt;logic-el:present role=&quot;role1,role2,role3&quot;&gt; code..... &lt;/logic-el:present&gt;</code></p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>The bean scope within which to search for the bean named by the <code>name</code> property, or &quot;any scope&quot; if not specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left"><p>Checks whether the currently authenticated user principal has the specified name.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="logic:redirect"></span>
### \<logic:redirect\>

**Render an HTTP Redirect**

Performs an `HttpServletResponse.sendRedirect()` call to the hyperlink specified by the attributes to this tag. URL rewriting will be applied automatically, to maintain session state in the absence of cookies.

The base URL for this redirect is calculated based on which of the following attributes you specify (you must specify exactly one of them):

-   *forward* - Use the value of this attribute as the name of a global `ActionForward` to be looked up, and use the module-relative or context-relative URI found there.
-   *href* - Use the value of this attribute unchanged.
-   *page* - Use the value of this attribute as an module-relative URI, and generate a server-relative URI by including the context path.

Normally, the redirect you specify with one of the attributes described in the previous paragraph will be left unchanged (other than URL rewriting if necessary). However, there are two ways you can append one or more dynamically defined query parameters to the hyperlink -- specify a single parameter with the `paramId` attribute (and its associated attributes to select the value), or specify the `name` (and optional `property`) attributes to select a `java.util.Map` bean that contains one or more parameter ids and corresponding values.

To specify a single parameter, use the `paramId` attribute to define the name of the request parameter to be submitted. To specify the corresponding value, use one of the following approaches:

-   *Specify only the `paramName` attribute* - The named JSP bean (optionally scoped by the value of the `paramScope` attribute) must identify a value that can be converted to a String.
-   *Specify both the `paramName` and `paramProperty` attributes* - The specified property getter method will be called on the JSP bean identified by the `paramName` (and optional `paramScope`) attributes, in order to select a value that can be converted to a String.

If you prefer to specify a `java.util.Map` that contains all of the request parameters to be added to the hyperlink, use one of the following techniques:

-   *Specify only the `name` attribute* - The named JSP bean (optionally scoped by the value of the `scope` attribute) must identify a `java.util.Map` containing the parameters.
-   *Specify both `name` and `property` attributes* - The specified property getter method will be called on the bean identified by the `name` (and optional `scope`) attributes, in order to return the `java.util.Map` containing the parameters.

As the `Map` is processed, the keys are assumed to be the names of query parameters to be appended to the hyperlink. The value associated with each key must be either a String or a String array representing the parameter value(s). If a String array is specified, more than one value for the same query parameter name will be created.

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
<td align="left">action</td>
<td align="left"><p>Logical name of a global <code>Action</code> that contains the actual content-relative URI of the destination of this transfer. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>action</code> attribute, the <code>forward</code> attribute, the <code>href</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">anchor</td>
<td align="left"><p>Optional anchor tag (&quot;#xxx&quot;) to be added to the generated hyperlink. Specify this value <strong>without</strong> any &quot;#&quot; character.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">forward</td>
<td align="left"><p>Logical name of a global <code>ActionForward</code> that contains the actual content-relative URI of the destination of this redirect. This URI may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">href</td>
<td align="left"><p>The URL to which this redirect will transfer control. This URL may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>The name of a JSP bean that contains a <code>Map</code> representing the query parameters (if <code>property</code> is not specified), or a JSP bean whose property getter is called to return a <code>Map</code> (if <code>property</code> is specified).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>The context-relative path (beginning with a &quot;/&quot; character) to which this hyperlink will transfer control if activated. This hyperlink may be dynamically modified by the inclusion of query parameters, as described in the tag description. You <strong>must</strong> specify exactly one of the <code>forward</code> attribute, the <code>href</code> attribute, the <code>linkName</code> attribute, or the <code>page</code> attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramId</td>
<td align="left"><p>The name of the request parameter that will be dynamically added to the generated hyperlink. The corresponding value is defined by the <code>paramName</code> and (optional) <code>paramProperty</code> attributes, optionally scoped by the <code>paramScope</code> attribute</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramName</td>
<td align="left"><p>The name of a JSP bean that is a String containing the value for the request parameter named by <code>paramId</code> (if <code>paramProperty</code> is not specified), or a JSP bean whose property getter is called to return a String (if <code>paramProperty</code> is specified). The JSP bean is constrained to the bean scope specified by the <code>paramScope</code> property, if it is specified.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">paramProperty</td>
<td align="left"><p>The name of a property of the bean specified by the <code>paramName</code> attribute, whose return value must be a String containing the value of the request parameter (named by the <code>paramId</code> attribute) that will be dynamically added to this hyperlink.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">paramScope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>paramName</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">property</td>
<td align="left"><p>The name of a property of the bean specified by the <code>name</code> attribute, whose return value must be a <code>java.util.Map</code> containing the query parameters to be added to the hyperlink. You <strong>must</strong> specify the <code>name</code> attribute if you specify this attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">scope</td>
<td align="left"><p>The scope within which to search for the bean specified by the <code>name</code> attribute. If not specified, all scopes are searched.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">transaction</td>
<td align="left"><p>Set to <code>true</code> if you want the current transaction control token included in the generated URL for this redirect.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">useLocalEncoding</td>
<td align="left"><p>If set to <code>true</code>, LocalCharacterEncoding will be used, that is, the characterEncoding set to the HttpServletResponse, as prefered character encoding rather than UTF-8, when URLEncoding is done on parameters of the URL.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="struts-tiles-el.tld"></span>
tiles
-----

This tag library provides tiles tags. Tiles were previously called Components. For historical reasons, names, pages, components and templates are used indifferently to design a tile. Also, a lot of tags and attribute names are left for backward compatibility. To know more about tags defined in this library, check the associated documentation: tiles-doc.

This is version 1.3.

-   [add](#tiles:add) Add an element to the surrounding list
-   [definition](#tiles:definition) Create a tile /component / template definition bean
-   [get](#tiles:get) Gets the content from request scope that was put there by a put tag
-   [getAsString](#tiles:getAsString) Render the value of the specified tile/component/template attribute to the current JspWriter Retrieve the value of the specified tile/component/template attribute property, and render it to the current JspWriter as a String
-   [importAttribute](#tiles:importAttribute) Import Tile's attribute in specified context
-   [initComponentDefinitions](#tiles:initComponentDefinitions) Initialize Tile/Component definitions factory
-   [insert](#tiles:insert) Insert a tiles/component/template
-   [put](#tiles:put) Put an attribute into tile/component/template context
-   [putList](#tiles:putList) Declare a list that will be pass as attribute to tile
-   [useAttribute](#tiles:useAttribute) Use attribute value inside page

Required attributes are marked with a **\***

<span id="tiles:add"></span>
### \<tiles:add\>

**Add an element to the surrounding list. Equivalent to 'put', but for list element.**

Add an element to the surrounding list. This tag can only be used inside putList tag. Value can come from a direct assignment (value="aValue") or from a bean. One of 'value' or 'beanName' must be present.

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
<td align="left">beanName</td>
<td align="left"><p>Name of the bean used as value. Bean is retrieved from specified context, if any. Otherwise, method pageContext.findAttribute is used. If beanProperty is specified, retrieve value from the corresponding bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">beanProperty</td>
<td align="left"><p>Bean property name. If specified, value is retrieved from this property. Supports nested/indexed properties.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">beanScope</td>
<td align="left"><p>Scope into which bean is searched. If not specified, method pageContext.findAttribute is used. Scope can be any JSP scope, 'component', or 'template'. In these two later cases, bean is search in tile/component/template context.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">content</td>
<td align="left"><p>Element value. Can be a String or Object. Synonym to value. Attribute added for compatibility with JSP Template.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">direct</td>
<td align="left"><p>Determines how content is handled: true means content is printed <em>direct</em></p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">role</td>
<td align="left"><p>If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).</p>
<p>The role isn't taken into account if <code>&lt;add&gt;</code> tag is used in a definition.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">type</td>
<td align="left"><p>Specify content type: string, page, template or instance.</p>
<ul>
<li>String : Content is printed directly.</li>
<li>page | template : Content is included from specified URL. Name is used as an URL.</li>
<li>definition : Value denote a definition defined in factory (xml file). Definition will be searched in the inserted tile, in a <code>&lt;insert attribute=&quot;attributeName&quot;&gt;</code> tag, where 'attributeName' is the name used for this tag.</li>
</ul></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">value</td>
<td align="left"><p>Element value. Can be a String or Object.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:definition"></span>
### \<tiles:definition\>

**Create a tile /component / template definition bean.**

Create a tile/component/template definition as a bean. Newly created bean will be saved under specified "id", in the requested "scope". Definition tag has same syntax as `insert`

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
<td align="left">extends</td>
<td align="left"><p>Name of a parent definition that is used to initialize this new definition. Parent definition is searched in definitions factory.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>id*</strong></td>
<td align="left"><p>Specifies the name under which the newly created definition bean will be saved.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">page</td>
<td align="left"><p>URL of the template / component to insert. Same as &quot;template&quot;.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">role</td>
<td align="left"><p>Role to check before inserting this definition. If role is not defined for current user, definition is not inserted. Checking is done at insert time, not during definition process.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>Specifies the variable scope into which the newly defined bean will be created. If not specified, the bean will be created in page scope.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">template</td>
<td align="left"><p>A string representing the URI of a tile/component/template (a JSP page).</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:get"></span>
### \<tiles:get\>

**Gets the content from request scope that was put there by a put tag.**

Retrieve content from tile context and include it.

Take into account the 'type' attribute.

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
<td align="left">flush</td>
<td align="left"><p>True or false. If true, current page out stream is flushed before insertion.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><strong>name*</strong></td>
<td align="left"><p>The name of the content to get from tile/component scope.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">role</td>
<td align="left"><p>If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:getAsString"></span>
### \<tiles:getAsString\>

**Render the value of the specified tile/component/template attribute to the current JspWriter**

Retrieve the value of the specified tile/component/template attribute property, and render it to the current JspWriter as a String. The usual toString() conversions is applied on found value.

Throw a JSPException if named value is not found.

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
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>name*</strong></td>
<td align="left"><p>Attribute name.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">role</td>
<td align="left"><p>If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:importAttribute"></span>
### \<tiles:importAttribute\>

**Import Tile's attribute in specified context.**

Import attribute from tile to requested scope. Attribute name and scope are optional. If not specified, all tile attributes are imported in page scope. Once imported, an attribute can be used as any other beans from jsp contexts.

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
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without error. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">Tile's attribute name. If not specified, all attributes are imported.</td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>Scope into which attribute is imported. Default to page.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:initComponentDefinitions"></span>
### \<tiles:initComponentDefinitions\>

**Initialize Tile/Component definitions factory.**

In order to use Tile/Component definitions factory, you need to initialize the factory. This is generally done in a initializing servlet. In particular, it is done in "ComponentActionServlet" if you use it. If you don't initialize factory in a servlet, you can initialize it using this tag. You need to provide the description file name, and optionally the factory classname. Initialization is done only once, at the first call of this tag. Subsequent calls are ignored (tag checks existence of the factory).

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
<td align="left">classname</td>
<td align="left"><p>If specified, classname of the factory to create and initialized.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>file*</strong></td>
<td align="left"><p>Definition file name.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:insert"></span>
### \<tiles:insert\>

**Insert a tiles/component/template.**

Insert a tiles/component/template with the possibility to pass parameters (called attribute). A tile can be seen as a procedure that can take parameters or attributes. `<tiles:insert>` allows to define these attributes and pass them to the inserted jsp page, called template. Attributes are defined using nested tag `<tiles:put>` or `<tiles:putList>`.

You must specify one of this tag attribute :

-   `template`, for inserting a tiles/component/template page,
-   `component`, for inserting a tiles/component/template page, (same as template)
-   `page` for inserting a JSP page, (same as template)
-   `definition`, for inserting a definition from definitions factory
-   `attribute`, surrounding tiles's attribute name whose value is used. If attribute is associated to 'direct' flag (see put), and flag is true, write attribute value (no insertion).
-   `name`, to let 'insert' determine the type of entities to insert. In this later case, search is done in this order : definitions, tiles/components/templates, pages.

In fact, Page, component and template, are equivalent as a tile, component or template are jsp page.

**Example :**

                  
                     <tiles:insert page="/basic/myLayout.jsp" flush="true">
                     <tiles:put name="title" value="My first page" />
                     <tiles:put name="header" value="/common/header.jsp" />
                     <tiles:put name="footer" value="/common/footer.jsp" />
                     <tiles:put name="menu" value="/basic/menu.jsp" />
                     <tiles:put name="body" value="/basic/helloBody.jsp" />
                     </tiles:insert>
                  
               

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
<td align="left">attribute</td>
<td align="left"><p>Name of an attribute in current tile/component context. Value of this attribute is passed to 'name' (see attribute 'name').</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">beanName</td>
<td align="left"><p>Name of the bean used as value. Bean is retrieved from specified context, if any. Otherwise, method pageContext.findAttribute is used. If beanProperty is also specified, retrieve value from the corresponding bean property.</p>
<p>If found bean (or property value) is instance of one of Attribute class (Direct, Instance, ...), insertion is done according to the class type. Otherwise, the toString method is called on the bean, and returned String is used as name to insert (see 'name' attribute).</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">beanProperty</td>
<td align="left"><p>Bean property name. If specified, value is retrieved from this property. Supports nested/indexed properties.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">beanScope</td>
<td align="left"><p>Scope into which bean is searched. If not specified, method pageContext.findAttribute is used. Scope can be any JSP scope, 'component', or 'template'. In these two later cases, bean is search in tile/component/template context.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">component</td>
<td align="left"><p>Path (relative or absolute to webapps) of the component to insert.</p>
<p>'page', 'component' and 'template' are synonyms : they have exactly the same behavior.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">controllerClass</td>
<td align="left"><p>Class type of a controller called immediately before page is inserted.</p>
<p>Controller is used to prepare data to be render by inserted Tile.</p>
<p>See also controlerUrl</p>
<p>Class must implements or extends one of the following :</p>
<ul>
<li>org.apache.struts.tiles.Controller</li>
<li>org.apache.struts.tiles.ControllerSupport</li>
<li>org.apache.struts.action.Action (wrapper org.apache.struts.action.ActionController is used)</li>
</ul>
<p>See also controllerUrl. Only one of controllerUrl or controllerClass should be used.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">controllerUrl</td>
<td align="left"><p>Url of a controller called immediately before page is inserted.</p>
<p>Url usually denote a Struts action. Controller (action) is used to prepare data to be render by inserted Tile.</p>
<p>See also controlerClass. Only one of controllerUrl or controllerClass should be used.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">definition</td>
<td align="left"><p>Name of the definition to insert. Definition are defined in a centralized file. For now, only definition from factory can be inserted with this attribute. To insert a definition defined with tag <code>&lt;tiles:definition&gt;</code>, use beanName=&quot;&quot;.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">flush</td>
<td align="left"><p>True or false. If true, current page out stream is flushed before insertion.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left"><p>Name of an entity to insert. Search is done in this order : definition, attribute, [tile/component/template/page].</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">page</td>
<td align="left"><p>Path (relative or absolute to webapps) of the page to insert.</p>
<p>'page', 'component' and 'template' are synonyms : they have exactly the same behavior.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">role</td>
<td align="left"><p>If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">template</td>
<td align="left"><p>A string representing the URI of a tile or template (a JSP page).</p>
<p>'page', 'component' and 'template' are synonyms : they have exactly the same behavior.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:put"></span>
### \<tiles:put\>

**Put an attribute into tile/component/template context.**

Define an attribute to pass to tile/component/template. This tag can only be used inside 'insert' or 'definition' tag. Value (or content) is specified using attribute 'value' (or 'content'), or using the tag body. It is also possible to specify the type of the value :

-   string : Content is written directly.
-   page | template : Content is included from specified URL. Name is used as an URL.
-   definition : Content come from specified definition (from factory). Name is used as definition name.

If 'type' attribute is not specified, content is 'untyped', unless it comes from a typed bean.

Note that using 'direct="true"' is equivalent to 'type="string"'.

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
<td align="left">beanName</td>
<td align="left"><p>Name of the bean used as value. Bean is retrieved from specified context, if any. Otherwise, method pageContext.findAttribute is used. If beanProperty is specified, retrieve value from the corresponding bean property.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">beanProperty</td>
<td align="left"><p>Bean property name. If specified, value is retrieve from this property. Support nested/indexed properties.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">beanScope</td>
<td align="left"><p>Scope into which bean is searched. If not specified, method pageContext.findAttribute is used. Scope can be any JSP scope, 'tile', 'component', or 'template'. In these three later cases, bean is search in tile/component/template context.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">content</td>
<td align="left"><p>Content that's put into tile scope. Synonym to value. Attribute added for compatibility with JSP Template.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">direct</td>
<td align="left"><p>Determines how content is handled: true means content is printed <em>direct</em></p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>Name of the attribute.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">role</td>
<td align="left"><p>If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">type</td>
<td align="left"><p>Specify content type: string, page, template or definition.</p>
<ul>
<li>String : Content is printed directly.</li>
<li>page | template : Content is included from specified URL. Name is used as an URL.</li>
<li>definition : Value is the name of a definition defined in factory (xml file). Definition will be searched in the inserted tile, in a <code>&lt;tiles:insert attribute=&quot;attributeName&quot;&gt;</code> tag, where 'attributeName' is the name used for this tag.</li>
</ul></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">value</td>
<td align="left"><p>Attribute value. Could be a String or an Object. Value can come from a direct assignment (value=&quot;aValue&quot;) or from a bean. One of 'value' 'content' or 'beanName' must be present.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:putList"></span>
### \<tiles:putList\>

**Declare a list that will be pass as attribute to tile.**

Declare a list that will be pass as attribute to tile. List elements are added using the tag 'add'. This tag can only be used inside 'insert' or 'definition' tag.

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
<td align="left"><strong>name*</strong></td>
<td align="left"><p>Name of the list.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

<span id="tiles:useAttribute"></span>
### \<tiles:useAttribute\>

**Use attribute value inside page.**

Declare a Java variable, and an attribute in the specified scope, using tile attribute value.

Java variable and attribute will have the name specified by 'id', or the original name if not specified.

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
<td align="left">classname</td>
<td align="left"><p>Class of the declared variable.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left">id</td>
<td align="left"><p>Declared attribute and variable name.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without error. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><strong>name*</strong></td>
<td align="left"><p>Tile's attribute name.</p></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left">scope</td>
<td align="left"><p>Scope of the declared attribute. Default to 'page'.</p></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


