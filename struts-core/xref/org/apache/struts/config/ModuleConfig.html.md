[View Javadoc](../../../../../apidocs/org/apache/struts/config/ModuleConfig.html.md)


    1   /*
    2    * $Id: ModuleConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  
    24  /**
    25   * <p>The collection of static configuration information that describes a
    26   * Struts-based module.  Multiple modules are identified by a <em>prefix</em>
    27   * at the beginning of the context relative portion of the request URI.  If no
    28   * module prefix can be matched, the default configuration (with a prefix
    29   * equal to a zero-length string) is selected, which is elegantly backwards
    30   * compatible with the previous Struts behavior that only supported one
    31   * module.</p>
    32   *
    33   * @version $Rev: 471754 $ $Date: 2005-08-06 04:12:10 -0400 (Sat, 06 Aug 2005)
    34   *          $
    35   * @since Struts 1.1
    36   */
    37  public interface ModuleConfig {
    38      /**
    39       * <p> Has this module been completely configured yet.  Once this flag has
    40       * been set, any attempt to modify the configuration will return an
    41       * IllegalStateException. </p>
    42       */
    43      boolean getConfigured();
    44  
    45      /**
    46       * <p> The controller configuration object for this module. </p>
    47       */
    48      ControllerConfig getControllerConfig();
    49  
    50      /**
    51       * <p> The controller configuration object for this module. </p>
    52       *
    53       * @param cc The controller configuration object for this module.
    54       */
    55      void setControllerConfig(ControllerConfig cc);
    56  
    57      /**
    58       * <p> The prefix of the context-relative portion of the request URI, used
    59       * to select this configuration versus others supported by the controller
    60       * servlet.  A configuration with a prefix of a zero-length String is the
    61       * default configuration for this web module. </p>
    62       */
    63      String getPrefix();
    64  
    65      /**
    66       * <p> The prefix of the context-relative portion of the request URI, used
    67       * to select this configuration versus others supported by the controller
    68       * servlet.  A configuration with a prefix of a zero-length String is the
    69       * default configuration for this web module. </p>
    70       *
    71       * @param prefix The prefix of the context-relative portion of the request
    72       *               URI.
    73       */
    74      public void setPrefix(String prefix);
    75  
    76      /**
    77       * <p> The default class name to be used when creating action form bean
    78       * instances. </p>
    79       */
    80      String getActionFormBeanClass();
    81  
    82      /**
    83       * <p> The default class name to be used when creating action form bean
    84       * instances. </p>
    85       *
    86       * @param actionFormBeanClass default class name to be used when creating
    87       *                            action form bean instances.
    88       */
    89      void setActionFormBeanClass(String actionFormBeanClass);
    90  
    91      /**
    92       * <p> The default class name to be used when creating action mapping
    93       * instances. </p>
    94       */
    95      String getActionMappingClass();
    96  
    97      /**
    98       * <p> The default class name to be used when creating action mapping
    99       * instances. </p>
    100      *
    101      * @param actionMappingClass default class name to be used when creating
    102      *                           action mapping instances.
    103      */
    104     void setActionMappingClass(String actionMappingClass);
    105 
    106     /**
    107      * <p> Add a new <code>ActionConfig</code> instance to the set associated
    108      * with this module. </p>
    109      *
    110      * @param config The new configuration instance to be added
    111      * @throws IllegalStateException if this module configuration has been
    112      *                               frozen
    113      */
    114     void addActionConfig(ActionConfig config);
    115 
    116     /**
    117      * <p> Add a new <code>ExceptionConfig</code> instance to the set
    118      * associated with this module. </p>
    119      *
    120      * @param config The new configuration instance to be added
    121      * @throws IllegalStateException if this module configuration has been
    122      *                               frozen
    123      */
    124     void addExceptionConfig(ExceptionConfig config);
    125 
    126     /**
    127      * <p> Add a new <code>FormBeanConfig</code> instance to the set
    128      * associated with this module. </p>
    129      *
    130      * @param config The new configuration instance to be added
    131      * @throws IllegalStateException if this module configuration has been
    132      *                               frozen
    133      */
    134     void addFormBeanConfig(FormBeanConfig config);
    135 
    136     /**
    137      * <p> The default class name to be used when creating action forward
    138      * instances. </p>
    139      */
    140     String getActionForwardClass();
    141 
    142     /**
    143      * <p> The default class name to be used when creating action forward
    144      * instances. </p>
    145      *
    146      * @param actionForwardClass default class name to be used when creating
    147      *                           action forward instances.
    148      */
    149     void setActionForwardClass(String actionForwardClass);
    150 
    151     /**
    152      * <p> Add a new <code>ForwardConfig</code> instance to the set of global
    153      * forwards associated with this module. </p>
    154      *
    155      * @param config The new configuration instance to be added
    156      * @throws IllegalStateException if this module configuration has been
    157      *                               frozen
    158      */
    159     void addForwardConfig(ForwardConfig config);
    160 
    161     /**
    162      * <p> Add a new <code>MessageResourcesConfig</code> instance to the set
    163      * associated with this module. </p>
    164      *
    165      * @param config The new configuration instance to be added
    166      * @throws IllegalStateException if this module configuration has been
    167      *                               frozen
    168      */
    169     void addMessageResourcesConfig(MessageResourcesConfig config);
    170 
    171     /**
    172      * <p> Add a newly configured {@link PlugInConfig} instance to the set of
    173      * plug-in Actions for this module. </p>
    174      *
    175      * @param plugInConfig The new configuration instance to be added
    176      */
    177     void addPlugInConfig(PlugInConfig plugInConfig);
    178 
    179     /**
    180      * <p> Return the action configuration for the specified path, if any;
    181      * otherwise return <code>null</code>. </p>
    182      *
    183      * @param path Path of the action configuration to return
    184      */
    185     ActionConfig findActionConfig(String path);
    186 
    187     /**
    188      * <p> Return the action configurations for this module.  If there are
    189      * none, a zero-length array is returned. </p>
    190      */
    191     ActionConfig[] findActionConfigs();
    192 
    193     /**
    194      * <p>Returns the action configuration for the specifed action
    195      * action identifier.</p>
    196      *
    197      * @param actionId the action identifier
    198      * @return the action config if found; otherwise <code>null</code>
    199      * @see ActionConfig#getActionId()
    200      * @since Struts 1.3.6
    201      */
    202     ActionConfig findActionConfigId(String actionId);
    203 
    204     /**
    205      * <p> Return the exception configuration for the specified type, if any;
    206      * otherwise return <code>null</code>. </p>
    207      *
    208      * @param type Exception class name to find a configuration for
    209      */
    210     ExceptionConfig findExceptionConfig(String type);
    211 
    212     /**
    213      * <p> Perform a recursive search for an ExceptionConfig registered for
    214      * this class, or for any superclass.  This should only be used in the
    215      * case when an <code>ActionConfig</code> is not available; otherwise, use
    216      * <code>ActionConfig.findException(Class)</code> to preserve the search
    217      * order. </p>
    218      *
    219      * @param type Exception class name to find a configuration for
    220      * @see ActionConfig findException(Class)
    221      */
    222     ExceptionConfig findException(Class type);
    223 
    224     /**
    225      * <p> Return the exception configurations for this module.  If there are
    226      * none, a zero-length array is returned. </p>
    227      */
    228     ExceptionConfig[] findExceptionConfigs();
    229 
    230     /**
    231      * <p> Return the form bean configuration for the specified key, if any;
    232      * otherwise return <code>null</code>.
    233      *
    234      * @param name Name of the form bean configuration to return
    235      */
    236     FormBeanConfig findFormBeanConfig(String name);
    237 
    238     /**
    239      * <p> Return the form bean configurations for this module.  If there are
    240      * none, a zero-length array is returned. </p>
    241      */
    242     FormBeanConfig[] findFormBeanConfigs();
    243 
    244     /**
    245      * <p> Return the forward configuration for the specified key, if any;
    246      * otherwise return <code>null</code>. </p>
    247      *
    248      * @param name Name of the forward configuration to return
    249      */
    250     ForwardConfig findForwardConfig(String name);
    251 
    252     /**
    253      * <p> Return the form bean configurations for this module.  If there are
    254      * none, a zero-length array is returned. </p>
    255      */
    256     ForwardConfig[] findForwardConfigs();
    257 
    258     /**
    259      * <p> Return the message resources configuration for the specified key,
    260      * if any; otherwise return <code>null</code>. </p>
    261      *
    262      * @param key Key of the data source configuration to return
    263      */
    264     MessageResourcesConfig findMessageResourcesConfig(String key);
    265 
    266     /**
    267      * <p> Return the message resources configurations for this module. If
    268      * there are none, a zero-length array is returned. </p>
    269      */
    270     MessageResourcesConfig[] findMessageResourcesConfigs();
    271 
    272     /**
    273      * <p> Return the configured plug-in actions for this module.  If there
    274      * are none, a zero-length array is returned. </p>
    275      */
    276     PlugInConfig[] findPlugInConfigs();
    277 
    278     /**
    279      * <p> Freeze the configuration of this module.  After this method
    280      * returns, any attempt to modify the configuration will return an
    281      * IllegalStateException. </p>
    282      */
    283     void freeze();
    284 
    285     /**
    286      * <p> Remove the specified action configuration instance. </p>
    287      *
    288      * @param config ActionConfig instance to be removed
    289      * @throws IllegalStateException if this module configuration has been
    290      *                               frozen
    291      */
    292     void removeActionConfig(ActionConfig config);
    293 
    294     /**
    295      * <p> Remove the specified exception configuration instance. </p>
    296      *
    297      * @param config ActionConfig instance to be removed
    298      * @throws IllegalStateException if this module configuration has been
    299      *                               frozen
    300      */
    301     void removeExceptionConfig(ExceptionConfig config);
    302 
    303     /**
    304      * <p> Remove the specified form bean configuration instance. </p>
    305      *
    306      * @param config FormBeanConfig instance to be removed
    307      * @throws IllegalStateException if this module configuration has been
    308      *                               frozen
    309      */
    310     void removeFormBeanConfig(FormBeanConfig config);
    311 
    312     /**
    313      * <p> Remove the specified forward configuration instance. </p>
    314      *
    315      * @param config ForwardConfig instance to be removed
    316      * @throws IllegalStateException if this module configuration has been
    317      *                               frozen
    318      */
    319     void removeForwardConfig(ForwardConfig config);
    320 
    321     /**
    322      * <p> Remove the specified message resources configuration instance.
    323      * </p>
    324      *
    325      * @param config MessageResourcesConfig instance to be removed
    326      * @throws IllegalStateException if this module configuration has been
    327      *                               frozen
    328      */
    329     void removeMessageResourcesConfig(MessageResourcesConfig config);
    330 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
