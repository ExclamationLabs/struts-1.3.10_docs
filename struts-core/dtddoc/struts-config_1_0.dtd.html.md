**`struts-config_1_0.dtd`**: [Elements](struts-config_1_0.dtd.html.md) - [Entities](struts-config_1_0.dtd.entities.html) - [Source](struts-config_1_0.dtd.org.html) | [Intro](intro.html) - [Index](elementsIndex.html)
 [FRAMES](index.html.md) / [NO FRAMES](struts-config_1_0.dtd.html)

struts-config\_1\_0.dtd
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
> [data-sources](#data-sources)
> One or none
> [form-beans](#form-beans)
> One or none
> [global-forwards](#global-forwards)
> One or none
> \<struts-config\>'s attributes
> Name
> Values
> Default
> [id](#struts-config_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([data-sources](#data-sources)?, [form-beans](#form-beans)?, [global-forwards](#global-forwards)?, [action-mappings](#action-mappings)?)

|-----|----------------------------------------------|
| @id | Attribute of [struts-config](#struts-config) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------------|------------------------------------------|
| \<data-sources\> | Child of [struts-config](#struts-config) |

The "data-sources" element describes a set of JDBC 2.0 Standard Extension data source objects which will be configured according to the nested "data-source" elements found inside.

> \<data-sources\>'s children
> Name
> Cardinality
> [data-source](#data-source)
> Any number
> \<data-sources\>'s attributes
> Name
> Values
> Default
> [id](#data-sources_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([data-source](#data-source)\*)

|-----|--------------------------------------------|
| @id | Attribute of [data-sources](#data-sources) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-----------------|----------------------------------------|
| \<data-source\> | Child of [data-sources](#data-sources) |

The "data-source" element describes a JDBC 2.0 Standard Extension data source object (that implements javax.sql.DataSource) which will be configured according to the properties and nested elements found here, and made available as a servlet context attribute (i.e. application scope bean). The following attributes are required:

key Servlet context attribute key under which this data source will be stored. Default is the value specified by string constant Action.DATA\_SOURCE\_KEY.

type Fully qualified Java class name of the implementation class (must implement javax.sql.DataSource). Default value is 'org.apache.struts.util.GenericDataSource'.

NOTE: The following attributes are defined by the default data source implementation, and only take effect for that class or subclasses of that class.

WARNING: The use of these attributes is deprecated. You should use nested \<set-property\> elements to configure \*all\* properties of your data source implementation.

autoCommit The default auto-commit state for newly created connections.

description The description of this data source.

driverClass The Java class name of the JDBC driver to be used. [REQUIRED]

loginTimeout The maximum number of seconds to wait for a connection to be created or returned. Default is driver dependent.

maxCount The maximum number of connections to be created.

minCount The minimum number of connections to be created.

password The database password to use when connecting. [REQUIRED]

readOnly The default read-only state for newly created connections.

url The JDBC URL to use when connecting. [REQUIRED]

user The database username to use when connecting. [REQUIRED]

> \<data-source\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<data-source\>'s attributes
> Name
> Values
> Default
> [autoCommit](#data-source_autoCommit)
> true, false, yes, no
> [description](#data-source_description)
> [driverClass](#data-source_driverClass)
> [id](#data-source_id)
> *Match the ID rules.*
> [key](#data-source_key)
> [loginTimeout](#data-source_loginTimeout)
> [maxCount](#data-source_maxCount)
> [minCount](#data-source_minCount)
> [password](#data-source_password)
> [readOnly](#data-source_readOnly)
> true, false, yes, no
> [type](#data-source_type)
> [url](#data-source_url)
> [user](#data-source_user)

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|-----|------------------------------------------|
| @id | Attribute of [data-source](#data-source) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------|------------------------------------------|
| @key | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-------|------------------------------------------|
| @type | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-------------|------------------------------------------|
| @autoCommit | Attribute of [data-source](#data-source) |

set-property element to configure data source properties.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|--------------|------------------------------------------|
| @description | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|--------------|------------------------------------------|
| @driverClass | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|---------------|------------------------------------------|
| @loginTimeout | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-----------|------------------------------------------|
| @maxCount | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-----------|------------------------------------------|
| @minCount | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-----------|------------------------------------------|
| @password | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-----------|------------------------------------------|
| @readOnly | Attribute of [data-source](#data-source) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|------|------------------------------------------|
| @url | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|-------|------------------------------------------|
| @user | Attribute of [data-source](#data-source) |

Sorry, no documentation.

|----------------|------------------------------------------|
| \<form-beans\> | Child of [struts-config](#struts-config) |

The "form-beans" element is the root of the set of form bean descriptors for this application. The following attributes are defined:

type Fully qualified Java class name of the implementation class used for ActionFormBean objects. DEPRECATED.

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
> org.apache.struts.action.ActionFormBean

<span class="inTextTitle">Element's model:</span>

([form-bean](#form-bean)\*)

|-----|----------------------------------------|
| @id | Attribute of [form-beans](#form-beans) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|----------------------------------------|
| @type | Attribute of [form-beans](#form-beans) |

Sorry, no documentation.

<span class="inTextTitle">Default value</span>: org.apache.struts.action.ActionFormBean

|---------------|------------------------------------|
| \<form-bean\> | Child of [form-beans](#form-beans) |

The "form-bean" element describes a particular form bean, which is a JavaBean that implements the org.apache.struts.action.ActionForm class. The following attributes are defined:

className Fully qualified Java class name of the ActionFormBean implementation class to use. Defaults to the value configured as the "formBean" initialization parameter to the Struts controller servlet.

name Unique identifier of this bean, used to reference it in corresponding action mappings.

type Fully qualified Java class name of the implementation class to be used or generated

> \<form-bean\>'s children
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
> \<form-bean\>'s attributes
> Name
> Values
> Default
> [className](#form-bean_className)
> [id](#form-bean_id)
> *Match the ID rules.*
> [name](#form-bean_name)
> [type](#form-bean_type)

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*)

|-----|--------------------------------------|
| @id | Attribute of [form-bean](#form-bean) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|--------------------------------------|
| @className | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

|-------|--------------------------------------|
| @name | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|--------------------------------------|
| @type | Attribute of [form-bean](#form-bean) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|---------------------|------------------------------------------|
| \<global-forwards\> | Child of [struts-config](#struts-config) |

The "global-forwards" element configures the global mappings of logical names (used within the application) to mappable resources (identified by context-relative URI paths). A global "forward" with a particular name can be locally overridden by defining a "forward" of the same name within an "action" element. The following attribute are defined:

type Fully qualified Java class name of the implementation class used for ActionForward objects. DEPRECATED.

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
> org.apache.struts.action.ActionForward

<span class="inTextTitle">Element's model:</span>

([forward](#forward)\*)

|-----|--------------------------------------------------|
| @id | Attribute of [global-forwards](#global-forwards) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|--------------------------------------------------|
| @type | Attribute of [global-forwards](#global-forwards) |

Sorry, no documentation.

<span class="inTextTitle">Default value</span>: org.apache.struts.action.ActionForward

|-------------|-----------------------------------------------------------------|
| \<forward\> | Child of [global-forwards](#global-forwards), [action](#action) |

The "forward" element describes a mapping of a logical name (used within the application) to a mappable resource identified by a context-relative URI path. The following attributes are defined:

className Fully qualified Java class name of the ActionForward implementation class to use. Defaults to the value configured as the "forward" initialization parameter to the Struts controller servlet.

name Unique identifier of this forward, used to reference it in application action classes.

path The context-relative path of the mapped resource.

redirect Set to "true" if sendRedirect() should be used to forward to this resource, or "false" in order to use RequestDispatcher.forward() instead.

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
> [className](#forward_className)
> [id](#forward_id)
> *Match the ID rules.*
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

|------------|----------------------------------|
| @className | Attribute of [forward](#forward) |

Sorry, no documentation.

|-------|----------------------------------|
| @name | Attribute of [forward](#forward) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|----------------------------------|
| @path | Attribute of [forward](#forward) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-----------|----------------------------------|
| @redirect | Attribute of [forward](#forward) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false, yes, no

|---------------------|------------------------------------------|
| \<action-mappings\> | Child of [struts-config](#struts-config) |

The "action-mappings" element configures the mappings from submitted request paths to the corresponding Action classes that should be used to process these requests. The following attributes are defined:

type Fully qualified Java class name of the ActionMapping implementation class to be used. DEPRECATED.

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
> org.apache.struts.action.ActionMapping

<span class="inTextTitle">Element's model:</span>

([action](#action)\*)

|-----|--------------------------------------------------|
| @id | Attribute of [action-mappings](#action-mappings) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|--------------------------------------------------|
| @type | Attribute of [action-mappings](#action-mappings) |

Sorry, no documentation.

<span class="inTextTitle">Default value</span>: org.apache.struts.action.ActionMapping

|------------|----------------------------------------------|
| \<action\> | Child of [action-mappings](#action-mappings) |

The "action" element describes a mapping from a request paths to the corresponding Action classes that should be used to process these requests. The following attributes are defined:

attribute Name of the request-scope or session-scope attribute under which our form bean is accessed, if it is other than the bean's specified "name". Optional if "name" is specified, else not allowed.

className Fully qualified Java class name of the ActionMapping implementation class to use. Defaults to the value configured as the "mapping" initialization parameter to the Struts controller servlet.

forward Context-relative path of the servlet or JSP resource that will process this request, instead of instantiating and calling the Action class specified by "type". Exactly one of "forward", "include", or "type" must be specified.

include Context-relative path of the servlet or JSP resource that will process this request, instead of instantiating and calling the Action class specified by "type". Exactly one of "forward", "include", or "type" must be specified.

input Context-relative path of the input form to which control should be returned if a validation error is encountered. Required if "name" is specified and the input bean returns validation errors. Optional if "name" is specified and the input bean does not return validation errors. Not allowed if "name" is not specified.

name Name of the form bean, if any, that is associated with this action.

path The context-relative path of the submitted request, starting with a "/" character, and without the filename extension if extension mapping is used.

parameter General purpose configuration parameter that can be used to pass extra information to the Action selected by this mapping.

prefix Prefix used to match request parameter names to form bean property names, if any. Optional if "name" is specified, else not allowed.

scope Identifier of the scope ("request" or "session") within which our form bean is accessed, if any. Optional if "name" is specified, else not allowed.

suffix Suffix used to match request parameter names to form bean property names, if any. Optional if "name" is specified, else not allowed.

type Fully qualified Java class name of the Action class (implements org.apache.struts.action.Action) to be used to process requests for this mapping if the "forward" or "include" attribute is not included. Exactly one of "forward", "include", or "type" must be specified.

unknown Set to "true" if this action should be configured as the default for this application, to handle all requests not handled by another action. Only one action can be defined as a default within a single application.

validate Set to "true" if the validate() method of the form bean should be called prior to calling this action, or set to "false" if you do not want validation performed.

> \<action\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
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
> [className](#action_className)
> [forward](#action_forward)
> [id](#action_id)
> *Match the ID rules.*
> [include](#action_include)
> [input](#action_input)
> [name](#action_name)
> [parameter](#action_parameter)
> [path](#action_path)
> [prefix](#action_prefix)
> [scope](#action_scope)
> request, session
> [suffix](#action_suffix)
> [type](#action_type)
> [unknown](#action_unknown)
> true, false, yes, no
> [validate](#action_validate)
> true, false, yes, no

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [set-property](#set-property)\*, [forward](#forward)\*)

|-----|--------------------------------|
| @id | Attribute of [action](#action) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|--------------------------------|
| @attribute | Attribute of [action](#action) |

Sorry, no documentation.

|------------|--------------------------------|
| @className | Attribute of [action](#action) |

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

|-------------------|-------------------------------------------------------------------------------------------------------|
| \<set-property/\> | Child of [forward](#forward), [action](#action), [data-source](#data-source), [form-bean](#form-bean) |

The "set-property" element specifies the name and value of an additional JavaBeans configuration property whose setter method will be called on the object that represents our surrounding element. This is especially useful when an extended implementation class (with additional properties) is configured on the \<global-forwards\> or \<action-mappings\> elements. The following attributes are defined:

property Name of the JavaBeans property whose setter method will be called.

value String representation of the value to which this property will be set, after suitable type conversion

> \<set-property\>'s attributes
> Name
> Values
> Default
> [id](#set-property_id)
> *Match the ID rules.*
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

<span class="inTextTitle">Required</span>

|--------|--------------------------------------------|
| @value | Attribute of [set-property](#set-property) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-----------------|--------------------------------------------------------------------------|
| \<description\> | Child of [forward](#forward), [action](#action), [form-bean](#form-bean) |

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

|------------------|--------------------------------------------------------------------------|
| \<display-name\> | Child of [forward](#forward), [action](#action), [form-bean](#form-bean) |

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

|----------|--------------------------------------------------------------------------|
| \<icon\> | Child of [forward](#forward), [action](#action), [form-bean](#form-bean) |

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
