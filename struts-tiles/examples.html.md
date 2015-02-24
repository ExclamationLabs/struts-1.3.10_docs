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
-   **Creating Templates**
-   [Taglib Reference](tagreference.html.md)

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

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Creating Templates
------------------

The following examples illustrate Tiles' templating features using a basic template. The template contains three elements: a title, a header, and a body displayed vertically. These elements will be manipulated in various ways in each example. Tiles' flexibility will be demonstrated by defining the template "inline" in a JSP page and by loading it from a "factory" defined in an XML file.

### Basic Template

The first example shows the basic template. There are three ways to define the template. First, it can be defined anonymously in a JSP page by using the Tiles insert tag. Secondly, it can be defined in a JSP using the Tiles definition tag. Finally, it can be defined in an XML file and loaded from a factory using the Tiles insert tag. This example will illustrate all three methods. First, let's look at the output of the example. Then we will examine each method.

**Example Output**
<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><strong>This is the title.</strong></td>
</tr>
<tr class="even">
<td align="left"><strong>This is the header</strong><img src="images/struts-power.gif" /></td>
</tr>
<tr class="odd">
<td align="left"><div align="center">
<strong><em>This is the body</em></strong>
</div></td>
</tr>
</tbody>
</table>

First let's look at the template. The layout.jsp file contains the template code. This file does not change no matter whether the Tile is defined anonymously, in a JSP, or in an XML definitions file.

**file: layout.jsp**
    <%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>

    <table  border="2"  width="300"  bordercolor="Gray">
      <tr>
        <td  bgcolor="Blue"><strong><tiles:getAsString name="title"/></strong></td>
      </tr>
      <tr>
        <td><tiles:insert attribute="header"/></td>
      </tr>
      <tr>
        <td><tiles:insert attribute="body"/></td>
      </tr>
    </table>                     
        

Next we show the template being inserted anonymously using the Tiles insert tag. The insert tag is used to define the Tile and insert it in a single action. The Tile is not placed in the Definitions Factory and is not available for later use. The template is invoked and the attributes are filled in. Notice that the title is inserted directly and the header and body values are included JSP pages.

**file: somepage.jsp**
    <%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>

    <tiles:insert template="layout.jsp">
      <tiles:put name="title"  value="This is the title." />
      <tiles:put name="header" value="header.jsp" />
      <tiles:put name="body"   value="body.jsp" />
    </tiles:insert>
        

**file: header.jsp**
    <strong>This is the header</strong>
    <img src="<%=request.getContextPath()%>/images/struts-power.gif" align="right" border="0"/>
        

**file: body.jsp**
    <div align="center"><b><i>This is a body</i></b></div>
        

Now we will see the same example in a different way. In this version the Tile is defined in a JSP using the Tiles definition tag. This works very similarly to the anonymous version. The only difference is that it is not anonymous. Using this method the template is included and populated and the Tile is inserted into the Definitions Factory so that it can be used by other JSP pages.

**file: somepage.jsp**
    <%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>

    <tiles:definition id="templateDefinition" template="layout.jsp">
      <tiles:put name="title"  value="This is the title." />
      <tiles:put name="header" value="header.jsp" />
      <tiles:put name="body"   value="body.jsp" />
    </tiles:definition>
    <tiles:insert definition="templateDefinition" />
        

Using this method of defining Tiles can be very tricky. If you define a Tile like this and then insert it in another page using the Tiles insert tag, you must make sure that JSP page will never be invoked before the page that defines the Tile. The Tiles Definitions Factory is stored in application scope. So if the server is restarted or the Definitions Factory is reloaded for any reason, a Tile defined in a JSP page is not reloaded until that JSP page is invoked.

The scenario above can be avoided by defining Tiles in an XML configuration file. The file is loaded at servlet startup using the Tiles Servlet or a plugin. The example below defines the Tile in an XML file and uses the Tiles insert tag in a JSP to invoke it.

**file: WEB-INF/tiles-defs.xml**
    ...
    <definition name="templateDefinition" path="/layout.jsp">
      <put name="title"  value="This is the title." />
      <put name="header" value="header.jsp" />
      <put name="body"   value="body.jsp" />
    </definition>
    ...
        

**file: somepage.jsp**
    <%@ taglib uri="http://struts.apache.org/tags-tiles" prefix="tiles" %>

    <tiles:insert beanName="templateDefinition" />
        

This is the preferred method of defining Tiles. It ensures that all definitions are loaded at application startup and reduces the coupling between JSP pages.

### Specify Attribute Types

The previous examples used the **put** tag to set attributes in a Tiles definition. In those examples Tiles inferred they attribute type. In most cases this is fine as long as you understand the rules of how value types are inferred. More on that later. This example shows that you can specify the attribute type to give Tiles a hint about what to do with the value.

**file: WEB-INF/tiles-defs.xml**
    ...
    <definition name="templateDefinition" path="/layout.jsp">
      <put name="title"  value="Title with specified Type." type="string" />
      <put name="header" value="header.jsp" type="page" />
      <put name="body"   value="body.jsp" type="page" />
    </definition>
    ...
        

The above code is really no different from the first example. Tiles would've inferred the types we specified. There are several valid settings for the type attribute. However, they all resolve to just three different types. The type will be interpreted in one of the following ways.

-   **String.** Value will be inserted directly in the page as text.
-   **Definition.** Value points to a valid Tiles definition that will be processed and inserted in the page.
-   **Page.** Value points to a JSP page that will be included in the current page.

In most cases Tiles will determine the appropriate type. When would you need to specify it? Perhaps you have an attribute that is a logo that is either reused or overriden for a Tile. Tiles might interpret this value as a path and try to process it as a JSP page. If you specify it as a String it will be inserted directly into the page. It would also be useful to specify the type if the value points to a Tiles definition and you want to make sure Tiles doesn't interpret it as a direct String.

### Set Attribute With Tag Body

**Example Output**
<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><strong>Test with tag body.</strong></td>
</tr>
<tr class="even">
<td align="left"><strong>This header is inserted as body of tag</strong></td>
</tr>
<tr class="odd">
<td align="left"><div align="center">
<strong><em>This is the body</em></strong>
</div></td>
</tr>
</tbody>
</table>

**file: WEB-INF/tiles-defs.xml**
    ...
    <definition name="templateDefinition" path="/layout.jsp">
      <put name="title"  value="Test with tag body." type="string" />
      <put name="header" type="string" >
        <strong>This header is inserted as body of tag</strong>
      </put>
      <put name="body"   value="body.jsp" type="page" />
    </definition>
    ...
        

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


