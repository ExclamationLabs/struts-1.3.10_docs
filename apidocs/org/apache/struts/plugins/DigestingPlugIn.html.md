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
<td align="left"><a href="class-use/DigestingPlugIn.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/plugins/ModuleConfigVerifier.html.md" title="class in org.apache.struts.plugins"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/plugins/DigestingPlugIn.html"><strong>FRAMES</strong></a>    <a href="DigestingPlugIn.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.plugins
 Class DigestingPlugIn
-------------------------

    java.lang.Object
      org.apache.struts.plugins.DigestingPlugIn

**All Implemented Interfaces:**  
[PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

------------------------------------------------------------------------

    public class DigestingPlugIn

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

An implementation of `PlugIn` which can be configured to instantiate a graph of objects using the Commons Digester and place the root object of that graph into the Application context.

**Since:**  
Struts 1.2

**Version:**  
$Rev: 471754 $

**See Also:**  
[`PlugIn`](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` configPath`
            

`protected  String`

` configSource`
            

`protected  String`

` digesterPath`
            

`protected  String`

` digesterSource`
            

`protected  String`

`key`
            

`protected  ModuleConfig`

` moduleConfig`
            

`protected  boolean`

`push`
            

`protected  String`

` rulesets`
            

`protected  ActionServlet`

` servlet`
            

`protected static String`

` SOURCE_CLASSPATH`
            

`protected static String`

` SOURCE_FILE`
            

`protected static String`

` SOURCE_SERVLET`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                     |
|---------------------------------------------|
| ` DigestingPlugIn()`                        
            Constructor for DigestingPlugIn.  |

  <span id="method_summary"></span>

**Method Summary**

`protected  void`

` applyRuleSets(org.apache.commons.digester.Digester digester)`
           Instantiate any `RuleSet` classes defined in the `rulesets` property and use them to add rules to our `Digester`.

` void`

` destroy()`
           Receive notification that our owning module is being shut down.

`protected  org.apache.commons.digester.Digester`

` digesterFromXml(String path, String source)`
           Instantiate a Digester from an XML input stream using the Commons `DigesterLoader`.

`protected  URL`

` getClassPathURL(String path)`
           Given a string, return a URL to a classpath resource of that name.

` String`

` getConfigPath()`
            

` String`

` getConfigSource()`
            

`protected  URL`

` getConfigURL(String path, String source)`
           Look up a resource path using one of a set of known path resolution mechanisms and return a URL to the resource.

` String`

` getDigesterPath()`
            

` String`

` getDigesterSource()`
            

`protected  URL`

` getFileURL(String path)`
           Given a string, return a URL to a Filesystem resource of that name.

` String`

` getKey()`
            

` boolean`

` getPush()`
            

` String`

` getRulesets()`
            

`protected  URL`

` getServletContextURL(String path)`
           Given a string, return a URL to a Servlet Context resource of that name.

` void`

` init(ActionServlet servlet, ModuleConfig config)`
           Initialize a `Digester` and use it to parse a configuration file, resulting in a root object which will be placed into the ServletContext.

`protected  org.apache.commons.digester.Digester`

` initializeDigester()`
           Initialize the `Digester` which will be used to process the main configuration.

`protected  org.apache.commons.digester.Digester`

` newDigesterInstance()`
           Instantiate a `Digester`.

` void`

` setConfigPath(String configPath)`
            

` void`

` setConfigSource(String configSource)`
           Set the source of the config file.

` void`

` setDigesterPath(String digesterPath)`
           The path to a Digester XML configuration file, relative to the `digesterSource` property.

` void`

` setDigesterSource(String digesterSource)`
           The lookup mechanism to be used to resolve `digesterPath` (optional).

` void`

` setKey(String key)`
            

` void`

` setPush(boolean push)`
           If set to `true`, this PlugIn will be pushed onto the Digester stack before the digester `parse` method is called.

` void`

` setRulesets(String ruleSets)`
           A comma-delimited list of one or more classes which implement `org.apache.commons.digester.RuleSet`.

`protected  void`

` storeGeneratedObject(Object obj)`
           This method is called after the Digester runs to store the generated object somewhere.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="SOURCE_CLASSPATH"></span>

### SOURCE\_CLASSPATH

    protected static final String SOURCE_CLASSPATH

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.plugins.DigestingPlugIn.SOURCE_CLASSPATH)

------------------------------------------------------------------------

<span id="SOURCE_FILE"></span>

### SOURCE\_FILE

    protected static final String SOURCE_FILE

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.plugins.DigestingPlugIn.SOURCE_FILE)

------------------------------------------------------------------------

