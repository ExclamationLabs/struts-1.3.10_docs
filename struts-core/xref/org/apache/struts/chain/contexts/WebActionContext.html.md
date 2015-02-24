[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/contexts/WebActionContext.html.md)


    1   /*
    2    * $Id: WebActionContext.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.contexts;
    22  
    23  import org.apache.commons.chain.web.WebContext;
    24  import org.apache.struts.Globals;
    25  import org.apache.struts.config.ModuleConfig;
    26  
    27  import java.util.Map;
    28  
    29  /**
    30   * <p> Provide a Subclass of ActionContextBase which is understood to be
    31   * wrapping an instance of <code>org.apache.commons.chain.web.WebContext</code>.
    32   * </p>
    33   */
    34  public class WebActionContext extends ActionContextBase {
    35      /**
    36       * Instantiate this composite by wrapping an instance of WebContext.
    37       *
    38       * @param context The WebContext to wrap
    39       */
    40      public WebActionContext(WebContext context) {
    41          super(context);
    42      }
    43  
    44      /**
    45       * Provide the wrapped WebContext for this composite.
    46       *
    47       * @return The wrapped WebContext
    48       */
    49      protected WebContext webContext() {
    50          return (WebContext) this.getBaseContext();
    51      }
    52  
    53      public void release() {
    54          super.release();
    55      }
    56  
    57      // -------------------------------
    58      // WebContext property wrappers
    59      // -------------------------------
    60  
    61      /**
    62       * <p> Return an immutable Map that maps header names to the first (or
    63       * only) header value (as a String). </p>
    64       *
    65       * @return A immutable Map of web request header names
    66       */
    67      public Map getHeader() {
    68          return webContext().getHeader();
    69      }
    70  
    71      /**
    72       * <p> Return an immutable Map that maps header names to the set of all
    73       * values specified in the request (as a String array). Header names must
    74       * be matched in a case-insensitive manner. </p>
    75       *
    76       * @return An immutable Map of web request header values
    77       */
    78      public Map getHeaderValues() {
    79          return webContext().getHeaderValues();
    80      }
    81  
    82      /**
    83       * <p> Return an immutable Map that maps context application
    84       * initialization parameters to their values. </p>
    85       *
    86       * @return An immutable Map of web context initialization parameters
    87       */
    88      public Map getInitParam() {
    89          return webContext().getInitParam();
    90      }
    91  
    92      /**
    93       * <p> Return a map whose keys are <code>String</code> request parameter
    94       * names and whose values are <code>String</code> values. </p> <p> For
    95       * parameters which were submitted with more than one value, only one
    96       * value will be returned, as if one called
    97       * <code>ServletRequest.getParameter(String)</code>
    98       * </p>
    99       *
    100      * @return A map of web request parameters
    101      */
    102     public Map getParam() {
    103         return webContext().getParam();
    104     }
    105 
    106     /**
    107      * <p> Return a map whose keys are <code>String</code> request parameter
    108      * names and whose values are <code>String[]</code> values. </p>
    109      *
    110      * @return A map of web request parameter values (as an array)
    111      */
    112     public Map getParamValues() {
    113         return webContext().getParamValues();
    114     }
    115 
    116     public Map getApplicationScope() {
    117         return webContext().getApplicationScope();
    118     }
    119 
    120     public Map getRequestScope() {
    121         return webContext().getRequestScope();
    122     }
    123 
    124     public Map getParameterMap() {
    125         return getParamValues();
    126     }
    127 
    128     public Map getSessionScope() {
    129         return webContext().getSessionScope();
    130     }
    131 
    132     // ISSUE: AbstractSelectModule set the precedent of doing this at the
    133     // "web context" level instead of the ServletWebContext level.
    134     // Consider whether that's how we want to do it universally for other
    135     // manipulations of the RequestScope or not...
    136     public void setModuleConfig(ModuleConfig moduleConfig) {
    137         super.setModuleConfig(moduleConfig);
    138         this.getRequestScope().put(Globals.MODULE_KEY, moduleConfig);
    139     }
    140 
    141     /**
    142      * @see org.apache.struts.chain.contexts.ActionContext#getModuleConfig()
    143      */
    144     public ModuleConfig getModuleConfig() {
    145         ModuleConfig mc = super.getModuleConfig();
    146 
    147         if (mc == null) {
    148             mc = (ModuleConfig) this.getRequestScope().get(Globals.MODULE_KEY);
    149         }
    150 
    151         return mc;
    152     }
    153 
    154     // ISSUE:  AbstractSelectModule set the precedent of doing this at the
    155     // "web context" level instead of the ServletWebContext level.  Consider
    156     // whether that's how we want to do it universally for other manipulations
    157     // of the RequestScope or not...
    158     public void setCancelled(Boolean cancelled) {
    159         super.setCancelled(cancelled);
    160 
    161         // historic semantics of "isCancelled" are to consider any non-null
    162         // value in the request under Globals.CANCEL_KEY as "yes, this was
    163         // cancelled."
    164         if ((cancelled != null) && cancelled.booleanValue()) {
    165             this.getRequestScope().put(Globals.CANCEL_KEY, cancelled);
    166         } else {
    167             this.getRequestScope().remove(Globals.CANCEL_KEY);
    168         }
    169     }
    170 
    171     public Boolean getCancelled() {
    172         Boolean cancelled = super.getCancelled();
    173 
    174         if (cancelled == null) {
    175             cancelled =
    176                 (Boolean) this.getRequestScope().get(Globals.CANCEL_KEY);
    177         }
    178 
    179         return cancelled;
    180     }
    181 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
