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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="insert.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

tiles
 Tag insert
-----------

------------------------------------------------------------------------

**Insert a tiles/component/template.**

Insert a tiles/component/template with the possibility to pass parameters (called attribute). A tile can be seen as a procedure that can take parameters or attributes. `<tiles:insert>` allows to define these attributes and pass them to the inserted jsp page, called template. Attributes are defined using nested tag `<tiles:put>` or `<tiles:putList>`.

You must specify one of this tag attribute :

-   `template`, for inserting a tiles/component/template page,
-   `component`, for inserting a tiles/component/template page, (same as template)
-   `page` for inserting a JSP page, (same as template)
-   `definition`, for inserting a definition from definitions factory
-   `attribute`, surrounding tiles's attribute name whose value is used.
     If attribute is associated to 'direct' flag (see put), and flag is true, write attribute value (no insertion).
-   `name`, to let 'insert' determine the type of entities to insert. In this later case, search is done in this order : definitions, tiles/components/templates, pages.

In fact, Page, component and template, are equivalent as a tile, component or template are jsp page.

**Example :**

      <tiles:insert page="/basic/myLayout.jsp" flush="true"> <tiles:put name="title" value="My first page" /> <tiles:put name="header" value="/common/header.jsp" /> <tiles:put name="footer" value="/common/footer.jsp" /> <tiles:put name="menu" value="/basic/menu.jsp" /> <tiles:put name="body" value="/basic/helloBody.jsp" /> </tiles:insert>  

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.strutsel.taglib.tiles.ELInsertTag

TagExtraInfo Class

*None*

Body Content

JSP

Display Name

*None*

**Attributes**

**Name**

**Required**

**Request-time**

**Type**

**Description**

template

false

true

`java.lang.String`

A string representing the URI of a tile or template (a JSP page).

'page', 'component' and 'template' are synonyms : they have exactly the same behavior.

component

false

true

`java.lang.String`

Path (relative or absolute to webapps) of the component to insert.

'page', 'component' and 'template' are synonyms : they have exactly the same behavior.

page

false

true

`java.lang.String`

Path (relative or absolute to webapps) of the page to insert.

'page', 'component' and 'template' are synonyms : they have exactly the same behavior.

definition

false

true

`java.lang.String`

Name of the definition to insert. Definition are defined in a centralized file. For now, only definition from factory can be inserted with this attribute. To insert a definition defined with tag `<tiles:definition>`, use beanName="".

attribute

false

false

`java.lang.String`

Name of an attribute in current tile/component context. Value of this attribute is passed to 'name' (see attribute 'name').

name

false

true

`java.lang.String`

Name of an entity to insert. Search is done in this order : definition, attribute, [tile/component/template/page].

beanName

false

true

`java.lang.String`

Name of the bean used as value. Bean is retrieved from specified context, if any. Otherwise, method pageContext.findAttribute is used. If beanProperty is also specified, retrieve value from the corresponding bean property.

If found bean (or property value) is instance of one of Attribute class (Direct, Instance, ...), insertion is done according to the class type. Otherwise, the toString method is called on the bean, and returned String is used as name to insert (see 'name' attribute).

beanProperty

false

true

`java.lang.String`

Bean property name. If specified, value is retrieved from this property. Supports nested/indexed properties.

beanScope

false

false

`java.lang.String`

Scope into which bean is searched. If not specified, method pageContext.findAttribute is used. Scope can be any JSP scope, 'component', or 'template'. In these two later cases, bean is search in tile/component/template context.

flush

false

false

`java.lang.String`

True or false. If true, current page out stream is flushed before insertion.

ignore

false

true

`java.lang.String`

If this attribute is set to true, and the attribute specified by the name does not exist, simply return without writing anything. The default value is false, which will cause a runtime exception to be thrown.

role

false

true

`java.lang.String`

If the user is in the specified role, the tag is taken into account; otherwise, the tag is ignored (skipped).

controllerUrl

false

true

`java.lang.String`

Url of a controller called immediately before page is inserted.

Url usually denote a Struts action. Controller (action) is used to prepare data to be render by inserted Tile.

See also controlerClass. Only one of controllerUrl or controllerClass should be used.

controllerClass

false

true

`java.lang.String`

Class type of a controller called immediately before page is inserted.

Controller is used to prepare data to be render by inserted Tile.

See also controlerUrl

Class must implements or extends one of the following :

-   org.apache.struts.tiles.Controller
-   org.apache.struts.tiles.ControllerSupport
-   org.apache.struts.action.Action (wrapper org.apache.struts.action.ActionController is used)

See also controllerUrl. Only one of controllerUrl or controllerClass should be used.

|-------------------------|
| **Variables**           |
| *No Variables Defined.* |

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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="insert.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
