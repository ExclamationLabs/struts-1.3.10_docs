[View Javadoc](../../../../../apidocs/org/apache/struts/validator/ValidatorForm.html.md)


    1   /*
    2    * $Id: ValidatorForm.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import org.apache.commons.validator.Validator;
    26  import org.apache.commons.validator.ValidatorException;
    27  import org.apache.commons.validator.ValidatorResults;
    28  import org.apache.struts.action.ActionErrors;
    29  import org.apache.struts.action.ActionForm;
    30  import org.apache.struts.action.ActionMapping;
    31  
    32  import javax.servlet.ServletContext;
    33  import javax.servlet.http.HttpServletRequest;
    34  
    35  import java.io.Serializable;
    36  
    37  import java.util.Map;
    38  
    39  /**
    40   * <p>This class extends <strong>ActionForm</strong> and provides basic field
    41   * validation based on an XML file.  The key passed into the validator is the
    42   * action element's 'name' attribute from the struts-config.xml which should
    43   * match the form element's name attribute in the validation.xml.</p>
    44   *
    45   * <ul>
    46   *
    47   * <li>See <code>ValidatorPlugin</code> definition in struts-config.xml for
    48   * validation rules.</li>
    49   *
    50   * </ul>
    51   *
    52   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    53   *          $
    54   * @see org.apache.struts.action.ActionForm
    55   * @since Struts 1.1
    56   */
    57  public class ValidatorForm extends ActionForm implements Serializable {
    58      /**
    59       * Commons Logging instance.
    60       */
    61      private static Log log = LogFactory.getLog(ValidatorForm.class);
    62  
    63      /**
    64       * The results returned from the validation performed by the
    65       * <code>Validator</code>.
    66       */
    67      protected ValidatorResults validatorResults = null;
    68  
    69      /**
    70       * Used to indicate the current page of a multi-page form.
    71       */
    72      protected int page = 0;
    73  
    74      /**
    75       * Gets page.
    76       *
    77       * @return page number
    78       */
    79      public int getPage() {
    80          return page;
    81      }
    82  
    83      /**
    84       * Sets page.
    85       *
    86       * @param page page number
    87       */
    88      public void setPage(int page) {
    89          this.page = page;
    90      }
    91  
    92      /**
    93       * Validate the properties that have been set from this HTTP request, and
    94       * return an <code>ActionErrors</code> object that encapsulates any
    95       * validation errors that have been found.  If no errors are found, return
    96       * <code>null</code> or an <code>ActionErrors</code> object with no
    97       * recorded error messages.
    98       *
    99       * @param mapping The mapping used to select this instance
    100      * @param request The servlet request we are processing
    101      * @return <code>ActionErrors</code> object that encapsulates any
    102      *         validation errors
    103      */
    104     public ActionErrors validate(ActionMapping mapping,
    105         HttpServletRequest request) {
    106         ServletContext application = getServlet().getServletContext();
    107         ActionErrors errors = new ActionErrors();
    108 
    109         String validationKey = getValidationKey(mapping, request);
    110 
    111         Validator validator =
    112             Resources.initValidator(validationKey, this, application, request,
    113                 errors, page);
    114 
    115         try {
    116             validatorResults = validator.validate();
    117         } catch (ValidatorException e) {
    118             log.error(e.getMessage(), e);
    119         }
    120 
    121         return errors;
    122     }
    123 
    124     /**
    125      * Returns the Validation key.
    126      *
    127      * @param mapping The mapping used to select this instance
    128      * @param request The servlet request we are processing
    129      * @return validation key - the form element's name in this case
    130      */
    131     public String getValidationKey(ActionMapping mapping,
    132         HttpServletRequest request) {
    133         return mapping.getAttribute();
    134     }
    135 
    136     /**
    137      * Reset all properties to their default values.
    138      *
    139      * @param mapping The mapping used to select this instance
    140      * @param request The servlet request we are processing
    141      */
    142     public void reset(ActionMapping mapping, HttpServletRequest request) {
    143         super.reset(mapping, request);
    144         page = 0;
    145         validatorResults = null;
    146     }
    147 
    148     /**
    149      * Get results of the validation performed by the <code>Validator</code>.
    150      *
    151      * @return results of the validation
    152      */
    153     public ValidatorResults getValidatorResults() {
    154         return validatorResults;
    155     }
    156 
    157     /**
    158      * Set results of the validation performed by the <code>Validator</code>.
    159      *
    160      * @param validatorResults results of validation
    161      */
    162     public void setValidatorResults(ValidatorResults validatorResults) {
    163         this.validatorResults = validatorResults;
    164     }
    165 
    166     /**
    167      * Returns a <code>Map</code> of values returned from any validation that
    168      * returns a value other than <code>null</code> or <code>Boolean</code>
    169      * with the key the full property path of the field.
    170      *
    171      * @return <code>Map</code> of non-null values
    172      */
    173     public Map getResultValueMap() {
    174         return ((validatorResults != null)
    175         ? validatorResults.getResultValueMap() : null);
    176     }
    177 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
