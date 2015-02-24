<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Tiles

-   [Welcome](index.html.md)
-   [FAQ](faq.html.md)
-   [Installation](installation.html.md)
-   [User Guide](userGuide.html.md)
-   [Creating Templates](examples.html.md)
-   **Taglib Reference**

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
    -   [DTDDoc](dtddoc/index.html.md)
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

-   [tiles (struts-tiles.tld)](#struts-tiles.tld) - uri: http://struts.apache.org/tags-tiles

<span id="struts-tiles.tld"></span>
tiles
-----

This tag library provides tiles tags.Tiles were previously called Components. For historical reasons, names, pages, components and templates are used indifferently to design a tile. Also, a lot of tags and attribute names are left for backward compatibility.To know more about tags defined in this library, check the associated documentation: tiles-doc.

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
<td align="left"><p>Bean property name. If specified, value is retrieve from this property. Support nested/indexed properties.</p></td>
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
<td align="left">boolean</td>
</tr>
<tr class="even">
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">boolean</td>
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
<td align="left">boolean</td>
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
<td align="left">boolean</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left"><p>Tile's attribute name. If not specified, all attributes are imported.</p></td>
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

In order to use Tile/Component definitions factory, you need to initialize the factory. This is generally done in a initializing servlet. In particular, it is done in "ComponentActionServlet" if you use it. If you don't initialize factory in a servlet, you can initialize it using this tag. You need to provide the description file name, and optionally the factory classname. Initialization is done only once, at the first call of this tag. Subsequent calls are ignored (tag checks existence of the factory.

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
-   `attribute`, surrounding tiles's attribute name whose value is used.If attribute is associated to 'direct' flag (see put), and flag is true, write attribute value (no insertion).
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
<td align="left"><p>Bean property name. If specified, value is retrieve from this property. Support nested/indexed properties.</p></td>
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
<td align="left">boolean</td>
</tr>
<tr class="even">
<td align="left">ignore</td>
<td align="left"><p>If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.</p></td>
<td align="left">boolean</td>
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
<td align="left">boolean</td>
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


