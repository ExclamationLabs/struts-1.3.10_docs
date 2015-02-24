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
<td align="left"><a href="class-use/FormBeanConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ExceptionConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/FormPropertyConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/FormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="FormBeanConfig.html"><strong>NO FRAMES</strong></a>    
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
 Class FormBeanConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.FormBeanConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[ActionFormBean](../../../../org/apache/struts/action/ActionFormBean.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

    public class FormBeanConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 472728 $ $Date: 2006-01-17 07:26:20 -0500 (Tue, 17 Jan 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.FormBeanConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  DynaActionFormClass`

` dynaActionFormClass`
           The DynaActionFormClass associated with a DynaActionForm.

`protected  boolean`

`dynamic`
           Is the form bean class an instance of DynaActionForm with dynamic properties?

`protected  boolean`

` extensionProcessed`
           Have the inheritance values for this class been applied?

`protected  HashMap`

` formProperties`
           The set of FormProperty elements defining dynamic form properties for this form bean, keyed by property name.

`protected  String`

`inherit`
           The name of the FormBeanConfig that this config inherits configuration information from.

`protected  String`

`lock`
           The lockable object we can synchronize on when creating DynaActionFormClass.

`protected  String`

`name`
           The unique identifier of this form bean, which is used to reference this bean in `ActionMapping` instances as well as for the name of the request or session attribute under which the corresponding form bean instance is created or accessed.

`protected  boolean`

` restricted`
           Is this DynaClass currently restricted (for DynaBeans with a MutableDynaClass).

`protected  String`

`type`
           The fully qualified Java class name of the implementation class to be used or generated.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` FormBeanConfig()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

` void`

` addFormPropertyConfig(FormPropertyConfig config)`
           Add a new `FormPropertyConfig` instance to the set associated with this module.

` boolean`

` canReuse(ActionForm form)`
           Checks if the given `ActionForm` instance is suitable for use as an alternative to calling this `FormBeanConfig` instance's `createActionForm` method.

`protected  boolean`

` checkCircularInheritance(ModuleConfig moduleConfig)`
           Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

` ActionForm`

` createActionForm(ActionContext context)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

` ActionForm`

` createActionForm(ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

` FormPropertyConfig`

` findFormPropertyConfig(String name)`
           Return the form property configuration for the specified property name, if any; otherwise return `null`.

` FormPropertyConfig[]`

` findFormPropertyConfigs()`
           Return the form property configurations for this module.

`protected  Class`

` formBeanClass()`
           Return the `Class` instance for the form bean implementation configured by this `FormBeanConfig` instance.

` void`

` freeze()`
           Freeze the configuration of this component.

` DynaActionFormClass`

` getDynaActionFormClass()`
           Return the DynaActionFormClass associated with a DynaActionForm.

` boolean`

` getDynamic()`
            

` String`

` getExtends()`
            

` String`

` getName()`
            

` String`

` getType()`
            

`protected  void`

` inheritFormProperties(FormBeanConfig config)`
           Compare the form properties of this bean with that of the given and copy those that are not present.

` void`

` inheritFrom(FormBeanConfig config)`
           Inherit values that have not been overridden from the provided config object.

` boolean`

` isExtensionProcessed()`
            

` boolean`

` isRestricted()`
           Indicates whether a MutableDynaClass is currently restricted.

` void`

` processExtends(ModuleConfig moduleConfig)`
           Inherit configuration information from the FormBeanConfig that this instance is extending.

` void`

` removeFormPropertyConfig(FormPropertyConfig config)`
           Remove the specified form property configuration instance.

` void`

` setExtends(String extend)`
            

` void`

` setName(String name)`
            

` void`

` setRestricted(boolean restricted)`
           Set whether a MutableDynaClass is currently restricted.

` void`

` setType(String type)`
            

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

<span id="formProperties"></span>

### formProperties

    protected HashMap formProperties

The set of FormProperty elements defining dynamic form properties for this form bean, keyed by property name.

------------------------------------------------------------------------

<span id="lock"></span>

### lock

    protected String lock

The lockable object we can synchronize on when creating DynaActionFormClass.

------------------------------------------------------------------------

<span id="dynaActionFormClass"></span>

### dynaActionFormClass

    protected transient DynaActionFormClass dynaActionFormClass

The DynaActionFormClass associated with a DynaActionForm.

------------------------------------------------------------------------

<span id="dynamic"></span>

### dynamic

    protected boolean dynamic

Is the form bean class an instance of DynaActionForm with dynamic properties?

------------------------------------------------------------------------

<span id="inherit"></span>

### inherit

    protected String inherit

The name of the FormBeanConfig that this config inherits configuration information from.

------------------------------------------------------------------------

<span id="extensionProcessed"></span>

### extensionProcessed

    protected boolean extensionProcessed

Have the inheritance values for this class been applied?

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

The unique identifier of this form bean, which is used to reference this bean in `ActionMapping` instances as well as for the name of the request or session attribute under which the corresponding form bean instance is created or accessed.

------------------------------------------------------------------------

<span id="type"></span>

### type

    protected String type

The fully qualified Java class name of the implementation class to be used or generated.

------------------------------------------------------------------------

<span id="restricted"></span>

### restricted

    protected boolean restricted

Is this DynaClass currently restricted (for DynaBeans with a MutableDynaClass).

<span id="constructor_detail"></span>

**Constructor Detail**

### FormBeanConfig

    public FormBeanConfig()

<span id="method_detail"></span>

**Method Detail**

### getDynaActionFormClass

    public DynaActionFormClass getDynaActionFormClass()

Return the DynaActionFormClass associated with a DynaActionForm.

**Throws:**  
`IllegalArgumentException` - if the ActionForm is not dynamic

------------------------------------------------------------------------

### getDynamic

    public boolean getDynamic()

------------------------------------------------------------------------

### getExtends

    public String getExtends()

------------------------------------------------------------------------

### setExtends

    public void setExtends(String extend)

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

### getType

    public String getType()

------------------------------------------------------------------------

### setType

    public void setType(String type)

------------------------------------------------------------------------

### isRestricted

    public boolean isRestricted()

Indicates whether a MutableDynaClass is currently restricted.

If so, no changes to the existing registration of property names, data types, readability, or writeability are allowed.

------------------------------------------------------------------------

### setRestricted

    public void setRestricted(boolean restricted)

Set whether a MutableDynaClass is currently restricted.

If so, no changes to the existing registration of property names, data types, readability, or writeability are allowed.

------------------------------------------------------------------------

### checkCircularInheritance

    protected boolean checkCircularInheritance(ModuleConfig moduleConfig)

Traces the hierarchy of this object to check if any of the ancestors is extending this instance.

**Parameters:**  
`moduleConfig` - The configuration for the module being configured.

**Returns:**  
true if circular inheritance was detected.

------------------------------------------------------------------------

### inheritFormProperties

    protected void inheritFormProperties(FormBeanConfig config)
                                  throws ClassNotFoundException,
                                         IllegalAccessException,
                                         InstantiationException,
                                         InvocationTargetException

Compare the form properties of this bean with that of the given and copy those that are not present.

**Parameters:**  
`config` - The form bean config to copy properties from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(FormBeanConfig)`](../../../../org/apache/struts/config/FormBeanConfig.html.md#inheritFrom(org.apache.struts.config.FormBeanConfig))

------------------------------------------------------------------------

### createActionForm

    public ActionForm createActionForm(ActionServlet servlet)
                                throws IllegalAccessException,
                                       InstantiationException

Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

Although this method is not formally deprecated yet, where possible, the form which accepts an `ActionContext` as an argument is preferred, to help sever direct dependencies on the Servlet API. As the ActionContext becomes more familiar in Struts, this method will almost certainly be deprecated.

**Parameters:**  
`servlet` - The action servlet

**Returns:**  
ActionForm instance

**Throws:**  
`IllegalAccessException` - if the Class or the appropriate constructor is not accessible

`InstantiationException` - if this Class represents an abstract class, an array class, a primitive type, or void; or if instantiation fails for some other reason

------------------------------------------------------------------------

### createActionForm

    public ActionForm createActionForm(ActionContext context)
                                throws IllegalAccessException,
                                       InstantiationException

Create and return an `ActionForm` instance appropriate to the information in this `FormBeanConfig`.

**NOTE:** If the given `ActionContext` is not of type `ServletActionContext` (or a subclass), then the form which is returned will have a null `servlet` property. Some of the subclasses of `ActionForm` included in Struts will later throw a `NullPointerException` in this case.

TODO: Find a way to control this direct dependency on the Servlet API.

**Parameters:**  
`context` - The ActionContext.

**Returns:**  
ActionForm instance

**Throws:**  
`IllegalAccessException` - if the Class or the appropriate constructor is not accessible

`InstantiationException` - if this Class represents an abstract class, an array class, a primitive type, or void; or if instantiation fails for some other reason

------------------------------------------------------------------------

### canReuse

    public boolean canReuse(ActionForm form)

Checks if the given `ActionForm` instance is suitable for use as an alternative to calling this `FormBeanConfig` instance's `createActionForm` method.

**Parameters:**  
`form` - an existing form instance that may be reused.

**Returns:**  
true if the given form can be reused as the form for this config.

------------------------------------------------------------------------

### addFormPropertyConfig

    public void addFormPropertyConfig(FormPropertyConfig config)

Add a new `FormPropertyConfig` instance to the set associated with this module.

**Parameters:**  
`config` - The new configuration instance to be added

**Throws:**  
`IllegalArgumentException` - if this property name has already been defined

------------------------------------------------------------------------

### findFormPropertyConfig

    public FormPropertyConfig findFormPropertyConfig(String name)

Return the form property configuration for the specified property name, if any; otherwise return `null`.

**Parameters:**  
`name` - Form property name to find a configuration for

------------------------------------------------------------------------

### findFormPropertyConfigs

    public FormPropertyConfig[] findFormPropertyConfigs()

Return the form property configurations for this module. If there are none, a zero-length array is returned.

------------------------------------------------------------------------

### freeze

    public void freeze()

Freeze the configuration of this component.

**Overrides:**  
`freeze` in class `BaseConfig`

------------------------------------------------------------------------

### inheritFrom

    public void inheritFrom(FormBeanConfig config)
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
[`processExtends(ModuleConfig)`](../../../../org/apache/struts/config/FormBeanConfig.html.md#processExtends(org.apache.struts.config.ModuleConfig))

------------------------------------------------------------------------

### processExtends

    public void processExtends(ModuleConfig moduleConfig)
                        throws ClassNotFoundException,
                               IllegalAccessException,
                               InstantiationException,
                               InvocationTargetException

Inherit configuration information from the FormBeanConfig that this instance is extending. This method verifies that any form bean config object that it inherits from has also had its processExtends() method called.

**Parameters:**  
`moduleConfig` - The [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config") that this bean is from.

**Throws:**  
`ClassNotFoundException`

`IllegalAccessException`

`InstantiationException`

`InvocationTargetException`

**See Also:**  
[`inheritFrom(FormBeanConfig)`](../../../../org/apache/struts/config/FormBeanConfig.html.md#inheritFrom(org.apache.struts.config.FormBeanConfig))

------------------------------------------------------------------------

### removeFormPropertyConfig

    public void removeFormPropertyConfig(FormPropertyConfig config)

Remove the specified form property configuration instance.

**Parameters:**  
`config` - FormPropertyConfig instance to be removed

------------------------------------------------------------------------

### toString

    public String toString()

Return a String representation of this object.

**Overrides:**  
`toString` in class `Object`

------------------------------------------------------------------------

### formBeanClass

    protected Class formBeanClass()

Return the `Class` instance for the form bean implementation configured by this `FormBeanConfig` instance. This method uses the same algorithm as `RequestUtils.applicationClass()` but is reproduced to avoid a runtime dependence.

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
<td align="left"><a href="class-use/FormBeanConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ExceptionConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/FormPropertyConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/FormBeanConfig.html"><strong>FRAMES</strong></a>    <a href="FormBeanConfig.html"><strong>NO FRAMES</strong></a>    
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