<span id="SOURCE_SERVLET"></span>

### SOURCE\_SERVLET

    protected static final String SOURCE_SERVLET

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.plugins.DigestingPlugIn.SOURCE_SERVLET)

------------------------------------------------------------------------

<span id="configPath"></span>

### configPath

    protected String configPath

------------------------------------------------------------------------

<span id="configSource"></span>

### configSource

    protected String configSource

------------------------------------------------------------------------

<span id="digesterPath"></span>

### digesterPath

    protected String digesterPath

------------------------------------------------------------------------

<span id="digesterSource"></span>

### digesterSource

    protected String digesterSource

------------------------------------------------------------------------

<span id="key"></span>

### key

    protected String key

------------------------------------------------------------------------

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

------------------------------------------------------------------------

<span id="rulesets"></span>

### rulesets

    protected String rulesets

------------------------------------------------------------------------

<span id="servlet"></span>

### servlet

    protected ActionServlet servlet

------------------------------------------------------------------------

<span id="push"></span>

### push

    protected boolean push

<span id="constructor_detail"></span>

**Constructor Detail**

### DigestingPlugIn

    public DigestingPlugIn()

Constructor for DigestingPlugIn.

<span id="method_detail"></span>

**Method Detail**

### destroy

    public void destroy()

Receive notification that our owning module is being shut down.

**Specified by:**  
`destroy` in interface `PlugIn`

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig config)
              throws ServletException

Initialize a `Digester` and use it to parse a configuration file, resulting in a root object which will be placed into the ServletContext.

**Specified by:**  
` init` in interface `PlugIn`

<!-- -->

**Parameters:**  
`servlet` - ActionServlet that is managing all the modules in this web application

`config` - ModuleConfig for the module with which this plug-in is associated

**Throws:**  
`ServletException` - if this `PlugIn` cannot be successfully initialized

------------------------------------------------------------------------

### initializeDigester

    protected org.apache.commons.digester.Digester initializeDigester()
                                                               throws ServletException

Initialize the `Digester` which will be used to process the main configuration.

**Returns:**  
a Digester, ready to use.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### newDigesterInstance

    protected org.apache.commons.digester.Digester newDigesterInstance()

Instantiate a `Digester`.

Subclasses may wish to override this to provide a subclass of Digester, or to configure the Digester using object methods.

**Returns:**  
a basic instance of `org.apache.commons.digester.Digester`

------------------------------------------------------------------------

### digesterFromXml

    protected org.apache.commons.digester.Digester digesterFromXml(String path,
                                                                   String source)
                                                            throws IOException

Instantiate a Digester from an XML input stream using the Commons `DigesterLoader`.

**Parameters:**  
`path` - the path to the digester rules XML to be found using `source`

`source` - a string indicating the lookup method to be used with `path`

**Returns:**  
a configured Digester

**Throws:**  
`FileNotFoundException`

`MalformedURLException`

`IOException`

**See Also:**  
[`getConfigURL(String, String)`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigURL(java.lang.String,%20java.lang.String))

------------------------------------------------------------------------

### applyRuleSets

    protected void applyRuleSets(org.apache.commons.digester.Digester digester)
                          throws ServletException

Instantiate any `RuleSet` classes defined in the `rulesets` property and use them to add rules to our `Digester`.

**Parameters:**  
`digester` - the Digester instance to add RuleSet objects to.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### getConfigURL

    protected URL getConfigURL(String path,
                               String source)
                        throws IOException

Look up a resource path using one of a set of known path resolution mechanisms and return a URL to the resource.

**Parameters:**  
`path` - a String which is meaningful to one of the known resolution mechanisms.

`source` - one of the known path resolution mechanisms:

-   file - the path is a fully-qualified filesystem path.
-   servlet - the path is a servlet-context relative path.
-   classpath - the path is a classpath-relative path.

**Returns:**  
a URL pointing to the given path in the given mechanism.

**Throws:**  
`FileNotFoundException`

`MalformedURLException`

`IOException`

------------------------------------------------------------------------

### getClassPathURL

    protected URL getClassPathURL(String path)

Given a string, return a URL to a classpath resource of that name.

**Parameters:**  
`path` - a Classpath-relative string identifying a resource.

**Returns:**  
a URL identifying the resource on the classpath. TODO Do we need to be smarter about ClassLoaders?

------------------------------------------------------------------------

### getServletContextURL

    protected URL getServletContextURL(String path)
                                throws IOException

Given a string, return a URL to a Servlet Context resource of that name.

**Parameters:**  
`path` - a Classpath-relative string identifying a resource.

**Returns:**  
a URL identifying the resource in the Servlet Context

