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
<td align="left"><a href="class-use/ActionForward.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionFormBean.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMapping.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ForwardConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.config.ForwardConfig">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class ActionForward
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ForwardConfig
              org.apache.struts.action.ActionForward

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[ActionRedirect](../../../../org/apache/struts/action/ActionRedirect.html.md "class in org.apache.struts.action"), [ForwardingActionForward](../../../../org/apache/struts/action/ForwardingActionForward.html "class in org.apache.struts.action"), [RedirectingActionForward](../../../../org/apache/struts/action/RedirectingActionForward.html "class in org.apache.struts.action")

------------------------------------------------------------------------

    public class ActionForward

extends [ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")

An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class. Instances of this class may be created dynamically as necessary, or configured in association with an ActionMapping instance for named lookup of potentially multiple destinations for a particular mapping instance.

An ActionForward has the following minimal set of properties. Additional properties can be provided as needed by subclassses.

-   **contextRelative** - Should the path value be interpreted as context-relative (instead of module-relative, if it starts with a '/' character? [false]
-   **name** - Logical name by which this instance may be looked up in relationship to a particular ActionMapping.
-   **path** - Module-relative or context-relative URI to which control should be forwarded, or an absolute or relative URI to which control should be redirected.
-   **redirect** - Set to true if the controller servlet should call HttpServletResponse.sendRedirect() on the associated path; otherwise false. [false]

Since Struts 1.1 this class extends ForwardConfig and inherits the contextRelative property.

**NOTE** - This class would have been deprecated and replaced by org.apache.struts.config.ForwardConfig except for the fact that it is part of the public API that existing applications are using.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionForward)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Fields inherited from class org.apache.struts.config.[ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `catalog, command,  extensionProcessed, inherit, module, name, path, redirect`                                                                                        |

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                    |
|--------------------------------------------------------------------------------------------|
| ` ActionForward()`                                                                         
            Construct a new instance with default values.                                    |
| ` ActionForward(ActionForward copyMe)`                                                     
            Construct a new instance based on the values of another ActionForward.           |
| ` ActionForward(String path)`                                                              
            Construct a new instance with the specified path.                                |
| ` ActionForward(String path, boolean redirect)`                                            
            Construct a new instance with the specified `path` and `redirect` flag.          |
| ` ActionForward(String name, String path, boolean redirect)`                               
            Construct a new instance with the specified `name`, `path` and `redirect` flag.  |
| ` ActionForward(String name, String path, boolean redirect, String module)`                
            Construct a new instance with the specified values.                              |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_org.apache.struts.config.ForwardConfig"></span>

| **Methods inherited from class org.apache.struts.config.[ForwardConfig](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config")**                                                                                                 |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` checkCircularInheritance,  getCatalog,  getCommand,  getExtends,  getModule,  getName,  getPath,  getRedirect,  inheritFrom,  isExtensionProcessed,  processExtends,  setCatalog,  setCommand,  setExtends,  setModule,  setName,  setPath,  setRedirect,  toString` |

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties, freeze,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                    |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionForward

    public ActionForward()

Construct a new instance with default values.

------------------------------------------------------------------------

### ActionForward

    public ActionForward(String path)

Construct a new instance with the specified path.

**Parameters:**  
`path` - Path for this instance

------------------------------------------------------------------------

### ActionForward

    public ActionForward(String path,
                         boolean redirect)

Construct a new instance with the specified `path` and `redirect` flag.

**Parameters:**  
`path` - Path for this instance

`redirect` - Redirect flag for this instance

------------------------------------------------------------------------

### ActionForward

    public ActionForward(String name,
                         String path,
                         boolean redirect)

Construct a new instance with the specified `name`, `path` and `redirect` flag.

**Parameters:**  
`name` - Name of this instance

`path` - Path for this instance

`redirect` - Redirect flag for this instance

------------------------------------------------------------------------

### ActionForward

    public ActionForward(String name,
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

### ActionForward

    public ActionForward(ActionForward copyMe)

Construct a new instance based on the values of another ActionForward.

**Parameters:**  
`copyMe` - An ActionForward instance to copy

**Since:**  
Struts 1.2.1

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
<td align="left"><a href="class-use/ActionForward.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionFormBean.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionMapping.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionForward.html"><strong>FRAMES</strong></a>    <a href="ActionForward.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.config.ForwardConfig">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_org.apache.struts.config.ForwardConfig">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
