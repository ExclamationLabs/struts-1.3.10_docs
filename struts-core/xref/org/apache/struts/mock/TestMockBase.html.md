[View Javadoc](../../../../../apidocs/org/apache/struts/mock/TestMockBase.html.md)


    1   /*
    2    * $Id: TestMockBase.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.mock;
    22  
    23  import junit.framework.Test;
    24  import junit.framework.TestCase;
    25  import junit.framework.TestSuite;
    26  
    27  import org.apache.struts.Globals;
    28  import org.apache.struts.action.ActionFormBean;
    29  import org.apache.struts.action.ActionForward;
    30  import org.apache.struts.action.ActionMapping;
    31  import org.apache.struts.config.ControllerConfig;
    32  import org.apache.struts.config.FormPropertyConfig;
    33  import org.apache.struts.config.ForwardConfig;
    34  import org.apache.struts.config.ModuleConfig;
    35  import org.apache.struts.config.ModuleConfigFactory;
    36  
    37  /**
    38   * <p>Convenience base class for unit tests of the <code>org.apache.struts.util</code>
    39   * package, and others that require a runtime environment similar to what the
    40   * Struts controller servlet sets up.  The <code>setUp()</code> method
    41   * establishes a consistent basic environment for the various tests.  The only
    42   * tests included in this class are simple validations that the basic
    43   * environment was set up correctly.</p>
    44   *
    45   * @version $Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005)
    46   *          $
    47   */
    48  public class TestMockBase extends TestCase {
    49      // ----------------------------------------------------- Instance Variables
    50      protected ModuleConfig moduleConfig = null;
    51      protected ModuleConfig moduleConfig2 = null;
    52      protected ModuleConfig moduleConfig3 = null;
    53      protected MockServletConfig config = null;
    54      protected MockServletContext context = null;
    55      protected MockPageContext page = null;
    56      protected MockPrincipal principal = null;
    57      protected MockHttpServletRequest request = null;
    58      protected MockHttpServletResponse response = null;
    59      protected MockHttpSession session = null;
    60  
    61      // ----------------------------------------------------------------- Basics
    62      public TestMockBase(String name) {
    63          super(name);
    64      }
    65  
    66      public static void main(String[] args) {
    67          junit.awtui.TestRunner.main(new String[] { TestMockBase.class.getName() });
    68      }
    69  
    70      public static Test suite() {
    71          return (new TestSuite(TestMockBase.class));
    72      }
    73  
    74      // ----------------------------------------------------- Setup and Teardown
    75      public void setUp() {
    76          // Set up the servlet API objects for a test scenario
    77          context = new MockServletContext();
    78          config = new MockServletConfig(context);
    79          session = new MockHttpSession(context);
    80          request = new MockHttpServletRequest(session);
    81          principal =
    82              new MockPrincipal("username", new String[] { "admin", "manager" });
    83          request.setUserPrincipal(principal);
    84          response = new MockHttpServletResponse();
    85          page = new MockPageContext(config, request, response);
    86  
    87          // Set up application configurations for our supported modules
    88          setUpDefaultApp();
    89          setUpSecondApp();
    90          setUpThirdApp();
    91  
    92          // NOTE - we do not initialize the request attribute
    93          // for the selected module so that fallbacks to the
    94          // default module can be tested.  To select a module,
    95          // tests should set the request attribute Globals.MODULE_KEY
    96          // to the ModuleConfig instance for the selected module
    97      }
    98  
    99      protected void setUpDefaultApp() {
    100         ActionFormBean formBean = null;
    101         ActionMapping mapping = null;
    102 
    103         ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    104 
    105         moduleConfig = factoryObject.createModuleConfig("");
    106 
    107         context.setAttribute(Globals.MODULE_KEY, moduleConfig);
    108 
    109         // Forward "external" to "http://jakarta.apache.org/"
    110         moduleConfig.addForwardConfig(new ActionForward("external",
    111                 "http://jakarta.apache.org/", false));
    112 
    113         // Forward "foo" to "/bar.jsp"
    114         moduleConfig.addForwardConfig(new ActionForward("foo", "/bar.jsp", false));
    115 
    116         // Forward "relative1" to "relative.jsp" non-context-relative
    117         moduleConfig.addForwardConfig(new ActionForward("relative1",
    118                 "relative.jsp", false));
    119 
    120         // Forward "relative2" to "relative.jsp" context-relative
    121         moduleConfig.addForwardConfig(new ActionForward("relative2",
    122                 "relative.jsp", false));
    123 
    124         // Form Bean "static" is a standard ActionForm subclass
    125         formBean =
    126             new ActionFormBean("static", "org.apache.struts.mock.MockFormBean");
    127         moduleConfig.addFormBeanConfig(formBean);
    128 
    129         // Action "/static" uses the "static" form bean in request scope
    130         mapping = new ActionMapping();
    131         mapping.setInput("/static.jsp");
    132         mapping.setName("static");
    133         mapping.setPath("/static");
    134         mapping.setScope("request");
    135         mapping.setType("org.apache.struts.mock.MockAction");
    136         moduleConfig.addActionConfig(mapping);
    137 
    138         // Form Bean "dynamic" is a DynaActionForm with the same properties
    139         formBean =
    140             new ActionFormBean("dynamic",
    141                 "org.apache.struts.action.DynaActionForm");
    142         formBean.addFormPropertyConfig(new FormPropertyConfig(
    143                 "booleanProperty", "boolean", "false"));
    144         formBean.addFormPropertyConfig(new FormPropertyConfig(
    145                 "stringProperty", "java.lang.String", null));
    146         moduleConfig.addFormBeanConfig(formBean);
    147 
    148         // Action "/dynamic" uses the "dynamic" form bean in session scope
    149         mapping = new ActionMapping();
    150         mapping.setInput("/dynamic.jsp");
    151         mapping.setName("dynamic");
    152         mapping.setPath("/dynamic");
    153         mapping.setScope("session");
    154         mapping.setType("org.apache.struts.mock.MockAction");
    155         moduleConfig.addActionConfig(mapping);
    156 
    157         // Form Bean "/dynamic0" is a DynaActionForm with initializers
    158         formBean =
    159             new ActionFormBean("dynamic0",
    160                 "org.apache.struts.action.DynaActionForm");
    161         formBean.addFormPropertyConfig(new FormPropertyConfig(
    162                 "booleanProperty", "boolean", "true"));
    163         formBean.addFormPropertyConfig(new FormPropertyConfig(
    164                 "stringProperty", "java.lang.String", "String Property"));
    165         formBean.addFormPropertyConfig(new FormPropertyConfig("intArray1",
    166                 "int[]", "{1,2,3}", 4)); // 4 should be ignored
    167         formBean.addFormPropertyConfig(new FormPropertyConfig("intArray2",
    168                 "int[]", null, 5)); // 5 should be respected
    169         formBean.addFormPropertyConfig(new FormPropertyConfig("principal",
    170                 "org.apache.struts.mock.MockPrincipal", null));
    171         formBean.addFormPropertyConfig(new FormPropertyConfig("stringArray1",
    172                 "java.lang.String[]", "{aaa,bbb,ccc}", 2)); // 2 should be ignored
    173         formBean.addFormPropertyConfig(new FormPropertyConfig("stringArray2",
    174                 "java.lang.String[]", null, 3)); // 3 should be respected
    175         moduleConfig.addFormBeanConfig(formBean);
    176 
    177         // Action "/dynamic0" uses the "dynamic0" form bean in request scope
    178         mapping = new ActionMapping();
    179         mapping.setName("dynamic0");
    180         mapping.setPath("/dynamic0");
    181         mapping.setScope("request");
    182         mapping.setType("org.apache.struts.mock.MockAction");
    183         moduleConfig.addActionConfig(mapping);
    184 
    185         // Action "/noform" has no form bean associated with it
    186         mapping = new ActionMapping();
    187         mapping.setPath("/noform");
    188         mapping.setType("org.apache.struts.mock.MockAction");
    189         moduleConfig.addActionConfig(mapping);
    190 
    191         // Configure global forward declarations
    192         moduleConfig.addForwardConfig(new ForwardConfig("moduleForward",
    193                 "/module/forward", false)); // No redirect, same module
    194 
    195         moduleConfig.addForwardConfig(new ForwardConfig("moduleRedirect",
    196                 "/module/redirect", true)); // Redirect, same module
    197 
    198         moduleConfig.addForwardConfig(new ForwardConfig("contextForward",
    199                 "/forward", false, // No redirect
    200                 "/context")); // Specify module
    201 
    202         moduleConfig.addForwardConfig(new ForwardConfig("contextRedirect",
    203                 "/redirect", true, // Redirect
    204                 "/context")); // Specify module
    205 
    206         moduleConfig.addForwardConfig(new ForwardConfig("moduleNoslash",
    207                 "module/noslash", false)); // No redirect, same module
    208 
    209         moduleConfig.addForwardConfig(new ForwardConfig("contextNoslash",
    210                 "noslash", false, // No redirect
    211                 "/context")); // Specify module
    212     }
    213 
    214     protected void setUpSecondApp() {
    215         ActionFormBean formBean = null;
    216         ActionMapping mapping = null;
    217 
    218         ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    219 
    220         moduleConfig2 = factoryObject.createModuleConfig("/2");
    221 
    222         context.setAttribute(Globals.MODULE_KEY + "/2", moduleConfig2);
    223 
    224         // Forward "external" to "http://jakarta.apache.org/"
    225         moduleConfig2.addForwardConfig(new ActionForward("external",
    226                 "http://jakarta.apache.org/", false));
    227 
    228         // Forward "foo" to "/baz.jsp" (different from default)
    229         moduleConfig2.addForwardConfig(new ActionForward("foo", "/baz.jsp",
    230                 false));
    231 
    232         // Forward "relative1" to "relative.jsp" non-context-relative
    233         moduleConfig2.addForwardConfig(new ActionForward("relative1",
    234                 "relative.jsp", false));
    235 
    236         // Forward "relative2" to "relative.jsp" context-relative
    237         moduleConfig2.addForwardConfig(new ActionForward("relative2",
    238                 "relative.jsp", false));
    239 
    240         // Form Bean "static" is a standard ActionForm subclass (same as default)
    241         formBean =
    242             new ActionFormBean("static", "org.apache.struts.mock.MockFormBean");
    243         moduleConfig2.addFormBeanConfig(formBean);
    244 
    245         // Action "/static" uses the "static" form bean in request scope (same as default)
    246         mapping = new ActionMapping();
    247         mapping.setInput("/static.jsp");
    248         mapping.setName("static");
    249         mapping.setPath("/static");
    250         mapping.setScope("request");
    251         mapping.setType("org.apache.struts.mock.MockAction");
    252         moduleConfig2.addActionConfig(mapping);
    253 
    254         // Form Bean "dynamic2" is a DynaActionForm with the same properties
    255         formBean =
    256             new ActionFormBean("dynamic2",
    257                 "org.apache.struts.action.DynaActionForm");
    258         formBean.addFormPropertyConfig(new FormPropertyConfig(
    259                 "booleanProperty", "boolean", "false"));
    260         formBean.addFormPropertyConfig(new FormPropertyConfig(
    261                 "stringProperty", "java.lang.String", null));
    262         moduleConfig2.addFormBeanConfig(formBean);
    263 
    264         // Action "/dynamic2" uses the "dynamic2" form bean in session scope
    265         mapping = new ActionMapping();
    266         mapping.setInput("/dynamic2.jsp");
    267         mapping.setName("dynamic2");
    268         mapping.setPath("/dynamic2");
    269         mapping.setScope("session");
    270         mapping.setType("org.apache.struts.mock.MockAction");
    271         moduleConfig2.addActionConfig(mapping);
    272 
    273         // Action "/noform" has no form bean associated with it (same as default)
    274         mapping = new ActionMapping();
    275         mapping.setPath("/noform");
    276         mapping.setType("org.apache.struts.mock.MockAction");
    277         moduleConfig2.addActionConfig(mapping);
    278 
    279         // Configure global forward declarations
    280         moduleConfig2.addForwardConfig(new ForwardConfig("moduleForward",
    281                 "/module/forward", false)); // No redirect, same module
    282 
    283         moduleConfig2.addForwardConfig(new ForwardConfig("moduleRedirect",
    284                 "/module/redirect", true)); // Redirect, same module
    285 
    286         moduleConfig2.addForwardConfig(new ForwardConfig("contextForward",
    287                 "/forward", false, // No redirect
    288                 "/context")); // Specify module
    289 
    290         moduleConfig2.addForwardConfig(new ForwardConfig("contextRedirect",
    291                 "/redirect", true, // Redirect
    292                 "/context")); // Specify module
    293 
    294         moduleConfig2.addForwardConfig(new ForwardConfig("moduleNoslash",
    295                 "module/noslash", false)); // No redirect, same module
    296 
    297         moduleConfig2.addForwardConfig(new ForwardConfig("contextNoslash",
    298                 "noslash", false, // No redirect
    299                 "/context")); // Specify module
    300     }
    301 
    302     // Set up third app for testing URL mapping
    303     protected void setUpThirdApp() {
    304         ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    305 
    306         moduleConfig3 = factoryObject.createModuleConfig("/3");
    307 
    308         context.setAttribute(Globals.MODULE_KEY + "/3", moduleConfig3);
    309 
    310         // Instantiate the controller configuration for this app
    311         ControllerConfig controller = new ControllerConfig();
    312 
    313         moduleConfig3.setControllerConfig(controller);
    314 
    315         // Configure the properties we will be testing
    316         controller.setForwardPattern("/forwarding$M$P");
    317         controller.setInputForward(true);
    318         controller.setPagePattern("/paging$M$P");
    319 
    320         // Configure global forward declarations
    321         moduleConfig3.addForwardConfig(new ForwardConfig("moduleForward",
    322                 "/module/forward", false)); // No redirect, same module
    323 
    324         moduleConfig3.addForwardConfig(new ForwardConfig("moduleRedirect",
    325                 "/module/redirect", true)); // Redirect, same module
    326 
    327         moduleConfig3.addForwardConfig(new ForwardConfig("contextForward",
    328                 "/forward", false, // No redirect
    329                 "/context")); // Specify module
    330 
    331         moduleConfig3.addForwardConfig(new ForwardConfig("contextRedirect",
    332                 "/redirect", true, // Redirect
    333                 "/context")); // Specify module
    334 
    335         moduleConfig3.addForwardConfig(new ForwardConfig("moduleNoslash",
    336                 "module/noslash", false)); // No redirect, same module
    337 
    338         moduleConfig3.addForwardConfig(new ForwardConfig("contextNoslash",
    339                 "noslash", false, // No redirect
    340                 "/context")); // specify module
    341     }
    342 
    343     public void tearDown() {
    344         moduleConfig3 = null;
    345         moduleConfig2 = null;
    346         moduleConfig = null;
    347         config = null;
    348         context = null;
    349         page = null;
    350         principal = null;
    351         request = null;
    352         response = null;
    353         session = null;
    354     }
    355 
    356     // ------------------------------------------------------- Individual Tests
    357     // Test the basic setup of the mock object environment
    358     public void testUtilBaseEnvironment() {
    359         // Validate the servlet API objects and inter-relationships
    360         assertNotNull("config is present", config);
    361         assertNotNull("context is present", context);
    362         assertNotNull("page is present", page);
    363         assertNotNull("principal is present", principal);
    364         assertNotNull("request is present", request);
    365         assertNotNull("response is present", response);
    366         assertNotNull("session is present", session);
    367         assertEquals("page-->config", config, page.getServletConfig());
    368         assertEquals("config-->context", context, config.getServletContext());
    369         assertEquals("page-->context", context, page.getServletContext());
    370         assertEquals("page-->request", request, page.getRequest());
    371         assertEquals("page-->response", response, page.getResponse());
    372         assertEquals("page-->session", session, page.getSession());
    373         assertEquals("request-->principal", principal,
    374             request.getUserPrincipal());
    375         assertEquals("request-->session", session, request.getSession());
    376         assertEquals("session-->context", context, session.getServletContext());
    377 
    378         // Validate the configuration for the default module
    379         assertNotNull("moduleConfig is present", moduleConfig);
    380         assertEquals("context-->moduleConfig", moduleConfig,
    381             context.getAttribute(Globals.MODULE_KEY));
    382 
    383         // Validate the configuration for the second module
    384         assertNotNull("moduleConfig2 is present", moduleConfig2);
    385         assertEquals("context-->moduleConfig2", moduleConfig2,
    386             context.getAttribute(Globals.MODULE_KEY + "/2"));
    387     }
    388 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
