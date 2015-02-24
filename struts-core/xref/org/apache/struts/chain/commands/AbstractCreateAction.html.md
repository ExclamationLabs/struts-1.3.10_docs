[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractCreateAction.html.md)


    1   /*
    2    * $Id: AbstractCreateAction.java 525705 2007-04-05 05:25:08Z pbenedict $
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
    25  import org.apache.struts.action.Action;
    26  import org.apache.struts.chain.contexts.ActionContext;
    27  import org.apache.struts.config.ActionConfig;
    28  
    29  /**
    30   * <p> Create (if necessary) and cache an <code>Action</code> for this
    31   * request. </p>
    32   *
    33   * @version $Rev: 525705 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    34   *          $
    35   */
    36  public abstract class AbstractCreateAction extends ActionCommandBase {
    37      // ------------------------------------------------------ Instance Variables
    38  
    39      /**
    40       * Provide a Commons logging instance for this class.
    41       */
    42      private static final Log LOG =
    43          LogFactory.getLog(AbstractCreateAction.class);
    44  
    45      // ---------------------------------------------------------- Public Methods
    46  
    47      /**
    48       * <p>Create (if necessary) and cache an <code>Action</code> for this
    49       * request.</p>
    50       *
    51       * @param actionCtx The <code>Context</code> for the current request
    52       * @return <code>false</code> so that processing continues
    53       * @throws Exception if there are any problems instantiating the Action
    54       *                   class.
    55       */
    56      public boolean execute(ActionContext actionCtx)
    57          throws Exception {
    58          // Skip processing if the current request is not valid
    59          Boolean valid = actionCtx.getFormValid();
    60  
    61          if ((valid == null) || !valid.booleanValue()) {
    62              LOG.trace("Invalid form; not going to execute.");
    63  
    64              return (false);
    65          }
    66  
    67          // Check to see if an action has already been created
    68          if (actionCtx.getAction() != null) {
    69              LOG.trace("already have an action [" + actionCtx.getAction() + "]");
    70  
    71              return (false);
    72          }
    73  
    74          // Look up the class name for the desired Action
    75          ActionConfig actionConfig = actionCtx.getActionConfig();
    76          String type = actionConfig.getType();
    77  
    78          if (type == null) {
    79              String command = actionConfig.getCommand();
    80              if ((command == null) && (actionConfig.getForward() == null)
    81                  && (actionConfig.getInclude() == null)) {
    82                  LOG.error("no type or command for " + actionConfig.getPath());
    83              } else {
    84                  LOG.trace("no type for " + actionConfig.getPath());
    85              }
    86  
    87              return (false);
    88          }
    89  
    90          // Create (if necessary) and cache an Action instance
    91          Action action = getAction(actionCtx, type, actionConfig);
    92  
    93          if (LOG.isTraceEnabled()) {
    94              LOG.trace("setting action to " + action);
    95          }
    96  
    97          actionCtx.setAction(action);
    98  
    99          return (false);
    100     }
    101 
    102     // ------------------------------------------------------- Protected Methods
    103 
    104     /**
    105      * <p> Create and return the appropriate <code>Action</code> class for the
    106      * given <code>type</code> and <code>actionConfig</code>. </p> <p> NOTE:
    107      * The dependence on ActionServlet suggests that this should be broken up
    108      * along the lines of the other Abstract/concrete pairs in the
    109      * org.apache.struts.chain.commands package. </p>
    110      *
    111      * @param context      The <code>Context</code> for this request
    112      * @param type         Name of class to instantiate
    113      * @param actionConfig The {@link ActionConfig} for this request
    114      * @return Instantiated Action class
    115      * @throws Exception if there are any problems instantiating the Action
    116      *                   class.
    117      */
    118     protected abstract Action getAction(ActionContext context, String type,
    119         ActionConfig actionConfig)
    120         throws Exception;
    121 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
