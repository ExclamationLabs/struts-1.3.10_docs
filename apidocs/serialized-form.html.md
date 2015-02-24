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

**Package** **org.apache.struts.apps.mailreader.dao**

<span id="org.apache.struts.apps.mailreader.dao.ExpiredPasswordException"></span>

**Class [org.apache.struts.apps.mailreader.dao.ExpiredPasswordException](org/apache/struts/apps/mailreader/dao/ExpiredPasswordException.html.md "class in org.apache.struts.apps.mailreader.dao") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

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

**Package** **org.apache.struts.faces.taglib**

<span id="org.apache.struts.faces.taglib.JavascriptValidatorTag"></span>

**Class [org.apache.struts.faces.taglib.JavascriptValidatorTag](org/apache/struts/faces/taglib/JavascriptValidatorTag.html.md "class in org.apache.struts.faces.taglib") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### formName

    String formName

The name of the form that corresponds with the action name in struts-config.xml. Specifying a form name places a \<script\> \</script\> around the javascript.

------------------------------------------------------------------------

### page

    int page

The current page number of a multi-part form. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### methodName

    String methodName

This will be used as is for the JavaScript validation method name if it has a value. This is the method name of the main JavaScript method that the form calls to perform validations.

------------------------------------------------------------------------

### staticJavascript

    String staticJavascript

The static JavaScript methods will only be printed if this is set to "true".

------------------------------------------------------------------------

### dynamicJavascript

    String dynamicJavascript

The dynamic JavaScript objects will only be generated if this is set to "true".

------------------------------------------------------------------------

### src

    String src

The src attribute for.html.md script element (used to include an external script resource). The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

###.html.mdComment

    String.html.mdComment

The JavaScript methods will enclosed with.html.md comments if this is set to "true".

------------------------------------------------------------------------

### cdata

    String cdata

Hide JavaScript methods in a CDATA section for XHTML when "true".

------------------------------------------------------------------------

###.html.mdBeginComment

    String.html.mdBeginComment

------------------------------------------------------------------------

###.html.mdEndComment

    String.html.mdEndComment

------------------------------------------------------------------------

### formClientId

    String formClientId

<span id="org.apache.struts.faces.taglib.LoadMessagesTag"></span>

