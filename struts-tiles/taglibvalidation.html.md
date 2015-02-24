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
    -   [Checkstyle](checkstyle.html.md)
    -   [CPD Report](cpd.html.md)
    -   [DTDDoc](dtddoc/index.html.md)
    -   [JavaDocs](apidocs/index.html.md)
    -   [PMD Report](pmd.html.md)
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)
    -   [Taglibdoc documentation](tlddoc/index.html.md)
    -   **Tag library validation**
    -   [Tag reference](tagreference.html.md)
    -   [Test JavaDocs](testapidocs/index.html.md)
    -   [Test Source Xref](xref-test/index.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Tag library validation report
-----------------------------

Tag library validation report automatically generated by the Maven taglib plugin

This report contains a basic validation of tag handler classes for the following tag libraries:

-   [tiles (struts-tiles.tld)](#struts-tiles.tld) - uri: http://struts.apache.org/tags-tiles

<span id="struts-tiles.tld"></span>
null struts-tiles.tld
---------------------

### \<tiles:add\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                 |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|---------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.AddTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanName</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanProperty</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanScope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">content</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">direct</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">type</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">value</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:definition\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                        |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|----------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.DefinitionTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">extends</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">id</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">page</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">scope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">template</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:get\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                 |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|---------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.GetTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">flush</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">ignore</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:getAsString\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                          |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|------------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.GetAttributeTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">ignore</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:importAttribute\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                             |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|---------------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.ImportAttributeTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">ignore</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">scope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:initComponentDefinitions\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                             |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|---------------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.InitDefinitionsTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">classname</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">file</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:insert\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                    |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.InsertTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">attribute</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanName</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanProperty</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanScope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">component</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">controllerClass</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">controllerUrl</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">definition</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">flush</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">ignore</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">page</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">template</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:put\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                 |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|---------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.PutTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanName</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanProperty</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">beanScope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">content</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">direct</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">role</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">type</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">value</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:putList\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                     |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|-------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.PutListTag |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

### \<tiles:useAttribute\>

| found                                   | loadable                                | extends TagSupport/TagExtraInfo         | class                                          |
|-----------------------------------------|-----------------------------------------|-----------------------------------------|------------------------------------------------|
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.UseAttributeTag |
| ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | ![success](images/icon_success_sml.gif) | org.apache.struts.tiles.taglib.UseAttributeTei |

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">-</th>
<th align="left">attribute name</th>
<th align="left">tld declares</th>
<th align="left">tag declares</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">classname</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">id</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">ignore</td>
<td align="left"></td>
<td align="left">-</td>
</tr>
<tr class="even">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">name</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
<tr class="odd">
<td align="left"><img src="images/icon_success_sml.gif" alt="success" /></td>
<td align="left">scope</td>
<td align="left"></td>
<td align="left">String</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------

