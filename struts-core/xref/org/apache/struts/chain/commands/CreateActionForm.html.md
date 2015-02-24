[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/CreateActionForm.html.md)


    1   /*
    2    * $Id: CreateActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.chain.contexts.ActionContext;
    27  import org.apache.struts.chain.contexts.ServletActionContext;
    28  import org.apache.struts.config.ActionConfig;
    29  import org.apache.struts.config.FormBeanConfig;
    30  
    31  import java.util.Map;
    32  
    33  /**
    34   * <p>Create (if necessary) and cache a form bean for this request.</p>
    35   *
    36   * @version $Id: CreateActionForm.java 471754 2006-11-06 14:55:09Z husted $
    37   */
    38  public class CreateActionForm extends ActionCommandBase {
    39      // ------------------------------------------------------ Instance Variables
    40  
    41      /**
    42       * <p> Provide Commons Logging instance for this class. </p>
    43       */
    44      private static final Log LOG = LogFactory.getLog(CreateActionForm.class);
    45  
    46      // ---------------------------------------------------------- Public Methods
    47  
    48      /**
    49       * <p>Create (if necessary) and cache a form bean for this request.</p>
    50       *
    51       * @param actionCtx The <code>Context</code> for the current request
    52       * @return <code>false</code> so that processing continues
    53       * @throws Exception on any error
    54       */
    55      public boolean execute(ActionContext actionCtx)
    56          throws Exception {
    57          // Is there a form bean associated with this ActionConfig?
    58          ActionConfig actionConfig = actionCtx.getActionConfig();
    59          String name = actionConfig.getName();
    60  
    61          if (name == null) {
    62              actionCtx.setActionForm(null);
    63  
    64              return (false);
    65          }
    66  
    67          if (LOG.isTraceEnabled()) {
    68              LOG.trace("Look up form-bean " + name);
    69          }
    70  
    71          // Look up the corresponding FormBeanConfig (if any)
    72          FormBeanConfig formBeanConfig =
    73              actionConfig.getModuleConfig().findFormBeanConfig(name);
    74  
    75          if (formBeanConfig == null) {
    76              LOG.warn("No FormBeanConfig found in module "
    77                  + actionConfig.getModuleConfig().getPrefix() + " under name "
    78                  + name);
    79              actionCtx.setActionForm(null);
    80  
    81              return (false);
    82          }
    83  
    84          Map scope = actionCtx.getScope(actionConfig.getScope());
    85  
    86          ActionForm instance;
    87  
    88          instance = (ActionForm) scope.get(actionConfig.getAttribute());
    89  
    90          // Can we recycle the existing instance (if any)?
    91          if (!formBeanConfig.canReuse(instance)) {
    92              instance = formBeanConfig.createActionForm(actionCtx);
    93          }
    94  
    95          // TODO: Remove ServletActionContext when ActionForm no longer
    96          //  directly depends on ActionServlet
    97          if (actionCtx instanceof ServletActionContext) {
    98              // The servlet property of ActionForm is transient, so
    99              // ActionForms which are restored from a serialized state
    100             // need to have their servlet restored.
    101             ServletActionContext sac = (ServletActionContext) actionCtx;
    102 
    103             instance.setServlet(sac.getActionServlet());
    104         }
    105 
    106         actionCtx.setActionForm(instance);
    107 
    108         scope.put(actionConfig.getAttribute(), instance);
    109 
    110         return (false);
    111     }
    112 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
