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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMessages.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMessages.html"><strong>FRAMES</strong></a>    <a href="ActionMessages.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Class
 org.apache.struts.action.ActionMessages**
------------------------------------------

Packages that use [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action")

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

[**org.apache.struts.validator.validwhen**](#org.apache.struts.validator.validwhen)

Generated classes by antlr to support the `validwhen` validator. 

 

<span id="org.apache.struts.action"></span>

Uses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

 

Subclasses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html)

` class`

`ActionErrors`
           A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) that return [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

`protected  ActionMessages`

`Action.getErrors(HttpServletRequest request)`
           Retrieves any existing errors placed in the request by previous actions.

`protected  ActionMessages`

`Action.getMessages(HttpServletRequest request)`
            Retrieves any existing messages placed in the request by previous actions.

 

Methods in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

` void`

`ActionMessages.add(ActionMessages actionMessages)`
           Adds the messages from the given `ActionMessages` object to this set of messages.

`protected  void`

`Action.addErrors(HttpServletRequest request, ActionMessages errors)`
           Adds the specified errors keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required.

`protected  void`

`Action.addMessages(HttpServletRequest request, ActionMessages messages)`
           Adds the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

`protected  void`

`Action.saveErrors(HttpServletRequest request, ActionMessages errors)`
           Save the specified error messages keys into the appropriate request attribute for use by the \.html.md:errors\> tag, if any messages are required.

`protected  void`

`Action.saveErrors(HttpSession session, ActionMessages errors)`
           Save the specified error messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="false") or \<html:errors\>, if any error messages are required.

`protected  void`

`Action.saveMessages(HttpServletRequest request, ActionMessages messages)`
           Save the specified messages keys into the appropriate request attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

`protected  void`

`Action.saveMessages(HttpSession session, ActionMessages messages)`
           Save the specified messages keys into the appropriate session attribute for use by the \.html.md:messages\> tag (if messages="true" is set), if any messages are required.

 

