
    1   /*
    2    * $Id: TestActionServlet.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.action;
    22  
    23  import junit.framework.Test;
    24  import junit.framework.TestCase;
    25  import junit.framework.TestSuite;
    26  
    27  import org.apache.struts.config.ActionConfig;
    28  import org.apache.struts.config.ExceptionConfig;
    29  import org.apache.struts.config.FormBeanConfig;
    30  import org.apache.struts.config.FormPropertyConfig;
    31  import org.apache.struts.config.ForwardConfig;
    32  import org.apache.struts.config.ModuleConfig;
    33  import org.apache.struts.config.ModuleConfigFactory;
    34  import org.apache.struts.util.MessageResources;
    35  
    36  import javax.servlet.ServletException;
    37  import javax.servlet.UnavailableException;
    38  
    39  import java.util.List;
    40  
    41  /**
    42   * Suite of unit tests for the <code>org.apache.struts.action.ActionServlet</code>
    43   * class.
    44   */
    45  public class TestActionServlet extends TestCase {
    46      // ----------------------------------------------------- Instance Variables
    47  
    48      /**
    49       * The ModuleConfig we'll use.
    50       */
    51      protected ModuleConfig moduleConfig = null;
    52  
    53      /**
    54       * The common form bean we'll use.
    55       */
    56      protected FormBeanConfig baseFormBean = null;
    57  
    58      /**
    59       * The common exception config we'll use.
    60       */
    61      protected ExceptionConfig baseException = null;
    62  
    63      /**
    64       * The common action config we'll use.
    65       */
    66      protected ActionMapping baseAction = null;
    67  
    68      /**
    69       * The common action forward we'll use.
    70       */
    71      protected ActionForward baseForward = null;
    72  
    73      /**
    74       * The ActionServlet we'll test.
    75       */
    76      protected ActionServlet actionServlet = null;
    77  
    78      // ------------------------------------------ Constructors, suite, and main
    79  
    80      /**
    81       * Defines the testcase name for JUnit.
    82       *
    83       * @param theName the testcase's name.
    84       */
    85      public TestActionServlet(String theName) {
    86          super(theName);
    87      }
    88  
    89      /**
    90       * Start the tests.
    91       *
    92       * @param theArgs the arguments. Not used
    93       */
    94      public static void main(String[] theArgs) {
    95          junit.awtui.TestRunner.main(new String[] {
    96                  TestActionServlet.class.getName()
    97              });
    98      }
    99  
    100     /**
    101      * @return a test suite (<code>TestSuite</code>) that includes all methods
    102      *         starting with "test"
    103      */
    104     public static Test suite() {
    105         // All methods starting with "test" will be executed in the test suite.
    106         return new TestSuite(TestActionServlet.class);
    107     }
    108 
    109     // ------------------------------------------------- setUp() and tearDown()
    110 
    111     /**
    112      * Set up instance variables required by this test case.
    113      */
    114     public void setUp() throws Exception {
    115         actionServlet = new ActionServlet();
    116         actionServlet.initInternal();
    117 
    118         ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    119 
    120         moduleConfig = factoryObject.createModuleConfig("");
    121 
    122         // Setup the base form
    123         baseFormBean = new FormBeanConfig();
    124         baseFormBean.setName("baseForm");
    125         baseFormBean.setType("org.apache.struts.action.DynaActionForm");
    126 
    127         // Set up id, name, and score
    128         FormPropertyConfig property = new FormPropertyConfig();
    129 
    130         property.setName("id");
    131         property.setType("java.lang.String");
    132         baseFormBean.addFormPropertyConfig(property);
    133 
    134         property = new FormPropertyConfig();
    135         property.setName("name");
    136         property.setType("java.lang.String");
    137         baseFormBean.addFormPropertyConfig(property);
    138 
    139         property = new FormPropertyConfig();
    140         property.setName("score");
    141         property.setType("java.lang.String");
    142         baseFormBean.addFormPropertyConfig(property);
    143 
    144         // Setup the exception handler
    145         baseException = new ExceptionConfig();
    146         baseException.setType("java.lang.NullPointerException");
    147         baseException.setKey("msg.exception.npe");
    148 
    149         // Setup the forward config
    150         baseForward = new ActionForward("success", "/succes.jsp", false);
    151 
    152         // Setup the action config
    153         baseAction = new ActionMapping();
    154         baseAction.setPath("/index");
    155         baseAction.setType("org.apache.struts.actions.DummyAction");
    156         baseAction.setName("someForm");
    157         baseAction.setInput("/input.jsp");
    158         baseAction.addForwardConfig(new ActionForward("next", "/next.jsp", false));
    159         baseAction.addForwardConfig(new ActionForward("prev", "/prev.jsp", false));
    160 
    161         ExceptionConfig exceptionConfig = new ExceptionConfig();
    162 
    163         exceptionConfig.setType("java.sql.SQLException");
    164         exceptionConfig.setKey("msg.exception.sql");
    165         baseAction.addExceptionConfig(exceptionConfig);
    166 
    167         // Nothing is registered to our module config until they are needed
    168     }
    169 
    170     /**
    171      * Tear down instance variables required by this test case.
    172      */
    173     public void tearDown() {
    174         moduleConfig = null;
    175     }
    176 
    177     // ----------------------------- initInternal() and destroyInternal() tests
    178 
    179     /**
    180      * Verify that we can initialize and destroy our internal message
    181      * resources object.
    182      */
    183     public void testInitDestroyInternal() {
    184         ActionServlet servlet = new ActionServlet();
    185 
    186         try {
    187             servlet.initInternal();
    188         } catch (ServletException e) {
    189             fail("initInternal() threw exception: " + e);
    190         }
    191 
    192         assertTrue("internal was initialized", servlet.getInternal() != null);
    193         assertTrue("internal of correct type",
    194             servlet.getInternal() instanceof MessageResources);
    195         servlet.destroyInternal();
    196         assertTrue("internal was destroyed", servlet.getInternal() == null);
    197     }
    198 
    199     /**
    200      * Test class loader resolution and splitting.
    201      */
    202     public void notestSplitAndResolvePaths()
    203         throws Exception {
    204         ActionServlet servlet = new ActionServlet();
    205         List list =
    206             servlet.splitAndResolvePaths(
    207                 "org/apache/struts/config/struts-config.xml");
    208 
    209         assertNotNull(list);
    210         assertTrue("List size should be 1", list.size() == 1);
    211 
    212         list =
    213             servlet.splitAndResolvePaths(
    214                 "org/apache/struts/config/struts-config.xml, "
    215                 + "org/apache/struts/config/struts-config-1.1.xml");
    216         assertNotNull(list);
    217         assertTrue("List size should be 2, was " + list.size(), list.size() == 2);
    218 
    219         list = servlet.splitAndResolvePaths("META-INF/MANIFEST.MF");
    220         assertNotNull(list);
    221         assertTrue("Number of manifests should be more than 5, was "
    222             + list.size(), list.size() > 5);
    223 
    224         // test invalid path
    225         try {
    226             list =
    227                 servlet.splitAndResolvePaths(
    228                     "org/apache/struts/config/struts-asdfasdfconfig.xml");
    229             fail("Should have thrown an exception on bad path");
    230         } catch (NullPointerException ex) {
    231             // correct behavior since internal error resources aren't loaded
    232         }
    233     }
    234 
    235     //----- Test initApplication() method --------------------------------------
    236 
    237     /**
    238      * Verify that nothing happens if no "application" property is defined in
    239      * the servlet configuration.
    240      */
    241 
    242     /*
    243     public void testInitApplicationNull() throws ServletException
    244     {
    245         ActionServlet servlet = new ActionServlet();
    246         servlet.init(config);
    247 
    248         // Test the initApplication() method
    249         servlet.initApplication();
    250 
    251         // As no "application" object is found in the servlet config, no
    252         // attribute should be set in the context
    253         assertTrue(config.getServletContext().getAttribute(Action.MESSAGES_KEY) == null);
    254     }
    255     */
    256 
    257     /**
    258      * Verify that eveything is fine when only a "application" parameter is
    259      * defined in the servlet configuration.
    260      */
    261 
    262     /*
    263     public void testInitApplicationOk1() throws ServletException
    264     {
    265         // initialize config
    266         config.setInitParameter("application", "org.apache.struts.webapp.example.ApplicationResources");
    267 
    268         ActionServlet servlet = new ActionServlet();
    269         servlet.init(config);
    270 
    271         // Test the initApplication() method
    272         servlet.initApplication();
    273 
    274         assertTrue(servlet.application != null);
    275         assertTrue(servlet.application.getReturnNull() == true);
    276 
    277         assertTrue(config.getServletContext().getAttribute(Action.MESSAGES_KEY) != null);
    278         assertEquals(servlet.application, config.getServletContext().getAttribute(Action.MESSAGES_KEY));
    279 
    280     }
    281     */
    282 
    283     // --------------------------------------------------- FormBeanConfig Tests
    284 
    285     /**
    286      * Test that nothing fails if there are no extensions.
    287      */
    288     public void testInitModuleFormBeansNoExtends()
    289         throws ServletException {
    290         moduleConfig.addFormBeanConfig(baseFormBean);
    291 
    292         try {
    293             actionServlet.initModuleExceptionConfigs(moduleConfig);
    294         } catch (Exception e) {
    295             fail("Unexpected exception caught.");
    296         }
    297     }
    298 
    299     /**
    300      * Test that initModuleFormBeans throws an exception when a form with a
    301      * null type is present.
    302      */
    303     public void testInitModuleFormBeansNullFormType()
    304         throws ServletException {
    305         FormBeanConfig formBean = new FormBeanConfig();
    306 
    307         formBean.setName("noTypeForm");
    308         moduleConfig.addFormBeanConfig(formBean);
    309 
    310         try {
    311             actionServlet.initModuleFormBeans(moduleConfig);
    312             fail("An exception should've been thrown here.");
    313         } catch (UnavailableException e) {
    314             // success
    315         } catch (Exception e) {
    316             fail("Unrecognized exception thrown: " + e);
    317         }
    318     }
    319 
    320     /**
    321      * Test that initModuleFormBeans throws an exception when a form whose
    322      * prop type is null is present.
    323      */
    324     public void testInitModuleFormBeansNullPropType()
    325         throws ServletException {
    326         moduleConfig.addFormBeanConfig(baseFormBean);
    327         baseFormBean.findFormPropertyConfig("name").setType(null);
    328 
    329         try {
    330             actionServlet.initModuleFormBeans(moduleConfig);
    331             fail("An exception should've been thrown here.");
    332         } catch (UnavailableException e) {
    333             // success
    334         } catch (Exception e) {
    335             fail("Unrecognized exception thrown: " + e);
    336         }
    337     }
    338 
    339     /**
    340      * Test that processFormBeanExtension() calls processExtends()
    341      */
    342     public void testProcessFormBeanExtension()
    343         throws ServletException {
    344         CustomFormBeanConfig form = new CustomFormBeanConfig();
    345 
    346         actionServlet.processFormBeanExtension(form, moduleConfig);
    347 
    348         assertTrue("processExtends() was not called", form.processExtendsCalled);
    349     }
    350 
    351     /**
    352      * Make sure processFormBeanConfigClass() returns an instance of the
    353      * correct class if the base config is using a custom class.
    354      */
    355     public void testProcessFormBeanConfigClass()
    356         throws Exception {
    357         CustomFormBeanConfig customBase = new CustomFormBeanConfig();
    358 
    359         customBase.setName("customBase");
    360         moduleConfig.addFormBeanConfig(customBase);
    361 
    362         FormBeanConfig customSub = new FormBeanConfig();
    363 
    364         customSub.setName("customSub");
    365         customSub.setExtends("customBase");
    366         customSub.setType("org.apache.struts.action.DynaActionForm");
    367         moduleConfig.addFormBeanConfig(customSub);
    368 
    369         FormBeanConfig result =
    370             actionServlet.processFormBeanConfigClass(customSub, moduleConfig);
    371 
    372         assertTrue("Incorrect class of form bean config",
    373             result instanceof CustomFormBeanConfig);
    374         assertEquals("Incorrect name", customSub.getName(), result.getName());
    375         assertEquals("Incorrect type", customSub.getType(), result.getType());
    376         assertEquals("Incorrect extends", customSub.getExtends(),
    377             result.getExtends());
    378         assertEquals("Incorrect 'restricted' value", customSub.isRestricted(),
    379             result.isRestricted());
    380 
    381         assertSame("Result was not registered in the module config", result,
    382             moduleConfig.findFormBeanConfig("customSub"));
    383     }
    384 
    385     /**
    386      * Make sure processFormBeanConfigClass() returns what it was given if the
    387      * form passed to it doesn't extend anything.
    388      */
    389     public void testProcessFormBeanConfigClassNoExtends()
    390         throws Exception {
    391         moduleConfig.addFormBeanConfig(baseFormBean);
    392 
    393         FormBeanConfig result = null;
    394 
    395         try {
    396             result =
    397                 actionServlet.processFormBeanConfigClass(baseFormBean,
    398                     moduleConfig);
    399         } catch (UnavailableException e) {
    400             fail("An exception should not be thrown when there's nothing to do");
    401         }
    402 
    403         assertSame("Result should be the same as the input.", baseFormBean,
    404             result);
    405     }
    406 
    407     /**
    408      * Make sure processFormBeanConfigClass() returns the same class instance
    409      * if the base config isn't using a custom class.
    410      */
    411     public void testProcessFormBeanConfigClassSubFormCustomClass()
    412         throws Exception {
    413         moduleConfig.addFormBeanConfig(baseFormBean);
    414 
    415         FormBeanConfig customSub = new FormBeanConfig();
    416 
    417         customSub.setName("customSub");
    418         customSub.setExtends("baseForm");
    419         moduleConfig.addFormBeanConfig(customSub);
    420 
    421         FormBeanConfig result =
    422             actionServlet.processFormBeanConfigClass(customSub, moduleConfig);
    423 
    424         assertSame("The instance returned should be the param given it.",
    425             customSub, result);
    426     }
    427 
    428     /**
    429      * Make sure the code throws the correct exception when it can't create an
    430      * instance of the base config's custom class.
    431      */
    432     public void notestProcessFormBeanConfigClassError()
    433         throws Exception {
    434         CustomFormBeanConfigArg customBase =
    435             new CustomFormBeanConfigArg("customBase");
    436 
    437         moduleConfig.addFormBeanConfig(customBase);
    438 
    439         FormBeanConfig customSub = new FormBeanConfig();
    440 
    441         customSub.setName("customSub");
    442         customSub.setExtends("customBase");
    443         moduleConfig.addFormBeanConfig(customSub);
    444 
    445         try {
    446             actionServlet.processFormBeanConfigClass(customSub, moduleConfig);
    447             fail("Exception should be thrown");
    448         } catch (UnavailableException e) {
    449             // success
    450         } catch (Exception e) {
    451             fail("Unexpected exception thrown.");
    452         }
    453     }
    454 
    455     /**
    456      * Test the case where the subform has already specified its own form bean
    457      * config class.  If the code still attempts to create a new instance, an
    458      * error will be thrown.
    459      */
    460     public void testProcessFormBeanConfigClassOverriddenSubFormClass()
    461         throws Exception {
    462         CustomFormBeanConfigArg customBase =
    463             new CustomFormBeanConfigArg("customBase");
    464 
    465         moduleConfig.addFormBeanConfig(customBase);
    466 
    467         FormBeanConfig customSub = new CustomFormBeanConfigArg("customSub");
    468 
    469         customSub.setExtends("customBase");
    470         moduleConfig.addFormBeanConfig(customSub);
    471 
    472         try {
    473             actionServlet.processFormBeanConfigClass(customSub, moduleConfig);
    474         } catch (Exception e) {
    475             fail("Exception should not be thrown");
    476         }
    477     }
    478 
    479     // -------------------------------------------------- ExceptionConfig Tests
    480 
    481     /**
    482      * Test that nothing fails if there are no extensions.
    483      */
    484     public void testInitModuleExceptionConfigsNoExtends()
    485         throws ServletException {
    486         moduleConfig.addExceptionConfig(baseException);
    487 
    488         try {
    489             actionServlet.initModuleExceptionConfigs(moduleConfig);
    490         } catch (Exception e) {
    491             fail("Unexpected exception caught.");
    492         }
    493     }
    494 
    495     /**
    496      * Test that initModuleExceptionConfigs throws an exception when a handler
    497      * with a null key is present.
    498      */
    499     public void testInitModuleExceptionConfigsNullFormType()
    500         throws ServletException {
    501         ExceptionConfig handler = new ExceptionConfig();
    502 
    503         handler.setType("java.lang.NullPointerException");
    504         moduleConfig.addExceptionConfig(handler);
    505 
    506         try {
    507             actionServlet.initModuleExceptionConfigs(moduleConfig);
    508             fail("An exception should've been thrown here.");
    509         } catch (UnavailableException e) {
    510             // success
    511         } catch (Exception e) {
    512             fail("Unrecognized exception thrown: " + e);
    513         }
    514     }
    515 
    516     /**
    517      * Test that processExceptionExtension() calls processExtends()
    518      */
    519     public void testProcessExceptionExtension()
    520         throws ServletException {
    521         CustomExceptionConfig handler = new CustomExceptionConfig();
    522 
    523         handler.setType("java.lang.NullPointerException");
    524         moduleConfig.addExceptionConfig(handler);
    525         actionServlet.processExceptionExtension(handler, moduleConfig, null);
    526 
    527         assertTrue("processExtends() was not called",
    528             handler.processExtendsCalled);
    529     }
    530 
    531     /**
    532      * Make sure processExceptionConfigClass() returns an instance of the
    533      * correct class if the base config is using a custom class.
    534      */
    535     public void testProcessExceptionConfigClass()
    536         throws Exception {
    537         CustomExceptionConfig customBase = new CustomExceptionConfig();
    538 
    539         customBase.setType("java.lang.NullPointerException");
    540         customBase.setKey("msg.exception.npe");
    541         moduleConfig.addExceptionConfig(customBase);
    542 
    543         ExceptionConfig customSub = new ExceptionConfig();
    544 
    545         customSub.setType("java.lang.IllegalStateException");
    546         customSub.setExtends("java.lang.NullPointerException");
    547         moduleConfig.addExceptionConfig(customSub);
    548 
    549         ExceptionConfig result =
    550             actionServlet.processExceptionConfigClass(customSub, moduleConfig,
    551                 null);
    552 
    553         assertTrue("Incorrect class of exception config",
    554             result instanceof CustomExceptionConfig);
    555         assertEquals("Incorrect type", customSub.getType(), result.getType());
    556         assertEquals("Incorrect key", customSub.getKey(), result.getKey());
    557         assertEquals("Incorrect extends", customSub.getExtends(),
    558             result.getExtends());
    559 
    560         assertSame("Result was not registered in the module config", result,
    561             moduleConfig.findExceptionConfig("java.lang.IllegalStateException"));
    562     }
    563 
    564     /**
    565      * Make sure processExceptionConfigClass() returns what it was given if
    566      * the handler passed to it doesn't extend anything.
    567      */
    568     public void testProcessExceptionConfigClassNoExtends()
    569         throws Exception {
    570         moduleConfig.addExceptionConfig(baseException);
    571 
    572         ExceptionConfig result = null;
    573 
    574         try {
    575             result =
    576                 actionServlet.processExceptionConfigClass(baseException,
    577                     moduleConfig, null);
    578         } catch (UnavailableException e) {
    579             fail("An exception should not be thrown when there's nothing to do");
    580         }
    581 
    582         assertSame("Result should be the same as the input.", baseException,
    583             result);
    584     }
    585 
    586     /**
    587      * Make sure processExceptionConfigClass() returns the same class instance
    588      * if the base config isn't using a custom class.
    589      */
    590     public void testProcessExceptionConfigClassSubConfigCustomClass()
    591         throws Exception {
    592         moduleConfig.addExceptionConfig(baseException);
    593 
    594         ExceptionConfig customSub = new ExceptionConfig();
    595 
    596         customSub.setType("java.lang.IllegalStateException");
    597         customSub.setExtends("java.lang.NullPointerException");
    598         moduleConfig.addExceptionConfig(customSub);
    599 
    600         ExceptionConfig result =
    601             actionServlet.processExceptionConfigClass(customSub, moduleConfig,
    602                 null);
    603 
    604         assertSame("The instance returned should be the param given it.",
    605             customSub, result);
    606     }
    607 
    608     /**
    609      * Make sure the code throws the correct exception when it can't create an
    610      * instance of the base config's custom class.
    611      */
    612     public void notestProcessExceptionConfigClassError()
    613         throws Exception {
    614         ExceptionConfig customBase =
    615             new CustomExceptionConfigArg("java.lang.NullPointerException");
    616 
    617         moduleConfig.addExceptionConfig(customBase);
    618 
    619         ExceptionConfig customSub = new ExceptionConfig();
    620 
    621         customSub.setType("java.lang.IllegalStateException");
    622         customSub.setExtends("java.lang.NullPointerException");
    623         moduleConfig.addExceptionConfig(customSub);
    624 
    625         try {
    626             actionServlet.processExceptionConfigClass(customSub, moduleConfig,
    627                 null);
    628             fail("Exception should be thrown");
    629         } catch (UnavailableException e) {
    630             // success
    631         } catch (Exception e) {
    632             fail("Unexpected exception thrown.");
    633         }
    634     }
    635 
    636     /**
    637      * Test the case where the subconfig has already specified its own config
    638      * class.  If the code still attempts to create a new instance, an error
    639      * will be thrown.
    640      */
    641     public void testProcessExceptionConfigClassOverriddenSubFormClass()
    642         throws Exception {
    643         moduleConfig.addExceptionConfig(baseException);
    644 
    645         ExceptionConfig customSub =
    646             new CustomExceptionConfigArg("java.lang.IllegalStateException");
    647 
    648         customSub.setExtends("java.lang.NullPointerException");
    649         moduleConfig.addExceptionConfig(customSub);
    650 
    651         try {
    652             actionServlet.processExceptionConfigClass(customSub, moduleConfig,
    653                 null);
    654         } catch (Exception e) {
    655             fail("Exception should not be thrown");
    656         }
    657     }
    658 
    659     // ---------------------------------------------------- ForwardConfig Tests
    660 
    661     /**
    662      * Test that nothing fails if there are no extensions.
    663      */
    664     public void testInitModuleForwardConfigsNoExtends()
    665         throws ServletException {
    666         moduleConfig.addForwardConfig(baseForward);
    667 
    668         try {
    669             actionServlet.initModuleForwards(moduleConfig);
    670         } catch (Exception e) {
    671             fail("Unexpected exception caught.");
    672         }
    673     }
    674 
    675     /**
    676      * Test that initModuleForwards throws an exception when a forward with a
    677      * null path is present.
    678      */
    679     public void testInitModuleForwardsNullFormType()
    680         throws ServletException {
    681         ActionForward forward = new ActionForward("success", null, false);
    682 
    683         moduleConfig.addForwardConfig(forward);
    684 
    685         try {
    686             actionServlet.initModuleForwards(moduleConfig);
    687             fail("An exception should've been thrown here.");
    688         } catch (UnavailableException e) {
    689             // success
    690         } catch (Exception e) {
    691             fail("Unrecognized exception thrown: " + e);
    692         }
    693     }
    694 
    695     /**
    696      * Test that processForwardExtension() calls processExtends()
    697      */
    698     public void testProcessForwardExtension()
    699         throws ServletException {
    700         CustomForwardConfig forward =
    701             new CustomForwardConfig("forward", "/forward.jsp");
    702 
    703         moduleConfig.addForwardConfig(forward);
    704         actionServlet.processForwardExtension(forward, moduleConfig, null);
    705 
    706         assertTrue("processExtends() was not called",
    707             forward.processExtendsCalled);
    708     }
    709 
    710     /**
    711      * Make sure processForwardConfigClass() returns an instance of the
    712      * correct class if the base config is using a custom class.
    713      */
    714     public void testProcessForwardConfigClass()
    715         throws Exception {
    716         CustomForwardConfig customBase =
    717             new CustomForwardConfig("success", "/success.jsp");
    718 
    719         moduleConfig.addForwardConfig(customBase);
    720 
    721         ActionForward customSub = new ActionForward();
    722 
    723         customSub.setName("failure");
    724         customSub.setExtends("success");
    725         moduleConfig.addForwardConfig(customSub);
    726 
    727         ForwardConfig result =
    728             actionServlet.processForwardConfigClass(customSub, moduleConfig,
    729                 null);
    730 
    731         assertTrue("Incorrect class of forward config",
    732             result instanceof CustomForwardConfig);
    733         assertEquals("Incorrect name", customSub.getName(), result.getName());
    734         assertEquals("Incorrect path", customSub.getPath(), result.getPath());
    735         assertEquals("Incorrect extends", customSub.getExtends(),
    736             result.getExtends());
    737 
    738         assertSame("Result was not registered in the module config", result,
    739             moduleConfig.findForwardConfig("failure"));
    740     }
    741 
    742     /**
    743      * Make sure processForwardConfigClass() returns what it was given if the
    744      * forward passed to it doesn't extend anything.
    745      */
    746     public void testProcessForwardConfigClassNoExtends()
    747         throws Exception {
    748         moduleConfig.addForwardConfig(baseForward);
    749 
    750         ForwardConfig result = null;
    751 
    752         try {
    753             result =
    754                 actionServlet.processForwardConfigClass(baseForward,
    755                     moduleConfig, null);
    756         } catch (UnavailableException e) {
    757             fail("An exception should not be thrown when there's nothing to do");
    758         }
    759 
    760         assertSame("Result should be the same as the input.", baseForward,
    761             result);
    762     }
    763 
    764     /**
    765      * Make sure processForwardConfigClass() returns the same class instance
    766      * if the base config isn't using a custom class.
    767      */
    768     public void testProcessForwardConfigClassSubConfigCustomClass()
    769         throws Exception {
    770         moduleConfig.addForwardConfig(baseForward);
    771 
    772         ForwardConfig customSub = new ActionForward();
    773 
    774         customSub.setName("failure");
    775         customSub.setExtends("success");
    776         moduleConfig.addForwardConfig(customSub);
    777 
    778         ForwardConfig result =
    779             actionServlet.processForwardConfigClass(customSub, moduleConfig,
    780                 null);
    781 
    782         assertSame("The instance returned should be the param given it.",
    783             customSub, result);
    784     }
    785 
    786     /**
    787      * Make sure the code throws the correct exception when it can't create an
    788      * instance of the base config's custom class.
    789      */
    790     public void notestProcessForwardConfigClassError()
    791         throws Exception {
    792         ForwardConfig customBase =
    793             new CustomForwardConfigArg("success", "/success.jsp");
    794 
    795         moduleConfig.addForwardConfig(customBase);
    796 
    797         ForwardConfig customSub = new ActionForward();
    798 
    799         customSub.setName("failure");
    800         customSub.setExtends("success");
    801         moduleConfig.addForwardConfig(customSub);
    802 
    803         try {
    804             actionServlet.processForwardConfigClass(customSub, moduleConfig,
    805                 null);
    806             fail("Exception should be thrown");
    807         } catch (UnavailableException e) {
    808             // success
    809         } catch (Exception e) {
    810             fail("Unexpected exception thrown.");
    811         }
    812     }
    813 
    814     /**
    815      * Test the case where the subconfig has already specified its own config
    816      * class.  If the code still attempts to create a new instance, an error
    817      * will be thrown.
    818      */
    819     public void testProcessForwardConfigClassOverriddenSubConfigClass()
    820         throws Exception {
    821         moduleConfig.addForwardConfig(baseForward);
    822 
    823         ForwardConfig customSub =
    824             new CustomForwardConfigArg("failure", "/failure.jsp");
    825 
    826         customSub.setExtends("success");
    827         moduleConfig.addForwardConfig(customSub);
    828 
    829         try {
    830             actionServlet.processForwardConfigClass(customSub, moduleConfig,
    831                 null);
    832         } catch (Exception e) {
    833             fail("Exception should not be thrown");
    834         }
    835     }
    836 
    837     // --------------------------------------------------- ActionConfig Tests
    838 
    839     /**
    840      * Test that nothing fails if there are no extensions.
    841      */
    842     public void testInitModuleActionConfigsNoExtends()
    843         throws ServletException {
    844         moduleConfig.addActionConfig(baseAction);
    845 
    846         try {
    847             actionServlet.initModuleActions(moduleConfig);
    848         } catch (Exception e) {
    849             fail("Unexpected exception caught.");
    850         }
    851     }
    852 
    853     /**
    854      * Test that processActionConfigExtension() calls processExtends()
    855      */
    856     public void testProcessActionExtension()
    857         throws ServletException {
    858         CustomActionConfig action = new CustomActionConfig("/action");
    859 
    860         moduleConfig.addActionConfig(action);
    861         actionServlet.processActionConfigExtension(action, moduleConfig);
    862 
    863         assertTrue("processExtends() was not called",
    864             action.processExtendsCalled);
    865     }
    866 
    867     /**
    868      * Test that an ActionConfig's ForwardConfig can inherit from a
    869      * global ForwardConfig.
    870      */
    871     public void testProcessActionExtensionWithForwardConfig()
    872         throws ServletException {
    873         ForwardConfig forwardConfig = new ForwardConfig();
    874         forwardConfig.setName("sub");
    875         forwardConfig.setExtends("success");
    876         baseAction.addForwardConfig(forwardConfig);
    877 
    878         moduleConfig.addActionConfig(baseAction);
    879         moduleConfig.addForwardConfig(baseForward);
    880         actionServlet.processActionConfigExtension(baseAction, moduleConfig);
    881 
    882         forwardConfig = baseAction.findForwardConfig("sub");
    883 
    884         assertEquals("'sub' forward's inheritance was not processed.",
    885             baseForward.getPath(), forwardConfig.getPath());
    886     }
    887 
    888     /**
    889      * Test that an ActionConfig's ExceptionConfig can inherit from a
    890      * global ExceptionConfig.
    891      */
    892     public void testProcessActionExtensionWithExceptionConfig()
    893         throws ServletException {
    894         ExceptionConfig exceptionConfig = new ExceptionConfig();
    895         exceptionConfig.setType("SomeException");
    896         exceptionConfig.setExtends("java.lang.NullPointerException");
    897         baseAction.addExceptionConfig(exceptionConfig);
    898 
    899         moduleConfig.addActionConfig(baseAction);
    900         moduleConfig.addExceptionConfig(baseException);
    901         actionServlet.processActionConfigExtension(baseAction, moduleConfig);
    902 
    903         exceptionConfig = baseAction.findExceptionConfig("SomeException");
    904 
    905         assertEquals("SomeException's inheritance was not processed.",
    906             baseException.getKey(), exceptionConfig.getKey());
    907     }
    908 
    909     /**
    910      * Make sure processActionConfigClass() returns an instance of the correct
    911      * class if the base config is using a custom class.
    912      */
    913     public void testProcessActionConfigClass()
    914         throws Exception {
    915         CustomActionConfig customBase = new CustomActionConfig("/base");
    916 
    917         moduleConfig.addActionConfig(customBase);
    918 
    919         ActionMapping customSub = new ActionMapping();
    920 
    921         customSub.setPath("/sub");
    922         customSub.setExtends("/base");
    923         moduleConfig.addActionConfig(customSub);
    924 
    925         ActionConfig result =
    926             actionServlet.processActionConfigClass(customSub, moduleConfig);
    927 
    928         assertTrue("Incorrect class of action config",
    929             result instanceof CustomActionConfig);
    930         assertEquals("Incorrect path", customSub.getPath(), result.getPath());
    931         assertEquals("Incorrect extends", customSub.getExtends(),
    932             result.getExtends());
    933 
    934         assertSame("Result was not registered in the module config", result,
    935             moduleConfig.findActionConfig("/sub"));
    936     }
    937 
    938     /**
    939      * Make sure processActionConfigClass() returns what it was given if the
    940      * action passed to it doesn't extend anything.
    941      */
    942     public void testProcessActionConfigClassNoExtends()
    943         throws Exception {
    944         moduleConfig.addActionConfig(baseAction);
    945 
    946         ActionConfig result = null;
    947 
    948         try {
    949             result =
    950                 actionServlet.processActionConfigClass(baseAction, moduleConfig);
    951         } catch (UnavailableException e) {
    952             fail("An exception should not be thrown here");
    953         }
    954 
    955         assertSame("Result should be the same as the input.", baseAction, result);
    956     }
    957 
    958     /**
    959      * Make sure processActionConfigClass() returns the same class instance if
    960      * the base config isn't using a custom class.
    961      */
    962     public void testProcessActionConfigClassSubConfigCustomClass()
    963         throws Exception {
    964         moduleConfig.addActionConfig(baseAction);
    965 
    966         ActionConfig customSub = new ActionMapping();
    967 
    968         customSub.setPath("/sub");
    969         customSub.setExtends("/index");
    970         moduleConfig.addActionConfig(customSub);
    971 
    972         ActionConfig result =
    973             actionServlet.processActionConfigClass(customSub, moduleConfig);
    974 
    975         assertSame("The instance returned should be the param given it.",
    976             customSub, result);
    977     }
    978 
    979     /**
    980      * Make sure the code throws the correct exception when it can't create an
    981      * instance of the base config's custom class.
    982      */
    983     public void notestProcessActionConfigClassError()
    984         throws Exception {
    985         ActionConfig customBase = new CustomActionConfigArg("/index");
    986 
    987         moduleConfig.addActionConfig(customBase);
    988 
    989         ActionConfig customSub = new ActionMapping();
    990 
    991         customSub.setPath("/sub");
    992         customSub.setExtends("/index");
    993         moduleConfig.addActionConfig(customSub);
    994 
    995         try {
    996             actionServlet.processActionConfigClass(customSub, moduleConfig);
    997             fail("Exception should be thrown");
    998         } catch (UnavailableException e) {
    999             // success
    1000         } catch (Exception e) {
    1001             fail("Unexpected exception thrown.");
    1002         }
    1003     }
    1004 
    1005     /**
    1006      * Test the case where the subconfig has already specified its own config
    1007      * class.  If the code still attempts to create a new instance, an error
    1008      * will be thrown.
    1009      */
    1010     public void testProcessActionConfigClassOverriddenSubConfigClass()
    1011         throws Exception {
    1012         moduleConfig.addActionConfig(baseAction);
    1013 
    1014         ActionConfig customSub = new CustomActionConfigArg("/sub");
    1015 
    1016         customSub.setExtends("/index");
    1017         moduleConfig.addActionConfig(customSub);
    1018 
    1019         try {
    1020             actionServlet.processActionConfigClass(customSub, moduleConfig);
    1021         } catch (Exception e) {
    1022             fail("Exception should not be thrown");
    1023         }
    1024     }
    1025 
    1026     /**
    1027      * Used for testing custom FormBeanConfig classes.
    1028      */
    1029     public static class CustomFormBeanConfig extends FormBeanConfig {
    1030         public boolean processExtendsCalled = false;
    1031 
    1032         public CustomFormBeanConfig() {
    1033             super();
    1034         }
    1035 
    1036         /**
    1037          * Set a flag so we know this method was called.
    1038          */
    1039         public void processExtends(ModuleConfig moduleConfig)
    1040             throws ClassNotFoundException, IllegalAccessException,
    1041                 InstantiationException {
    1042             processExtendsCalled = true;
    1043         }
    1044     }
    1045 
    1046     /**
    1047      * Used to test cases where the subclass cannot be created with a no-arg
    1048      * constructor.
    1049      */
    1050     private class CustomFormBeanConfigArg extends FormBeanConfig {
    1051         CustomFormBeanConfigArg(String name) {
    1052             super();
    1053             setName(name);
    1054         }
    1055     }
    1056 
    1057     /**
    1058      * Used for testing custom ExceptionConfig classes.
    1059      */
    1060     public static class CustomExceptionConfig extends ExceptionConfig {
    1061         public boolean processExtendsCalled = false;
    1062 
    1063         public CustomExceptionConfig() {
    1064             super();
    1065         }
    1066 
    1067         /**
    1068          * Set a flag so we know this method was called.
    1069          */
    1070         public void processExtends(ModuleConfig moduleConfig,
    1071             ActionConfig actionConfig)
    1072             throws ClassNotFoundException, IllegalAccessException,
    1073                 InstantiationException {
    1074             processExtendsCalled = true;
    1075         }
    1076     }
    1077 
    1078     /**
    1079      * Used to test cases where the subclass cannot be created with a no-arg
    1080      * constructor.
    1081      */
    1082     private class CustomExceptionConfigArg extends ExceptionConfig {
    1083         CustomExceptionConfigArg(String type) {
    1084             super();
    1085             setType(type);
    1086         }
    1087     }
    1088 
    1089     /**
    1090      * Used for testing custom ForwardConfig classes.
    1091      */
    1092     public static class CustomForwardConfig extends ForwardConfig {
    1093         public boolean processExtendsCalled = false;
    1094 
    1095         public CustomForwardConfig() {
    1096             super();
    1097         }
    1098 
    1099         public CustomForwardConfig(String name, String path) {
    1100             super(name, path, false);
    1101         }
    1102 
    1103         /**
    1104          * Set a flag so we know this method was called.
    1105          */
    1106         public void processExtends(ModuleConfig moduleConfig,
    1107             ActionConfig actionConfig)
    1108             throws ClassNotFoundException, IllegalAccessException,
    1109                 InstantiationException {
    1110             processExtendsCalled = true;
    1111         }
    1112     }
    1113 
    1114     /**
    1115      * Used to test cases where the subclass cannot be created with a no-arg
    1116      * constructor.
    1117      */
    1118     private class CustomForwardConfigArg extends ForwardConfig {
    1119         CustomForwardConfigArg(String name, String path) {
    1120             super();
    1121             setName(name);
    1122             setPath(path);
    1123         }
    1124     }
    1125 
    1126     /**
    1127      * Used for testing custom ActionConfig classes.
    1128      */
    1129     public static class CustomActionConfig extends ActionConfig {
    1130         public boolean processExtendsCalled = false;
    1131 
    1132         public CustomActionConfig() {
    1133             super();
    1134         }
    1135 
    1136         public CustomActionConfig(String path) {
    1137             super();
    1138             setPath(path);
    1139         }
    1140 
    1141         /**
    1142          * Set a flag so we know this method was called.
    1143          */
    1144         public void processExtends(ModuleConfig moduleConfig)
    1145             throws ClassNotFoundException, IllegalAccessException,
    1146                 InstantiationException {
    1147             processExtendsCalled = true;
    1148         }
    1149     }
    1150 
    1151     /**
    1152      * Used to test cases where the subclass cannot be created with a no-arg
    1153      * constructor.
    1154      */
    1155     private class CustomActionConfigArg extends ActionConfig {
    1156         CustomActionConfigArg(String path) {
    1157             super();
    1158             setPath(path);
    1159         }
    1160     }
    1161 
    1162     // [...]
    1163 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