**Class [org.apache.struts.faces.taglib.LoadMessagesTag](org/apache/struts/faces/taglib/LoadMessagesTag.html.md "class in org.apache.struts.faces.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### messages

    String messages

The name of the `MessageResources` to expose, or `null` for the default `MessageResources` for this application module.

------------------------------------------------------------------------

### var

    String var

The request attribute key under which a `Map` will be exposed.

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

**Package** **org.apache.struts.taglib.bean**

<span id="org.apache.struts.taglib.bean.CookieTag"></span>

**Class [org.apache.struts.taglib.bean.CookieTag](org/apache/struts/taglib/bean/CookieTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of Cookies if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the cookie whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no cookie of the specified name is found.

<span id="org.apache.struts.taglib.bean.DefineTag"></span>

**Class [org.apache.struts.taglib.bean.DefineTag](org/apache/struts/taglib/bean/DefineTag.html.md "class in org.apache.struts.taglib.bean") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### body

    String body

The body content of this tag (if any).

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### name

    String name

The name of the bean owning the property to be exposed.

------------------------------------------------------------------------

### property

    String property

The name of the property to be retrieved.

------------------------------------------------------------------------

### scope

    String scope

The scope within which to search for the specified bean.

------------------------------------------------------------------------

### toScope

    String toScope

The scope within which the newly defined bean will be creatd.

------------------------------------------------------------------------

### type

    String type

The fully qualified Java class name of the value to be exposed.

------------------------------------------------------------------------

### value

    String value

The (String) value to which the defined bean will be set.

<span id="org.apache.struts.taglib.bean.HeaderTag"></span>

**Class [org.apache.struts.taglib.bean.HeaderTag](org/apache/struts/taglib/bean/HeaderTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of header values if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the header whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no header of the specified name is found.

<span id="org.apache.struts.taglib.bean.IncludeTag"></span>

**Class [org.apache.struts.taglib.bean.IncludeTag](org/apache/struts/taglib/bean/IncludeTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The name of the global `ActionForward` that contains a path to our requested resource.

------------------------------------------------------------------------

### href

    String href

The absolute URL to the resource to be included.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### page

    String page

The context-relative URI of the page or servlet to be included.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.bean.MessageTag"></span>

**Class [org.apache.struts.taglib.bean.MessageTag](org/apache/struts/taglib/bean/MessageTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### arg0

    String arg0

The first optional argument.

------------------------------------------------------------------------

### arg1

    String arg1

The second optional argument.

------------------------------------------------------------------------

### arg2

    String arg2

The third optional argument.

------------------------------------------------------------------------

### arg3

    String arg3

The fourth optional argument.

------------------------------------------------------------------------

### arg4

    String arg4

The fifth optional argument.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### key

    String key

The message key of the message to be retrieved.

------------------------------------------------------------------------

### name

    String name

Name of the bean that contains the message key.

------------------------------------------------------------------------

### property

    String property

Name of the property to be accessed on the specified bean.

------------------------------------------------------------------------

### scope

    String scope

The scope to be searched to retrieve the specified bean.

------------------------------------------------------------------------

### localeKey

    String localeKey

The session scope key under which our Locale is stored.

<span id="org.apache.struts.taglib.bean.PageTag"></span>

**Class [org.apache.struts.taglib.bean.PageTag](org/apache/struts/taglib/bean/PageTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### property

    String property

The name of the page context property to be retrieved.

<span id="org.apache.struts.taglib.bean.ParameterTag"></span>

**Class [org.apache.struts.taglib.bean.ParameterTag](org/apache/struts/taglib/bean/ParameterTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### multiple

    String multiple

Return an array of parameter values if `multiple` is non-null.

------------------------------------------------------------------------

### name

    String name

The name of the parameter whose value is to be exposed.

------------------------------------------------------------------------

### value

    String value

The default value to return if no parameter of the specified name is found.

<span id="org.apache.struts.taglib.bean.ResourceTag"></span>

**Class [org.apache.struts.taglib.bean.ResourceTag](org/apache/struts/taglib/bean/ResourceTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### input

    String input

Return an InputStream to the specified resource if this is non-null.

------------------------------------------------------------------------

### name

    String name

The module-relative URI of the resource whose contents are to be exposed.

<span id="org.apache.struts.taglib.bean.SizeTag"></span>

**Class [org.apache.struts.taglib.bean.SizeTag](org/apache/struts/taglib/bean/SizeTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collection

    Object collection

The actual collection to be counted.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### name

    String name

The name of the bean owning the property to be counted.

------------------------------------------------------------------------

### property

    String property

The name of the property to be retrieved.

------------------------------------------------------------------------

### scope

    String scope

The scope within which to search for the specified bean.

<span id="org.apache.struts.taglib.bean.StrutsTag"></span>

**Class [org.apache.struts.taglib.bean.StrutsTag](org/apache/struts/taglib/bean/StrutsTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

The name of the scripting variable that will be exposed as a page scope attribute.

------------------------------------------------------------------------

### formBean

    String formBean

The name of the `ActionFormBean` object to be exposed.

------------------------------------------------------------------------

### forward

    String forward

The name of the `ActionForward` object to be exposed.

------------------------------------------------------------------------

### mapping

    String mapping

The name of the `ActionMapping` object to be exposed.

<span id="org.apache.struts.taglib.bean.WriteTag"></span>

**Class [org.apache.struts.taglib.bean.WriteTag](org/apache/struts/taglib/bean/WriteTag.html.md "class in org.apache.struts.taglib.bean") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

Filter the rendered output for characters that are sensitive in HTML?

------------------------------------------------------------------------

### ignore

    boolean ignore

Should we ignore missing beans and simply output nothing?

------------------------------------------------------------------------

### name

    String name

Name of the bean that contains the data we will be rendering.

------------------------------------------------------------------------

### property

    String property

Name of the property to be accessed on the specified bean.

------------------------------------------------------------------------

### scope

    String scope

The scope to be searched to retrieve the specified bean.

------------------------------------------------------------------------

### formatStr

    String formatStr

The format string to be used as format to convert value to String.

------------------------------------------------------------------------

### formatKey

    String formatKey

The key to search format string in applciation resources

------------------------------------------------------------------------

### localeKey

    String localeKey

The session scope key under which our Locale is stored.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.html.md**

<span id="org.apache.struts.taglib.html.md.BaseFieldTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") extends [BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accept

    String accept

Comma-delimited list of content types that a server processing this form will handle correctly. This property is defined only for the `file` tag, but is implemented here because it affects the rendered HTML of the corresponding \<input\> tag.

------------------------------------------------------------------------

### redisplay

    boolean redisplay

The "redisplay contents" flag (used only on `password`).

------------------------------------------------------------------------

### type

    String type

The type of input field represented by this tag (text, password, or hidden).

<span id="org.apache.struts.taglib.html.md.BaseHandlerTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskey

    String accesskey

Access key character.

------------------------------------------------------------------------

### tabindex

    String tabindex

Tab index value.

------------------------------------------------------------------------

### indexed

    boolean indexed

Whether to created indexed names for fields

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### onclick

    String onclick

Mouse click event.

------------------------------------------------------------------------

### ondblclick

    String ondblclick

Mouse double click event.

------------------------------------------------------------------------

### onmouseover

    String onmouseover

Mouse over component event.

------------------------------------------------------------------------

### onmouseout

    String onmouseout

Mouse exit component event.

------------------------------------------------------------------------

### onmousemove

    String onmousemove

Mouse moved over component event.

------------------------------------------------------------------------

### onmousedown

    String onmousedown

Mouse pressed on component event.

------------------------------------------------------------------------

### onmouseup

    String onmouseup

Mouse released on component event.

------------------------------------------------------------------------

### onkeydown

    String onkeydown

Key down in component event.

------------------------------------------------------------------------

### onkeyup

    String onkeyup

Key released in component event.

------------------------------------------------------------------------

### onkeypress

    String onkeypress

Key down and up together in component event.

------------------------------------------------------------------------

### onselect

    String onselect

Text selected in component event.

------------------------------------------------------------------------

### onchange

    String onchange

Content changed after component lost focus event.

------------------------------------------------------------------------

### onblur

    String onblur

Component lost focus event.

------------------------------------------------------------------------

### onfocus

    String onfocus

Component has received focus event.

------------------------------------------------------------------------

### disabled

    boolean disabled

Component is disabled.

------------------------------------------------------------------------

### doDisabled

    boolean doDisabled

Indicates whether 'disabled' is a valid attribute

------------------------------------------------------------------------

### readonly

    boolean readonly

Component is readonly.

------------------------------------------------------------------------

### doReadonly

    boolean doReadonly

Indicates whether 'readonly' is a valid attribute.

According to the HTML 4.0 Specification \<readonly\> is valid for \<input type="text"\>, \<input type="password"\> and \<textarea"\> elements. Therefore, except for those tags this value is set to `false`.

------------------------------------------------------------------------

### style

    String style

Style attribute associated with component.

------------------------------------------------------------------------

### styleClass

    String styleClass

Named Style class associated with component.

------------------------------------------------------------------------

### styleId

    String styleId

Identifier associated with component.

------------------------------------------------------------------------

### errorKey

    String errorKey

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### errorStyle

    String errorStyle

Style attribute associated with component when errors exist.

------------------------------------------------------------------------

### errorStyleClass

    String errorStyleClass

Named Style class associated with component when errors exist.

------------------------------------------------------------------------

### errorStyleId

    String errorStyleId

Identifier associated with component when errors exist.

------------------------------------------------------------------------

### alt

    String alt

The alternate text of this element.

------------------------------------------------------------------------

### altKey

    String altKey

The message resources key of the alternate text.

------------------------------------------------------------------------

### bundle

    String bundle

The name of the message resources bundle for message lookups.

------------------------------------------------------------------------

### locale

    String locale

The name of the session attribute key for our locale.

------------------------------------------------------------------------

### title

    String title

The advisory title of this element.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

------------------------------------------------------------------------

### titleKey

    String titleKey

The message resources key of the advisory title.

------------------------------------------------------------------------

### loopTagClass

    Class<T> loopTagClass

------------------------------------------------------------------------

### loopTagGetStatus

    Method loopTagGetStatus

------------------------------------------------------------------------

### loopTagStatusClass

    Class<T> loopTagStatusClass

------------------------------------------------------------------------

### loopTagStatusGetIndex

    Method loopTagStatusGetIndex

------------------------------------------------------------------------

### triedJstlInit

    boolean triedJstlInit

------------------------------------------------------------------------

### triedJstlSuccess

    boolean triedJstlSuccess

<span id="org.apache.struts.taglib.html.md.BaseInputTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### autocomplete

    String autocomplete

Autocomplete non standard attribute

------------------------------------------------------------------------

### cols

    String cols

The number of character columns for this field, or negative for no limit.

------------------------------------------------------------------------

### maxlength

    String maxlength

The maximum number of characters allowed, or negative for no limit.

------------------------------------------------------------------------

### property

    String property

The name of the field (and associated property) being processed.

------------------------------------------------------------------------

### rows

    String rows

The number of rows for this field, or negative for no limit.

------------------------------------------------------------------------

### value

    String value

The value for this field, or `null` to retrieve the corresponding property from our associated bean.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

<span id="org.apache.struts.taglib.html.md.BaseTag"></span>

**Class [org.apache.struts.taglib.html.md.BaseTag](org/apache/struts/taglib/html/BaseTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### REF\_SITE

    String REF_SITE

------------------------------------------------------------------------

### REF\_PAGE

    String REF_PAGE

------------------------------------------------------------------------

### server

    String server

The server name to use instead of request.getServerName().

------------------------------------------------------------------------

### target

    String target

The target window for this base reference.

------------------------------------------------------------------------

### ref

    String ref

The reference to which the base will created.

<span id="org.apache.struts.taglib.html.md.ButtonTag"></span>

**Class [org.apache.struts.taglib.html.md.ButtonTag](org/apache/struts/taglib/html/ButtonTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.CancelTag"></span>

**Class [org.apache.struts.taglib.html.md.CancelTag](org/apache/struts/taglib/html/CancelTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.CheckboxTag"></span>

**Class [org.apache.struts.taglib.html.md.CheckboxTag](org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The server value for this option.

<span id="org.apache.struts.taglib.html.md.ErrorsTag"></span>

**Class [org.apache.struts.taglib.html.md.ErrorsTag](org/apache/struts/taglib/html/ErrorsTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### locale

    String locale

The session attribute key for our locale.

------------------------------------------------------------------------

### name

    String name

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### property

    String property

The name of the property for which error messages should be returned, or `null` to return all errors.

------------------------------------------------------------------------

### header

    String header

The message resource key for errors header.

------------------------------------------------------------------------

### footer

    String footer

The message resource key for errors footer.

------------------------------------------------------------------------

### prefix

    String prefix

The message resource key for errors prefix.

------------------------------------------------------------------------

### suffix

    String suffix

The message resource key for errors suffix.

<span id="org.apache.struts.taglib.html.md.FileTag"></span>

**Class [org.apache.struts.taglib.html.md.FileTag](org/apache/struts/taglib/html/FileTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.FormTag"></span>

**Class [org.apache.struts.taglib.html.md.FormTag](org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### action

    String action

The action URL to which this form should be submitted, if any.

------------------------------------------------------------------------

### autocomplete

    String autocomplete

Autocomplete non standard attribute

------------------------------------------------------------------------

### postbackAction

    String postbackAction

A postback action URL to which this form should be submitted, if any.

------------------------------------------------------------------------

### moduleConfig

    ModuleConfig moduleConfig

The module configuration for our module.

------------------------------------------------------------------------

### enctype

    String enctype

The content encoding to be used on a POST submit.

------------------------------------------------------------------------

### focus

    String focus

The name of the field to receive focus, if any.

------------------------------------------------------------------------

### focusIndex

    String focusIndex

The index in the focus field array to receive focus. This only applies if the field given in the focus attribute is actually an array of fields. This allows a specific field in a radio button array to receive focus while still allowing indexed field names like "myRadioButtonField[1]" to be passed in the focus attribute.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### mapping

    ActionMapping mapping

The ActionMapping defining where we will be submitting this form

------------------------------------------------------------------------

### method

    String method

The request method used when submitting this form.

------------------------------------------------------------------------

### onreset

    String onreset

The onReset event script.

------------------------------------------------------------------------

### onsubmit

    String onsubmit

The onSubmit event script.

------------------------------------------------------------------------

### scriptLanguage

    boolean scriptLanguage

Include language attribute in the focus script's \<script\> element. This property is ignored in XHTML mode.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### servlet

    ActionServlet servlet

The ActionServlet instance we are associated with (so that we can initialize the `servlet` property on any form bean that we create).

------------------------------------------------------------------------

### style

    String style

The style attribute associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The style class associated with this tag.

------------------------------------------------------------------------

### styleId

    String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

### target

    String target

The window target.

------------------------------------------------------------------------

### beanName

    String beanName

The name of the form bean to (create and) use. This is either the same as the 'name' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### beanScope

    String beanScope

The scope of the form bean to (create and) use. This is either the same as the 'scope' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### beanType

    String beanType

The type of the form bean to (create and) use. This is either the same as the 'type' attribute, if that was specified, or is obtained from the associated `ActionMapping` otherwise.

------------------------------------------------------------------------

### acceptCharset

    String acceptCharset

The list of character encodings for input data that the server should accept.

------------------------------------------------------------------------

### disabled

    boolean disabled

Controls whether child controls should be 'disabled'.

------------------------------------------------------------------------

### readonly

    boolean readonly

Controls whether child controls should be 'readonly'.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

<span id="org.apache.struts.taglib.html.md.FrameTag"></span>

**Class [org.apache.struts.taglib.html.md.FrameTag](org/apache/struts/taglib/html/FrameTag.html "class in org.apache.struts.taglib.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### frameborder

    String frameborder

The frameborder attribute that should be rendered (1, 0).

------------------------------------------------------------------------

### frameName

    String frameName

The `name` attribute that should be rendered for this frame.

------------------------------------------------------------------------

### longdesc

    String longdesc

URI of a long description of this frame (complements title).

------------------------------------------------------------------------

### marginheight

    Integer marginheight

The margin height in pixels, or zero for no setting.

------------------------------------------------------------------------

### marginwidth

    Integer marginwidth

The margin width in pixels, or null for no setting.

------------------------------------------------------------------------

### noresize

    boolean noresize

Should users be disallowed to resize the frame?

------------------------------------------------------------------------

### scrolling

    String scrolling

What type of scrolling should be supported (yes, no, auto)?

<span id="org.apache.struts.taglib.html.md.HiddenTag"></span>

**Class [org.apache.struts.taglib.html.md.HiddenTag](org/apache/struts/taglib/html/HiddenTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### write

    boolean write

Should the value of this field also be rendered to the response?

<span id="org.apache.struts.taglib.html.md.HtmlTag"></span>

**Class [org.apache.struts.taglib.html.md.HtmlTag](org/apache/struts/taglib/html/HtmlTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### .html.md

    boolean .html.md

Are we rendering an .html.md page?

------------------------------------------------------------------------

### lang

    boolean lang

Are we rendering a lang attribute?

**Since:**  
Struts 1.2

<span id="org.apache.struts.taglib.html.md.ImageTag"></span>

**Class [org.apache.struts.taglib.html.md.ImageTag](org/apache/struts/taglib/html/ImageTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### align

    String align

The alignment for this image.

------------------------------------------------------------------------

### border

    String border

The border size around the image.

------------------------------------------------------------------------

### page

    String page

The module-relative URI of the image.

------------------------------------------------------------------------

### pageKey

    String pageKey

The message resources key of the module-relative URI of the image.

------------------------------------------------------------------------

### src

    String src

The URL of this image.

------------------------------------------------------------------------

### srcKey

    String srcKey

The message resources key for the URL of this image.

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

<span id="org.apache.struts.taglib.html.md.ImgTag"></span>

**Class [org.apache.struts.taglib.html.md.ImgTag](org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### align

    String align

The property to specify where to align the image.

------------------------------------------------------------------------

### border

    String border

The border size around the image.

------------------------------------------------------------------------

### height

    String height

The image height.

------------------------------------------------------------------------

### hspace

    String hspace

The horizontal spacing around the image.

------------------------------------------------------------------------

### imageName

    String imageName

The image name for named images.

------------------------------------------------------------------------

### ismap

    String ismap

Server-side image map declaration.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative path, starting with a slash character, of the image to be displayed by this rendered tag.

------------------------------------------------------------------------

### pageKey

    String pageKey

The message resources key under which we should look up the `page` attribute for this generated tag, if any.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be used as the source for this image.

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

In situations where an image is dynamically generated (such as to create a chart graph), this specifies the single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### src

    String src

The image source URI.

------------------------------------------------------------------------

### srcKey

    String srcKey

The message resources key under which we should look up the `src` attribute for this generated tag, if any.

------------------------------------------------------------------------

### usemap

    String usemap

Client-side image map declaration.

------------------------------------------------------------------------

### vspace

    String vspace

The vertical spacing around the image.

------------------------------------------------------------------------

### width

    String width

The image width.

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.html.md.JavascriptValidatorTag"></span>

**Class [org.apache.struts.taglib.html.md.JavascriptValidatorTag](org/apache/struts/taglib/html/JavascriptValidatorTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### formName

    String formName

The name of the form that corresponds with the action name in struts-config.xml. Specifying a form name places a \<script\> \</script\> around the javascript.

------------------------------------------------------------------------

### jsFormName

    String jsFormName

formName is used for both Javascript and non-javascript validations. For the javascript validations, there is the possibility that we will be rewriting the formName (if it is a ValidatorActionForm instead of just a ValidatorForm) so we need another variable to hold the formName just for javascript usage.

------------------------------------------------------------------------

### page

    int page

The current page number of a multi-part form. Only valid when the formName attribute is set.

------------------------------------------------------------------------

### methodName

    String methodName

This will be used as is for the JavaScript validation method name if it has a value. This is the method name of the main JavaScript method that the form calls to perform validations.

------------------------------------------------------------------------

### scriptLanguage

    boolean scriptLanguage

Include language attribute in the \<script\> element. This property is ignored in XHTML mode.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### staticJavascript

    String staticJavascript

The static JavaScript methods will only be printed if this is set to "true".

------------------------------------------------------------------------

### dynamicJavascript

    String dynamicJavascript

The dynamic JavaScript objects will only be generated if this is set to "true".

------------------------------------------------------------------------

### src

    String src

The src attribute for.html.md script element (used to include an external script resource). The src attribute is only recognized when the formName attribute is specified.

------------------------------------------------------------------------

###.html.mdComment

    String.html.mdComment

The JavaScript methods will enclosed with.html.md comments if this is set to "true".

------------------------------------------------------------------------

### cdata

    String cdata

Hide JavaScript methods in a CDATA section for XHTML when "true".

<span id="org.apache.struts.taglib.html.md.LinkTag"></span>

**Class [org.apache.struts.taglib.html.md.LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The logical forward name from which to retrieve the hyperlink URI.

Usage note: If a forward config is used in a hyperlink, and a module is specified, the path must lead to another action and not directly to a page. This is in keeping with rule that in a modular application all links must be to an action rather than a page.

------------------------------------------------------------------------

### href

    String href

The hyperlink URI.

------------------------------------------------------------------------

### linkName

    String linkName

The link name for named links.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative page URL (beginning with a slash) to which this hyperlink will be rendered.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

The single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### target

    String target

The window target.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include transaction token (if any) in the hyperlink?

------------------------------------------------------------------------

### parameters

    Map<K,V> parameters

Additional parameters included programatically.

------------------------------------------------------------------------

### indexId

    String indexId

Name of parameter to generate to hold index number

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

<span id="org.apache.struts.taglib.html.md.MessagesTag"></span>

**Class [org.apache.struts.taglib.html.md.MessagesTag](org/apache/struts/taglib/html/MessagesTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### iterator

    Iterator<E> iterator

Iterator of the elements of this error collection, while we are actually running.

------------------------------------------------------------------------

### processed

    boolean processed

Whether or not any error messages have been processed.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

### bundle

    String bundle

The servlet context attribute key for our resources.

------------------------------------------------------------------------

### locale

    String locale

The session attribute key for our locale.

------------------------------------------------------------------------

### name

    String name

The request attribute key for our error messages (if any).

------------------------------------------------------------------------

### property

    String property

The name of the property for which error messages should be returned, or `null` to return all errors.

------------------------------------------------------------------------

### header

    String header

The message resource key for errors header.

------------------------------------------------------------------------

### footer

    String footer

The message resource key for errors footer.

------------------------------------------------------------------------

### message

    String message

If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

<span id="org.apache.struts.taglib.html.md.MultiboxTag"></span>

**Class [org.apache.struts.taglib.html.md.MultiboxTag](org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### constant

    String constant

The constant String value to be returned when this checkbox is selected and the form is submitted.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### value

    String value

The value which will mark this checkbox as "checked" if present in the array returned by our property getter.

<span id="org.apache.struts.taglib.html.md.OptionsCollectionTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionsCollectionTag](org/apache/struts/taglib/html/OptionsCollectionTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

Should the label values be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### label

    String label

The name of the bean property containing the label.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing the values collection.

------------------------------------------------------------------------

### property

    String property

The name of the property to use to build the values collection.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

------------------------------------------------------------------------

### value

    String value

The name of the bean property containing the value.

<span id="org.apache.struts.taglib.html.md.OptionsTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionsTag](org/apache/struts/taglib/html/OptionsTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collection

    String collection

The name of the collection containing beans that have properties to provide both the values and the labels (identified by the `property` and `labelProperty` attributes).

------------------------------------------------------------------------

### filter

    boolean filter

Should the label values be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### labelName

    String labelName

The name of the bean containing the labels collection.

------------------------------------------------------------------------

### labelProperty

    String labelProperty

The bean property containing the labels collection.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing the values collection.

------------------------------------------------------------------------

### property

    String property

The name of the property to use to build the values collection.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

<span id="org.apache.struts.taglib.html.md.OptionTag"></span>

**Class [org.apache.struts.taglib.html.md.OptionTag](org/apache/struts/taglib/html/OptionTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### text

    String text

The message text to be displayed to the user for this tag (if any)

------------------------------------------------------------------------

### bundle

    String bundle

The name of the servlet context attribute containing our message resources.

------------------------------------------------------------------------

### disabled

    boolean disabled

Is this option disabled?

------------------------------------------------------------------------

### filter

    boolean filter

Should the label be filtered for HTML sensitive characters?

------------------------------------------------------------------------

### key

    String key

The key used to look up the text displayed to the user for this option, if any.

------------------------------------------------------------------------

### locale

    String locale

The name of the attribute containing the Locale to be used for looking up internationalized messages.

------------------------------------------------------------------------

### style

    String style

The style associated with this tag.

------------------------------------------------------------------------

### styleClass

    String styleClass

The named style class associated with this tag.

------------------------------------------------------------------------

### styleId

    String styleId

The identifier associated with this tag.

------------------------------------------------------------------------

### lang

    String lang

The language code of this element.

------------------------------------------------------------------------

### dir

    String dir

The direction for weak/neutral text of this element.

------------------------------------------------------------------------

### value

    String value

The server value for this option, also used to match against the current property value to determine whether this option should be marked as selected.

<span id="org.apache.struts.taglib.html.md.ParamTag"></span>

**Class [org.apache.struts.taglib.html.md.ParamTag](org/apache/struts/taglib/html/ParamTag.html "class in org.apache.struts.taglib.html") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the query parameter.

------------------------------------------------------------------------

### value

    String value

The value of the query parameter or body content of this tag (if any).

<span id="org.apache.struts.taglib.html.md.PasswordTag"></span>

**Class [org.apache.struts.taglib.html.md.PasswordTag](org/apache/struts/taglib/html/PasswordTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.RadioTag"></span>

**Class [org.apache.struts.taglib.html.md.RadioTag](org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name for this field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The server value for this option.

------------------------------------------------------------------------

### idName

    String idName

Name of the bean (in some scope) that will return the value of the radio tag.

If an iterator is used to render a series of radio tags, this field may be used to specify the name of the bean exposed by the iterator. In this case, the value attribute is used as the name of a property on the `idName` bean that returns the value of the radio tag in this iteration.

<span id="org.apache.struts.taglib.html.md.ResetTag"></span>

**Class [org.apache.struts.taglib.html.md.ResetTag](org/apache/struts/taglib/html/ResetTag.html "class in org.apache.struts.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.RewriteTag"></span>

**Class [org.apache.struts.taglib.html.md.RewriteTag](org/apache/struts/taglib/html/RewriteTag.html "class in org.apache.struts.taglib.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.SelectTag"></span>

**Class [org.apache.struts.taglib.html.md.SelectTag](org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### match

    String[] match

The actual values we will match against, calculated in doStartTag().

------------------------------------------------------------------------

### multiple

    String multiple

Should multiple selections be allowed. Any non-null value will trigger rendering this.

------------------------------------------------------------------------

### name

    String name

The name of the bean containing our underlying property.

------------------------------------------------------------------------

### property

    String property

The property name we are associated with.

------------------------------------------------------------------------

### saveBody

    String saveBody

The saved body content of this tag.

------------------------------------------------------------------------

### size

    String size

How many available options should be displayed when this element is rendered?

------------------------------------------------------------------------

### value

    String value

The value to compare with for marking an option selected.

<span id="org.apache.struts.taglib.html.md.SubmitTag"></span>

**Class [org.apache.struts.taglib.html.md.SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") extends [BaseHandlerTag](org/apache/struts/taglib/html/BaseHandlerTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

The name of the generated input field.

------------------------------------------------------------------------

### text

    String text

The body content of this tag (if any).

------------------------------------------------------------------------

### value

    String value

The value of the button label.

<span id="org.apache.struts.taglib.html.md.TextareaTag"></span>

**Class [org.apache.struts.taglib.html.md.TextareaTag](org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html") extends [BaseInputTag](org/apache/struts/taglib/html/BaseInputTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.TextTag"></span>

**Class [org.apache.struts.taglib.html.md.TextTag](org/apache/struts/taglib/html/TextTag.html "class in org.apache.struts.taglib.html") extends [BaseFieldTag](org/apache/struts/taglib/html/BaseFieldTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="org.apache.struts.taglib.html.md.XhtmlTag"></span>

**Class [org.apache.struts.taglib.html.md.XhtmlTag](org/apache/struts/taglib/html/XhtmlTag.html "class in org.apache.struts.taglib.html") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.logic**

<span id="org.apache.struts.taglib.logic.CompareTagBase"></span>

**Class [org.apache.struts.taglib.logic.CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### value

    String value

The value to which the variable specified by other attributes of this tag will be compared.

<span id="org.apache.struts.taglib.logic.ConditionalTagBase"></span>

**Class [org.apache.struts.taglib.logic.ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookie

    String cookie

The name of the cookie to be used as a variable.

------------------------------------------------------------------------

### header

    String header

The name of the HTTP request header to be used as a variable.

------------------------------------------------------------------------

### name

    String name

The name of the JSP bean to be used as a variable (if `property` is not specified), or whose property is to be accessed (if `property` is specified).

------------------------------------------------------------------------

### parameter

    String parameter

The name of the HTTP request parameter to be used as a variable.

------------------------------------------------------------------------

### property

    String property

The name of the bean property to be used as a variable.

------------------------------------------------------------------------

### role

    String role

The name of the security role to be checked for.

------------------------------------------------------------------------

### scope

    String scope

The scope to search for the bean named by the name property, or "any scope" if null.

------------------------------------------------------------------------

### user

    String user

The user principal name to be checked for.

<span id="org.apache.struts.taglib.logic.EmptyTag"></span>

**Class [org.apache.struts.taglib.logic.EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.EqualTag"></span>

**Class [org.apache.struts.taglib.logic.EqualTag](org/apache/struts/taglib/logic/EqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.ForwardTag"></span>

**Class [org.apache.struts.taglib.logic.ForwardTag](org/apache/struts/taglib/logic/ForwardTag.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The logical name of the `ActionForward` entry to be looked up.

<span id="org.apache.struts.taglib.logic.GreaterEqualTag"></span>

**Class [org.apache.struts.taglib.logic.GreaterEqualTag](org/apache/struts/taglib/logic/GreaterEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.GreaterThanTag"></span>

**Class [org.apache.struts.taglib.logic.GreaterThanTag](org/apache/struts/taglib/logic/GreaterThanTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.IterateTag"></span>

**Class [org.apache.struts.taglib.logic.IterateTag](org/apache/struts/taglib/logic/IterateTag.html.md "class in org.apache.struts.taglib.logic") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### iterator

    Iterator<E> iterator

Iterator of the elements of this collection, while we are actually running.

------------------------------------------------------------------------

### lengthCount

    int lengthCount

The number of elements we have already rendered.

------------------------------------------------------------------------

### lengthValue

    int lengthValue

The actual length value (calculated in the start tag).

------------------------------------------------------------------------

### offsetValue

    int offsetValue

The actual offset value (calculated in the start tag).

------------------------------------------------------------------------

### started

    boolean started

Has this tag instance been started?

------------------------------------------------------------------------

### collection

    Object collection

The collection over which we will be iterating.

------------------------------------------------------------------------

### id

    String id

The name of the scripting variable to be exposed.

------------------------------------------------------------------------

### indexId

    String indexId

The name of the scripting variable to be exposed as the current index.

------------------------------------------------------------------------

### length

    String length

The length value or attribute name (\<=0 means no limit).

------------------------------------------------------------------------

### name

    String name

The name of the collection or owning bean.

------------------------------------------------------------------------

### offset

    String offset

The starting offset (zero relative).

------------------------------------------------------------------------

### property

    String property

The property name containing the collection.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### type

    String type

The Java class of each exposed element of the collection.

<span id="org.apache.struts.taglib.logic.LessEqualTag"></span>

**Class [org.apache.struts.taglib.logic.LessEqualTag](org/apache/struts/taglib/logic/LessEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.LessThanTag"></span>

**Class [org.apache.struts.taglib.logic.LessThanTag](org/apache/struts/taglib/logic/LessThanTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.MatchTag"></span>

**Class [org.apache.struts.taglib.logic.MatchTag](org/apache/struts/taglib/logic/MatchTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### location

    String location

The location where the match must exist (`start` or `end`), or `null` for anywhere.

------------------------------------------------------------------------

### value

    String value

The value to which the variable specified by other attributes of this tag will be matched.

<span id="org.apache.struts.taglib.logic.MessagesNotPresentTag"></span>

**Class [org.apache.struts.taglib.logic.MessagesNotPresentTag](org/apache/struts/taglib/logic/MessagesNotPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.MessagesPresentTag"></span>

**Class [org.apache.struts.taglib.logic.MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### message

    String message

If this is set to 'true', then the `Globals.MESSAGE_KEY` will be used to retrieve the messages from scope.

<span id="org.apache.struts.taglib.logic.NotEmptyTag"></span>

**Class [org.apache.struts.taglib.logic.NotEmptyTag](org/apache/struts/taglib/logic/NotEmptyTag.html.md "class in org.apache.struts.taglib.logic") extends [EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotEqualTag"></span>

**Class [org.apache.struts.taglib.logic.NotEqualTag](org/apache/struts/taglib/logic/NotEqualTag.html.md "class in org.apache.struts.taglib.logic") extends [CompareTagBase](org/apache/struts/taglib/logic/CompareTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotMatchTag"></span>

**Class [org.apache.struts.taglib.logic.NotMatchTag](org/apache/struts/taglib/logic/NotMatchTag.html.md "class in org.apache.struts.taglib.logic") extends [MatchTag](org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.NotPresentTag"></span>

**Class [org.apache.struts.taglib.logic.NotPresentTag](org/apache/struts/taglib/logic/NotPresentTag.html.md "class in org.apache.struts.taglib.logic") extends [PresentTag](org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.PresentTag"></span>

**Class [org.apache.struts.taglib.logic.PresentTag](org/apache/struts/taglib/logic/PresentTag.html.md "class in org.apache.struts.taglib.logic") extends [ConditionalTagBase](org/apache/struts/taglib/logic/ConditionalTagBase.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="org.apache.struts.taglib.logic.RedirectTag"></span>

**Class [org.apache.struts.taglib.logic.RedirectTag](org/apache/struts/taglib/logic/RedirectTag.html.md "class in org.apache.struts.taglib.logic") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### anchor

    String anchor

The anchor to be added to the end of the generated hyperlink.

------------------------------------------------------------------------

### forward

    String forward

The logical forward name from which to retrieve the redirect URI.

------------------------------------------------------------------------

### href

    String href

The redirect URI.

------------------------------------------------------------------------

### name

    String name

The JSP bean name for query parameters.

------------------------------------------------------------------------

### page

    String page

The module-relative page URL (beginning with a slash) to which this redirect will be rendered.

------------------------------------------------------------------------

### action

    String action

The module-relative action (beginning with a slash) which will be called by this link

------------------------------------------------------------------------

### module

    String module

The module prefix (beginning with a slash) which will be used to find the action for this link.

------------------------------------------------------------------------

### paramId

    String paramId

The single-parameter request parameter name to generate.

------------------------------------------------------------------------

### paramName

    String paramName

The single-parameter JSP bean name.

------------------------------------------------------------------------

### paramProperty

    String paramProperty

The single-parameter JSP bean property.

------------------------------------------------------------------------

### paramScope

    String paramScope

The single-parameter JSP bean scope.

------------------------------------------------------------------------

### property

    String property

The JSP bean property name for query parameters.

------------------------------------------------------------------------

### scope

    String scope

The scope of the bean specified by the name property, if any.

------------------------------------------------------------------------

### transaction

    boolean transaction

Include our transaction control token?

------------------------------------------------------------------------

### useLocalEncoding

    boolean useLocalEncoding

Use character encoding from ServletResponse\#getCharacterEncoding to get bytes of the url string for urlencoding?

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested**

<span id="org.apache.struts.taglib.nested.NestedPropertyTag"></span>

**Class [org.apache.struts.taglib.nested.NestedPropertyTag](org/apache/struts/taglib/nested/NestedPropertyTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

------------------------------------------------------------------------

### originalNest

    String originalNest

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.NestedReference"></span>

**Class [org.apache.struts.taglib.nested.NestedReference](org/apache/struts/taglib/nested/NestedReference.html.md "class in org.apache.struts.taglib.nested") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### beanName

    String beanName

------------------------------------------------------------------------

### property

    String property

<span id="org.apache.struts.taglib.nested.NestedRootTag"></span>

**Class [org.apache.struts.taglib.nested.NestedRootTag](org/apache/struts/taglib/nested/NestedRootTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.NestedWriteNestingTag"></span>

**Class [org.apache.struts.taglib.nested.NestedWriteNestingTag](org/apache/struts/taglib/nested/NestedWriteNestingTag.html.md "class in org.apache.struts.taglib.nested") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filter

    boolean filter

------------------------------------------------------------------------

### property

    String property

------------------------------------------------------------------------

### id

    String id

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.bean**

<span id="org.apache.struts.taglib.nested.bean.NestedDefineTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedDefineTag](org/apache/struts/taglib/nested/bean/NestedDefineTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [DefineTag](org/apache/struts/taglib/bean/DefineTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedMessageTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedMessageTag](org/apache/struts/taglib/nested/bean/NestedMessageTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [MessageTag](org/apache/struts/taglib/bean/MessageTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedSizeTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedSizeTag](org/apache/struts/taglib/nested/bean/NestedSizeTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [SizeTag](org/apache/struts/taglib/bean/SizeTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.bean.NestedWriteTag"></span>

**Class [org.apache.struts.taglib.nested.bean.NestedWriteTag](org/apache/struts/taglib/nested/bean/NestedWriteTag.html.md "class in org.apache.struts.taglib.nested.bean") extends [WriteTag](org/apache/struts/taglib/bean/WriteTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.html.md**

<span id="org.apache.struts.taglib.nested.html.md.NestedCheckboxTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedCheckboxTag](org/apache/struts/taglib/nested/html/NestedCheckboxTag.html "class in org.apache.struts.taglib.nested.html") extends [CheckboxTag](org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedErrorsTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedErrorsTag](org/apache/struts/taglib/nested/html/NestedErrorsTag.html "class in org.apache.struts.taglib.nested.html") extends [ErrorsTag](org/apache/struts/taglib/html/ErrorsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedFileTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedFileTag](org/apache/struts/taglib/nested/html/NestedFileTag.html "class in org.apache.struts.taglib.nested.html") extends [FileTag](org/apache/struts/taglib/html/FileTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedFormTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedFormTag](org/apache/struts/taglib/nested/html/NestedFormTag.html "class in org.apache.struts.taglib.nested.html") extends [FormTag](org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

The name

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.html.md.NestedHiddenTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedHiddenTag](org/apache/struts/taglib/nested/html/NestedHiddenTag.html "class in org.apache.struts.taglib.nested.html") extends [HiddenTag](org/apache/struts/taglib/html/HiddenTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedImageTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedImageTag](org/apache/struts/taglib/nested/html/NestedImageTag.html "class in org.apache.struts.taglib.nested.html") extends [ImageTag](org/apache/struts/taglib/html/ImageTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedImgTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedImgTag](org/apache/struts/taglib/nested/html/NestedImgTag.html "class in org.apache.struts.taglib.nested.html") extends [ImgTag](org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedLinkTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedLinkTag](org/apache/struts/taglib/nested/html/NestedLinkTag.html "class in org.apache.struts.taglib.nested.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### origName

    String origName

------------------------------------------------------------------------

### origProperty

    String origProperty

------------------------------------------------------------------------

### origParamProperty

    String origParamProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedMessagesTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedMessagesTag](org/apache/struts/taglib/nested/html/NestedMessagesTag.html "class in org.apache.struts.taglib.nested.html") extends [MessagesTag](org/apache/struts/taglib/html/MessagesTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedMultiboxTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedMultiboxTag](org/apache/struts/taglib/nested/html/NestedMultiboxTag.html "class in org.apache.struts.taglib.nested.html") extends [MultiboxTag](org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedOptionsCollectionTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedOptionsCollectionTag](org/apache/struts/taglib/nested/html/NestedOptionsCollectionTag.html "class in org.apache.struts.taglib.nested.html") extends [OptionsCollectionTag](org/apache/struts/taglib/html/OptionsCollectionTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedOptionsTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedOptionsTag](org/apache/struts/taglib/nested/html/NestedOptionsTag.html "class in org.apache.struts.taglib.nested.html") extends [OptionsTag](org/apache/struts/taglib/html/OptionsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

### originalLabelProperty

    String originalLabelProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedPasswordTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedPasswordTag](org/apache/struts/taglib/nested/html/NestedPasswordTag.html "class in org.apache.struts.taglib.nested.html") extends [PasswordTag](org/apache/struts/taglib/html/PasswordTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedRadioTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedRadioTag](org/apache/struts/taglib/nested/html/NestedRadioTag.html "class in org.apache.struts.taglib.nested.html") extends [RadioTag](org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedSelectTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedSelectTag](org/apache/struts/taglib/nested/html/NestedSelectTag.html "class in org.apache.struts.taglib.nested.html") extends [SelectTag](org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedSubmitTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedSubmitTag](org/apache/struts/taglib/nested/html/NestedSubmitTag.html "class in org.apache.struts.taglib.nested.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedTextareaTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedTextareaTag](org/apache/struts/taglib/nested/html/NestedTextareaTag.html "class in org.apache.struts.taglib.nested.html") extends [TextareaTag](org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.html.md.NestedTextTag"></span>

**Class [org.apache.struts.taglib.nested.html.md.NestedTextTag](org/apache/struts/taglib/nested/html/NestedTextTag.html "class in org.apache.struts.taglib.nested.html") extends [TextTag](org/apache/struts/taglib/html/TextTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.taglib.nested.logic**

<span id="org.apache.struts.taglib.nested.logic.NestedEmptyTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedEmptyTag](org/apache/struts/taglib/nested/logic/NestedEmptyTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [EmptyTag](org/apache/struts/taglib/logic/EmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedEqualTag](org/apache/struts/taglib/nested/logic/NestedEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [EqualTag](org/apache/struts/taglib/logic/EqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedGreaterEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedGreaterEqualTag](org/apache/struts/taglib/nested/logic/NestedGreaterEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [GreaterEqualTag](org/apache/struts/taglib/logic/GreaterEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedGreaterThanTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedGreaterThanTag](org/apache/struts/taglib/nested/logic/NestedGreaterThanTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [GreaterThanTag](org/apache/struts/taglib/logic/GreaterThanTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedIterateTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedIterateTag](org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [IterateTag](org/apache/struts/taglib/logic/IterateTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nesting

    String nesting

------------------------------------------------------------------------

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

### originalNesting

    String originalNesting

------------------------------------------------------------------------

### originalNestingName

    String originalNestingName

<span id="org.apache.struts.taglib.nested.logic.NestedLessEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedLessEqualTag](org/apache/struts/taglib/nested/logic/NestedLessEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [LessEqualTag](org/apache/struts/taglib/logic/LessEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedLessThanTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedLessThanTag](org/apache/struts/taglib/nested/logic/NestedLessThanTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [LessThanTag](org/apache/struts/taglib/logic/LessThanTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMatchTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMatchTag](org/apache/struts/taglib/nested/logic/NestedMatchTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MatchTag](org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMessagesNotPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMessagesNotPresentTag](org/apache/struts/taglib/nested/logic/NestedMessagesNotPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MessagesNotPresentTag](org/apache/struts/taglib/logic/MessagesNotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedMessagesPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedMessagesPresentTag](org/apache/struts/taglib/nested/logic/NestedMessagesPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotEmptyTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotEmptyTag](org/apache/struts/taglib/nested/logic/NestedNotEmptyTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotEmptyTag](org/apache/struts/taglib/logic/NotEmptyTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotEqualTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotEqualTag](org/apache/struts/taglib/nested/logic/NestedNotEqualTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotEqualTag](org/apache/struts/taglib/logic/NotEqualTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotMatchTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotMatchTag](org/apache/struts/taglib/nested/logic/NestedNotMatchTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotMatchTag](org/apache/struts/taglib/logic/NotMatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedNotPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedNotPresentTag](org/apache/struts/taglib/nested/logic/NestedNotPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [NotPresentTag](org/apache/struts/taglib/logic/NotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

<span id="org.apache.struts.taglib.nested.logic.NestedPresentTag"></span>

**Class [org.apache.struts.taglib.nested.logic.NestedPresentTag](org/apache/struts/taglib/nested/logic/NestedPresentTag.html.md "class in org.apache.struts.taglib.nested.logic") extends [PresentTag](org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### originalName

    String originalName

------------------------------------------------------------------------

### originalProperty

    String originalProperty

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles**

<span id="org.apache.struts.tiles.ComponentContext"></span>

**Class [org.apache.struts.tiles.ComponentContext](org/apache/struts/tiles/ComponentContext.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributes

    Map<K,V> attributes

Component attributes.

<span id="org.apache.struts.tiles.ComponentDefinition"></span>

**Class [org.apache.struts.tiles.ComponentDefinition](org/apache/struts/tiles/ComponentDefinition.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

Definition name

------------------------------------------------------------------------

### path

    String path

Component / template path (URL).

------------------------------------------------------------------------

### attributes

    Map<K,V> attributes

Attributes defined for the component.

------------------------------------------------------------------------

### role

    String role

Role associated to definition.

------------------------------------------------------------------------

### controller

    String controller

Associated Controller URL or classname, if defined

------------------------------------------------------------------------

### controllerType

    String controllerType

Associated Controller typename, if controllerName defined. Can be CONTROLLER, ACTION or URL, or null.

------------------------------------------------------------------------

### controllerInstance

    Controller controllerInstance

Controller associated to Definition. Lazy creation : only on first request

<span id="org.apache.struts.tiles.DefinitionAttribute"></span>

**Class [org.apache.struts.tiles.DefinitionAttribute](org/apache/struts/tiles/DefinitionAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.DefinitionNameAttribute"></span>

**Class [org.apache.struts.tiles.DefinitionNameAttribute](org/apache/struts/tiles/DefinitionNameAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.DefinitionsFactoryConfig"></span>

**Class [org.apache.struts.tiles.DefinitionsFactoryConfig](org/apache/struts/tiles/DefinitionsFactoryConfig.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factoryClassname

    String factoryClassname

Fully qualified classname of the factory to create. If no classname is set, a default factory is created (of class "org.apache.struts.tiles.xmlDefinition.I18nFactorySet").

------------------------------------------------------------------------

### parserValidate

    boolean parserValidate

Specifies whether the parser will validate configuration files. Default value is true.

------------------------------------------------------------------------

### definitionConfigFiles

    String definitionConfigFiles

Definition configuration file specified by user.

------------------------------------------------------------------------

### moduleAware

    boolean moduleAware

Specifies whether the factory is "module-aware".

------------------------------------------------------------------------

### factoryName

    String factoryName

The name associated to this factory.
 With Struts 1.1, this name is the module name to which this factory belong. It is set by the system.
 In prior versions, this property is not used.

------------------------------------------------------------------------

### extraAttributes

    Map<K,V> extraAttributes

Map of extra attribute available.

<span id="org.apache.struts.tiles.DefinitionsFactoryException"></span>

**Class [org.apache.struts.tiles.DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html.md "class in org.apache.struts.tiles") extends [TilesException](org/apache/struts/tiles/TilesException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

Any "wrapped" exception will be exposed when this is serialized.

 

<span id="org.apache.struts.tiles.DirectStringAttribute"></span>

**Class [org.apache.struts.tiles.DirectStringAttribute](org/apache/struts/tiles/DirectStringAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.FactoryNotFoundException"></span>

**Class [org.apache.struts.tiles.FactoryNotFoundException](org/apache/struts/tiles/FactoryNotFoundException.html.md "class in org.apache.struts.tiles") extends [DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.NoSuchDefinitionException"></span>

**Class [org.apache.struts.tiles.NoSuchDefinitionException](org/apache/struts/tiles/NoSuchDefinitionException.html.md "class in org.apache.struts.tiles") extends [DefinitionsFactoryException](org/apache/struts/tiles/DefinitionsFactoryException.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.PathAttribute"></span>

**Class [org.apache.struts.tiles.PathAttribute](org/apache/struts/tiles/PathAttribute.html.md "class in org.apache.struts.tiles") extends [UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.RedeployableActionServlet"></span>

**Class [org.apache.struts.tiles.RedeployableActionServlet](org/apache/struts/tiles/RedeployableActionServlet.html.md "class in org.apache.struts.tiles") extends [ActionServlet](org/apache/struts/action/ActionServlet.html "class in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### tileProcessor

    TilesRequestProcessor tileProcessor

<span id="org.apache.struts.tiles.TilesException"></span>

**Class [org.apache.struts.tiles.TilesException](org/apache/struts/tiles/TilesException.html.md "class in org.apache.struts.tiles") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exception

    Exception exception

Any "wrapped" exception will be exposed when this is serialized.

 

<span id="org.apache.struts.tiles.TilesUtilImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilImpl](org/apache/struts/tiles/TilesUtilImpl.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilStrutsImpl](org/apache/struts/tiles/TilesUtilStrutsImpl.html.md "class in org.apache.struts.tiles") extends [TilesUtilImpl](org/apache/struts/tiles/TilesUtilImpl.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.TilesUtilStrutsModulesImpl"></span>

**Class [org.apache.struts.tiles.TilesUtilStrutsModulesImpl](org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md "class in org.apache.struts.tiles") extends [TilesUtilStrutsImpl](org/apache/struts/tiles/TilesUtilStrutsImpl.html "class in org.apache.struts.tiles") implements Serializable**

<span id="org.apache.struts.tiles.UntypedAttribute"></span>

**Class [org.apache.struts.tiles.UntypedAttribute](org/apache/struts/tiles/UntypedAttribute.html.md "class in org.apache.struts.tiles") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### role

    String role

Role associated to this attribute.

------------------------------------------------------------------------

### value

    Object value

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.beans**

<span id="org.apache.struts.tiles.beans.SimpleMenuItem"></span>

**Class [org.apache.struts.tiles.beans.SimpleMenuItem](org/apache/struts/tiles/beans/SimpleMenuItem.html.md "class in org.apache.struts.tiles.beans") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### value

    String value

------------------------------------------------------------------------

### link

    String link

------------------------------------------------------------------------

### icon

    String icon

------------------------------------------------------------------------

### tooltip

    String tooltip

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.definition**

<span id="org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper"></span>

**Class [org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper](org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md "class in org.apache.struts.tiles.definition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    ComponentDefinitionsFactory factory

The underlying factory.

------------------------------------------------------------------------

### config

    DefinitionsFactoryConfig config

Factory configuration,

<span id="org.apache.struts.tiles.definition.ReloadableDefinitionsFactory"></span>

**Class [org.apache.struts.tiles.definition.ReloadableDefinitionsFactory](org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html.md "class in org.apache.struts.tiles.definition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    ComponentDefinitionsFactory factory

The real factory instance.

------------------------------------------------------------------------

### properties

    Map<K,V> properties

Initialization parameters.

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.taglib**

<span id="org.apache.struts.tiles.taglib.AddTag"></span>

**Class [org.apache.struts.tiles.taglib.AddTag](org/apache/struts/tiles/taglib/AddTag.html.md "class in org.apache.struts.tiles.taglib") extends [PutTag](org/apache/struts/tiles/taglib/PutTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="org.apache.struts.tiles.taglib.AttributeToScopeTag"></span>

**Class [org.apache.struts.tiles.taglib.AttributeToScopeTag](org/apache/struts/tiles/taglib/AttributeToScopeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### scopeName

    String scopeName

**Deprecated.** 

The scope name.

------------------------------------------------------------------------

### scope

    int scope

**Deprecated.** 

The scope value.

------------------------------------------------------------------------

### property

    String property

**Deprecated.** 

The property name to be exposed.

<span id="org.apache.struts.tiles.taglib.DefinitionTag"></span>

**Class [org.apache.struts.tiles.taglib.DefinitionTag](org/apache/struts/tiles/taglib/DefinitionTag.html.md "class in org.apache.struts.tiles.taglib") extends [DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### id

    String id

Definition identifier.

------------------------------------------------------------------------

### scope

    String scope

Scope into which definition will be saved.

------------------------------------------------------------------------

### extendsDefinition

    String extendsDefinition

Extends attribute value.

------------------------------------------------------------------------

### definition

    ComponentDefinition definition

Template definition

<span id="org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

**Class [org.apache.struts.tiles.taglib.DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### controllerType

    String controllerType

Associated Controller type

------------------------------------------------------------------------

### controllerName

    String controllerName

Associated Controller name (classname or url)

------------------------------------------------------------------------

### role

    String role

Role associated to definition.

------------------------------------------------------------------------

### page

    String page

Uri of page assoicated to this definition.

<span id="org.apache.struts.tiles.taglib.GetAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.GetAttributeTag](org/apache/struts/tiles/taglib/GetAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attribute

    String attribute

------------------------------------------------------------------------

### role

    String role

Role attribute

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Do we ignore error if attribute is not found. Default value is `false`, which will throw an exception.

<span id="org.apache.struts.tiles.taglib.GetTag"></span>

**Class [org.apache.struts.tiles.taglib.GetTag](org/apache/struts/tiles/taglib/GetTag.html.md "class in org.apache.struts.tiles.taglib") extends [InsertTag](org/apache/struts/tiles/taglib/InsertTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="org.apache.struts.tiles.taglib.ImportAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.ImportAttributeTag](org/apache/struts/tiles/taglib/ImportAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### name

    String name

Class name of object.

------------------------------------------------------------------------

### scopeName

    String scopeName

The scope name.

------------------------------------------------------------------------

### scope

    int scope

The scope value.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute `ignore`. Default value is `false`, which throws an exception. Only "attribute not found" - errors are ignored.

<span id="org.apache.struts.tiles.taglib.InitDefinitionsTag"></span>

**Class [org.apache.struts.tiles.taglib.InitDefinitionsTag](org/apache/struts/tiles/taglib/InitDefinitionsTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filename

    String filename

------------------------------------------------------------------------

### classname

    String classname

<span id="org.apache.struts.tiles.taglib.InsertTag"></span>

**Class [org.apache.struts.tiles.taglib.InsertTag](org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib") extends [DefinitionTagSupport](org/apache/struts/tiles/taglib/DefinitionTagSupport.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### flush

    boolean flush

Flush attribute value.

------------------------------------------------------------------------

### name

    String name

Name to insert.

------------------------------------------------------------------------

### attribute

    String attribute

Name of attribute from which to read page name to include.

------------------------------------------------------------------------

### beanName

    String beanName

Name of bean used as entity to include.

------------------------------------------------------------------------

### beanProperty

    String beanProperty

Name of bean property, if any.

------------------------------------------------------------------------

### beanScope

    String beanScope

Scope of bean, if any.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute 'ignore'. Default value is false, which throw an exception. Only 'attribute not found' errors are ignored.

------------------------------------------------------------------------

### definitionName

    String definitionName

Name of component instance to include.

------------------------------------------------------------------------

### processEndTag

    boolean processEndTag

Does the end tag need to be processed. Default value is true. Boolean set in case of ignored errors.

------------------------------------------------------------------------

### cachedCurrentContext

    ComponentContext cachedCurrentContext

Current component context.

------------------------------------------------------------------------

### tagHandler

    InsertTag.TagHandler tagHandler

Final handler of tag methods.

------------------------------------------------------------------------

### pageContext

    PageContext pageContext

Trick to allows inner classes to access pageContext.

<span id="org.apache.struts.tiles.taglib.PutListTag"></span>

**Class [org.apache.struts.tiles.taglib.PutListTag](org/apache/struts/tiles/taglib/PutListTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributeName

    String attributeName

Name of this attribute.

------------------------------------------------------------------------

### list

    List<E> list

The list itself.

------------------------------------------------------------------------

### role

    String role

Role attribute.

<span id="org.apache.struts.tiles.taglib.PutTag"></span>

**Class [org.apache.struts.tiles.taglib.PutTag](org/apache/struts/tiles/taglib/PutTag.html.md "class in org.apache.struts.tiles.taglib") extends [BodyTagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/BodyTagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### attributeName

    String attributeName

Name of attribute to put in component context.

------------------------------------------------------------------------

### value

    Object value

Associated attribute value.

------------------------------------------------------------------------

### direct

    String direct

JSP Template compatibility.

------------------------------------------------------------------------

### valueType

    String valueType

Requested type for the value.

------------------------------------------------------------------------

### beanName

    String beanName

Bean name attribute.

------------------------------------------------------------------------

### beanProperty

    String beanProperty

Bean property attribute.

------------------------------------------------------------------------

### beanScope

    String beanScope

Bean scope attribute.

------------------------------------------------------------------------

### role

    String role

Role attribute.

------------------------------------------------------------------------

### realValue

    Object realValue

Cached real value computed from tag attributes.

------------------------------------------------------------------------

### body

    String body

The body content of this tag.

<span id="org.apache.struts.tiles.taglib.UseAttributeTag"></span>

**Class [org.apache.struts.tiles.taglib.UseAttributeTag](org/apache/struts/tiles/taglib/UseAttributeTag.html.md "class in org.apache.struts.tiles.taglib") extends [TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html?is-external=true "class or interface in javax.servlet.jsp.tagext") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### classname

    String classname

Class name of object.

------------------------------------------------------------------------

### scopeName

    String scopeName

The scope name.

------------------------------------------------------------------------

### scope

    int scope

The scope value.

------------------------------------------------------------------------

### attributeName

    String attributeName

The attribute name to be exposed.

------------------------------------------------------------------------

### isErrorIgnored

    boolean isErrorIgnored

Are errors ignored. This is the property for attribute 'ignore'. Default value is `false`, which throws an exception. Only "attribute not found" - errors are ignored.

------------------------------------------------------------------------

**Package** **org.apache.struts.tiles.xmlDefinition**

<span id="org.apache.struts.tiles.xmlDefinition.DefinitionsFactory"></span>

**Class [org.apache.struts.tiles.xmlDefinition.DefinitionsFactory](org/apache/struts/tiles/xmlDefinition/DefinitionsFactory.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### definitions

    Map<K,V> definitions

Underlying map containing all definitions.

<span id="org.apache.struts.tiles.xmlDefinition.FactorySet"></span>

**Class [org.apache.struts.tiles.xmlDefinition.FactorySet](org/apache/struts/tiles/xmlDefinition/FactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factories

    Map<K,V> factories

Loaded factories

<span id="org.apache.struts.tiles.xmlDefinition.I18nFactorySet"></span>

**Class [org.apache.struts.tiles.xmlDefinition.I18nFactorySet](org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [FactorySet](org/apache/struts/tiles/xmlDefinition/FactorySet.html "class in org.apache.struts.tiles.xmlDefinition") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### defaultFactory

    DefinitionsFactory defaultFactory

Default factory.

------------------------------------------------------------------------

### isValidatingParser

    boolean isValidatingParser

Do we want validating parser. Default is `false`. Can be set from servlet config file.

------------------------------------------------------------------------

### parserDetailLevel

    int parserDetailLevel

Parser detail level. Default is 0. Can be set from servlet config file.

------------------------------------------------------------------------

### filenames

    List<E> filenames

Names of files containing instances descriptions.

------------------------------------------------------------------------

### loaded

    Map<K,V> loaded

Collection of already loaded definitions set, referenced by their suffix.

<span id="org.apache.struts.tiles.xmlDefinition.XmlDefinition"></span>

**Class [org.apache.struts.tiles.xmlDefinition.XmlDefinition](org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md "class in org.apache.struts.tiles.xmlDefinition") extends [ComponentDefinition](org/apache/struts/tiles/ComponentDefinition.html "class in org.apache.struts.tiles") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### inherit

    String inherit

Extends attribute value.

------------------------------------------------------------------------

### isVisited

    boolean isVisited

Used for resolving inheritance.

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

<span id="org.apache.struts.validator.DynaValidatorActionForm"></span>

**Class [org.apache.struts.validator.DynaValidatorActionForm](org/apache/struts/validator/DynaValidatorActionForm.html.md "class in org.apache.struts.validator") extends [DynaValidatorForm](org/apache/struts/validator/DynaValidatorForm.html "class in org.apache.struts.validator") implements Serializable**

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

<span id="org.apache.struts.validator.ValidatorActionForm"></span>

**Class [org.apache.struts.validator.ValidatorActionForm](org/apache/struts/validator/ValidatorActionForm.html.md "class in org.apache.struts.validator") extends [ValidatorForm](org/apache/struts/validator/ValidatorForm.html "class in org.apache.struts.validator") implements Serializable**

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

**Package** **org.apache.strutsel.taglib.bean**

<span id="org.apache.strutsel.taglib.bean.ELIncludeTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELIncludeTag](org/apache/strutsel/taglib/bean/ELIncludeTag.html.md "class in org.apache.strutsel.taglib.bean") extends [IncludeTag](org/apache/struts/taglib/bean/IncludeTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### anchorExpr

    String anchorExpr

Instance variable mapped to "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hrefExpr

    String hrefExpr

Instance variable mapped to "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### transactionExpr

    String transactionExpr

Instance variable mapped to "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.bean.ELMessageTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELMessageTag](org/apache/strutsel/taglib/bean/ELMessageTag.html.md "class in org.apache.strutsel.taglib.bean") extends [MessageTag](org/apache/struts/taglib/bean/MessageTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### arg0Expr

    String arg0Expr

Instance variable mapped to "arg0" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### arg1Expr

    String arg1Expr

Instance variable mapped to "arg1" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### arg2Expr

    String arg2Expr

Instance variable mapped to "arg2" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### arg3Expr

    String arg3Expr

Instance variable mapped to "arg3" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### arg4Expr

    String arg4Expr

Instance variable mapped to "arg4" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### keyExpr

    String keyExpr

Instance variable mapped to "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.bean.ELPageTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELPageTag](org/apache/strutsel/taglib/bean/ELPageTag.html.md "class in org.apache.strutsel.taglib.bean") extends [PageTag](org/apache/struts/taglib/bean/PageTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.bean.ELResourceTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELResourceTag](org/apache/strutsel/taglib/bean/ELResourceTag.html.md "class in org.apache.strutsel.taglib.bean") extends [ResourceTag](org/apache/struts/taglib/bean/ResourceTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### inputExpr

    String inputExpr

Instance variable mapped to "input" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.bean.ELSizeTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELSizeTag](org/apache/strutsel/taglib/bean/ELSizeTag.html.md "class in org.apache.strutsel.taglib.bean") extends [SizeTag](org/apache/struts/taglib/bean/SizeTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collectionExpr

    String collectionExpr

Instance variable mapped to "collection" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.bean.ELStrutsTag"></span>

**Class [org.apache.strutsel.taglib.bean.ELStrutsTag](org/apache/strutsel/taglib/bean/ELStrutsTag.html.md "class in org.apache.strutsel.taglib.bean") extends [StrutsTag](org/apache/struts/taglib/bean/StrutsTag.html "class in org.apache.struts.taglib.bean") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### formBeanExpr

    String formBeanExpr

Instance variable mapped to "formBean" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### mappingExpr

    String mappingExpr

Instance variable mapped to "mapping" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

**Package** **org.apache.strutsel.taglib.html.md**

<span id="org.apache.strutsel.taglib.html.md.ELBaseTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELBaseTag](org/apache/strutsel/taglib/html/ELBaseTag.html "class in org.apache.strutsel.taglib.html") extends [BaseTag](org/apache/struts/taglib/html/BaseTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### targetExpr

    String targetExpr

Instance variable mapped to "target" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### serverExpr

    String serverExpr

Instance variable mapped to "server" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### refExpr

    String refExpr

Instance variable mapped to "ref" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELButtonTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELButtonTag](org/apache/strutsel/taglib/html/ELButtonTag.html "class in org.apache.strutsel.taglib.html") extends [ButtonTag](org/apache/struts/taglib/html/ButtonTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELCancelTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELCancelTag](org/apache/strutsel/taglib/html/ELCancelTag.html "class in org.apache.strutsel.taglib.html") extends [CancelTag](org/apache/struts/taglib/html/CancelTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskeyExpr

    String accesskeyExpr

Instance variable mapped to "accesskey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELCheckboxTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELCheckboxTag](org/apache/strutsel/taglib/html/ELCheckboxTag.html "class in org.apache.strutsel.taglib.html") extends [CheckboxTag](org/apache/struts/taglib/html/CheckboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskeyExpr

    String accesskeyExpr

Instance variable mapped to "accesskey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELErrorsTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELErrorsTag](org/apache/strutsel/taglib/html/ELErrorsTag.html "class in org.apache.strutsel.taglib.html") extends [ErrorsTag](org/apache/struts/taglib/html/ErrorsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### footerExpr

    String footerExpr

Instance variable mapped to "footer" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### prefixExpr

    String prefixExpr

Instance variable mapped to "prefix" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### suffixExpr

    String suffixExpr

Instance variable mapped to "suffix" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELFileTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELFileTag](org/apache/strutsel/taglib/html/ELFileTag.html "class in org.apache.strutsel.taglib.html") extends [FileTag](org/apache/struts/taglib/html/FileTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskeyExpr

    String accesskeyExpr

Instance variable mapped to "accesskey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### acceptExpr

    String acceptExpr

Instance variable mapped to "accept" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### maxlengthExpr

    String maxlengthExpr

Instance variable mapped to "maxlength" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### sizeExpr

    String sizeExpr

Instance variable mapped to "size" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELFormTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELFormTag](org/apache/strutsel/taglib/html/ELFormTag.html "class in org.apache.strutsel.taglib.html") extends [FormTag](org/apache/struts/taglib/html/FormTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### enctypeExpr

    String enctypeExpr

Instance variable mapped to "enctype" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### focusExpr

    String focusExpr

Instance variable mapped to "focus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### focusIndexExpr

    String focusIndexExpr

Instance variable mapped to "focusIndex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### methodExpr

    String methodExpr

Instance variable mapped to "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onresetExpr

    String onresetExpr

Instance variable mapped to "onreset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onsubmitExpr

    String onsubmitExpr

Instance variable mapped to "onsubmit" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### readonlyExpr

    String readonlyExpr

Instance variable mapped to "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scriptLanguageExpr

    String scriptLanguageExpr

Instance variable mapped to "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### targetExpr

    String targetExpr

Instance variable mapped to "target" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### acceptCharsetExpr

    String acceptCharsetExpr

Instance variable mapped to "acceptCharset" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELFrameTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELFrameTag](org/apache/strutsel/taglib/html/ELFrameTag.html "class in org.apache.strutsel.taglib.html") extends [FrameTag](org/apache/struts/taglib/html/FrameTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### moduleExpr

    String moduleExpr

Instance variable mapped to "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### anchorExpr

    String anchorExpr

Instance variable mapped to "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### frameborderExpr

    String frameborderExpr

Instance variable mapped to "frameborder" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### frameNameExpr

    String frameNameExpr

Instance variable mapped to "frameName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hrefExpr

    String hrefExpr

Instance variable mapped to "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### longdescExpr

    String longdescExpr

Instance variable mapped to "longdesc" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### marginheightExpr

    String marginheightExpr

Instance variable mapped to "marginheight" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### marginwidthExpr

    String marginwidthExpr

Instance variable mapped to "marginwidth" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### noresizeExpr

    String noresizeExpr

Instance variable mapped to "noresize" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramIdExpr

    String paramIdExpr

Instance variable mapped to "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramNameExpr

    String paramNameExpr

Instance variable mapped to "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramPropertyExpr

    String paramPropertyExpr

Instance variable mapped to "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramScopeExpr

    String paramScopeExpr

Instance variable mapped to "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scrollingExpr

    String scrollingExpr

Instance variable mapped to "scrolling" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### transactionExpr

    String transactionExpr

Instance variable mapped to "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELHiddenTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELHiddenTag](org/apache/strutsel/taglib/html/ELHiddenTag.html "class in org.apache.strutsel.taglib.html") extends [HiddenTag](org/apache/struts/taglib/html/HiddenTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskeyExpr

    String accesskeyExpr

Instance variable mapped to "accesskey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### writeExpr

    String writeExpr

Instance variable mapped to "write" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELHtmlTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELHtmlTag](org/apache/strutsel/taglib/html/ELHtmlTag.html "class in org.apache.strutsel.taglib.html") extends [HtmlTag](org/apache/struts/taglib/html/HtmlTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### .html.mdExpr

    String .html.mdExpr

Instance variable mapped to ".html.md" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELImageTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELImageTag](org/apache/strutsel/taglib/html/ELImageTag.html "class in org.apache.strutsel.taglib.html") extends [ImageTag](org/apache/struts/taglib/html/ImageTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### alignExpr

    String alignExpr

Instance variable mapped to "align" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### borderExpr

    String borderExpr

Instance variable mapped to "border" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### moduleExpr

    String moduleExpr

Instance variable mapped to "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageKeyExpr

    String pageKeyExpr

Instance variable mapped to "pageKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### srcExpr

    String srcExpr

Instance variable mapped to "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### srcKeyExpr

    String srcKeyExpr

Instance variable mapped to "srcKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELImgTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELImgTag](org/apache/strutsel/taglib/html/ELImgTag.html "class in org.apache.strutsel.taglib.html") extends [ImgTag](org/apache/struts/taglib/html/ImgTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### moduleExpr

    String moduleExpr

Instance variable mapped to "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### alignExpr

    String alignExpr

Instance variable mapped to "align" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### borderExpr

    String borderExpr

Instance variable mapped to "border" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### heightExpr

    String heightExpr

Instance variable mapped to "height" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hspaceExpr

    String hspaceExpr

Instance variable mapped to "hspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### imageNameExpr

    String imageNameExpr

Instance variable mapped to "imageName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ismapExpr

    String ismapExpr

Instance variable mapped to "ismap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramIdExpr

    String paramIdExpr

Instance variable mapped to "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageKeyExpr

    String pageKeyExpr

Instance variable mapped to "pageKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramNameExpr

    String paramNameExpr

Instance variable mapped to "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramPropertyExpr

    String paramPropertyExpr

Instance variable mapped to "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramScopeExpr

    String paramScopeExpr

Instance variable mapped to "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### srcExpr

    String srcExpr

Instance variable mapped to "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### srcKeyExpr

    String srcKeyExpr

Instance variable mapped to "srcKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### useLocalEncodingExpr

    String useLocalEncodingExpr

Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### usemapExpr

    String usemapExpr

Instance variable mapped to "usemap" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### vspaceExpr

    String vspaceExpr

Instance variable mapped to "vspace" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### widthExpr

    String widthExpr

Instance variable mapped to "width" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELJavascriptValidatorTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELJavascriptValidatorTag](org/apache/strutsel/taglib/html/ELJavascriptValidatorTag.html "class in org.apache.strutsel.taglib.html") extends [JavascriptValidatorTag](org/apache/struts/taglib/html/JavascriptValidatorTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cdataExpr

    String cdataExpr

Instance variable mapped to "cdata" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dynamicJavascriptExpr

    String dynamicJavascriptExpr

Instance variable mapped to "dynamicJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### formNameExpr

    String formNameExpr

Instance variable mapped to "formName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### methodExpr

    String methodExpr

Instance variable mapped to "method" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scriptLanguageExpr

    String scriptLanguageExpr

Instance variable mapped to "scriptLanguage" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### srcExpr

    String srcExpr

Instance variable mapped to "src" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### staticJavascriptExpr

    String staticJavascriptExpr

Instance variable mapped to "staticJavascript" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

###.html.mdCommentExpr

    String.html.mdCommentExpr

Instance variable mapped to .html.mdComment" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELLinkTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELLinkTag](org/apache/strutsel/taglib/html/ELLinkTag.html "class in org.apache.strutsel.taglib.html") extends [LinkTag](org/apache/struts/taglib/html/LinkTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### moduleExpr

    String moduleExpr

Instance variable mapped to "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### anchorExpr

    String anchorExpr

Instance variable mapped to "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hrefExpr

    String hrefExpr

Instance variable mapped to "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexIdExpr

    String indexIdExpr

Instance variable mapped to "indexId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### linkNameExpr

    String linkNameExpr

Instance variable mapped to "linkName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramIdExpr

    String paramIdExpr

Instance variable mapped to "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramNameExpr

    String paramNameExpr

Instance variable mapped to "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramPropertyExpr

    String paramPropertyExpr

Instance variable mapped to "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramScopeExpr

    String paramScopeExpr

Instance variable mapped to "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### targetExpr

    String targetExpr

Instance variable mapped to "target" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### transactionExpr

    String transactionExpr

Instance variable mapped to "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### useLocalEncodingExpr

    String useLocalEncodingExpr

Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELMessagesTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELMessagesTag](org/apache/strutsel/taglib/html/ELMessagesTag.html "class in org.apache.strutsel.taglib.html") extends [MessagesTag](org/apache/struts/taglib/html/MessagesTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### footerExpr

    String footerExpr

Instance variable mapped to "footer" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### messageExpr

    String messageExpr

Instance variable mapped to "message" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELMultiboxTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELMultiboxTag](org/apache/strutsel/taglib/html/ELMultiboxTag.html "class in org.apache.strutsel.taglib.html") extends [MultiboxTag](org/apache/struts/taglib/html/MultiboxTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELOptionsCollectionTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELOptionsCollectionTag](org/apache/strutsel/taglib/html/ELOptionsCollectionTag.html "class in org.apache.strutsel.taglib.html") extends [OptionsCollectionTag](org/apache/struts/taglib/html/OptionsCollectionTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### filterExpr

    String filterExpr

Instance variable mapped to "filter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### labelExpr

    String labelExpr

Instance variable mapped to "label" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELOptionsTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELOptionsTag](org/apache/strutsel/taglib/html/ELOptionsTag.html "class in org.apache.strutsel.taglib.html") extends [OptionsTag](org/apache/struts/taglib/html/OptionsTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collectionExpr

    String collectionExpr

Instance variable mapped to "collection" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### filterExpr

    String filterExpr

Instance variable mapped to "filter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### labelNameExpr

    String labelNameExpr

Instance variable mapped to "labelName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### labelPropertyExpr

    String labelPropertyExpr

Instance variable mapped to "labelProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELOptionTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELOptionTag](org/apache/strutsel/taglib/html/ELOptionTag.html "class in org.apache.strutsel.taglib.html") extends [OptionTag](org/apache/struts/taglib/html/OptionTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### filterExpr

    String filterExpr

Instance variable mapped to "filter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### keyExpr

    String keyExpr

Instance variable mapped to "key" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### localeExpr

    String localeExpr

Instance variable mapped to "locale" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELParamTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELParamTag](org/apache/strutsel/taglib/html/ELParamTag.html "class in org.apache.strutsel.taglib.html") extends [ParamTag](org/apache/struts/taglib/html/ParamTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELPasswordTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELPasswordTag](org/apache/strutsel/taglib/html/ELPasswordTag.html "class in org.apache.strutsel.taglib.html") extends [PasswordTag](org/apache/struts/taglib/html/PasswordTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### maxlengthExpr

    String maxlengthExpr

Instance variable mapped to "maxlength" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onselectExpr

    String onselectExpr

Instance variable mapped to "onselect" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### readonlyExpr

    String readonlyExpr

Instance variable mapped to "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### redisplayExpr

    String redisplayExpr

Instance variable mapped to "redisplay" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### sizeExpr

    String sizeExpr

Instance variable mapped to "size" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELRadioTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELRadioTag](org/apache/strutsel/taglib/html/ELRadioTag.html "class in org.apache.strutsel.taglib.html") extends [RadioTag](org/apache/struts/taglib/html/RadioTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### idNameExpr

    String idNameExpr

Instance variable mapped to "idName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELResetTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELResetTag](org/apache/strutsel/taglib/html/ELResetTag.html "class in org.apache.strutsel.taglib.html") extends [ResetTag](org/apache/struts/taglib/html/ResetTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELRewriteTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELRewriteTag](org/apache/strutsel/taglib/html/ELRewriteTag.html "class in org.apache.strutsel.taglib.html") extends [RewriteTag](org/apache/struts/taglib/html/RewriteTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### moduleExpr

    String moduleExpr

Instance variable mapped to "module" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### anchorExpr

    String anchorExpr

Instance variable mapped to "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hrefExpr

    String hrefExpr

Instance variable mapped to "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramIdExpr

    String paramIdExpr

Instance variable mapped to "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramNameExpr

    String paramNameExpr

Instance variable mapped to "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramPropertyExpr

    String paramPropertyExpr

Instance variable mapped to "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramScopeExpr

    String paramScopeExpr

Instance variable mapped to "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### transactionExpr

    String transactionExpr

Instance variable mapped to "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### useLocalEncodingExpr

    String useLocalEncodingExpr

Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELSelectTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELSelectTag](org/apache/strutsel/taglib/html/ELSelectTag.html "class in org.apache.strutsel.taglib.html") extends [SelectTag](org/apache/struts/taglib/html/SelectTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### multipleExpr

    String multipleExpr

Instance variable mapped to "multiple" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### sizeExpr

    String sizeExpr

Instance variable mapped to "size" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELSubmitTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELSubmitTag](org/apache/strutsel/taglib/html/ELSubmitTag.html "class in org.apache.strutsel.taglib.html") extends [SubmitTag](org/apache/struts/taglib/html/SubmitTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELTextareaTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELTextareaTag](org/apache/strutsel/taglib/html/ELTextareaTag.html "class in org.apache.strutsel.taglib.html") extends [TextareaTag](org/apache/struts/taglib/html/TextareaTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessKeyExpr

    String accessKeyExpr

Instance variable mapped to "accessKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### colsExpr

    String colsExpr

Instance variable mapped to "cols" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onselectExpr

    String onselectExpr

Instance variable mapped to "onselect" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### readonlyExpr

    String readonlyExpr

Instance variable mapped to "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### rowsExpr

    String rowsExpr

Instance variable mapped to "rows" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### sizeExpr

    String sizeExpr

Instance variable mapped to "size" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.html.md.ELTextTag"></span>

**Class [org.apache.strutsel.taglib.html.md.ELTextTag](org/apache/strutsel/taglib/html/ELTextTag.html "class in org.apache.strutsel.taglib.html") extends [TextTag](org/apache/struts/taglib/html/TextTag.html "class in org.apache.struts.taglib.html") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accesskeyExpr

    String accesskeyExpr

Instance variable mapped to "accesskey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altExpr

    String altExpr

Instance variable mapped to "alt" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### altKeyExpr

    String altKeyExpr

Instance variable mapped to "altKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### bundleExpr

    String bundleExpr

Instance variable mapped to "bundle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### dirExpr

    String dirExpr

Instance variable mapped to "dir" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### disabledExpr

    String disabledExpr

Instance variable mapped to "disabled" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorKeyExpr

    String errorKeyExpr

Instance variable mapped to "errorKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleExpr

    String errorStyleExpr

Instance variable mapped to "errorStyle" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleClassExpr

    String errorStyleClassExpr

Instance variable mapped to "errorStyleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### errorStyleIdExpr

    String errorStyleIdExpr

Instance variable mapped to "errorStyleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexedExpr

    String indexedExpr

Instance variable mapped to "indexed" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### langExpr

    String langExpr

Instance variable mapped to "lang" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### maxlengthExpr

    String maxlengthExpr

Instance variable mapped to "maxlength" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onblurExpr

    String onblurExpr

Instance variable mapped to "onblur" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onchangeExpr

    String onchangeExpr

Instance variable mapped to "onchange" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onclickExpr

    String onclickExpr

Instance variable mapped to "onclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ondblclickExpr

    String ondblclickExpr

Instance variable mapped to "ondblclick" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onfocusExpr

    String onfocusExpr

Instance variable mapped to "onfocus" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeydownExpr

    String onkeydownExpr

Instance variable mapped to "onkeydown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeypressExpr

    String onkeypressExpr

Instance variable mapped to "onkeypress" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onkeyupExpr

    String onkeyupExpr

Instance variable mapped to "onkeyup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousedownExpr

    String onmousedownExpr

Instance variable mapped to "onmousedown" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmousemoveExpr

    String onmousemoveExpr

Instance variable mapped to "onmousemove" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoutExpr

    String onmouseoutExpr

Instance variable mapped to "onmouseout" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseoverExpr

    String onmouseoverExpr

Instance variable mapped to "onmouseover" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onmouseupExpr

    String onmouseupExpr

Instance variable mapped to "onmouseup" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### onselectExpr

    String onselectExpr

Instance variable mapped to "onselect" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### readonlyExpr

    String readonlyExpr

Instance variable mapped to "readonly" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleExpr

    String styleExpr

Instance variable mapped to "style" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### sizeExpr

    String sizeExpr

Instance variable mapped to "size" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleClassExpr

    String styleClassExpr

Instance variable mapped to "styleClass" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### styleIdExpr

    String styleIdExpr

Instance variable mapped to "styleId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### tabindexExpr

    String tabindexExpr

Instance variable mapped to "tabindex" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleExpr

    String titleExpr

Instance variable mapped to "title" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### titleKeyExpr

    String titleKeyExpr

Instance variable mapped to "titleKey" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

**Package** **org.apache.strutsel.taglib.logic**

<span id="org.apache.strutsel.taglib.logic.ELForwardTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELForwardTag](org/apache/strutsel/taglib/logic/ELForwardTag.html.md "class in org.apache.strutsel.taglib.logic") extends [ForwardTag](org/apache/struts/taglib/logic/ForwardTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELIterateTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELIterateTag](org/apache/strutsel/taglib/logic/ELIterateTag.html.md "class in org.apache.strutsel.taglib.logic") extends [IterateTag](org/apache/struts/taglib/logic/IterateTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### collectionExpr

    String collectionExpr

Instance variable mapped to "collection" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### indexIdExpr

    String indexIdExpr

Instance variable mapped to "indexId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### lengthExpr

    String lengthExpr

Instance variable mapped to "length" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### offsetExpr

    String offsetExpr

Instance variable mapped to "offset" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### typeExpr

    String typeExpr

Instance variable mapped to "type" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELMatchTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELMatchTag](org/apache/strutsel/taglib/logic/ELMatchTag.html.md "class in org.apache.strutsel.taglib.logic") extends [MatchTag](org/apache/struts/taglib/logic/MatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookieExpr

    String cookieExpr

Instance variable mapped to "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### locationExpr

    String locationExpr

Instance variable mapped to "location" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### parameterExpr

    String parameterExpr

Instance variable mapped to "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### expr

    String expr

String value of expression to be evaluated.

------------------------------------------------------------------------

### exprValue

    String exprValue

Evaluated value of expression.

<span id="org.apache.strutsel.taglib.logic.ELMessagesNotPresentTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELMessagesNotPresentTag](org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html.md "class in org.apache.strutsel.taglib.logic") extends [MessagesNotPresentTag](org/apache/struts/taglib/logic/MessagesNotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### messageExpr

    String messageExpr

Instance variable mapped to "message" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELMessagesPresentTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELMessagesPresentTag](org/apache/strutsel/taglib/logic/ELMessagesPresentTag.html.md "class in org.apache.strutsel.taglib.logic") extends [MessagesPresentTag](org/apache/struts/taglib/logic/MessagesPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### messageExpr

    String messageExpr

Instance variable mapped to "message" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELNotMatchTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELNotMatchTag](org/apache/strutsel/taglib/logic/ELNotMatchTag.html.md "class in org.apache.strutsel.taglib.logic") extends [NotMatchTag](org/apache/struts/taglib/logic/NotMatchTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookieExpr

    String cookieExpr

Instance variable mapped to "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### locationExpr

    String locationExpr

Instance variable mapped to "location" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### parameterExpr

    String parameterExpr

Instance variable mapped to "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### expr

    String expr

String value of expression to be evaluated.

------------------------------------------------------------------------

### exprValue

    String exprValue

Evaluated value of expression.

<span id="org.apache.strutsel.taglib.logic.ELNotPresentTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELNotPresentTag](org/apache/strutsel/taglib/logic/ELNotPresentTag.html.md "class in org.apache.strutsel.taglib.logic") extends [NotPresentTag](org/apache/struts/taglib/logic/NotPresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookieExpr

    String cookieExpr

Instance variable mapped to "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### parameterExpr

    String parameterExpr

Instance variable mapped to "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### userExpr

    String userExpr

Instance variable mapped to "user" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELPresentTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELPresentTag](org/apache/strutsel/taglib/logic/ELPresentTag.html.md "class in org.apache.strutsel.taglib.logic") extends [PresentTag](org/apache/struts/taglib/logic/PresentTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### cookieExpr

    String cookieExpr

Instance variable mapped to "cookie" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### headerExpr

    String headerExpr

Instance variable mapped to "header" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### parameterExpr

    String parameterExpr

Instance variable mapped to "parameter" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### userExpr

    String userExpr

Instance variable mapped to "user" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.logic.ELRedirectTag"></span>

**Class [org.apache.strutsel.taglib.logic.ELRedirectTag](org/apache/strutsel/taglib/logic/ELRedirectTag.html.md "class in org.apache.strutsel.taglib.logic") extends [RedirectTag](org/apache/struts/taglib/logic/RedirectTag.html "class in org.apache.struts.taglib.logic") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### actionExpr

    String actionExpr

Instance variable mapped to "action" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### anchorExpr

    String anchorExpr

Instance variable mapped to "anchor" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### forwardExpr

    String forwardExpr

Instance variable mapped to "forward" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### hrefExpr

    String hrefExpr

Instance variable mapped to "href" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramIdExpr

    String paramIdExpr

Instance variable mapped to "paramId" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramNameExpr

    String paramNameExpr

Instance variable mapped to "paramName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramPropertyExpr

    String paramPropertyExpr

Instance variable mapped to "paramProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### paramScopeExpr

    String paramScopeExpr

Instance variable mapped to "paramScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### propertyExpr

    String propertyExpr

Instance variable mapped to "property" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### transactionExpr

    String transactionExpr

Instance variable mapped to "transaction" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### useLocalEncodingExpr

    String useLocalEncodingExpr

Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

**Package** **org.apache.strutsel.taglib.tiles**

<span id="org.apache.strutsel.taglib.tiles.ELAddTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELAddTag](org/apache/strutsel/taglib/tiles/ELAddTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [AddTag](org/apache/struts/tiles/taglib/AddTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### contentExpr

    String contentExpr

Instance variable mapped to "content" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### directExpr

    String directExpr

Instance variable mapped to "direct" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### typeExpr

    String typeExpr

Instance variable mapped to "type" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanNameExpr

    String beanNameExpr

Instance variable mapped to "beanName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanPropertyExpr

    String beanPropertyExpr

Instance variable mapped to "beanProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanScopeExpr

    String beanScopeExpr

Instance variable mapped to "beanScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELDefinitionTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELDefinitionTag](org/apache/strutsel/taglib/tiles/ELDefinitionTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [DefinitionTag](org/apache/struts/tiles/taglib/DefinitionTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### templateExpr

    String templateExpr

Instance variable mapped to "template" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### extendsExpr

    String extendsExpr

Instance variable mapped to "extends" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELGetAttributeTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELGetAttributeTag](org/apache/strutsel/taglib/tiles/ELGetAttributeTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [GetAttributeTag](org/apache/struts/tiles/taglib/GetAttributeTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ignoreExpr

    String ignoreExpr

Instance variable mapped to "ignore" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELGetTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELGetTag](org/apache/strutsel/taglib/tiles/ELGetTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [GetTag](org/apache/struts/tiles/taglib/GetTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ignoreExpr

    String ignoreExpr

Instance variable mapped to "ignore" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### flushExpr

    String flushExpr

Instance variable mapped to "flush" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELImportAttributeTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELImportAttributeTag](org/apache/strutsel/taglib/tiles/ELImportAttributeTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [ImportAttributeTag](org/apache/struts/tiles/taglib/ImportAttributeTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ignoreExpr

    String ignoreExpr

Instance variable mapped to "ignore" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELInitDefinitionsTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELInitDefinitionsTag](org/apache/strutsel/taglib/tiles/ELInitDefinitionsTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [InitDefinitionsTag](org/apache/struts/tiles/taglib/InitDefinitionsTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### fileExpr

    String fileExpr

Instance variable mapped to "file" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### classnameExpr

    String classnameExpr

Instance variable mapped to "classname" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELInsertTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELInsertTag](org/apache/strutsel/taglib/tiles/ELInsertTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [InsertTag](org/apache/struts/tiles/taglib/InsertTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### templateExpr

    String templateExpr

Instance variable mapped to "template" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### componentExpr

    String componentExpr

Instance variable mapped to "component" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### pageExpr

    String pageExpr

Instance variable mapped to "page" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### definitionExpr

    String definitionExpr

Instance variable mapped to "definition" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### attributeExpr

    String attributeExpr

Instance variable mapped to "attribute" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanNameExpr

    String beanNameExpr

Instance variable mapped to "beanName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanPropertyExpr

    String beanPropertyExpr

Instance variable mapped to "beanProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanScopeExpr

    String beanScopeExpr

Instance variable mapped to "beanScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### flushExpr

    String flushExpr

Instance variable mapped to "flush" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ignoreExpr

    String ignoreExpr

(Mapping set in associated BeanInfo class.) Instance variable mapped to "ignore" tag attribute.

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### controllerUrlExpr

    String controllerUrlExpr

Instance variable mapped to "controllerUrl" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### controllerClassExpr

    String controllerClassExpr

Instance variable mapped to "controllerClass" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELPutListTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELPutListTag](org/apache/strutsel/taglib/tiles/ELPutListTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [PutListTag](org/apache/struts/tiles/taglib/PutListTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELPutTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELPutTag](org/apache/strutsel/taglib/tiles/ELPutTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [PutTag](org/apache/struts/tiles/taglib/PutTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### valueExpr

    String valueExpr

Instance variable mapped to "value" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### contentExpr

    String contentExpr

Instance variable mapped to "content" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### directExpr

    String directExpr

Instance variable mapped to "direct" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### typeExpr

    String typeExpr

Instance variable mapped to "type" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanNameExpr

    String beanNameExpr

Instance variable mapped to "beanName" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanPropertyExpr

    String beanPropertyExpr

Instance variable mapped to "beanProperty" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### beanScopeExpr

    String beanScopeExpr

Instance variable mapped to "beanScope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### roleExpr

    String roleExpr

Instance variable mapped to "role" tag attribute. (Mapping set in associated BeanInfo class.)

<span id="org.apache.strutsel.taglib.tiles.ELUseAttributeTag"></span>

**Class [org.apache.strutsel.taglib.tiles.ELUseAttributeTag](org/apache/strutsel/taglib/tiles/ELUseAttributeTag.html.md "class in org.apache.strutsel.taglib.tiles") extends [UseAttributeTag](org/apache/struts/tiles/taglib/UseAttributeTag.html "class in org.apache.struts.tiles.taglib") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### idExpr

    String idExpr

Instance variable mapped to "id" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### classnameExpr

    String classnameExpr

Instance variable mapped to "classname" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### scopeExpr

    String scopeExpr

Instance variable mapped to "scope" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### nameExpr

    String nameExpr

Instance variable mapped to "name" tag attribute. (Mapping set in associated BeanInfo class.)

------------------------------------------------------------------------

### ignoreExpr

    String ignoreExpr

Instance variable mapped to "ignore" tag attribute. (Mapping set in associated BeanInfo class.)

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
