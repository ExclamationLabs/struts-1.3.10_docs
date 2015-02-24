[View Javadoc](../../../apidocs/examples/multibox/MultiboxActionForm.html.md)


    1   /*
    2    * $Id: MultiboxActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples.multibox;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  
    26  import org.apache.struts.action.ActionErrors;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionMapping;
    29  
    30  /**
    31   * An ActionForm for the Multibox examples
    32   *
    33   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    34   */
    35  public class MultiboxActionForm extends ActionForm {
    36  
    37      // ------------------------------------------------------ Instance Variables
    38  
    39      /** Fruits */
    40      private String[] fruits = {};
    41  
    42      /** Colors */
    43      private String[] colors = {};
    44  
    45      // ------------------------------------------------------------ Constructors
    46  
    47      /**
    48       * Constructor for MultiboxActionForm.
    49       */
    50      public MultiboxActionForm() {
    51          super();
    52      }
    53  
    54      // ---------------------------------------------------------- Public Methods
    55  
    56      /**
    57       * Clear all checkboxes
    58       *
    59       * @param mapping The mapping used to select this instance
    60       * @param request The servlet request we are processing
    61       */
    62      public void reset(ActionMapping mapping, HttpServletRequest request) {
    63  
    64          /*
    65           * The ActionForm reset method should only be used to *clear*
    66           * checkboxes. The correct place to *set* default checkbox values is in
    67           * the 'prepare' action, called prior to displaying the form page.
    68           */
    69          String[] empty = {};
    70          this.fruits = empty;
    71          this.colors = empty;
    72  
    73      }
    74  
    75      /**
    76       * Validate the properties that have been set from this HTTP request,
    77       * and return an <code>ActionMessages</code> object that encapsulates any
    78       * validation errors that have been found.  If no errors are found, return
    79       * <code>null</code> or an <code>ActionMessages</code> object with no
    80       * recorded error messages.
    81       *
    82       * @param mapping The mapping used to select this instance
    83       * @param request The servlet request we are processing
    84       *
    85       * @return ActionMessages if any validation errors occurred
    86       */
    87      public ActionErrors validate(
    88          ActionMapping mapping,
    89          HttpServletRequest request) {
    90  
    91          /*
    92           * We're not doing any validation (yet) so return null to
    93           * indicate that there were no errors. (We don't
    94           * actually need to override this nethod unles we're doing
    95           * validation - but it's here for reference)
    96           */
    97          return null;
    98      }
    99  
    100     // -------------------------------------------------------------- Properties
    101 
    102     /**
    103      * Returns the colors.
    104      * @return String[]
    105      */
    106     public String[] getColors() {
    107         return colors;
    108     }
    109 
    110     /**
    111      * Returns the fruits.
    112      * @return String[]
    113      */
    114     public String[] getFruits() {
    115         return fruits;
    116     }
    117 
    118     /**
    119      * Sets the colors.
    120      * @param colors The colors to set
    121      */
    122     public void setColors(String[] colors) {
    123         this.colors = colors;
    124     }
    125 
    126     /**
    127      * Sets the fruits.
    128      * @param fruits The fruits to set
    129      */
    130     public void setFruits(String[] fruits) {
    131         this.fruits = fruits;
    132     }
    133 
    134 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
