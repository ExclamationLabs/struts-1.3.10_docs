**`tiles-config_1_1.dtd`**: [Elements](tiles-config_1_1.dtd.html.md) - [Entities](tiles-config_1_1.dtd.entities.html) - [Source](tiles-config_1_1.dtd.org.html) | [Intro](intro.html) - [Index](elementsIndex.html)
 [FRAMES](index.html.md) / [NO FRAMES](tiles-config_1_1.dtd.html)

tiles-config\_1\_1.dtd
======================

$Id: tiles-config\_1\_1.dtd 481833 2006-12-03 17:32:52Z niallp $

Licensed to the Apache Software Foundation (ASF) under one or more contributor license agreements. See the NOTICE file distributed with this work for additional information regarding copyright ownership. The ASF licenses this file to You under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

|---------------------------|--------------|
| \<component-definitions\> | Root element |

deprecated: use tiles-definitions instead.

> \<component-definitions\>'s children
> Name
> Cardinality
> [definition](#definition)
> At least one

<span class="inTextTitle">Element's model:</span>

([definition](#definition)+)

|-----------------------|--------------|
| \<tiles-definitions\> | Root element |

The "tiles-definitions" element is the root of the configuration file hierarchy, and contains nested elements for all of the other configuration settings.

> \<tiles-definitions\>'s children
> Name
> Cardinality
> [definition](#definition)
> At least one

<span class="inTextTitle">Element's model:</span>

([definition](#definition)+)

|----------------|---------------------------------------------------------------------------------------------------|
| \<definition\> | Child of [component-definitions](#component-definitions), [tiles-definitions](#tiles-definitions) |

The "definition" element describes a definition that can be inserted in a jsp page. This definition is identified by its logical name. A definition allows to define all the attributes that can be set in \<insert\> tag from a jsp page.

controllerClass The fully qualified Java class name of the controller subclass to call immediately before the tiles is inserted. Only one of controllerClass or controllerUrl should be specified.

controllerUrl The context-relative path to the resource used as controller called immediately before the tiles is inserted. Only one of controllerClass or controllerUrl should be specified.

extends Name of a definition that is used as ancestor of this definition. All attributes from the ancestor are available to the new definition. Any attribute inherited from the ancestor can be overloaded by providing a new value.

name The unique identifier for this definition.

page Same as path.

path The context-relative path to the resource used as tiles to insert. This tiles will be inserted and a tiles context containing appropriate attributes will be available.

role Security role name that is allowed access to this definition object. The definition is inserted only if the role name is allowed.

template Same as path. For compatibility with the template tag library.

> \<definition\>'s children
> Name
> Cardinality
> [description](#description)
> One or none
> [display-name](#display-name)
> One or none
> [icon](#icon)
> One or none
> [put](#put)
> Any number
> [putList](#putList)
> Any number
> \<definition\>'s attributes
> Name
> Values
> Default
> [controllerClass](#definition_controllerClass)
> [controllerUrl](#definition_controllerUrl)
> [extends](#definition_extends)
> [id](#definition_id)
> *Match the ID rules.*
> [name](#definition_name)
> [page](#definition_page)
> [path](#definition_path)
> [role](#definition_role)
> [template](#definition_template)

<span class="inTextTitle">Element's model:</span>

([icon](#icon)?, [display-name](#display-name)?, [description](#description)?, [put](#put)\*, [putList](#putList)\*)

|-----|----------------------------------------|
| @id | Attribute of [definition](#definition) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------------|----------------------------------------|
| @controllerClass | Attribute of [definition](#definition) |

Sorry, no documentation.

|----------------|----------------------------------------|
| @controllerUrl | Attribute of [definition](#definition) |

Sorry, no documentation.

|----------|----------------------------------------|
| @extends | Attribute of [definition](#definition) |

Sorry, no documentation.

|-------|----------------------------------------|
| @name | Attribute of [definition](#definition) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|----------------------------------------|
| @page | Attribute of [definition](#definition) |

Sorry, no documentation.

|-------|----------------------------------------|
| @path | Attribute of [definition](#definition) |

Sorry, no documentation.

|-------|----------------------------------------|
| @role | Attribute of [definition](#definition) |

Sorry, no documentation.

|-----------|----------------------------------------|
| @template | Attribute of [definition](#definition) |

Sorry, no documentation.

|---------|------------------------------------|
| \<put\> | Child of [definition](#definition) |

The "put" element describes an attribute of a definition. It allows to specify the tiles attribute name and its value. The tiles value can be specified as an xml attribute, or in the body of the \<put\> tag.

content Same as value. For compatibility with the template tag library.

direct Same as type="string". For compatibility with the template tag library.

name The unique identifier for this put.

type The type of the value. Can be: string, page, template or definition. By default, no type is associated to a value. If a type is associated, it will be used as a hint to process the value when the attribute will be used in the inserted tiles.

value The value associated to this tiles attribute. The value should be specified with this tag attribute, or in the body of the tag.

> \<put\>'s attributes
> Name
> Values
> Default
> [content](#put_content)
> [direct](#put_direct)
> true, false
> [id](#put_id)
> *Match the ID rules.*
> [name](#put_name)
> [type](#put_type)
> string, page, template, definition
> [value](#put_value)

|-----|--------------------------|
| @id | Attribute of [put](#put) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------|--------------------------|
| @content | Attribute of [put](#put) |

Sorry, no documentation.

|---------|--------------------------|
| @direct | Attribute of [put](#put) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false

|-------|--------------------------|
| @name | Attribute of [put](#put) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------|--------------------------|
| @type | Attribute of [put](#put) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: string, page, template, definition

|--------|--------------------------|
| @value | Attribute of [put](#put) |

Sorry, no documentation.

|-------------|------------------------------------|
| \<putList\> | Child of [definition](#definition) |

The "putList" element describes a list attribute of a definition. It allows to specify an attribute that is a java List containing any kind of values. In the config file, the list elements are specified by nested \<add\>, \<item\> or \<putList\>.

name The unique identifier for this put list.

> \<putList\>'s children
> Name
> Cardinality
> [add](#add)
> Any number
> [bean](#bean)
> Any number
> [item](#item)
> Any number
> [putList](#putList)
> Any number
> \<putList\>'s attributes
> Name
> Values
> Default
> [id](#putList_id)
> *Match the ID rules.*
> [name](#putList_name)

<span class="inTextTitle">Element's model:</span>

(([add](#add)\* | [item](#item)\* | [bean](#bean)\* | [putList](#putList)\*)+)

|-----|----------------------------------|
| @id | Attribute of [putList](#putList) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|-------|----------------------------------|
| @name | Attribute of [putList](#putList) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|---------|------------------------------|
| \<add\> | Child of [putList](#putList) |

The "add" element describes an element of a list. It is similar to the \<put\> element.

content Same as value. For compatibility with the template tag library.

direct Same as type="string". For compatibility with the template tag library.

type The type of the value. Can be: string, page, template or definition. By default, no type is associated to a value. If a type is associated, it will be used as a hint to process the value when the attribute will be used in the inserted tiles.

value The value associated to this tiles attribute. The value should be specified with this tag attribute, or in the body of the tag.

> \<add\>'s attributes
> Name
> Values
> Default
> [content](#add_content)
> [direct](#add_direct)
> true, false
> [id](#add_id)
> *Match the ID rules.*
> [type](#add_type)
> string, page, template, definition
> [value](#add_value)

|-----|--------------------------|
| @id | Attribute of [add](#add) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|----------|--------------------------|
| @content | Attribute of [add](#add) |

Sorry, no documentation.

|---------|--------------------------|
| @direct | Attribute of [add](#add) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: true, false

|-------|--------------------------|
| @type | Attribute of [add](#add) |

Sorry, no documentation.

<span class="inTextTitle">Possible values</span>: string, page, template, definition

|--------|--------------------------|
| @value | Attribute of [add](#add) |

Sorry, no documentation.

|----------|------------------------------|
| \<bean\> | Child of [putList](#putList) |

The "bean" element describes an element of a list. It create a bean of the specified java classtype. This bean is initialized with appropriate nested \<set-property\>.

classtype The fully qualified classname for this bean.

> \<bean\>'s children
> Name
> Cardinality
> [set-property](#set-property)
> Any number
> \<bean\>'s attributes
> Name
> Values
> Default
> [classtype](#bean_classtype)
> [id](#bean_id)
> *Match the ID rules.*

<span class="inTextTitle">Element's model:</span>

([set-property](#set-property)\*)

|-----|----------------------------|
| @id | Attribute of [bean](#bean) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|----------------------------|
| @classtype | Attribute of [bean](#bean) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-------------------|------------------------|
| \<set-property/\> | Child of [bean](#bean) |

The "set-property" element specifies the method name and initial value of a bean property. When the object representing the surrounding element is instantiated, the accessor for the indicated property is called and passed the indicated value.

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

|----------|------------------------------|
| \<item\> | Child of [putList](#putList) |

The "item" element describes an element of a list. It create a bean added as element to the list. Each bean can contain different properties: value, link, icon, tooltip. These properties are to be interpreted by the jsp page using them. By default the bean is of type "org.apache.struts.tiles.beans.SimpleMenuItem". This bean is useful to create a list of beans used as menu items.

classtype The fully qualified classtype for this bean. If specified, the classtype must be a subclass of the interface "org.apache.struts.tiles.beans.MenuItem".

icon The bean 'icon' property.

link The bean 'link' property.

tooltip The bean 'tooltip' property.

value The bean 'value' property.

> \<item\>'s attributes
> Name
> Values
> Default
> [classtype](#item_classtype)
> [icon](#item_icon)
> [id](#item_id)
> *Match the ID rules.*
> [link](#item_link)
> [tooltip](#item_tooltip)
> [value](#item_value)

|-----|----------------------------|
| @id | Attribute of [item](#item) |

Element identifier.

<span class="inTextTitle">Possible values</span>: *Match the ID rules.*

|------------|----------------------------|
| @classtype | Attribute of [item](#item) |

Sorry, no documentation.

|-------|----------------------------|
| @icon | Attribute of [item](#item) |

Sorry, no documentation.

|-------|----------------------------|
| @link | Attribute of [item](#item) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|----------|----------------------------|
| @tooltip | Attribute of [item](#item) |

Sorry, no documentation.

|--------|----------------------------|
| @value | Attribute of [item](#item) |

Sorry, no documentation.

<span class="inTextTitle">Required</span>

|-----------------|------------------------------------|
| \<description\> | Child of [definition](#definition) |

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

|------------------|------------------------------------|
| \<display-name\> | Child of [definition](#definition) |

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

|----------|------------------------------------|
| \<icon\> | Child of [definition](#definition) |

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
