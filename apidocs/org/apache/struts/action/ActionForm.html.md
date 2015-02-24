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
<td align="left"><a href="class-use/ActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionFormBean.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionForm.html"><strong>FRAMES</strong></a>    <a href="ActionForm.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class ActionForm
------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[DynaActionForm](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action"), [MockFormBean](../../../../org/apache/struts/mock/MockFormBean.html "class in org.apache.struts.mock"), [ValidatorForm](../../../../org/apache/struts/validator/ValidatorForm.html "class in org.apache.struts.validator")

------------------------------------------------------------------------

    public abstract class ActionForm

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`. Such a bean will have had its properties initialized from the corresponding request parameters before the corresponding `Action.execute` method is called.

When the properties of this bean have been populated, but before the `execute` method of the `Action` is called, this bean's `validate` method will be called, which gives the bean a chance to verify that the properties submitted by the user are correct and valid. If this method finds problems, it returns an error messages object that encapsulates those problems, and the controller servlet will return control to the corresponding input form. Otherwise, the `validate` method returns `null`, indicating that everything is acceptable and the corresponding `Action.execute` method should be called.

This class must be subclassed in order to be instantiated. Subclasses should provide property getter and setter methods for all of the bean properties they wish to expose, plus override any of the public or protected methods for which they wish to provide modified functionality.

Because ActionForms are JavaBeans, subclasses should also implement `Serializable`, as required by the JavaBean specification. Some containers require that an object meet all JavaBean requirements in order to use the introspection API upon which ActionForms rely.

**Version:**  
$Rev: 471754 $ $Date: 2005-11-12 08:14:24 -0500 (Sat, 12 Nov 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.action.ActionForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  MultipartRequestHandler`

` multipartRequestHandler`
           The MultipartRequestHandler for this form, can be `null`.

`protected  ActionServlet`

`servlet`
           The servlet instance to which we are attached.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ActionForm()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

` MultipartRequestHandler`

` getMultipartRequestHandler()`
           Return the `MultipartRequestHandler` for this form The reasoning behind this is to give form bean developers control over the lifecycle of their multipart requests through the use of the `finish` and/or `rollback` methods of `MultipartRequestHandler`.

`protected  ActionServlet`

` getServlet()`
           Return the servlet instance to which we are attached.

` ActionServletWrapper`

` getServletWrapper()`
           Return the controller servlet instance to which we are attached.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Can be used to reset bean properties to their default state, as needed.

` void`

` reset(ActionMapping mapping, ServletRequest request)`
           \>Can be used to reset all bean properties to their default state.

` void`

` setMultipartRequestHandler(MultipartRequestHandler multipartRequestHandler)`
           Set the Handler provided for use in dealing with file uploads.

` void`

` setServlet(ActionServlet servlet)`
           Set the servlet instance to which we are attached (if `servlet` is non-null).

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Can be used to validate the properties that have been set for this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

` ActionErrors`

` validate(ActionMapping mapping, ServletRequest request)`
           Can be used to validate the properties that have been set for this non-HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="servlet"></span>

### servlet

    protected transient ActionServlet servlet

The servlet instance to which we are attached.

------------------------------------------------------------------------

<span id="multipartRequestHandler"></span>

### multipartRequestHandler

    protected transient MultipartRequestHandler multipartRequestHandler

The MultipartRequestHandler for this form, can be `null`.

<span id="constructor_detail"></span>

**Constructor Detail**

### ActionForm

    public ActionForm()

<span id="method_detail"></span>

**Method Detail**

### getServlet

    protected ActionServlet getServlet()

Return the servlet instance to which we are attached.

**Returns:**  
The servlet instance to which we are attached.

------------------------------------------------------------------------

### getServletWrapper

    public ActionServletWrapper getServletWrapper()

Return the controller servlet instance to which we are attached. as an `ActionServletWrapper`.

**Returns:**  
An instance of [`ActionServletWrapper`](../../../../org/apache/struts/action/ActionServletWrapper.html.md "class in org.apache.struts.action")

**Since:**  
Struts 1.0.1

**See Also:**  
[`ActionServletWrapper`](../../../../org/apache/struts/action/ActionServletWrapper.html.md "class in org.apache.struts.action")

------------------------------------------------------------------------

### getMultipartRequestHandler

    public MultipartRequestHandler getMultipartRequestHandler()

Return the `MultipartRequestHandler` for this form The reasoning behind this is to give form bean developers control over the lifecycle of their multipart requests through the use of the `finish` and/or `rollback` methods of `MultipartRequestHandler`. This method will return `null` if this form's enctype is not "multipart/form-data".

**Returns:**  
The [`MultipartRequestHandler`](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload") for this form.

**See Also:**  
[`MultipartRequestHandler`](../../../../org/apache/struts/upload/MultipartRequestHandler.html.md "interface in org.apache.struts.upload")

------------------------------------------------------------------------

### setServlet

    public void setServlet(ActionServlet servlet)

Set the servlet instance to which we are attached (if `servlet` is non-null).

**Parameters:**  
`servlet` - The new controller servlet, if any

------------------------------------------------------------------------

### setMultipartRequestHandler

    public void setMultipartRequestHandler(MultipartRequestHandler multipartRequestHandler)

Set the Handler provided for use in dealing with file uploads.

**Parameters:**  
`multipartRequestHandler` - The Handler to use for fileuploads.

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      ServletRequest request)

\>Can be used to reset all bean properties to their default state. This method is called before the properties are repopulated by the controller.

The default implementation attempts to forward to the HTTP version of this method.

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Can be used to reset bean properties to their default state, as needed. This method is called before the properties are repopulated by the controller.

The default implementation does nothing. In practice, the only properties that need to be reset are those which represent checkboxes on a session-scoped form. Otherwise, properties can be given initial values where the field is declared.

If the form is stored in session-scope so that values can be collected over multiple requests (a "wizard"), you must be very careful of which properties, if any, are reset. As mentioned, session-scope checkboxes must be reset to false for any page where this property is set. This is because the client does not submit a checkbox value when it is clear (false). If a session-scoped checkbox is not proactively reset, it can never be set to false.

This method is **not** the appropriate place to initialize form value for an "update" type page (this should be done in a setup Action). You mainly need to worry about setting checkbox values to false; most of the time you can leave this method unimplemented.

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 ServletRequest request)

Can be used to validate the properties that have been set for this non-HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found. If no errors are found, return `null` or an `ActionErrors` object with no recorded error messages.

The default implementation attempts to forward to the HTTP version of this method.

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
The set of validation errors, if validation failed; an empty set or `null` if validation succeeded.

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 HttpServletRequest request)

Can be used to validate the properties that have been set for this HTTP request, and return an `ActionErrors` object that encapsulates any validation errors that have been found. If no errors are found, return `null` or an `ActionErrors` object with no recorded error messages.

The default implementation performs no validation and returns `null`. Subclasses must override this method to provide any validation they wish to perform.

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
The set of validation errors, if validation failed; an empty set or `null` if validation succeeded.

**See Also:**  
[`DynaActionForm`](../../../../org/apache/struts/action/DynaActionForm.html.md "class in org.apache.struts.action")

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
<td align="left"><a href="class-use/ActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/ActionErrors.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ActionFormBean.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ActionForm.html"><strong>FRAMES</strong></a>    <a href="ActionForm.html"><strong>NO FRAMES</strong></a>    
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
