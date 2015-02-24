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
<td align="left"><a href="class-use/ActionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/config/ActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ActionConfig.html"><strong>FRAMES</strong></a>    <a href="ActionConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class ActionConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ActionConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[ActionMapping](../../../../org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

    public class ActionConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 480593 $ $Date: 2006-11-29 09:17:52 -0600 (Wed, 29 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.ActionConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`actionId`
           The internal identification of this action mapping.

`protected  String`

`attribute`
            The request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

`protected  boolean`

` cancellable`
           Can this Action be cancelled? [false]

`protected  String`

`catalog`
            The name of a `commons-chain` catalog in which `command` should be sought.

`protected  String`

`command`
            The name of a `commons-chain` command which should be executed as part of the processing of this action.

`protected  HashMap`

` exceptions`
            The set of exception handling configurations for this action, if any, keyed by the `type` property.

`protected  boolean`

` extensionProcessed`
            Have the inheritance values for this class been applied?

`protected  String`

`forward`
            Context-relative path of the web application resource that will process this request via RequestDispatcher.forward(), instead of instantiating and calling the `Action` class specified by "type".

`protected  HashMap`

`forwards`
            The set of local forward configurations for this action, if any, keyed by the `name` property.

`protected  String`

`include`
            Context-relative path of the web application resource that will process this request via RequestDispatcher.include(), instead of instantiating and calling the `Action` class specified by "type".

`protected  String`

`inherit`
           The path of the ActionConfig that this object should inherit properties from.

`protected  String`

`input`
            Context-relative path of the input form to which control should be returned if a validation error is encountered.

`protected  ModuleConfig`

` moduleConfig`
            The module configuration with which we are associated.

`protected  String`

` multipartClass`
            Fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

`protected  String`

`name`
            Name of the form bean, if any, associated with this Action.

`protected  String`

`parameter`
            General purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action.

`protected  String`

`path`
            Context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

`protected  String`

`prefix`
            Prefix used to match request parameter names to form bean property names, if any.

`protected  String[]`

`roleNames`
            The set of security role names used to authorize access to this Action, as an array for faster access.

`protected  String`

`roles`
            Comma-delimited list of security role names allowed to request this Action.

`protected  String`

`scope`
            Identifier of the scope ("request" or "session") within which our form bean is accessed, if any.

`protected  String`

`suffix`
            Suffix used to match request parameter names to form bean property names, if any.

`protected  String`

`type`
            Fully qualified Java class name of the `Action` class to be used to process requests for this mapping if the `forward` and `include` properties are not set.

`protected  boolean`

`unknown`
            Indicates Action be configured as the default one for this module, when true.

`protected  boolean`

`validate`
            Should the `validate()` method of the form bean associated with this action be called?

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ActionConfig()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addExceptionConfig(ExceptionConfig config)`
            Add a new `ExceptionConfig` instance to the set associated with this action.

` void`

` addForwardConfig(ForwardConfig config)`
            Add a new `ForwardConfig` instance to the set of global forwards associated with this action.

`protected  boolean`

` checkCircularInheritance(ModuleConfig moduleConfig)`
           Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

` ExceptionConfig`

` findException(Class type)`
           Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled.

` ExceptionConfig`

` findExceptionConfig(String type)`
            Return the exception configuration for the specified type, if any; otherwise return `null`.

` ExceptionConfig[]`

` findExceptionConfigs()`
            Return the exception configurations for this action.

` ForwardConfig`

` findForwardConfig(String name)`
            Return the forward configuration for the specified key, if any; otherwise return `null`.

` ForwardConfig[]`

` findForwardConfigs()`
            Return all forward configurations for this module.

` void`

`freeze()`
            Freeze the configuration of this action.

` String`

` getActionId()`
           The internal name of this action mapping.

` String`

` getAttribute()`
            Returns the request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

` boolean`

` getCancellable()`
           Accessor for cancellable property

` String`

` getCatalog()`
            Get the name of a `commons-chain` catalog in which a specified command should be sought.

` String`

` getCommand()`
            Get the name of a `commons-chain` command which should be executed as part of the processing of this action.

` String`

` getExtends()`
           Returns the path of the ActionConfig that this object should inherit properties from.

` String`

` getForward()`
            Returns context-relative path of the web application resource that will process this request.

` String`

` getInclude()`
            Context-relative path of the web application resource that will process this request.

` String`

` getInput()`
            Get the context-relative path of the input form to which control should be returned if a validation error is encountered.

` ModuleConfig`

` getModuleConfig()`
            The module configuration with which we are associated.

` String`

` getMultipartClass()`
            Return the fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

` String`

`getName()`
            Return name of the form bean, if any, associated with this Action.

` String`

` getParameter()`
            Return general purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action.

` String`

`getPath()`
            Return context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

` String`

` getPrefix()`
            Retruns prefix used to match request parameter names to form bean property names, if any.

` String[]`

` getRoleNames()`
            Get array of security role names used to authorize access to this Action.

` String`

` getRoles()`
            

` String`

` getScope()`
            Get the scope ("request" or "session") within which our form bean is accessed, if any.

` String`

` getSuffix()`
            Return suffix used to match request parameter names to form bean property names, if any.

` String`

`getType()`
            

` boolean`

` getUnknown()`
            Determine whether Action is configured as the default one for this module.

` boolean`

` getValidate()`
            

`protected  void`

` inheritExceptionHandlers(ActionConfig baseConfig)`
           Compare the exception handlers of this action with that of the given and copy those that are not present.

`protected  void`

` inheritForwards(ActionConfig baseConfig)`
           Compare the forwards of this action with that of the given and copy those that are not present.

` void`

` inheritFrom(ActionConfig config)`
           Inherit values that have not been overridden from the provided config object.

` boolean`

` isExtensionProcessed()`
            

` void`

` processExtends(ModuleConfig moduleConfig)`
           Inherit configuration information from the ActionConfig that this instance is extending.

` void`

` removeExceptionConfig(ExceptionConfig config)`
            Remove the specified exception configuration instance.

` void`

` removeForwardConfig(ForwardConfig config)`
            Remove the specified forward configuration instance.

` void`

` setActionId(String actionId)`
           The internal name of this action mapping.

` void`

` setAttribute(String attribute)`
            Set the request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

` void`

` setCancellable(boolean cancellable)`
           Mutator for for cancellable property

` void`

` setCatalog(String catalog)`
            Set the name of a `commons-chain` catalog in which a specified command should be sought.

` void`

` setCommand(String command)`
            Set the name of a `commons-chain` command which should be executed as part of the processing of this action.

` void`

` setExtends(String inherit)`
           Set the path of the ActionConfig that this object should inherit properties from.

` void`

` setForward(String forward)`
            Set the context-relative path of the web application resource that will process this request.

` void`

` setInclude(String include)`
            Set context-relative path of the web application resource that will process this request.

` void`

` setInput(String input)`
            Set the context-relative path of the input form to which control should be returned if a validation error is encountered.

` void`

` setModuleConfig(ModuleConfig moduleConfig)`
            The module configuration with which we are associated.

` void`

` setMultipartClass(String multipartClass)`
            Set the fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

` void`

` setName(String name)`
            

` void`

` setParameter(String parameter)`
            General purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action.

` void`

` setPath(String path)`
            Set context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

` void`

` setPrefix(String prefix)`
            

` void`

` setRoles(String roles)`
            

` void`

` setScope(String scope)`
            

` void`

` setSuffix(String suffix)`
            

` void`

` setType(String type)`
            

` void`

` setUnknown(boolean unknown)`
            

` void`

` setValidate(boolean validate)`
            

` String`

` toString()`
            Return a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                            |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="exceptions"></span>

### exceptions

    protected HashMap exceptions

The set of exception handling configurations for this action, if any, keyed by the `type` property.

------------------------------------------------------------------------

<span id="forwards"></span>

### forwards

    protected HashMap forwards

The set of local forward configurations for this action, if any, keyed by the `name` property.

------------------------------------------------------------------------

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

The module configuration with which we are associated.

------------------------------------------------------------------------

<span id="attribute"></span>

### attribute

    protected String attribute

The request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

------------------------------------------------------------------------

<span id="actionId"></span>

### actionId

    protected String actionId

The internal identification of this action mapping. Identifications are not inheritable and must be unique within a module.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

<span id="inherit"></span>

### inherit

    protected String inherit

The path of the ActionConfig that this object should inherit properties from.

------------------------------------------------------------------------

<span id="cancellable"></span>

### cancellable

    protected boolean cancellable

Can this Action be cancelled? [false]

By default, when an Action is cancelled, validation is bypassed and the Action should not execute the business operation. If a request tries to cancel an Action when cancellable is not set, a "InvalidCancelException" is thrown.

------------------------------------------------------------------------

<span id="extensionProcessed"></span>

### extensionProcessed

    protected boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

<span id="forward"></span>

### forward

    protected String forward

Context-relative path of the web application resource that will process this request via RequestDispatcher.forward(), instead of instantiating and calling the `Action` class specified by "type". Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

<span id="include"></span>

### include

    protected String include

Context-relative path of the web application resource that will process this request via RequestDispatcher.include(), instead of instantiating and calling the `Action` class specified by "type". Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

<span id="input"></span>

### input

    protected String input

Context-relative path of the input form to which control should be returned if a validation error is encountered. Required if "name" is specified and the input bean returns validation errors.

------------------------------------------------------------------------

<span id="multipartClass"></span>

### multipartClass

    protected String multipartClass

Fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

Name of the form bean, if any, associated with this Action.

------------------------------------------------------------------------

<span id="parameter"></span>

### parameter

    protected String parameter

General purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action. Struts does not itself use this value in any way.

------------------------------------------------------------------------

<span id="path"></span>

### path

    protected String path

Context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

------------------------------------------------------------------------

<span id="prefix"></span>

### prefix

    protected String prefix

Prefix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

<span id="roles"></span>

### roles

    protected String roles

Comma-delimited list of security role names allowed to request this Action.

------------------------------------------------------------------------

<span id="roleNames"></span>

### roleNames

    protected String[] roleNames

The set of security role names used to authorize access to this Action, as an array for faster access.

------------------------------------------------------------------------

<span id="scope"></span>

### scope

    protected String scope

Identifier of the scope ("request" or "session") within which our form bean is accessed, if any.

------------------------------------------------------------------------

<span id="suffix"></span>

### suffix

    protected String suffix

Suffix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

<span id="type"></span>

### type

    protected String type

Fully qualified Java class name of the `Action` class to be used to process requests for this mapping if the `forward` and `include` properties are not set. Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

<span id="unknown"></span>

### unknown

    protected boolean unknown

Indicates Action be configured as the default one for this module, when true.

------------------------------------------------------------------------

<span id="validate"></span>

### validate

    protected boolean validate

Should the `validate()` method of the form bean associated with this action be called?

------------------------------------------------------------------------

<span id="command"></span>

### command

    protected String command

The name of a `commons-chain` command which should be executed as part of the processing of this action.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

<span id="catalog"></span>

### catalog

    protected String catalog

The name of a `commons-chain` catalog in which `command` should be sought. If a `command` is defined and this property is undefined, the "default" catalog will be used. This is likely to be infrequently used after a future release of `commons-chain` supports a one-string expression of a catalog/chain combination.

**Since:**  
Struts 1.3.0

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionConfig

    public ActionConfig()

<span id="method_detail"></span>

**Method Detail**

### getActionId

    public String getActionId()

The internal name of this action mapping. If an action has a name, it may be used as a shortcut in a URI. For example, an action with an identification of "editPerson" may be internally forwarded as "editPerson?id=1" which will then resolve to the real URI path at execution time.

**Returns:**  
the actionId

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### setActionId

    public void setActionId(String actionId)

The internal name of this action mapping. The name is not inheritable, may not contain a forward slash, and must be unique within a module.

**Parameters:**  
`actionId` - the action identifier

**Throws:**  
`IllegalStateException` - if the configuration is frozen

`IllegalArgumentException` - if the identifier contains a forward slash

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig()

The module configuration with which we are associated.

------------------------------------------------------------------------

### setModuleConfig

    public void setModuleConfig(ModuleConfig moduleConfig)

The module configuration with which we are associated.

------------------------------------------------------------------------

### getAttribute

    public String getAttribute()

Returns the request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

**Returns:**  
attribute name under which our form bean is accessed.

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String attribute)

Set the request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

**Parameters:**  
`attribute` - the request-scope or session-scope attribute name under which our form bean is access.

------------------------------------------------------------------------

### getCancellable

    public boolean getCancellable()

Accessor for cancellable property

**Returns:**  
True if Action can be cancelled

------------------------------------------------------------------------

### setCancellable

    public void setCancellable(boolean cancellable)

Mutator for for cancellable property

**Parameters:**  
`cancellable` -

------------------------------------------------------------------------

### getExtends

    public String getExtends()

Returns the path of the ActionConfig that this object should inherit properties from.

**Returns:**  
the path of the ActionConfig that this object should inherit properties from.

------------------------------------------------------------------------

### setExtends

    public void setExtends(String inherit)

Set the path of the ActionConfig that this object should inherit properties from.

**Parameters:**  
`inherit` - the path of the ActionConfig that this object should inherit properties from.

------------------------------------------------------------------------

### isExtensionProcessed

    public boolean isExtensionProcessed()

------------------------------------------------------------------------

### getForward

    public String getForward()

Returns context-relative path of the web application resource that will process this request.

**Returns:**  
context-relative path of the web application resource that will process this request.

------------------------------------------------------------------------

### setForward

    public void setForward(String forward)

Set the context-relative path of the web application resource that will process this request. Exactly one of `forward`, `include`, or `type` must be specified.

**Parameters:**  
`forward` - context-relative path of the web application resource that will process this request.

------------------------------------------------------------------------

### getInclude

    public String getInclude()

Context-relative path of the web application resource that will process this request.

**Returns:**  
Context-relative path of the web application resource that will process this request.

------------------------------------------------------------------------

### setInclude

    public void setInclude(String include)

Set context-relative path of the web application resource that will process this request. Exactly one of `forward`, `include`, or `type` must be specified.

**Parameters:**  
`include` - context-relative path of the web application resource that will process this request.

------------------------------------------------------------------------

### getInput

    public String getInput()

Get the context-relative path of the input form to which control should be returned if a validation error is encountered.

**Returns:**  
context-relative path of the input form to which control should be returned if a validation error is encountered.

------------------------------------------------------------------------

### setInput

    public void setInput(String input)

Set the context-relative path of the input form to which control should be returned if a validation error is encountered. Required if "name" is specified and the input bean returns validation errors.

**Parameters:**  
`input` - context-relative path of the input form to which control should be returned if a validation error is encountered.

------------------------------------------------------------------------

### getMultipartClass

    public String getMultipartClass()

Return the fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

------------------------------------------------------------------------

### setMultipartClass

    public void setMultipartClass(String multipartClass)

Set the fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

**Parameters:**  
`multipartClass` - fully qualified class name of the `MultipartRequestHandler` implementation class.

------------------------------------------------------------------------

### getName

    public String getName()

Return name of the form bean, if any, associated with this Action.

------------------------------------------------------------------------

### setName

    public void setName(String name)

**Parameters:**  
`name` - name of the form bean associated with this Action.

------------------------------------------------------------------------

### getParameter

    public String getParameter()

Return general purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action. Struts does not itself use this value in any way.

------------------------------------------------------------------------

### setParameter

    public void setParameter(String parameter)

General purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action. Struts does not itself use this value in any way.

**Parameters:**  
`parameter` - General purpose configuration parameter.

------------------------------------------------------------------------

### getPath

    public String getPath()

Return context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

------------------------------------------------------------------------

### setPath

    public void setPath(String path)

Set context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

**Parameters:**  
`path` - context-relative path of the submitted request.

------------------------------------------------------------------------

### getPrefix

    public String getPrefix()

Retruns prefix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### setPrefix

    public void setPrefix(String prefix)

**Parameters:**  
`prefix` - Prefix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### getRoles

    public String getRoles()

------------------------------------------------------------------------

### setRoles

    public void setRoles(String roles)

------------------------------------------------------------------------

### getRoleNames

    public String[] getRoleNames()

Get array of security role names used to authorize access to this Action.

------------------------------------------------------------------------

### getScope

    public String getScope()

Get the scope ("request" or "session") within which our form bean is accessed, if any.

------------------------------------------------------------------------

### setScope

    public void setScope(String scope)

**Parameters:**  
`scope` - scope ("request" or "session") within which our form bean is accessed, if any.

------------------------------------------------------------------------

### getSuffix

    public String getSuffix()

Return suffix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### setSuffix

    public void setSuffix(String suffix)

**Parameters:**  
`suffix` - Suffix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### getUnknown

    public boolean getUnknown()

Determine whether Action is configured as the default one for this module.

------------------------------------------------------------------------

### setUnknown

    public void setUnknown(boolean unknown)

**Parameters:**  
`unknown` - Indicates Action is configured as the default one for this module, when true.

------------------------------------------------------------------------

### getValidate

    public boolean getValidate()

------------------------------------------------------------------------

### setValidate

    public void setValidate(boolean validate)

------------------------------------------------------------------------

### getCommand

    public String getCommand()

Get the name of a `commons-chain` command which should be executed as part of the processing of this action.

**Returns:**  
name of a `commons-chain` command which should be executed as part of the processing of this action.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

### getCatalog

    public String getCatalog()

Get the name of a `commons-chain` catalog in which a specified command should be sought. This is likely to be infrequently used after a future release of `commons-chain` supports a one-string expression of a catalog/chain combination.

**Returns:**  
name of a `commons-chain` catalog in which a specified command should be sought.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

### setCommand

    public void setCommand(String command)

Set the name of a `commons-chain` command which should be executed as part of the processing of this action.

**Parameters:**  
`command` - name of a `commons-chain` command which should be executed as part of the processing of this action.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

### setCatalog

    public void setCatalog(String catalog)

Set the name of a `commons-chain` catalog in which a specified command should be sought. This is likely to be infrequently used after a future release of `commons-chain` supports a one-string expression of a catalog/chain combination.

**Parameters:**  
`catalog` - name of a `commons-chain` catalog in which a specified command should be sought.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

### checkCircularInheritance

    protected boolean checkCircularInheritance(ModuleConfig moduleConfig)

Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

**Parameters:**  
`moduleConfig` - The configuration for the module being configured.

**Returns:**  
true if circular inheritance was detected.

------------------------------------------------------------------------

### inheritExceptionHandlers

    protected void inheritExceptionHandlers(ActionConfig baseConfig)
                                     throws ClassNotFoundException,
                                            IllegalAccessException,
                                            InstantiationException,
                                            InvocationTargetException

Compare the exception handlers of this action with that of the given and copy those that are not present.

**Parameters:**  
`baseConfig` - The action config to copy handlers from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(ActionConfig)`](../../../../org/apache/struts/config/ActionConfig.html.md#inheritFrom(org.apache.struts.config.ActionConfig))

------------------------------------------------------------------------

### inheritForwards

    protected void inheritForwards(ActionConfig baseConfig)
                            throws ClassNotFoundException,
                                   IllegalAccessException,
                                   InstantiationException,
                                   InvocationTargetException

Compare the forwards of this action with that of the given and copy those that are not present.

**Parameters:**  
`baseConfig` - The action config to copy forwards from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(ActionConfig)`](../../../../org/apache/struts/config/ActionConfig.html.md#inheritFrom(org.apache.struts.config.ActionConfig))

------------------------------------------------------------------------

### addExceptionConfig

    public void addExceptionConfig(ExceptionConfig config)

Add a new `ExceptionConfig` instance to the set associated with this action.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### addForwardConfig

    public void addForwardConfig(ForwardConfig config)

Add a new `ForwardConfig` instance to the set of global forwards associated with this action.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### findExceptionConfig

    public ExceptionConfig findExceptionConfig(String type)

Return the exception configuration for the specified type, if any; otherwise return `null`.

**Parameters:**  
`type` - Exception class name to find a configuration for

------------------------------------------------------------------------

### findExceptionConfigs

    public ExceptionConfig[] findExceptionConfigs()

Return the exception configurations for this action. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### findException

    public ExceptionConfig findException(Class type)

Find and return the `ExceptionConfig` instance defining how `Exceptions` of the specified type should be handled. This is performed by checking local and then global configurations for the specified exception's class, and then looking up the superclass chain (again checking local and then global configurations). If no handler configuration can be found, return `null`.

Introduced in `ActionMapping` in Struts 1.1, but pushed up to `ActionConfig` in Struts 1.2.0.

**Parameters:**  
`type` - Exception class for which to find a handler

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### findForwardConfig

    public ForwardConfig findForwardConfig(String name)

Return the forward configuration for the specified key, if any; otherwise return `null`.

**Parameters:**  
`name` - Name of the forward configuration to return

------------------------------------------------------------------------

### findForwardConfigs

    public ForwardConfig[] findForwardConfigs()

Return all forward configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### freeze

    public void freeze()

Freeze the configuration of this action.

**Overrides:**  
`freeze` in class `BaseConfig`

------------------------------------------------------------------------

### inheritFrom

    public void inheritFrom(ActionConfig config)
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
[`processExtends(ModuleConfig)`](../../../../org/apache/struts/config/ActionConfig.html.md#processExtends(org.apache.struts.config.ModuleConfig))

------------------------------------------------------------------------

### processExtends

    public void processExtends(ModuleConfig moduleConfig)
                        throws ClassNotFoundException,
                               IllegalAccessException,
                               InstantiationException,
                               InvocationTargetException

Inherit configuration information from the ActionConfig that this instance is extending. This method verifies that any action config object that it inherits from has also had its processExtends() method called.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this bean is from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(ActionConfig)`](../../../../org/apache/struts/config/ActionConfig.html.md#inheritFrom(org.apache.struts.config.ActionConfig))

------------------------------------------------------------------------

### removeExceptionConfig

    public void removeExceptionConfig(ExceptionConfig config)

Remove the specified exception configuration instance.

**Parameters:**  
`config` - ExceptionConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

------------------------------------------------------------------------

### removeForwardConfig

    public void removeForwardConfig(ForwardConfig config)

Remove the specified forward configuration instance.

**Parameters:**  
`config` - ForwardConfig instance to be removed

**Throws:**  
`IllegalStateException` - if this module configuration has been frozen

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
<td align="left"><a href="class-use/ActionConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/config/ActionConfigMatcher.html.md" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ActionConfig.html"><strong>FRAMES</strong></a>    <a href="ActionConfig.html"><strong>NO FRAMES</strong></a>    
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
