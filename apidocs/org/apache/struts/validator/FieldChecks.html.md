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
<td align="left"><a href="class-use/FieldChecks.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/DynaValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/LazyValidatorForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/FieldChecks.html"><strong>FRAMES</strong></a>    <a href="FieldChecks.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.validator
 Class FieldChecks
---------------------------

    java.lang.Object
      org.apache.struts.validator.FieldChecks

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class FieldChecks

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

This class contains the default validations that are used in the validator-rules.xml file.

In general passing in a null or blank will return a null Object or a false boolean. However, nulls and blanks do not result in an error being added to the errors.

**Since:**  
Struts 1.1

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.validator.FieldChecks)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` FIELD_TEST_EQUAL`
            

`static String`

` FIELD_TEST_NOTNULL`
            

`static String`

` FIELD_TEST_NULL`
            

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` FieldChecks()`        
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected static boolean`

` isString(Object o)`
           Return `true` if the specified object is a String or a `null` value.

`static Object`

` validateByte(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a byte primitive.

`static Object`

` validateByteLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a byte primitive.

`static Object`

` validateCreditCard(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field is a valid credit card number.

`static Object`

` validateDate(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field is a valid date.

`static Object`

` validateDouble(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a double primitive.

`static Object`

` validateDoubleLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a double primitive.

`static boolean`

` validateDoubleRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static boolean`

` validateEmail(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a field has a valid e-mail address.

`static Object`

` validateFloat(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a float primitive.

`static Object`

` validateFloatLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a float primitive.

`static boolean`

` validateFloatRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static Object`

` validateInteger(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to an int primitive.

`static Object`

` validateIntegerLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to an int primitive.

`static boolean`

` validateIntRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static Object`

` validateLong(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a long primitive.

`static Object`

` validateLongLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a long primitive.

`static boolean`

` validateLongRange(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a fields value is within a range (min & max specified in the vars attribute).

`static boolean`

` validateMask(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field matches the regular expression in the field's mask attribute.

`static boolean`

` validateMaxLength(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field's length is less than or equal to the maximum value.

`static boolean`

` validateMinLength(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field's length is greater than or equal to the minimum value.

`static boolean`

` validateRequired(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field isn't null and length of the field is greater than zero not including whitespace.

`static boolean`

` validateRequiredIf(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field isn't null based on the values of other fields.

`static Object`

` validateShort(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a short primitive.

`static Object`

` validateShortLocale(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if the field can safely be converted to a short primitive.

`static boolean`

` validateUrl(Object bean, ValidatorAction va, Field field, ActionMessages errors, Validator validator, HttpServletRequest request)`
           Checks if a field has a valid url.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="FIELD_TEST_NULL"></span>

### FIELD\_TEST\_NULL

    public static final String FIELD_TEST_NULL

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.validator.FieldChecks.FIELD_TEST_NULL)

------------------------------------------------------------------------

<span id="FIELD_TEST_NOTNULL"></span>

### FIELD\_TEST\_NOTNULL

    public static final String FIELD_TEST_NOTNULL

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.validator.FieldChecks.FIELD_TEST_NOTNULL)

------------------------------------------------------------------------

<span id="FIELD_TEST_EQUAL"></span>

### FIELD\_TEST\_EQUAL

    public static final String FIELD_TEST_EQUAL

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.validator.FieldChecks.FIELD_TEST_EQUAL)

<span id="constructor_detail"></span>

**Constructor Detail**

### FieldChecks

    public FieldChecks()

<span id="method_detail"></span>

**Method Detail**

### validateRequired

    public static boolean validateRequired(Object bean,
                                           ValidatorAction va,
                                           Field field,
                                           ActionMessages errors,
                                           Validator validator,
                                           HttpServletRequest request)

Checks if the field isn't null and length of the field is greater than zero not including whitespace.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if meets stated requirements, false otherwise.

------------------------------------------------------------------------

### validateRequiredIf

    public static boolean validateRequiredIf(Object bean,
                                             ValidatorAction va,
                                             Field field,
                                             ActionMessages errors,
                                             Validator validator,
                                             HttpServletRequest request)

Checks if the field isn't null based on the values of other fields.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if meets stated requirements, false otherwise.

------------------------------------------------------------------------

### validateMask

    public static boolean validateMask(Object bean,
                                       ValidatorAction va,
                                       Field field,
                                       ActionMessages errors,
                                       Validator validator,
                                       HttpServletRequest request)

Checks if the field matches the regular expression in the field's mask attribute.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if field matches mask, false otherwise.

------------------------------------------------------------------------

### validateByte

    public static Object validateByte(Object bean,
                                      ValidatorAction va,
                                      Field field,
                                      ActionMessages errors,
                                      Validator validator,
                                      HttpServletRequest request)

Checks if the field can safely be converted to a byte primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateByteLocale

    public static Object validateByteLocale(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if the field can safely be converted to a byte primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateShort

    public static Object validateShort(Object bean,
                                       ValidatorAction va,
                                       Field field,
                                       ActionMessages errors,
                                       Validator validator,
                                       HttpServletRequest request)

Checks if the field can safely be converted to a short primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateShortLocale

    public static Object validateShortLocale(Object bean,
                                             ValidatorAction va,
                                             Field field,
                                             ActionMessages errors,
                                             Validator validator,
                                             HttpServletRequest request)

Checks if the field can safely be converted to a short primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateInteger

    public static Object validateInteger(Object bean,
                                         ValidatorAction va,
                                         Field field,
                                         ActionMessages errors,
                                         Validator validator,
                                         HttpServletRequest request)

Checks if the field can safely be converted to an int primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateIntegerLocale

    public static Object validateIntegerLocale(Object bean,
                                               ValidatorAction va,
                                               Field field,
                                               ActionMessages errors,
                                               Validator validator,
                                               HttpServletRequest request)

Checks if the field can safely be converted to an int primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateLong

    public static Object validateLong(Object bean,
                                      ValidatorAction va,
                                      Field field,
                                      ActionMessages errors,
                                      Validator validator,
                                      HttpServletRequest request)

Checks if the field can safely be converted to a long primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateLongLocale

    public static Object validateLongLocale(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if the field can safely be converted to a long primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateFloat

    public static Object validateFloat(Object bean,
                                       ValidatorAction va,
                                       Field field,
                                       ActionMessages errors,
                                       Validator validator,
                                       HttpServletRequest request)

Checks if the field can safely be converted to a float primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateFloatLocale

    public static Object validateFloatLocale(Object bean,
                                             ValidatorAction va,
                                             Field field,
                                             ActionMessages errors,
                                             Validator validator,
                                             HttpServletRequest request)

Checks if the field can safely be converted to a float primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateDouble

    public static Object validateDouble(Object bean,
                                        ValidatorAction va,
                                        Field field,
                                        ActionMessages errors,
                                        Validator validator,
                                        HttpServletRequest request)

Checks if the field can safely be converted to a double primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateDoubleLocale

    public static Object validateDoubleLocale(Object bean,
                                              ValidatorAction va,
                                              Field field,
                                              ActionMessages errors,
                                              Validator validator,
                                              HttpServletRequest request)

Checks if the field can safely be converted to a double primitive.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateDate

    public static Object validateDate(Object bean,
                                      ValidatorAction va,
                                      Field field,
                                      ActionMessages errors,
                                      Validator validator,
                                      HttpServletRequest request)

Checks if the field is a valid date. If the field has a datePattern variable, that will be used to format `java.text.SimpleDateFormat`. If the field has a datePatternStrict variable, that will be used to format `java.text.SimpleDateFormat` and the length will be checked so '2/12/1999' will not pass validation with the format 'MM/dd/yyyy' because the month isn't two digits. If no datePattern variable is specified, then the field gets the DateFormat.SHORT format for the locale. The setLenient method is set to `false` for all variations.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateLongRange

    public static boolean validateLongRange(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if a fields value is within a range (min & max specified in the vars attribute).

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if in range, false otherwise.

------------------------------------------------------------------------

### validateIntRange

    public static boolean validateIntRange(Object bean,
                                           ValidatorAction va,
                                           Field field,
                                           ActionMessages errors,
                                           Validator validator,
                                           HttpServletRequest request)

Checks if a fields value is within a range (min & max specified in the vars attribute).

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if in range, false otherwise.

------------------------------------------------------------------------

### validateDoubleRange

    public static boolean validateDoubleRange(Object bean,
                                              ValidatorAction va,
                                              Field field,
                                              ActionMessages errors,
                                              Validator validator,
                                              HttpServletRequest request)

Checks if a fields value is within a range (min & max specified in the vars attribute).

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if in range, false otherwise.

------------------------------------------------------------------------

### validateFloatRange

    public static boolean validateFloatRange(Object bean,
                                             ValidatorAction va,
                                             Field field,
                                             ActionMessages errors,
                                             Validator validator,
                                             HttpServletRequest request)

Checks if a fields value is within a range (min & max specified in the vars attribute).

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if in range, false otherwise.

------------------------------------------------------------------------

### validateCreditCard

    public static Object validateCreditCard(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if the field is a valid credit card number.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
true if valid, false otherwise.

------------------------------------------------------------------------

### validateEmail

    public static boolean validateEmail(Object bean,
                                        ValidatorAction va,
                                        Field field,
                                        ActionMessages errors,
                                        Validator validator,
                                        HttpServletRequest request)

Checks if a field has a valid e-mail address.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if valid, false otherwise.

------------------------------------------------------------------------

### validateMaxLength

    public static boolean validateMaxLength(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if the field's length is less than or equal to the maximum value. A `Null` will be considered an error.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if stated conditions met.

------------------------------------------------------------------------

### validateMinLength

    public static boolean validateMinLength(Object bean,
                                            ValidatorAction va,
                                            Field field,
                                            ActionMessages errors,
                                            Validator validator,
                                            HttpServletRequest request)

Checks if the field's length is greater than or equal to the minimum value. A `Null` will be considered an error.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if stated conditions met.

------------------------------------------------------------------------

### validateUrl

    public static boolean validateUrl(Object bean,
                                      ValidatorAction va,
                                      Field field,
                                      ActionMessages errors,
                                      Validator validator,
                                      HttpServletRequest request)

Checks if a field has a valid url. Four optional variables can be specified to configure url validation.

-   Variable `allow2slashes` can be set to `true` or `false` to control whether two slashes are allowed - default is `false` (i.e. two slashes are NOT allowed).
-   Variable `nofragments` can be set to `true` or `false` to control whether fragments are allowed - default is `false` (i.e. fragments ARE allowed).
-   Variable `allowallschemes` can be set to `true` or `false` to control if all schemes are allowed - default is `false` (i.e. all schemes are NOT allowed).
-   Variable `schemes` can be set to a comma delimited list of valid schemes. This value is ignored if `allowallschemes` is set to `true`. Default schemes allowed are "http", "https" and "ftp" if this variable is not specified.

**Parameters:**  
`bean` - The bean validation is being performed on.

`va` - The `ValidatorAction` that is currently being performed.

`field` - The `Field` object associated with the current field being validated.

`errors` - The `ActionMessages` object to add errors to if any validation errors occur.

`validator` - The `Validator` instance, used to access other field values.

`request` - Current request object.

**Returns:**  
True if valid, false otherwise.

------------------------------------------------------------------------

### isString

    protected static boolean isString(Object o)

Return `true` if the specified object is a String or a `null` value.

**Parameters:**  
`o` - Object to be tested

**Returns:**  
The string value

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
<td align="left"><a href="class-use/FieldChecks.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/validator/DynaValidatorForm.html.md" title="class in org.apache.struts.validator"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/validator/LazyValidatorForm.html" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/FieldChecks.html"><strong>FRAMES</strong></a>    <a href="FieldChecks.html"><strong>NO FRAMES</strong></a>    
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
