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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ResponseUtils.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/util/RequestUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ServletContextWriter.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ResponseUtils.html"><strong>FRAMES</strong></a>    <a href="ResponseUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class ResponseUtils
----------------------

    java.lang.Object
      org.apache.struts.util.ResponseUtils

------------------------------------------------------------------------

    public class ResponseUtils

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

General purpose utility methods related to generating a servlet response in the Struts controller framework.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-21 14:46:28 -0400 (Sun, 21 Aug 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static MessageResources`

`messages`
           The message resources for this package.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ResponseUtils()`      
                          |

  <span id="method_summary"></span>

**Method Summary**

`static String`

` encodeURL(String url)`
           URLencodes a string assuming the character encoding is UTF-8.

`static String`

` encodeURL(String url, String enc)`
           Use the new URLEncoder.encode() method from Java 1.4 if available, else use the old deprecated version.

`static String`

` filter(String value)`
           Filter the specified string for characters that are senstive to HTML interpreters, returning the string with these characters replaced by the corresponding character entities.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="messages"></span>

### messages

    protected static MessageResources messages

The message resources for this package.

<span id="constructor_detail"></span>

**Constructor Detail**

### ResponseUtils

    public ResponseUtils()

<span id="method_detail"></span>

**Method Detail**

### filter

    public static String filter(String value)

Filter the specified string for characters that are senstive to HTML interpreters, returning the string with these characters replaced by the corresponding character entities.

**Parameters:**  
`value` - The string to be filtered and returned

------------------------------------------------------------------------

### encodeURL

    public static String encodeURL(String url)

URLencodes a string assuming the character encoding is UTF-8.

**Parameters:**  
`url` -

**Returns:**  
String The encoded url in UTF-8

------------------------------------------------------------------------

### encodeURL

    public static String encodeURL(String url,
                                   String enc)

Use the new URLEncoder.encode() method from Java 1.4 if available, else use the old deprecated version. This method uses reflection to find the appropriate method; if the reflection operations throw exceptions, this will return the url encoded with the old URLEncoder.encode() method.

**Parameters:**  
`enc` - The character encoding the urlencode is performed on.

**Returns:**  
String The encoded url.

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
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ResponseUtils.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/util/RequestUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ServletContextWriter.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ResponseUtils.html"><strong>FRAMES</strong></a>    <a href="ResponseUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
