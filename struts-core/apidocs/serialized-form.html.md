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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts**

<span id="org.apache.struts.Globals"></span>

**Class [org.apache.struts.Globals](org/apache/struts/Globals.html.md "class in org.apache.struts") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.action**

<span id="org.apache.struts.action.ActionErrors"></span>

**Class [org.apache.struts.action.ActionErrors](org/apache/struts/action/ActionErrors.html.md "class in org.apache.struts.action") extends [ActionMessages](org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.ActionForm"></span>

**Class [org.apache.struts.action.ActionForm](org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.ActionFormBean"></span>

**Class [org.apache.struts.action.ActionFormBean](org/apache/struts/action/ActionFormBean.html.md "class in org.apache.struts.action") extends [FormBeanConfig](org/apache/struts/config/FormBeanConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionForward"></span>

**Class [org.apache.struts.action.ActionForward](org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") extends [ForwardConfig](org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionMapping"></span>

**Class [org.apache.struts.action.ActionMapping](org/apache/struts/action/ActionMapping.html.md "class in org.apache.struts.action") extends [ActionConfig](org/apache/struts/config/ActionConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionMessage"></span>

**Class [org.apache.struts.action.ActionMessage](org/apache/struts/action/ActionMessage.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### key

    String key

The message key for this message.

------------------------------------------------------------------------

### values

    Object[] values

The replacement values for this mesasge.

------------------------------------------------------------------------

### resource

    boolean resource

Indicates whether the key is taken to be as a bundle key [true] or literal value [false].

<span id="org.apache.struts.action.ActionMessages"></span>

**Class [org.apache.struts.action.ActionMessages](org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessed

    boolean accessed

Have the messages been retrieved from this object?

The controller uses this property to determine if session-scoped messages can be removed.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### messages

    HashMap<K,V> messages

The accumulated set of `ActionMessage` objects (represented as an ArrayList) for each property, keyed by property name.

------------------------------------------------------------------------

### iCount

    int iCount

The current number of the property/key being added. This is used to maintain the order messages are added.

<span id="org.apache.struts.action.ActionMessages.ActionMessageItem"></span>

**Class [org.apache.struts.action.ActionMessages.ActionMessageItem](org/apache/struts/action/ActionMessages.ActionMessageItem.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### list

    List<E> list

The list of `ActionMessage`s.

------------------------------------------------------------------------

### iOrder

    int iOrder

The position in the list of messages.

------------------------------------------------------------------------

### property

    String property

The property associated with `ActionMessage`.

<span id="org.apache.struts.action.ActionRedirect"></span>

**Class [org.apache.struts.action.ActionRedirect](org/apache/struts/action/ActionRedirect.html.md "class in org.apache.struts.action") extends [ActionForward](org/apache/struts/action/ActionForward.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### parameterValues

    Map<K,V> parameterValues

Holds the redirect parameters. Each entry is either a String or a String[] depending on whether it has one or more entries.

------------------------------------------------------------------------

### anchorValue

    String anchorValue

Holds the anchor value.

<span id="org.apache.struts.action.ActionServlet"></span>

**Class [org.apache.struts.action.ActionServlet](org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") extends [HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html?is-external=true "class or interface in javax.servlet.http") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    String config

Comma-separated list of context-relative path(s) to our configuration resource(s) for the default module.

------------------------------------------------------------------------

### chainConfig

    String chainConfig

Comma-separated list of context or classloader-relative path(s) that contain the configuration for the default commons-chain catalog(s).

------------------------------------------------------------------------

### configDigester

    org.apache.commons.digester.Digester configDigester

The Digester used to produce ModuleConfig objects from a Struts configuration file.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### convertNull

    boolean convertNull

The flag to request backwards-compatible conversions for form bean properties of the Java wrapper class types.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### internal

    MessageResources internal

The resources object for our internal resources.

------------------------------------------------------------------------

### internalName

    String internalName

The Java base name of our internal resources.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### registrations

    String[] registrations

The set of public identifiers, and corresponding resource names, for the versions of the configuration file DTDs that we know about. There **MUST** be an even number of Strings in this list!

------------------------------------------------------------------------

### servletMapping

    String servletMapping

The URL pattern to which we are mapped in our web application deployment descriptor.

------------------------------------------------------------------------

### servletName

    String servletName

The servlet name under which we are registered in our web application deployment descriptor.

<span id="org.apache.struts.action.ActionServletWrapper"></span>

**Class [org.apache.struts.action.ActionServletWrapper](org/apache/struts/action/ActionServletWrapper.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.DynaActionForm"></span>

**Class [org.apache.struts.action.DynaActionForm](org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action") extends [ActionForm](org/apache/struts/action/ActionForm.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### dynaClass

    DynaActionFormClass dynaClass

The `DynaActionFormClass` with which we are associated.

------------------------------------------------------------------------

### dynaValues

    HashMap<K,V> dynaValues

The set of property values for this `DynaActionForm`, keyed by property name.

<span id="org.apache.struts.action.DynaActionFormClass"></span>

**Class [org.apache.struts.action.DynaActionFormClass](org/apache/struts/action/DynaActionFormClass.html.md "class in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    FormBeanConfig config

The form bean configuration information for this class.

------------------------------------------------------------------------

### name

    String name

The "dynamic class name" for this `DynaClass`.

------------------------------------------------------------------------

### properties

    DynaProperty[] properties

The set of dynamic properties that are part of this DynaClass.

------------------------------------------------------------------------

### propertiesMap

    HashMap<K,V> propertiesMap

The set of dynamic properties that are part of this `DynaClass`, keyed by the property name. Individual descriptor instances will be the same instances as those in the `properties` list.

<span id="org.apache.struts.action.ForwardingActionForward"></span>

**Class [org.apache.struts.action.ForwardingActionForward](org/apache/struts/action/ForwardingActionForward.html.md "class in org.apache.struts.action") extends [ActionForward](org/apache/struts/action/ActionForward.html "class in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.InvalidCancelException"></span>

**Class [org.apache.struts.action.InvalidCancelException](org/apache/struts/action/InvalidCancelException.html.md "class in org.apache.struts.action") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.RedirectingActionForward"></span>

**Class [org.apache.struts.action.RedirectingActionForward](org/apache/struts/action/RedirectingActionForward.html.md "class in org.apache.struts.action") extends [ActionForward](org/apache/struts/action/ActionForward.html "class in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.RequestActionMapping"></span>

**Class [org.apache.struts.action.RequestActionMapping](org/apache/struts/action/RequestActionMapping.html.md "class in org.apache.struts.action") extends [ActionMapping](org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.SessionActionMapping"></span>

**Class [org.apache.struts.action.SessionActionMapping](org/apache/struts/action/SessionActionMapping.html.md "class in org.apache.struts.action") extends [ActionMapping](org/apache/struts/action/ActionMapping.html "class in org.apache.struts.action") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.chain.commands**

<span id="org.apache.struts.chain.commands.InvalidPathException"></span>

**Class [org.apache.struts.chain.commands.InvalidPathException](org/apache/struts/chain/commands/InvalidPathException.html.md "class in org.apache.struts.chain.commands") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### path

    String path

Field for Path property.

<span id="org.apache.struts.chain.commands.UnauthorizedActionException"></span>

**Class [org.apache.struts.chain.commands.UnauthorizedActionException](org/apache/struts/chain/commands/UnauthorizedActionException.html.md "class in org.apache.struts.chain.commands") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.config**

<span id="org.apache.struts.config.ActionConfig"></span>

**Class [org.apache.struts.config.ActionConfig](org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exceptions

    HashMap<K,V> exceptions

The set of exception handling configurations for this action, if any, keyed by the `type` property.

------------------------------------------------------------------------

### forwards

    HashMap<K,V> forwards

The set of local forward configurations for this action, if any, keyed by the `name` property.

------------------------------------------------------------------------

### moduleConfig

    ModuleConfig moduleConfig

The module configuration with which we are associated.

------------------------------------------------------------------------

### attribute

    String attribute

The request-scope or session-scope attribute name under which our form bean is accessed, if it is different from the form bean's specified `name`.

------------------------------------------------------------------------

### actionId

    String actionId

The internal identification of this action mapping. Identifications are not inheritable and must be unique within a module.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### inherit

    String inherit

The path of the ActionConfig that this object should inherit properties from.

------------------------------------------------------------------------

### cancellableSet

    boolean cancellableSet

Indicates whether the "cancellable " property has been set or not.

------------------------------------------------------------------------

### cancellable

    boolean cancellable

Can this Action be cancelled? [false]

By default, when an Action is cancelled, validation is bypassed and the Action should not execute the business operation. If a request tries to cancel an Action when cancellable is not set, a "InvalidCancelException" is thrown.

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

### forward

    String forward

Context-relative path of the web application resource that will process this request via RequestDispatcher.forward(), instead of instantiating and calling the `Action` class specified by "type". Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

### include

    String include

Context-relative path of the web application resource that will process this request via RequestDispatcher.include(), instead of instantiating and calling the `Action` class specified by "type". Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

### input

    String input

Context-relative path of the input form to which control should be returned if a validation error is encountered. Required if "name" is specified and the input bean returns validation errors.

------------------------------------------------------------------------

### multipartClass

    String multipartClass

Fully qualified Java class name of the `MultipartRequestHandler` implementation class used to process multi-part request data for this Action.

------------------------------------------------------------------------

### name

    String name

Name of the form bean, if any, associated with this Action.

------------------------------------------------------------------------

### parameter

    String parameter

General purpose configuration parameter that can be used to pass extra information to the Action instance selected by this Action. Struts does not itself use this value in any way.

------------------------------------------------------------------------

### path

    String path

Context-relative path of the submitted request, starting with a slash ("/") character, and omitting any filename extension if extension mapping is being used.

------------------------------------------------------------------------

### prefix

    String prefix

Prefix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### roles

    String roles

Comma-delimited list of security role names allowed to request this Action.

------------------------------------------------------------------------

### roleNames

    String[] roleNames

The set of security role names used to authorize access to this Action, as an array for faster access.

------------------------------------------------------------------------

### scope

    String scope

Identifier of the scope ("request" or "session") within which our form bean is accessed, if any.

------------------------------------------------------------------------

### suffix

    String suffix

Suffix used to match request parameter names to form bean property names, if any.

------------------------------------------------------------------------

### type

    String type

Fully qualified Java class name of the `Action` class to be used to process requests for this mapping if the `forward` and `include` properties are not set. Exactly one of `forward`, `include`, or `type` must be specified.

------------------------------------------------------------------------

### unknown

    boolean unknown

Indicates Action be configured as the default one for this module, when true.

------------------------------------------------------------------------

### validateSet

    boolean validateSet

Indicates whether the "validate" property has been set or not.

------------------------------------------------------------------------

### validate

    boolean validate

Should the `validate()` method of the form bean associated with this action be called?

------------------------------------------------------------------------

### command

    String command

The name of a `commons-chain` command which should be executed as part of the processing of this action.

**Since:**  
Struts 1.3.0

------------------------------------------------------------------------

### catalog

    String catalog

The name of a `commons-chain` catalog in which `command` should be sought. If a `command` is defined and this property is undefined, the "default" catalog will be used. This is likely to be infrequently used after a future release of `commons-chain` supports a one-string expression of a catalog/chain combination.

**Since:**  
Struts 1.3.0

<span id="org.apache.struts.config.ActionConfigMatcher"></span>

**Class [org.apache.struts.config.ActionConfigMatcher](org/apache/struts/config/ActionConfigMatcher.html.md "class in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### compiledPaths

    List<E> compiledPaths

The compiled paths and their associated ActionConfig's

<span id="org.apache.struts.config.BaseConfig"></span>

**Class [org.apache.struts.config.BaseConfig](org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### configured

    boolean configured

Indicates if configuration of this component been completed. TODO change protected to private and use methods provided by extenders?

------------------------------------------------------------------------

### properties

    Properties properties

A map of arbitrary properties configured for this component.

**Since:**  
Struts 1.3

<span id="org.apache.struts.config.ControllerConfig"></span>

**Class [org.apache.struts.config.ControllerConfig](org/apache/struts/config/ControllerConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bufferSize

    int bufferSize

The input buffer size for file uploads.

------------------------------------------------------------------------

### contentType

    String contentType

The content type and character encoding to be set on each response.

------------------------------------------------------------------------

### catalog

    String catalog

The chain catalog name for this module.

------------------------------------------------------------------------

### command

    String command

The chain command to execute for each request.

------------------------------------------------------------------------

### forwardPattern

    String forwardPattern

The replacement pattern used to determine a context-relative URL from a [`ForwardConfig`](org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") element. The pattern may consist of any combination of the following markers and characters:

-   `$M` - Replaced by the module prefix for the current module.
-   `$P` - Replaced by the `path` property of a [`ForwardConfig`](org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") instance.
-   `$$` - Renders a literal dollar sign ("$") character in the resulting URL.
-   A dollar sign followed by any other character is reserved for future use, and both characters are silently swallowed.
-   All other characters in the pattern are passed through unchanged.

If this property is set to `null`, a default pattern of `$M$P` is utilized, which is backwards compatible with the hard coded functionality in prior versions.

------------------------------------------------------------------------

### inputForward

    boolean inputForward

Should the `input` property of [`ActionConfig`](org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") instances associated with this module be treated as the name of a corresponding [`ForwardConfig`](org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config"). A `false` value treats them as a module-relative path (consistent with the hard coded behavior of earlier versions of Struts.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### locale

    boolean locale

Should we store a Locale object in the user's session if needed?

------------------------------------------------------------------------

### maxFileSize

    String maxFileSize

The maximum file size to process for file uploads.

------------------------------------------------------------------------

### memFileSize

    String memFileSize

The maximum file size to retain in memory.

------------------------------------------------------------------------

### multipartClass

    String multipartClass

The fully qualified Java class name of the MultipartRequestHandler class to be used.

------------------------------------------------------------------------

### nocache

    boolean nocache

Should we set no-cache HTTP headers on each response?

------------------------------------------------------------------------

### pagePattern

    String pagePattern

The replacement pattern used to determine a context-relative URL from the `page` attribute of Struts tags and configuration properties. The pattern may consist of any combination of the following markers and characters:

-   `$M` - Replaced by the module prefix for the current module.
-   `$P` - Replaced by the `page` attribute value being evaluated.
-   `$$` - Renders a literal dollar sign ("$") character in the resulting URL.
-   A dollar sign followed by any other character is reserved for future use, and both characters are silently swallowed.
-   All other characters in the pattern are passed through unchanged.

If this property is set to `null`, a default pattern of `$M$P` is utilized, which is backwards compatible with the hard coded functionality in prior versions.

------------------------------------------------------------------------

### processorClass

    String processorClass

The fully qualified class name of the RequestProcessor implementation class to be used for this module.

------------------------------------------------------------------------

### tempDir

    String tempDir

The temporary working directory to use for file uploads.

<span id="org.apache.struts.config.ExceptionConfig"></span>

**Class [org.apache.struts.config.ExceptionConfig](org/apache/struts/config/ExceptionConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute under which the message resources bundle to be used for this exception is located. If not set, the default message resources for the current module is assumed.

------------------------------------------------------------------------

### inherit

    String inherit

The type of the ExceptionConfig that this object should inherit properties from.

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

### handler

    String handler

The fully qualified Java class name of the exception handler class which should be instantiated to handle this exception.

------------------------------------------------------------------------

### key

    String key

The message resources key specifying the error message associated with this exception.

------------------------------------------------------------------------

### path

    String path

The module-relative path of the resource to forward to if this exception occurs during an `Action`.

------------------------------------------------------------------------

### scope

    String scope

The scope in which we should expose the ActionMessage for this exception handler.

------------------------------------------------------------------------

### type

    String type

The fully qualified Java class name of the exception that is to be handled by this handler.

<span id="org.apache.struts.config.FormBeanConfig"></span>

**Class [org.apache.struts.config.FormBeanConfig](org/apache/struts/config/FormBeanConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### formProperties

    HashMap<K,V> formProperties

The set of FormProperty elements defining dynamic form properties for this form bean, keyed by property name.

------------------------------------------------------------------------

### lock

    String lock

The lockable object we can synchronize on when creating DynaActionFormClass.

------------------------------------------------------------------------

### dynamic

    boolean dynamic

Is the form bean class an instance of DynaActionForm with dynamic properties?

------------------------------------------------------------------------

### inherit

    String inherit

The name of the FormBeanConfig that this config inherits configuration information from.

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

### name

    String name

The unique identifier of this form bean, which is used to reference this bean in `ActionMapping` instances as well as for the name of the request or session attribute under which the corresponding form bean instance is created or accessed.

------------------------------------------------------------------------

### type

    String type

The fully qualified Java class name of the implementation class to be used or generated.

------------------------------------------------------------------------

### restricted

    boolean restricted

Is this DynaClass currently restricted (for DynaBeans with a MutableDynaClass).

<span id="org.apache.struts.config.FormPropertyConfig"></span>

**Class [org.apache.struts.config.FormPropertyConfig](org/apache/struts/config/FormPropertyConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### initial

    String initial

String representation of the initial value for this property.

------------------------------------------------------------------------

### name

    String name

The JavaBean property name of the property described by this element.

------------------------------------------------------------------------

### reset

    String reset

The conditions under which the property described by this element should be reset to its `initial` value when the form's `reset` method is called.

This may be set to true (to always reset the property) or a comma-separated list of HTTP request methods.

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### size

    int size

The size of the array to be created if this property is an array type and there is no specified `initial` value. This value must be non-negative.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### type

    String type

The fully qualified Java class name of the implementation class of this bean property, optionally followed by `[]` to indicate that the property is indexed.

<span id="org.apache.struts.config.ForwardConfig"></span>

**Class [org.apache.struts.config.ForwardConfig](org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### inherit

    String inherit

The name of the ForwardConfig that this object should inherit properties from.

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

### name

    String name

The unique identifier of this forward, which is used to reference it in `Action` classes.

------------------------------------------------------------------------

### path

    String path

The URL to which this `ForwardConfig` entry points, which must start with a slash ("/") character. It is interpreted according to the following rules:

-   If `contextRelative` property is `true`, the path is considered to be context-relative within the current web application (even if we are in a named module). It will be prefixed by the context path to create a server-relative URL.
-   If the `contextRelative` property is false, the path is considered to be the module-relative portion of the URL. It will be used as the replacement for the `$P` marker in the `forwardPattern` property defined on the [`ControllerConfig`](org/apache/struts/config/ControllerConfig.html.md "class in org.apache.struts.config") element for our current module. For the default `forwardPattern` value of `$C$M$P`, the resulting server-relative URL will be the concatenation of the context path, the module prefix, and the `path` from this `ForwardConfig`.

------------------------------------------------------------------------

### module

    String module

The prefix of the module to which this `ForwardConfig` entry points, which must start with a slash ("/") character.

Usage note: If a forward config is used in a hyperlink, and a module is specified, the path must lead to another action and not directly to a page. This is in keeping with rule that in a modular application all links must be to an action rather than a page.

------------------------------------------------------------------------

### redirect

    boolean redirect

Should a redirect be used to transfer control to the specified path?

------------------------------------------------------------------------

### command

    String command

The name of a `commons-chain` command which should be looked up and executed before Struts dispatches control to the view represented by this config.

------------------------------------------------------------------------

### catalog

    String catalog

The name of a `commons-chain` catalog in which `command` should be looked up. If this value is undefined, then the command will be looked up in the "default" catalog. This value has no meaning except in the context of the `command` property.

<span id="org.apache.struts.config.MessageResourcesConfig"></span>

**Class [org.apache.struts.config.MessageResourcesConfig](org/apache/struts/config/MessageResourcesConfig.html.md "class in org.apache.struts.config") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    String factory

Fully qualified Java class name of the MessageResourcesFactory class we should use.

------------------------------------------------------------------------

### key

    String key

The servlet context attributes key under which this MessageResources instance is stored.

------------------------------------------------------------------------

### nullValue

    boolean nullValue

Should we return `null` for unknown message keys?

------------------------------------------------------------------------

### escape

    boolean escape

Indicates whether 'escape processing' should be performed on the error message string.

------------------------------------------------------------------------

### parameter

    String parameter

Parameter that is passed to the `createResources()` method of our MessageResourcesFactory implementation.

<span id="org.apache.struts.config.PlugInConfig"></span>

**Class [org.apache.struts.config.PlugInConfig](org/apache/struts/config/PlugInConfig.html.md "class in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### configured

    boolean configured

Has this component been completely configured?

------------------------------------------------------------------------

### properties

    Map<K,V> properties

A `Map` of the name-value pairs that will be used to configure the property values of a `PlugIn` instance.

------------------------------------------------------------------------

### className

    String className

The fully qualified Java class name of the `PlugIn` implementation class being configured.

------------------------------------------------------------------------

**Package** **org.apache.struts.config.impl**

<span id="org.apache.struts.config.impl.DefaultModuleConfigFactory"></span>

**Class [org.apache.struts.config.impl.DefaultModuleConfigFactory](org/apache/struts/config/impl/DefaultModuleConfigFactory.html.md "class in org.apache.struts.config.impl") extends [ModuleConfigFactory](org/apache/struts/config/ModuleConfigFactory.html "class in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.config.impl.ModuleConfigImpl"></span>

**Class [org.apache.struts.config.impl.ModuleConfigImpl](org/apache/struts/config/impl/ModuleConfigImpl.html.md "class in org.apache.struts.config.impl") extends [BaseConfig](org/apache/struts/config/BaseConfig.html "class in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionConfigs

    HashMap<K,V> actionConfigs

The set of action configurations for this module, if any, keyed by the `path` property.

------------------------------------------------------------------------

### actionConfigIds

    HashMap<K,V> actionConfigIds

The set of action configuration for this module, if any, keyed by the `actionId` property.

------------------------------------------------------------------------

### actionConfigList

    List<E> actionConfigList

The set of action configurations for this module, if any, listed in the order in which they are added.

------------------------------------------------------------------------

### exceptions

    HashMap<K,V> exceptions

The set of exception handling configurations for this module, if any, keyed by the `type` property.

------------------------------------------------------------------------

### formBeans

    HashMap<K,V> formBeans

The set of form bean configurations for this module, if any, keyed by the `name` property.

------------------------------------------------------------------------

### forwards

    HashMap<K,V> forwards

The set of global forward configurations for this module, if any, keyed by the `name` property.

------------------------------------------------------------------------

### messageResources

    HashMap<K,V> messageResources

The set of message resources configurations for this module, if any, keyed by the `key` property.

------------------------------------------------------------------------

### plugIns

    ArrayList<E> plugIns

The set of configured plug-in Actions for this module, if any, in the order they were declared and configured.

------------------------------------------------------------------------

### controllerConfig

    ControllerConfig controllerConfig

The controller configuration object for this module.

------------------------------------------------------------------------

### prefix

    String prefix

The prefix of the context-relative portion of the request URI, used to select this configuration versus others supported by the controller servlet. A configuration with a prefix of a zero-length String is the default configuration for this web module.

------------------------------------------------------------------------

### actionFormBeanClass

    String actionFormBeanClass

The default class name to be used when creating action form bean instances.

------------------------------------------------------------------------

### actionMappingClass

    String actionMappingClass

The default class name to be used when creating action mapping instances.

------------------------------------------------------------------------

### actionForwardClass

    String actionForwardClass

The default class name to be used when creating action forward instances.

------------------------------------------------------------------------

### matcher

    ActionConfigMatcher matcher

Matches action config paths against compiled wildcard patterns

------------------------------------------------------------------------

**Package** **org.apache.struts.mock**

<span id="org.apache.struts.mock.MockActionServlet"></span>

**Class [org.apache.struts.mock.MockActionServlet](org/apache/struts/mock/MockActionServlet.html.md "class in org.apache.struts.mock") extends [ActionServlet](org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### servletContext

    ServletContext servletContext

------------------------------------------------------------------------

### servletConfig

    ServletConfig servletConfig

<span id="org.apache.struts.mock.MockFormBean"></span>

**Class [org.apache.struts.mock.MockFormBean](org/apache/struts/mock/MockFormBean.html.md "class in org.apache.struts.mock") extends [ActionForm](org/apache/struts/action/ActionForm.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### throwException

    boolean throwException

------------------------------------------------------------------------

### returnNulls

    boolean returnNulls

------------------------------------------------------------------------

### defaultValue

    String defaultValue

------------------------------------------------------------------------

### defaultDouble

    Double defaultDouble

------------------------------------------------------------------------

### arrayCount

    int arrayCount

------------------------------------------------------------------------

### booleanProperty

    boolean booleanProperty

------------------------------------------------------------------------

### stringProperty

    String stringProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.util**

<span id="org.apache.struts.util.ImageButtonBean"></span>

**Class [org.apache.struts.util.ImageButtonBean](org/apache/struts/util/ImageButtonBean.html.md "class in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### x

    String x

The X coordinate of the button press.

------------------------------------------------------------------------

### y

    String y

The Y coordinate of the button press.

<span id="org.apache.struts.util.LabelValueBean"></span>

**Class [org.apache.struts.util.LabelValueBean](org/apache/struts/util/LabelValueBean.html.md "class in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### label

    String label

The property which supplies the option label visible to the end user.

------------------------------------------------------------------------

### value

    String value

The property which supplies the value returned to the server.

<span id="org.apache.struts.util.MessageResources"></span>

**Class [org.apache.struts.util.MessageResources](org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    String config

The configuration parameter used to initialize this MessageResources.

------------------------------------------------------------------------

### defaultLocale

    Locale defaultLocale

The default Locale for our environment.

------------------------------------------------------------------------

### factory

    MessageResourcesFactory factory

The `MessageResourcesFactory` that created this instance.

------------------------------------------------------------------------

### formats

    HashMap<K,V> formats

The set of previously created MessageFormat objects, keyed by the key computed in `messageKey()`.

------------------------------------------------------------------------

### returnNull

    boolean returnNull

Indicate is a `null` is returned instead of an error message string when an unknown Locale or key is requested.

------------------------------------------------------------------------

### escape

    boolean escape

Indicates whether 'escape processing' should be performed on the error message string.

<span id="org.apache.struts.util.MessageResourcesFactory"></span>

**Class [org.apache.struts.util.MessageResourcesFactory](org/apache/struts/util/MessageResourcesFactory.html.md "class in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    MessageResourcesConfig config

Configuration information for Message Resources.

------------------------------------------------------------------------

### returnNull

    boolean returnNull

The "return null" property value to which newly created MessageResourcess should be initialized.

<span id="org.apache.struts.util.ModuleException"></span>

**Class [org.apache.struts.util.ModuleException](org/apache/struts/util/ModuleException.html.md "class in org.apache.struts.util") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

------------------------------------------------------------------------

### message

    ActionMessage message

The ActionMessage associated with this exception.

**Since:**  
Struts 1.2

<span id="org.apache.struts.util.PropertyMessageResources"></span>

**Class [org.apache.struts.util.PropertyMessageResources](org/apache/struts/util/PropertyMessageResources.html.md "class in org.apache.struts.util") extends [MessageResources](org/apache/struts/util/MessageResources.html "class in org.apache.struts.util") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### locales

    HashMap<K,V> locales

The set of locale keys for which we have already loaded messages, keyed by the value calculated in `localeKey()`.

------------------------------------------------------------------------

### messages

    HashMap<K,V> messages

The cache of messages we have accumulated over time, keyed by the value calculated in `messageKey()`.

------------------------------------------------------------------------

### mode

    int mode

Compatibility mode that PropertyMessageResources is operating in.

<span id="org.apache.struts.util.PropertyMessageResourcesFactory"></span>

**Class [org.apache.struts.util.PropertyMessageResourcesFactory](org/apache/struts/util/PropertyMessageResourcesFactory.html.md "class in org.apache.struts.util") extends [MessageResourcesFactory](org/apache/struts/util/MessageResourcesFactory.html "class in org.apache.struts.util") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.validator**

<span id="org.apache.struts.validator.BeanValidatorForm"></span>

**Class [org.apache.struts.validator.BeanValidatorForm](org/apache/struts/validator/BeanValidatorForm.html.md "class in org.apache.struts.validator") extends [ValidatorForm](org/apache/struts/validator/ValidatorForm.html "class in org.apache.struts.validator") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### dynaBean

    DynaBean dynaBean

The `DynaBean` that this ActionForm is backed by.

------------------------------------------------------------------------

### pathValidation

    boolean pathValidation

Indicates whether the ActionMapping's path should be used for the validation key.

------------------------------------------------------------------------

### strutsConfigFormName

    String strutsConfigFormName

The name used to identify the ActionForm in the struts-config.xml

<span id="org.apache.struts.validator.DynaValidatorForm"></span>

**Class [org.apache.struts.validator.DynaValidatorForm](org/apache/struts/validator/DynaValidatorForm.html.md "class in org.apache.struts.validator") extends [DynaActionForm](org/apache/struts/action/DynaActionForm.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### validatorResults

    ValidatorResults validatorResults

The results returned from the validation performed by the `Validator`.

------------------------------------------------------------------------

### page

    int page

Used to indicate the current page of a multi-page form.

<span id="org.apache.struts.validator.FieldChecks"></span>

**Class [org.apache.struts.validator.FieldChecks](org/apache/struts/validator/FieldChecks.html.md "class in org.apache.struts.validator") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.validator.LazyValidatorForm"></span>

**Class [org.apache.struts.validator.LazyValidatorForm](org/apache/struts/validator/LazyValidatorForm.html.md "class in org.apache.struts.validator") extends [BeanValidatorForm](org/apache/struts/validator/BeanValidatorForm.html "class in org.apache.struts.validator") implements Serializable**

<span id="org.apache.struts.validator.ValidatorForm"></span>

**Class [org.apache.struts.validator.ValidatorForm](org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator") extends [ActionForm](org/apache/struts/action/ActionForm.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### validatorResults

    ValidatorResults validatorResults

The results returned from the validation performed by the `Validator`.

------------------------------------------------------------------------

### page

    int page

Used to indicate the current page of a multi-page form.

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
