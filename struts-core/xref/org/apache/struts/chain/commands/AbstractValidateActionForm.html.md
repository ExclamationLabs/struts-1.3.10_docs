[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractValidateActionForm.html.md)


    1   /*
    2    * $Id: AbstractValidateActionForm.java 481833 2006-12-03 17:32:52Z niallp $
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
    21  package org.apache.struts.chain.commands;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.action.ActionErrors;
    26  import org.apache.struts.action.ActionForm;
    27  import org.apache.struts.action.InvalidCancelException;
    28  import org.apache.struts.chain.contexts.ActionContext;
    29  import org.apache.struts.config.ActionConfig;
    30  
    31  /**
    32   * <p>Validate the properties of the form bean for this request.  If there are
    33   * any validation errors, execute the specified command; otherwise, proceed
    34   * normally.</p>
    35   *
    36   * @version $Rev: 481833 $ $Date: 2005-06-04 10:58:46 -0400 (Sat, 04 Jun 2005)
    37   *          $
    38   */
    39  public abstract class AbstractValidateActionForm extends ActionCommandBase {
    40      // ------------------------------------------------------ Instance Variables
    41  
    42      /**
    43       * <p> Provide Commons Logging instance for this class. </p>
    44       */
    45      private static final Log LOG =
    46          LogFactory.getLog(AbstractSelectForward.class);
    47  
    48      // ------------------------------------------------------ Protected Methods
    49  
    50      /**
    51       * <p>Helper method to verify the Cancel state.</p>
    52       *
    53       * <p>If the state is invalid, Cancel is unset and an
    54       * InvalidCancelException is thrown.</p>
    55       *
    56       * @param actionCtx    Our ActionContext
    57       * @param actionConfig Our ActionConfig
    58       * @return true if cancel is set, false otherwise.
    59       * @throws InvalidCancelException
    60       */
    61      private boolean isCancelled(ActionContext actionCtx,
    62          ActionConfig actionConfig)
    63          throws InvalidCancelException {
    64          Boolean cancel = actionCtx.getCancelled();
    65          boolean cancelled = ((cancel != null) && cancel.booleanValue());
    66          boolean cancellable = actionConfig.getCancellable();
    67  
    68          boolean invalidState = (cancelled && !cancellable);
    69  
    70          if (invalidState) {
    71              actionCtx.setCancelled(Boolean.FALSE);
    72              actionCtx.setFormValid(Boolean.FALSE);
    73              throw new InvalidCancelException();
    74          }
    75  
    76          return cancelled;
    77      }
    78  
    79      // ---------------------------------------------------------- Public Methods
    80  
    81      /**
    82       * <p>Validate the properties of the form bean for this request.  If there
    83       * are any validation errors, execute the child commands in our chain;
    84       * otherwise, proceed normally.</p>
    85       *
    86       * @param actionCtx The <code>Context</code> for the current request
    87       * @return <code>false</code> so that processing continues, if there are
    88       *         no validation errors; otherwise <code>true</code>
    89       * @throws Exception if thrown by the Action class
    90       */
    91      public boolean execute(ActionContext actionCtx)
    92          throws Exception {
    93          // Set form valid until found otherwise
    94          actionCtx.setFormValid(Boolean.TRUE);
    95  
    96          // Is there a form bean for this request?
    97          ActionForm actionForm = actionCtx.getActionForm();
    98  
    99          if (actionForm == null) {
    100             return false;
    101         }
    102 
    103         // Is validation disabled on this request?
    104         ActionConfig actionConfig = actionCtx.getActionConfig();
    105 
    106         if (!actionConfig.getValidate()) {
    107             return false;
    108         }
    109 
    110         // Was this request cancelled?
    111         if (isCancelled(actionCtx, actionConfig)) {
    112             if (LOG.isDebugEnabled()) {
    113                 LOG.debug(" Cancelled transaction, skipping validation");
    114             }
    115 
    116             return false;
    117         }
    118 
    119         // Call the validate() method of this form bean
    120         ActionErrors errors = validate(actionCtx, actionConfig, actionForm);
    121 
    122         // If there were no errors, proceed normally
    123         if ((errors == null) || (errors.isEmpty())) {
    124             return false;
    125         }
    126 
    127         // Flag the validation failure and proceed
    128         /* NOTE: Is there any concern that there might have already
    129          * been errors, or that other errors might be coming?
    130          */
    131         actionCtx.saveErrors(errors);
    132         actionCtx.setFormValid(Boolean.FALSE);
    133 
    134         return false;
    135     }
    136 
    137     // ------------------------------------------------------- Protected Methods
    138 
    139     /**
    140      * <p>Call the <code>validate()</code> method of the specified form bean,
    141      * and return the resulting <code>ActionErrors</code> object.</p>
    142      *
    143      * @param context      The context for this request
    144      * @param actionConfig The <code>ActionConfig</code> for this request
    145      * @param actionForm   The form bean for this request
    146      * @return ActionErrors object, if any
    147      */
    148     protected abstract ActionErrors validate(ActionContext context,
    149         ActionConfig actionConfig, ActionForm actionForm);
    150 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