| Constructors in [org.apache.struts.action](../../../../../org/apache/struts/action/package-summary.html.md) with parameters of type [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action") |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ActionMessages(ActionMessages messages)`                                                                                                                                                                                                         
            Create an `ActionMessages` object initialized with the given messages.                                                                                                                                                                   |

 

<span id="org.apache.struts.chain.contexts"></span>

Uses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html)

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) that return [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

` ActionMessages`

`ServletActionContext.getErrors()`
            

` ActionMessages`

`ActionContextBase.getErrors()`
            

` ActionMessages`

`ActionContext.getErrors()`
            Retrieve error messages from an internal cache, creating an empty cache if one is not already present.

` ActionMessages`

`ServletActionContext.getMessages()`
            

` ActionMessages`

`ActionContextBase.getMessages()`
            

` ActionMessages`

`ActionContext.getMessages()`
            Retrieve messages from an internal cache, creating an empty cache if one is not already present.

 

Methods in [org.apache.struts.chain.contexts](../../../../../org/apache/struts/chain/contexts/package-summary.html.md) with parameters of type [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

` void`

`ActionContextBase.addActionMessages(String key, ActionMessages messages)`
            Add the given messages to a cache stored in this Context, under key.

` void`

`ServletActionContext.addErrors(ActionMessages errors)`
            

` void`

`ActionContextBase.addErrors(ActionMessages errors)`
            

` void`

`ActionContext.addErrors(ActionMessages errors)`
            Append the given errors keys to an internal cache, creating the cache if one is not already present.

` void`

`ServletActionContext.addMessages(ActionMessages messages)`
            

` void`

`ActionContextBase.addMessages(ActionMessages messages)`
            

` void`

`ActionContext.addMessages(ActionMessages messages)`
            Append the given messages keys to an internal cache, creating the cache if one is not already present.

` void`

`ActionContextBase.saveActionMessages(String key, ActionMessages messages)`
            Save the given ActionMessages into the request scope under the given key, clearing the attribute if the messages are empty or null.

` void`

`ActionContextBase.saveActionMessages(String scopeId, String key, ActionMessages messages)`
           Save the given `messages` into the map identified by the given `scopeId` under the given `key`.

` void`

`ServletActionContext.saveErrors(ActionMessages errors)`
            

` void`

`ActionContextBase.saveErrors(ActionMessages errors)`
            

` void`

`ActionContext.saveErrors(ActionMessages errors)`
            Save the given error messages to the internal cache, clearing any previous messages in the cache.

` void`

`ServletActionContext.saveMessages(ActionMessages messages)`
            

` void`

`ActionContextBase.saveMessages(ActionMessages messages)`
            

` void`

`ActionContext.saveMessages(ActionMessages messages)`
            Save the given messages to the internal cache, clearing any previous messages in the cache.

` void`

`ActionContextBase.saveMessages(String scope, ActionMessages messages)`
            Adapt a legacy form of SaveMessages to the ActionContext API by storing the ActoinMessages under the default scope.

` void`

`ActionContext.saveMessages(String scope, ActionMessages messages)`
            Save the given messages to the internal cache, clearing any previous messages in the cache, but only for the specified scope.

 

<span id="org.apache.struts.config"></span>

Uses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html)

 

Methods in [org.apache.struts.config](../../../../../org/apache/struts/config/package-summary.html.md) that return [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

` ActionMessages`

`ConfigHelperInterface.getActionMessages()`
            The `org.apache.struts.action.ActionFormBeans` collection for this application.

` ActionMessages`

`ConfigHelper.getActionMessages()`
            

 

<span id="org.apache.struts.validator"></span>

Uses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html)

 

Methods in [org.apache.struts.validator](../../../../../org/apache/struts/validator/package-summary.html.md) with parameters of type [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

`static Validator`

`Resources.initValidator(String key, Object bean, ServletContext application, HttpServletRequest request, ActionMessages errors, int page)`
           Initialize the `Validator` to perform validation.

`static Object`

`FieldChecks.validateByte(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a byte primitive.

`static Object`

`FieldChecks.validateByteLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a byte primitive.

`static Object`

`FieldChecks.validateCreditCard(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field is a valid credit card number.

`static Object`

`FieldChecks.validateDate(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field is a valid date.

`static Object`

`FieldChecks.validateDouble(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a double primitive.

`static Object`

`FieldChecks.validateDoubleLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a double primitive.

`static boolean`

`FieldChecks.validateDoubleRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static boolean`

`FieldChecks.validateEmail(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a field has a valid e-mail address.

`static Object`

`FieldChecks.validateFloat(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a float primitive.

`static Object`

`FieldChecks.validateFloatLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a float primitive.

`static boolean`

`FieldChecks.validateFloatRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static Object`

`FieldChecks.validateInteger(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to an int primitive.

`static Object`

`FieldChecks.validateIntegerLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to an int primitive.

`static boolean`

`FieldChecks.validateIntRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static Object`

`FieldChecks.validateLong(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a long primitive.

`static Object`

`FieldChecks.validateLongLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a long primitive.

`static boolean`

`FieldChecks.validateLongRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static boolean`

`FieldChecks.validateMask(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field matches the regular expression in the field's mask attribute.

`static boolean`

`FieldChecks.validateMaxLength(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field's length is less than or equal to the maximum value.

`static boolean`

`FieldChecks.validateMinLength(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field's length is greater than or equal to the minimum value.

`static boolean`

`FieldChecks.validateRequired(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field isn't null and length of the field is greater than zero not including whitespace.

`static boolean`

`FieldChecks.validateRequiredIf(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field isn't null based on the values of other fields.

`static Object`

`FieldChecks.validateShort(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a short primitive.

`static Object`

`FieldChecks.validateShortLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a short primitive.

`static boolean`

`FieldChecks.validateUrl(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a field has a valid url.

 

<span id="org.apache.struts.validator.validwhen"></span>

Uses of [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html.md "class in org.apache.struts.action") in [org.apache.struts.validator.validwhen](../../../../../org/apache/struts/validator/validwhen/package-summary.html)

 

Methods in [org.apache.struts.validator.validwhen](../../../../../org/apache/struts/validator/validwhen/package-summary.html.md) with parameters of type [ActionMessages](../../../../../org/apache/struts/action/ActionMessages.html "class in org.apache.struts.action")

`static boolean`

`ValidWhen.validateValidWhen(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field matches the boolean expression specified in `test` parameter.

 

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="../package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"><a href="../../../../../org/apache/struts/action/ActionMessages.html.md" title="class in org.apache.struts.action"><strong>Class</strong></a> </td>
<td align="left"> <strong>Use</strong> </td>
<td align="left"><a href="../package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/action//class-useActionMessages.html"><strong>FRAMES</strong></a>    <a href="ActionMessages.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
