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
<td align="left"><a href="class-use/XmlParser.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlParser.html"><strong>FRAMES</strong></a>    <a href="XmlParser.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles.xmlDefinition
 Class XmlParser
-------------------------------------

    java.lang.Object
      org.apache.struts.tiles.xmlDefinition.XmlParser

------------------------------------------------------------------------

    public class XmlParser

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Parse an XML definitions file.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  org.apache.commons.digester.Digester`

` digester`
           Associated digester.

`protected  String[]`

` registrations`
           The set of public identifiers, and corresponding resource names for the versions of the configuration file DTDs we know about.

`protected  boolean`

` validating`
           Should we use a validating XML parser to read the configuration file.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` XmlParser()`          
            Constructor.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` initDigester(org.apache.commons.digester.Digester digester)`
           Init digester.

`static void`

` main(String[] args)`
           Main method to check file syntax.

` void`

` parse(InputStream in, XmlDefinitionsSet definitions)`
           Parse input reader and add encountered definitions to definitions set.

` void`

` setValidating(boolean validating)`
           Set digester validating flag.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="digester"></span>

### digester

    protected org.apache.commons.digester.Digester digester

Associated digester.

------------------------------------------------------------------------

<span id="validating"></span>

### validating

    protected boolean validating

Should we use a validating XML parser to read the configuration file. Default is `false`.

------------------------------------------------------------------------

<span id="registrations"></span>

### registrations

    protected String[] registrations

The set of public identifiers, and corresponding resource names for the versions of the configuration file DTDs we know about. There **MUST** be an even number of Strings in this list!

<span id="constructor_detail"></span>

**Constructor Detail**

### XmlParser

    public XmlParser()

Constructor. Creates a digester parser and initializes syntax rules.

<span id="method_detail"></span>

**Method Detail**

### setValidating

    public void setValidating(boolean validating)

Set digester validating flag.

------------------------------------------------------------------------

### initDigester

    protected void initDigester(org.apache.commons.digester.Digester digester)

Init digester.

**Parameters:**  
`digester` - Digester instance to use.

------------------------------------------------------------------------

### parse

    public void parse(InputStream in,
                      XmlDefinitionsSet definitions)
               throws IOException,
                      SAXException

Parse input reader and add encountered definitions to definitions set.

**Parameters:**  
`in` - Input stream.

`definitions` - Xml Definitions set to which encountered definition are added.

**Throws:**  
`IOException` - On errors during file parsing.

`SAXException` - On errors parsing XML.

------------------------------------------------------------------------

### main

    public static void main(String[] args)

Main method to check file syntax.

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
<td align="left"><a href="class-use/XmlParser.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/xmlDefinition/XmlListAttribute.html.md" title="class in org.apache.struts.tiles.xmlDefinition"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/xmlDefinition/XmlParser.html"><strong>FRAMES</strong></a>    <a href="XmlParser.html"><strong>NO FRAMES</strong></a>    
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
