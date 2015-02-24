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
<td align="left"><a href="class-use/ComponentDefinition.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentContext.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html" title="interface in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentDefinition.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinition.html"><strong>NO FRAMES</strong></a>    
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
 Class ComponentDefinition
--------------------------

    java.lang.Object
      org.apache.struts.tiles.ComponentDefinition

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[XmlDefinition](../../../../org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md "class in org.apache.struts.tiles.xmlDefinition")

------------------------------------------------------------------------

    public class ComponentDefinition

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Definition of a template / component attributes. Attributes of a component can be defined with the help of this class. An instance of this class can be used as a bean, and passed to 'insert' tag.

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.tiles.ComponentDefinition)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` ACTION`
           Controller name type.

`protected  Map`

` attributes`
           Attributes defined for the component.

`protected  String`

` controller`
           Associated Controller URL or classname, if defined

`static String`

` CONTROLLER`
           Controller name type.

`protected  String`

` controllerType`
           Associated Controller typename, if controllerName defined.

`protected static Log`

`log`
           Commons Logging instance.

`protected  String`

` name`
           Definition name

`protected  String`

` path`
           Component / template path (URL).

`protected  String`

` role`
           Role associated to definition.

`static String`

`URL`
           Controller name type.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                          |
|------------------------------------------------------------------|
| ` ComponentDefinition()`                                         
            Constructor.                                           |
| ` ComponentDefinition(ComponentDefinition definition)`           
            Copy Constructor.                                      |
| ` ComponentDefinition(String name, String path, Map attributes)` 
            Constructor.                                           |
| ` ComponentDefinition(XmlDefinition definition)`                 
            Constructor.                                           |

  <span id="method_summary"></span>

**Method Summary**

`static Controller`

` createController(String name, String controllerType)`
           Create a new instance of controller named in parameter.

`static Controller`

` createControllerFromClassname(String classname)`
           Create a controller from specified classname

` Object`

` getAttribute(String key)`
           Returns the value of the named attribute as an Object, or null if no attribute of the given name exists.

` Map`

` getAttributes()`
           Access method for the attributes property.

` String`

` getController()`
           Get associated controller local URL.

` Controller`

` getControllerInstance()`
           Get controller instance.

` String`

` getControllerType()`
           Get associated controller type.

` String`

` getName()`
           Access method for the name property.

` Controller`

` getOrCreateController()`
           Get or create controller.

` String`

` getPage()`
           Access method for the path property.

` String`

` getPath()`
           Access method for the path property.

` String`

` getRole()`
           Access method for the role property.

` String`

` getTemplate()`
           Access method for the template property.

` void`

` put(String name, Object content)`
           Put an attribute in component / template definition.

` void`

` put(String name, Object content, boolean direct)`
           Put an attribute in template definition.

` void`

` put(String name, Object content, boolean direct, String role)`
           Put an attribute in template definition.

` void`

` put(String name, Object content, String type, String role)`
           Put an attribute in template definition.

` void`

` putAttribute(String key, Object value)`
           Put a new attribute in this component

` void`

` setController(String url)`
           Set associated controller URL.

` void`

` setControllerClass(String controller)`
           Set associated controller name as a classtype, and controller type as "classname".

` void`

` setControllerInstance(Controller controller)`
           Set controller.

` void`

` setControllerType(String controllerType)`
           Set associated controller type.

` void`

` setControllerUrl(String controller)`
           Set associated controller name as an url, and controller type as "url".

` void`

` setName(String aName)`
           Sets the value of the name property.

` void`

` setPage(String page)`
           Sets the value of the path property.

` void`

` setPath(String aPath)`
           Sets the value of the path property.

` void`

` setRole(String role)`
           Sets the value of the role property.

` void`

` setTemplate(String template)`
           Sets the value of the template property.

` String`

` toString()`
           Returns a description of the attributes.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

Definition name

------------------------------------------------------------------------

<span id="path"></span>

### path

    protected String path

Component / template path (URL).

------------------------------------------------------------------------

<span id="attributes"></span>

### attributes

    protected Map attributes

Attributes defined for the component.

------------------------------------------------------------------------

<span id="role"></span>

### role

    protected String role

Role associated to definition.

------------------------------------------------------------------------

<span id="controller"></span>

### controller

    protected String controller

Associated Controller URL or classname, if defined

------------------------------------------------------------------------

<span id="controllerType"></span>

### controllerType

    protected String controllerType

