
    1   /*
    2    * $Id: TestRequestUtils.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import junit.framework.Test;
    24  import junit.framework.TestSuite;
    25  
    26  import org.apache.struts.Globals;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionMapping;
    29  import org.apache.struts.action.DynaActionForm;
    30  import org.apache.struts.action.RequestProcessor;
    31  import org.apache.struts.config.ForwardConfig;
    32  import org.apache.struts.config.ModuleConfig;
    33  import org.apache.struts.mock.MockFormBean;
    34  import org.apache.struts.mock.MockPrincipal;
    35  import org.apache.struts.mock.TestMockBase;
    36  
    37  import java.net.MalformedURLException;
    38  
    39  /**
    40   * <p>Unit tests for <code>org.apache.struts.util.RequestUtils</code>.</p>
    41   *
    42   * @version $Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005)
    43   *          $
    44   */
    45  public class TestRequestUtils extends TestMockBase {
    46      // ----------------------------------------------------------------- Basics
    47      public TestRequestUtils(String name) {
    48          super(name);
    49      }
    50  
    51      public static void main(String[] args) {
    52          junit.awtui.TestRunner.main(new String[] {
    53                  TestRequestUtils.class.getName()
    54              });
    55      }
    56  
    57      public static Test suite() {
    58          return (new TestSuite(TestRequestUtils.class));
    59      }
    60  
    61      // ----------------------------------------------------- Instance Variables
    62      // ----------------------------------------------------- Setup and Teardown
    63      public void setUp() {
    64          super.setUp();
    65      }
    66  
    67      public void tearDown() {
    68          super.tearDown();
    69      }
    70  
    71      // ------------------------------------------------------- Individual Tests
    72      // ---------------------------------------------------------- absoluteURL()
    73      public void testAbsoluteURL() {
    74          request.setPathElements("/myapp", "/action.do", null, null);
    75  
    76          String url = null;
    77  
    78          try {
    79              url = RequestUtils.absoluteURL(request, "/foo/bar.jsp").toString();
    80              assertEquals("absoluteURL is correct",
    81                  "http://localhost:8080/myapp/foo/bar.jsp", url);
    82          } catch (MalformedURLException e) {
    83              fail("Threw MalformedURLException: " + e);
    84          }
    85      }
    86  
    87      // ------------------------------------------------------------ actionURL()
    88      // Default application -- extension mapping
    89      public void testActionURL1() {
    90          request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    91          request.setPathElements("/myapp", "/foo.do", null, null);
    92  
    93          String url =
    94              RequestUtils.actionURL(request,
    95                  moduleConfig.findActionConfig("/dynamic"), "*.do");
    96  
    97          assertNotNull("URL was returned", url);
    98          assertEquals("URL value", "/dynamic.do", url);
    99      }
    100 
    101     // Second application -- extension mapping
    102     public void testActionURL2() {
    103         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    104         request.setPathElements("/myapp", "/2/foo.do", null, null);
    105 
    106         String url =
    107             RequestUtils.actionURL(request,
    108                 moduleConfig2.findActionConfig("/dynamic2"), "*.do");
    109 
    110         assertNotNull("URL was returned", url);
    111         assertEquals("URL value", "/2/dynamic2.do", url);
    112     }
    113 
    114     // Default application -- path mapping
    115     public void testActionURL3() {
    116         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    117         request.setPathElements("/myapp", "/do/foo", null, null);
    118 
    119         String url =
    120             RequestUtils.actionURL(request,
    121                 moduleConfig.findActionConfig("/dynamic"), "/do/*");
    122 
    123         assertNotNull("URL was returned", url);
    124         assertEquals("URL value", "/do/dynamic", url);
    125     }
    126 
    127     // ----------------------------------------------------- createActionForm()
    128     // Default module -- No ActionForm should be created
    129     public void testCreateActionForm1a() {
    130         request.setPathElements("/myapp", "/noform.do", null, null);
    131 
    132         ActionMapping mapping =
    133             (ActionMapping) moduleConfig.findActionConfig("/noform");
    134 
    135         assertNotNull("Found /noform mapping", mapping);
    136 
    137         ActionForm form =
    138             RequestUtils.createActionForm(request, mapping, moduleConfig, null);
    139 
    140         assertNull("No ActionForm returned", form);
    141     }
    142 
    143     // Second module -- No ActionForm should be created
    144     public void testCreateActionForm1b() {
    145         request.setPathElements("/myapp", "/2/noform.do", null, null);
    146 
    147         ActionMapping mapping =
    148             (ActionMapping) moduleConfig2.findActionConfig("/noform");
    149 
    150         assertNotNull("Found /noform mapping", mapping);
    151 
    152         ActionForm form =
    153             RequestUtils.createActionForm(request, mapping, moduleConfig2, null);
    154 
    155         assertNull("No ActionForm returned", form);
    156     }
    157 
    158     // Default module -- Standard ActionForm should be created
    159     public void testCreateActionForm2a() {
    160         request.setPathElements("/myapp", "/static.do", null, null);
    161 
    162         ActionMapping mapping =
    163             (ActionMapping) moduleConfig.findActionConfig("/static");
    164 
    165         assertNotNull("Found /static mapping", mapping);
    166         assertNotNull("Mapping has non-null name", mapping.getName());
    167         assertEquals("Mapping has correct name", "static", mapping.getName());
    168         assertNotNull("AppConfig has form bean " + mapping.getName(),
    169             moduleConfig.findFormBeanConfig(mapping.getName()));
    170 
    171         ActionForm form =
    172             RequestUtils.createActionForm(request, mapping, moduleConfig, null);
    173 
    174         assertNotNull("ActionForm returned", form);
    175         assertTrue("ActionForm of correct type", form instanceof MockFormBean);
    176     }
    177 
    178     // Second module -- Standard ActionForm should be created
    179     public void testCreateActionForm2b() {
    180         request.setPathElements("/myapp", "/2/static.do", null, null);
    181 
    182         ActionMapping mapping =
    183             (ActionMapping) moduleConfig2.findActionConfig("/static");
    184 
    185         assertNotNull("Found /static mapping", mapping);
    186         assertNotNull("Mapping has non-null name", mapping.getName());
    187         assertEquals("Mapping has correct name", "static", mapping.getName());
    188         assertNotNull("AppConfig has form bean " + mapping.getName(),
    189             moduleConfig.findFormBeanConfig(mapping.getName()));
    190 
    191         ActionForm form =
    192             RequestUtils.createActionForm(request, mapping, moduleConfig2, null);
    193 
    194         assertNotNull("ActionForm returned", form);
    195         assertTrue("ActionForm of correct type", form instanceof MockFormBean);
    196     }
    197 
    198     // Default module -- Dynamic ActionForm should be created
    199     public void testCreateActionForm3a() {
    200         request.setPathElements("/myapp", "/dynamic.do", null, null);
    201 
    202         ActionMapping mapping =
    203             (ActionMapping) moduleConfig.findActionConfig("/dynamic");
    204 
    205         assertNotNull("Found /dynamic mapping", mapping);
    206         assertNotNull("Mapping has non-null name", mapping.getName());
    207         assertEquals("Mapping has correct name", "dynamic", mapping.getName());
    208         assertNotNull("AppConfig has form bean " + mapping.getName(),
    209             moduleConfig.findFormBeanConfig(mapping.getName()));
    210 
    211         ActionForm form =
    212             RequestUtils.createActionForm(request, mapping, moduleConfig, null);
    213 
    214         assertNotNull("ActionForm returned", form);
    215         assertTrue("ActionForm of correct type", form instanceof DynaActionForm);
    216     }
    217 
    218     // Second module -- Dynamic ActionForm should be created
    219     public void testCreateActionForm3b() {
    220         request.setPathElements("/myapp", "/2/dynamic2.do", null, null);
    221 
    222         ActionMapping mapping =
    223             (ActionMapping) moduleConfig2.findActionConfig("/dynamic2");
    224 
    225         assertNotNull("Found /dynamic2 mapping", mapping);
    226         assertNotNull("Mapping has non-null name", mapping.getName());
    227         assertEquals("Mapping has correct name", "dynamic2", mapping.getName());
    228         assertNotNull("AppConfig has form bean " + mapping.getName(),
    229             moduleConfig2.findFormBeanConfig(mapping.getName()));
    230 
    231         ActionForm form =
    232             RequestUtils.createActionForm(request, mapping, moduleConfig2, null);
    233 
    234         assertNotNull("ActionForm returned", form);
    235         assertTrue("ActionForm of correct type", form instanceof DynaActionForm);
    236     }
    237 
    238     // Default module -- Dynamic ActionForm with initializers
    239     public void testCreateActionForm4a() {
    240         // Retrieve an appropriately configured DynaActionForm instance
    241         request.setPathElements("/myapp", "/dynamic0.do", null, null);
    242 
    243         ActionMapping mapping =
    244             (ActionMapping) moduleConfig.findActionConfig("/dynamic0");
    245 
    246         assertNotNull("Found /dynamic0 mapping", mapping);
    247         assertNotNull("Mapping has non-null name", mapping.getName());
    248         assertEquals("Mapping has correct name", "dynamic0", mapping.getName());
    249         assertNotNull("AppConfig has form bean " + mapping.getName(),
    250             moduleConfig.findFormBeanConfig(mapping.getName()));
    251 
    252         ActionForm form =
    253             RequestUtils.createActionForm(request, mapping, moduleConfig, null);
    254 
    255         assertNotNull("ActionForm returned", form);
    256         assertTrue("ActionForm of correct type", form instanceof DynaActionForm);
    257 
    258         // Validate the property values
    259         DynaActionForm dform = (DynaActionForm) form;
    260         Boolean booleanProperty = (Boolean) dform.get("booleanProperty");
    261 
    262         assertTrue("booleanProperty is true", booleanProperty.booleanValue());
    263 
    264         String stringProperty = (String) dform.get("stringProperty");
    265 
    266         assertEquals("stringProperty is correct", "String Property",
    267             stringProperty);
    268 
    269         Object value = null;
    270 
    271         value = dform.get("intArray1");
    272         assertNotNull("intArray1 exists", value);
    273         assertTrue("intArray1 is int[]", value instanceof int[]);
    274 
    275         int[] intArray1 = (int[]) value;
    276 
    277         assertEquals("intArray1 length is correct", 3, intArray1.length);
    278         assertEquals("intArray1[0] value is correct", 1, intArray1[0]);
    279         assertEquals("intArray1[1] value is correct", 2, intArray1[1]);
    280         assertEquals("intArray1[2] value is correct", 3, intArray1[2]);
    281 
    282         value = dform.get("intArray2");
    283         assertNotNull("intArray2 exists", value);
    284         assertTrue("intArray2 is int[]", value instanceof int[]);
    285 
    286         int[] intArray2 = (int[]) value;
    287 
    288         assertEquals("intArray2 length is correct", 5, intArray2.length);
    289         assertEquals("intArray2[0] value is correct", 0, intArray2[0]);
    290         assertEquals("intArray2[1] value is correct", 0, intArray2[1]);
    291         assertEquals("intArray2[2] value is correct", 0, intArray2[2]);
    292         assertEquals("intArray2[3] value is correct", 0, intArray2[3]);
    293         assertEquals("intArray2[4] value is correct", 0, intArray2[4]);
    294 
    295         value = dform.get("principal");
    296         assertNotNull("principal exists", value);
    297         assertTrue("principal is MockPrincipal", value instanceof MockPrincipal);
    298 
    299         value = dform.get("stringArray1");
    300         assertNotNull("stringArray1 exists", value);
    301         assertTrue("stringArray1 is int[]", value instanceof String[]);
    302 
    303         String[] stringArray1 = (String[]) value;
    304 
    305         assertEquals("stringArray1 length is correct", 3, stringArray1.length);
    306         assertEquals("stringArray1[0] value is correct", "aaa", stringArray1[0]);
    307         assertEquals("stringArray1[1] value is correct", "bbb", stringArray1[1]);
    308         assertEquals("stringArray1[2] value is correct", "ccc", stringArray1[2]);
    309 
    310         value = dform.get("stringArray2");
    311         assertNotNull("stringArray2 exists", value);
    312         assertTrue("stringArray2 is int[]", value instanceof String[]);
    313 
    314         String[] stringArray2 = (String[]) value;
    315 
    316         assertEquals("stringArray2 length is correct", 3, stringArray2.length);
    317         assertEquals("stringArray2[0] value is correct", new String(),
    318             stringArray2[0]);
    319         assertEquals("stringArray2[1] value is correct", new String(),
    320             stringArray2[1]);
    321         assertEquals("stringArray2[2] value is correct", new String(),
    322             stringArray2[2]);
    323 
    324         // Different form beans should get different property value instances
    325         Object value1 = null;
    326         DynaActionForm dform1 =
    327             (DynaActionForm) RequestUtils.createActionForm(request, mapping,
    328                 moduleConfig, null);
    329 
    330         value = dform.get("principal");
    331         value1 = dform1.get("principal");
    332         assertEquals("Different form beans get equal instance values", value,
    333             value1);
    334         assertTrue("Different form beans get different instances 1",
    335             value != value1);
    336 
    337         value = dform.get("stringArray1");
    338         value1 = dform1.get("stringArray1");
    339         assertTrue("Different form beans get different instances 2",
    340             value != value1);
    341 
    342         dform1.set("stringProperty", "Different stringProperty value");
    343         value = dform.get("stringProperty");
    344         value1 = dform1.get("stringProperty");
    345         assertTrue("Different form beans get different instances 3",
    346             value != value1);
    347     }
    348 
    349     // ----------------------------------------------------------- forwardURL()
    350     // Default module (default forwardPattern)
    351     public void testForwardURL1() {
    352         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    353         request.setPathElements("/myapp", "/action.do", null, null);
    354 
    355         ForwardConfig forward = null;
    356         String result = null;
    357 
    358         // redirect=false, module=null
    359         forward = moduleConfig.findForwardConfig("moduleForward");
    360         assertNotNull("moduleForward found", forward);
    361         result = RequestUtils.forwardURL(request, forward, null);
    362         assertNotNull("moduleForward computed", result);
    363         assertEquals("moduleForward value", "/module/forward", result);
    364 
    365         // redirect=true, module=null
    366         forward = moduleConfig.findForwardConfig("moduleRedirect");
    367         assertNotNull("moduleRedirect found", forward);
    368         result = RequestUtils.forwardURL(request, forward, null);
    369         assertNotNull("moduleRedirect computed", result);
    370         assertEquals("moduleRedirect value", "/module/redirect", result);
    371 
    372         // redirect=false, module=/context
    373         forward = moduleConfig.findForwardConfig("contextForward");
    374         assertNotNull("contextForward found", forward);
    375         result = RequestUtils.forwardURL(request, forward, null);
    376         assertNotNull("contextForward computed", result);
    377         assertEquals("contextForward value", "/context/forward", result);
    378 
    379         // redirect=true, module=/context
    380         forward = moduleConfig.findForwardConfig("contextRedirect");
    381         assertNotNull("contextRedirect found", forward);
    382         result = RequestUtils.forwardURL(request, forward, null);
    383         assertNotNull("contextRedirect computed", result);
    384         assertEquals("contextRedirct value", "/context/redirect", result);
    385 
    386         // noslash, module=null
    387         forward = moduleConfig.findForwardConfig("moduleNoslash");
    388         assertNotNull("moduleNoslash found", forward);
    389         result = RequestUtils.forwardURL(request, forward, null);
    390         assertNotNull("moduleNoslash computed", result);
    391         assertEquals("moduleNoslash value", "/module/noslash", result);
    392 
    393         // noslash, module=/
    394         forward = moduleConfig.findForwardConfig("contextNoslash");
    395         assertNotNull("contextNoslash found", forward);
    396         result = RequestUtils.forwardURL(request, forward, null);
    397         assertNotNull("contextNoslash computed", result);
    398         assertEquals("contextNoslash value", "/context/noslash", result);
    399     }
    400 
    401     // Second module (default forwardPattern)
    402     public void testForwardURL2() {
    403         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    404         request.setPathElements("/myapp", "/2/action.do", null, null);
    405 
    406         ForwardConfig forward = null;
    407         String result = null;
    408 
    409         // redirect=false, module=null
    410         forward = moduleConfig2.findForwardConfig("moduleForward");
    411         assertNotNull("moduleForward found", forward);
    412         result = RequestUtils.forwardURL(request, forward, null);
    413         assertNotNull("moduleForward computed", result);
    414         assertEquals("moduleForward value", "/2/module/forward", result);
    415 
    416         // redirect=true, module=null
    417         forward = moduleConfig2.findForwardConfig("moduleRedirect");
    418         assertNotNull("moduleRedirect found", forward);
    419         result = RequestUtils.forwardURL(request, forward, null);
    420         assertNotNull("moduleRedirect computed", result);
    421         assertEquals("moduleRedirect value", "/2/module/redirect", result);
    422 
    423         // redirect=false, module=/context
    424         forward = moduleConfig2.findForwardConfig("contextForward");
    425         assertNotNull("contextForward found", forward);
    426         result = RequestUtils.forwardURL(request, forward, null);
    427         assertNotNull("contextForward computed", result);
    428         assertEquals("contextForward value", "/context/forward", result);
    429 
    430         // redirect=true, module=/context
    431         forward = moduleConfig2.findForwardConfig("contextRedirect");
    432         assertNotNull("contextRedirect found", forward);
    433         result = RequestUtils.forwardURL(request, forward, null);
    434         assertNotNull("contextRedirect computed", result);
    435         assertEquals("contextRedirct value", "/context/redirect", result);
    436 
    437         // noslash, module=null
    438         forward = moduleConfig2.findForwardConfig("moduleNoslash");
    439         assertNotNull("moduleNoslash found", forward);
    440         result = RequestUtils.forwardURL(request, forward, null);
    441         assertNotNull("moduleNoslash computed", result);
    442         assertEquals("moduleNoslash value", "/2/module/noslash", result);
    443 
    444         // noslash, module=/
    445         forward = moduleConfig2.findForwardConfig("contextNoslash");
    446         assertNotNull("contextNoslash found", forward);
    447         result = RequestUtils.forwardURL(request, forward, null);
    448         assertNotNull("contextNoslash computed", result);
    449         assertEquals("contextNoslash value", "/context/noslash", result);
    450     }
    451 
    452     // Third module (custom forwardPattern)
    453     public void testForwardURL3() {
    454         request.setAttribute(Globals.MODULE_KEY, moduleConfig3);
    455         request.setPathElements("/myapp", "/3/action.do", null, null);
    456 
    457         ForwardConfig forward = null;
    458         String result = null;
    459 
    460         // redirect=false, module=null
    461         forward = moduleConfig3.findForwardConfig("moduleForward");
    462         assertNotNull("moduleForward found", forward);
    463         result = RequestUtils.forwardURL(request, forward, null);
    464         assertNotNull("moduleForward computed", result);
    465         assertEquals("moduleForward value", "/forwarding/3/module/forward",
    466             result);
    467 
    468         // redirect=true, module=null
    469         forward = moduleConfig3.findForwardConfig("moduleRedirect");
    470         assertNotNull("moduleRedirect found", forward);
    471         result = RequestUtils.forwardURL(request, forward, null);
    472         assertNotNull("moduleRedirect computed", result);
    473         assertEquals("moduleRedirect value", "/forwarding/3/module/redirect",
    474             result);
    475 
    476         // redirect=false, module=/context
    477         forward = moduleConfig3.findForwardConfig("contextForward");
    478         assertNotNull("contextForward found", forward);
    479         result = RequestUtils.forwardURL(request, forward, null);
    480         assertNotNull("contextForward computed", result);
    481         assertEquals("contextForward value", "/forwarding/context/forward",
    482             result);
    483 
    484         // redirect=true, module=/context
    485         forward = moduleConfig3.findForwardConfig("contextRedirect");
    486         assertNotNull("contextRedirect found", forward);
    487         result = RequestUtils.forwardURL(request, forward, null);
    488         assertNotNull("contextRedirect computed", result);
    489         assertEquals("contextRedirct value", "/forwarding/context/redirect",
    490             result);
    491 
    492         // noslash, module=null
    493         forward = moduleConfig3.findForwardConfig("moduleNoslash");
    494         assertNotNull("moduleNoslash found", forward);
    495         result = RequestUtils.forwardURL(request, forward, null);
    496         assertNotNull("moduleNoslash computed", result);
    497         assertEquals("moduleNoslash value", "/forwarding/3/module/noslash",
    498             result);
    499 
    500         // noslash, module=/
    501         forward = moduleConfig3.findForwardConfig("contextNoslash");
    502         assertNotNull("contextNoslash found", forward);
    503         result = RequestUtils.forwardURL(request, forward, null);
    504         assertNotNull("contextNoslash computed", result);
    505         assertEquals("contextNoslash value", "/forwarding/context/noslash",
    506             result);
    507     }
    508 
    509     // Cross module forwards
    510     public void testForwardURLa() {
    511         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    512         request.setPathElements("/myapp", "/action.do", null, null);
    513 
    514         ForwardConfig forward = null;
    515         String result = null;
    516 
    517         // redirect=false, contextRelative=false, link to module 3
    518         forward = moduleConfig3.findForwardConfig("moduleForward");
    519         assertNotNull("moduleForward found", forward);
    520         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    521         assertNotNull("moduleForward computed", result);
    522         assertEquals("moduleForward value", "/forwarding/3/module/forward",
    523             result);
    524 
    525         // redirect=true, contextRelative=false, link to module 3
    526         forward = moduleConfig3.findForwardConfig("moduleRedirect");
    527         assertNotNull("moduleRedirect found", forward);
    528         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    529         assertNotNull("moduleRedirect computed", result);
    530         assertEquals("moduleRedirect value", "/forwarding/3/module/redirect",
    531             result);
    532 
    533         // redirect=false, module=/context
    534         forward = moduleConfig3.findForwardConfig("contextForward");
    535         assertNotNull("contextForward found", forward);
    536         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    537         assertNotNull("contextForward computed", result);
    538         assertEquals("contextForward value", "/forwarding/context/forward",
    539             result);
    540 
    541         // redirect=true, module=/context
    542         forward = moduleConfig3.findForwardConfig("contextRedirect");
    543         assertNotNull("contextRedirect found", forward);
    544         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    545         assertNotNull("contextRedirect computed", result);
    546         assertEquals("contextRedirct value", "/forwarding/context/redirect",
    547             result);
    548 
    549         // noslash, contextRelative=false, link to module 3
    550         forward = moduleConfig3.findForwardConfig("moduleNoslash");
    551         assertNotNull("moduleNoslash found", forward);
    552         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    553         assertNotNull("moduleNoslash computed", result);
    554         assertEquals("moduleNoslash value", "/forwarding/3/module/noslash",
    555             result);
    556 
    557         // noslash, module=/
    558         forward = moduleConfig3.findForwardConfig("contextNoslash");
    559         assertNotNull("contextNoslash found", forward);
    560         result = RequestUtils.forwardURL(request, forward, moduleConfig3);
    561         assertNotNull("contextNoslash computed", result);
    562         assertEquals("contextNoslash value", "/forwarding/context/noslash",
    563             result);
    564     }
    565 
    566     // ----------------------------------------------------------- requestURL()
    567     public void testRequestURL() {
    568         request.setPathElements("/myapp", "/foo.do", null, null);
    569 
    570         String url = null;
    571 
    572         try {
    573             url = RequestUtils.requestURL(request).toString();
    574         } catch (MalformedURLException e) {
    575             fail("MalformedURLException: " + e);
    576         }
    577 
    578         assertNotNull("URL was returned", url);
    579         assertEquals("URL value", "http://localhost:8080/myapp/foo.do", url);
    580     }
    581 
    582     // ---------------------------------------------------- selectApplication()
    583     // Map to the default module -- direct
    584     public void testSelectApplication1a() {
    585         request.setPathElements("/myapp", "/noform.do", null, null);
    586         ModuleUtils.getInstance().selectModule(request, context);
    587 
    588         ModuleConfig moduleConfig =
    589             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    590 
    591         assertNotNull("Selected a module", moduleConfig);
    592         assertEquals("Selected correct module", "", moduleConfig.getPrefix());
    593 
    594         // FIXME - check module resources?
    595     }
    596 
    597     // Map to the second module -- direct
    598     public void testSelectApplication1b() {
    599         String[] prefixes = { "/1", "/2" };
    600 
    601         context.setAttribute(Globals.MODULE_PREFIXES_KEY, prefixes);
    602         request.setPathElements("/myapp", "/2/noform.do", null, null);
    603 
    604         ModuleUtils.getInstance().selectModule(request, context);
    605 
    606         ModuleConfig moduleConfig =
    607             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    608 
    609         assertNotNull("Selected a module", moduleConfig);
    610         assertEquals("Selected correct module", "/2", moduleConfig.getPrefix());
    611 
    612         // FIXME - check module resources?
    613     }
    614 
    615     // Map to the default module -- include
    616     public void testSelectApplication2a() {
    617         request.setPathElements("/myapp", "/2/noform.do", null, null);
    618         request.setAttribute(RequestProcessor.INCLUDE_SERVLET_PATH, "/noform.do");
    619         ModuleUtils.getInstance().selectModule(request, context);
    620 
    621         ModuleConfig moduleConfig =
    622             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    623 
    624         assertNotNull("Selected an application", moduleConfig);
    625         assertEquals("Selected correct application", "",
    626             moduleConfig.getPrefix());
    627 
    628         // FIXME - check application resources?
    629     }
    630 
    631     // Map to the second module -- include
    632     public void testSelectApplication2b() {
    633         String[] prefixes = { "/1", "/2" };
    634 
    635         context.setAttribute(Globals.MODULE_PREFIXES_KEY, prefixes);
    636         request.setPathElements("/myapp", "/noform.do", null, null);
    637         request.setAttribute(RequestProcessor.INCLUDE_SERVLET_PATH,
    638             "/2/noform.do");
    639         ModuleUtils.getInstance().selectModule(request, context);
    640 
    641         ModuleConfig moduleConfig =
    642             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    643 
    644         assertNotNull("Selected a module", moduleConfig);
    645         assertEquals("Selected correct module", "/2", moduleConfig.getPrefix());
    646 
    647         // FIXME - check application resources?
    648     }
    649 
    650     // ------------------------------------------------------------ serverURL()
    651     // Basic test on values in mock objects
    652     public void testServerURL() {
    653         String url = null;
    654 
    655         try {
    656             url = RequestUtils.serverURL(request).toString();
    657         } catch (MalformedURLException e) {
    658             fail("Threw MalformedURLException: " + e);
    659         }
    660 
    661         assertNotNull("serverURL is present", url);
    662         assertEquals("serverURL value", "http://localhost:8080", url);
    663     }
    664 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
