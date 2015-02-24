[View Javadoc](../../../apidocs/examples/validator/CustomValidator.html.md)


    1   /*
    2    * $Id: CustomValidator.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package examples.validator;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  
    26  import org.apache.commons.validator.Field;
    27  import org.apache.commons.validator.GenericValidator;
    28  import org.apache.commons.validator.ValidatorAction;
    29  import org.apache.commons.validator.util.ValidatorUtils;
    30  import org.apache.struts.action.ActionMessages;
    31  import org.apache.struts.validator.Resources;
    32  
    33  /**
    34   * A custom validator example
    35   *
    36   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    37   */
    38  public class CustomValidator {
    39  
    40      // ------------------------------------------------------------ Constructors
    41  
    42      /**
    43       * Constructor for CustomValidator.
    44       */
    45      public CustomValidator() {
    46          super();
    47      }
    48  
    49      // ---------------------------------------------------------- Public Methods
    50  
    51      /**
    52       * Example validator for comparing the equality of two fields
    53       *
    54       * http://struts.apache.org/userGuide/dev_validator.html.md
    55       * http://www.raibledesigns.com/page/rd/20030226
    56       */
    57      public static boolean validateTwoFields(
    58          Object bean,
    59          ValidatorAction va,
    60          Field field,
    61          ActionMessages errors,
    62          HttpServletRequest request) {
    63  
    64          String value =
    65              ValidatorUtils.getValueAsString(bean, field.getProperty());
    66          String property2 = field.getVarValue("secondProperty");
    67          String value2 = ValidatorUtils.getValueAsString(bean, property2);
    68  
    69          if (!GenericValidator.isBlankOrNull(value)) {
    70              try {
    71                  if (!value.equals(value2)) {
    72                      errors.add(
    73                          field.getKey(),
    74                          Resources.getActionMessage(request, va, field));
    75  
    76                      return false;
    77                  }
    78              } catch (Exception e) {
    79                  errors.add(
    80                      field.getKey(),
    81                      Resources.getActionMessage(request, va, field));
    82                  return false;
    83              }
    84          }
    85          return true;
    86      }
    87  
    88  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)