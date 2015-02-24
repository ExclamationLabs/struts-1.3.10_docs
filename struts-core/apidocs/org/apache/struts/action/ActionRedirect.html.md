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
<td align="left"><a href="class-use/ActionRedirect.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMessages.ActionMessageItem.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionServlet.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionRedirect.html"><strong>FRAMES</strong></a>    <a href="ActionRedirect.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class ActionRedirect
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ForwardConfig
              org.apache.struts.action.ActionForward
                  org.apache.struts.action.ActionRedirect

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ActionRedirect

extends [ActionForward](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action")

A subclass of [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.
 An [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") (or subclass) can be passed to the constructor to copy its configuration:

     public ActionForward execute(ActionMapping mapping,
                                  ActionForm form,
                                  HttpServletRequest request,
                                  HttpServletResponse response)
             throws Exception {
         ActionRedirect redirect =
                 new ActionRedirect(mapping.findForward("doRedirect"));
         redirect.addParameter("param1","value1");
         redirect.addParameter("param2","2");
         redirect.addParameter("param3","3.0");
         return redirect;
     }
     

**Version:**  
$Rev: 513602 $ $Date: 2007-03-01 20:50:23 -0600 (Thu, 01 Mar 2007) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionRedirect)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` anchorValue`
           Holds the anchor value.

`protected static Log`

`LOG`
           Commons logging instance.

`protected  Map`

` parameterValues`
           Holds the redirect parameters.

 <span id="fields_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `catalog, command,  extensionProcessed, inherit, module, name, path, redirect`                                                                                        |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                                                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionRedirect()`                                                                                                                                                                                                                       
            Construct a new instance with redirect set to true and initialize parameter lists.                                                                                                                                              |
| ` ActionRedirect(ForwardConfig baseConfig)`                                                                                                                                                                                               
            Construct a new instance with a [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") object to copy name, path, contextRelative, and arbitrary property values from.  |
| ` ActionRedirect(String path)`                                                                                                                                                                                                            
            Construct a new instance with the specified path and initialize parameter lists.                                                                                                                                                |
| ` ActionRedirect(String name, String path, String module)`                                                                                                                                                                                
            Construct a new instance with the specified values and initialize parameter lists.                                                                                                                                              |

  <span id="method_summary"></span>

**Method Summary**

` ActionRedirect`

` addParameter(String fieldName, Object valueObj)`
           Adds the object's toString() to the list of parameters if it's not null, or an empty string with the given fieldName if it is.

` String`

` getAnchorString()`
           Forms the string containing the parameters passed onto this object thru calls to addParameter().

` String`

` getOriginalPath()`
           Get the original path without the parameters added at runtime.

` String`

` getParameterString()`
           Forms the string containing the parameters passed onto this object thru calls to addParameter().

` String`

` getPath()`
           Get the path for this object, including any parameters that may have been added at runtime.

` ActionRedirect`

` setAnchor(String anchorValue)`
           Adds an anchor to the path.

` String`

` toString()`
           Return a string description of this object.

 <span id="methods_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")**                                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` checkCircularInheritance,  getCatalog,  getCommand,  getExtends,  getModule,  getName,  getRedirect,  inheritFrom,  isExtensionProcessed,  processExtends,  setCatalog,  setCommand,  setExtends,  setModule,  setName,  setPath,  setRedirect` |

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

<span id="LOG"></span>

### LOG

    protected static final Log LOG

Commons logging instance.

------------------------------------------------------------------------

<span id="parameterValues"></span>

### parameterValues

    protected Map parameterValues

Holds the redirect parameters. Each entry is either a String or a String[] depending on whether it has one or more entries.

------------------------------------------------------------------------

<span id="anchorValue"></span>

### anchorValue

    protected String anchorValue

Holds the anchor value.

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionRedirect

    public ActionRedirect()

Construct a new instance with redirect set to true and initialize parameter lists.

------------------------------------------------------------------------

### ActionRedirect

    public ActionRedirect(String path)

Construct a new instance with the specified path and initialize parameter lists.

**Parameters:**  
`path` - Path for this instance

------------------------------------------------------------------------

### ActionRedirect

    public ActionRedirect(String name,
                          String path,
                          String module)

Construct a new instance with the specified values and initialize parameter lists.

**Parameters:**  
`name` - Name of this instance

`path` - Path for this instance

`module` - Module prefix, if any

------------------------------------------------------------------------

### ActionRedirect

    public ActionRedirect(ForwardConfig baseConfig)

Construct a new instance with a [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") object to copy name, path, contextRelative, and arbitrary property values from.

**Parameters:**  
`baseConfig` - the [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") to copy configuration values from

<span id="method_detail"></span>

**Method Detail**

### addParameter

    public ActionRedirect addParameter(String fieldName,
                                       Object valueObj)

Adds the object's toString() to the list of parameters if it's not null, or an empty string with the given fieldName if it is.

**Parameters:**  
`fieldName` - the name to use for the parameter

`valueObj` - the value for this parameter

**Returns:**  
The ActionRedirect instance this method is called on

------------------------------------------------------------------------

### setAnchor

    public ActionRedirect setAnchor(String anchorValue)

Adds an anchor to the path. Technically, the anchor value is just stored for later and will be added to the path in getPath(). Note that this is a considerably simpler method than the addParmaeter method because aside from encoding the value, there isn't really anything to do. Passing in null is fine because that is the value that will be checked for later to determine whether to append an anchor to the path or not.

**Parameters:**  
`anchorValue` - The anchor to append to the path

**Returns:**  
The ActionRefirect instance this method is called on

------------------------------------------------------------------------

### getOriginalPath

    public String getOriginalPath()

Get the original path without the parameters added at runtime.

**Returns:**  
the original path as configured.

------------------------------------------------------------------------

### getPath

    public String getPath()

Get the path for this object, including any parameters that may have been added at runtime.

**Overrides:**  
` getPath` in class `ForwardConfig`

<!-- -->

**Returns:**  
The path for this object.

------------------------------------------------------------------------

### getAnchorString

    public String getAnchorString()

Forms the string containing the parameters passed onto this object thru calls to addParameter().

**Returns:**  
a string which can be appended to the URLs. The return string includes a leading hash mark (\#).

------------------------------------------------------------------------

### getParameterString

    public String getParameterString()

Forms the string containing the parameters passed onto this object thru calls to addParameter().

**Returns:**  
a string which can be appended to the URLs. The return string does not include a leading question mark (?).

------------------------------------------------------------------------

### toString

    public String toString()

Return a string description of this object.

**Overrides:**  
` toString` in class `ForwardConfig`

<!-- -->

**Returns:**  
a string containing the original path for this object and the parameters it currently holds

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
<td align="left"><a href="class-use/ActionRedirect.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionMessages.ActionMessageItem.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionServlet.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionRedirect.html"><strong>FRAMES</strong></a>    <a href="ActionRedirect.html"><strong>NO FRAMES</strong></a>    
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
