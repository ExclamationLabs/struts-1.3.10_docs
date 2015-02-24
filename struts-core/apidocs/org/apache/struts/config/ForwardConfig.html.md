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
<td align="left"><a href="class-use/ForwardConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/FormPropertyConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/MessageResourcesConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ForwardConfig.html"><strong>FRAMES</strong></a>    <a href="ForwardConfig.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class ForwardConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ForwardConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[ActionForward](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

    public class ForwardConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.ForwardConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`catalog`
           The name of a `commons-chain` catalog in which `command` should be looked up.

`protected  String`

`command`
           The name of a `commons-chain` command which should be looked up and executed before Struts dispatches control to the view represented by this config.

`protected  boolean`

` extensionProcessed`
           Have the inheritance values for this class been applied?

`protected  String`

`inherit`
           The name of the ForwardConfig that this object should inherit properties from.

`protected  String`

`module`
           The prefix of the module to which this `ForwardConfig` entry points, which must start with a slash ("/") character.

`protected  String`

`name`
           The unique identifier of this forward, which is used to reference it in `Action` classes.

`protected  String`

`path`
           The URL to which this `ForwardConfig` entry points, which must start with a slash ("/") character.

`protected  boolean`

`redirect`
           Should a redirect be used to transfer control to the specified path?

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                           |
|-----------------------------------------------------------------------------------|
| ` ForwardConfig()`                                                                
            Construct a new instance with default values.                           |
| ` ForwardConfig(ForwardConfig copyMe)`                                            
            Construct a new instance based on the values of another ForwardConfig.  |
| ` ForwardConfig(String name, String path, boolean redirect)`                      
            Construct a new instance with the specified values.                     |
| ` ForwardConfig(String name, String path, boolean redirect, String module)`       
            Construct a new instance with the specified values.                     |

  <span id="method_summary"></span>

**Method Summary**

`protected  boolean`

