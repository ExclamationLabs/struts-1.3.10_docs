[View Javadoc](../../../../../apidocs/org/apache/struts/validator/DynaValidatorForm.html.md)


    1   /*
    2    * $Id: DynaValidatorForm.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.commons.validator.Validator;
    27  import org.apache.commons.validator.ValidatorException;
    28  import org.apache.commons.validator.ValidatorResults;
    29  import org.apache.struts.action.ActionErrors;
    30  import org.apache.struts.action.ActionMapping;
    31  import org.apache.struts.action.DynaActionForm;
    32  
    33  import javax.servlet.ServletContext;
    34  import javax.servlet.http.HttpServletRequest;
    35  
    36  import java.io.Serializable;
    37  
    38  import java.util.Map;
    39  
    40  /**
    41   * <p>This class extends <strong>DynaActionForm</strong> and provides basic
    42   * field validation based on an XML file.  The key passed into the validator
    43   * is the action element's 'name' attribute from the struts-config.xml which
    44   * should match the form element's name attribute in the validation.xml.</p>
    45   *
    46   * <ul>
    47   *
    48   * <li>See <code>ValidatorPlugin</code> definition in struts-config.xml for
    49   * validation rules.</li>
    50   *
    51   * </ul>
    52   *
    53   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    54   *          $
    55   * @see org.apache.struts.action.ActionForm
    56   * @since Struts 1.1
    57   */
    58  public class DynaValidatorForm extends DynaActionForm implements DynaBean,
    59      Serializable {
    60      /**
    61       * Commons Logging instance.
    62       */
    63      private static Log log = LogFactory.getLog(DynaValidatorForm.class);
    64  
    65      /**
    66       * The results returned from the validation performed by the
    67       * <code>Validator</code>.
    68       */
    69      protected ValidatorResults validatorResults = null;
    70  
    71      /**
    72       * Used to indicate the current page of a multi-page form.
    73       */
    74      protected int page = 0;
    75  
    76      /**
    77       * Gets page.
    78       *
    79       * @return page number.
    80       */
    81      public int getPage() {
    82          return page;
    83      }
    84  
    85      /**
    86       * Sets page.
    87       *
    88       * @param page page number
    89       */
    90      public void setPage(int page) {
    91          this.page = page;
    92      }
    93  
    94      /**
    95       * Validate the properties that have been set from this HTTP request, and
    96       * return an <code>ActionErrors</code> object that encapsulates any
    97       * validation errors that have been found.  If no errors are found, return
    98       * <code>null</code> or an <code>ActionErrors</code> object with no
    99       * recorded error messages.
    100      *
    101      * @param mapping The mapping used to select this instance.
    102      * @param request The servlet request we are processing.
    103      * @return <code>ActionErrors</code> object that encapsulates any
    104      *         validation errors.
    105      */
    106     public ActionErrors validate(ActionMapping mapping,
    107         HttpServletRequest request) {
    108         this.setPageFromDynaProperty();
    109 
    110         ServletContext application = getServlet().getServletContext();
    111         ActionErrors errors = new ActionErrors();
    112 
    113         String validationKey = getValidationKey(mapping, request);
    114 
    115         Validator validator =
    116             Resources.initValidator(validationKey, this, application, request,
    117                 errors, page);
    118 
    119         try {
    120             validatorResults = validator.validate();
    121         } catch (ValidatorException e) {
    122             log.error(e.getMessage(), e);
    123         }
    124 
    125         return errors;
    126     }
    127 
    128     /**
    129      * Returns the Validation key.
    130      *
    131      * @param mapping The mapping used to select this instance
    132      * @param request The servlet request we are processing
    133      * @return validation key - the form element's name in this case
    134      */
    135     public String getValidationKey(ActionMapping mapping,
    136         HttpServletRequest request) {
    137         return mapping.getAttribute();
    138     }
    139 
    140     /**
    141      * Sets this.page to the value of the Dyna property "page" if it's
    142      * defined.  This is used to setup the page variable before validation
    143      * starts.
    144      *
    145      * @since Struts 1.2
    146      */
    147     protected void setPageFromDynaProperty() {
    148         Map props = this.getMap();
    149 
    150         if (props.containsKey("page")) {
    151             Integer p = null;
    152 
    153             try {
    154                 p = (Integer) props.get("page");
    155             } catch (ClassCastException e) {
    156                 log.error("Dyna 'page' property must be of type java.lang.Integer.",
    157                     e);
    158                 throw e;
    159             }
    160 
    161             if (p == null) {
    162                 throw new NullPointerException(
    163                     "Dyna 'page' property must not be null. "
    164                     + " Either provide an initial value or set 'convertNull' to false. ");
    165             }
    166 
    167             this.page = p.intValue();
    168         }
    169     }
    170 
    171     /**
    172      * Reset all properties to their default values.
    173      *
    174      * @param mapping The mapping used to select this instance
    175      * @param request The servlet request we are processing
    176      */
    177     public void reset(ActionMapping mapping, HttpServletRequest request) {
    178         super.reset(mapping, request);
    179         page = 0;
    180         validatorResults = null;
    181     }
    182 
    183     /**
    184      * Get results of the validation performed by the <code>Validator</code>.
    185      *
    186      * @return validator results as ValidatorResults object
    187      */
    188     public ValidatorResults getValidatorResults() {
    189         return validatorResults;
    190     }
    191 
    192     /**
    193      * Set results of the validation performed by the <code>Validator</code>.
    194      *
    195      * @param validatorResults Set results of the validation performed
    196      */
    197     public void setValidatorResults(ValidatorResults validatorResults) {
    198         this.validatorResults = validatorResults;
    199     }
    200 
    201     /**
    202      * Returns a <code>Map</code> of values returned from any validation that
    203      * returns a value other than <code>null</code> or <code>Boolean</code>
    204      * with the key the full property path of the field.
    205      *
    206      * @return Returns a <code>Map</code> of values, otherwise returns null if
    207      *         no results.
    208      */
    209     public Map getResultValueMap() {
    210         return ((validatorResults != null)
    211         ? validatorResults.getResultValueMap() : null);
    212     }
    213 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
