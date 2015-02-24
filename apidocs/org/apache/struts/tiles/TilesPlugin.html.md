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
<td align="left"><a href="class-use/TilesPlugin.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesException.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesRequestProcessor.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesPlugin.html"><strong>FRAMES</strong></a>    <a href="TilesPlugin.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles
 Class TilesPlugin
-----------------------

    java.lang.Object
      org.apache.struts.tiles.TilesPlugin

**All Implemented Interfaces:**  
[PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

------------------------------------------------------------------------

    public class TilesPlugin

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [PlugIn](../../../../org/apache/struts/action/PlugIn.html.md "interface in org.apache.struts.action")

Tiles Plugin used to initialize Tiles. This plugin is to be used with Struts 1.1 in association with [`TilesRequestProcessor`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md "class in org.apache.struts.tiles").
 This plugin creates one definition factory for each Struts-module. The definition factory configuration is read first from 'web.xml' (backward compatibility), then it is overloaded with values found in the plugin property values.
 The plugin changes the Struts configuration by specifying a [`TilesRequestProcessor`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html.md "class in org.apache.struts.tiles") as request processor. If you want to use your own RequestProcessor, it should subclass TilesRequestProcessor.
 This plugin can also be used to create one single factory for all modules. This behavior is enabled by specifying `moduleAware=false` in each plugin properties. In this case, the definition factory configuration file is read by the first Tiles plugin to be initialized. The order is determined by the order of modules declaration in web.xml. The first module is always the default one if it exists. The plugin should be declared in each struts-config.xml file in order to properly initialize the request processor.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  PlugInConfig`

` currentPlugInConfigObject`
           The plugin config object provided by the ActionServlet initializing this plugin.

`protected  DefinitionsFactory`

` definitionFactory`
           Associated definition factory.

`protected static Log`

`log`
           Commons Logging instance.

`protected  boolean`

`moduleAware`
           Is the factory module aware?

`protected  String`

` tilesUtilImplClassname`
           Tiles util implementation classname.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TilesPlugin()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

`destroy()`
           End plugin.

`protected  Map`

` findStrutsPlugInConfigProperties(ActionServlet servlet, ModuleConfig config)`
           Find original properties set in the Struts PlugInConfig object.

` String`

` getTilesUtilImplClassname()`
           Get Tiles util implemention classname.

` void`

` init(ActionServlet servlet, ModuleConfig moduleConfig)`
           Receive notification that the specified module is being started up.

`protected  void`

` initRequestProcessorClass(ModuleConfig config)`
           Set RequestProcessor to appropriate Tiles [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action").

` boolean`

` isModuleAware()`
           Get the module aware flag.

`protected  DefinitionsFactoryConfig`

` readFactoryConfig(ActionServlet servlet, ModuleConfig config)`
           Create FactoryConfig and initialize it from web.xml and struts-config.xml.

` void`

` setCurrentPlugInConfigObject(PlugInConfig plugInConfigObject)`
           Method used by the ActionServlet initializing this plugin.

` void`

` setModuleAware(boolean moduleAware)`
           Set the module aware flag.

` void`

` setTilesUtilImplClassname(String tilesUtilImplClassname)`
           Set Tiles util implemention classname.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="moduleAware"></span>

### moduleAware

    protected boolean moduleAware

Is the factory module aware?

------------------------------------------------------------------------

<span id="tilesUtilImplClassname"></span>

### tilesUtilImplClassname

    protected String tilesUtilImplClassname

Tiles util implementation classname. This property can be set by user in the plugin declaration.

------------------------------------------------------------------------

<span id="definitionFactory"></span>

### definitionFactory

    protected DefinitionsFactory definitionFactory

Associated definition factory.

------------------------------------------------------------------------

<span id="currentPlugInConfigObject"></span>

### currentPlugInConfigObject

    protected PlugInConfig currentPlugInConfigObject

The plugin config object provided by the ActionServlet initializing this plugin.

<span id="constructor_detail"></span>

**Constructor Detail**

### TilesPlugin

    public TilesPlugin()

<span id="method_detail"></span>

**Method Detail**

### isModuleAware

    public boolean isModuleAware()

Get the module aware flag.

**Returns:**  
`true`: user wants a single factory instance, `false:` user wants multiple factory instances (one per module with Struts)

------------------------------------------------------------------------

### setModuleAware

    public void setModuleAware(boolean moduleAware)

Set the module aware flag. This flag is only meaningful if the property `tilesUtilImplClassname` is not set.

**Parameters:**  
`moduleAware` - `true`: user wants a single factory instance, `false:` user wants multiple factory instances (one per module with Struts)

------------------------------------------------------------------------

### init

    public void init(ActionServlet servlet,
                     ModuleConfig moduleConfig)
              throws ServletException

Receive notification that the specified module is being started up.

**Specified by:**  
` init` in interface `PlugIn`

<!-- -->

**Parameters:**  
`servlet` - ActionServlet that is managing all the modules in this web application.

`moduleConfig` - ModuleConfig for the module with which this plugin is associated.

**Throws:**  
`ServletException` - if this `PlugIn` cannot be successfully initialized.

------------------------------------------------------------------------

### destroy

    public void destroy()

End plugin.

**Specified by:**  
`destroy` in interface `PlugIn`

------------------------------------------------------------------------

### readFactoryConfig

    protected DefinitionsFactoryConfig readFactoryConfig(ActionServlet servlet,
                                                         ModuleConfig config)
                                                  throws ServletException

Create FactoryConfig and initialize it from web.xml and struts-config.xml.

**Parameters:**  
`servlet` - ActionServlet that is managing all the modules in this web application.

`config` - ModuleConfig for the module with which this plugin is associated.

**Throws:**  
`ServletException` - if this `PlugIn` cannot be successfully initialized.

------------------------------------------------------------------------

### findStrutsPlugInConfigProperties

    protected Map findStrutsPlugInConfigProperties(ActionServlet servlet,
                                                   ModuleConfig config)
                                            throws ServletException

Find original properties set in the Struts PlugInConfig object. First, we need to find the index of this plugin. Then we retrieve the array of configs and then the object for this plugin.

**Parameters:**  
`servlet` - ActionServlet that is managing all the modules in this web application.

`config` - ModuleConfig for the module with which this plug in is associated.

**Throws:**  
`ServletException` - if this `PlugIn` cannot be successfully initialized.

------------------------------------------------------------------------

### initRequestProcessorClass

    protected void initRequestProcessorClass(ModuleConfig config)
                                      throws ServletException

Set RequestProcessor to appropriate Tiles [`RequestProcessor`](../../../../org/apache/struts/action/RequestProcessor.html.md "class in org.apache.struts.action"). First, check if a RequestProcessor is specified. If yes, check if it extends the appropriate [`TilesRequestProcessor`](../../../../org/apache/struts/tiles/TilesRequestProcessor.html "class in org.apache.struts.tiles") class. If not, set processor class to TilesRequestProcessor.

**Parameters:**  
`config` - ModuleConfig for the module with which this plugin is associated.

**Throws:**  
`ServletException` - On errors.

------------------------------------------------------------------------

### setTilesUtilImplClassname

    public void setTilesUtilImplClassname(String tilesUtilImplClassname)

Set Tiles util implemention classname. If this property is set, the flag `moduleAware` will not be used anymore.

**Parameters:**  
`tilesUtilImplClassname` - Classname.

------------------------------------------------------------------------

### getTilesUtilImplClassname

    public String getTilesUtilImplClassname()

Get Tiles util implemention classname.

**Returns:**  
The classname or `null` if none is set.

------------------------------------------------------------------------

### setCurrentPlugInConfigObject

    public void setCurrentPlugInConfigObject(PlugInConfig plugInConfigObject)

Method used by the ActionServlet initializing this plugin. Set the plugin config object read from module config.

**Parameters:**  
`plugInConfigObject` - PlugInConfig.

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
<td align="left"><a href="class-use/TilesPlugin.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/TilesException.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/TilesRequestProcessor.html" title="class in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TilesPlugin.html"><strong>FRAMES</strong></a>    <a href="TilesPlugin.html"><strong>NO FRAMES</strong></a>    
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
