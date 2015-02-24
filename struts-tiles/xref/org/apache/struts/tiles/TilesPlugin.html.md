[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/TilesPlugin.html.md)


    1   /*
    2    * $Id: TilesPlugin.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.tiles;
    23  
    24  import java.util.Map;
    25  
    26  import javax.servlet.ServletContext;
    27  import javax.servlet.ServletException;
    28  import javax.servlet.UnavailableException;
    29  
    30  import org.apache.commons.logging.Log;
    31  import org.apache.commons.logging.LogFactory;
    32  import org.apache.struts.action.ActionServlet;
    33  import org.apache.struts.action.PlugIn;
    34  import org.apache.struts.action.RequestProcessor;
    35  import org.apache.struts.chain.ComposableRequestProcessor;
    36  import org.apache.struts.config.ControllerConfig;
    37  import org.apache.struts.config.ModuleConfig;
    38  import org.apache.struts.config.PlugInConfig;
    39  import org.apache.struts.util.RequestUtils;
    40  
    41  /**
    42   * Tiles Plugin used to initialize Tiles.
    43   * This plugin is to be used with Struts 1.1 in association with
    44   * {@link TilesRequestProcessor}.
    45   * <br>
    46   * This plugin creates one definition factory for each Struts-module. The definition factory
    47   * configuration is read first from 'web.xml' (backward compatibility), then it is
    48   * overloaded with values found in the plugin property values.
    49   * <br>
    50   * The plugin changes the Struts configuration by specifying a {@link TilesRequestProcessor} as
    51   * request processor. If you want to use your own RequestProcessor,
    52   * it should subclass TilesRequestProcessor.
    53   * <br>
    54   * This plugin can also be used to create one single factory for all modules.
    55   * This behavior is enabled by specifying <code>moduleAware=false</code> in each
    56   * plugin properties. In this case, the definition factory
    57   * configuration file is read by the first Tiles plugin to be initialized. The order is
    58   * determined by the order of modules declaration in web.xml. The first module
    59   * is always the default one if it exists.
    60   * The plugin should be declared in each struts-config.xml file in order to
    61   * properly initialize the request processor.
    62   * @since Struts 1.1
    63   */
    64  public class TilesPlugin implements PlugIn {
    65  
    66      /**
    67       * Commons Logging instance.
    68       */
    69      protected static Log log = LogFactory.getLog(TilesPlugin.class);
    70  
    71      /**
    72       * Is the factory module aware?
    73       */
    74      protected boolean moduleAware = false;
    75  
    76      /**
    77       * Tiles util implementation classname. This property can be set
    78       * by user in the plugin declaration.
    79       */
    80      protected String tilesUtilImplClassname = null;
    81  
    82      /**
    83       * Associated definition factory.
    84       */
    85      protected DefinitionsFactory definitionFactory = null;
    86  
    87      /**
    88       * The plugin config object provided by the ActionServlet initializing
    89       * this plugin.
    90       */
    91      protected PlugInConfig currentPlugInConfigObject=null;
    92  
    93      /**
    94       * Get the module aware flag.
    95       * @return <code>true</code>: user wants a single factory instance,
    96       * <code>false:</code> user wants multiple factory instances (one per module with Struts)
    97       */
    98      public boolean isModuleAware() {
    99          return moduleAware;
    100     }
    101 
    102     /**
    103      * Set the module aware flag.
    104      * This flag is only meaningful if the property <code>tilesUtilImplClassname</code> is not
    105      * set.
    106      * @param moduleAware <code>true</code>: user wants a single factory instance,
    107      * <code>false:</code> user wants multiple factory instances (one per module with Struts)
    108      */
    109     public void setModuleAware(boolean moduleAware) {
    110         this.moduleAware = moduleAware;
    111     }
    112 
    113     /**
    114      * <p>Receive notification that the specified module is being
    115      * started up.</p>
    116      *
    117      * @param servlet ActionServlet that is managing all the modules
    118      *  in this web application.
    119      * @param moduleConfig ModuleConfig for the module with which
    120      *  this plugin is associated.
    121      *
    122      * @exception ServletException if this <code>PlugIn</code> cannot
    123      *  be successfully initialized.
    124      */
    125     public void init(ActionServlet servlet, ModuleConfig moduleConfig)
    126         throws ServletException {
    127 
    128         // Create factory config object
    129         DefinitionsFactoryConfig factoryConfig =
    130             readFactoryConfig(servlet, moduleConfig);
    131 
    132         // Set the module name in the config. This name will be used to compute
    133         // the name under which the factory is stored.
    134         factoryConfig.setFactoryName(moduleConfig.getPrefix());
    135 
    136         // Set RequestProcessor class
    137         this.initRequestProcessorClass(moduleConfig);
    138 
    139         this.initTilesUtil();
    140 
    141         this.initDefinitionsFactory(servlet.getServletContext(), moduleConfig, factoryConfig);
    142     }
    143 
    144     /**
    145      * Set TilesUtil implementation according to properties 'tilesUtilImplClassname'
    146      * and 'moduleAware'.  These properties are taken into account only once. A
    147      * side effect is that only the values set in the first initialized plugin are
    148      * effectively taken into account.
    149      * @throws ServletException
    150      */
    151     private void initTilesUtil() throws ServletException {
    152 
    153         if (TilesUtil.isTilesUtilImplSet()) {
    154             return;
    155         }
    156 
    157         // Check if user has specified a TilesUtil implementation classname or not.
    158         // If no implementation is specified, check if user has specified one
    159         // shared single factory for all module, or one factory for each module.
    160 
    161         if (this.getTilesUtilImplClassname() == null) {
    162 
    163             if (isModuleAware()) {
    164                 TilesUtil.setTilesUtil(new TilesUtilStrutsModulesImpl());
    165             } else {
    166                 TilesUtil.setTilesUtil(new TilesUtilStrutsImpl());
    167             }
    168 
    169         } else { // A classname is specified for the tilesUtilImp, use it.
    170             try {
    171                 TilesUtilStrutsImpl impl =
    172                     (TilesUtilStrutsImpl) RequestUtils
    173                         .applicationClass(getTilesUtilImplClassname())
    174                         .newInstance();
    175                 TilesUtil.setTilesUtil(impl);
    176 
    177             } catch (ClassCastException ex) {
    178                 throw new ServletException(
    179                     "Can't set TilesUtil implementation to '"
    180                         + getTilesUtilImplClassname()
    181                         + "'. TilesUtil implementation should be a subclass of '"
    182                         + TilesUtilStrutsImpl.class.getName()
    183                         + "'");
    184 
    185             } catch (Exception ex) {
    186                 throw new ServletException(
    187                     "Can't set TilesUtil implementation.",
    188                     ex);
    189             }
    190         }
    191 
    192     }
    193 
    194     /**
    195      * Initialize the DefinitionsFactory this module will use.
    196      * @param servletContext
    197      * @param moduleConfig
    198      * @param factoryConfig
    199      * @throws ServletException
    200      */
    201     private void initDefinitionsFactory(
    202         ServletContext servletContext,
    203         ModuleConfig moduleConfig,
    204         DefinitionsFactoryConfig factoryConfig)
    205         throws ServletException {
    206 
    207         // Check if a factory already exist for this module
    208         definitionFactory =
    209             ((TilesUtilStrutsImpl) TilesUtil.getTilesUtil()).getDefinitionsFactory(
    210                 servletContext,
    211                 moduleConfig);
    212 
    213         if (definitionFactory != null) {
    214             log.info(
    215                 "Factory already exists for module '"
    216                     + moduleConfig.getPrefix()
    217                     + "'. The factory found is from module '"
    218                     + definitionFactory.getConfig().getFactoryName()
    219                     + "'. No new creation.");
    220 
    221             return;
    222         }
    223 
    224         // Create configurable factory
    225         try {
    226             definitionFactory =
    227                 TilesUtil.createDefinitionsFactory(
    228                     servletContext,
    229                     factoryConfig);
    230 
    231         } catch (DefinitionsFactoryException ex) {
    232             log.error(
    233                 "Can't create Tiles definition factory for module '"
    234                     + moduleConfig.getPrefix()
    235                     + "'.");
    236 
    237             throw new ServletException(ex);
    238         }
    239 
    240         log.info(
    241             "Tiles definition factory loaded for module '"
    242                 + moduleConfig.getPrefix()
    243                 + "'.");
    244     }
    245 
    246     /**
    247      * End plugin.
    248      */
    249     public void destroy() {
    250         definitionFactory.destroy();
    251         definitionFactory = null;
    252     }
    253 
    254     /**
    255      * Create FactoryConfig and initialize it from web.xml and struts-config.xml.
    256      *
    257      * @param servlet ActionServlet that is managing all the modules
    258      *  in this web application.
    259      * @param config ModuleConfig for the module with which
    260      *  this plugin is associated.
    261      * @exception ServletException if this <code>PlugIn</code> cannot
    262      *  be successfully initialized.
    263      */
    264     protected DefinitionsFactoryConfig readFactoryConfig(
    265         ActionServlet servlet,
    266         ModuleConfig config)
    267         throws ServletException {
    268 
    269         // Create tiles definitions config object
    270         DefinitionsFactoryConfig factoryConfig = new DefinitionsFactoryConfig();
    271         // Get init parameters from web.xml files
    272         try {
    273             DefinitionsUtil.populateDefinitionsFactoryConfig(
    274                 factoryConfig,
    275                 servlet.getServletConfig());
    276 
    277         } catch (Exception ex) {
    278             if (log.isDebugEnabled()){
    279                 log.debug("", ex);
    280             }
    281             ex.printStackTrace();
    282             throw new UnavailableException(
    283                 "Can't populate DefinitionsFactoryConfig class from 'web.xml': "
    284                     + ex.getMessage());
    285         }
    286 
    287         // Get init parameters from struts-config.xml
    288         try {
    289             Map strutsProperties = findStrutsPlugInConfigProperties(servlet, config);
    290             factoryConfig.populate(strutsProperties);
    291 
    292         } catch (Exception ex) {
    293             if (log.isDebugEnabled()) {
    294                 log.debug("", ex);
    295             }
    296 
    297             throw new UnavailableException(
    298                 "Can't populate DefinitionsFactoryConfig class from '"
    299                     + config.getPrefix()
    300                     + "/struts-config.xml':"
    301                     + ex.getMessage());
    302         }
    303 
    304         return factoryConfig;
    305     }
    306 
    307     /**
    308      * Find original properties set in the Struts PlugInConfig object.
    309      * First, we need to find the index of this plugin. Then we retrieve the array of configs
    310      * and then the object for this plugin.
    311      * @param servlet ActionServlet that is managing all the modules
    312      *  in this web application.
    313      * @param config ModuleConfig for the module with which
    314      *  this plug in is associated.
    315      *
    316      * @exception ServletException if this <code>PlugIn</code> cannot
    317      *  be successfully initialized.
    318      */
    319     protected Map findStrutsPlugInConfigProperties(
    320         ActionServlet servlet,
    321         ModuleConfig config)
    322         throws ServletException {
    323 
    324         return currentPlugInConfigObject.getProperties();
    325     }
    326 
    327     /**
    328      * Set RequestProcessor to appropriate Tiles {@link RequestProcessor}.
    329      * First, check if a RequestProcessor is specified. If yes, check if it extends
    330      * the appropriate {@link TilesRequestProcessor} class. If not, set processor class to
    331      * TilesRequestProcessor.
    332      *
    333      * @param config ModuleConfig for the module with which
    334      *  this plugin is associated.
    335      * @throws ServletException On errors.
    336      */
    337     protected void initRequestProcessorClass(ModuleConfig config)
    338         throws ServletException {
    339 
    340         String tilesProcessorClassname = TilesRequestProcessor.class.getName();
    341         ControllerConfig ctrlConfig = config.getControllerConfig();
    342         String configProcessorClassname = ctrlConfig.getProcessorClass();
    343 
    344         // Check if specified classname exist
    345         Class configProcessorClass;
    346         try {
    347             configProcessorClass =
    348                 RequestUtils.applicationClass(configProcessorClassname);
    349 
    350         } catch (ClassNotFoundException ex) {
    351             log.fatal(
    352                 "Can't set TilesRequestProcessor: bad class name '"
    353                     + configProcessorClassname
    354                     + "'.");
    355             throw new ServletException(ex);
    356         }
    357 
    358         // Check to see if request processor uses struts-chain.  If so,
    359         // no need to replace the request processor.
    360         if (ComposableRequestProcessor.class.isAssignableFrom(configProcessorClass)) {
    361             return;
    362         }
    363 
    364         // Check if it is the default request processor or Tiles one.
    365         // If true, replace by Tiles' one.
    366         if (configProcessorClassname.equals(RequestProcessor.class.getName())
    367             || configProcessorClassname.endsWith(tilesProcessorClassname)) {
    368 
    369             ctrlConfig.setProcessorClass(tilesProcessorClassname);
    370             return;
    371         }
    372 
    373         // Check if specified request processor is compatible with Tiles.
    374         Class tilesProcessorClass = TilesRequestProcessor.class;
    375         if (!tilesProcessorClass.isAssignableFrom(configProcessorClass)) {
    376             // Not compatible
    377             String msg =
    378                 "TilesPlugin : Specified RequestProcessor not compatible with TilesRequestProcessor";
    379             if (log.isFatalEnabled()) {
    380                 log.fatal(msg);
    381             }
    382             throw new ServletException(msg);
    383         }
    384     }
    385 
    386     /**
    387      * Set Tiles util implemention classname.
    388      * If this property is set, the flag <code>moduleAware</code> will not be used anymore.
    389      * @param tilesUtilImplClassname Classname.
    390      */
    391     public void setTilesUtilImplClassname(String tilesUtilImplClassname) {
    392         this.tilesUtilImplClassname = tilesUtilImplClassname;
    393     }
    394 
    395     /**
    396      * Get Tiles util implemention classname.
    397      * @return The classname or <code>null</code> if none is set.
    398      */
    399     public String getTilesUtilImplClassname() {
    400         return tilesUtilImplClassname;
    401     }
    402 
    403     /**
    404      * Method used by the ActionServlet initializing this plugin.
    405      * Set the plugin config object read from module config.
    406      * @param plugInConfigObject PlugInConfig.
    407      */
    408     public void setCurrentPlugInConfigObject(PlugInConfig plugInConfigObject) {
    409         this.currentPlugInConfigObject = plugInConfigObject;
    410     }
    411 
    412 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
