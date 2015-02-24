[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractSelectInput.html.md)


    1   /*
    2    * $Id: AbstractSelectInput.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import org.apache.struts.chain.contexts.ActionContext;
    26  import org.apache.struts.config.ActionConfig;
    27  import org.apache.struts.config.ForwardConfig;
    28  import org.apache.struts.config.ModuleConfig;
    29  
    30  /**
    31   * <p>Select and cache a <code>ForwardConfig</code> that returns us to the
    32   * input page for the current action, if any.</p>
    33   *
    34   * @version $Rev: 471754 $ $Date: 2005-06-04 10:58:46 -0400 (Sat, 04 Jun 2005)
    35   *          $
    36   */
    37  public abstract class AbstractSelectInput extends ActionCommandBase {
    38      // ------------------------------------------------------ Instance Variables
    39  
    40      /**
    41       * <p> Provide Commons Logging instance for this class. </p>
    42       */
    43      private static final Log LOG = LogFactory.getLog(AbstractSelectInput.class);
    44  
    45      // ---------------------------------------------------------- Public Methods
    46  
    47      /**
    48       * <p>Select and cache a <code>ForwardConfig</code> for the input page for
    49       * the current request.</p>
    50       *
    51       * @param actionCtx The <code>Context</code> for the current request
    52       * @return <code>false</code> so that processing continues
    53       * @throws Exception if thrown by the Action class
    54       */
    55      public boolean execute(ActionContext actionCtx)
    56          throws Exception {
    57          // Skip processing if the current request is valid
    58          Boolean valid = actionCtx.getFormValid();
    59  
    60          if ((valid != null) && valid.booleanValue()) {
    61              return (false);
    62          }
    63  
    64          // Acquire configuration objects that we need
    65          ActionConfig actionConfig = actionCtx.getActionConfig();
    66          ModuleConfig moduleConfig = actionConfig.getModuleConfig();
    67  
    68          // Cache an ForwardConfig back to our input page
    69          ForwardConfig forwardConfig;
    70          String input = actionConfig.getInput();
    71  
    72          if (moduleConfig.getControllerConfig().getInputForward()) {
    73              if (LOG.isTraceEnabled()) {
    74                  LOG.trace("Finding ForwardConfig for '" + input + "'");
    75              }
    76  
    77              forwardConfig = actionConfig.findForwardConfig(input);
    78  
    79              if (forwardConfig == null) {
    80                  forwardConfig = moduleConfig.findForwardConfig(input);
    81              }
    82          } else {
    83              if (LOG.isTraceEnabled()) {
    84                  LOG.trace("Delegating to forward() for '" + input + "'");
    85              }
    86  
    87              forwardConfig = forward(actionCtx, moduleConfig, input);
    88          }
    89  
    90          if (LOG.isDebugEnabled()) {
    91              LOG.debug("Forwarding back to " + forwardConfig);
    92          }
    93  
    94          actionCtx.setForwardConfig(forwardConfig);
    95  
    96          return (false);
    97      }
    98  
    99      // ------------------------------------------------------- Protected Methods
    100 
    101     /**
    102      * <p>Create and return a <code>ForwardConfig</code> representing the
    103      * specified module-relative destination.</p>
    104      *
    105      * @param context      The context for this request
    106      * @param moduleConfig The <code>ModuleConfig</code> for this request
    107      * @param uri          The module-relative URI to be the destination
    108      * @return ForwardConfig representing destination
    109      */
    110     protected abstract ForwardConfig forward(ActionContext context,
    111         ModuleConfig moduleConfig, String uri);
    112 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