**Throws:**  
`MalformedURLException`

`IOException`

------------------------------------------------------------------------

### getFileURL

    protected URL getFileURL(String path)
                      throws IOException

Given a string, return a URL to a Filesystem resource of that name.

**Parameters:**  
`path` - a path to a file.

**Returns:**  
a URL identifying the resource in the in the file system.

**Throws:**  
`MalformedURLException`

`FileNotFoundException`

`IOException`

------------------------------------------------------------------------

### setConfigPath

    public void setConfigPath(String configPath)

**Parameters:**  
`configPath` - the path to configuration information for this PlugIn.

**See Also:**  
[`configSource`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#configSource)

------------------------------------------------------------------------

### getConfigPath

    public String getConfigPath()

**Returns:**  
the configPath property

**See Also:**  
[`configSource`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#configSource)

------------------------------------------------------------------------

### setConfigSource

    public void setConfigSource(String configSource)

Set the source of the config file. Should be one of the following:

-   "classpath" - indicates that the configPath will be resolved by the ClassLoader.
-   "file" - indicates that the configPath is a fully-qualified filesystem path.
-   "servlet" - indicates that the configPath will be found by the ServletContext.

**Parameters:**  
`configSource` - the source (lookup method) for the config file.

**See Also:**  
[`configPath`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#configPath)

------------------------------------------------------------------------

### getConfigSource

    public String getConfigSource()

**Returns:**  
the string describing which access method should be used to resolve configPath.

**See Also:**  
[`configPath`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#configPath)

------------------------------------------------------------------------

### storeGeneratedObject

    protected void storeGeneratedObject(Object obj)

This method is called after the Digester runs to store the generated object somewhere. This implementation places the given object into the ServletContext under the attribute name as defined in `key`.

**Parameters:**  
`obj` - The object to save.

------------------------------------------------------------------------

### setKey

    public void setKey(String key)

**Parameters:**  
`key` - The ServletContext attribute name to store the generated object under.

------------------------------------------------------------------------

### getKey

    public String getKey()

**Returns:**  
The ServletContext attribute name the generated object is stored under.

------------------------------------------------------------------------

### setRulesets

    public void setRulesets(String ruleSets)

A comma-delimited list of one or more classes which implement `org.apache.commons.digester.RuleSet`. (Optional)

------------------------------------------------------------------------

### getRulesets

    public String getRulesets()

**Returns:**  
The configured list of `RuleSet` classes.

------------------------------------------------------------------------

### setDigesterPath

    public void setDigesterPath(String digesterPath)

The path to a Digester XML configuration file, relative to the `digesterSource` property. (Optional)

**See Also:**  
[`digesterSource`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#digesterSource), [`getConfigURL(String, String)`](../../../../org/apache/struts/plugins/DigestingPlugIn.html#getConfigURL(java.lang.String,%20java.lang.String))

------------------------------------------------------------------------

### getDigesterPath

    public String getDigesterPath()

**Returns:**  
the configured path to a Digester XML config file, or null.

**See Also:**  
[`digesterSource`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#digesterSource), [`getConfigURL(String, String)`](../../../../org/apache/struts/plugins/DigestingPlugIn.html#getConfigURL(java.lang.String,%20java.lang.String))

------------------------------------------------------------------------

### setDigesterSource

    public void setDigesterSource(String digesterSource)

The lookup mechanism to be used to resolve `digesterPath` (optional).

**Parameters:**  
`digesterSource` -

**See Also:**  
[`getConfigURL(String, String)`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigURL(java.lang.String,%20java.lang.String))

------------------------------------------------------------------------

### getDigesterSource

    public String getDigesterSource()

**Returns:**  
the configured lookup mechanism for resolving `digesterPath`.

**See Also:**  
[`getConfigURL(String, String)`](../../../../org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigURL(java.lang.String,%20java.lang.String))

------------------------------------------------------------------------

### setPush

    public void setPush(boolean push)

If set to `true`, this PlugIn will be pushed onto the Digester stack before the digester `parse` method is called.

Defaults to `false`

**Parameters:**  
`push` -

------------------------------------------------------------------------

### getPush

    public boolean getPush()

**Returns:**  
Whether or not this `PlugIn` instance will be pushed onto the `Digester` stack before `digester.parse()` is called.

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
<td align="left"><a href="class-use/DigestingPlugIn.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/plugins/ModuleConfigVerifier.html.md" title="class in org.apache.struts.plugins"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/plugins/DigestingPlugIn.html"><strong>FRAMES</strong></a>    <a href="DigestingPlugIn.html"><strong>NO FRAMES</strong></a>    
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
