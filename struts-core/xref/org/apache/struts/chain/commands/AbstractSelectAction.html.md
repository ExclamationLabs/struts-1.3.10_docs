[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractSelectAction.html.md)


    1   /*
    2    * $Id: AbstractSelectAction.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.chain.contexts.ActionContext;
    24  import org.apache.struts.config.ActionConfig;
    25  import org.apache.struts.config.ModuleConfig;
    26  
    27  /**
    28   * <p>Cache the <code>ActionConfig</code> instance for the action to be used
    29   * for processing this request.</p>
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-11-05 21:44:59 -0500 (Sat, 05 Nov 2005)
    32   *          $
    33   */
    34  public abstract class AbstractSelectAction extends ActionCommandBase {
    35      // ---------------------------------------------------------- Public Methods
    36  
    37      /**
    38       * <p>Cache the <code>ActionConfig</code> instance for the action to be
    39       * used for processing this request.</p>
    40       *
    41       * @param actionCtx The <code>Context</code> for the current request
    42       * @return <code>false</code> so that processing continues
    43       * @throws InvalidPathException if no valid action can be identified for
    44       *                              this request
    45       * @throws Exception            if thrown by the Action class
    46       */
    47      public boolean execute(ActionContext actionCtx)
    48          throws Exception {
    49          // Identify the matching path for this request
    50          String path = getPath(actionCtx);
    51  
    52          // Cache the corresponding ActonConfig instance
    53          ModuleConfig moduleConfig = actionCtx.getModuleConfig();
    54          ActionConfig actionConfig = moduleConfig.findActionConfig(path);
    55  
    56          if (actionConfig == null) {
    57              // NOTE Shouldn't this be the responsibility of ModuleConfig?
    58              // Locate the mapping for unknown paths (if any)
    59              ActionConfig[] configs = moduleConfig.findActionConfigs();
    60  
    61              for (int i = 0; i < configs.length; i++) {
    62                  if (configs[i].getUnknown()) {
    63                      actionConfig = configs[i];
    64  
    65                      break;
    66                  }
    67              }
    68          }
    69  
    70          if (actionConfig == null) {
    71              throw new InvalidPathException("No action config found for the specified url.",
    72                  path);
    73          }
    74  
    75          actionCtx.setActionConfig(actionConfig);
    76  
    77          return (false);
    78      }
    79  
    80      // ------------------------------------------------------- Protected Methods
    81  
    82      /**
    83       * <p>Return the path to be used to select the <code>ActionConfig</code>
    84       * for this request.</p>
    85       *
    86       * @param context The <code>Context</code> for this request
    87       * @return Path to be used to select the ActionConfig
    88       */
    89      protected abstract String getPath(ActionContext context);
    90  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
