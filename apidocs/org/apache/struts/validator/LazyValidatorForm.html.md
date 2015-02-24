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
<td align="left"><a href="class-use/LazyValidatorForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/FieldChecks.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/Resources.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/LazyValidatorForm.html"><strong>FRAMES</strong></a>    <a href="LazyValidatorForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.BeanValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator
 Class LazyValidatorForm
---------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.validator.BeanValidatorForm
                  org.apache.struts.validator.LazyValidatorForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [DynaBean](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/DynaBean.html?is-external=true "class or interface in org.apache.commons.beanutils")

------------------------------------------------------------------------

    public class LazyValidatorForm

extends [BeanValidatorForm](../../../../org/apache/struts/validator/BeanValidatorForm.html.md "class in org.apache.struts.validator")

Struts *Lazy* `ActionForm` which *wraps* a `LazyDynaBean`.

There isn't really that much to this implementation as most of the *lazy* behaviour is in `LazyDynaBean` and *wrapping* the `LazyDynaBean` is handled in the parent `BeanValidatorForm`. The only thing it really does is populate *indexed* properties which are a `List` type with a `LazyDynaBean` in the `get(name, index)` method.

*Lazy* DynaBeans provide several types of *lazy* behaviour:

-   ***lazy* property addition** - properties which do not exist are automatically added.
-   ***lazy* List facilities** - automatically *grows* a `List` or `Array` to accomodate the index value being set.
-   ***lazy* List creation** - automatic creation of a `List` or `Array` for *indexed* properties, if it doesn't exist.
-   ***lazy* Map creation** - automatic creation of a `Map` for *mapped* properties, if it doesn't exist.

Using this *lazy* `ActionForm` means that you don't have to define the ActionForm's properties in the `struts-config.xml`. However, a word of warning, everything in the Request gets populated into this `ActionForm` circumventing the normal *firewall* function of Struts forms. Therefore you should only *take out* of this form properties you expect to be there rather than blindly populating all the properties into the business tier.

Having said that it is not necessary to pre-define properties in the `struts-config.xml`, it is useful to sometimes do so for *mapped* or *indexed* properties. For example, if you want to use a different `Map` implementation from the default `HashMap` or an array for indexed properties, rather than the default `List` type:


       <form-bean name="myForm" type="org.apache.struts.validator.LazyValidatorForm">
         <form-property name="myMap" type="java.util.TreeMap" />
         <form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]"
     />
       </form-bean>
     

Another reason for defining *indexed* properties in the `struts-config.xml` is that if you are validating indexed properties using the Validator and none are submitted then the indexed property will be `null` which causes validator to fail. Pre-defining them in the `struts-config.xml` will result in a zero-length indexed property (array or List) being instantiated, avoiding an issue with validator in that circumstance.

This implementation validates using the ActionForm *name*. If you require a version that validates according to the *path* then it can be easily created in the following manner:


        public class MyLazyForm extends LazyValidatorForm {

            public MyLazyForm () {
                super();
                setPathValidation(true);
            }

        }
     

Rather than using this class, another alternative is to either use a `LazyDynaBean` or custom version of `LazyDynaBean` directly. Struts now automatically *wraps* objects which are not `ActionForms` in a `BeanValidatorForm`. For example:


       <form-bean name="myForm" type="org.apache.commons.beanutils.LazyDynaBean">
         <form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]"
     />
       </form-bean>
     

**Since:**  
Struts 1.2.6

**Version:**  
$Rev: 562121 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

**See Also:**  
[Commons BeanUtils JavaDoc](http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/package-summary.html.md#dynamic.lazy), [Serialized Form](../../../../serialized-form.html#org.apache.struts.validator.LazyValidatorForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.validator.BeanValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[BeanValidatorForm](../../../../org/apache/struts/validator/BeanValidatorForm.html.md "class in org.apache.struts.validator")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` dynaBean,  logger,  pathValidation`                                                                                                                                                  |

 <span id="fields_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `page,  validatorResults`                                                                                                                                                      |

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` multipartRequestHandler, servlet`                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                            |
|------------------------------------------------------------------------------------|
| ` LazyValidatorForm()`                                                             
            Default Constructor which creates a `LazyDynaBean` to *back* this form.  |
| ` LazyValidatorForm(DynaBean bean)`                                                
                                                                                     |

  <span id="method_summary"></span>

**Method Summary**

` Object`

` get(String name, int index)`
           Return an indexed property value.

` Map`

` getMap()`
           Return the `Map` containing the property values.

`protected  DynaBean`

` newIndexedBean(String name)`
           Creates new `DynaBean` instances to populate an 'indexed' property of beans - defaults to `LazyDynaBean` type.

 <span id="methods_inherited_from_class_org.apache.struts.validator.BeanValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[BeanValidatorForm](../../../../org/apache/struts/validator/BeanValidatorForm.html.md "class in org.apache.struts.validator")**               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` contains,  get,  get,  getDynaBean,  getDynaClass,  getInstance,  getStrutsConfigFormName,  getValidationKey,  initialize,  isPathValidation,  remove,  set,  set,  set,  setPathValidation,  size` |

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html.md "class in org.apache.struts.validator")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getPage,  getResultValueMap,  getValidatorResults,  reset,  setPage,  setValidatorResults,  validate`                                                                         |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getMultipartRequestHandler,  getServlet,  getServletWrapper,  reset,  setMultipartRequestHandler,  setServlet,  validate`                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### LazyValidatorForm

    public LazyValidatorForm()

Default Constructor which creates a `LazyDynaBean` to *back* this form.

------------------------------------------------------------------------

### LazyValidatorForm

    public LazyValidatorForm(DynaBean bean)

<span id="method_detail"></span>

**Method Detail**

### get

    public Object get(String name,
                      int index)

Return an indexed property value.

If the "indexed" property is a `List` type then any missing values are populated with a bean (created in the `newIndexedBean(name)` method - in this implementation this is a `LazyDynaBean` type.

**Specified by:**  
`get` in interface `DynaBean`

**Overrides:**  
` get` in class `BeanValidatorForm`

<!-- -->

**Parameters:**  
`name` - Name of the property whose value is to be retrieved

`index` - Index of the value to be retrieved

------------------------------------------------------------------------

### getMap

    public Map getMap()

Return the `Map` containing the property values.

Provided so that properties can be access using JSTL.

------------------------------------------------------------------------

### newIndexedBean

    protected DynaBean newIndexedBean(String name)

Creates new `DynaBean` instances to populate an 'indexed' property of beans - defaults to `LazyDynaBean` type.

Override this method if you require a different type of `DynaBean`.

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
<td align="left"><a href="class-use/LazyValidatorForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/FieldChecks.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/Resources.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/LazyValidatorForm.html"><strong>FRAMES</strong></a>    <a href="LazyValidatorForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.BeanValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
