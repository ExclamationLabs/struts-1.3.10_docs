[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractSelectForward.html.md)


    1   /*
    2    * $Id: AbstractSelectForward.java 471754 2006-11-06 14:55:09Z husted $
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
    31   * <p>Select and cache the <code>ActionForward</code> for this
    32   * <code>ActionConfig</code> if specified.</p>
    33   *
    34   * @version $Rev: 471754 $ $Date: 2005-06-04 10:58:46 -0400 (Sat, 04 Jun 2005)
    35   *          $
    36   */
    37  public abstract class AbstractSelectForward extends ActionCommandBase {
    38      // ------------------------------------------------------ Instance Variables
    39  
    40      /**
    41       * <p> Provide Commons Logging instance for this class. </p>
    42       */
    43      private static final Log LOG =
    44          LogFactory.getLog(AbstractSelectForward.class);
    45  
    46      // ---------------------------------------------------------- Public Methods
    47  
    48      /**
    49       * <p>Select and cache the <code>ActionForward</code> for this
    50       * <code>ActionConfig</code> if specified.</p>
    51       *
    52       * @param actionCtx The <code>Context</code> for the current request
    53       * @return <code>false</code> so that processing continues
    54       * @throws Exception if thrown by the Action class
    55       */
    56      public boolean execute(ActionContext actionCtx)
    57          throws Exception {
    58          // Skip processing if the current request is not valid
    59          Boolean valid = actionCtx.getFormValid();
    60  
    61          if ((valid == null) || !valid.booleanValue()) {
    62              return (false);
    63          }
    64  
    65          // Acquire configuration objects that we need
    66          ActionConfig actionConfig = actionCtx.getActionConfig();
    67          ModuleConfig moduleConfig = actionConfig.getModuleConfig();
    68  
    69          ForwardConfig forwardConfig = null;
    70          String forward = actionConfig.getForward();
    71  
    72          if (forward != null) {
    73              forwardConfig = forward(actionCtx, moduleConfig, forward);
    74  
    75              if (LOG.isDebugEnabled()) {
    76                  LOG.debug("Forwarding to " + forwardConfig);
    77              }
    78  
    79              actionCtx.setForwardConfig(forwardConfig);
    80          }
    81  
    82          return (false);
    83      }
    84  
    85      // ------------------------------------------------------- Protected Methods
    86  
    87      /**
    88       * <p>Create and return a <code>ForwardConfig</code> representing the
    89       * specified module-relative destination.</p>
    90       *
    91       * @param context      The context for this request
    92       * @param moduleConfig The <code>ModuleConfig</code> for this request
    93       * @param uri          The module-relative URI to be the destination
    94       * @return ForwwardConfig representing the destination
    95       */
    96      protected abstract ForwardConfig forward(ActionContext context,
    97          ModuleConfig moduleConfig, String uri);
    98  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)