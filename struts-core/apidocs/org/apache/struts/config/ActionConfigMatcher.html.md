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
<td align="left"><a href="class-use/ActionConfigMatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ActionConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/BaseConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ActionConfigMatcher.html"><strong>FRAMES</strong></a>    <a href="ActionConfigMatcher.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.config
 Class ActionConfigMatcher
--------------------------

    java.lang.Object
      org.apache.struts.config.ActionConfigMatcher

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ActionConfigMatcher

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Matches paths against pre-compiled wildcard expressions pulled from action configs. It uses the wildcard matcher from the Apache Cocoon project. Patterns will be matched in the order they exist in the Struts config file. The last match wins, so more specific patterns should be defined after less specific patterns.

**Since:**  
Struts 1.2

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.ActionConfigMatcher)

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary**                                                                          |
|--------------------------------------------------------------------------------------------------|
| ` ActionConfigMatcher(ActionConfig[] configs)`                                                   
             Finds and precompiles the wildcard patterns from the ActionConfig "path" attributes.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  ActionConfig`

` convertActionConfig(String path, ActionConfig orig, Map vars)`
            Clones the ActionConfig and its children, replacing various properties with the values of the wildcard-matched strings.

`protected  String`

` convertParam(String val, Map vars)`
            Inserts into a value wildcard-matched strings where specified.

` ActionConfig`

` match(String path)`
            Matches the path against the compiled wildcard patterns.

`protected  void`

` replaceProperties(Properties orig, Properties props, Map vars)`
            Replaces placeholders from one Properties values set to another.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionConfigMatcher

    public ActionConfigMatcher(ActionConfig[] configs)

Finds and precompiles the wildcard patterns from the ActionConfig "path" attributes. ActionConfig's will be evaluated in the order they exist in the Struts config file. Only paths that actually contain a wildcard will be compiled.

**Parameters:**  
`configs` - An array of ActionConfig's to process

<span id="method_detail"></span>

**Method Detail**

### match

    public ActionConfig match(String path)

Matches the path against the compiled wildcard patterns.

**Parameters:**  
`path` - The portion of the request URI for selecting a config.

**Returns:**  
The action config if matched, else null

------------------------------------------------------------------------

### convertActionConfig

    protected ActionConfig convertActionConfig(String path,
                                               ActionConfig orig,
                                               Map vars)

Clones the ActionConfig and its children, replacing various properties with the values of the wildcard-matched strings.

**Parameters:**  
`path` - The requested path

`orig` - The original ActionConfig

`vars` - A Map of wildcard-matched strings

**Returns:**  
A cloned ActionConfig with appropriate properties replaced with wildcard-matched values

------------------------------------------------------------------------

### replaceProperties

    protected void replaceProperties(Properties orig,
                                     Properties props,
                                     Map vars)

Replaces placeholders from one Properties values set to another.

**Parameters:**  
`orig` - The original properties set with placehold values

`props` - The target properties to store the processed values

`vars` - A Map of wildcard-matched strings

------------------------------------------------------------------------

### convertParam

    protected String convertParam(String val,
                                  Map vars)

Inserts into a value wildcard-matched strings where specified.

**Parameters:**  
`val` - The value to convert

`vars` - A Map of wildcard-matched strings

**Returns:**  
The new value

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
<td align="left"><a href="class-use/ActionConfigMatcher.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ActionConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/BaseConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ActionConfigMatcher.html"><strong>FRAMES</strong></a>    <a href="ActionConfigMatcher.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