` checkCircularInheritance(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

` String`

` getCatalog()`
            

` String`

` getCommand()`
            

` String`

` getExtends()`
            

` String`

` getModule()`
            

` String`

` getName()`
            

` String`

` getPath()`
            

` boolean`

` getRedirect()`
            

` void`

` inheritFrom(ForwardConfig config)`
           Inherit values that have not been overridden from the provided config object.

` boolean`

` isExtensionProcessed()`
            

` void`

` processExtends(ModuleConfig moduleConfig, ActionConfig actionConfig)`
           Inherit configuration information from the ForwardConfig that this instance is extending.

` void`

` setCatalog(String catalog)`
            

` void`

` setCommand(String command)`
            

` void`

` setExtends(String inherit)`
            

` void`

` setModule(String module)`
            

` void`

` setName(String name)`
            

` void`

` setPath(String path)`
            

` void`

` setRedirect(boolean redirect)`
            

` String`

` toString()`
           Return a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties, freeze,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                    |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="inherit"></span>

### inherit

    protected String inherit

The name of the ForwardConfig that this object should inherit properties from.

------------------------------------------------------------------------

<span id="extensionProcessed"></span>

### extensionProcessed

    protected boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The unique identifier of this forward, which is used to reference it in `Action` classes.

------------------------------------------------------------------------

<span id="path"></span>

### path

    protected String path

The URL to which this `ForwardConfig` entry points, which must start with a slash ("/") character. It is interpreted according to the following rules:

-   If `contextRelative` property is `true`, the path is considered to be context-relative within the current web application (even if we are in a named module). It will be prefixed by the context path to create a server-relative URL.
-   If the `contextRelative` property is false, the path is considered to be the module-relative portion of the URL. It will be used as the replacement for the `$P` marker in the `forwardPattern` property defined on the [`ControllerConfig`](../../../../org/apache/struts/config/ControllerConfig.html.md "class in org.apache.struts.config") element for our current module. For the default `forwardPattern` value of `$C$M$P`, the resulting server-relative URL will be the concatenation of the context path, the module prefix, and the `path` from this `ForwardConfig`.

------------------------------------------------------------------------

<span id="module"></span>

### module

    protected String module

The prefix of the module to which this `ForwardConfig` entry points, which must start with a slash ("/") character.

Usage note: If a forward config is used in a hyperlink, and a module is specified, the path must lead to another action and not directly to a page. This is in keeping with rule that in a modular application all links must be to an action rather than a page.

------------------------------------------------------------------------

<span id="redirect"></span>

### redirect

    protected boolean redirect

Should a redirect be used to transfer control to the specified path?

------------------------------------------------------------------------

<span id="command"></span>

### command

    protected String command

The name of a `commons-chain` command which should be looked up and executed before Struts dispatches control to the view represented by this config.

------------------------------------------------------------------------

<span id="catalog"></span>

### catalog

    protected String catalog

The name of a `commons-chain` catalog in which `command` should be looked up. If this value is undefined, then the command will be looked up in the "default" catalog. This value has no meaning except in the context of the `command` property.

<span id="constructor_detail"></span>

**Constructor Detail**

### ForwardConfig

    public ForwardConfig()

Construct a new instance with default values.

------------------------------------------------------------------------

### ForwardConfig

    public ForwardConfig(String name,
                         String path,
                         boolean redirect)

Construct a new instance with the specified values.

**Parameters:**  
`name` - Name of this forward

`path` - Path to which control should be forwarded or redirected

`redirect` - Should we do a redirect?

------------------------------------------------------------------------

### ForwardConfig

    public ForwardConfig(String name,
                         String path,
                         boolean redirect,
                         String module)

Construct a new instance with the specified values.

**Parameters:**  
`name` - Name of this forward

`path` - Path to which control should be forwarded or redirected

`redirect` - Should we do a redirect?

`module` - Module prefix, if any

------------------------------------------------------------------------

### ForwardConfig

    public ForwardConfig(ForwardConfig copyMe)

Construct a new instance based on the values of another ForwardConfig.

**Parameters:**  
`copyMe` - A ForwardConfig instance to copy

**Since:**  
Struts 1.3.6

<span id="method_detail"></span>

**Method Detail**

### getExtends

    public String getExtends()

------------------------------------------------------------------------

### setExtends

    public void setExtends(String inherit)

------------------------------------------------------------------------

### isExtensionProcessed

    public boolean isExtensionProcessed()

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getPath

    public String getPath()

------------------------------------------------------------------------

### setPath

    public void setPath(String path)

------------------------------------------------------------------------

### getModule

    public String getModule()

------------------------------------------------------------------------

### setModule

    public void setModule(String module)

------------------------------------------------------------------------

### getRedirect

    public boolean getRedirect()

------------------------------------------------------------------------

### setRedirect

    public void setRedirect(boolean redirect)

------------------------------------------------------------------------

### getCommand

    public String getCommand()

------------------------------------------------------------------------

### setCommand

    public void setCommand(String command)

------------------------------------------------------------------------

### getCatalog

    public String getCatalog()

------------------------------------------------------------------------

### setCatalog

    public void setCatalog(String catalog)

------------------------------------------------------------------------

### checkCircularInheritance

    protected boolean checkCircularInheritance(ModuleConfig moduleConfig,
                                               ActionConfig actionConfig)

Traces the hierarchy of this object to check if any of the ancestors are extending this instance.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this config is from.

`actionConfig` - The [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") that this config is from, if applicable. This parameter must be null if this forward config is a global forward.

**Returns:**  
true if circular inheritance was detected.

------------------------------------------------------------------------

### inheritFrom

    public void inheritFrom(ForwardConfig config)
                     throws ClassNotFoundException,
                            IllegalAccessException,
                            InstantiationException,
                            InvocationTargetException

Inherit values that have not been overridden from the provided config object. Subclasses overriding this method should verify that the given parameter is of a class that contains a property it is trying to inherit:

     if (config instanceof MyCustomConfig) {
         MyCustomConfig myConfig =
             (MyCustomConfig) config;

         if (getMyCustomProp() == null) {
             setMyCustomProp(myConfig.getMyCustomProp());
         }
     }
     

If the given `config` is extending another object, those extensions should be resolved before it's used as a parameter to this method.

**Parameters:**  
`config` - The object that this instance will be inheriting its values from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`processExtends(ModuleConfig, ActionConfig)`](../../../../org/apache/struts/config/ForwardConfig.html.md#processExtends(org.apache.struts.config.ModuleConfig,%20org.apache.struts.config.ActionConfig))

------------------------------------------------------------------------

### processExtends

    public void processExtends(ModuleConfig moduleConfig,
                               ActionConfig actionConfig)
                        throws ClassNotFoundException,
                               IllegalAccessException,
                               InstantiationException,
                               InvocationTargetException

Inherit configuration information from the ForwardConfig that this instance is extending. This method verifies that any forward config object that it inherits from has also had its processExtends() method called.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this config is from.

`actionConfig` - The [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") that this config is from, if applicable. This must be null for global forwards.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(ForwardConfig)`](../../../../org/apache/struts/config/ForwardConfig.html.md#inheritFrom(org.apache.struts.config.ForwardConfig))

------------------------------------------------------------------------

### toString

    public String toString()

Return a String representation of this object.

**Overrides:**  
`toString` in class `Object`

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
<td align="left"><a href="class-use/ForwardConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/FormPropertyConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/MessageResourcesConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ForwardConfig.html"><strong>FRAMES</strong></a>    <a href="ForwardConfig.html"><strong>NO FRAMES</strong></a>    
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