Associated Controller typename, if controllerName defined. Can be CONTROLLER, ACTION or URL, or null.

------------------------------------------------------------------------

<span id="URL"></span>

### URL

    public static final String URL

Controller name type.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.ComponentDefinition.URL)

------------------------------------------------------------------------

<span id="CONTROLLER"></span>

### CONTROLLER

    public static final String CONTROLLER

Controller name type.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.ComponentDefinition.CONTROLLER)

------------------------------------------------------------------------

<span id="ACTION"></span>

### ACTION

    public static final String ACTION

Controller name type.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.tiles.ComponentDefinition.ACTION)

<span id="constructor_detail"></span>

**Constructor Detail**

### ComponentDefinition

    public ComponentDefinition()

Constructor.

------------------------------------------------------------------------

### ComponentDefinition

    public ComponentDefinition(ComponentDefinition definition)

Copy Constructor. Create a new definition initialized with parent definition. Do a shallow copy : attributes are shared between copies, but not the Map containing attributes.

------------------------------------------------------------------------

### ComponentDefinition

    public ComponentDefinition(XmlDefinition definition)

Constructor. Create a new definition initialized from a RawDefinition. Raw definitions are used to read definition from a data source (xml file, db, ...). A RawDefinition mainly contains properties of type String, while Definition contains more complex type (ex : Controller). Do a shallow copy : attributes are shared between objects, but not the Map containing attributes. OO Design issues : Actually RawDefinition (XmlDefinition) extends ComponentDefinition. This must not be the case. I have do it because I am lazy.

