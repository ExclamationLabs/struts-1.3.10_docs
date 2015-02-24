[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractExceptionHandler.html.md)


    1   /*
    2    * $Id: AbstractExceptionHandler.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import org.apache.struts.config.ExceptionConfig;
    28  import org.apache.struts.config.ForwardConfig;
    29  import org.apache.struts.config.ModuleConfig;
    30  
    31  /**
    32   * <p>Invoke the local or global exception handler configured for the
    33   * exception class that occurred.</p>
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    36   *          $
    37   */
    38  public abstract class AbstractExceptionHandler extends ActionCommandBase {
    39      // ------------------------------------------------------ Instance Variables
    40  
    41      /**
    42       * Provide a Commons logging instance for this class.
    43       */
    44      private static final Log LOG =
    45          LogFactory.getLog(AbstractExceptionHandler.class);
    46  
    47      // ---------------------------------------------------------- Public Methods
    48  
    49      /**
    50       * <p>Invoke the appropriate <code>Action</code> for this request, and
    51       * cache the returned <code>ActionForward</code>.</p>
    52       *
    53       * @param actionCtx The <code>Context</code> for the current request
    54       * @return <code>false</code> if a <code>ForwardConfig</code> is returned,
    55       *         else <code>true</code> to complete processing
    56       * @throws Exception if thrown by the Action class and not declared by an
    57       *                   Exception Handler
    58       */
    59      public boolean execute(ActionContext actionCtx)
    60          throws Exception {
    61          // Look up the exception that was thrown
    62          Exception exception = actionCtx.getException();
    63  
    64          if (exception == null) {
    65              LOG.warn("No Exception found in ActionContext");
    66  
    67              return (true);
    68          }
    69  
    70          // Look up the local or global exception handler configuration
    71          ExceptionConfig exceptionConfig = null;
    72          ActionConfig actionConfig = actionCtx.getActionConfig();
    73          ModuleConfig moduleConfig = actionCtx.getModuleConfig();
    74  
    75          if (actionConfig != null) {
    76              if (LOG.isDebugEnabled()) {
    77                  LOG.debug("See if actionConfig " + actionConfig
    78                      + " has an exceptionConfig for "
    79                      + exception.getClass().getName());
    80              }
    81  
    82              exceptionConfig = actionConfig.findException(exception.getClass());
    83          } else if (moduleConfig != null) {
    84              if (LOG.isDebugEnabled()) {
    85                  LOG.debug("No action yet, see if moduleConfig " + moduleConfig
    86                      + " has an exceptionConfig "
    87                      + exception.getClass().getName());
    88              }
    89  
    90              exceptionConfig = moduleConfig.findException(exception.getClass());
    91          }
    92  
    93          // Handle the exception in the configured manner
    94          if (exceptionConfig == null) {
    95              LOG.warn("Unhandled exception", exception);
    96              throw exception;
    97          }
    98  
    99          ForwardConfig forwardConfig =
    100             handle(actionCtx, exception, exceptionConfig, actionConfig,
    101                 moduleConfig);
    102 
    103         if (forwardConfig != null) {
    104             actionCtx.setForwardConfig(forwardConfig);
    105 
    106             return (false);
    107         } else {
    108             return (true);
    109         }
    110     }
    111 
    112     // ------------------------------------------------------- Protected Methods
    113 
    114     /**
    115      * <p>Perform the required handling of the specified exception.</p>
    116      *
    117      * @param context         The <code>Context</code> for this request
    118      * @param exception       The exception being handled
    119      * @param exceptionConfig The corresponding {@link ExceptionConfig}
    120      * @param actionConfig    The {@link ActionConfig} for this request
    121      * @param moduleConfig    The {@link ModuleConfig} for this request
    122      * @return the <code>ForwardConfig</code> to be processed next (if any),
    123      *         or <code>null</code> if processing has been completed
    124      * @throws Exception if there are any problems handling the exception
    125      */
    126     protected abstract ForwardConfig handle(ActionContext context,
    127         Exception exception, ExceptionConfig exceptionConfig,
    128         ActionConfig actionConfig, ModuleConfig moduleConfig)
    129         throws Exception;
    130 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
