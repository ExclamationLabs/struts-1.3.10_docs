[View Javadoc](../../../../../apidocs/org/apache/struts/util/ModuleUtils.html.md)


    1   /*
    2    * $Id: ModuleUtils.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.action.RequestProcessor;
    27  import org.apache.struts.config.MessageResourcesConfig;
    28  import org.apache.struts.config.ModuleConfig;
    29  
    30  import javax.servlet.ServletContext;
    31  import javax.servlet.http.HttpServletRequest;
    32  
    33  /**
    34   * General purpose utility methods related to module processing.
    35   *
    36   * @version $Rev: 471754 $
    37   * @since Struts 1.2
    38   */
    39  public class ModuleUtils {
    40      /**
    41       * The Singleton instance.
    42       */
    43      private static final ModuleUtils instance = new ModuleUtils();
    44  
    45      /**
    46       * Commons logging instance.
    47       */
    48      private static final Log log = LogFactory.getLog(ModuleUtils.class);
    49  
    50      /**
    51       * Constructor for ModuleUtils.
    52       */
    53      protected ModuleUtils() {
    54          super();
    55      }
    56  
    57      /**
    58       * Returns the Singleton instance of TagUtils.
    59       */
    60      public static ModuleUtils getInstance() {
    61          return instance;
    62      }
    63  
    64      /**
    65       * Return the current ModuleConfig object stored in request, if it exists,
    66       * null otherwise. This method can be used by plugin to retrieve the
    67       * current module config object. If no moduleConfig is found, this means
    68       * that the request haven't hit the server throught the struts servlet.
    69       * The appropriate module config can be set and found with <code>{@link
    70       * ModuleUtils#selectModule(HttpServletRequest, ServletContext)} </code>.
    71       *
    72       * @param request The servlet request we are processing
    73       * @return the ModuleConfig object from request, or null if none is set in
    74       *         the request.
    75       */
    76      public ModuleConfig getModuleConfig(HttpServletRequest request) {
    77          return (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    78      }
    79  
    80      /**
    81       * Return the desired ModuleConfig object stored in context, if it exists,
    82       * null otherwise.
    83       *
    84       * @param prefix  The module prefix of the desired module
    85       * @param context The ServletContext for this web application
    86       * @return the ModuleConfig object specified, or null if not found in the
    87       *         context.
    88       */
    89      public ModuleConfig getModuleConfig(String prefix, ServletContext context) {
    90          if ((prefix == null) || "/".equals(prefix)) {
    91              return (ModuleConfig) context.getAttribute(Globals.MODULE_KEY);
    92          } else {
    93              return (ModuleConfig) context.getAttribute(Globals.MODULE_KEY
    94                  + prefix);
    95          }
    96      }
    97  
    98      /**
    99       * Return the desired ModuleConfig object stored in context, if it exists,
    100      * otherwise return the current ModuleConfig
    101      *
    102      * @param prefix  The module prefix of the desired module
    103      * @param request The servlet request we are processing
    104      * @param context The ServletContext for this web application
    105      * @return the ModuleConfig object specified, or null if not found in the
    106      *         context.
    107      */
    108     public ModuleConfig getModuleConfig(String prefix,
    109         HttpServletRequest request, ServletContext context) {
    110         ModuleConfig moduleConfig = null;
    111 
    112         if (prefix != null) {
    113             //lookup module stored with the given prefix.
    114             moduleConfig = this.getModuleConfig(prefix, context);
    115         } else {
    116             //return the current module if no prefix was supplied.
    117             moduleConfig = this.getModuleConfig(request, context);
    118         }
    119 
    120         return moduleConfig;
    121     }
    122 
    123     /**
    124      * Return the ModuleConfig object is it exists, null otherwise.
    125      *
    126      * @param request The servlet request we are processing
    127      * @param context The ServletContext for this web application
    128      * @return the ModuleConfig object
    129      */
    130     public ModuleConfig getModuleConfig(HttpServletRequest request,
    131         ServletContext context) {
    132         ModuleConfig moduleConfig = this.getModuleConfig(request);
    133 
    134         if (moduleConfig == null) {
    135             moduleConfig = this.getModuleConfig("", context);
    136             request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    137         }
    138 
    139         return moduleConfig;
    140     }
    141 
    142     /**
    143      * Get the module name to which the specified request belong.
    144      *
    145      * @param request The servlet request we are processing
    146      * @param context The ServletContext for this web application
    147      * @return The module prefix or ""
    148      */
    149     public String getModuleName(HttpServletRequest request,
    150         ServletContext context) {
    151         // Acquire the path used to compute the module
    152         String matchPath =
    153             (String) request.getAttribute(RequestProcessor.INCLUDE_SERVLET_PATH);
    154 
    155         if (matchPath == null) {
    156             matchPath = request.getServletPath();
    157         }
    158 
    159         return this.getModuleName(matchPath, context);
    160     }
    161 
    162     /**
    163      * Get the module name to which the specified uri belong.
    164      *
    165      * @param matchPath The uri from which we want the module name.
    166      * @param context   The ServletContext for this web application
    167      * @return The module prefix or ""
    168      */
    169     public String getModuleName(String matchPath, ServletContext context) {
    170         if (log.isDebugEnabled()) {
    171             log.debug("Get module name for path " + matchPath);
    172         }
    173 
    174         String prefix = ""; // Initialize prefix before we try lookup
    175         String[] prefixes = getModulePrefixes(context);
    176 
    177         // Get all other possible prefixes
    178         int lastSlash = 0; // Initialize before loop
    179 
    180         while (prefix.equals("")
    181             && ((lastSlash = matchPath.lastIndexOf("/")) > 0)) {
    182             // We may be in a non-default module.  Try to get it's prefix.
    183             matchPath = matchPath.substring(0, lastSlash);
    184 
    185             // Match against the list of module prefixes
    186             for (int i = 0; i < prefixes.length; i++) {
    187                 if (matchPath.equals(prefixes[i])) {
    188                     prefix = prefixes[i];
    189 
    190                     break;
    191                 }
    192             }
    193         }
    194 
    195         if (log.isDebugEnabled()) {
    196             log.debug("Module name found: "
    197                 + (prefix.equals("") ? "default" : prefix));
    198         }
    199 
    200         return prefix;
    201     }
    202 
    203     /**
    204      * Return the list of module prefixes that are defined for this web
    205      * application.  <strong>NOTE</strong> - the "" prefix for the default
    206      * module is not included in this list.
    207      *
    208      * @param context The ServletContext for this web application.
    209      * @return An array of module prefixes.
    210      */
    211     public String[] getModulePrefixes(ServletContext context) {
    212         return (String[]) context.getAttribute(Globals.MODULE_PREFIXES_KEY);
    213     }
    214 
    215     /**
    216      * Select the module to which the specified request belongs, and add
    217      * corresponding request attributes to this request.
    218      *
    219      * @param request The servlet request we are processing
    220      * @param context The ServletContext for this web application
    221      */
    222     public void selectModule(HttpServletRequest request, ServletContext context) {
    223         // Compute module name
    224         String prefix = getModuleName(request, context);
    225 
    226         // Expose the resources for this module
    227         this.selectModule(prefix, request, context);
    228     }
    229 
    230     /**
    231      * Select the module to which the specified request belongs, and add
    232      * corresponding request attributes to this request.
    233      *
    234      * @param prefix  The module prefix of the desired module
    235      * @param request The servlet request we are processing
    236      * @param context The ServletContext for this web application
    237      */
    238     public void selectModule(String prefix, HttpServletRequest request,
    239         ServletContext context) {
    240         // Expose the resources for this module
    241         ModuleConfig config = getModuleConfig(prefix, context);
    242 
    243         if (config != null) {
    244             request.setAttribute(Globals.MODULE_KEY, config);
    245 
    246             MessageResourcesConfig[] mrConfig =
    247                 config.findMessageResourcesConfigs();
    248 
    249             for (int i = 0; i < mrConfig.length; i++) {
    250                 String key = mrConfig[i].getKey();
    251                 MessageResources resources =
    252                     (MessageResources) context.getAttribute(key + prefix);
    253 
    254                 if (resources != null) {
    255                     request.setAttribute(key, resources);
    256                 } else {
    257                     request.removeAttribute(key);
    258                 }
    259             }
    260         } else {
    261             request.removeAttribute(Globals.MODULE_KEY);
    262         }
    263     }
    264 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