**Throws:**  
`InstantiationException` - if an error occur while instanciating Controller : (classname can't be instanciated, Illegal access with instanciated class, Error while instanciating class, classname can't be instanciated.

------------------------------------------------------------------------

### ComponentDefinition

    public ComponentDefinition(String name,
                               String path,
                               Map attributes)

Constructor.

<span id="method_detail"></span>

**Method Detail**

### getName

    public String getName()

Access method for the name property.

**Returns:**  
the current value of the name property

------------------------------------------------------------------------

### setName

    public void setName(String aName)

Sets the value of the name property.

**Parameters:**  
`aName` - the new value of the name property

------------------------------------------------------------------------

### getPage

    public String getPage()

Access method for the path property.

**Returns:**  
The current value of the path property.

------------------------------------------------------------------------

### setPage

    public void setPage(String page)

Sets the value of the path property.

**Parameters:**  
`page` - the new value of the path property

------------------------------------------------------------------------

### getPath

    public String getPath()

Access method for the path property.

**Returns:**  
the current value of the path property

------------------------------------------------------------------------

### setPath

    public void setPath(String aPath)

Sets the value of the path property.

**Parameters:**  
`aPath` - the new value of the path property

------------------------------------------------------------------------

### getTemplate

    public String getTemplate()

Access method for the template property. Same as getPath()

**Returns:**  
the current value of the template property

------------------------------------------------------------------------

### setTemplate

    public void setTemplate(String template)

Sets the value of the template property. Same as setPath()

**Parameters:**  
`template` - the new value of the path property

------------------------------------------------------------------------

### getRole

    public String getRole()

Access method for the role property.

**Returns:**  
the current value of the role property

------------------------------------------------------------------------

### setRole

    public void setRole(String role)

Sets the value of the role property.

**Parameters:**  
`role` - the new value of the path property

------------------------------------------------------------------------

### getAttributes

    public Map getAttributes()

Access method for the attributes property. If there is no attributes, return an empty map.

**Returns:**  
the current value of the attributes property

------------------------------------------------------------------------

### getAttribute

    public Object getAttribute(String key)

Returns the value of the named attribute as an Object, or null if no attribute of the given name exists.

**Returns:**  
requested attribute or null if not found

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(String key,
                             Object value)

Put a new attribute in this component

**Parameters:**  
`key` - String key for attribute

`value` - Attibute value.

------------------------------------------------------------------------

### put

    public void put(String name,
                    Object content)

Put an attribute in component / template definition. Attribute can be used as content for tag get.

**Parameters:**  
`name` - Attribute name

`content` - Attribute value

------------------------------------------------------------------------

### put

    public void put(String name,
                    Object content,
                    boolean direct)

Put an attribute in template definition. Attribute can be used as content for tag get.

**Parameters:**  
`name` - Attribute name

`content` - Attribute value Ã¯Â¿Â½

`direct` - Determines how content is handled by get tag: true means content is printed directly; false, the default, means content is included

------------------------------------------------------------------------

### put

    public void put(String name,
                    Object content,
                    boolean direct,
                    String role)

Put an attribute in template definition. Attribute can be used as content for tag get.

**Parameters:**  
`name` - Attribute name

`content` - Attribute value

`direct` - Determines how content is handled by get tag: true means content is printed directly; false, the default, means content is included

`role` - Determine if content is used by get tag. If user is in role, content is used.

------------------------------------------------------------------------

### put

    public void put(String name,
                    Object content,
                    String type,
                    String role)

Put an attribute in template definition. Attribute can be used as content for tag get.

**Parameters:**  
`name` - Attribute name

`content` - Attribute value

`type` - attribute type: template, string, definition

`role` - Determine if content is used by get tag. If user is in role, content is used.

------------------------------------------------------------------------

### toString

    public String toString()

Returns a description of the attributes.

**Overrides:**  
`toString` in class `Object`

------------------------------------------------------------------------

### getControllerType

    public String getControllerType()

Get associated controller type. Type denote a fully qualified classname.

------------------------------------------------------------------------

### setControllerType

    public void setControllerType(String controllerType)

Set associated controller type. Type denote a fully qualified classname.

**Parameters:**  
`controllerType` - Typeof associated controller

------------------------------------------------------------------------

### setControllerUrl

    public void setControllerUrl(String controller)

Set associated controller name as an url, and controller type as "url". Name must be an url (not checked). Convenience method.

**Parameters:**  
`controller` - Controller url

------------------------------------------------------------------------

### setControllerClass

    public void setControllerClass(String controller)

Set associated controller name as a classtype, and controller type as "classname". Name denote a fully qualified classname Convenience method.

**Parameters:**  
`controller` - Controller classname.

------------------------------------------------------------------------

### getController

    public String getController()

Get associated controller local URL. URL should be local to webcontainer in order to allow request context followup. URL comes as a string.

------------------------------------------------------------------------

### setController

    public void setController(String url)

Set associated controller URL. URL should be local to webcontainer in order to allow request context followup. URL is specified as a string.

**Parameters:**  
`url` - Url called locally

------------------------------------------------------------------------

### getControllerInstance

    public Controller getControllerInstance()

Get controller instance.

**Returns:**  
controller instance.

------------------------------------------------------------------------

### getOrCreateController

    public Controller getOrCreateController()
                                     throws InstantiationException

Get or create controller. Get controller, create it if necessary.

**Returns:**  
controller if controller or controllerType is set, null otherwise.

**Throws:**  
`InstantiationException` - if an error occur while instanciating Controller : (classname can't be instanciated, Illegal access with instanciated class, Error while instanciating class, classname can't be instanciated.

------------------------------------------------------------------------

### setControllerInstance

    public void setControllerInstance(Controller controller)

Set controller.

------------------------------------------------------------------------

### createController

    public static Controller createController(String name,
                                              String controllerType)
                                       throws InstantiationException

Create a new instance of controller named in parameter. If controllerType is specified, create controller accordingly. Otherwise, if name denote a classname, create an instance of it. If class is subclass of org.apache.struts.action.Action, wrap controller appropriately. Otherwise, consider name as an url.

**Parameters:**  
`name` - Controller name (classname, url, ...)

`controllerType` - Expected Controller type

**Returns:**  
org.apache.struts.tiles.Controller

**Throws:**  
`InstantiationException` - if an error occur while instanciating Controller : (classname can't be instanciated, Illegal access with instanciated class, Error while instanciating class, classname can't be instanciated.

------------------------------------------------------------------------

### createControllerFromClassname

    public static Controller createControllerFromClassname(String classname)
                                                    throws InstantiationException

Create a controller from specified classname

**Parameters:**  
`classname` - Controller classname.

**Returns:**  
org.apache.struts.tiles.Controller

**Throws:**  
`InstantiationException` - if an error occur while instanciating Controller : (classname can't be instanciated, Illegal access with instanciated class, Error while instanciating class, classname can't be instanciated.

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
<td align="left"><a href="class-use/ComponentDefinition.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/ComponentContext.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/tiles/ComponentDefinitionsFactory.html" title="interface in org.apache.struts.tiles"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/ComponentDefinition.html"><strong>FRAMES</strong></a>    <a href="ComponentDefinition.html"><strong>NO FRAMES</strong></a>    
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
