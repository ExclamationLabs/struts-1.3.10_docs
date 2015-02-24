[View Javadoc](../../../../../apidocs/org/apache/struts/validator/FieldChecks.html.md)


    1   /*
    2    * $Id: FieldChecks.java 471754 2006-11-06 14:55:09Z husted $
    3    *
    4    * Licensed to the Apache Software Foundation (ASF) under one
    5    * or more contributor license agreements.  See the NOTICE file
    6    * distributed with this work for additional information
    7    * regarding copyright ownership.  The ASF licenses this file
    8    * to you under the Apache License, Version 2.0 (the
    9    * "License"); you may not use this file except in compliance
    10   * with the License.  You may obtain a copy of the License at
    11   *
    12   *  http://www.apache.org/licenses/LICENSE-2.0
    13   *
    14   * Unless required by applicable law or agreed to in writing,
    15   * software distributed under the License is distributed on an
    16   * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    17   * KIND, either express or implied.  See the License for the
    18   * specific language governing permissions and limitations
    19   * under the License.
    20   */
    21  package org.apache.struts.validator;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.commons.validator.Field;
    26  import org.apache.commons.validator.GenericTypeValidator;
    27  import org.apache.commons.validator.GenericValidator;
    28  import org.apache.commons.validator.UrlValidator;
    29  import org.apache.commons.validator.Validator;
    30  import org.apache.commons.validator.ValidatorAction;
    31  import org.apache.commons.validator.util.ValidatorUtils;
    32  import org.apache.struts.action.ActionMessage;
    33  import org.apache.struts.action.ActionMessages;
    34  import org.apache.struts.util.MessageResources;
    35  import org.apache.struts.util.RequestUtils;
    36  
    37  import javax.servlet.http.HttpServletRequest;
    38  
    39  import java.io.Serializable;
    40  
    41  import java.util.Locale;
    42  import java.util.StringTokenizer;
    43  
    44  /**
    45   * <p> This class contains the default validations that are used in the
    46   * validator-rules.xml file. </p> <p> In general passing in a null or blank
    47   * will return a null Object or a false boolean. However, nulls and blanks do
    48   * not result in an error being added to the errors. </p>
    49   *
    50   * @since Struts 1.1
    51   */
    52  public class FieldChecks implements Serializable {
    53      /**
    54       * Commons Logging instance.
    55       */
    56      private static final Log log = LogFactory.getLog(FieldChecks.class);
    57  
    58      /**
    59       * The message resources for this package.
    60       */
    61      private static MessageResources sysmsgs =
    62          MessageResources.getMessageResources(
    63              "org.apache.struts.validator.LocalStrings");
    64      public static final String FIELD_TEST_NULL = "NULL";
    65      public static final String FIELD_TEST_NOTNULL = "NOTNULL";
    66      public static final String FIELD_TEST_EQUAL = "EQUAL";
    67  
    68      /**
    69       * Checks if the field isn't null and length of the field is greater than
    70       * zero not including whitespace.
    71       *
    72       * @param bean      The bean validation is being performed on.
    73       * @param va        The <code>ValidatorAction</code> that is currently
    74       *                  being performed.
    75       * @param field     The <code>Field</code> object associated with the
    76       *                  current field being validated.
    77       * @param errors    The <code>ActionMessages</code> object to add errors
    78       *                  to if any validation errors occur.
    79       * @param validator The <code>Validator</code> instance, used to access
    80       *                  other field values.
    81       * @param request   Current request object.
    82       * @return true if meets stated requirements, false otherwise.
    83       */
    84      public static boolean validateRequired(Object bean, ValidatorAction va,
    85          Field field, ActionMessages errors, Validator validator,
    86          HttpServletRequest request) {
    87          String value = null;
    88  
    89          value = evaluateBean(bean, field);
    90  
    91          if (GenericValidator.isBlankOrNull(value)) {
    92              errors.add(field.getKey(),
    93                  Resources.getActionMessage(validator, request, va, field));
    94  
    95              return false;
    96          } else {
    97              return true;
    98          }
    99      }
    100 
    101     /**
    102      * Checks if the field isn't null based on the values of other fields.
    103      *
    104      * @param bean      The bean validation is being performed on.
    105      * @param va        The <code>ValidatorAction</code> that is currently
    106      *                  being performed.
    107      * @param field     The <code>Field</code> object associated with the
    108      *                  current field being validated.
    109      * @param errors    The <code>ActionMessages</code> object to add errors
    110      *                  to if any validation errors occur.
    111      * @param validator The <code>Validator</code> instance, used to access
    112      *                  other field values.
    113      * @param request   Current request object.
    114      * @return true if meets stated requirements, false otherwise.
    115      */
    116     public static boolean validateRequiredIf(Object bean, ValidatorAction va,
    117         Field field, ActionMessages errors, Validator validator,
    118         HttpServletRequest request) {
    119         Object form =
    120             validator.getParameterValue(org.apache.commons.validator.Validator.BEAN_PARAM);
    121         String value = null;
    122         boolean required = false;
    123 
    124         value = evaluateBean(bean, field);
    125 
    126         int i = 0;
    127         String fieldJoin = "AND";
    128 
    129         if (!GenericValidator.isBlankOrNull(field.getVarValue("fieldJoin"))) {
    130             fieldJoin = field.getVarValue("fieldJoin");
    131         }
    132 
    133         if (fieldJoin.equalsIgnoreCase("AND")) {
    134             required = true;
    135         }
    136 
    137         while (!GenericValidator.isBlankOrNull(field.getVarValue("field[" + i
    138                     + "]"))) {
    139             String dependProp = field.getVarValue("field[" + i + "]");
    140             String dependTest = field.getVarValue("fieldTest[" + i + "]");
    141             String dependTestValue = field.getVarValue("fieldValue[" + i + "]");
    142             String dependIndexed = field.getVarValue("fieldIndexed[" + i + "]");
    143 
    144             if (dependIndexed == null) {
    145                 dependIndexed = "false";
    146             }
    147 
    148             String dependVal = null;
    149             boolean thisRequired = false;
    150 
    151             if (field.isIndexed() && dependIndexed.equalsIgnoreCase("true")) {
    152                 String key = field.getKey();
    153 
    154                 if ((key.indexOf("[") > -1) && (key.indexOf("]") > -1)) {
    155                     String ind = key.substring(0, key.indexOf(".") + 1);
    156 
    157                     dependProp = ind + dependProp;
    158                 }
    159             }
    160 
    161             dependVal = ValidatorUtils.getValueAsString(form, dependProp);
    162 
    163             if (dependTest.equals(FIELD_TEST_NULL)) {
    164                 if ((dependVal != null) && (dependVal.length() > 0)) {
    165                     thisRequired = false;
    166                 } else {
    167                     thisRequired = true;
    168                 }
    169             }
    170 
    171             if (dependTest.equals(FIELD_TEST_NOTNULL)) {
    172                 if ((dependVal != null) && (dependVal.length() > 0)) {
    173                     thisRequired = true;
    174                 } else {
    175                     thisRequired = false;
    176                 }
    177             }
    178 
    179             if (dependTest.equals(FIELD_TEST_EQUAL)) {
    180                 thisRequired = dependTestValue.equalsIgnoreCase(dependVal);
    181             }
    182 
    183             if (fieldJoin.equalsIgnoreCase("AND")) {
    184                 required = required && thisRequired;
    185             } else {
    186                 required = required || thisRequired;
    187             }
    188 
    189             i++;
    190         }
    191 
    192         if (required) {
    193             if (GenericValidator.isBlankOrNull(value)) {
    194                 errors.add(field.getKey(),
    195                     Resources.getActionMessage(validator, request, va, field));
    196 
    197                 return false;
    198             } else {
    199                 return true;
    200             }
    201         }
    202 
    203         return true;
    204     }
    205 
    206     /**
    207      * Checks if the field matches the regular expression in the field's mask
    208      * attribute.
    209      *
    210      * @param bean      The bean validation is being performed on.
    211      * @param va        The <code>ValidatorAction</code> that is currently
    212      *                  being performed.
    213      * @param field     The <code>Field</code> object associated with the
    214      *                  current field being validated.
    215      * @param errors    The <code>ActionMessages</code> object to add errors
    216      *                  to if any validation errors occur.
    217      * @param validator The <code>Validator</code> instance, used to access
    218      *                  other field values.
    219      * @param request   Current request object.
    220      * @return true if field matches mask, false otherwise.
    221      */
    222     public static boolean validateMask(Object bean, ValidatorAction va,
    223         Field field, ActionMessages errors, Validator validator,
    224         HttpServletRequest request) {
    225         String value = null;
    226 
    227         value = evaluateBean(bean, field);
    228 
    229         try {
    230             String mask =
    231                 Resources.getVarValue("mask", field, validator, request, true);
    232 
    233             if (value != null && value.length()>0
    234                 && !GenericValidator.matchRegexp(value, mask)) {
    235                 errors.add(field.getKey(),
    236                     Resources.getActionMessage(validator, request, va, field));
    237 
    238                 return false;
    239             } else {
    240                 return true;
    241             }
    242         } catch (Exception e) {
    243             processFailure(errors, field, "mask", e);
    244 
    245             return false;
    246         }
    247     }
    248 
    249     /**
    250      * Checks if the field can safely be converted to a byte primitive.
    251      *
    252      * @param bean      The bean validation is being performed on.
    253      * @param va        The <code>ValidatorAction</code> that is currently
    254      *                  being performed.
    255      * @param field     The <code>Field</code> object associated with the
    256      *                  current field being validated.
    257      * @param errors    The <code>ActionMessages</code> object to add errors
    258      *                  to if any validation errors occur.
    259      * @param validator The <code>Validator</code> instance, used to access
    260      *                  other field values.
    261      * @param request   Current request object.
    262      * @return true if valid, false otherwise.
    263      */
    264     public static Object validateByte(Object bean, ValidatorAction va,
    265         Field field, ActionMessages errors, Validator validator,
    266         HttpServletRequest request) {
    267         Object result = null;
    268         String value = null;
    269 
    270         value = evaluateBean(bean, field);
    271 
    272         if (GenericValidator.isBlankOrNull(value)) {
    273             return Boolean.TRUE;
    274         }
    275 
    276         result = GenericTypeValidator.formatByte(value);
    277 
    278         if (result == null) {
    279             errors.add(field.getKey(),
    280                 Resources.getActionMessage(validator, request, va, field));
    281         }
    282 
    283         return (result == null) ? Boolean.FALSE : result;
    284     }
    285 
    286     /**
    287      * Checks if the field can safely be converted to a byte primitive.
    288      *
    289      * @param bean      The bean validation is being performed on.
    290      * @param va        The <code>ValidatorAction</code> that is currently
    291      *                  being performed.
    292      * @param field     The <code>Field</code> object associated with the
    293      *                  current field being validated.
    294      * @param errors    The <code>ActionMessages</code> object to add errors
    295      *                  to if any validation errors occur.
    296      * @param validator The <code>Validator</code> instance, used to access
    297      *                  other field values.
    298      * @param request   Current request object.
    299      * @return true if valid, false otherwise.
    300      */
    301     public static Object validateByteLocale(Object bean, ValidatorAction va,
    302         Field field, ActionMessages errors, Validator validator,
    303         HttpServletRequest request) {
    304         Object result = null;
    305         String value = null;
    306 
    307         value = evaluateBean(bean, field);
    308 
    309         if (GenericValidator.isBlankOrNull(value)) {
    310             return Boolean.TRUE;
    311         }
    312 
    313         Locale locale = RequestUtils.getUserLocale(request, null);
    314 
    315         result = GenericTypeValidator.formatByte(value, locale);
    316 
    317         if (result == null) {
    318             errors.add(field.getKey(),
    319                 Resources.getActionMessage(validator, request, va, field));
    320         }
    321 
    322         return (result == null) ? Boolean.FALSE : result;
    323     }
    324 
    325     /**
    326      * @param bean
    327      * @param field
    328      * @return
    329      */
    330     private static String evaluateBean(Object bean, Field field) {
    331         String value;
    332 
    333         if (isString(bean)) {
    334             value = (String) bean;
    335         } else {
    336             value = ValidatorUtils.getValueAsString(bean, field.getProperty());
    337         }
    338 
    339         return value;
    340     }
    341 
    342     /**
    343      * Checks if the field can safely be converted to a short primitive.
    344      *
    345      * @param bean      The bean validation is being performed on.
    346      * @param va        The <code>ValidatorAction</code> that is currently
    347      *                  being performed.
    348      * @param field     The <code>Field</code> object associated with the
    349      *                  current field being validated.
    350      * @param errors    The <code>ActionMessages</code> object to add errors
    351      *                  to if any validation errors occur.
    352      * @param validator The <code>Validator</code> instance, used to access
    353      *                  other field values.
    354      * @param request   Current request object.
    355      * @return true if valid, false otherwise.
    356      */
    357     public static Object validateShort(Object bean, ValidatorAction va,
    358         Field field, ActionMessages errors, Validator validator,
    359         HttpServletRequest request) {
    360         Object result = null;
    361         String value = null;
    362 
    363         value = evaluateBean(bean, field);
    364 
    365         if (GenericValidator.isBlankOrNull(value)) {
    366             return Boolean.TRUE;
    367         }
    368 
    369         result = GenericTypeValidator.formatShort(value);
    370 
    371         if (result == null) {
    372             errors.add(field.getKey(),
    373                 Resources.getActionMessage(validator, request, va, field));
    374         }
    375 
    376         return (result == null) ? Boolean.FALSE : result;
    377     }
    378 
    379     /**
    380      * Checks if the field can safely be converted to a short primitive.
    381      *
    382      * @param bean      The bean validation is being performed on.
    383      * @param va        The <code>ValidatorAction</code> that is currently
    384      *                  being performed.
    385      * @param field     The <code>Field</code> object associated with the
    386      *                  current field being validated.
    387      * @param errors    The <code>ActionMessages</code> object to add errors
    388      *                  to if any validation errors occur.
    389      * @param validator The <code>Validator</code> instance, used to access
    390      *                  other field values.
    391      * @param request   Current request object.
    392      * @return true if valid, false otherwise.
    393      */
    394     public static Object validateShortLocale(Object bean, ValidatorAction va,
    395         Field field, ActionMessages errors, Validator validator,
    396         HttpServletRequest request) {
    397         Object result = null;
    398         String value = null;
    399 
    400         value = evaluateBean(bean, field);
    401 
    402         if (GenericValidator.isBlankOrNull(value)) {
    403             return Boolean.TRUE;
    404         }
    405 
    406         Locale locale = RequestUtils.getUserLocale(request, null);
    407 
    408         result = GenericTypeValidator.formatShort(value, locale);
    409 
    410         if (result == null) {
    411             errors.add(field.getKey(),
    412                 Resources.getActionMessage(validator, request, va, field));
    413         }
    414 
    415         return (result == null) ? Boolean.FALSE : result;
    416     }
    417 
    418     /**
    419      * Checks if the field can safely be converted to an int primitive.
    420      *
    421      * @param bean      The bean validation is being performed on.
    422      * @param va        The <code>ValidatorAction</code> that is currently
    423      *                  being performed.
    424      * @param field     The <code>Field</code> object associated with the
    425      *                  current field being validated.
    426      * @param errors    The <code>ActionMessages</code> object to add errors
    427      *                  to if any validation errors occur.
    428      * @param validator The <code>Validator</code> instance, used to access
    429      *                  other field values.
    430      * @param request   Current request object.
    431      * @return true if valid, false otherwise.
    432      */
    433     public static Object validateInteger(Object bean, ValidatorAction va,
    434         Field field, ActionMessages errors, Validator validator,
    435         HttpServletRequest request) {
    436         Object result = null;
    437         String value = null;
    438 
    439         value = evaluateBean(bean, field);
    440 
    441         if (GenericValidator.isBlankOrNull(value)) {
    442             return Boolean.TRUE;
    443         }
    444 
    445         result = GenericTypeValidator.formatInt(value);
    446 
    447         if (result == null) {
    448             errors.add(field.getKey(),
    449                 Resources.getActionMessage(validator, request, va, field));
    450         }
    451 
    452         return (result == null) ? Boolean.FALSE : result;
    453     }
    454 
    455     /**
    456      * Checks if the field can safely be converted to an int primitive.
    457      *
    458      * @param bean      The bean validation is being performed on.
    459      * @param va        The <code>ValidatorAction</code> that is currently
    460      *                  being performed.
    461      * @param field     The <code>Field</code> object associated with the
    462      *                  current field being validated.
    463      * @param errors    The <code>ActionMessages</code> object to add errors
    464      *                  to if any validation errors occur.
    465      * @param validator The <code>Validator</code> instance, used to access
    466      *                  other field values.
    467      * @param request   Current request object.
    468      * @return true if valid, false otherwise.
    469      */
    470     public static Object validateIntegerLocale(Object bean, ValidatorAction va,
    471         Field field, ActionMessages errors, Validator validator,
    472         HttpServletRequest request) {
    473         Object result = null;
    474         String value = null;
    475 
    476         value = evaluateBean(bean, field);
    477 
    478         if (GenericValidator.isBlankOrNull(value)) {
    479             return Boolean.TRUE;
    480         }
    481 
    482         Locale locale = RequestUtils.getUserLocale(request, null);
    483 
    484         result = GenericTypeValidator.formatInt(value, locale);
    485 
    486         if (result == null) {
    487             errors.add(field.getKey(),
    488                 Resources.getActionMessage(validator, request, va, field));
    489         }
    490 
    491         return (result == null) ? Boolean.FALSE : result;
    492     }
    493 
    494     /**
    495      * Checks if the field can safely be converted to a long primitive.
    496      *
    497      * @param bean      The bean validation is being performed on.
    498      * @param va        The <code>ValidatorAction</code> that is currently
    499      *                  being performed.
    500      * @param field     The <code>Field</code> object associated with the
    501      *                  current field being validated.
    502      * @param errors    The <code>ActionMessages</code> object to add errors
    503      *                  to if any validation errors occur.
    504      * @param validator The <code>Validator</code> instance, used to access
    505      *                  other field values.
    506      * @param request   Current request object.
    507      * @return true if valid, false otherwise.
    508      */
    509     public static Object validateLong(Object bean, ValidatorAction va,
    510         Field field, ActionMessages errors, Validator validator,
    511         HttpServletRequest request) {
    512         Object result = null;
    513         String value = null;
    514 
    515         value = evaluateBean(bean, field);
    516 
    517         if (GenericValidator.isBlankOrNull(value)) {
    518             return Boolean.TRUE;
    519         }
    520 
    521         result = GenericTypeValidator.formatLong(value);
    522 
    523         if (result == null) {
    524             errors.add(field.getKey(),
    525                 Resources.getActionMessage(validator, request, va, field));
    526         }
    527 
    528         return (result == null) ? Boolean.FALSE : result;
    529     }
    530 
    531     /**
    532      * Checks if the field can safely be converted to a long primitive.
    533      *
    534      * @param bean      The bean validation is being performed on.
    535      * @param va        The <code>ValidatorAction</code> that is currently
    536      *                  being performed.
    537      * @param field     The <code>Field</code> object associated with the
    538      *                  current field being validated.
    539      * @param errors    The <code>ActionMessages</code> object to add errors
    540      *                  to if any validation errors occur.
    541      * @param validator The <code>Validator</code> instance, used to access
    542      *                  other field values.
    543      * @param request   Current request object.
    544      * @return true if valid, false otherwise.
    545      */
    546     public static Object validateLongLocale(Object bean, ValidatorAction va,
    547         Field field, ActionMessages errors, Validator validator,
    548         HttpServletRequest request) {
    549         Object result = null;
    550         String value = null;
    551 
    552         value = evaluateBean(bean, field);
    553 
    554         if (GenericValidator.isBlankOrNull(value)) {
    555             return Boolean.TRUE;
    556         }
    557 
    558         Locale locale = RequestUtils.getUserLocale(request, null);
    559 
    560         result = GenericTypeValidator.formatLong(value, locale);
    561 
    562         if (result == null) {
    563             errors.add(field.getKey(),
    564                 Resources.getActionMessage(validator, request, va, field));
    565         }
    566 
    567         return (result == null) ? Boolean.FALSE : result;
    568     }
    569 
    570     /**
    571      * Checks if the field can safely be converted to a float primitive.
    572      *
    573      * @param bean      The bean validation is being performed on.
    574      * @param va        The <code>ValidatorAction</code> that is currently
    575      *                  being performed.
    576      * @param field     The <code>Field</code> object associated with the
    577      *                  current field being validated.
    578      * @param errors    The <code>ActionMessages</code> object to add errors
    579      *                  to if any validation errors occur.
    580      * @param validator The <code>Validator</code> instance, used to access
    581      *                  other field values.
    582      * @param request   Current request object.
    583      * @return true if valid, false otherwise.
    584      */
    585     public static Object validateFloat(Object bean, ValidatorAction va,
    586         Field field, ActionMessages errors, Validator validator,
    587         HttpServletRequest request) {
    588         Object result = null;
    589         String value = null;
    590 
    591         value = evaluateBean(bean, field);
    592 
    593         if (GenericValidator.isBlankOrNull(value)) {
    594             return Boolean.TRUE;
    595         }
    596 
    597         result = GenericTypeValidator.formatFloat(value);
    598 
    599         if (result == null) {
    600             errors.add(field.getKey(),
    601                 Resources.getActionMessage(validator, request, va, field));
    602         }
    603 
    604         return (result == null) ? Boolean.FALSE : result;
    605     }
    606 
    607     /**
    608      * Checks if the field can safely be converted to a float primitive.
    609      *
    610      * @param bean      The bean validation is being performed on.
    611      * @param va        The <code>ValidatorAction</code> that is currently
    612      *                  being performed.
    613      * @param field     The <code>Field</code> object associated with the
    614      *                  current field being validated.
    615      * @param errors    The <code>ActionMessages</code> object to add errors
    616      *                  to if any validation errors occur.
    617      * @param validator The <code>Validator</code> instance, used to access
    618      *                  other field values.
    619      * @param request   Current request object.
    620      * @return true if valid, false otherwise.
    621      */
    622     public static Object validateFloatLocale(Object bean, ValidatorAction va,
    623         Field field, ActionMessages errors, Validator validator,
    624         HttpServletRequest request) {
    625         Object result = null;
    626         String value = null;
    627 
    628         value = evaluateBean(bean, field);
    629 
    630         if (GenericValidator.isBlankOrNull(value)) {
    631             return Boolean.TRUE;
    632         }
    633 
    634         Locale locale = RequestUtils.getUserLocale(request, null);
    635 
    636         result = GenericTypeValidator.formatFloat(value, locale);
    637 
    638         if (result == null) {
    639             errors.add(field.getKey(),
    640                 Resources.getActionMessage(validator, request, va, field));
    641         }
    642 
    643         return (result == null) ? Boolean.FALSE : result;
    644     }
    645 
    646     /**
    647      * Checks if the field can safely be converted to a double primitive.
    648      *
    649      * @param bean      The bean validation is being performed on.
    650      * @param va        The <code>ValidatorAction</code> that is currently
    651      *                  being performed.
    652      * @param field     The <code>Field</code> object associated with the
    653      *                  current field being validated.
    654      * @param errors    The <code>ActionMessages</code> object to add errors
    655      *                  to if any validation errors occur.
    656      * @param validator The <code>Validator</code> instance, used to access
    657      *                  other field values.
    658      * @param request   Current request object.
    659      * @return true if valid, false otherwise.
    660      */
    661     public static Object validateDouble(Object bean, ValidatorAction va,
    662         Field field, ActionMessages errors, Validator validator,
    663         HttpServletRequest request) {
    664         Object result = null;
    665         String value = null;
    666 
    667         value = evaluateBean(bean, field);
    668 
    669         if (GenericValidator.isBlankOrNull(value)) {
    670             return Boolean.TRUE;
    671         }
    672 
    673         result = GenericTypeValidator.formatDouble(value);
    674 
    675         if (result == null) {
    676             errors.add(field.getKey(),
    677                 Resources.getActionMessage(validator, request, va, field));
    678         }
    679 
    680         return (result == null) ? Boolean.FALSE : result;
    681     }
    682 
    683     /**
    684      * Checks if the field can safely be converted to a double primitive.
    685      *
    686      * @param bean      The bean validation is being performed on.
    687      * @param va        The <code>ValidatorAction</code> that is currently
    688      *                  being performed.
    689      * @param field     The <code>Field</code> object associated with the
    690      *                  current field being validated.
    691      * @param errors    The <code>ActionMessages</code> object to add errors
    692      *                  to if any validation errors occur.
    693      * @param validator The <code>Validator</code> instance, used to access
    694      *                  other field values.
    695      * @param request   Current request object.
    696      * @return true if valid, false otherwise.
    697      */
    698     public static Object validateDoubleLocale(Object bean, ValidatorAction va,
    699         Field field, ActionMessages errors, Validator validator,
    700         HttpServletRequest request) {
    701         Object result = null;
    702         String value = null;
    703 
    704         value = evaluateBean(bean, field);
    705 
    706         if (GenericValidator.isBlankOrNull(value)) {
    707             return Boolean.TRUE;
    708         }
    709 
    710         Locale locale = RequestUtils.getUserLocale(request, null);
    711 
    712         result = GenericTypeValidator.formatDouble(value, locale);
    713 
    714         if (result == null) {
    715             errors.add(field.getKey(),
    716                 Resources.getActionMessage(validator, request, va, field));
    717         }
    718 
    719         return (result == null) ? Boolean.FALSE : result;
    720     }
    721 
    722     /**
    723      * Checks if the field is a valid date. If the field has a datePattern
    724      * variable, that will be used to format <code>java.text.SimpleDateFormat</code>.
    725      * If the field has a datePatternStrict variable, that will be used to
    726      * format <code>java.text.SimpleDateFormat</code> and the length will be
    727      * checked so '2/12/1999' will not pass validation with the format
    728      * 'MM/dd/yyyy' because the month isn't two digits. If no datePattern
    729      * variable is specified, then the field gets the DateFormat.SHORT format
    730      * for the locale. The setLenient method is set to <code>false</code> for
    731      * all variations.
    732      *
    733      * @param bean      The bean validation is being performed on.
    734      * @param va        The <code>ValidatorAction</code> that is currently
    735      *                  being performed.
    736      * @param field     The <code>Field</code> object associated with the
    737      *                  current field being validated.
    738      * @param errors    The <code>ActionMessages</code> object to add errors
    739      *                  to if any validation errors occur.
    740      * @param validator The <code>Validator</code> instance, used to access
    741      *                  other field values.
    742      * @param request   Current request object.
    743      * @return true if valid, false otherwise.
    744      */
    745     public static Object validateDate(Object bean, ValidatorAction va,
    746         Field field, ActionMessages errors, Validator validator,
    747         HttpServletRequest request) {
    748         Object result = null;
    749         String value = null;
    750 
    751         value = evaluateBean(bean, field);
    752 
    753         boolean isStrict = false;
    754         String datePattern =
    755             Resources.getVarValue("datePattern", field, validator, request,
    756                 false);
    757 
    758         if (GenericValidator.isBlankOrNull(datePattern)) {
    759             datePattern =
    760                 Resources.getVarValue("datePatternStrict", field, validator,
    761                     request, false);
    762 
    763             if (!GenericValidator.isBlankOrNull(datePattern)) {
    764                 isStrict = true;
    765             }
    766         }
    767 
    768         Locale locale = RequestUtils.getUserLocale(request, null);
    769 
    770         if (GenericValidator.isBlankOrNull(value)) {
    771             return Boolean.TRUE;
    772         }
    773 
    774         try {
    775             if (GenericValidator.isBlankOrNull(datePattern)) {
    776                 result = GenericTypeValidator.formatDate(value, locale);
    777             } else {
    778                 result =
    779                     GenericTypeValidator.formatDate(value, datePattern, isStrict);
    780             }
    781         } catch (Exception e) {
    782             log.error(e.getMessage(), e);
    783         }
    784 
    785         if (result == null) {
    786             errors.add(field.getKey(),
    787                 Resources.getActionMessage(validator, request, va, field));
    788         }
    789 
    790         return (result == null) ? Boolean.FALSE : result;
    791     }
    792 
    793     /**
    794      * Checks if a fields value is within a range (min &amp; max specified in
    795      * the vars attribute).
    796      *
    797      * @param bean      The bean validation is being performed on.
    798      * @param va        The <code>ValidatorAction</code> that is currently
    799      *                  being performed.
    800      * @param field     The <code>Field</code> object associated with the
    801      *                  current field being validated.
    802      * @param errors    The <code>ActionMessages</code> object to add errors
    803      *                  to if any validation errors occur.
    804      * @param validator The <code>Validator</code> instance, used to access
    805      *                  other field values.
    806      * @param request   Current request object.
    807      * @return True if in range, false otherwise.
    808      */
    809     public static boolean validateLongRange(Object bean, ValidatorAction va,
    810         Field field, ActionMessages errors, Validator validator,
    811         HttpServletRequest request) {
    812         String value = null;
    813 
    814         value = evaluateBean(bean, field);
    815 
    816         if (!GenericValidator.isBlankOrNull(value)) {
    817             try {
    818                 String minVar =
    819                     Resources.getVarValue("min", field, validator, request, true);
    820                 String maxVar =
    821                     Resources.getVarValue("max", field, validator, request, true);
    822                 long longValue = Long.parseLong(value);
    823                 long min = Long.parseLong(minVar);
    824                 long max = Long.parseLong(maxVar);
    825 
    826                 if (min > max) {
    827                     throw new IllegalArgumentException(sysmsgs.getMessage(
    828                             "invalid.range", minVar, maxVar));
    829                 }
    830 
    831                 if (!GenericValidator.isInRange(longValue, min, max)) {
    832                     errors.add(field.getKey(),
    833                         Resources.getActionMessage(validator, request, va, field));
    834 
    835                     return false;
    836                 }
    837             } catch (Exception e) {
    838                 processFailure(errors, field, "longRange", e);
    839 
    840                 return false;
    841             }
    842         }
    843 
    844         return true;
    845     }
    846 
    847     /**
    848      * Checks if a fields value is within a range (min &amp; max specified in
    849      * the vars attribute).
    850      *
    851      * @param bean      The bean validation is being performed on.
    852      * @param va        The <code>ValidatorAction</code> that is currently
    853      *                  being performed.
    854      * @param field     The <code>Field</code> object associated with the
    855      *                  current field being validated.
    856      * @param errors    The <code>ActionMessages</code> object to add errors
    857      *                  to if any validation errors occur.
    858      * @param validator The <code>Validator</code> instance, used to access
    859      *                  other field values.
    860      * @param request   Current request object.
    861      * @return True if in range, false otherwise.
    862      */
    863     public static boolean validateIntRange(Object bean, ValidatorAction va,
    864         Field field, ActionMessages errors, Validator validator,
    865         HttpServletRequest request) {
    866         String value = null;
    867 
    868         value = evaluateBean(bean, field);
    869 
    870         if (!GenericValidator.isBlankOrNull(value)) {
    871             try {
    872                 String minVar =
    873                     Resources.getVarValue("min", field, validator, request, true);
    874                 String maxVar =
    875                     Resources.getVarValue("max", field, validator, request, true);
    876                 int min = Integer.parseInt(minVar);
    877                 int max = Integer.parseInt(maxVar);
    878                 int intValue = Integer.parseInt(value);
    879 
    880                 if (min > max) {
    881                     throw new IllegalArgumentException(sysmsgs.getMessage(
    882                             "invalid.range", minVar, maxVar));
    883                 }
    884 
    885                 if (!GenericValidator.isInRange(intValue, min, max)) {
    886                     errors.add(field.getKey(),
    887                         Resources.getActionMessage(validator, request, va, field));
    888 
    889                     return false;
    890                 }
    891             } catch (Exception e) {
    892                 processFailure(errors, field, "intRange", e);
    893 
    894                 return false;
    895             }
    896         }
    897 
    898         return true;
    899     }
    900 
    901     /**
    902      * Checks if a fields value is within a range (min &amp; max specified in
    903      * the vars attribute).
    904      *
    905      * @param bean      The bean validation is being performed on.
    906      * @param va        The <code>ValidatorAction</code> that is currently
    907      *                  being performed.
    908      * @param field     The <code>Field</code> object associated with the
    909      *                  current field being validated.
    910      * @param errors    The <code>ActionMessages</code> object to add errors
    911      *                  to if any validation errors occur.
    912      * @param validator The <code>Validator</code> instance, used to access
    913      *                  other field values.
    914      * @param request   Current request object.
    915      * @return True if in range, false otherwise.
    916      */
    917     public static boolean validateDoubleRange(Object bean, ValidatorAction va,
    918         Field field, ActionMessages errors, Validator validator,
    919         HttpServletRequest request) {
    920         String value = null;
    921 
    922         value = evaluateBean(bean, field);
    923 
    924         if (!GenericValidator.isBlankOrNull(value)) {
    925             try {
    926                 String minVar =
    927                     Resources.getVarValue("min", field, validator, request, true);
    928                 String maxVar =
    929                     Resources.getVarValue("max", field, validator, request, true);
    930                 double doubleValue = Double.parseDouble(value);
    931                 double min = Double.parseDouble(minVar);
    932                 double max = Double.parseDouble(maxVar);
    933 
    934                 if (min > max) {
    935                     throw new IllegalArgumentException(sysmsgs.getMessage(
    936                             "invalid.range", minVar, maxVar));
    937                 }
    938 
    939                 if (!GenericValidator.isInRange(doubleValue, min, max)) {
    940                     errors.add(field.getKey(),
    941                         Resources.getActionMessage(validator, request, va, field));
    942 
    943                     return false;
    944                 }
    945             } catch (Exception e) {
    946                 processFailure(errors, field, "doubleRange", e);
    947 
    948                 return false;
    949             }
    950         }
    951 
    952         return true;
    953     }
    954 
    955     /**
    956      * Checks if a fields value is within a range (min &amp; max specified in
    957      * the vars attribute).
    958      *
    959      * @param bean      The bean validation is being performed on.
    960      * @param va        The <code>ValidatorAction</code> that is currently
    961      *                  being performed.
    962      * @param field     The <code>Field</code> object associated with the
    963      *                  current field being validated.
    964      * @param errors    The <code>ActionMessages</code> object to add errors
    965      *                  to if any validation errors occur.
    966      * @param validator The <code>Validator</code> instance, used to access
    967      *                  other field values.
    968      * @param request   Current request object.
    969      * @return True if in range, false otherwise.
    970      */
    971     public static boolean validateFloatRange(Object bean, ValidatorAction va,
    972         Field field, ActionMessages errors, Validator validator,
    973         HttpServletRequest request) {
    974         String value = null;
    975 
    976         value = evaluateBean(bean, field);
    977 
    978         if (!GenericValidator.isBlankOrNull(value)) {
    979             try {
    980                 String minVar =
    981                     Resources.getVarValue("min", field, validator, request, true);
    982                 String maxVar =
    983                     Resources.getVarValue("max", field, validator, request, true);
    984                 float floatValue = Float.parseFloat(value);
    985                 float min = Float.parseFloat(minVar);
    986                 float max = Float.parseFloat(maxVar);
    987 
    988                 if (min > max) {
    989                     throw new IllegalArgumentException(sysmsgs.getMessage(
    990                             "invalid.range", minVar, maxVar));
    991                 }
    992 
    993                 if (!GenericValidator.isInRange(floatValue, min, max)) {
    994                     errors.add(field.getKey(),
    995                         Resources.getActionMessage(validator, request, va, field));
    996 
    997                     return false;
    998                 }
    999             } catch (Exception e) {
    1000                 processFailure(errors, field, "floatRange", e);
    1001 
    1002                 return false;
    1003             }
    1004         }
    1005 
    1006         return true;
    1007     }
    1008 
    1009     /**
    1010      * Checks if the field is a valid credit card number.
    1011      *
    1012      * @param bean      The bean validation is being performed on.
    1013      * @param va        The <code>ValidatorAction</code> that is currently
    1014      *                  being performed.
    1015      * @param field     The <code>Field</code> object associated with the
    1016      *                  current field being validated.
    1017      * @param errors    The <code>ActionMessages</code> object to add errors
    1018      *                  to if any validation errors occur.
    1019      * @param validator The <code>Validator</code> instance, used to access
    1020      *                  other field values.
    1021      * @param request   Current request object.
    1022      * @return true if valid, false otherwise.
    1023      */
    1024     public static Object validateCreditCard(Object bean, ValidatorAction va,
    1025         Field field, ActionMessages errors, Validator validator,
    1026         HttpServletRequest request) {
    1027         Object result = null;
    1028         String value = null;
    1029 
    1030         value = evaluateBean(bean, field);
    1031 
    1032         if (GenericValidator.isBlankOrNull(value)) {
    1033             return Boolean.TRUE;
    1034         }
    1035 
    1036         result = GenericTypeValidator.formatCreditCard(value);
    1037 
    1038         if (result == null) {
    1039             errors.add(field.getKey(),
    1040                 Resources.getActionMessage(validator, request, va, field));
    1041         }
    1042 
    1043         return (result == null) ? Boolean.FALSE : result;
    1044     }
    1045 
    1046     /**
    1047      * Checks if a field has a valid e-mail address.
    1048      *
    1049      * @param bean      The bean validation is being performed on.
    1050      * @param va        The <code>ValidatorAction</code> that is currently
    1051      *                  being performed.
    1052      * @param field     The <code>Field</code> object associated with the
    1053      *                  current field being validated.
    1054      * @param errors    The <code>ActionMessages</code> object to add errors
    1055      *                  to if any validation errors occur.
    1056      * @param validator The <code>Validator</code> instance, used to access
    1057      *                  other field values.
    1058      * @param request   Current request object.
    1059      * @return True if valid, false otherwise.
    1060      */
    1061     public static boolean validateEmail(Object bean, ValidatorAction va,
    1062         Field field, ActionMessages errors, Validator validator,
    1063         HttpServletRequest request) {
    1064         String value = null;
    1065 
    1066         value = evaluateBean(bean, field);
    1067 
    1068         if (!GenericValidator.isBlankOrNull(value)
    1069             && !GenericValidator.isEmail(value)) {
    1070             errors.add(field.getKey(),
    1071                 Resources.getActionMessage(validator, request, va, field));
    1072 
    1073             return false;
    1074         } else {
    1075             return true;
    1076         }
    1077     }
    1078 
    1079     /**
    1080      * Checks if the field's length is less than or equal to the maximum
    1081      * value. A <code>Null</code> will be considered an error.
    1082      *
    1083      * @param bean      The bean validation is being performed on.
    1084      * @param va        The <code>ValidatorAction</code> that is currently
    1085      *                  being performed.
    1086      * @param field     The <code>Field</code> object associated with the
    1087      *                  current field being validated.
    1088      * @param errors    The <code>ActionMessages</code> object to add errors
    1089      *                  to if any validation errors occur.
    1090      * @param validator The <code>Validator</code> instance, used to access
    1091      *                  other field values.
    1092      * @param request   Current request object.
    1093      * @return True if stated conditions met.
    1094      */
    1095     public static boolean validateMaxLength(Object bean, ValidatorAction va,
    1096         Field field, ActionMessages errors, Validator validator,
    1097         HttpServletRequest request) {
    1098         String value = null;
    1099 
    1100         value = evaluateBean(bean, field);
    1101 
    1102         if (value != null) {
    1103             try {
    1104                 String maxVar =
    1105                     Resources.getVarValue("maxlength", field, validator,
    1106                         request, true);
    1107                 int max = Integer.parseInt(maxVar);
    1108 
    1109                 boolean isValid = false;
    1110                 String endLth = Resources.getVarValue("lineEndLength", field,
    1111                     validator, request, false);
    1112                 if (GenericValidator.isBlankOrNull(endLth)) {
    1113                     isValid = GenericValidator.maxLength(value, max);
    1114                 } else {
    1115                     isValid = GenericValidator.maxLength(value, max,
    1116                         Integer.parseInt(endLth));
    1117                 }
    1118 
    1119                 if (!isValid) {
    1120                     errors.add(field.getKey(),
    1121                         Resources.getActionMessage(validator, request, va, field));
    1122 
    1123                     return false;
    1124                 }
    1125             } catch (Exception e) {
    1126                 processFailure(errors, field, "maxlength", e);
    1127 
    1128                 return false;
    1129             }
    1130         }
    1131 
    1132         return true;
    1133     }
    1134 
    1135     /**
    1136      * Checks if the field's length is greater than or equal to the minimum
    1137      * value. A <code>Null</code> will be considered an error.
    1138      *
    1139      * @param bean      The bean validation is being performed on.
    1140      * @param va        The <code>ValidatorAction</code> that is currently
    1141      *                  being performed.
    1142      * @param field     The <code>Field</code> object associated with the
    1143      *                  current field being validated.
    1144      * @param errors    The <code>ActionMessages</code> object to add errors
    1145      *                  to if any validation errors occur.
    1146      * @param validator The <code>Validator</code> instance, used to access
    1147      *                  other field values.
    1148      * @param request   Current request object.
    1149      * @return True if stated conditions met.
    1150      */
    1151     public static boolean validateMinLength(Object bean, ValidatorAction va,
    1152         Field field, ActionMessages errors, Validator validator,
    1153         HttpServletRequest request) {
    1154         String value = null;
    1155 
    1156         value = evaluateBean(bean, field);
    1157 
    1158         if (!GenericValidator.isBlankOrNull(value)) {
    1159             try {
    1160                 String minVar =
    1161                     Resources.getVarValue("minlength", field, validator,
    1162                         request, true);
    1163                 int min = Integer.parseInt(minVar);
    1164 
    1165                 boolean isValid = false;
    1166                 String endLth = Resources.getVarValue("lineEndLength", field,
    1167                     validator, request, false);
    1168                 if (GenericValidator.isBlankOrNull(endLth)) {
    1169                     isValid = GenericValidator.minLength(value, min);
    1170                 } else {
    1171                     isValid = GenericValidator.minLength(value, min,
    1172                         Integer.parseInt(endLth));
    1173                 }
    1174 
    1175                 if (!isValid) {
    1176                     errors.add(field.getKey(),
    1177                         Resources.getActionMessage(validator, request, va, field));
    1178 
    1179                     return false;
    1180                 }
    1181             } catch (Exception e) {
    1182                 processFailure(errors, field, "minlength", e);
    1183 
    1184                 return false;
    1185             }
    1186         }
    1187 
    1188         return true;
    1189     }
    1190 
    1191     /**
    1192      * Checks if a field has a valid url. Four optional variables can be
    1193      * specified to configure url validation.
    1194      *
    1195      * <ul>
    1196      *
    1197      * <li>Variable <code>allow2slashes</code> can be set to <code>true</code>
    1198      * or <code>false</code> to control whether two slashes are allowed -
    1199      * default is <code>false</code> (i.e. two slashes are NOT allowed).</li>
    1200      *
    1201      * <li>Variable <code>nofragments</code> can be set to <code>true</code>
    1202      * or <code>false</code> to control whether fragments are allowed -
    1203      * default is <code>false</code> (i.e. fragments ARE allowed).</li>
    1204      *
    1205      * <li>Variable <code>allowallschemes</code> can be set to
    1206      * <code>true</code> or <code>false</code> to control if all schemes are
    1207      * allowed - default is <code>false</code> (i.e. all schemes are NOT
    1208      * allowed).</li>
    1209      *
    1210      * <li>Variable <code>schemes</code> can be set to a comma delimited list
    1211      * of valid schemes. This value is ignored if <code>allowallschemes</code>
    1212      * is set to <code>true</code>. Default schemes allowed are "http",
    1213      * "https" and "ftp" if this variable is not specified.</li>
    1214      *
    1215      * </ul>
    1216      *
    1217      * @param bean      The bean validation is being performed on.
    1218      * @param va        The <code>ValidatorAction</code> that is currently
    1219      *                  being performed.
    1220      * @param field     The <code>Field</code> object associated with the
    1221      *                  current field being validated.
    1222      * @param errors    The <code>ActionMessages</code> object to add errors
    1223      *                  to if any validation errors occur.
    1224      * @param validator The <code>Validator</code> instance, used to access
    1225      *                  other field values.
    1226      * @param request   Current request object.
    1227      * @return True if valid, false otherwise.
    1228      */
    1229     public static boolean validateUrl(Object bean, ValidatorAction va,
    1230         Field field, ActionMessages errors, Validator validator,
    1231         HttpServletRequest request) {
    1232         String value = null;
    1233 
    1234         value = evaluateBean(bean, field);
    1235 
    1236         if (GenericValidator.isBlankOrNull(value)) {
    1237             return true;
    1238         }
    1239 
    1240         // Get the options and schemes Vars
    1241         String allowallschemesVar =
    1242             Resources.getVarValue("allowallschemes", field, validator, request,
    1243                 false);
    1244         boolean allowallschemes = "true".equalsIgnoreCase(allowallschemesVar);
    1245         int options = allowallschemes ? UrlValidator.ALLOW_ALL_SCHEMES : 0;
    1246 
    1247         String allow2slashesVar =
    1248             Resources.getVarValue("allow2slashes", field, validator, request,
    1249                 false);
    1250 
    1251         if ("true".equalsIgnoreCase(allow2slashesVar)) {
    1252             options += UrlValidator.ALLOW_2_SLASHES;
    1253         }
    1254 
    1255         String nofragmentsVar =
    1256             Resources.getVarValue("nofragments", field, validator, request,
    1257                 false);
    1258 
    1259         if ("true".equalsIgnoreCase(nofragmentsVar)) {
    1260             options += UrlValidator.NO_FRAGMENTS;
    1261         }
    1262 
    1263         String schemesVar =
    1264             allowallschemes ? null
    1265                             : Resources.getVarValue("schemes", field,
    1266                 validator, request, false);
    1267 
    1268         // No options or schemes - use GenericValidator as default
    1269         if ((options == 0) && (schemesVar == null)) {
    1270             if (GenericValidator.isUrl(value)) {
    1271                 return true;
    1272             } else {
    1273                 errors.add(field.getKey(),
    1274                     Resources.getActionMessage(validator, request, va, field));
    1275 
    1276                 return false;
    1277             }
    1278         }
    1279 
    1280         // Parse comma delimited list of schemes into a String[]
    1281         String[] schemes = null;
    1282 
    1283         if (schemesVar != null) {
    1284             StringTokenizer st = new StringTokenizer(schemesVar, ",");
    1285 
    1286             schemes = new String[st.countTokens()];
    1287 
    1288             int i = 0;
    1289 
    1290             while (st.hasMoreTokens()) {
    1291                 schemes[i++] = st.nextToken().trim();
    1292             }
    1293         }
    1294 
    1295         // Create UrlValidator and validate with options/schemes
    1296         UrlValidator urlValidator = new UrlValidator(schemes, options);
    1297 
    1298         if (urlValidator.isValid(value)) {
    1299             return true;
    1300         } else {
    1301             errors.add(field.getKey(),
    1302                 Resources.getActionMessage(validator, request, va, field));
    1303 
    1304             return false;
    1305         }
    1306     }
    1307 
    1308     /**
    1309      * Process a validation failure.
    1310      */
    1311     private static void processFailure(ActionMessages errors, Field field,
    1312         String validator, Throwable t) {
    1313         // Log the error
    1314         String logErrorMsg =
    1315             sysmsgs.getMessage("validation.failed", validator,
    1316                 field.getProperty(), t.toString());
    1317 
    1318         log.error(logErrorMsg);
    1319 
    1320         // Add general "system error" message to show to the user
    1321         String userErrorMsg = sysmsgs.getMessage("system.error");
    1322 
    1323         errors.add(field.getKey(), new ActionMessage(userErrorMsg, false));
    1324     }
    1325 
    1326     /**
    1327      * Return <code>true</code> if the specified object is a String or a
    1328      * <code>null</code> value.
    1329      *
    1330      * @param o Object to be tested
    1331      * @return The string value
    1332      */
    1333     protected static boolean isString(Object o) {
    1334         return (o == null) ? true : String.class.isInstance(o);
    1335     }
    1336 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
