**`struts-config_1_3.dtd`**: [Elements](struts-config_1_3.dtd.html.md) - [Entities](struts-config_1_3.dtd.entities.html) - [Source](struts-config_1_3.dtd.org.html) | [Intro](intro.html) - [Index](elementsIndex.html)
 [FRAMES](index.html.md) / [NO FRAMES](struts-config_1_3.dtd.html)

struts-config\_1\_3.dtd
=======================

Licensed to the Apache Software Foundation (ASF) under one or more contributor license agreements. See the NOTICE file distributed with this work for additional information regarding copyright ownership. The ASF licenses this file to You under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

|-------------------|--------------|
| \<struts-config\> | Root element |

The "struts-config" element is the root of the configuration file hierarchy, and contains nested elements for all of the other configuration settings.

> \<struts-config\>'s children
> Name
> Cardinality
> [action-mappings](#action-mappings)
> One or none
> [controller](#controller)
> One or none
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [form-beans](#form-beans)
> One or none
> [global-exceptions](#global-exceptions)
> One or none
> [global-forwards](#global-forwards)
> One or none
> [message-resources](#message-resources)
> Any number
> [plug-in](#plug-in)
> Any number
> \<struts-config\>'s attributes
> Name
> Values
> Default
> [id](#struts-config_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([display-name](#display-name)?, [description](#description)?, [form-beans](#form-beans)?, [global-exceptions](#global-exceptions)?, [global-forwards](#global-forwards)?, [action-mappings](#action-mappings)?, [controller](#controller)?, [message-resources](#message-resources)\*, [plug-in](#plug-in)\*)

|-----|----------------------------------------------|
| @id | Attribute of [struts-config](#struts-config) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------------|------------------------------------------|
| \<form-beans\> | Child of [struts-config](#struts-config) |

The "form-beans" element describes the set of form bean descriptors for this module. The following attributes are defined:

type Fully qualified Java class to use when instantiating ActionFormBean objects. If specified, the object must be a subclass of the default class type.

WARNING: For Struts 1.0, this value is ignored. You can set the default implementation class name with the "formBean" initialization parameter to the Struts controller servlet.

> \<form-beans\>'s children
> Name
> Cardinality
> [form-bean](#form-bean)
> Any number
> \<form-beans\>'s attributes
> Name
> Values
> Default
> [id](#form-beans_id)
> *Match the ID rules.*
> [type](#form-beans_type)

<span class="inTextTitle">Element's model:</span>

([form-bean](#form-bean)\*)

|-----|----------------------------------------|
| @id | Attribute of [form-beans](#form-beans) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|----------------------------------------|
| @type | Attribute of [form-beans](#form-beans) |

Sorry, no documentation.

|---------------|------------------------------------|
| \<form-bean\> | Child of [form-beans](#form-beans) |

The "form-bean" element describes an ActionForm subclass [org.apache.struts.action.ActionForm] that can be referenced by an "action" element.

The "form-bean" element describes a particular form bean, which is a JavaBean that implements the org.apache.struts.action.ActionForm class. The following attributes are defined:

className The configuration bean for this form bean object. If specified, the object must be a subclass of the default configuration bean. ["org.apache.struts.config.FormBeanConfig"]

extends The name of the form bean that this bean will inherit configuration information from.

name The unique identifier for this form bean. Referenced by the \<action\> element to specify which form bean to use with its request.

type Fully qualified Java class name of the ActionForm subclass to use with this form bean.

enhanced Reserved for future use.

> \<form-bean\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [form-property](#form-property)
> Any number
> [icon](#icon)
> One or none
> [set-property](#set-property)
> Any number
> \<form-bean\>'s attributes
> Name
> Values
> Default
> [className](#form-bean_className)
> [enhanced](#form-bean_enhanced)
> true, false, yes, no
> [extends](#form-bean_extends)
> [id](#form-bean_id)
> *Match the ID rules.*
> [name](#form-bean_name)
> [type](#form-bean_type)

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*, [form-property](#form-property)\*)

|-----|--------------------------------------|
| @id | Attribute of [form-bean](#form-bean) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|--------------------------------------|
| @className | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

|-----------|--------------------------------------|
| @enhanced | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|----------|--------------------------------------|
| @extends | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

|-------|--------------------------------------|
| @name | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|--------------------------------------|
| @type | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

|-------------------|----------------------------------|
| \<form-property\> | Child of [form-bean](#form-bean) |

The "form-property" element describes a JavaBean property that can be used to configure an instance of a DynaActionForm or a subclass thereof. This element is only utilized when the "type" attribute of the enclosing "form-bean" element is [org.apache.struts.action.DynaActionForm] or a subclass of DynaActionForm. If a custom DynaActionForm subclass is used, then the "dynamic" attribute of the enclosing \<form-bean\> element must be set to "true". Since Struts 1.1.

className The configuration bean for this form property object. If specified, the object must be a subclass of the default configuration bean. ["org.apache.struts.config.FormPropertyConfig"]

initial String representation of the initial value for this property. If not specified, primitives will be initialized to zero and objects initialized to the zero-argument instantiation of that object class. For example, Strings will be initialized to ""

name The name of the JavaBean property described by this element.

reset The flag that indicates when this property should be reset to its "initial" value when the form's "reset()" method is called. If this is set to "true", the property is always reset when "reset()" is called. This can also be set to one or more HTTP methods, such as GET or POST. In such a case, the property will be reset only when the HTTP method used for the request being processed is included in this attribute's value(s). Multiple HTTP methods can be specified by separating them with whitespace or commas.

size The number of array elements to create if the value of the "type" attribute specifies an array, but there is no value specified for the "initial" attribute.

type Fully qualified Java class name of the field underlying this property, optionally followed by "[]" to indicate that the field is indexed.

> \<form-property\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<form-property\>'s attributes
> Name
> Values
> Default
> [className](#form-property_className)
> [initial](#form-property_initial)
> [name](#form-property_name)
> [reset](#form-property_reset)
> true, false, yes, no
> [size](#form-property_size)
> [type](#form-property_type)

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|------------|----------------------------------------------|
| @className | Attribute of [form-property](#form-property) |

Sorry, no documentation.

|----------|----------------------------------------------|
| @initial | Attribute of [form-property](#form-property) |

Sorry, no documentation.

|-------|----------------------------------------------|
| @name | Attribute of [form-property](#form-property) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|--------|----------------------------------------------|
| @reset | Attribute of [form-property](#form-property) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|-------|----------------------------------------------|
| @size | Attribute of [form-property](#form-property) |

Sorry, no documentation.

|-------|----------------------------------------------|
| @type | Attribute of [form-property](#form-property) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-----------------------|------------------------------------------|
| \<global-exceptions\> | Child of [struts-config](#struts-config) |

The "global-exceptions" element describes a set of exceptions that might be thrown by an Action object. The handling of individual exception types is configured through nested exception elements. An \<action\> element may override a global exception handler by registering a local exception handler for the same exception type. Since Struts 1.1.

> \<global-exceptions\>'s children
> Name
> Cardinality
> [exception](#exception)
> Any number
> \<global-exceptions\>'s attributes
> Name
> Values
> Default
> [id](#global-exceptions_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([exception](#exception)\*)

|-----|------------------------------------------------------|
| @id | Attribute of [global-exceptions](#global-exceptions) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|---------------|---------------------------------------------------------------------|
| \<exception\> | Child of [action](#action), [global-exceptions](#global-exceptions) |

The "exception" element registers an ExceptionHandler for an exception type. The following attributes are defined:

bundle Servlet context attribute for the message resources bundle associated with this handler. The default attribute is the value specified by the string constant declared at Globals.MESSAGES\_KEY. [org.apache.struts.Globals.MESSAGES\_KEY]

className The configuration bean for this ExceptionHandler object. If specified, className must be a subclass of the default configuration bean ["org.apache.struts.config.ExceptionConfig"]

extends The name of the exception handler that this will inherit configuration information from.

handler Fully qualified Java class name for this exception handler. ["org.apache.struts.action.ExceptionHandler"]

key The key to use with this handler's message resource bundle that will retrieve the error message template for this exception.

path The module-relative URI to the resource that will complete the request/response if this exception occurs.

scope The context ("request" or "session") that is used to access the ActionMessage object [org.apache.struts.action.ActionMessage] for this exception.

type Fully qualified Java class name of the exception type to register with this handler.

> \<exception\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [icon](#icon)
> One or none
> [set-property](#set-property)
> Any number
> \<exception\>'s attributes
> Name
> Values
> Default
> [bundle](#exception_bundle)
> [className](#exception_className)
> [extends](#exception_extends)
> [handler](#exception_handler)
> [id](#exception_id)
> *Match the ID rules.*
> [key](#exception_key)
> [path](#exception_path)
> [scope](#exception_scope)
> [type](#exception_type)

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*)

|-----|--------------------------------------|
| @id | Attribute of [exception](#exception) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|---------|--------------------------------------|
| @bundle | Attribute of [exception](#exception) |

Sorry, no documentation.

|------------|--------------------------------------|
| @className | Attribute of [exception](#exception) |

Sorry, no documentation.

|----------|--------------------------------------|
| @extends | Attribute of [exception](#exception) |

Sorry, no documentation.

|----------|--------------------------------------|
| @handler | Attribute of [exception](#exception) |

Sorry, no documentation.

|------|--------------------------------------|
| @key | Attribute of [exception](#exception) |

Sorry, no documentation.

|-------|--------------------------------------|
| @path | Attribute of [exception](#exception) |

Sorry, no documentation.

|--------|--------------------------------------|
| @scope | Attribute of [exception](#exception) |

Sorry, no documentation.

|-------|--------------------------------------|
| @type | Attribute of [exception](#exception) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|---------------------|------------------------------------------|
| \<global-forwards\> | Child of [struts-config](#struts-config) |

The "global-forwards" element describes a set of ActionForward objects [org.apache.struts.action.ActionForward] that are available to all Action objects as a return value. The individual ActionForwards are configured through nested \<forward\> elements. An \<action\> element may override a global forward by defining a local \<forward\> of the same name.

type Fully qualified Java class to use when instantiating ActionForward objects. If specified, the object must be a subclass of the default class type.

WARNING: For Struts 1.0, this value is ignored. You can set the default implementation class name with the "forward" initialization parameter to the Struts controller servlet.

> \<global-forwards\>'s children
> Name
> Cardinality
> [forward](#forward)
> Any number
> \<global-forwards\>'s attributes
> Name
> Values
> Default
> [id](#global-forwards_id)
> *Match the ID rules.*
> [type](#global-forwards_type)

<span class="inTextTitle">Element's model:</span>

([forward](#forward)\*)

|-----|--------------------------------------------------|
| @id | Attribute of [global-forwards](#global-forwards) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|--------------------------------------------------|
| @type | Attribute of [global-forwards](#global-forwards) |

Sorry, no documentation.

|-------------|-----------------------------------------------------------------|
| \<forward\> | Child of [action](#action), [global-forwards](#global-forwards) |

The "forward" element describes an ActionForward that is to be made available to an Action as a return value. An ActionForward is referenced by a logical name and encapsulates a URI. A "forward" element may be used to describe both global and local ActionForwards. Global forwards are available to all the Action objects in the module. Local forwards can be nested within an \<action\> element and only available to an Action object when it is invoked through that ActionMapping.

catalog The name of a commons-chain catalog in which to look up a command to be executed as part of servicing this request. Only meaningful if "command" is also specified.

className Fully qualified Java class name of ActionForward subclass to use for this object. ["org.apache.struts.action.ActionForward"]

command The name of a commons-chain command which should be looked up and executed as part of servicing this request.

extends The name of the forward configuration that this will inherit configuration information from.

module The module prefix to use with this path. This value should begin with a slash ("/").

name The unique identifier for this forward. Referenced by the Action object at runtime to select - by its logical name - the resource that should complete the request/response.

path The module-relative path to the resources that is encapsulated by the logical name of this ActionForward. This value should begin with a slash ("/") character.

redirect Set to "true" if a redirect instruction should be issued to the user-agent so that a new request is issued for this forward's resource. If true, RequestDispatcher.Redirect is called. If "false", RequestDispatcher.forward is called instead. [false]

> \<forward\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [icon](#icon)
> One or none
> [set-property](#set-property)
> Any number
> \<forward\>'s attributes
> Name
> Values
> Default
> [catalog](#forward_catalog)
> [className](#forward_className)
> [command](#forward_command)
> [extends](#forward_extends)
> [id](#forward_id)
> *Match the ID rules.*
> [module](#forward_module)
> [name](#forward_name)
> [path](#forward_path)
> [redirect](#forward_redirect)
> true, false, yes, no

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*)

|-----|----------------------------------|
| @id | Attribute of [forward](#forward) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------|----------------------------------|
| @catalog | Attribute of [forward](#forward) |

Sorry, no documentation.

|------------|----------------------------------|
| @className | Attribute of [forward](#forward) |

Sorry, no documentation.

|----------|----------------------------------|
| @command | Attribute of [forward](#forward) |

Sorry, no documentation.

|----------|----------------------------------|
| @extends | Attribute of [forward](#forward) |

Sorry, no documentation.

|---------|----------------------------------|
| @module | Attribute of [forward](#forward) |

Sorry, no documentation.

|-------|----------------------------------|
| @name | Attribute of [forward](#forward) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|----------------------------------|
| @path | Attribute of [forward](#forward) |

Sorry, no documentation.

|-----------|----------------------------------|
| @redirect | Attribute of [forward](#forward) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|---------------------|------------------------------------------|
| \<action-mappings\> | Child of [struts-config](#struts-config) |

The "action-mappings" element describes a set of ActionMapping objects [org.apache.struts.action.ActionMapping] that are available to process requests matching the url-pattern our ActionServlet registered with the container. The individual ActionMappings are configured through nested \<action\> elements. The following attributes are defined:

type Fully qualified Java class to use when instantiating ActionMapping objects. If specified, the object must be a subclass of the default class type.

WARNING: For Struts 1.0, this value is ignored. You can set the default implementation class name with the "mapping" initialization parameter to the Struts controller servlet.

> \<action-mappings\>'s children
> Name
> Cardinality
> [action](#action)
> Any number
> \<action-mappings\>'s attributes
> Name
> Values
> Default
> [id](#action-mappings_id)
> *Match the ID rules.*
> [type](#action-mappings_type)

<span class="inTextTitle">Element's model:</span>

([action](#action)\*)

|-----|--------------------------------------------------|
| @id | Attribute of [action-mappings](#action-mappings) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|--------------------------------------------------|
| @type | Attribute of [action-mappings](#action-mappings) |

Sorry, no documentation.

|------------|----------------------------------------------|
| \<action\> | Child of [action-mappings](#action-mappings) |

The "action" element describes an ActionMapping object that is to be used to process a request for a specific module-relative URI. The following attributes are defined:

attribute Name of the request-scope or session-scope attribute that is used to access our ActionForm bean, if it is other than the bean's specified "name". Optional if "name" is specified, else not valid.

cancellable Set to "true" if the Action can be cancelled. By default, when an Action is cancelled, validation is bypassed and the Action should not execute the business operation. If a request tries to cancel an Action when cancellable is not set, a "InvalidCancelException" is thrown. [false]

catalog The name of a commons-chain catalog in which to look up a command to be executed as part of servicing this request. Only meaningful if "command" is also specified.

className The fully qualified Java class name of the ActionMapping subclass to use for this action mapping object. Defaults to the type specified by the enclosing \<action-mappings\> element or to "org.apache.struts.action.ActionMapping" if not specified. ["org.apache.struts.action.ActionMapping"]

command The name of a commons-chain command which should be looked up and executed as part of servicing this request.

extends The path of the action mapping configuration that this will inherit configuration information from.

forward Module-relative path of the servlet or other resource that will process this request, instead of the Action class specified by "type". The path WILL NOT be processed through the "forwardPattern" attribute that is configured on the "controller" element for this module. Exactly one of "forward", "include", or "type" must be specified.

include Module-relative path of the servlet or other resource that will process this request, instead of the Action class specified by "type". The path WILL NOT be processed through the "forwardPattern" attribute that is configured on the "controller" element for this module. Exactly one of "forward", "include", or "type" must be specified.

input Module-relative path of the action or other resource to which control should be returned if a validation error is encountered. Valid only when "name" is specified. Required if "name" is specified and the input bean returns validation errors. Optional if "name" is specified and the input bean does not return validation errors.

name Name of the form bean, if any, that is associated with this action mapping.

parameter General-purpose configuration parameter that can be used to pass extra information to the Action object selected by this action mapping.

path The module-relative path of the submitted request, starting with a "/" character, and without the filename extension if extension mapping is used.

NOTE: Do \*not\* include a period in your path name, because it will look like a filename extension and cause your Action to not be located.

prefix Prefix used to match request parameter names to ActionForm property names, if any. Optional if "name" is specified, else not allowed.

roles Comma-delimited list of security role names that are allowed access to this ActionMapping object. Since Struts 1.1.

scope The context ("request" or "session") that is used to access our ActionForm bean, if any. Optional if "name" is specified, else not valid. [session]

suffix Suffix used to match request parameter names to ActionForm bean property names, if any. Optional if "name" is specified, else not valid.

type Fully qualified Java class name of the Action subclass [org.apache.struts.action.Action] that will process requests for this action mapping. Not valid if either the "forward" or "include" attribute is specified. Exactly one of "forward", "include", or "type" must be specified.

unknown Set to "true" if this object should be configured as the default action mapping for this module. If a request does not match another object, it will be passed to the ActionMapping object with unknown set to "true". Only one ActionMapping can be marked as "unknown" within a module. [false]

validate Set to "true" if the validate method of the ActionForm bean should be called prior to calling the Action object for this action mapping, or set to "false" if you do not want the validate method called. [true]

> \<action\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [exception](#exception)
> Any number
> [forward](#forward)
> Any number
> [icon](#icon)
> One or none
> [set-property](#set-property)
> Any number
> \<action\>'s attributes
> Name
> Values
> Default
> [attribute](#action_attribute)
> [cancellable](#action_cancellable)
> true, false, yes, no
> [catalog](#action_catalog)
> [className](#action_className)
> [command](#action_command)
> [extends](#action_extends)
> [forward](#action_forward)
> [id](#action_id)
> *Match the ID rules.*
> [include](#action_include)
> [input](#action_input)
> [name](#action_name)
> [parameter](#action_parameter)
> [path](#action_path)
> [prefix](#action_prefix)
> [roles](#action_roles)
> [scope](#action_scope)
> request, session
> [suffix](#action_suffix)
> [type](#action_type)
> [unknown](#action_unknown)
> true, false, yes, no
> [validate](#action_validate)
> true, false, yes, no

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*, [exception](#exception)\*, [forward](#forward)\*)

|-----|--------------------------------|
| @id | Attribute of [action](#action) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|--------------------------------|
| @attribute | Attribute of [action](#action) |

Sorry, no documentation.

|--------------|--------------------------------|
| @cancellable | Attribute of [action](#action) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|----------|--------------------------------|
| @catalog | Attribute of [action](#action) |

Sorry, no documentation.

|------------|--------------------------------|
| @className | Attribute of [action](#action) |

Sorry, no documentation.

|----------|--------------------------------|
| @command | Attribute of [action](#action) |

Sorry, no documentation.

|----------|--------------------------------|
| @extends | Attribute of [action](#action) |

Sorry, no documentation.

|----------|--------------------------------|
| @forward | Attribute of [action](#action) |

Sorry, no documentation.

|----------|--------------------------------|
| @include | Attribute of [action](#action) |

Sorry, no documentation.

|--------|--------------------------------|
| @input | Attribute of [action](#action) |

Sorry, no documentation.

|-------|--------------------------------|
| @name | Attribute of [action](#action) |

Sorry, no documentation.

|------------|--------------------------------|
| @parameter | Attribute of [action](#action) |

Sorry, no documentation.

|-------|--------------------------------|
| @path | Attribute of [action](#action) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|---------|--------------------------------|
| @prefix | Attribute of [action](#action) |

Sorry, no documentation.

|--------|--------------------------------|
| @roles | Attribute of [action](#action) |

Sorry, no documentation.

|--------|--------------------------------|
| @scope | Attribute of [action](#action) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: request, session

|---------|--------------------------------|
| @suffix | Attribute of [action](#action) |

Sorry, no documentation.

|-------|--------------------------------|
| @type | Attribute of [action](#action) |

Sorry, no documentation.

|----------|--------------------------------|
| @unknown | Attribute of [action](#action) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|-----------|--------------------------------|
| @validate | Attribute of [action](#action) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|----------------|------------------------------------------|
| \<controller\> | Child of [struts-config](#struts-config) |

The "controller" element describes the ControllerConfig bean [org.apache.struts.config.ControllerConfig] that encapsulates a module's runtime configuration. The following attributes are defined:

bufferSize The size of the input buffer used when processing file uploads. [4096]

catalog Name of the catalog to use when processing requests for this module. [struts]

className Fully qualified Java class name of the ControllerConfig subclass for this controller object. If specified, the object must be a subclass of the default class. ["org.apache.struts.config.ControllerConfig"]

command Name of the command to execute to process a request. [servlet-standard]

contentType Default content type (and optional character encoding) to be set on each response. May be overridden by the Action, JSP, or other resource to which the request is forwarded. ["text.html.md"]

forwardPattern Replacement pattern defining how the "path" attribute of a \<forward\> element is mapped to a context-relative URL when it starts with a slash (and when the contextRelative property is false). This value may consist of any combination of the following: - "$M" - Replaced by the module prefix of this module - "$P" - Replaced by the "path" attribute of the selected "forward" element - "$$" - Causes a literal dollar sign to be rendered - "$x" - (Where "x" is any character not defined above) Silently swallowed, reserved for future use If not specified, the default forwardPattern is "$M$P", which is consistent with the previous behavior of forwards. Since Struts 1.1. ["$M$P"]

inputForward Set to "true" if you want the "input" attribute of \<action\> elements to be the name of a local or global ActionForward, which will then be used to calculate the ultimate URL. Set to "false" (the default) to treat the "input" parameter of \<action\> elements as a module-relative path to the resource to be used as the input form. Since Struts 1.1. [false]

locale Set to "true" if you want a Locale object stored in the user's session if not already present. [true]

maxFileSize The maximum size (in bytes) of a file to be accepted as a file upload. Can be expressed as a number followed by a "K", "M", or "G", which are interpreted to mean kilobytes, megabytes, or gigabytes, respectively. ["250M"]

memFileSize The maximum size (in bytes) of a file whose contents will be retained in memory after uploading. Files larger than this threshold will be written to some alternative storage medium, typically a hard disk. Can be expressed as a number followed by a "K", "M", or "G", which are interpreted to mean kilobytes, megabytes, or gigabytes, respectively. ["256K"]

multipartClass The fully qualified Java class name of the multipart request handler class to be used with this module. ["org.apache.struts.upload.CommonsMultipartRequestHandler"]

nocache Set to "true" if you want the controller to add HTTP headers for defeating caching to every response from this module. [false]

pagePattern Replacement pattern defining how the "page" attribute of custom tags using it is mapped to a context-relative URL of the corresponding resource. This value may consist of any combination of the following: - "$M" - Replaced by the module prefix of this module - "$P" - Replaced by the value of the "page" attribute - "$$" - Causes a literal dollar sign to be rendered - "$x" - (Where "x" is any character not defined above) Silently swallowed, reserved for future use If not specified, the default forwardPattern is "$M$P", which is consistent with previous hard coded behavior of URL evaluation for "page" attributes. ["$M$P"]

processorClass The fully qualified Java class name of the RequestProcessor subclass to be used with this module. ["org.apache.struts.chain.ComposableRequestProcessor"]

tempDir Temporary working directory to use when processing file uploads. [{Directory provided by servlet container}]

> \<controller\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<controller\>'s attributes
> Name
> Values
> Default
> [bufferSize](#controller_bufferSize)
> [catalog](#controller_catalog)
> [className](#controller_className)
> [command](#controller_command)
> [contentType](#controller_contentType)
> [forwardPattern](#controller_forwardPattern)
> [id](#controller_id)
> *Match the ID rules.*
> [inputForward](#controller_inputForward)
> true, false, yes, no
> [locale](#controller_locale)
> true, false, yes, no
> [maxFileSize](#controller_maxFileSize)
> [memFileSize](#controller_memFileSize)
> [multipartClass](#controller_multipartClass)
> [nocache](#controller_nocache)
> true, false, yes, no
> [pagePattern](#controller_pagePattern)
> [processorClass](#controller_processorClass)
> [tempDir](#controller_tempDir)

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|-----|----------------------------------------|
| @id | Attribute of [controller](#controller) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------------|----------------------------------------|
| @bufferSize | Attribute of [controller](#controller) |

Sorry, no documentation.

|----------|----------------------------------------|
| @catalog | Attribute of [controller](#controller) |

Sorry, no documentation.

|------------|----------------------------------------|
| @className | Attribute of [controller](#controller) |

Sorry, no documentation.

|----------|----------------------------------------|
| @command | Attribute of [controller](#controller) |

Sorry, no documentation.

|--------------|----------------------------------------|
| @contentType | Attribute of [controller](#controller) |

Sorry, no documentation.

|-----------------|----------------------------------------|
| @forwardPattern | Attribute of [controller](#controller) |

Sorry, no documentation.

|---------------|----------------------------------------|
| @inputForward | Attribute of [controller](#controller) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|---------|----------------------------------------|
| @locale | Attribute of [controller](#controller) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|--------------|----------------------------------------|
| @maxFileSize | Attribute of [controller](#controller) |

Sorry, no documentation.

|--------------|----------------------------------------|
| @memFileSize | Attribute of [controller](#controller) |

Sorry, no documentation.

|-----------------|----------------------------------------|
| @multipartClass | Attribute of [controller](#controller) |

Sorry, no documentation.

|----------|----------------------------------------|
| @nocache | Attribute of [controller](#controller) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|--------------|----------------------------------------|
| @pagePattern | Attribute of [controller](#controller) |

Sorry, no documentation.

|-----------------|----------------------------------------|
| @processorClass | Attribute of [controller](#controller) |

Sorry, no documentation.

|----------|----------------------------------------|
| @tempDir | Attribute of [controller](#controller) |

Sorry, no documentation.

|-----------------------|------------------------------------------|
| \<message-resources\> | Child of [struts-config](#struts-config) |

The "message-resources" element describes a MessageResources object with message templates for this module. The following attributes are defined:

className The configuration bean for this message resources object. If specified, the object must be a subclass of the default configuration bean. ["org.apache.struts.config.MessageResourcesConfig"]

factory Fully qualified Java class name of the MessageResourcesFactory subclass to use for this message resources object. ["org.apache.struts.util.PropertyMessageResourcesFactory"]

key Servlet context attribute under which this message resources bundle will be stored. The default attribute is the value specified by the string constant at [Globals.MESSAGES\_KEY]. The module prefix (if any) is appended to the key (${key}${prefix}). [org.apache.struts.Globals.MESSAGES\_KEY]

NOTE: The module prefix includes the leading slash, so the default message resource bundle for a module named "foo" is stored under "org.apache.struts.action.MESSAGE/foo".

null Set to "true" if you want our message resources to return a null string for unknown message keys, or "false" to return a message with the bad key value.

parameter Configuration parameter to be passed to the createResources method of our factory object.

> \<message-resources\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<message-resources\>'s attributes
> Name
> Values
> Default
> [className](#message-resources_className)
> [factory](#message-resources_factory)
> [id](#message-resources_id)
> *Match the ID rules.*
> [key](#message-resources_key)
> [null](#message-resources_null)
> true, false, yes, no
> [parameter](#message-resources_parameter)

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|-----|------------------------------------------------------|
| @id | Attribute of [message-resources](#message-resources) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|------------------------------------------------------|
| @className | Attribute of [message-resources](#message-resources) |

Sorry, no documentation.

|----------|------------------------------------------------------|
| @factory | Attribute of [message-resources](#message-resources) |

Sorry, no documentation.

|------|------------------------------------------------------|
| @key | Attribute of [message-resources](#message-resources) |

Sorry, no documentation.

|-------|------------------------------------------------------|
| @null | Attribute of [message-resources](#message-resources) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|------------|------------------------------------------------------|
| @parameter | Attribute of [message-resources](#message-resources) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------------|------------------------------------------|
| \<plug-in\> | Child of [struts-config](#struts-config) |

The "plug-in" element specifies the fully qualified class name of a general-purpose application plug-in module that receives notification of application startup and shutdown events. An instance of the specified class is created for each element, and can be configured with nested \<set-property\> elements. The following attributes are supported:

className Fully qualified Java class name of the plug-in class; must implement [org.apache.struts.action.PlugIn].

> \<plug-in\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<plug-in\>'s attributes
> Name
> Values
> Default
> [className](#plug-in_className)
> [id](#plug-in_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|-----|----------------------------------|
| @id | Attribute of [plug-in](#plug-in) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|----------------------------------|
| @className | Attribute of [plug-in](#plug-in) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
| \<description\> | Child of [action](#action), [exception](#exception), [struts-config](#struts-config), [forward](#forward), [form-bean](#form-bean) |

The "description" element contains descriptive (paragraph length) text about the surrounding element, suitable for use in GUI tools.

> \<description\>'s attributes
> Name
> Values
> Default
> [id](#description_id)
> *Match the ID rules.*

|-----|------------------------------------------|
| @id | Attribute of [description](#description) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------------|------------------------------------------------------------------------------------------------------------------------------------|
| \<display-name\> | Child of [action](#action), [exception](#exception), [struts-config](#struts-config), [forward](#forward), [form-bean](#form-bean) |

The "display-name" element contains a short (one line) description of the surrounding element, suitable for use in GUI tools.

> \<display-name\>'s attributes
> Name
> Values
> Default
> [id](#display-name_id)
> *Match the ID rules.*

|-----|--------------------------------------------|
| @id | Attribute of [display-name](#display-name) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------|---------------------------------------------------------------------------------------------------|
| \<icon\> | Child of [action](#action), [exception](#exception), [forward](#forward), [form-bean](#form-bean) |

The "icon" element contains a small-icon and large-icon element which specify the location, relative to the Struts configuration file, for small and large images used to represent the surrounding element in GUI tools.

> \<icon\>'s children
> Name
> Cardinality
> [large-icon](#large-icon)
> One or none
> [small-icon](#small-icon)
> One or none
> \<icon\>'s attributes
> Name
> Values
> Default
> [id](#icon_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([small-icon](#small-icon)?, [large-icon](#large-icon)?)

|-----|----------------------------|
| @id | Attribute of [icon](#icon) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------------|------------------------|
| \<large-icon\> | Child of [icon](#icon) |

The "large-icon" element specifies the location, relative to the Struts configuration file, of a resource containing a large (32x32 pixel) icon image.

> \<large-icon\>'s attributes
> Name
> Values
> Default
> [id](#large-icon_id)
> *Match the ID rules.*

|-----|----------------------------------------|
| @id | Attribute of [large-icon](#large-icon) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<set-property/\> | Child of [plug-in](#plug-in), [message-resources](#message-resources), [action](#action), [exception](#exception), [form-property](#form-property), [forward](#forward), [controller](#controller), [form-bean](#form-bean) |

The "set-property" element specifies the method name and initial value of an additional JavaBean configuration property. When the object representing the surrounding element is instantiated, the accessor for the indicated property is called and passed the indicated value. The "set-property" element is especially useful when a custom subclass is used with \<forward\>, \<action\>, or \<plug-in\> elements. The subclass can be passed whatever other properties may be required to configure the object without changing how the struts-config is parsed.

Since Struts 1.3, an alternate syntax is supported. By using the "key" attribute instead of the "property" attribute, you can set arbitrary string properties on the Config object which is populated based on the containing element. NOTE: the "key" attribute is NOT supported for \<set-property\> inside a \<plug-in\> element.

property Name of the JavaBeans property whose setter method will be called. Exactly one of "property" or "key" must be specified.

key Where supported, the key which will be used to store the specified value in the given config object. Exactly one of "property" or "key" must be specified.

value String representation of the value to which this property will be set, after suitable type conversion

> \<set-property\>'s attributes
> Name
> Values
> Default
> [id](#set-property_id)
> *Match the ID rules.*
> [key](#set-property_key)
> [property](#set-property_property)
> [value](#set-property_value)

This element is always empty.

|-----|--------------------------------------------|
| @id | Attribute of [set-property](#set-property) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-----------|--------------------------------------------|
| @property | Attribute of [set-property](#set-property) |

Sorry, no documentation.

|------|--------------------------------------------|
| @key | Attribute of [set-property](#set-property) |

Sorry, no documentation.

|--------|--------------------------------------------|
| @value | Attribute of [set-property](#set-property) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|----------------|------------------------|
| \<small-icon\> | Child of [icon](#icon) |

The "small-icon" element specifies the location, relative to the Struts configuration file, of a resource containing a small (16x16 pixel) icon image.

> \<small-icon\>'s attributes
> Name
> Values
> Default
> [id](#small-icon_id)
> *Match the ID rules.*

|-----|----------------------------------------|
| @id | Attribute of [small-icon](#small-icon) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*
