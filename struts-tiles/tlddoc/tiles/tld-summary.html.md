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

tiles
-----

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix="tiles" uri="http://struts.apache.org/tags-tiles" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:tiles="http://struts.apache.org/tags-tiles" />`

------------------------------------------------------------------------


    This tag library provides tiles tags.Tiles were previously called Components. For historical reasons, names, pages, components and templates are used indifferently to design a tile. Also, a lot of tags and attribute names are left for backward compatibility.To know more about tags defined in this library, check the associated documentation: tiles-doc.

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

tiles

URI

http://struts.apache.org/tags-tiles

 

**Tag Summary**

**[insert](insert.html.md)**

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

**[definition](definition.html.md)**

**Create a tile /component / template definition bean.**

Create a tile/component/template definition as a bean. Newly created bean will be saved under specified "id", in the requested "scope". Definition tag has same syntax as `insert`

**[put](put.html.md)**

**Put an attribute into tile/component/template context.**

Define an attribute to pass to tile/component/template. This tag can only be used inside 'insert' or 'definition' tag. Value (or content) is specified using attribute 'value' (or 'content'), or using the tag body. It is also possible to specify the type of the value :

-   string : Content is written directly.
-   page | template : Content is included from specified URL. Name is used as an URL.
-   definition : Content come from specified definition (from factory). Name is used as definition name.

If 'type' attribute is not specified, content is 'untyped', unless it comes from a typed bean.

Note that using 'direct="true"' is equivalent to 'type="string"'.

**[putList](putList.html.md)**

**Declare a list that will be pass as attribute to tile.**

Declare a list that will be pass as attribute to tile. List elements are added using the tag 'add'. This tag can only be used inside 'insert' or 'definition' tag.

**[add](add.html.md)**

**Add an element to the surrounding list. Equivalent to 'put', but for list element.**

Add an element to the surrounding list. This tag can only be used inside putList tag. Value can come from a direct assignment (value="aValue") or from a bean. One of 'value' or 'beanName' must be present.

**[get](get.html.md)**

**Gets the content from request scope that was put there by a put tag.**

Retrieve content from tile context and include it.

Take into account the 'type' attribute.

**[getAsString](getAsString.html.md)**

**Render the value of the specified tile/component/template attribute to the current JspWriter**

Retrieve the value of the specified tile/component/template attribute property, and render it to the current JspWriter as a String. The usual toString() conversions is applied on found value.

Throw a JSPException if named value is not found.

**[useAttribute](useAttribute.html.md)**

**Use attribute value inside page.**

Declare a Java variable, and an attribute in the specified scope, using tile attribute value.

Java variable and attribute will have the name specified by 'id', or the original name if not specified.

**[importAttribute](importAttribute.html.md)**

**Import Tile's attribute in specified context.**

Import attribute from tile to requested scope. Attribute name and scope are optional. If not specified, all tile attributes are imported in page scope. Once imported, an attribute can be used as any other beans from jsp contexts.

**[initComponentDefinitions](initComponentDefinitions.html.md)**

**Initialize Tile/Component definitions factory.**

In order to use Tile/Component definitions factory, you need to initialize the factory. This is generally done in a initializing servlet. In particular, it is done in "ComponentActionServlet" if you use it. If you don't initialize factory in a servlet, you can initialize it using this tag. You need to provide the description file name, and optionally the factory classname. Initialization is done only once, at the first call of this tag. Subsequent calls are ignored (tag checks existence of the factory.

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
