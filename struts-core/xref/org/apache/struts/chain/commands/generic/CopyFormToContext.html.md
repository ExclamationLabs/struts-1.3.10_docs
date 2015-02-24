[View Javadoc](../../../../../../../apidocs/org/apache/struts/chain/commands/generic/CopyFormToContext.html.md)


    1   /*
    2    * $Id: CopyFormToContext.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands.generic;
    22  
    23  import org.apache.struts.action.ActionForm;
    24  import org.apache.struts.chain.commands.ActionCommandBase;
    25  import org.apache.struts.chain.contexts.ActionContext;
    26  import org.apache.struts.chain.contexts.ActionContextBase;
    27  import org.apache.struts.config.ActionConfig;
    28  
    29  /**
    30   * <p>Subclass this command and configure it as part of a per-forward chain to
    31   * perform any necessary pre-population or other preparation for a form before
    32   * control is dispatched to the view layer.</p>
    33   *
    34   * @version $Id: CopyFormToContext.java 471754 2006-11-06 14:55:09Z husted $
    35   */
    36  public class CopyFormToContext extends ActionCommandBase {
    37      // ------------------------------------------------------ Instance Variables
    38  
    39      /**
    40       * <p>The name of a form bean as configured in a struts-config.xml file
    41       * for this module.  </p>
    42       *
    43       * <p> Either actionPath or both this and scope are required configuration
    44       * properties.</p>
    45       */
    46      private String formName = null;
    47  
    48      /**
    49       * <p>The name of a scope, such as "request" or "session" in which the
    50       * form to be prepared will be placed for reference by the view and other
    51       * parts of Struts.</p>
    52       *
    53       * <p>Either <code>actionPath</code> or both this and
    54       * <code>formName</code> are required configuration properties.</p>
    55       */
    56      private String scope = null;
    57  
    58      /**
    59       * <p>The path of an <code>&lt;action&gt;</code> mapping as configured in
    60       * a <code>struts-config.xml</code> file for this module.  This action
    61       * will be looked up, and its <code>name</code> and <code>scope</code>
    62       * values will be used as if those values were configured directly in this
    63       * instance's <code>formName</code> and <code>scope</code>
    64       * properties.</p>
    65       *
    66       * <p>Either <code>this</code> or both <code>scope</code> and
    67       * <code>formName</code> are required configuration properties.</p>
    68       */
    69      private String actionPath = null;
    70  
    71      /**
    72       * The context key under which the form which was looked up will be
    73       * stored. Defaults to "actionForm" but may be overridden in cases where
    74       * the "request" ActionForm must be preserved.
    75       */
    76      private String toKey = ActionContextBase.ACTION_FORM_KEY;
    77  
    78      // ------------------------------------------------------ Properties
    79  
    80      /**
    81       * <p>Return ActionPath property.</p>
    82       *
    83       * @return ActionPath property
    84       */
    85      public String getActionPath() {
    86          return this.actionPath;
    87      }
    88  
    89      /**
    90       * <p>Set ActionPath property.</p>
    91       *
    92       * @param actionPath New valuefor ActionPath
    93       */
    94      public void setActionPath(String actionPath) {
    95          this.actionPath = actionPath;
    96      }
    97  
    98      /**
    99       * <p>Return FormName property.</p>
    100      *
    101      * @return FormName property
    102      */
    103     public String getFormName() {
    104         return this.formName;
    105     }
    106 
    107     /**
    108      * <p>Set FormName property.</p>
    109      *
    110      * @param formName New valuefor FormName
    111      */
    112     public void setFormName(String formName) {
    113         this.formName = formName;
    114     }
    115 
    116     /**
    117      * <p>Return Scope property.</p>
    118      *
    119      * @return Scope property
    120      */
    121     public String getScope() {
    122         return this.scope;
    123     }
    124 
    125     /**
    126      * <p>Set Scope property.</p>
    127      *
    128      * @param scope New valuefor Scope
    129      */
    130     public void setScope(String scope) {
    131         this.scope = scope;
    132     }
    133 
    134     /**
    135      * <p>Return ToKey property.</p>
    136      *
    137      * @return ToKey property
    138      */
    139     public String getToKey() {
    140         return this.toKey;
    141     }
    142 
    143     /**
    144      * <p>Set ToKey property.</p>
    145      *
    146      * @param toKey New valuefor FormName
    147      */
    148     public void setToKey(String toKey) {
    149         this.toKey = toKey;
    150     }
    151 
    152     // ------------------------------------------------------
    153 
    154     /**
    155      * <p>Look up an ActionForm instance based on the configured properties of
    156      * this command and copy it into the <code>Context</code>.  After this
    157      * command successfully executes, an ActionForm instance will exist in the
    158      * specified scope and will be available, for example for backing fields
    159      * in an HTML form.  It will also be in the <code>ActionContext</code>
    160      * available for another command to do prepopulation of values or other
    161      * preparation.</p>
    162      *
    163      * @param actionContext Our ActionContext
    164      * @return TRUE if processing should halt
    165      * @throws Exception on any error
    166      */
    167     public boolean execute(ActionContext actionContext)
    168         throws Exception {
    169         ActionForm form = findOrCreateForm(actionContext);
    170 
    171         if (isEmpty(getToKey())) {
    172             throw new IllegalStateException("Property 'toKey' must be defined.");
    173         }
    174 
    175         actionContext.put(getToKey(), form);
    176 
    177         return false;
    178     }
    179 
    180     /**
    181      * <p>Based on the properties of this command and the given
    182      * <code>ActionContext</code>, find or create an ActionForm instance for
    183      * preparation.</p>
    184      *
    185      * @param context ActionContextBase class that we are processing
    186      * @return ActionForm instance
    187      * @throws IllegalArgumentException On ActionConfig not found
    188      * @throws IllegalStateException    On undefined scope and formbean
    189      * @throws IllegalAccessException   On failed instantiation
    190      * @throws InstantiationException   If ActionContext is not subsclass of
    191      *                                  ActionContextBase
    192      */
    193     protected ActionForm findOrCreateForm(ActionContext context)
    194         throws IllegalAccessException, InstantiationException {
    195         String effectiveFormName;
    196         String effectiveScope;
    197 
    198         if (!(isEmpty(this.getActionPath()))) {
    199             ActionConfig actionConfig =
    200                 context.getModuleConfig().findActionConfig(this.getActionPath());
    201 
    202             if (actionConfig == null) {
    203                 throw new IllegalArgumentException(
    204                     "No ActionConfig found for path " + this.getActionPath());
    205             }
    206 
    207             effectiveFormName = actionConfig.getName();
    208             effectiveScope = actionConfig.getScope();
    209         } else {
    210             effectiveFormName = this.getFormName();
    211             effectiveScope = this.getScope();
    212         }
    213 
    214         if (isEmpty(effectiveScope) || isEmpty(effectiveFormName)) {
    215             throw new IllegalStateException("Both scope [" + effectiveScope
    216                 + "] and formName [" + effectiveFormName + "] must be defined.");
    217         }
    218 
    219         return findOrCreateForm(context, effectiveFormName, effectiveScope);
    220     }
    221 
    222     /**
    223      * <p>Actually find or create an instance of ActionForm configured under
    224      * the form-bean-name <code>effectiveFormName</code>, looking in in the
    225      * <code>ActionContext's</code> scope as identified by
    226      * <code>effectiveScope</code>. If a form is created, it will also be
    227      * stored in that scope.</p>
    228      *
    229      * <p><b>NOTE:</b> This specific method depends on the instance of
    230      * <code>ActionContext</code> which is passed being a subclass of
    231      * <code>ActionContextBase</code>, which implements the utility method
    232      * <code>findOrCreateActionForm</code>. </p>
    233      *
    234      * @param ctx               The ActionContext we are processing
    235      * @param effectiveFormName the target form name
    236      * @param effectiveScope    The target scope
    237      * @return ActionForm instnace, storing in scope if created
    238      * @throws InstantiationException   If ActionContext is not subsclass of
    239      *                                  ActionContextBase
    240      * @throws InstantiationException   If object cannot be created
    241      * @throws IllegalArgumentException On form not found in/ scope
    242      * @throws IllegalAccessException   On failed instantiation
    243      * @throws IllegalStateException    If ActionContext is not a subclass of
    244      *                                  ActionBase
    245      */
    246     protected ActionForm findOrCreateForm(ActionContext ctx,
    247         String effectiveFormName, String effectiveScope)
    248         throws IllegalAccessException, InstantiationException {
    249         ActionContextBase context;
    250 
    251         try {
    252             context = (ActionContextBase) ctx;
    253         } catch (ClassCastException e) {
    254             throw new IllegalStateException("ActionContext [" + ctx + "]"
    255                 + " must be subclass of ActionContextBase");
    256         }
    257 
    258         ActionForm form =
    259             context.findOrCreateActionForm(effectiveFormName, effectiveScope);
    260 
    261         if (form == null) {
    262             throw new IllegalArgumentException("No form found under scope ["
    263                 + effectiveScope + "] and formName [" + effectiveFormName + "]");
    264         }
    265 
    266         return form;
    267     }
    268 
    269     /**
    270      * <p>Convenience method to test for an empty string.</p>
    271      *
    272      * @param test String to test
    273      * @return TRUE if test is null or zero-length
    274      */
    275     private boolean isEmpty(String test) {
    276         return (test == null) || (test.trim().length() == 0);
    277     }
    278 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
