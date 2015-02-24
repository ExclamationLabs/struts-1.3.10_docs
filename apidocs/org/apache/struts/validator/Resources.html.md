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
<td align="left"><a href="class-use/Resources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/LazyValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorActionForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/Resources.html"><strong>FRAMES</strong></a>    <a href="Resources.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator
 Class Resources
---------------------------

    java.lang.Object
      org.apache.struts.validator.Resources

------------------------------------------------------------------------

    public class Resources

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

This class helps provides some useful methods for retrieving objects from different scopes of the application.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 476419 $ $Date: 2005-09-16 23:34:41 -0400 (Fri, 16 Sep 2005) $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` Resources()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

`static ActionMessage`

` getActionMessage(HttpServletRequest request, ValidatorAction va, Field field)`
           **Deprecated.** *Use getActionMessage(Validator, HttpServletRequest, ValidatorAction, Field) method instead*

`static ActionMessage`

` getActionMessage(Validator validator, HttpServletRequest request, ValidatorAction va, Field field)`
           Gets the `ActionMessage` based on the `ValidatorAction` message and the `Field`'s arg objects.

`static String[]`

` getArgs(String actionName, MessageResources messages, Locale locale, Field field)`
           Gets the message arguments based on the current `ValidatorAction` and `Field`.

`static String`

` getMessage(HttpServletRequest request, String key)`
           Gets the `Locale` sensitive value based on the key passed in.

`static String`

` getMessage(MessageResources messages, Locale locale, String key)`
           Gets the `Locale` sensitive value based on the key passed in.

`static String`

` getMessage(MessageResources messages, Locale locale, ValidatorAction va, Field field)`
           Gets the locale sensitive message based on the `ValidatorAction` message and the `Field`'s arg objects.

`static String`

` getMessage(ServletContext application, HttpServletRequest request, MessageResources defaultMessages, Locale locale, ValidatorAction va, Field field)`
           Gets the `Locale` sensitive value based on the key passed in.

`static MessageResources`

` getMessageResources(HttpServletRequest request)`
           Retrieve `MessageResources` for the module.

`static MessageResources`

` getMessageResources(ServletContext application, HttpServletRequest request, String bundle)`
           Retrieve `MessageResources` for the module and bundle.

`static ValidatorResources`

` getValidatorResources(ServletContext application, HttpServletRequest request)`
           Retrieve `ValidatorResources` for the current module.

`static String`

` getVarValue(String varName, Field field, Validator validator, HttpServletRequest request, boolean required)`
           Get the value of a variable.

`static String`

` getVarValue(Var var, ServletContext application, HttpServletRequest request, boolean required)`
           Get the value of a variable.

`static Validator`

` initValidator(String key, Object bean, ServletContext application, HttpServletRequest request, ActionMessages errors, int page)`
           Initialize the `Validator` to perform validation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### Resources

    public Resources()

<span id="method_detail"></span>

**Method Detail**

### getValidatorResources

    public static ValidatorResources getValidatorResources(ServletContext application,
                                                           HttpServletRequest request)

Retrieve `ValidatorResources` for the current module.

**Parameters:**  
`application` - Application Context

`request` - The ServletRequest

------------------------------------------------------------------------

### getMessageResources

    public static MessageResources getMessageResources(HttpServletRequest request)

Retrieve `MessageResources` for the module.

**Parameters:**  
`request` - the servlet request

------------------------------------------------------------------------

### getMessageResources

    public static MessageResources getMessageResources(ServletContext application,
                                                       HttpServletRequest request,
                                                       String bundle)

Retrieve `MessageResources` for the module and bundle.

**Parameters:**  
`application` - the servlet context

`request` - the servlet request

`bundle` - the bundle key

------------------------------------------------------------------------

### getVarValue

    public static String getVarValue(String varName,
                                     Field field,
                                     Validator validator,
                                     HttpServletRequest request,
                                     boolean required)

Get the value of a variable.

**Parameters:**  
`varName` - The variable name

`field` - the validator Field

`validator` - The Validator

`request` - the servlet request

`required` - Whether the variable is mandatory

**Returns:**  
The variable's value

------------------------------------------------------------------------

### getVarValue

    public static String getVarValue(Var var,
                                     ServletContext application,
                                     HttpServletRequest request,
                                     boolean required)

Get the value of a variable.

**Parameters:**  
`var` - the validator variable

`application` - The ServletContext

`request` - the servlet request

`required` - Whether the variable is mandatory

**Returns:**  
The variables values

------------------------------------------------------------------------

### getMessage

    public static String getMessage(MessageResources messages,
                                    Locale locale,
                                    String key)

Gets the `Locale` sensitive value based on the key passed in.

**Parameters:**  
`messages` - The Message resources

`locale` - The locale.

`key` - Key used to lookup the message

------------------------------------------------------------------------

### getMessage

    public static String getMessage(HttpServletRequest request,
                                    String key)

Gets the `Locale` sensitive value based on the key passed in.

**Parameters:**  
`request` - servlet request

`key` - the request key

------------------------------------------------------------------------

### getMessage

    public static String getMessage(MessageResources messages,
                                    Locale locale,
                                    ValidatorAction va,
                                    Field field)

Gets the locale sensitive message based on the `ValidatorAction` message and the `Field`'s arg objects.

**Parameters:**  
`messages` - The Message resources

`locale` - The locale

`va` - The Validator Action

`field` - The Validator Field

------------------------------------------------------------------------

### getMessage

    public static String getMessage(ServletContext application,
                                    HttpServletRequest request,
                                    MessageResources defaultMessages,
                                    Locale locale,
                                    ValidatorAction va,
                                    Field field)

Gets the `Locale` sensitive value based on the key passed in.

**Parameters:**  
`application` - the servlet context

`request` - the servlet request

`defaultMessages` - The default Message resources

`locale` - The locale

`va` - The Validator Action

`field` - The Validator Field

------------------------------------------------------------------------

### getActionMessage

    public static ActionMessage getActionMessage(HttpServletRequest request,
                                                 ValidatorAction va,
                                                 Field field)

**Deprecated.** *Use getActionMessage(Validator, HttpServletRequest, ValidatorAction, Field) method instead*

Gets the `ActionMessage` based on the `ValidatorAction` message and the `Field`'s arg objects.

**Note:** this method does not respect bundle information stored with the field's \<msg\> or \<arg\> elements, and localization will not work for alternative resource bundles. This method is deprecated for this reason, and you should use [`getActionMessage(Validator,HttpServletRequest,ValidatorAction,Field)`](../../../../org/apache/struts/validator/Resources.html.md#getActionMessage(org.apache.commons.validator.Validator,%20javax.servlet.http.HttpServletRequest,%20org.apache.commons.validator.ValidatorAction,%20org.apache.commons.validator.Field)) instead.

**Parameters:**  
`request` - the servlet request

`va` - Validator action

`field` - the validator Field

------------------------------------------------------------------------

### getActionMessage

    public static ActionMessage getActionMessage(Validator validator,
                                                 HttpServletRequest request,
                                                 ValidatorAction va,
                                                 Field field)

Gets the `ActionMessage` based on the `ValidatorAction` message and the `Field`'s arg objects.

**Parameters:**  
`validator` - the Validator

`request` - the servlet request

`va` - Validator action

`field` - the validator Field

------------------------------------------------------------------------

### getArgs

    public static String[] getArgs(String actionName,
                                   MessageResources messages,
                                   Locale locale,
                                   Field field)

Gets the message arguments based on the current `ValidatorAction` and `Field`.

**Parameters:**  
`actionName` - action name

`messages` - message resources

`locale` - the locale

`field` - the validator field

------------------------------------------------------------------------

### initValidator

    public static Validator initValidator(String key,
                                          Object bean,
                                          ServletContext application,
                                          HttpServletRequest request,
                                          ActionMessages errors,
                                          int page)

Initialize the `Validator` to perform validation.

**Parameters:**  
`key` - The key that the validation rules are under (the form elements name attribute).

`bean` - The bean validation is being performed on.

`application` - servlet context

`request` - The current request object.

`errors` - The object any errors will be stored in.

`page` - This in conjunction with the page property of a `Field` can control the processing of fields. If the field's page is less than or equal to this page value, it will be processed.

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
<td align="left"><a href="class-use/Resources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/LazyValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/ValidatorActionForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/Resources.html"><strong>FRAMES</strong></a>    <a href="Resources.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
