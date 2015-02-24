[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/AbstractPopulateActionForm.html.md)


    1   /*
    2    * $Id: AbstractPopulateActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.action.ActionForm;
    25  import org.apache.struts.chain.contexts.ActionContext;
    26  import org.apache.struts.config.ActionConfig;
    27  
    28  import java.util.Map;
    29  
    30  /**
    31   * <p>Populate the form bean (if any) for this request.</p>
    32   *
    33   * @version $Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    34   *          $
    35   */
    36  public abstract class AbstractPopulateActionForm extends ActionCommandBase {
    37      // ---------------------------------------------------------- Public Methods
    38  
    39      /**
    40       * <p>Populate the form bean (if any) for this request.</p>
    41       *
    42       * @param actionCtx The <code>Context</code> for the current request
    43       * @return <code>false</code> so that processing continues
    44       * @throws Exception On an unexpected error
    45       */
    46      public boolean execute(ActionContext actionCtx)
    47          throws Exception {
    48          // Is there a form bean for this request?
    49          ActionForm actionForm = actionCtx.getActionForm();
    50  
    51          if (actionForm == null) {
    52              return (false);
    53          }
    54  
    55          // Reset the form bean property values
    56          ActionConfig actionConfig = actionCtx.getActionConfig();
    57  
    58          reset(actionCtx, actionConfig, actionForm);
    59  
    60          populate(actionCtx, actionConfig, actionForm);
    61  
    62          handleCancel(actionCtx, actionConfig, actionForm);
    63  
    64          return (false);
    65      }
    66  
    67      // ------------------------------------------------------- Protected Methods
    68  
    69      /**
    70       * <p>Call the <code>reset()</code> method on the specified form
    71       * bean.</p>
    72       *
    73       * @param context      The context for this request
    74       * @param actionConfig The actionConfig for this request
    75       * @param actionForm   The form bean for this request
    76       */
    77      protected abstract void reset(ActionContext context,
    78          ActionConfig actionConfig, ActionForm actionForm);
    79  
    80      /**
    81       * <p> Populate the given <code>ActionForm</code> with request parameter
    82       * values, taking into account any prefix/suffix values configured on the
    83       * given <code>ActionConfig</code>. </p>
    84       *
    85       * @param context      The ActionContext we are processing
    86       * @param actionConfig The ActionConfig we are processing
    87       * @param actionForm   The ActionForm we are processing
    88       * @throws Exception On an unexpected error
    89       */
    90      protected abstract void populate(ActionContext context,
    91          ActionConfig actionConfig, ActionForm actionForm)
    92          throws Exception;
    93  
    94      // original implementation casting context to WebContext is not safe
    95      // when the input value is an ActionContext.
    96  
    97      /**
    98       * <p>For a given request parameter name, trim off any prefix and/or
    99       * suffix which are defined in <code>actionConfig</code> and return what
    100      * remains. If either prefix or suffix is defined, then return null for
    101      * <code>name</code> values which do not begin or end accordingly.</p>
    102      *
    103      * @param actionConfig The ActionConfig we are processing
    104      * @param name         The request parameter name to proceess
    105      * @return The request parameter name trimmed of any suffix or prefix
    106      */
    107     protected String trimParameterName(ActionConfig actionConfig, String name) {
    108         String stripped = name;
    109         String prefix = actionConfig.getPrefix();
    110         String suffix = actionConfig.getSuffix();
    111 
    112         if (prefix != null) {
    113             if (!stripped.startsWith(prefix)) {
    114                 return null;
    115             }
    116 
    117             stripped = stripped.substring(prefix.length());
    118         }
    119 
    120         if (suffix != null) {
    121             if (!stripped.endsWith(suffix)) {
    122                 return null;
    123             }
    124 
    125             stripped =
    126                 stripped.substring(0, stripped.length() - suffix.length());
    127         }
    128 
    129         return stripped;
    130     }
    131 
    132     /**
    133      * <p>Take into account whether the request includes any defined value for
    134      * the global "cancel" parameter.</p> <p> An issue was raised (but I don't
    135      * think a Bugzilla ticket created) about the security implications of
    136      * using a well-known cancel property which skips form validation, as you
    137      * may not write your actions to deal with the cancellation case. </p>
    138      *
    139      * @param context      The ActionContext we are processing
    140      * @param actionConfig The ActionConfig we are processing
    141      * @param actionForm   The ActionForm we are processing
    142      * @throws Exception On an unexpected error
    143      * @see Globals.CANCEL_PROPERTY
    144      * @see Globals.CANCEL_PROPERTY_X
    145      */
    146     protected void handleCancel(ActionContext context,
    147         ActionConfig actionConfig, ActionForm actionForm)
    148         throws Exception {
    149         Map paramValues = context.getParameterMap();
    150 
    151         // Set the cancellation attribute if appropriate
    152         if ((paramValues.get(Globals.CANCEL_PROPERTY) != null)
    153             || (paramValues.get(Globals.CANCEL_PROPERTY_X) != null)) {
    154             context.setCancelled(Boolean.TRUE);
    155         } else {
    156             context.setCancelled(Boolean.FALSE);
    157         }
    158     }
    159 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
