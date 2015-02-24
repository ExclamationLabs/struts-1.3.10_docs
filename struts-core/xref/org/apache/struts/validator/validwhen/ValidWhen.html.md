[View Javadoc](../../../../../../apidocs/org/apache/struts/validator/validwhen/ValidWhen.html.md)


    1   /*
    2    * $Id: ValidWhen.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.validator.validwhen;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.commons.validator.Field;
    26  import org.apache.commons.validator.Validator;
    27  import org.apache.commons.validator.ValidatorAction;
    28  import org.apache.commons.validator.util.ValidatorUtils;
    29  import org.apache.struts.action.ActionMessage;
    30  import org.apache.struts.action.ActionMessages;
    31  import org.apache.struts.util.MessageResources;
    32  import org.apache.struts.validator.Resources;
    33  
    34  import javax.servlet.http.HttpServletRequest;
    35  
    36  import java.io.StringReader;
    37  
    38  /**
    39   * This class contains the validwhen validation that is used in the
    40   * validator-rules.xml file.
    41   *
    42   * @since Struts 1.2
    43   */
    44  public class ValidWhen {
    45      /**
    46       * Commons Logging instance.
    47       */
    48      private static final Log log = LogFactory.getLog(ValidWhen.class);
    49  
    50      /**
    51       * The message resources for this package.
    52       */
    53      private static MessageResources sysmsgs =
    54          MessageResources.getMessageResources(
    55              "org.apache.struts.validator.LocalStrings");
    56  
    57      /**
    58       * Returns true if <code>obj</code> is null or a String.
    59       */
    60      private static boolean isString(Object obj) {
    61          return (obj == null) ? true : String.class.isInstance(obj);
    62      }
    63  
    64      /**
    65       * Checks if the field matches the boolean expression specified in
    66       * <code>test</code> parameter.
    67       *
    68       * @param bean    The bean validation is being performed on.
    69       * @param va      The <code>ValidatorAction</code> that is currently being
    70       *                performed.
    71       * @param field   The <code>Field</code> object associated with the
    72       *                current field being validated.
    73       * @param errors  The <code>ActionMessages</code> object to add errors to
    74       *                if any validation errors occur.
    75       * @param request Current request object.
    76       * @return <code>true</code> if meets stated requirements,
    77       *         <code>false</code> otherwise.
    78       */
    79      public static boolean validateValidWhen(Object bean, ValidatorAction va,
    80          Field field, ActionMessages errors, Validator validator,
    81          HttpServletRequest request) {
    82          Object form = validator.getParameterValue(Validator.BEAN_PARAM);
    83          String value = null;
    84          boolean valid = false;
    85          int index = -1;
    86  
    87          if (field.isIndexed()) {
    88              String key = field.getKey();
    89  
    90              final int leftBracket = key.indexOf("[");
    91              final int rightBracket = key.indexOf("]");
    92  
    93              if ((leftBracket > -1) && (rightBracket > -1)) {
    94                  index =
    95                      Integer.parseInt(key.substring(leftBracket + 1,
    96                          rightBracket));
    97              }
    98          }
    99  
    100         if (isString(bean)) {
    101             value = (String) bean;
    102         } else {
    103             value = ValidatorUtils.getValueAsString(bean, field.getProperty());
    104         }
    105 
    106         String test = null;
    107 
    108         try {
    109             test =
    110                 Resources.getVarValue("test", field, validator, request, true);
    111         } catch (IllegalArgumentException ex) {
    112             String logErrorMsg =
    113                 sysmsgs.getMessage("validation.failed", "validwhen",
    114                     field.getProperty(), ex.toString());
    115 
    116             log.error(logErrorMsg);
    117 
    118             String userErrorMsg = sysmsgs.getMessage("system.error");
    119 
    120             errors.add(field.getKey(), new ActionMessage(userErrorMsg, false));
    121 
    122             return false;
    123         }
    124 
    125         // Create the Lexer
    126         ValidWhenLexer lexer = null;
    127 
    128         try {
    129             lexer = new ValidWhenLexer(new StringReader(test));
    130         } catch (Exception ex) {
    131             String logErrorMsg =
    132                 "ValidWhenLexer Error for field ' " + field.getKey() + "' - "
    133                 + ex;
    134 
    135             log.error(logErrorMsg);
    136 
    137             String userErrorMsg = sysmsgs.getMessage("system.error");
    138 
    139             errors.add(field.getKey(), new ActionMessage(userErrorMsg, false));
    140 
    141             return false;
    142         }
    143 
    144         // Create the Parser
    145         ValidWhenParser parser = null;
    146 
    147         try {
    148             parser = new ValidWhenParser(lexer);
    149         } catch (Exception ex) {
    150             String logErrorMsg =
    151                 "ValidWhenParser Error for field ' " + field.getKey() + "' - "
    152                 + ex;
    153 
    154             log.error(logErrorMsg);
    155 
    156             String userErrorMsg = sysmsgs.getMessage("system.error");
    157 
    158             errors.add(field.getKey(), new ActionMessage(userErrorMsg, false));
    159 
    160             return false;
    161         }
    162 
    163         parser.setForm(form);
    164         parser.setIndex(index);
    165         parser.setValue(value);
    166 
    167         try {
    168             parser.expression();
    169             valid = parser.getResult();
    170         } catch (Exception ex) {
    171             String logErrorMsg =
    172                 "ValidWhen Error for field ' " + field.getKey() + "' - " + ex;
    173 
    174             log.error(logErrorMsg);
    175 
    176             String userErrorMsg = sysmsgs.getMessage("system.error");
    177 
    178             errors.add(field.getKey(), new ActionMessage(userErrorMsg, false));
    179 
    180             return false;
    181         }
    182 
    183         if (!valid) {
    184             errors.add(field.getKey(),
    185                 Resources.getActionMessage(validator, request, va, field));
    186 
    187             return false;
    188         }
    189 
    190         return true;
    191     }
    192 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
