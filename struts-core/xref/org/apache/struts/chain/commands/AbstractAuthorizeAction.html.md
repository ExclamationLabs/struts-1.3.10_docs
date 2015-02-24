[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractAuthorizeAction.html.md)


    1   /*
    2    * $Id: AbstractAuthorizeAction.java 481115 2006-12-01 00:16:41Z germuska $
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
    27  
    28  /**
    29   * <p>Determine whether the requested action is authorized for the current
    30   * user. If not, abort chain processing and perferably, return an error
    31   * message of some kind.</p>
    32   *
    33   * @version $Rev: 481115 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    34   *          $
    35   */
    36  public abstract class AbstractAuthorizeAction extends ActionCommandBase {
    37      // ------------------------------------------------------ Instance Variables
    38  
    39      /**
    40       * Provide a Commons logging instance for this class.
    41       */
    42      private static final Log LOG =
    43          LogFactory.getLog(AbstractAuthorizeAction.class);
    44  
    45      // ---------------------------------------------------------- Public Methods
    46  
    47      /**
    48       * <p>Determine whether the requested action is authorized for the current
    49       * user.  If not, abort chain processing and perferably, return an error
    50       * message of some kind.</p>
    51       *
    52       * @param actionCtx The <code>Context</code> for the current request
    53       * @return <code>false</code> if the user is authorized for the selected
    54       *         action, else <code>true</code> to abort processing.
    55       * @throws UnauthorizedActionException if authorization fails 
    56       * or if an error is encountered in the course of performing the authorization.
    57       */
    58      public boolean execute(ActionContext actionCtx)
    59          throws Exception {
    60          // Retrieve ActionConfig
    61          ActionConfig actionConfig = actionCtx.getActionConfig();
    62  
    63          // Is this action protected by role requirements?
    64          if (!isAuthorizationRequired(actionConfig)) {
    65              return (false);
    66          }
    67  
    68          boolean throwEx;
    69  
    70          try {
    71              throwEx =
    72                  !(isAuthorized(actionCtx, actionConfig.getRoleNames(),
    73                      actionConfig));
    74          } catch (UnauthorizedActionException ex) {
    75             throw ex;
    76          } catch (Exception ex) {
    77              throwEx = true;
    78              LOG.error("Unable to complete authorization process", ex);
    79          }
    80  
    81          if (throwEx) {
    82              // The current user is not authorized for this action
    83              throw new UnauthorizedActionException(getErrorMessage(actionCtx,
    84                      actionConfig));
    85          } else {
    86              return (false);
    87          }
    88      }
    89  
    90      /**
    91       * <p>Must authorization rules be consulted?  The base implementation
    92       * returns <code>true</code> if the given <code>ActionConfig</code> has
    93       * one or more roles defined.</p>
    94       *
    95       * @param actionConfig the current ActionConfig object
    96       * @return true if the <code>isAuthorized</code> method should be
    97       *         consulted.
    98       */
    99      protected boolean isAuthorizationRequired(ActionConfig actionConfig) {
    100         String[] roles = actionConfig.getRoleNames();
    101 
    102         return (roles != null) && (roles.length > 0);
    103     }
    104 
    105     // ------------------------------------------------------- Protected Methods
    106 
    107     /**
    108      * <p>Determine if the action is authorized for the given roles.</p>
    109      *
    110      * @param context      The <code>Context</code> for the current request
    111      * @param roles        An array of valid roles for this request
    112      * @param actionConfig The current action mapping
    113      * @return <code>true</code> if the request is authorized, else
    114      *         <code>false</code>
    115      * @throws UnauthorizedActionException If the logic determines that the request is not authorized 
    116      * but does not wish to rely upon the default mechanism reporting the error.
    117      * @throws Exception If the action cannot be tested for authorization
    118      */
    119     protected abstract boolean isAuthorized(ActionContext context,
    120         String[] roles, ActionConfig actionConfig)
    121         throws Exception;
    122 
    123     /**
    124      * <p> Retrieve error message from context. </p>
    125      *
    126      * @param context      The <code>Context</code> for the current request
    127      * @param actionConfig The current action mapping
    128      * @return error message
    129      */
    130     protected abstract String getErrorMessage(ActionContext context,
    131         ActionConfig actionConfig);
    132 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
