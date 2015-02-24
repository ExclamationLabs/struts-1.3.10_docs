[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/ExecuteCommand.html.md)


    1   /*
    2    * $Id: ExecuteCommand.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.chain.Catalog;
    24  import org.apache.commons.chain.CatalogFactory;
    25  import org.apache.commons.chain.Command;
    26  import org.apache.commons.logging.Log;
    27  import org.apache.commons.logging.LogFactory;
    28  import org.apache.struts.chain.contexts.ActionContext;
    29  import org.apache.struts.config.ActionConfig;
    30  
    31  /**
    32   * <p>Invoke the appropriate <code>Command</code> for this request.  If the
    33   * context's <code>ActionConfig</code> has no <code>command</code> property
    34   * defined, no action will be taken.  If the specified command cannot be
    35   * found, a warning will be logged, but processing will continue.  Depending
    36   * on how the chain is configured, this can be used in place of an
    37   * <code>Action</code> or as a method of performing pre-processing. </p>
    38   *
    39   * <p>If used instead of an action, the command which is looked up should put
    40   * an ActionForward into the context, unless it has already dealt with the
    41   * response.</p>
    42   *
    43   * @version $Id: ExecuteCommand.java 471754 2006-11-06 14:55:09Z husted $
    44   */
    45  public class ExecuteCommand extends ActionCommandBase {
    46      // ------------------------------------------------------ Instance Variables
    47  
    48      /**
    49       * Provide Commons Logging instance for this class.
    50       */
    51      private static final Log LOG = LogFactory.getLog(ExecuteCommand.class);
    52  
    53      // ---------------------------------------------------------- Public Methods
    54  
    55      /**
    56       * <p>If the <code>context</code> is "valid", lookup a command and execute
    57       * it.</p>
    58       *
    59       * @param actionCtx The <code>Context</code> for the current request
    60       * @return the result of the lookup command's <code>execute</code> method,
    61       *         if executed, or <code>false</code> if it was not executed.
    62       * @throws Exception on any error
    63       */
    64      public boolean execute(ActionContext actionCtx)
    65          throws Exception {
    66          if (shouldProcess(actionCtx)) {
    67              Command command = getCommand(actionCtx);
    68  
    69              if (command != null) {
    70                  return (command.execute(actionCtx));
    71              }
    72          }
    73  
    74          return (false);
    75      }
    76  
    77      /**
    78       * <p>Evaluate the current context to see if a command should even be
    79       * executed.</p>
    80       *
    81       * @param context A valid ActionContext
    82       * @return TRUE if the pending Command should be executed
    83       */
    84      protected boolean shouldProcess(ActionContext context) {
    85          // Skip processing if the current request is not valid
    86          Boolean valid = context.getFormValid();
    87  
    88          return ((valid != null) && valid.booleanValue());
    89      }
    90  
    91      /**
    92       * <p>Find the <code>ActionConfig</code> in the current context and, if it
    93       * is properly configured, lookup the appropriate <code>commons-chain</code>
    94       * command.</p>
    95       *
    96       * @param context A valid ActionContext
    97       * @return a <code>Command</code> to execute, or null if none is specified
    98       *         or if the specified command cannot be found.
    99       */
    100     protected Command getCommand(ActionContext context) {
    101         ActionConfig actionConfig = context.getActionConfig();
    102 
    103         String commandName = actionConfig.getCommand();
    104 
    105         if (commandName == null) {
    106             return null;
    107         }
    108 
    109         String catalogName = actionConfig.getCatalog();
    110 
    111         return getCommand(commandName, catalogName);
    112     }
    113 
    114     /**
    115      * <p> Retrieve the specified Command from the specified Catalog. </p>
    116      *
    117      * @param commandName The Command to retrieve.
    118      * @param catalogName The Catalog to search.
    119      * @return Instantiated Command, or null
    120      */
    121     protected Command getCommand(String commandName, String catalogName) {
    122         if (commandName == null) {
    123             return null;
    124         }
    125 
    126         Catalog catalog;
    127 
    128         if (catalogName != null) {
    129             catalog = CatalogFactory.getInstance().getCatalog(catalogName);
    130 
    131             if (catalog == null) {
    132                 LOG.warn("When looking up " + commandName + ","
    133                     + " no catalog found under " + catalogName);
    134 
    135                 return null;
    136             }
    137         } else {
    138             catalogName = "the default catalog";
    139             catalog = CatalogFactory.getInstance().getCatalog();
    140 
    141             if (catalog == null) {
    142                 LOG.warn("When looking up " + commandName + ","
    143                     + " no default catalog found.");
    144 
    145                 return null;
    146             }
    147         }
    148 
    149         if (LOG.isDebugEnabled()) {
    150             LOG.debug("looking up command " + commandName + " in "
    151                 + catalogName);
    152         }
    153 
    154         return catalog.getCommand(commandName);
    155     }
    156 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
