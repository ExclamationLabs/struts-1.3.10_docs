
    1   /*
    2    * $Id: TestForwardConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import junit.framework.Test;
    24  import junit.framework.TestCase;
    25  import junit.framework.TestSuite;
    26  
    27  /**
    28   * <p>Unit tests for ForwardConfig.  Currently contains tests for methods
    29   * supporting configuration inheritance.</p>
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-05-21 19:06:53 -0400 (Sat, 21 May 2005)
    32   *          $
    33   */
    34  public class TestForwardConfig extends TestCase {
    35      // ----------------------------------------------------- Instance Variables
    36  
    37      /**
    38       * The ModuleConfig we'll use.
    39       */
    40      protected ModuleConfig moduleConfig = null;
    41  
    42      /**
    43       * The common base we'll use.
    44       */
    45      protected ForwardConfig baseConfig = null;
    46  
    47      /**
    48       * The common subForward we'll use.
    49       */
    50      protected ForwardConfig subConfig = null;
    51  
    52      /**
    53       * A ForwardConfig we'll use to test cases where a ForwardConfig declared
    54       * for an action extends a ForwardConfig declared globally, with both
    55       * ForwardConfigs using the same name.
    56       */
    57      protected ForwardConfig actionBaseConfig = null;
    58  
    59      /**
    60       * An action mapping we'll use within tests.
    61       */
    62      protected ActionConfig actionConfig = null;
    63  
    64      // ----------------------------------------------------------- Constructors
    65  
    66      /**
    67       * Construct a new instance of this test case.
    68       *
    69       * @param name Name of the test case
    70       */
    71      public TestForwardConfig(String name) {
    72          super(name);
    73      }
    74  
    75      // --------------------------------------------------------- Public Methods
    76  
    77      /**
    78       * Set up instance variables required by this test case.
    79       */
    80      public void setUp() {
    81          ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    82  
    83          moduleConfig = factoryObject.createModuleConfig("");
    84  
    85          // Setup the base and sub forwards, with sub extending base
    86          baseConfig = new ForwardConfig();
    87          baseConfig.setName("baseConfig");
    88          baseConfig.setPath("/somePage.jsp");
    89  
    90          subConfig = new ForwardConfig();
    91          subConfig.setName("subConfig");
    92          subConfig.setExtends("baseConfig");
    93          subConfig.setRedirect(true);
    94  
    95          actionBaseConfig = new ForwardConfig();
    96          actionBaseConfig.setName("baseConfig");
    97          actionBaseConfig.setExtends("baseConfig");
    98          actionBaseConfig.setModule("/other");
    99  
    100         // Setup the default action config
    101         actionConfig = new ActionConfig();
    102         actionConfig.setPath("/index");
    103         moduleConfig.addActionConfig(actionConfig);
    104 
    105         // No forward configs are registered to either module or action configs.
    106         // Each test will determine where it needs these configs, if at all.
    107     }
    108 
    109     /**
    110      * Return the tests included in this test suite.
    111      */
    112     public static Test suite() {
    113         return (new TestSuite(TestForwardConfig.class));
    114     }
    115 
    116     /**
    117      * Tear down instance variables required by this test case.
    118      */
    119     public void tearDown() {
    120         moduleConfig = null;
    121         baseConfig = null;
    122     }
    123 
    124     // ------------------------------------------------------- Individual Tests
    125 
    126     /**
    127      * Make sure checkCircularInheritance() works as expected where there is
    128      * no inheritance set up.
    129      */
    130     public void testCheckCircularInheritanceNoExtends() {
    131         moduleConfig.addForwardConfig(baseConfig);
    132 
    133         boolean result =
    134             baseConfig.checkCircularInheritance(moduleConfig, null);
    135 
    136         assertTrue("Incorrect result", !result);
    137     }
    138 
    139     /**
    140      * Test checkCircularInheritance() for when there is no circular
    141      * inheritance.
    142      */
    143     public void testCheckCircularInheritanceNoConflicts() {
    144         moduleConfig.addForwardConfig(baseConfig);
    145         moduleConfig.addForwardConfig(subConfig);
    146 
    147         boolean result = subConfig.checkCircularInheritance(moduleConfig, null);
    148 
    149         assertTrue("Incorrect result", !result);
    150     }
    151 
    152     /**
    153      * Test checkCircularInheritance() for circular inheritance between global
    154      * forwards.
    155      */
    156     public void testCheckCircularInheritanceBasicGlobal() {
    157         moduleConfig.addForwardConfig(subConfig);
    158         moduleConfig.addForwardConfig(baseConfig);
    159 
    160         // set the baseConfig to extend subConfig
    161         baseConfig.setExtends("subConfig");
    162 
    163         boolean result = subConfig.checkCircularInheritance(moduleConfig, null);
    164 
    165         assertTrue("Circular inheritance not detected.", result);
    166     }
    167 
    168     /**
    169      * Test checkCircularInheritance() for circular inheritance between global
    170      * forwards.
    171      */
    172     public void testCheckCircularInheritanceGlobal2Levels() {
    173         moduleConfig.addForwardConfig(baseConfig);
    174         moduleConfig.addForwardConfig(subConfig);
    175 
    176         ForwardConfig grand = new ForwardConfig();
    177 
    178         grand.setName("grandConfig");
    179         grand.setExtends("subConfig");
    180         moduleConfig.addForwardConfig(grand);
    181 
    182         // set the baseConfig to extend grandConfig
    183         baseConfig.setExtends("grandConfig");
    184 
    185         boolean result = grand.checkCircularInheritance(moduleConfig, null);
    186 
    187         assertTrue("Circular inheritance not detected.", result);
    188     }
    189 
    190     /**
    191      * Test checkCircularInheritance() for circular inheritance between
    192      * forwards in an action.
    193      */
    194     public void testCheckCircularInheritanceActionForwardsNoConflict() {
    195         actionConfig.addForwardConfig(baseConfig);
    196         actionConfig.addForwardConfig(subConfig);
    197 
    198         boolean result =
    199             subConfig.checkCircularInheritance(moduleConfig, actionConfig);
    200 
    201         assertTrue("Incorrect result", !result);
    202     }
    203 
    204     /**
    205      * Test checkCircularInheritance() for circular inheritance between
    206      * forwards in an action.
    207      */
    208     public void testCheckCircularInheritanceActionForwardsBasic() {
    209         actionConfig.addForwardConfig(baseConfig);
    210         actionConfig.addForwardConfig(subConfig);
    211 
    212         // set base to extend sub
    213         baseConfig.setExtends("subConfig");
    214 
    215         boolean result =
    216             subConfig.checkCircularInheritance(moduleConfig, actionConfig);
    217 
    218         assertTrue("Circular inheritance not detected.", result);
    219     }
    220 
    221     /**
    222      * Test checkCircularInheritance() for circular inheritance between a
    223      * forward declared in an action and a global forward.
    224      */
    225     public void testCheckCircularInheritanceActionForwardExtendGlobal() {
    226         actionConfig.addForwardConfig(subConfig);
    227         moduleConfig.addForwardConfig(baseConfig);
    228 
    229         boolean result =
    230             subConfig.checkCircularInheritance(moduleConfig, actionConfig);
    231 
    232         assertTrue("Incorrect result", !result);
    233     }
    234 
    235     /**
    236      * Test checkCircularInheritance() for circular inheritance between a
    237      * forward declared in an action and a global forward and both forwards
    238      * have the same name.
    239      */
    240     public void testCheckCircularInheritanceActionForwardExtendGlobalSameName() {
    241         moduleConfig.addForwardConfig(baseConfig);
    242         actionConfig.addForwardConfig(actionBaseConfig);
    243 
    244         boolean result =
    245             actionBaseConfig.checkCircularInheritance(moduleConfig, actionConfig);
    246 
    247         assertTrue("Incorrect result", !result);
    248     }
    249 
    250     /**
    251      * Make sure processExtends() throws an error when the config is already
    252      * configured.
    253      */
    254     public void testProcessExtendsConfigured()
    255         throws Exception {
    256         baseConfig.configured = true;
    257         moduleConfig.addForwardConfig(baseConfig);
    258 
    259         try {
    260             baseConfig.processExtends(moduleConfig, null);
    261             fail(
    262                 "processExtends should not succeed when object is already configured");
    263         } catch (IllegalStateException e) {
    264             // success
    265         }
    266     }
    267 
    268     /**
    269      * Test processExtends() when nothing is extended.
    270      */
    271     public void testProcessExtendsNoExtension()
    272         throws Exception {
    273         String path = baseConfig.getPath();
    274         String module = baseConfig.getModule();
    275         String name = baseConfig.getName();
    276         String inherit = baseConfig.getExtends();
    277         boolean redirect = baseConfig.getRedirect();
    278 
    279         moduleConfig.addForwardConfig(baseConfig);
    280         baseConfig.processExtends(moduleConfig, null);
    281 
    282         assertEquals("Path shouldn't have changed", path, baseConfig.getPath());
    283         assertEquals("Module shouldn't have changed", module,
    284             baseConfig.getModule());
    285         assertEquals("Name shouldn't have changed", name, baseConfig.getName());
    286         assertEquals("Extends shouldn't have changed", inherit,
    287             baseConfig.getExtends());
    288         assertEquals("Redirect shouldn't have changed", redirect,
    289             baseConfig.getRedirect());
    290     }
    291 
    292     /**
    293      * Test processExtends() with a basic extension.
    294      */
    295     public void testProcessExtendsBasicExtension()
    296         throws Exception {
    297         String baseCount = "10";
    298 
    299         baseConfig.setProperty("count", baseCount);
    300 
    301         String baseLabel = "label a";
    302 
    303         baseConfig.setProperty("label", baseLabel);
    304 
    305         String path = baseConfig.getPath();
    306         String module = baseConfig.getModule();
    307 
    308         String inherit = subConfig.getExtends();
    309         String name = subConfig.getName();
    310         boolean redirect = subConfig.getRedirect();
    311 
    312         String subLabel = "label b";
    313 
    314         subConfig.setProperty("label", subLabel);
    315 
    316         moduleConfig.addForwardConfig(baseConfig);
    317         moduleConfig.addForwardConfig(subConfig);
    318         subConfig.processExtends(moduleConfig, null);
    319 
    320         assertEquals("Path wasn't inherited", path, subConfig.getPath());
    321         assertEquals("Module wasn't inherited", module, subConfig.getModule());
    322         assertEquals("Name shouldn't have changed", name, subConfig.getName());
    323         assertEquals("Extends shouldn't have changed", inherit,
    324             subConfig.getExtends());
    325         assertEquals("Redirect shouldn't have changed", redirect,
    326             subConfig.getRedirect());
    327         assertEquals("Arbitrary config property was not inherited", baseCount,
    328             subConfig.getProperty("count"));
    329         assertEquals("Overridden config property was not retained", subLabel,
    330             subConfig.getProperty("label"));
    331     }
    332 
    333     /**
    334      * Test processExtends() with a basic extension between an action config
    335      * and a global config.
    336      */
    337     public void testProcessExtendsBasicGlobalExtension()
    338         throws Exception {
    339         String path = baseConfig.getPath();
    340         String module = baseConfig.getModule();
    341 
    342         boolean redirect = subConfig.getRedirect();
    343         String inherit = subConfig.getExtends();
    344         String name = subConfig.getName();
    345 
    346         moduleConfig.addForwardConfig(baseConfig);
    347         actionConfig.addForwardConfig(subConfig);
    348         subConfig.processExtends(moduleConfig, actionConfig);
    349 
    350         assertEquals("Path wasn't inherited", path, subConfig.getPath());
    351         assertEquals("Module wasn't inherited", module, subConfig.getModule());
    352         assertEquals("Name shouldn't have changed", name, subConfig.getName());
    353         assertEquals("Extends shouldn't have changed", inherit,
    354             subConfig.getExtends());
    355         assertEquals("Redirect shouldn't have changed", redirect,
    356             subConfig.getRedirect());
    357     }
    358 
    359     /**
    360      * Test processExtends() with an incorrect setup where a global config
    361      * attempts to extend an action config.
    362      */
    363     public void testProcessExtendsGlobalExtendingAction()
    364         throws Exception {
    365         moduleConfig.addForwardConfig(subConfig);
    366         actionConfig.addForwardConfig(baseConfig);
    367 
    368         try {
    369             subConfig.processExtends(moduleConfig, actionConfig);
    370             fail(
    371                 "Should not find config from actionConfig when *this* is global");
    372         } catch (NullPointerException npe) {
    373             // succeed
    374         }
    375     }
    376 
    377     /**
    378      * Test processExtends() with an action config that extends a global
    379      * config with the same name.
    380      */
    381     public void testProcessExtendsSameNames()
    382         throws Exception {
    383         String path = baseConfig.getPath();
    384         boolean redirect = baseConfig.getRedirect();
    385 
    386         String module = actionBaseConfig.getModule();
    387         String inherit = actionBaseConfig.getExtends();
    388         String name = actionBaseConfig.getName();
    389 
    390         moduleConfig.addForwardConfig(baseConfig);
    391         actionConfig.addForwardConfig(actionBaseConfig);
    392 
    393         actionBaseConfig.processExtends(moduleConfig, actionConfig);
    394 
    395         assertEquals("Path wasn't inherited", path, actionBaseConfig.getPath());
    396         assertEquals("Module shouldn't have changed", module,
    397             actionBaseConfig.getModule());
    398         assertEquals("Name shouldn't have changed", name,
    399             actionBaseConfig.getName());
    400         assertEquals("Extends shouldn't have changed", inherit,
    401             actionBaseConfig.getExtends());
    402         assertEquals("Redirect shouldn't have changed", redirect,
    403             actionBaseConfig.getRedirect());
    404     }
    405 
    406     /**
    407      * Test processExtends() where an action ForwardConfig extends another
    408      * ForwardConfig, which in turn extends a global ForwardConfig with the
    409      * same name.
    410      */
    411     public void testProcessExtendsActionExtendsActionExtendsGlobalWithSameName()
    412         throws Exception {
    413         String path = baseConfig.getPath();
    414 
    415         String module = actionBaseConfig.getModule();
    416 
    417         boolean redirect = subConfig.getRedirect();
    418         String inherit = subConfig.getExtends();
    419         String name = subConfig.getName();
    420 
    421         moduleConfig.addForwardConfig(baseConfig);
    422         actionConfig.addForwardConfig(actionBaseConfig);
    423         actionConfig.addForwardConfig(subConfig);
    424 
    425         subConfig.processExtends(moduleConfig, actionConfig);
    426 
    427         assertTrue("baseConfig's processExtends() should've been called",
    428             baseConfig.extensionProcessed);
    429         assertTrue("actionBaseConfig's processExtends() should've been called",
    430             actionBaseConfig.extensionProcessed);
    431 
    432         assertEquals("Path wasn't inherited", path, subConfig.getPath());
    433         assertEquals("Module wasn't inherited", module, subConfig.getModule());
    434         assertEquals("Name shouldn't have changed", name, subConfig.getName());
    435         assertEquals("Extends shouldn't have changed", inherit,
    436             subConfig.getExtends());
    437         assertEquals("Redirect shouldn't have changed", redirect,
    438             subConfig.getRedirect());
    439     }
    440 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
