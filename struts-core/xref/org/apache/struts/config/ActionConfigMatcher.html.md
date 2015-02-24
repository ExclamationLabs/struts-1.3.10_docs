[View Javadoc](../../../../../apidocs/org/apache/struts/config/ActionConfigMatcher.html.md)


    1   /*
    2    * $Id: ActionConfigMatcher.java 530002 2007-04-18 12:35:44Z pbenedict $
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
    21  package org.apache.struts.config;
    22  
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.action.ActionForward;
    27  import org.apache.struts.util.WildcardHelper;
    28  
    29  import java.io.Serializable;
    30  
    31  import java.util.ArrayList;
    32  import java.util.HashMap;
    33  import java.util.Iterator;
    34  import java.util.List;
    35  import java.util.Map;
    36  import java.util.Properties;
    37  
    38  /**
    39   * <p> Matches paths against pre-compiled wildcard expressions pulled from
    40   * action configs. It uses the wildcard matcher from the Apache Cocoon
    41   * project. Patterns will be matched in the order they exist in the Struts
    42   * config file. The last match wins, so more specific patterns should be
    43   * defined after less specific patterns.
    44   *
    45   * @since Struts 1.2
    46   */
    47  public class ActionConfigMatcher implements Serializable {
    48      /**
    49       * <p> The logging instance </p>
    50       */
    51      private static final Log log = LogFactory.getLog(ActionConfigMatcher.class);
    52  
    53      /**
    54       * <p> Handles all wildcard pattern matching. </p>
    55       */
    56      private static final WildcardHelper wildcard = new WildcardHelper();
    57  
    58      /**
    59       * <p> The compiled paths and their associated ActionConfig's </p>
    60       */
    61      private List compiledPaths;
    62  
    63      /**
    64       * <p> Finds and precompiles the wildcard patterns from the ActionConfig
    65       * "path" attributes. ActionConfig's will be evaluated in the order they
    66       * exist in the Struts config file. Only paths that actually contain a
    67       * wildcard will be compiled. </p>
    68       *
    69       * @param configs An array of ActionConfig's to process
    70       */
    71      public ActionConfigMatcher(ActionConfig[] configs) {
    72          compiledPaths = new ArrayList();
    73  
    74          int[] pattern;
    75          String path;
    76  
    77          for (int x = 0; x < configs.length; x++) {
    78              path = configs[x].getPath();
    79  
    80              if ((path != null) && (path.indexOf('*') > -1)) {
    81                  if ((path.length() > 0) && (path.charAt(0) == '/')) {
    82                      path = path.substring(1);
    83                  }
    84  
    85                  if (log.isDebugEnabled()) {
    86                      log.debug("Compiling action config path '" + path + "'");
    87                  }
    88  
    89                  pattern = wildcard.compilePattern(path);
    90                  compiledPaths.add(new Mapping(pattern, configs[x]));
    91              }
    92          }
    93      }
    94  
    95      /**
    96       * <p> Matches the path against the compiled wildcard patterns. </p>
    97       *
    98       * @param path The portion of the request URI for selecting a config.
    99       * @return The action config if matched, else null
    100      */
    101     public ActionConfig match(String path) {
    102         ActionConfig config = null;
    103 
    104         if (compiledPaths.size() > 0) {
    105             if (log.isDebugEnabled()) {
    106                 log.debug("Attempting to match '" + path
    107                     + "' to a wildcard pattern");
    108             }
    109 
    110             if ((path.length() > 0) && (path.charAt(0) == '/')) {
    111                 path = path.substring(1);
    112             }
    113 
    114             Mapping m;
    115             HashMap vars = new HashMap();
    116 
    117             for (Iterator i = compiledPaths.iterator(); i.hasNext();) {
    118                 m = (Mapping) i.next();
    119 
    120                 if (wildcard.match(vars, path, m.getPattern())) {
    121                     if (log.isDebugEnabled()) {
    122                         log.debug("Path matches pattern '"
    123                             + m.getActionConfig().getPath() + "'");
    124                     }
    125 
    126                     config =
    127                         convertActionConfig(path,
    128                             (ActionConfig) m.getActionConfig(), vars);
    129                 }
    130             }
    131         }
    132 
    133         return config;
    134     }
    135 
    136     /**
    137      * <p> Clones the ActionConfig and its children, replacing various
    138      * properties with the values of the wildcard-matched strings. </p>
    139      *
    140      * @param path The requested path
    141      * @param orig The original ActionConfig
    142      * @param vars A Map of wildcard-matched strings
    143      * @return A cloned ActionConfig with appropriate properties replaced with
    144      *         wildcard-matched values
    145      */
    146     protected ActionConfig convertActionConfig(String path, ActionConfig orig,
    147         Map vars) {
    148         ActionConfig config = null;
    149 
    150         try {
    151             config = (ActionConfig) BeanUtils.cloneBean(orig);
    152         } catch (Exception ex) {
    153             log.warn("Unable to clone action config, recommend not using "
    154                 + "wildcards", ex);
    155 
    156             return null;
    157         }
    158 
    159         config.setName(convertParam(orig.getName(), vars));
    160 
    161         if ((path.length() == 0) || (path.charAt(0) != '/')) {
    162             path = "/" + path;
    163         }
    164 
    165         config.setPath(path);
    166         config.setType(convertParam(orig.getType(), vars));
    167         config.setRoles(convertParam(orig.getRoles(), vars));
    168         config.setParameter(convertParam(orig.getParameter(), vars));
    169         config.setAttribute(convertParam(orig.getAttribute(), vars));
    170         config.setForward(convertParam(orig.getForward(), vars));
    171         config.setInclude(convertParam(orig.getInclude(), vars));
    172         config.setInput(convertParam(orig.getInput(), vars));
    173         config.setCatalog(convertParam(orig.getCatalog(), vars));
    174         config.setCommand(convertParam(orig.getCommand(), vars));
    175         config.setMultipartClass(convertParam(orig.getMultipartClass(), vars));
    176         config.setPrefix(convertParam(orig.getPrefix(), vars));
    177         config.setSuffix(convertParam(orig.getSuffix(), vars));
    178 
    179         ForwardConfig[] fConfigs = orig.findForwardConfigs();
    180         ForwardConfig cfg;
    181 
    182         for (int x = 0; x < fConfigs.length; x++) {
    183             try {
    184                 cfg = (ActionForward) BeanUtils.cloneBean(fConfigs[x]);
    185             } catch (Exception ex) {
    186                 log.warn("Unable to clone action config, recommend not using "
    187                         + "wildcards", ex);
    188                 return null;
    189             }
    190             cfg.setName(fConfigs[x].getName());
    191             cfg.setPath(convertParam(fConfigs[x].getPath(), vars));
    192             cfg.setRedirect(fConfigs[x].getRedirect());
    193             cfg.setCommand(convertParam(fConfigs[x].getCommand(), vars));
    194             cfg.setCatalog(convertParam(fConfigs[x].getCatalog(), vars));
    195             cfg.setModule(convertParam(fConfigs[x].getModule(), vars));
    196 
    197             replaceProperties(fConfigs[x].getProperties(), cfg.getProperties(),
    198                 vars);
    199 
    200             config.removeForwardConfig(fConfigs[x]);
    201             config.addForwardConfig(cfg);
    202         }
    203 
    204         replaceProperties(orig.getProperties(), config.getProperties(), vars);
    205 
    206         ExceptionConfig[] exConfigs = orig.findExceptionConfigs();
    207 
    208         for (int x = 0; x < exConfigs.length; x++) {
    209             config.addExceptionConfig(exConfigs[x]);
    210         }
    211 
    212         config.freeze();
    213 
    214         return config;
    215     }
    216 
    217     /**
    218      * <p> Replaces placeholders from one Properties values set to another.
    219      * </p>
    220      *
    221      * @param orig  The original properties set with placehold values
    222      * @param props The target properties to store the processed values
    223      * @param vars  A Map of wildcard-matched strings
    224      */
    225     protected void replaceProperties(Properties orig, Properties props, Map vars) {
    226         Map.Entry entry = null;
    227 
    228         for (Iterator i = orig.entrySet().iterator(); i.hasNext();) {
    229             entry = (Map.Entry) i.next();
    230             props.setProperty((String) entry.getKey(),
    231                 convertParam((String) entry.getValue(), vars));
    232         }
    233     }
    234 
    235     /**
    236      * <p> Inserts into a value wildcard-matched strings where specified.
    237      * </p>
    238      *
    239      * @param val  The value to convert
    240      * @param vars A Map of wildcard-matched strings
    241      * @return The new value
    242      */
    243     protected String convertParam(String val, Map vars) {
    244         if (val == null) {
    245             return null;
    246         } else if (val.indexOf("{") == -1) {
    247             return val;
    248         }
    249 
    250         Map.Entry entry;
    251         StringBuffer key = new StringBuffer("{0}");
    252         StringBuffer ret = new StringBuffer(val);
    253         String keyTmp;
    254         int x;
    255 
    256         for (Iterator i = vars.entrySet().iterator(); i.hasNext();) {
    257             entry = (Map.Entry) i.next();
    258             key.setCharAt(1, ((String) entry.getKey()).charAt(0));
    259             keyTmp = key.toString();
    260 
    261             // Replace all instances of the placeholder
    262             while ((x = ret.toString().indexOf(keyTmp)) > -1) {
    263                 ret.replace(x, x + 3, (String) entry.getValue());
    264             }
    265         }
    266 
    267         return ret.toString();
    268     }
    269 
    270     /**
    271      * <p> Stores a compiled wildcard pattern and the ActionConfig it came
    272      * from. </p>
    273      */
    274     private class Mapping implements Serializable {
    275         /**
    276          * <p> The compiled pattern. </p>
    277          */
    278         private int[] pattern;
    279 
    280         /**
    281          * <p> The original ActionConfig. </p>
    282          */
    283         private ActionConfig config;
    284 
    285         /**
    286          * <p> Contructs a read-only Mapping instance. </p>
    287          *
    288          * @param pattern The compiled pattern
    289          * @param config  The original ActionConfig
    290          */
    291         public Mapping(int[] pattern, ActionConfig config) {
    292             this.pattern = pattern;
    293             this.config = config;
    294         }
    295 
    296         /**
    297          * <p> Gets the compiled wildcard pattern. </p>
    298          *
    299          * @return The compiled pattern
    300          */
    301         public int[] getPattern() {
    302             return this.pattern;
    303         }
    304 
    305         /**
    306          * <p> Gets the ActionConfig that contains the pattern. </p>
    307          *
    308          * @return The associated ActionConfig
    309          */
    310         public ActionConfig getActionConfig() {
    311             return this.config;
    312         }
    313     }
    314 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
