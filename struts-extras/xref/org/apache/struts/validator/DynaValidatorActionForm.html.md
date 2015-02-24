[View Javadoc](../../../../../apidocs/org/apache/struts/validator/DynaValidatorActionForm.html.md)


    1   /*
    2    * $Id: DynaValidatorActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.beanutils.DynaBean;
    24  import org.apache.struts.action.ActionMapping;
    25  
    26  import javax.servlet.http.HttpServletRequest;
    27  
    28  import java.io.Serializable;
    29  
    30  /**
    31   * <p>This class extends <strong>DynaValidatorForm</strong> and provides basic
    32   * field validation based on an XML file.  The key passed into the validator
    33   * is the action element's 'path' attribute from the struts-config.xml which
    34   * should match the form element's name attribute in the validation.xml.</p>
    35   *
    36   * <ul>
    37   *
    38   * <li>See <code>ValidatorPlugin</code> definition in struts-config.xml for
    39   * validation rules.</li>
    40   *
    41   * </ul>
    42   *
    43   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    44   *          $
    45   * @since Struts 1.1
    46   */
    47  public class DynaValidatorActionForm extends DynaValidatorForm
    48      implements DynaBean, Serializable {
    49      /**
    50       * Returns the Validation key.
    51       *
    52       * @param mapping The mapping used to select this instance
    53       * @param request The servlet request we are processing
    54       * @return validation key - the action element's 'path' attribute in this
    55       *         case
    56       */
    57      public String getValidationKey(ActionMapping mapping,
    58          HttpServletRequest request) {
    59          return mapping.getPath();
    60      }
    61  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)