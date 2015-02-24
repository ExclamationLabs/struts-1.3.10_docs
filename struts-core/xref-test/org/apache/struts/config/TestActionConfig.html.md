
    1   /*
    2    * $Id: TestActionConfig.java 480593 2006-11-29 15:17:52Z niallp $
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
    27  import java.lang.reflect.InvocationTargetException;
    28  
    29  /**
    30   * Unit tests for the <code>org.apache.struts.config.ActionConfig</code>
    31   * class.  Currently only contains code to test the methods that support
    32   * configuration inheritance.
    33   *
    34   * @version $Rev: 480593 $ $Date: 2005-05-25 19:35:00 -0400 (Wed, 25 May 2005)
    35   *          $
    36   */
    37  public class TestActionConfig extends TestCase {
    38      // ----------------------------------------------------- Instance Variables
    39  
    40      /**
    41       * The ModuleConfig we'll use.
    42       */
    43      protected ModuleConfig config = null;
    44  
    45      /**
    46       * The common base we'll use.
    47       */
    48      protected ActionConfig baseConfig = null;
    49  
    50      // ----------------------------------------------------------- Constructors
    51  
    52      /**
    53       * Construct a new instance of this test case.
    54       *
    55       * @param name Name of the test case
    56       */
    57      public TestActionConfig(String name) {
    58          super(name);
    59      }
    60  
    61      // --------------------------------------------------------- Public Methods
    62  
    63      /**
    64       * Set up instance variables required by this test case.
    65       */
    66      public void setUp() {
    67          ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    68  
    69          config = factoryObject.createModuleConfig("");
    70  
    71          // setup the base form
    72          baseConfig = new ActionConfig();
    73          baseConfig.setPath("/base");
    74          baseConfig.setType("org.apache.struts.actions.DummyAction");
    75  
    76          // set up success and failure forward
    77          ForwardConfig forward =
    78              new ForwardConfig("success", "/success.jsp", false);
    79  
    80          baseConfig.addForwardConfig(forward);
    81  
    82          forward = new ForwardConfig("failure", "/failure.jsp", false);
    83          forward.setProperty("forwardCount", "10");
    84          baseConfig.addForwardConfig(forward);
    85  
    86          // setup an exception handler
    87          ExceptionConfig exceptionConfig = new ExceptionConfig();
    88  
    89          exceptionConfig.setType("java.sql.SQLException");
    90          exceptionConfig.setKey("msg.exception.sql");
    91          exceptionConfig.setProperty("exceptionCount", "10");
    92          baseConfig.addExceptionConfig(exceptionConfig);
    93  
    94          // set some arbitrary properties
    95          baseConfig.setProperty("label", "base");
    96          baseConfig.setProperty("version", "1a");
    97  
    98          // register it to our config
    99          config.addActionConfig(baseConfig);
    100     }
    101 
    102     /**
    103      * Return the tests included in this test suite.
    104      */
    105     public static Test suite() {
    106         return (new TestSuite(TestActionConfig.class));
    107     }
    108 
    109     /**
    110      * Tear down instance variables required by this test case.
    111      */
    112     public void tearDown() {
    113         config = null;
    114         baseConfig = null;
    115     }
    116 
    117     // ------------------------------------------------------- Individual Tests
    118 
    119     /**
    120      * Basic check that shouldn't detect circular inheritance.
    121      */
    122     public void testCheckCircularInheritance() {
    123         ActionConfig child = new ActionConfig();
    124 
    125         child.setPath("/child");
    126         child.setExtends("/base");
    127 
    128         ActionConfig grandChild = new ActionConfig();
    129 
    130         grandChild.setPath("/grandChild");
    131         grandChild.setExtends("/child");
    132 
    133         config.addActionConfig(child);
    134         config.addActionConfig(grandChild);
    135 
    136         assertTrue("Circular inheritance shouldn't have been detected",
    137             !grandChild.checkCircularInheritance(config));
    138     }
    139 
    140     /**
    141      * Basic check that should detect circular inheritance.
    142      */
    143     public void testCheckCircularInheritanceError() {
    144         ActionConfig child = new ActionConfig();
    145 
    146         child.setPath("/child");
    147         child.setExtends("/base");
    148 
    149         ActionConfig grandChild = new ActionConfig();
    150 
    151         grandChild.setPath("/grandChild");
    152         grandChild.setExtends("/child");
    153 
    154         // establish the circular relationship with base
    155         baseConfig.setExtends("/grandChild");
    156 
    157         config.addActionConfig(child);
    158         config.addActionConfig(grandChild);
    159 
    160         assertTrue("Circular inheritance should've been detected",
    161             grandChild.checkCircularInheritance(config));
    162     }
    163 
    164     /**
    165      * Test that processExtends() makes sure that a base action's own
    166      * extension has been processed.
    167      */
    168     public void testProcessExtendsActionExtends()
    169         throws Exception {
    170         CustomActionConfig first = new CustomActionConfig();
    171 
    172         first.setPath("/first");
    173 
    174         CustomActionConfig second = new CustomActionConfig();
    175 
    176         second.setPath("/second");
    177         second.setExtends("/first");
    178 
    179         config.addActionConfig(first);
    180         config.addActionConfig(second);
    181 
    182         // set baseConfig to extend second
    183         baseConfig.setExtends("/second");
    184 
    185         baseConfig.processExtends(config);
    186 
    187         assertTrue("The first action's processExtends() wasn't called",
    188             first.processExtendsCalled);
    189         assertTrue("The second action's processExtends() wasn't called",
    190             second.processExtendsCalled);
    191     }
    192 
    193     /**
    194      * Make sure that correct exception is thrown if a base action can't be
    195      * found.
    196      */
    197     public void testProcessExtendsMissingAction()
    198         throws Exception {
    199         baseConfig.setExtends("/someMissingAction");
    200 
    201         try {
    202             baseConfig.processExtends(config);
    203             fail(
    204                 "An exception should be thrown if a super form can't be found.");
    205         } catch (NullPointerException e) {
    206             // succeed
    207         } catch (InstantiationException e) {
    208             fail("Unrecognized exception thrown.");
    209         }
    210     }
    211 
    212     /**
    213      * Test a typical form bean configuration extension where various forwards
    214      * and exception handlers should be inherited from a base form. This
    215      * method checks all the subelements.
    216      */
    217     public void testInheritFrom()
    218         throws Exception {
    219         // create a basic subform
    220         ActionConfig subConfig = new ActionConfig();
    221         String subConfigPath = "subConfig";
    222 
    223         subConfig.setPath(subConfigPath);
    224         subConfig.setExtends("/base");
    225 
    226         // override success
    227         ForwardConfig forward = new ForwardConfig();
    228 
    229         forward.setName("success");
    230         forward.setPath("/newSuccess.jsp");
    231         forward.setRedirect(true);
    232         subConfig.addForwardConfig(forward);
    233 
    234         // add an exception handler
    235         ExceptionConfig handler = new ExceptionConfig();
    236 
    237         handler.setType("java.lang.NullPointerException");
    238         handler.setKey("msg.exception.npe");
    239         subConfig.addExceptionConfig(handler);
    240 
    241         // override arbitrary "label" property
    242         subConfig.setProperty("label", "sub");
    243 
    244         config.addActionConfig(subConfig);
    245 
    246         subConfig.inheritFrom(baseConfig);
    247 
    248         // check that our subConfig is still the one in the config
    249         assertSame("subConfig no longer in ModuleConfig", subConfig,
    250             config.findActionConfig("subConfig"));
    251 
    252         // check our configured sub config
    253         assertNotNull("Action type was not inherited", subConfig.getType());
    254         assertEquals("Wrong config path", subConfigPath, subConfig.getPath());
    255         assertEquals("Wrong config type", baseConfig.getType(),
    256             subConfig.getType());
    257 
    258         // check our forwards
    259         ForwardConfig[] forwards = subConfig.findForwardConfigs();
    260 
    261         assertEquals("Wrong forwards count", 2, forwards.length);
    262 
    263         forward = subConfig.findForwardConfig("success");
    264         assertNotNull("'success' forward was not found", forward);
    265         assertEquals("Wrong path for success", "/newSuccess.jsp",
    266             forward.getPath());
    267 
    268         forward = subConfig.findForwardConfig("failure");
    269 
    270         ForwardConfig origForward = baseConfig.findForwardConfig("failure");
    271 
    272         assertNotNull("'failure' forward was not inherited", forward);
    273         assertEquals("Wrong type for 'failure'", origForward.getPath(),
    274             forward.getPath());
    275         assertEquals("Arbitrary property not copied",
    276             origForward.getProperty("forwardCount"),
    277             forward.getProperty("forwardCount"));
    278 
    279         // check our exceptions
    280         ExceptionConfig[] handlers = subConfig.findExceptionConfigs();
    281 
    282         assertEquals("Wrong exception config count", 2, handlers.length);
    283 
    284         handler = subConfig.findExceptionConfig("java.sql.SQLException");
    285 
    286         ExceptionConfig origHandler =
    287             baseConfig.findExceptionConfig("java.sql.SQLException");
    288 
    289         assertNotNull("'SQLException' handler was not found", handler);
    290         assertEquals("Wrong key for 'SQLException'", origHandler.getKey(),
    291             handler.getKey());
    292         assertEquals("Arbitrary property not copied",
    293             origHandler.getProperty("exceptionCount"),
    294             handler.getProperty("exceptionCount"));
    295 
    296         handler =
    297             subConfig.findExceptionConfig("java.lang.NullPointerException");
    298         assertNotNull("'NullPointerException' handler disappeared", handler);
    299 
    300         // check the arbitrary properties
    301         String version = subConfig.getProperty("version");
    302 
    303         assertEquals("Arbitrary property 'version' wasn't inherited", "1a",
    304             version);
    305 
    306         String label = subConfig.getProperty("label");
    307 
    308         assertEquals("Arbitrary property 'label' shouldn't have changed",
    309             "sub", label);
    310     }
    311 
    312     /**
    313      * Make sure that correct exception is thrown if a base action can't be
    314      * found.
    315      */
    316     public void testInheritBoolean()
    317         throws Exception {
    318 
    319         ActionConfig parentConfig = new ActionConfig();
    320         parentConfig.setPath("/parent");
    321         ActionConfig childConfig  = null;
    322 
    323         // Test if boolean is NOT set it IS inherited
    324         parentConfig.setValidate(true);
    325         parentConfig.setCancellable(true);
    326         childConfig = new ActionConfig();
    327         childConfig.inheritFrom(parentConfig);
    328         assertEquals("default validate inherit true", true, childConfig.getValidate());
    329         assertEquals("default cancellable inherit true", true, childConfig.getValidate());
    330 
    331         // Test if boolean is NOT set it IS inherited
    332         parentConfig.setValidate(false);
    333         parentConfig.setCancellable(false);
    334         childConfig = new ActionConfig();
    335         childConfig.inheritFrom(parentConfig);
    336         assertEquals("default validate inherit false", false, childConfig.getValidate());
    337         assertEquals("default cancellable inherit false", false, childConfig.getValidate());
    338 
    339         // Test if boolean IS set it is NOT inherited
    340         parentConfig.setValidate(true);
    341         parentConfig.setCancellable(true);
    342         childConfig = new ActionConfig();
    343         childConfig.setValidate(false);
    344         childConfig.setCancellable(false);
    345         childConfig.inheritFrom(parentConfig);
    346         assertEquals("set validate (not inherit true)", false, childConfig.getValidate());
    347         assertEquals("set cancellable (not inherit false)", false, childConfig.getValidate());
    348 
    349         // Test if boolean IS set it is NOT inherited
    350         parentConfig.setValidate(false);
    351         parentConfig.setCancellable(false);
    352         childConfig = new ActionConfig();
    353         childConfig.setValidate(true);
    354         childConfig.setCancellable(true);
    355         childConfig.inheritFrom(parentConfig);
    356         assertEquals("set validate (not inherit false)", true, childConfig.getValidate());
    357         assertEquals("set cancellable (not inherit false)", true, childConfig.getValidate());
    358 
    359     }
    360 
    361     /**
    362      * Used to detect that ActionConfig is making the right calls.
    363      */
    364     public static class CustomActionConfig extends ActionConfig {
    365         boolean processExtendsCalled = false;
    366 
    367         public void processExtends(ModuleConfig moduleConfig)
    368             throws ClassNotFoundException, IllegalAccessException,
    369                 InstantiationException, InvocationTargetException {
    370             super.processExtends(moduleConfig);
    371             processExtendsCalled = true;
    372         }
    373     }
    374 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
