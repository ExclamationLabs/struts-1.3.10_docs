
    1   /*
    2    * $Id: TestTilesPlugin.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import org.apache.struts.config.ModuleConfig;
    25  import org.apache.struts.config.ModuleConfigFactory;
    26  import org.apache.struts.config.PlugInConfig;
    27  import org.apache.struts.mock.MockActionServlet;
    28  import org.apache.struts.mock.TestMockBase;
    29  import org.apache.struts.Globals;
    30  import org.apache.struts.tiles.xmlDefinition.I18nFactorySet;
    31  import org.apache.struts.util.RequestUtils;
    32  import org.apache.struts.action.PlugIn;
    33  import org.apache.commons.beanutils.BeanUtils;
    34  import junit.framework.Test;
    35  import junit.framework.TestSuite;
    36  
    37  import javax.servlet.ServletException;
    38  import java.util.Locale;
    39  import java.util.Map;
    40  import java.util.HashMap;
    41  
    42  public class TestTilesPlugin extends TestMockBase {
    43  
    44  
    45    protected ModuleConfig module1;
    46    protected ModuleConfig module2;
    47    protected MockActionServlet actionServlet;
    48  
    49      // ----------------------------------------------------------------- Basics
    50  
    51  
    52      public TestTilesPlugin(String name) {
    53          super(name);
    54      }
    55  
    56  
    57      public static void main(String args[]) {
    58          junit.awtui.TestRunner.main
    59              (new String[] { TestTilesPlugin.class.getName() } );
    60      }
    61  
    62  
    63      public static Test suite() {
    64          return (new TestSuite(TestTilesPlugin.class));
    65      }
    66  
    67  
    68      // ----------------------------------------------------- Instance Variables
    69  
    70  
    71  
    72      // ----------------------------------------------------- Setup and Teardown
    73  
    74  
    75      public void setUp()
    76      {
    77  
    78      super.setUp();
    79      TilesUtil.testReset();
    80      actionServlet = new MockActionServlet(context, config);
    81      }
    82  
    83  
    84      public void tearDown() {
    85  
    86          super.tearDown();
    87  
    88      }
    89  
    90  
    91      // ------------------------------------------------------- Individual Tests
    92  
    93  
    94      /**
    95       * Create a module configuration
    96       * @param moduleName
    97       */
    98      public ModuleConfig createModuleConfig(
    99          String moduleName,
    100         String configFileName,
    101         boolean moduleAware) {
    102 
    103         ModuleConfig moduleConfig =
    104             ModuleConfigFactory.createFactory().createModuleConfig(moduleName);
    105 
    106         context.setAttribute(Globals.MODULE_KEY + moduleName, moduleConfig);
    107 
    108         // Set tiles plugin
    109         PlugInConfig pluginConfig = new PlugInConfig();
    110         pluginConfig.setClassName("org.apache.struts.tiles.TilesPlugin");
    111 
    112         pluginConfig.addProperty(
    113             "moduleAware",
    114             (moduleAware == true ? "true" : "false"));
    115 
    116         pluginConfig.addProperty(
    117             "definitions-config",
    118             "/org/apache/struts/tiles/config/" + configFileName);
    119 
    120         moduleConfig.addPlugInConfig(pluginConfig);
    121         return moduleConfig;
    122     }
    123 
    124     /**
    125      * Fake call to init module plugins
    126      * @param moduleConfig
    127      */
    128   public void initModulePlugIns( ModuleConfig moduleConfig)
    129   {
    130   PlugInConfig plugInConfigs[] = moduleConfig.findPlugInConfigs();
    131   PlugIn plugIns[] = new PlugIn[plugInConfigs.length];
    132 
    133   context.setAttribute(Globals.PLUG_INS_KEY + moduleConfig.getPrefix(), plugIns);
    134   for (int i = 0; i < plugIns.length; i++) {
    135       try {
    136           plugIns[i] =
    137               (PlugIn) RequestUtils.applicationInstance(plugInConfigs[i].getClassName());
    138           BeanUtils.populate(plugIns[i], plugInConfigs[i].getProperties());
    139             // Pass the current plugIn config object to the PlugIn.
    140             // The property is set only if the plugin declares it.
    141             // This plugin config object is needed by Tiles
    142           BeanUtils.copyProperty( plugIns[i], "currentPlugInConfigObject", plugInConfigs[i]);
    143           plugIns[i].init(actionServlet, moduleConfig);
    144       } catch (ServletException e) {
    145           // Lets propagate
    146           e.printStackTrace();
    147           //throw e;
    148       } catch (Exception e) {
    149           e.printStackTrace();
    150           //throw e;
    151       }
    152   }
    153   }
    154 
    155     // ---------------------------------------------------------- absoluteURL()
    156 
    157 
    158     /**
    159      * Test multi factory creation when moduleAware=true.
    160      */
    161     public void testMultiFactory() {
    162         // init TilesPlugin
    163         module1 = createModuleConfig("/module1", "tiles-defs.xml", true);
    164         module2 = createModuleConfig("/module2", "tiles-defs.xml", true);
    165         initModulePlugIns(module1);
    166         initModulePlugIns(module2);
    167 
    168         // mock request context
    169         request.setAttribute(Globals.MODULE_KEY, module1);
    170         request.setPathElements("/myapp", "/module1/foo.do", null, null);
    171         // Retrieve factory for module1
    172         DefinitionsFactory factory1 =
    173             TilesUtil.getDefinitionsFactory(request, context);
    174 
    175         assertNotNull("factory found", factory1);
    176         assertEquals(
    177             "factory name",
    178             "/module1",
    179             factory1.getConfig().getFactoryName());
    180 
    181         // mock request context
    182         request.setAttribute(Globals.MODULE_KEY, module2);
    183         request.setPathElements("/myapp", "/module2/foo.do", null, null);
    184         // Retrieve factory for module2
    185         DefinitionsFactory factory2 =
    186             TilesUtil.getDefinitionsFactory(request, context);
    187         assertNotNull("factory found", factory2);
    188         assertEquals(
    189             "factory name",
    190             "/module2",
    191             factory2.getConfig().getFactoryName());
    192 
    193         // Check that factory are different
    194         assertNotSame("Factory from different modules", factory1, factory2);
    195     }
    196 
    197     /**
    198      * Test single factory creation when moduleAware=false.
    199      */
    200   public void testSingleSharedFactory()
    201   {
    202     // init TilesPlugin
    203   module1 = createModuleConfig( "/module1", "tiles-defs.xml", false );
    204   module2 = createModuleConfig( "/module2", "tiles-defs.xml", false );
    205   initModulePlugIns(module1);
    206   initModulePlugIns(module2);
    207 
    208     // mock request context
    209   request.setAttribute(Globals.MODULE_KEY, module1);
    210   request.setPathElements("/myapp", "/module1/foo.do", null, null);
    211     // Retrieve factory for module1
    212   DefinitionsFactory factory1 = TilesUtil.getDefinitionsFactory( request, context);
    213   assertNotNull( "factory found", factory1);
    214   assertEquals( "factory name", "/module1", factory1.getConfig().getFactoryName() );
    215 
    216     // mock request context
    217   request.setAttribute(Globals.MODULE_KEY, module2);
    218   request.setPathElements("/myapp", "/module2/foo.do", null, null);
    219     // Retrieve factory for module2
    220   DefinitionsFactory factory2 = TilesUtil.getDefinitionsFactory( request, context);
    221   assertNotNull( "factory found", factory2);
    222   assertEquals( "factory name", "/module1", factory2.getConfig().getFactoryName() );
    223 
    224     // Check that factory are different
    225   assertEquals("Same factory", factory1, factory2);
    226   }
    227 
    228   /**
    229    * Test I18nFactorySet.
    230    */
    231   public void testI18FactorySet_A() {
    232 
    233      Locale locale = null;
    234      ComponentDefinition definition = null;
    235      org.apache.struts.tiles.xmlDefinition.DefinitionsFactory factory = null;
    236 
    237      Map properties = new HashMap();
    238 
    239      // Set the file name
    240      properties.put(I18nFactorySet.DEFINITIONS_CONFIG_PARAMETER_NAME,
    241                     "config/I18nFactorySet-A.xml");
    242 
    243      try {
    244          CustomI18nFactorySet i18nFactorySet = new CustomI18nFactorySet(context, properties);
    245          String defName = "A-DEFAULT";
    246 
    247          // Default Locale
    248          locale = new Locale("", "", "");
    249          factory = i18nFactorySet.createFactory(locale , request, context);
    250          assertNotNull("DefinitionsFactory is nullfor locale='" + print(locale) + "'", factory);
    251          definition = factory.getDefinition(defName, request, context);
    252          assertNotNull("Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    253          assertEquals("Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    254 
    255          // Variant Only
    256          locale = new Locale("", "", "XX");
    257          factory = i18nFactorySet.createFactory(locale , request, context);
    258          assertNotNull("DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    259          definition = factory.getDefinition(defName, request, context);
    260          assertNotNull("Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    261          assertEquals("Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    262 
    263          // No Language, Country & Variant Locale
    264          locale = new Locale("", "US", "XX");
    265          factory = i18nFactorySet.createFactory(locale , request, context);
    266          assertNotNull("DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    267          definition = factory.getDefinition(defName, request, context);
    268          assertNotNull("Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    269          assertEquals("Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    270 
    271          // Language & Country
    272          locale = new Locale("en", "US");
    273          factory = i18nFactorySet.createFactory(locale , request, context);
    274          assertNotNull("DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    275          definition = factory.getDefinition(defName, request, context);
    276          assertNotNull("Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    277          assertEquals("Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    278 
    279      } catch(Exception ex) {
    280          fail(ex.toString());
    281      }
    282   }
    283 
    284 
    285   /**
    286    * Test I18nFactorySet.
    287    */
    288   public void testI18FactorySet_B() {
    289 
    290      Locale locale = null;
    291      ComponentDefinition definition = null;
    292      org.apache.struts.tiles.xmlDefinition.DefinitionsFactory factory = null;
    293 
    294      Map properties = new HashMap();
    295 
    296      // Set the file name
    297      properties.put(I18nFactorySet.DEFINITIONS_CONFIG_PARAMETER_NAME,
    298                     "config/I18nFactorySet-B.xml");
    299 
    300      try {
    301 
    302          CustomI18nFactorySet i18nFactorySet = new CustomI18nFactorySet(context, properties);
    303          String defName = null;
    304 
    305          // Default Locale
    306          locale = new Locale("", "", "");
    307          factory = i18nFactorySet.createFactory(locale , request, context);
    308          assertNotNull("1. DefinitionsFactory is nullfor locale='" + print(locale) + "'", factory);
    309          defName = "B-DEFAULT";
    310          definition = factory.getDefinition(defName, request, context);
    311          assertNotNull("2. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    312          assertEquals("3. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    313 
    314          // Variant Only
    315          locale = new Locale("", "", "XX");
    316          factory = i18nFactorySet.createFactory(locale , request, context);
    317          assertNotNull("4. DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    318          defName = "B___XX";
    319          definition = factory.getDefinition(defName, request, context);
    320          assertNotNull("5. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    321          assertEquals("6. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    322          defName = "B-DEFAULT";
    323          definition = factory.getDefinition(defName, request, context);
    324          assertNotNull("7. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    325          assertEquals("8. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    326 
    327          // No Language, Country & Unknown Variant
    328          locale = new Locale("", "US", "XX");
    329          factory = i18nFactorySet.createFactory(locale , request, context);
    330          assertNotNull("9. DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    331          defName = "B__US";
    332          definition = factory.getDefinition(defName, request, context);
    333          assertNotNull("10. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    334          assertEquals("11. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    335 
    336          // Language & Country
    337          locale = new Locale("en", "US");
    338          factory = i18nFactorySet.createFactory(locale , request, context);
    339          assertNotNull("12. DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    340          defName = "B_en_US";
    341          definition = factory.getDefinition(defName, request, context);
    342          assertNotNull("13. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    343          assertEquals("14. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    344 
    345          // Language, Country & Unknown Variant
    346          locale = new Locale("en", "GB", "XX");
    347          factory = i18nFactorySet.createFactory(locale , request, context);
    348          assertNotNull("15. DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    349          defName = "B_en_GB";
    350          definition = factory.getDefinition(defName, request, context);
    351          assertNotNull("16. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    352          assertEquals("17. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    353 
    354          // Language, Unknown Country & Unknown Variant
    355          locale = new Locale("en", "FR", "XX");
    356          factory = i18nFactorySet.createFactory(locale , request, context);
    357          assertNotNull("18. DefinitionsFactory is null for locale='" + print(locale) + "'", factory);
    358          defName = "B_en";
    359          definition = factory.getDefinition(defName, request, context);
    360          assertNotNull("19. Definition '" + defName + "' Not Found for locale='" + print(locale) + "'", definition);
    361          assertEquals("20. Definition '" + defName + "' for locale='" + print(locale) + "'", defName, definition.getName());
    362 
    363      } catch(Exception ex) {
    364          fail(ex.toString());
    365      }
    366 
    367   }
    368 
    369   /**
    370    * String representation of a Locale. A bug in the
    371    * Locale.toString() method results in Locales with
    372    * just a variant being incorrectly displayed.
    373    */
    374   private String print(Locale locale) {
    375 
    376       return locale.getLanguage() + "_" +
    377                 locale.getCountry() + "_" +
    378                 locale.getVariant();
    379   }
    380 
    381 
    382 
    383 }
    384 

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
