
    1   /*
    2    * $Id: $
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
    21  package org.apache.struts.taglib;
    22  
    23  import junit.framework.Test;
    24  import junit.framework.TestSuite;
    25  
    26  import org.apache.commons.logging.Log;
    27  import org.apache.commons.logging.LogFactory;
    28  import org.apache.struts.Globals;
    29  import org.apache.struts.action.ActionMessage;
    30  import org.apache.struts.action.ActionMessages;
    31  import org.apache.struts.config.ActionConfig;
    32  import org.apache.struts.config.ModuleConfig;
    33  import org.apache.struts.config.impl.ModuleConfigImpl;
    34  import org.apache.struts.mock.MockFormBean;
    35  import org.apache.struts.mock.MockHttpServletRequest;
    36  import org.apache.struts.mock.MockHttpServletResponse;
    37  import org.apache.struts.mock.MockPageContext;
    38  import org.apache.struts.mock.MockServletConfig;
    39  import org.apache.struts.mock.MockServletContext;
    40  import org.apache.struts.taglib.html.md.Constants;
    41  
    42  import javax.servlet.jsp.JspException;
    43  import javax.servlet.jsp.PageContext;
    44  
    45  import java.net.MalformedURLException;
    46  
    47  import java.util.HashMap;
    48  import java.util.Iterator;
    49  import java.util.Locale;
    50  import java.util.Map;
    51  
    52  /**
    53   * Unit tests for the TagUtils.
    54   */
    55  public class TestTagUtils extends TagTestBase {
    56      private static final Log log = LogFactory.getLog(TestTagUtils.class);
    57  
    58      /**
    59       * Defines the testcase name for JUnit.
    60       *
    61       * @param theName the testcase's name.
    62       */
    63      public TestTagUtils(String theName) {
    64          super(theName);
    65      }
    66  
    67      /**
    68       * Start the tests.
    69       *
    70       * @param theArgs the arguments. Not used
    71       */
    72      public static void main(String[] theArgs) {
    73          junit.awtui.TestRunner.main(new String[] { TestTagUtils.class.getName() });
    74      }
    75  
    76      /**
    77       * @return a test suite (<code>TestSuite</code>) that includes all methods
    78       *         starting with "test"
    79       */
    80      public static Test suite() {
    81          // All methods starting with "test" will be executed in the test suite.
    82          return new TestSuite(TestTagUtils.class);
    83      }
    84  
    85      /**
    86       * Test Operators.
    87       */
    88      public void testFilter() {
    89          assertNull("Null", null);
    90  
    91          // Test Null
    92          assertNull("Filter Test 1", tagutils.filter(null));
    93  
    94          // Test Empty String
    95          assertEquals("Filter Test 2", "", tagutils.filter(""));
    96  
    97          // Test Single Character
    98          assertEquals("Filter Test 3", "a", tagutils.filter("a"));
    99  
    100         // Test Multiple Characters
    101         assertEquals("Filter Test 4", "adhdfhdfhadhf",
    102             tagutils.filter("adhdfhdfhadhf"));
    103 
    104         // Test Each filtered Character
    105         assertEquals("Filter Test 5", "&lt;", tagutils.filter("<"));
    106         assertEquals("Filter Test 6", "&gt;", tagutils.filter(">"));
    107         assertEquals("Filter Test 7", "&amp;", tagutils.filter("&"));
    108         assertEquals("Filter Test 8", "&quot;", tagutils.filter("\""));
    109         assertEquals("Filter Test 9", "&#39;", tagutils.filter("'"));
    110 
    111         // Test filtering beginning, middle, end
    112         assertEquals("Filter Test 10", "a&lt;", tagutils.filter("a<"));
    113         assertEquals("Filter Test 11", "&lt;a", tagutils.filter("<a"));
    114         assertEquals("Filter Test 12", "a&lt;a", tagutils.filter("a<a"));
    115 
    116         // Test filtering beginning, middle, end
    117         assertEquals("Filter Test 13", "abc&lt;", tagutils.filter("abc<"));
    118         assertEquals("Filter Test 14", "&lt;abc", tagutils.filter("<abc"));
    119         assertEquals("Filter Test 15", "abc&lt;abc", tagutils.filter("abc<abc"));
    120 
    121         // Test Multiple Characters
    122         assertEquals("Filter Test 16",
    123             "&lt;input type=&quot;text&quot; value=&#39;Me &amp; You&#39;&gt;",
    124             tagutils.filter("<input type=\"text\" value='Me & You'>"));
    125     }
    126 
    127     // ---------------------------------------------------- computeParameters()
    128     // No parameters and no transaction token
    129     public void testComputeParameters0a() {
    130         Map map = null;
    131 
    132         try {
    133             map = tagutils.computeParameters(pageContext, null, null, null,
    134                     null, null, null, null, false);
    135         } catch (JspException e) {
    136             fail("JspException: " + e);
    137         }
    138 
    139         assertNull("Map is null", map);
    140     }
    141 
    142     // No parameters but add transaction token
    143     public void testComputeParameters0b() {
    144         request.getSession().setAttribute(Globals.TRANSACTION_TOKEN_KEY, "token");
    145 
    146         Map map = null;
    147 
    148         try {
    149             map = tagutils.computeParameters(pageContext, null, null, null,
    150                     null, null, null, null, true);
    151         } catch (JspException e) {
    152             fail("JspException: " + e);
    153         }
    154 
    155         assertNotNull("Map is not null", map);
    156         assertEquals("One parameter in the returned map", 1, map.size());
    157         assertTrue("Transaction token parameter present",
    158             map.containsKey(Constants.TOKEN_KEY));
    159         assertEquals("Transaction token parameter value", "token",
    160             (String) map.get(Constants.TOKEN_KEY));
    161     }
    162 
    163     // invalid scope name is requested
    164     public void testComputeParametersInvalidScope() {
    165         Map map = null;
    166 
    167         try {
    168             map = tagutils.computeParameters(pageContext, null, null, null,
    169                     "session", "i-do-not-exist", null, null, false);
    170 
    171             fail("JspException not thrown");
    172         } catch (JspException e) {
    173             assertNull("map is null", map);
    174         }
    175     }
    176 
    177     // specified bean is not found
    178     public void testComputeParametersBeanNotFound() {
    179         Map map = null;
    180 
    181         try {
    182             map = tagutils.computeParameters(pageContext, null, null, null,
    183                     null, "i-do-not-exist", null, null, false);
    184 
    185             fail("JspException not thrown");
    186         } catch (JspException e) {
    187             assertNull("map is null", map);
    188         }
    189     }
    190 
    191     // accessing this property causes an exception
    192     public void testComputeParametersPropertyThrowsException() {
    193         request.getSession().setAttribute("SomeBean", new MockFormBean(true));
    194 
    195         Map map = null;
    196 
    197         try {
    198             map = tagutils.computeParameters(pageContext, null, null, null,
    199                     null, "SomeBean", "justThrowAnException", null, false);
    200             fail("JspException not thrown");
    201         } catch (JspException e) {
    202             assertNull("map is null", map);
    203         }
    204     }
    205 
    206     public void testComputeParametersParamIdParamPropThrowException() {
    207         request.getSession().setAttribute("SomeBean", new MockFormBean(true));
    208 
    209         Map map = null;
    210 
    211         try {
    212             map = tagutils.computeParameters(pageContext, "paramId",
    213                     "SomeBean", "justThrowAnException", null, null, null, null,
    214                     false);
    215 
    216             fail("JspException not thrown");
    217         } catch (JspException e) {
    218             assertNull("map is null", map);
    219         }
    220     }
    221 
    222     public void testComputeParametersParamValueToString() {
    223         request.getSession().setAttribute("SomeBean",
    224             new MockFormBean(false, false, new Double(1)));
    225 
    226         Map map = null;
    227 
    228         try {
    229             map = tagutils.computeParameters(pageContext, "paramId",
    230                     "SomeBean", "doubleValue", null, null, null, null, false);
    231 
    232             assertNotNull("map is null", map);
    233 
    234             String val = (String) map.get("paramId");
    235 
    236             assertTrue("paramId should be 1.0", "1.0".equals(val));
    237         } catch (JspException e) {
    238             fail("JspException not thrown");
    239         }
    240     }
    241 
    242     public void skiptestComputeParametersParamIdAsStringArray() {
    243         Map params = new HashMap();
    244 
    245         //        String[] vals = new String[]{"test0, test1"};
    246         params.put("fooParamId", "fooParamValue");
    247 
    248         request.getSession().setAttribute("SomeBean", params);
    249 
    250         Map map = null;
    251 
    252         try {
    253             map = tagutils.computeParameters(pageContext, "fooParamId",
    254                     "SomeBean", null, null, "SomeBean", null, null, false);
    255 
    256             //            map = tagutils.computeParameters(
    257             //                    page, "paramId", "SomeBean", "stringArray", null,
    258             //                    null, null, null, false);
    259             assertNotNull("map is null", map);
    260 
    261             String val = (String) map.get("key0");
    262 
    263             assertTrue("paramId should be \"test\"", "1.0".equals(val));
    264         } catch (JspException e) {
    265             fail("JspException not thrown");
    266         }
    267     }
    268 
    269     // Single parameter -- name
    270     public void testComputeParameters1a() {
    271         request.getSession().setAttribute("attr", "bar");
    272 
    273         Map map = null;
    274 
    275         try {
    276             map = tagutils.computeParameters(pageContext, "foo", "attr", null,
    277                     null, null, null, null, false);
    278         } catch (JspException e) {
    279             fail("JspException: " + e);
    280         }
    281 
    282         assertNotNull("Map is not null", map);
    283         assertEquals("One parameter in the returned map", 1, map.size());
    284         assertTrue("Parameter present", map.containsKey("foo"));
    285         assertEquals("Parameter value", "bar", (String) map.get("foo"));
    286     }
    287 
    288     // Single parameter -- scope + name
    289     public void testComputeParameters1b() {
    290         request.setAttribute("attr", "bar");
    291 
    292         Map map = null;
    293 
    294         try {
    295             map = tagutils.computeParameters(pageContext, "foo", "attr", null,
    296                     "request", null, null, null, false);
    297         } catch (JspException e) {
    298             fail("JspException: " + e);
    299         }
    300 
    301         assertNotNull("Map is not null", map);
    302         assertEquals("One parameter in the returned map", 1, map.size());
    303         assertTrue("Parameter present", map.containsKey("foo"));
    304         assertEquals("Parameter value", "bar", (String) map.get("foo"));
    305     }
    306 
    307     // Single parameter -- scope + name + property
    308     public void testComputeParameters1c() {
    309         request.setAttribute("attr", new MockFormBean("bar"));
    310 
    311         Map map = null;
    312 
    313         try {
    314             map = tagutils.computeParameters(pageContext, "foo", "attr",
    315                     "stringProperty", "request", null, null, null, false);
    316         } catch (JspException e) {
    317             fail("JspException: " + e);
    318         }
    319 
    320         assertNotNull("Map is not null", map);
    321         assertEquals("One parameter in the returned map", 1, map.size());
    322         assertTrue("Parameter present", map.containsKey("foo"));
    323         assertEquals("Parameter value", "bar", (String) map.get("foo"));
    324     }
    325 
    326     // Provided map -- name
    327     public void testComputeParameters2a() {
    328         Map map = new HashMap();
    329 
    330         map.put("foo1", "bar1");
    331         map.put("foo2", "bar2");
    332         request.getSession().setAttribute("attr", map);
    333 
    334         try {
    335             map = tagutils.computeParameters(pageContext, null, null, null,
    336                     null, "attr", null, null, false);
    337         } catch (JspException e) {
    338             fail("JspException: " + e);
    339         }
    340 
    341         assertNotNull("Map is not null", map);
    342         assertEquals("Two parameter in the returned map", 2, map.size());
    343         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    344         assertEquals("Parameter foo1 value", "bar1", (String) map.get("foo1"));
    345         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    346         assertEquals("Parameter foo2 value", "bar2", (String) map.get("foo2"));
    347     }
    348 
    349     // Provided map -- scope + name
    350     public void testComputeParameters2b() {
    351         Map map = new HashMap();
    352 
    353         map.put("foo1", "bar1");
    354         map.put("foo2", "bar2");
    355         request.setAttribute("attr", map);
    356 
    357         try {
    358             map = tagutils.computeParameters(pageContext, null, null, null,
    359                     null, "attr", null, "request", false);
    360         } catch (JspException e) {
    361             fail("JspException: " + e);
    362         }
    363 
    364         assertNotNull("Map is not null", map);
    365         assertEquals("Two parameter in the returned map", 2, map.size());
    366         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    367         assertEquals("Parameter foo1 value", "bar1", (String) map.get("foo1"));
    368         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    369         assertEquals("Parameter foo2 value", "bar2", (String) map.get("foo2"));
    370     }
    371 
    372     // Provided map -- scope + name + property
    373     public void testComputeParameters2c() {
    374         request.setAttribute("attr", new MockFormBean());
    375 
    376         Map map = null;
    377 
    378         try {
    379             map = tagutils.computeParameters(pageContext, null, null, null,
    380                     null, "attr", "mapProperty", "request", false);
    381         } catch (JspException e) {
    382             fail("JspException: " + e);
    383         }
    384 
    385         assertNotNull("Map is not null", map);
    386         assertEquals("Two parameter in the returned map", 2, map.size());
    387         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    388         assertEquals("Parameter foo1 value", "bar1", (String) map.get("foo1"));
    389         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    390         assertEquals("Parameter foo2 value", "bar2", (String) map.get("foo2"));
    391     }
    392 
    393     // Provided map -- name with one key and two values
    394     public void testComputeParameters2d() {
    395         Map map = new HashMap();
    396 
    397         map.put("foo", new String[] { "bar1", "bar2" });
    398         request.getSession().setAttribute("attr", map);
    399 
    400         try {
    401             map = tagutils.computeParameters(pageContext, null, null, null,
    402                     null, "attr", null, null, false);
    403         } catch (JspException e) {
    404             fail("JspException: " + e);
    405         }
    406 
    407         assertNotNull("Map is not null", map);
    408         assertEquals("One parameter in the returned map", 1, map.size());
    409         assertTrue("Parameter foo present", map.containsKey("foo"));
    410         assertTrue("Parameter foo value type",
    411             map.get("foo") instanceof String[]);
    412 
    413         String[] values = (String[]) map.get("foo");
    414 
    415         assertEquals("Values count", 2, values.length);
    416     }
    417 
    418     // Kitchen sink combination of parameters with a merge
    419     public void testComputeParameters3a() {
    420         request.setAttribute("attr", new MockFormBean("bar3"));
    421         request.getSession().setAttribute(Globals.TRANSACTION_TOKEN_KEY, "token");
    422 
    423         Map map = null;
    424 
    425         try {
    426             map = tagutils.computeParameters(pageContext, "foo1", "attr",
    427                     "stringProperty", "request", "attr", "mapProperty",
    428                     "request", true);
    429         } catch (JspException e) {
    430             fail("JspException: " + e);
    431         }
    432 
    433         assertNotNull("Map is not null", map);
    434         assertEquals("Three parameter in the returned map", 3, map.size());
    435 
    436         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    437         assertTrue("Parameter foo1 value type",
    438             map.get("foo1") instanceof String[]);
    439 
    440         String[] values = (String[]) map.get("foo1");
    441 
    442         assertEquals("Values count", 2, values.length);
    443 
    444         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    445         assertEquals("Parameter foo2 value", "bar2", (String) map.get("foo2"));
    446 
    447         assertTrue("Transaction token parameter present",
    448             map.containsKey(Constants.TOKEN_KEY));
    449         assertEquals("Transaction token parameter value", "token",
    450             (String) map.get(Constants.TOKEN_KEY));
    451     }
    452 
    453     // Kitchen sink combination of parameters with a merge
    454     // with array values in map
    455     public void testComputeParameters3aa() {
    456         request.setAttribute("attr", new MockFormBean("bar3"));
    457         request.getSession().setAttribute(Globals.TRANSACTION_TOKEN_KEY, "token");
    458 
    459         Map map = null;
    460 
    461         try {
    462             map = tagutils.computeParameters(pageContext, "foo1", "attr",
    463                     "stringProperty", "request", "attr",
    464                     "mapPropertyArrayValues", "request", true);
    465         } catch (JspException e) {
    466             fail("JspException: " + e);
    467         }
    468 
    469         assertNotNull("Map is not null", map);
    470         assertEquals("Three parameter in the returned map", 3, map.size());
    471 
    472         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    473         assertTrue("Parameter foo1 value type",
    474             map.get("foo1") instanceof String[]);
    475 
    476         String[] values = (String[]) map.get("foo1");
    477 
    478         assertEquals("Values count", 3, values.length);
    479 
    480         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    481 
    482         String[] arrayValues = (String[]) map.get("foo2");
    483         String val = arrayValues[0];
    484 
    485         assertEquals("Parameter foo2 value", "bar2", val);
    486 
    487         assertTrue("Transaction token parameter present",
    488             map.containsKey(Constants.TOKEN_KEY));
    489         assertEquals("Transaction token parameter value", "token",
    490             (String) map.get(Constants.TOKEN_KEY));
    491     }
    492 
    493     // Kitchen sink combination of parameters with a merge
    494     public void testComputeParameters3b() {
    495         request.setAttribute("attr", new MockFormBean("bar3"));
    496         request.getSession().setAttribute(Globals.TRANSACTION_TOKEN_KEY, "token");
    497 
    498         Map map = null;
    499 
    500         try {
    501             map = tagutils.computeParameters(pageContext, "foo1", "attr",
    502                     "stringProperty", "request", "attr", "mapProperty",
    503                     "request", true);
    504         } catch (JspException e) {
    505             fail("JspException: " + e);
    506         }
    507 
    508         assertNotNull("Map is not null", map);
    509         assertEquals("Three parameter in the returned map", 3, map.size());
    510 
    511         assertTrue("Parameter foo1 present", map.containsKey("foo1"));
    512         assertTrue("Parameter foo1 value type",
    513             map.get("foo1") instanceof String[]);
    514 
    515         String[] values = (String[]) map.get("foo1");
    516 
    517         assertEquals("Values count", 2, values.length);
    518 
    519         assertTrue("Parameter foo2 present", map.containsKey("foo2"));
    520         assertEquals("Parameter foo2 value", "bar2", (String) map.get("foo2"));
    521 
    522         assertTrue("Transaction token parameter present",
    523             map.containsKey(Constants.TOKEN_KEY));
    524         assertEquals("Transaction token parameter value", "token",
    525             (String) map.get(Constants.TOKEN_KEY));
    526     }
    527 
    528     // ----------------------------------------------------------- computeURL()
    529     // Default module -- Forward only
    530     public void testComputeURL1a() {
    531         request.setPathElements("/myapp", "/action.do", null, null);
    532 
    533         String url = null;
    534 
    535         try {
    536             url = tagutils.computeURL(pageContext, "foo", null, null, null,
    537                     null, null, null, false);
    538         } catch (MalformedURLException e) {
    539             fail("MalformedURLException: " + e);
    540         }
    541 
    542         assertNotNull("url present", url);
    543         assertEquals("url value", "/myapp/bar.jsp", url);
    544     }
    545 
    546     // Default module -- Href only
    547     public void testComputeURL1b() {
    548         request.setPathElements("/myapp", "/action.do", null, null);
    549 
    550         String url = null;
    551 
    552         try {
    553             url = tagutils.computeURL(pageContext, null, "http://foo.com/bar",
    554                     null, null, null, null, null, false);
    555         } catch (MalformedURLException e) {
    556             fail("MalformedURLException: " + e);
    557         }
    558 
    559         assertNotNull("url present", url);
    560         assertEquals("url value", "http://foo.com/bar", url);
    561     }
    562 
    563     // Default module -- Page only
    564     public void testComputeURL1c() {
    565         request.setPathElements("/myapp", "/action.do", null, null);
    566 
    567         String url = null;
    568 
    569         try {
    570             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    571                     null, null, null, false);
    572         } catch (MalformedURLException e) {
    573             fail("MalformedURLException: " + e);
    574         }
    575 
    576         assertNotNull("url present", url);
    577         assertEquals("url value", "/myapp/bar", url);
    578     }
    579 
    580     // Default module -- Forward with pattern
    581     public void testComputeURL1d() {
    582         moduleConfig.getControllerConfig().setForwardPattern("$C/WEB-INF/pages$M$P");
    583         request.setPathElements("/myapp", "/action.do", null, null);
    584 
    585         String url = null;
    586 
    587         try {
    588             url = tagutils.computeURL(pageContext, "foo", null, null, null,
    589                     null, null, null, false);
    590         } catch (MalformedURLException e) {
    591             fail("MalformedURLException: " + e);
    592         }
    593 
    594         assertNotNull("url present", url);
    595         assertEquals("url value", "/myapp/WEB-INF/pages/bar.jsp", url);
    596     }
    597 
    598     // Default module -- Page with pattern
    599     public void testComputeURL1e() {
    600         moduleConfig.getControllerConfig().setPagePattern("$C/WEB-INF/pages$M$P");
    601         request.setPathElements("/myapp", "/action.do", null, null);
    602 
    603         String url = null;
    604 
    605         try {
    606             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    607                     null, null, null, false);
    608         } catch (MalformedURLException e) {
    609             fail("MalformedURLException: " + e);
    610         }
    611 
    612         assertNotNull("url present", url);
    613         assertEquals("url value", "/myapp/WEB-INF/pages/bar", url);
    614     }
    615 
    616     // Default module -- Forward with relative path (non-context-relative)
    617     public void testComputeURL1f() {
    618         request.setPathElements("/myapp", "/action.do", null, null);
    619 
    620         String url = null;
    621 
    622         try {
    623             url = tagutils.computeURL(pageContext, "relative1", null, null,
    624                     null, null, null, null, false);
    625         } catch (MalformedURLException e) {
    626             fail("MalformedURLException: " + e);
    627         }
    628 
    629         assertNotNull("url present", url);
    630         assertEquals("url value",
    631         //                     "/myapp/relative.jsp",
    632         "relative.jsp", url);
    633     }
    634 
    635     // Default module -- Forward with relative path (context-relative)
    636     public void testComputeURL1g() {
    637         request.setPathElements("/myapp", "/action.do", null, null);
    638 
    639         String url = null;
    640 
    641         try {
    642             url = tagutils.computeURL(pageContext, "relative2", null, null,
    643                     null, null, null, null, false);
    644         } catch (MalformedURLException e) {
    645             fail("MalformedURLException: " + e);
    646         }
    647 
    648         assertNotNull("url present", url);
    649         assertEquals("url value",
    650         //                     "/myapp/relative.jsp",
    651         "relative.jsp", url);
    652     }
    653 
    654     // Default module -- Forward with external path
    655     public void testComputeURL1h() {
    656         request.setPathElements("/myapp", "/action.do", null, null);
    657 
    658         String url = null;
    659 
    660         try {
    661             url = tagutils.computeURL(pageContext, "external", null, null,
    662                     null, null, null, null, false);
    663         } catch (MalformedURLException e) {
    664             fail("MalformedURLException: " + e);
    665         }
    666 
    667         assertNotNull("url present", url);
    668         assertEquals("url value", "http://struts.apache.org/", url);
    669     }
    670 
    671     // Second module -- Forward only
    672     public void testComputeURL2a() {
    673         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    674         request.setPathElements("/myapp", "/2/action.do", null, null);
    675 
    676         String url = null;
    677 
    678         try {
    679             url = tagutils.computeURL(pageContext, "foo", null, null, null,
    680                     null, null, null, false);
    681         } catch (MalformedURLException e) {
    682             fail("MalformedURLException: " + e);
    683         }
    684 
    685         assertNotNull("url present", url);
    686         assertEquals("url value", "/myapp/2/baz.jsp", url);
    687     }
    688 
    689     // Second module -- Href only
    690     public void testComputeURL2b() {
    691         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    692         request.setPathElements("/myapp", "/2/action.do", null, null);
    693 
    694         String url = null;
    695 
    696         try {
    697             url = tagutils.computeURL(pageContext, null, "http://foo.com/bar",
    698                     null, null, null, null, null, false);
    699         } catch (MalformedURLException e) {
    700             fail("MalformedURLException: " + e);
    701         }
    702 
    703         assertNotNull("url present", url);
    704         assertEquals("url value", "http://foo.com/bar", url);
    705     }
    706 
    707     // Second module -- Page only
    708     public void testComputeURL2c() {
    709         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    710         request.setPathElements("/myapp", "/2/action.do", null, null);
    711 
    712         String url = null;
    713 
    714         try {
    715             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    716                     null, null, null, false);
    717         } catch (MalformedURLException e) {
    718             fail("MalformedURLException: " + e);
    719         }
    720 
    721         assertNotNull("url present", url);
    722         assertEquals("url value", "/myapp/2/bar", url);
    723     }
    724 
    725     // Default module -- Forward with pattern
    726     public void testComputeURL2d() {
    727         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    728         moduleConfig2.getControllerConfig().setForwardPattern("$C/WEB-INF/pages$M$P");
    729         request.setPathElements("/myapp", "/2/action.do", null, null);
    730 
    731         String url = null;
    732 
    733         try {
    734             url = tagutils.computeURL(pageContext, "foo", null, null, null,
    735                     null, null, null, false);
    736         } catch (MalformedURLException e) {
    737             fail("MalformedURLException: " + e);
    738         }
    739 
    740         assertNotNull("url present", url);
    741         assertEquals("url value", "/myapp/WEB-INF/pages/2/baz.jsp", url);
    742     }
    743 
    744     // Second module -- Page with pattern
    745     public void testComputeURL2e() {
    746         moduleConfig2.getControllerConfig().setPagePattern("$C/WEB-INF/pages$M$P");
    747         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    748         request.setPathElements("/myapp", "/2/action.do", null, null);
    749 
    750         String url = null;
    751 
    752         try {
    753             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    754                     null, null, null, false);
    755         } catch (MalformedURLException e) {
    756             fail("MalformedURLException: " + e);
    757         }
    758 
    759         assertNotNull("url present", url);
    760         assertEquals("url value", "/myapp/WEB-INF/pages/2/bar", url);
    761     }
    762 
    763     // Second module -- Forward with relative path (non-context-relative)
    764     public void testComputeURL2f() {
    765         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    766         request.setPathElements("/myapp", "/2/action.do", null, null);
    767 
    768         String url = null;
    769 
    770         try {
    771             url = tagutils.computeURL(pageContext, "relative1", null, null,
    772                     null, null, null, null, false);
    773         } catch (MalformedURLException e) {
    774             fail("MalformedURLException: " + e);
    775         }
    776 
    777         assertNotNull("url present", url);
    778         assertEquals("url value",
    779         //                     "/myapp/2/relative.jsp",
    780         "relative.jsp", url);
    781     }
    782 
    783     // Second module -- Forward with relative path (context-relative)
    784     public void testComputeURL2g() {
    785         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    786         request.setPathElements("/myapp", "/2/action.do", null, null);
    787 
    788         String url = null;
    789 
    790         try {
    791             url = tagutils.computeURL(pageContext, "relative2", null, null,
    792                     null, null, null, null, false);
    793         } catch (MalformedURLException e) {
    794             fail("MalformedURLException: " + e);
    795         }
    796 
    797         assertNotNull("url present", url);
    798         assertEquals("url value",
    799         //                     "/myapp/relative.jsp",
    800         "relative.jsp", url);
    801     }
    802 
    803     // Second module -- Forward with external path
    804     public void testComputeURL2h() {
    805         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    806         request.setPathElements("/myapp", "/2/action.do", null, null);
    807 
    808         String url = null;
    809 
    810         try {
    811             url = tagutils.computeURL(pageContext, "external", null, null,
    812                     null, null, null, null, false);
    813         } catch (MalformedURLException e) {
    814             fail("MalformedURLException: " + e);
    815         }
    816 
    817         assertNotNull("url present", url);
    818         assertEquals("url value", "http://struts.apache.org/", url);
    819     }
    820 
    821     // Add parameters only -- forward URL
    822     public void testComputeURL3a() {
    823         request.setPathElements("/myapp", "/action.do", null, null);
    824 
    825         Map map = new HashMap();
    826 
    827         map.put("foo1", "bar1");
    828         map.put("foo2", "bar2");
    829 
    830         String url = null;
    831 
    832         try {
    833             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    834                     null, map, null, false);
    835         } catch (MalformedURLException e) {
    836             fail("MalformedURLException: " + e);
    837         }
    838 
    839         assertNotNull("url present", url);
    840         assertTrue("url value",
    841             url.equals("/myapp/bar?foo1=bar1&amp;foo2=bar2")
    842             || url.equals("/myapp/bar?foo2=bar2&amp;foo1=bar1"));
    843     }
    844 
    845     // Add anchor only -- forward URL
    846     public void testComputeURL3b() {
    847         request.setPathElements("/myapp", "/action.do", null, null);
    848 
    849         String url = null;
    850 
    851         try {
    852             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    853                     null, null, "anchor", false);
    854         } catch (MalformedURLException e) {
    855             fail("MalformedURLException: " + e);
    856         }
    857 
    858         assertNotNull("url present", url);
    859         assertEquals("url value", "/myapp/bar#anchor", url);
    860     }
    861 
    862     // Add parameters + anchor -- forward URL
    863     public void testComputeURL3c() {
    864         request.setPathElements("/myapp", "/action.do", null, null);
    865 
    866         Map map = new HashMap();
    867 
    868         map.put("foo1", "bar1");
    869         map.put("foo2", "bar2");
    870 
    871         String url = null;
    872 
    873         try {
    874             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    875                     null, map, "anchor", false);
    876         } catch (MalformedURLException e) {
    877             fail("MalformedURLException: " + e);
    878         }
    879 
    880         assertNotNull("url present", url);
    881         assertTrue("url value",
    882             url.equals("/myapp/bar?foo1=bar1&amp;foo2=bar2#anchor")
    883             || url.equals("/myapp/bar?foo2=bar2&amp;foo1=bar1#anchor"));
    884     }
    885 
    886     // Add parameters only -- redirect URL
    887     public void testComputeURL3d() {
    888         request.setPathElements("/myapp", "/action.do", null, null);
    889 
    890         Map map = new HashMap();
    891 
    892         map.put("foo1", "bar1");
    893         map.put("foo2", "bar2");
    894 
    895         String url = null;
    896 
    897         try {
    898             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    899                     null, map, null, true);
    900         } catch (MalformedURLException e) {
    901             fail("MalformedURLException: " + e);
    902         }
    903 
    904         assertNotNull("url present", url);
    905         assertTrue("url value",
    906             url.equals("/myapp/bar?foo1=bar1&foo2=bar2")
    907             || url.equals("/myapp/bar?foo2=bar2&foo1=bar1"));
    908     }
    909 
    910     // Add anchor only -- redirect URL
    911     public void testComputeURL3e() {
    912         request.setPathElements("/myapp", "/action.do", null, null);
    913 
    914         String url = null;
    915 
    916         try {
    917             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    918                     null, null, "anchor", true);
    919         } catch (MalformedURLException e) {
    920             fail("MalformedURLException: " + e);
    921         }
    922 
    923         assertNotNull("url present", url);
    924         assertEquals("url value", "/myapp/bar#anchor", url);
    925     }
    926 
    927     // Add parameters + anchor -- redirect URL
    928     public void testComputeURL3f() {
    929         request.setPathElements("/myapp", "/action.do", null, null);
    930 
    931         Map map = new HashMap();
    932 
    933         map.put("foo1", "bar1");
    934         map.put("foo2", "bar2");
    935 
    936         String url = null;
    937 
    938         try {
    939             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    940                     null, map, "anchor", false);
    941         } catch (MalformedURLException e) {
    942             fail("MalformedURLException: " + e);
    943         }
    944 
    945         assertNotNull("url present", url);
    946         assertTrue("url value",
    947             url.equals("/myapp/bar?foo1=bar1&amp;foo2=bar2#anchor")
    948             || url.equals("/myapp/bar?foo2=bar2&amp;foo1=bar1#anchor"));
    949     }
    950 
    951     // Add parameters only -- forward URL -- do not encode seperator
    952     public void testComputeURL3g() {
    953         request.setPathElements("/myapp", "/action.do", null, null);
    954 
    955         Map map = new HashMap();
    956 
    957         map.put("foo1", "bar1");
    958         map.put("foo2", "bar2");
    959 
    960         String url = null;
    961 
    962         try {
    963             url = tagutils.computeURLWithCharEncoding(pageContext, null, null,
    964                     "/bar", null, null, map, null, false, false, false);
    965         } catch (MalformedURLException e) {
    966             fail("MalformedURLException: " + e);
    967         }
    968 
    969         assertNotNull("url present", url);
    970         assertTrue("url value",
    971             url.equals("/myapp/bar?foo1=bar1&foo2=bar2")
    972             || url.equals("/myapp/bar?foo2=bar2&foo1=bar1"));
    973     }
    974 
    975     // Add parameters only
    976     //  -- forward URL
    977     //  -- do not encode seperator
    978     //  -- send param with null value
    979     public void testComputeURL3h() {
    980         request.setPathElements("/myapp", "/action.do", null, null);
    981 
    982         Map map = new HashMap();
    983 
    984         map.put("foo1", null);
    985 
    986         String url = null;
    987 
    988         try {
    989             url = tagutils.computeURLWithCharEncoding(pageContext, null, null,
    990                     "/bar", null, null, map, null, false, false, false);
    991         } catch (MalformedURLException e) {
    992             fail("MalformedURLException: " + e);
    993         }
    994 
    995         assertNotNull("url present", url);
    996         assertTrue("url value", url.equals("/myapp/bar?foo1="));
    997     }
    998 
    999     // Add parameters only
    1000     //  -- forward URL
    1001     //  -- do not encode seperator
    1002     //  -- send param with null value
    1003     //  -- add ? to page
    1004     public void testComputeURL3i() {
    1005         request.setPathElements("/myapp", "/action.do", null, null);
    1006 
    1007         Map map = new HashMap();
    1008 
    1009         map.put("foo1", null);
    1010 
    1011         String url = null;
    1012 
    1013         try {
    1014             url = tagutils.computeURLWithCharEncoding(pageContext, null, null,
    1015                     "/bar?", null, null, map, null, false, false, false);
    1016         } catch (MalformedURLException e) {
    1017             fail("MalformedURLException: " + e);
    1018         }
    1019 
    1020         assertNotNull("url present", url);
    1021         assertTrue("url value", url.equals("/myapp/bar?&foo1="));
    1022     }
    1023 
    1024     // Add parameters only
    1025     //  -- forward URL
    1026     //  -- do not encode seperator
    1027     //  -- send param with null value
    1028     //  -- add ? and param to page
    1029     public void testComputeURL3j() {
    1030         request.setPathElements("/myapp", "/action.do", null, null);
    1031 
    1032         Map map = new HashMap();
    1033 
    1034         map.put("foo1", null);
    1035         map.put("foo2", "bar2");
    1036 
    1037         String url = null;
    1038 
    1039         try {
    1040             url = tagutils.computeURLWithCharEncoding(pageContext, null, null,
    1041                     "/bar?a=b", null, null, map, null, false, false, false);
    1042         } catch (MalformedURLException e) {
    1043             fail("MalformedURLException: " + e);
    1044         }
    1045 
    1046         assertNotNull("url present", url);
    1047         assertTrue("url value",
    1048             url.equals("/myapp/bar?a=b&foo1=&foo2=bar2")
    1049             || url.equals("/myapp/bar?a=b&foo2=bar2&foo1="));
    1050     }
    1051 
    1052     // -- Add Parameters
    1053     // -- Parameter as String Array
    1054     public void testComputeURL3k() {
    1055         request.setPathElements("/myapp", "/action.do", null, null);
    1056 
    1057         Map map = new HashMap();
    1058 
    1059         map.put("foo1", new String[] { "bar1", "baz1" });
    1060 
    1061         String url = null;
    1062 
    1063         try {
    1064             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    1065                     null, map, null, false);
    1066         } catch (MalformedURLException e) {
    1067             fail("MalformedURLException: " + e);
    1068         }
    1069 
    1070         assertNotNull("url present", url);
    1071         assertTrue("url value",
    1072             url.equals("/myapp/bar?foo1=bar1&amp;foo1=baz1")
    1073             || url.equals("/myapp/bar?foo1=baz1&amp;foo1=bar1"));
    1074     }
    1075 
    1076     // -- Add Parameters
    1077     // -- Parameter as non String or String Array
    1078     public void testComputeURL3l() {
    1079         request.setPathElements("/myapp", "/action.do", null, null);
    1080 
    1081         Map map = new HashMap();
    1082 
    1083         map.put("foo1", new Double(0));
    1084 
    1085         String url = null;
    1086 
    1087         try {
    1088             url = tagutils.computeURL(pageContext, null, null, "/bar", null,
    1089                     null, map, null, false);
    1090         } catch (MalformedURLException e) {
    1091             fail("MalformedURLException: " + e);
    1092         }
    1093 
    1094         assertNotNull("url present", url);
    1095         assertTrue("url value", url.equals("/myapp/bar?foo1=0.0"));
    1096     }
    1097 
    1098     // -- Add Parameters
    1099     // -- Parameter as non String or String Array
    1100     // -- with ? on path
    1101     public void testComputeURL3m() {
    1102         request.setPathElements("/myapp", "/action.do", null, null);
    1103 
    1104         Map map = new HashMap();
    1105 
    1106         map.put("foo1", new Double(0));
    1107 
    1108         String url = null;
    1109 
    1110         try {
    1111             url = tagutils.computeURL(pageContext, null, null, "/bar?", null,
    1112                     null, map, null, false);
    1113         } catch (MalformedURLException e) {
    1114             fail("MalformedURLException: " + e);
    1115         }
    1116 
    1117         assertNotNull("url present", url);
    1118         assertTrue("url value", url.equals("/myapp/bar?&amp;foo1=0.0"));
    1119     }
    1120 
    1121     public void testComputeURLCharacterEncoding() {
    1122         request.setPathElements("/myapp", "/action.do", null, null);
    1123 
    1124         String url = null;
    1125 
    1126         try {
    1127             url = tagutils.computeURLWithCharEncoding(pageContext, "foo", null,
    1128                     null, null, null, null, null, false, true, true);
    1129             fail("Exception not thrown");
    1130         } catch (MalformedURLException e) {
    1131             fail("MalformedURLException: " + e);
    1132         } catch (UnsupportedOperationException e) {
    1133             assertNull("url should be null", url);
    1134         }
    1135     }
    1136 
    1137     public void testComputeURLCharacterEncodingMultipleSpecifier() {
    1138         verifyBadSetOfSpecifiers("foo", "foo", null, null);
    1139         verifyBadSetOfSpecifiers("foo", null, "foo", null);
    1140         verifyBadSetOfSpecifiers("foo", null, null, "foo");
    1141 
    1142         verifyBadSetOfSpecifiers(null, "foo", "foo", null);
    1143         verifyBadSetOfSpecifiers(null, "foo", null, "foo");
    1144 
    1145         verifyBadSetOfSpecifiers(null, null, "foo", "foo");
    1146     }
    1147 
    1148     public void testComputeURLCharacterEncodingAction() {
    1149         ActionConfig actionConfig = new ActionConfig();
    1150 
    1151         actionConfig.setName("baz");
    1152         actionConfig.setPath("/baz");
    1153 
    1154         moduleConfig.addActionConfig(actionConfig);
    1155 
    1156         request.setPathElements("/myapp", "/foo.do", null, null);
    1157 
    1158         Map map = new HashMap();
    1159 
    1160         map.put("foo1", "bar1");
    1161         map.put("foo2", "bar2");
    1162 
    1163         String url = null;
    1164 
    1165         try {
    1166             url = tagutils.computeURL(pageContext, null, null, null, "baz",
    1167                     null, map, "anchor", false);
    1168         } catch (MalformedURLException e) {
    1169             fail("MalformedURLException: " + e);
    1170         }
    1171 
    1172         assertNotNull("url present", url);
    1173         assertTrue("url value",
    1174             url.equals("/myapp/baz?foo1=bar1&amp;foo2=bar2#anchor")
    1175             || url.equals("/myapp/baz?foo2=bar2&amp;foo1=bar1#anchor"));
    1176     }
    1177 
    1178     // -------------------------------------------------------------- pageURL()
    1179     // Default module (default pagePattern)
    1180     public void testPageURL1() {
    1181         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1182         request.setPathElements("/myapp", "/action.do", null, null);
    1183 
    1184         String page = null;
    1185         String result = null;
    1186 
    1187         // Straight substitution
    1188         page = "/mypages/index.jsp";
    1189         result = tagutils.pageURL(request, page, moduleConfig);
    1190         assertNotNull("straight sub found", result);
    1191         assertEquals("straight sub value", "/mypages/index.jsp", result);
    1192     }
    1193 
    1194     // Second module (default pagePattern)
    1195     public void testPageURL2() {
    1196         request.setAttribute(Globals.MODULE_KEY, moduleConfig2);
    1197         request.setPathElements("/myapp", "/2/action.do", null, null);
    1198 
    1199         String page = null;
    1200         String result = null;
    1201 
    1202         // Straight substitution
    1203         page = "/mypages/index.jsp";
    1204         result = tagutils.pageURL(request, page, moduleConfig2);
    1205         assertNotNull("straight sub found", result);
    1206         assertEquals("straight sub value", "/2/mypages/index.jsp", result);
    1207     }
    1208 
    1209     // Third module (custom pagePattern)
    1210     // TODO finish me
    1211     public void testPageURL3a() {
    1212         request.setAttribute(Globals.MODULE_KEY, moduleConfig3);
    1213         request.setPathElements("/myapp", "/3/action.do", null, null);
    1214 
    1215         //        String page = null;
    1216         //        String result = null;
    1217     }
    1218 
    1219     // Third module (custom pagePattern)
    1220     public void testPageURL3b() {
    1221         request.setAttribute(Globals.MODULE_KEY, moduleConfig3);
    1222         request.setPathElements("/myapp", "/3/action.do", null, null);
    1223 
    1224         String page = null;
    1225         String result = null;
    1226 
    1227         // Straight substitution
    1228         page = "/mypages/index.jsp";
    1229         result = tagutils.pageURL(request, page, moduleConfig3);
    1230         assertNotNull("straight sub found", result);
    1231         assertEquals("straight sub value", "/3/mypages/index.jsp", result);
    1232     }
    1233 
    1234     /**
    1235      * Helper method that verifies the supplied specifiers.
    1236      *
    1237      * @param forward    The forward specified
    1238      * @param href       The href specified
    1239      * @param pageString The pageString specified
    1240      * @param action     The action specified
    1241      */
    1242     private void verifyBadSetOfSpecifiers(String forward, String href,
    1243         String pageString, String action) {
    1244         String url = null;
    1245 
    1246         try {
    1247             url = tagutils.computeURLWithCharEncoding(pageContext, forward,
    1248                     href, pageString, action, null, null, null, false, true,
    1249                     false);
    1250         } catch (MalformedURLException e) {
    1251             assertNull("url should be null", url);
    1252         } catch (UnsupportedOperationException e) {
    1253             fail("MalformedURLException not thrown");
    1254         }
    1255     }
    1256 
    1257     // -------------------------------------------------------------- encodeURL()
    1258     // Default module (default pagePattern)
    1259     public void testencodeURL1() {
    1260         String encodedURL = null;
    1261 
    1262         encodedURL = tagutils.encodeURL("foo-bar.baz");
    1263         assertEquals("encode url", "foo-bar.baz", encodedURL);
    1264     }
    1265 
    1266     // ------------------------------------------ getActionErrors()
    1267     // ActionErrors
    1268     public void testGetActionErrors1a() {
    1269         ActionMessages actionErrors = new ActionMessages();
    1270 
    1271         actionErrors.add("prop", new ActionMessage("key.key"));
    1272         request.setAttribute("errors", actionErrors);
    1273 
    1274         try {
    1275             ActionMessages errors =
    1276                 tagutils.getActionMessages(pageContext, "errors");
    1277 
    1278             assertNotNull("errors should not be null", errors);
    1279             assertNotNull("errors prop should not be null", errors.get("prop"));
    1280 
    1281             String val = null;
    1282             int i = 0;
    1283 
    1284             for (Iterator iter = errors.get("prop"); iter.hasNext();) {
    1285                 ActionMessage error = (ActionMessage) iter.next();
    1286 
    1287                 val = error.getKey();
    1288                 i++;
    1289             }
    1290 
    1291             assertEquals("only 1 error", i, 1);
    1292             assertEquals("errors prop should match", val, "key.key");
    1293         } catch (JspException e) {
    1294             fail(e.getMessage());
    1295         }
    1296     }
    1297 
    1298     // String
    1299     public void testGetActionErrors1b() {
    1300         request.setAttribute("foo", "bar");
    1301 
    1302         try {
    1303             ActionMessages errors =
    1304                 tagutils.getActionMessages(pageContext, "foo");
    1305 
    1306             assertNotNull("errors should not be null", errors);
    1307             assertNotNull("errors prop should not be null", errors.get("prop"));
    1308 
    1309             String key = null;
    1310             int i = 0;
    1311 
    1312             for (Iterator iter = errors.get(ActionMessages.GLOBAL_MESSAGE);
    1313                 iter.hasNext();) {
    1314                 ActionMessage error = (ActionMessage) iter.next();
    1315 
    1316                 key = error.getKey();
    1317 
    1318                 Object[] values = error.getValues();
    1319 
    1320                 assertNull(values);
    1321                 i++;
    1322             }
    1323 
    1324             assertEquals("only 1 error", i, 1);
    1325             assertEquals("key should match", key, "bar");
    1326         } catch (JspException e) {
    1327             fail(e.getMessage());
    1328         }
    1329     }
    1330 
    1331     // String Array
    1332     public void testGetActionErrors1c() {
    1333         String[] vals = new String[] { "bar", "baz" };
    1334 
    1335         request.setAttribute("foo", vals);
    1336 
    1337         try {
    1338             ActionMessages errors =
    1339                 tagutils.getActionMessages(pageContext, "foo");
    1340 
    1341             assertNotNull("errors should not be null", errors);
    1342             assertNotNull("errors prop should not be null", errors.get("prop"));
    1343 
    1344             String key = null;
    1345             int i = 0;
    1346 
    1347             for (Iterator iter = errors.get(ActionMessages.GLOBAL_MESSAGE);
    1348                 iter.hasNext();) {
    1349                 ActionMessage error = (ActionMessage) iter.next();
    1350 
    1351                 key = error.getKey();
    1352 
    1353                 Object[] values = error.getValues();
    1354 
    1355                 assertNull((values));
    1356                 assertEquals("1st key should match", key, vals[i]);
    1357                 i++;
    1358             }
    1359 
    1360             assertEquals("only 1 error", i, 2);
    1361         } catch (JspException e) {
    1362             fail(e.getMessage());
    1363         }
    1364     }
    1365 
    1366     // String Array (thrown JspException)
    1367     public void testGetActionErrors1d() {
    1368         request.setAttribute("foo", new MockFormBean());
    1369 
    1370         ActionMessages errors = null;
    1371 
    1372         try {
    1373             errors = tagutils.getActionMessages(pageContext, "foo");
    1374             fail("should have thrown JspException");
    1375         } catch (JspException e) {
    1376             assertNull("errors should be null", errors);
    1377         }
    1378     }
    1379 
    1380     // ActionErrors (thrown Exception)
    1381     // TODO -- currently this does not hit the line for caught Exception
    1382     public void testGetActionErrors1e() {
    1383         ActionMessages actionErrors = new ActionMessages();
    1384 
    1385         actionErrors.add("prop", new ActionMessage("key.key"));
    1386         request.setAttribute("errors", actionErrors);
    1387 
    1388         try {
    1389             ActionMessages errors =
    1390                 tagutils.getActionMessages(pageContext, "does-not-exist");
    1391 
    1392             assertNotNull("errors should not be null", errors);
    1393             assertNotNull("errors prop should not be null", errors.get("prop"));
    1394 
    1395             for (Iterator iter = errors.get("prop"); iter.hasNext();) {
    1396                 fail("Should not have any errors for does-not-exist");
    1397             }
    1398         } catch (JspException e) {
    1399             fail(e.getMessage());
    1400         }
    1401     }
    1402 
    1403     // ------------------------------------------ getActionMappingName()
    1404     public void testGetActionMappingName1() {
    1405         String[] paths =
    1406             {
    1407                 "foo", "foo.do", "foo?foo=bar", "foo?foo=bar&bar=baz",
    1408                 "foo?foo=bar&amp;bar=baz"
    1409             };
    1410 
    1411         String[][] prepends =
    1412             {
    1413                 { "", "/foo" },
    1414                 { "/", "/foo" },
    1415                 { "bar/", "/bar/foo" },
    1416                 { "/bar/", "/bar/foo" }
    1417             };
    1418 
    1419         String[] appends =
    1420             {
    1421                 "", "#anchor", "?", "?#", "?foo=bar", "?foo1=bar1&foo2=bar2",
    1422                 "?foo1=bar1&amp;foo2=bar2"
    1423             };
    1424 
    1425         String finalResult = null;
    1426 
    1427         String path = null;
    1428         String results = null;
    1429         boolean equality = false;
    1430         int ct = 0;
    1431 
    1432         for (int i = 0; i < appends.length; i++) {
    1433             for (int j = 0; j < prepends.length; j++) {
    1434                 finalResult = prepends[j][1];
    1435 
    1436                 for (int k = 0; k < paths.length; k++) {
    1437                     path = prepends[j][0] + paths[k] + appends[i];
    1438                     results = tagutils.getActionMappingName(path);
    1439                     equality = finalResult.equals(results);
    1440 
    1441                     if (!equality) {
    1442                         fail("Path does not return correct result\n"
    1443                             + "\nexpected: " + results + "\nfound: " + path);
    1444                     }
    1445 
    1446                     assertTrue("Path should translate to result", equality);
    1447                     ct++;
    1448                 }
    1449             }
    1450         }
    1451 
    1452         log.debug(ct + " assertions run in this test");
    1453     }
    1454 
    1455     public void testString_getActionMappingURL_String_PageContext() {
    1456         ActionConfig actionConfig = new ActionConfig();
    1457 
    1458         actionConfig.setParameter("/foo");
    1459         moduleConfig.addActionConfig(actionConfig);
    1460 
    1461         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1462         request.setPathElements("/myapp", "/foo.do", null, null);
    1463 
    1464         assertEquals("Check path /foo",
    1465             tagutils.getActionMappingURL("/foo", pageContext), "/myapp/foo");
    1466     }
    1467 
    1468     // use servlet mapping (extension mapping)
    1469     public void testString_getActionMappingURL_String_String_PageContext_boolean1() {
    1470         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY, "*.do");
    1471 
    1472         ActionConfig actionConfig = new ActionConfig();
    1473 
    1474         actionConfig.setParameter("/foo");
    1475         moduleConfig.addActionConfig(actionConfig);
    1476 
    1477         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1478         request.setPathElements("/myapp", "/baz.do", null, null);
    1479 
    1480         assertEquals("Check path /foo",
    1481             tagutils.getActionMappingURL("/foo", pageContext), "/myapp/foo.do");
    1482     }
    1483 
    1484     // use servlet mapping (extension mapping)
    1485     //  -- with params
    1486     public void testString_getActionMappingURL_String_String_PageContext_boolean2() {
    1487         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY, "*.do");
    1488 
    1489         ActionConfig actionConfig = new ActionConfig();
    1490 
    1491         actionConfig.setParameter("/foo");
    1492         moduleConfig.addActionConfig(actionConfig);
    1493 
    1494         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1495         request.setPathElements("/myapp", "/baz.do?foo=bar", null, null);
    1496 
    1497         assertEquals("Check path /foo",
    1498             tagutils.getActionMappingURL("/foo?foo=bar", pageContext),
    1499             "/myapp/foo.do?foo=bar");
    1500     }
    1501 
    1502     // use servlet mapping (extension mapping)
    1503     //  -- path as "/"
    1504     // (this is probably not a realistic use case)
    1505     public void testString_getActionMappingURL_String_String_PageContext_boolean3() {
    1506         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY, "*.do");
    1507 
    1508         ActionConfig actionConfig = new ActionConfig();
    1509 
    1510         actionConfig.setParameter("/foo");
    1511         moduleConfig.addActionConfig(actionConfig);
    1512 
    1513         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1514         request.setPathElements("/mycontext", "/baz", null, null);
    1515 
    1516         assertEquals("Check path /foo",
    1517             tagutils.getActionMappingURL("/", pageContext), "/mycontext/.do");
    1518     }
    1519 
    1520     // use servlet mapping (path mapping)
    1521     public void testString_getActionMappingURL_String_String_PageContext_boolean4() {
    1522         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY,
    1523             "/myapp/*");
    1524 
    1525         ActionConfig actionConfig = new ActionConfig();
    1526 
    1527         actionConfig.setParameter("/foo");
    1528         moduleConfig.addActionConfig(actionConfig);
    1529 
    1530         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1531         request.setPathElements("/mycontext", "/baz", null, null);
    1532 
    1533         assertEquals("Check path /foo",
    1534             tagutils.getActionMappingURL("/foo", pageContext),
    1535             "/mycontext/myapp/foo");
    1536     }
    1537 
    1538     // use servlet mapping (path mapping)
    1539     //  -- with params
    1540     public void testString_getActionMappingURL_String_String_PageContext_boolean5() {
    1541         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY,
    1542             "/myapp/*");
    1543 
    1544         ActionConfig actionConfig = new ActionConfig();
    1545 
    1546         actionConfig.setParameter("/foo");
    1547         moduleConfig.addActionConfig(actionConfig);
    1548 
    1549         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1550         request.setPathElements("/mycontext", "/baz?foo=bar", null, null);
    1551 
    1552         assertEquals("Check path /foo",
    1553             tagutils.getActionMappingURL("/foo?foo=bar", pageContext),
    1554             "/mycontext/myapp/foo?foo=bar");
    1555     }
    1556 
    1557     // use servlet mapping (path mapping)
    1558     //  -- using "/" as mapping
    1559     public void testString_getActionMappingURL_String_String_PageContext_boolean6() {
    1560         pageContext.getServletContext().setAttribute(Globals.SERVLET_KEY, "/");
    1561 
    1562         ActionConfig actionConfig = new ActionConfig();
    1563 
    1564         actionConfig.setParameter("/foo");
    1565         moduleConfig.addActionConfig(actionConfig);
    1566 
    1567         request.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1568         request.setPathElements("/mycontext", "/baz", null, null);
    1569 
    1570         assertEquals("Check path /foo",
    1571             tagutils.getActionMappingURL("/", pageContext), "/mycontext/");
    1572     }
    1573 
    1574     // ------------------------------------------ getActionMessages()
    1575     // -- using ActionMessages
    1576     public void testActionMessages_getActionMessages_PageContext_String1() {
    1577         ActionMessages actionMessages = new ActionMessages();
    1578 
    1579         actionMessages.add("prop", new ActionMessage("key.key"));
    1580         request.setAttribute("messages", actionMessages);
    1581 
    1582         try {
    1583             ActionMessages messages =
    1584                 tagutils.getActionMessages(pageContext, "messages");
    1585 
    1586             assertNotNull("messages should not be null", messages);
    1587             assertNotNull("messages prop should not be null",
    1588                 messages.get("prop"));
    1589 
    1590             String val = null;
    1591             int i = 0;
    1592 
    1593             for (Iterator iter = messages.get("prop"); iter.hasNext();) {
    1594                 ActionMessage message = (ActionMessage) iter.next();
    1595 
    1596                 val = message.getKey();
    1597                 i++;
    1598             }
    1599 
    1600             assertEquals("only 1 message", i, 1);
    1601             assertEquals("messages prop should match", val, "key.key");
    1602         } catch (JspException e) {
    1603             fail(e.getMessage());
    1604         }
    1605     }
    1606 
    1607     // -- using ActionErrors
    1608     public void testActionMessages_getActionMessages_PageContext_String2() {
    1609         ActionMessages actionMessages = new ActionMessages();
    1610 
    1611         actionMessages.add("prop", new ActionMessage("key.key"));
    1612         request.setAttribute("messages", actionMessages);
    1613 
    1614         try {
    1615             ActionMessages messages =
    1616                 tagutils.getActionMessages(pageContext, "messages");
    1617 
    1618             assertNotNull("messages should not be null", messages);
    1619             assertNotNull("messages prop should not be null",
    1620                 messages.get("prop"));
    1621 
    1622             String val = null;
    1623             int i = 0;
    1624 
    1625             for (Iterator iter = messages.get("prop"); iter.hasNext();) {
    1626                 ActionMessage message = (ActionMessage) iter.next();
    1627 
    1628                 val = message.getKey();
    1629                 i++;
    1630             }
    1631 
    1632             assertEquals("only 1 message", i, 1);
    1633             assertEquals("messages prop should match", val, "key.key");
    1634         } catch (JspException e) {
    1635             fail(e.getMessage());
    1636         }
    1637     }
    1638 
    1639     // -- using String
    1640     public void testActionMessages_getActionMessages_PageContext_String3() {
    1641         request.setAttribute("foo", "bar");
    1642 
    1643         try {
    1644             ActionMessages messages =
    1645                 tagutils.getActionMessages(pageContext, "foo");
    1646 
    1647             assertNotNull("messages should not be null", messages);
    1648             assertNotNull("messages prop should not be null",
    1649                 messages.get("prop"));
    1650 
    1651             String key = null;
    1652             int i = 0;
    1653 
    1654             for (Iterator iter = messages.get(ActionMessages.GLOBAL_MESSAGE);
    1655                 iter.hasNext();) {
    1656                 ActionMessage message = (ActionMessage) iter.next();
    1657 
    1658                 key = message.getKey();
    1659 
    1660                 Object[] values = message.getValues();
    1661 
    1662                 assertNull(values);
    1663                 i++;
    1664             }
    1665 
    1666             assertEquals("only 1 message", i, 1);
    1667             assertEquals("key should match", key, "bar");
    1668         } catch (JspException e) {
    1669             fail(e.getMessage());
    1670         }
    1671     }
    1672 
    1673     // -- using String Array
    1674     public void testActionMessages_getActionMessages_PageContext_String4() {
    1675         String[] vals = new String[] { "bar", "baz" };
    1676 
    1677         request.setAttribute("foo", vals);
    1678 
    1679         try {
    1680             ActionMessages messages =
    1681                 tagutils.getActionMessages(pageContext, "foo");
    1682 
    1683             assertNotNull("messages should not be null", messages);
    1684             assertNotNull("messages prop should not be null",
    1685                 messages.get("prop"));
    1686 
    1687             String key = null;
    1688             int i = 0;
    1689 
    1690             for (Iterator iter = messages.get(ActionMessages.GLOBAL_MESSAGE);
    1691                 iter.hasNext();) {
    1692                 ActionMessage message = (ActionMessage) iter.next();
    1693 
    1694                 key = message.getKey();
    1695 
    1696                 Object[] values = message.getValues();
    1697 
    1698                 assertNull((values));
    1699                 assertEquals("1st key should match", key, vals[i]);
    1700                 i++;
    1701             }
    1702 
    1703             assertEquals("only 1 message", i, 2);
    1704         } catch (JspException e) {
    1705             fail(e.getMessage());
    1706         }
    1707     }
    1708 
    1709     // String Array (thrown JspException)
    1710     public void testActionMessages_getActionMessages_PageContext_String5() {
    1711         request.setAttribute("foo", new MockFormBean());
    1712 
    1713         ActionMessages messages = null;
    1714 
    1715         try {
    1716             messages = tagutils.getActionMessages(pageContext, "foo");
    1717             fail("should have thrown JspException");
    1718         } catch (JspException e) {
    1719             assertNull("messages should be null", messages);
    1720         }
    1721     }
    1722 
    1723     // ActionMessages (thrown Exception)
    1724     // TODO -- currently this does not hit the line for caught Exception
    1725     public void testActionMessages_getActionMessages_PageContext_String6() {
    1726         ActionMessages actionMessages = new ActionMessages();
    1727 
    1728         actionMessages.add("prop", new ActionMessage("key.key"));
    1729         request.setAttribute("messages", actionMessages);
    1730 
    1731         try {
    1732             ActionMessages messages =
    1733                 tagutils.getActionMessages(pageContext, "does-not-exist");
    1734 
    1735             assertNotNull("messages should not be null", messages);
    1736             assertNotNull("messages prop should not be null",
    1737                 messages.get("prop"));
    1738 
    1739             for (Iterator iter = messages.get("prop"); iter.hasNext();) {
    1740                 fail("Should not have any messages for does-not-exist");
    1741             }
    1742         } catch (JspException e) {
    1743             fail(e.getMessage());
    1744         }
    1745     }
    1746 
    1747     // ----public ModuleConfig getModuleConfig(PageContext pageContext)
    1748     public void testModuleConfig_getModuleConfig_PageContext() {
    1749         MockServletConfig mockServletConfig = new MockServletConfig();
    1750         ModuleConfig moduleConfig = new ModuleConfigImpl("");
    1751         MockServletContext mockServletContext = new MockServletContext();
    1752         MockHttpServletRequest mockHttpServletRequest =
    1753             new MockHttpServletRequest();
    1754         MockHttpServletResponse mockHttpServletResponse =
    1755             new MockHttpServletResponse();
    1756 
    1757         mockServletConfig.setServletContext(mockServletContext);
    1758 
    1759         MockPageContext mockPageContext =
    1760             new MockPageContext(mockServletConfig, mockHttpServletRequest,
    1761                 mockHttpServletResponse);
    1762 
    1763         ModuleConfig foundModuleConfig = null;
    1764 
    1765         try {
    1766             foundModuleConfig = tagutils.getModuleConfig(mockPageContext);
    1767             fail("Expected ModuleConfig to not be found");
    1768         } catch (NullPointerException ignore) {
    1769             // expected result
    1770         }
    1771 
    1772         mockHttpServletRequest.setAttribute(Globals.MODULE_KEY, moduleConfig);
    1773 
    1774         mockPageContext.getServletContext().setAttribute(Globals.MODULE_KEY,
    1775             mockPageContext);
    1776 
    1777         foundModuleConfig = tagutils.getModuleConfig(mockPageContext);
    1778         assertNotNull(foundModuleConfig);
    1779     }
    1780 
    1781     // -- public Locale getUserLocale(PageContext pageContext, String locale)
    1782     public void testLocale_getUserLocale_PageContext_String() {
    1783         request.setLocale(Locale.ENGLISH);
    1784         assertEquals(tagutils.getUserLocale(pageContext, ""), Locale.ENGLISH);
    1785 
    1786         request.setLocale(Locale.CANADA);
    1787         assertEquals(tagutils.getUserLocale(pageContext, ""), Locale.CANADA);
    1788     }
    1789 
    1790     // -- public boolean is.html.md(PageContext pageContext)
    1791     public void test_boolean_is.html.md_PageContext() {
    1792         assertFalse(tagutils.is.html.md(pageContext));
    1793         pageContext.setAttribute(Globals.XHTML_KEY, "true");
    1794 
    1795         assertTrue(tagutils.is.html.md(pageContext));
    1796     }
    1797 
    1798     // -- public Object lookup(PageContext pageContext, String name, String scopeName)
    1799     // lookup with null scope
    1800     public void test_Object_lookup_PageContext_String__String1() {
    1801         pageContext.setAttribute("bean", new MockFormBean());
    1802 
    1803         try {
    1804             Object val = tagutils.lookup(pageContext, "bean", null);
    1805 
    1806             assertNotNull((val));
    1807         } catch (JspException e) {
    1808             fail("bean not found:" + e.getMessage());
    1809         }
    1810     }
    1811 
    1812     // lookup with page scope
    1813     public void test_Object_lookup_PageContext_String__String2() {
    1814         pageContext.setAttribute("bean", new MockFormBean());
    1815 
    1816         try {
    1817             Object val = tagutils.lookup(pageContext, "bean", "page");
    1818 
    1819             assertNotNull((val));
    1820         } catch (JspException e) {
    1821             fail("bean not found:" + e.getMessage());
    1822         }
    1823     }
    1824 
    1825     // lookup with invalid scope
    1826     // -- (where an exception is thrown)
    1827     public void test_Object_lookup_PageContext_String__String3() {
    1828         pageContext.setAttribute("bean", new MockFormBean());
    1829 
    1830         Object val = null;
    1831 
    1832         try {
    1833             val = tagutils.lookup(pageContext, "bean", "invalid");
    1834             fail("invalid scope :");
    1835         } catch (JspException e) {
    1836             assertNull((val));
    1837         }
    1838     }
    1839 
    1840     // try to get the call to throw an IllegalAccessException
    1841     public void test_Object_lookup_PageContext_String_String_String1() {
    1842         //        page.setAttribute("bean", new MockFormBean());
    1843         //        Object val = null;
    1844         //        try {
    1845         //            val = tagutils.lookup(page, "bean", "throwIllegalAccessException");
    1846         //            fail("should have thrown exception");
    1847         //        } catch (JspException e) {
    1848         //            assertNull(val);
    1849         //        }
    1850     }
    1851 
    1852     // try to get the call to throw an IllegalArgumentException
    1853     public void test_Object_lookup_PageContext_String_String_String2() {
    1854         pageContext.setAttribute("bean", new MockFormBean());
    1855 
    1856         Object val = null;
    1857 
    1858         try {
    1859             val = tagutils.lookup(pageContext, "bean", "doesNotExistMethod",
    1860                     "page");
    1861             fail("should have thrown exception");
    1862         } catch (JspException e) {
    1863             assertNull(val);
    1864         }
    1865     }
    1866 
    1867     // try to get the call to throw an NoSuchMethodException
    1868     public void test_Object_lookup_PageContext_String_String_String3() {
    1869         pageContext.setAttribute("bean", new MockFormBean());
    1870 
    1871         Object val = null;
    1872 
    1873         try {
    1874             val = tagutils.lookup(pageContext, "bean", "doesNotExistMethod");
    1875             fail("should have thrown exception");
    1876         } catch (JspException e) {
    1877             assertNull(val);
    1878         }
    1879     }
    1880 
    1881     /**
    1882      * Testing message()
    1883      *
    1884      * public String message( PageContext pageContext, String bundle, String
    1885      * locale, String key) throws JspException
    1886      */
    1887     public void testMessageBadParams() {
    1888         String val = null;
    1889 
    1890         try {
    1891             val = tagutils.message(pageContext, "bundle", "locale", "key");
    1892             fail("val should be null");
    1893         } catch (JspException e) {
    1894             assertNull(val);
    1895         }
    1896     }
    1897 
    1898     // set bundle in page scope
    1899     // message() assumes the bundle will never be in page scope
    1900     // -- bad key
    1901     public void donttestMessagePageBadKey() {
    1902         putBundleInScope(PageContext.PAGE_SCOPE, true);
    1903 
    1904         String val = null;
    1905 
    1906         try {
    1907             val = tagutils.message(pageContext, null, null,
    1908                     "foo.bar.does.not.exist");
    1909             fail("val should be null");
    1910         } catch (JspException e) {
    1911             assertNull(val);
    1912         }
    1913     }
    1914 
    1915     // set bundle in request scope
    1916     // -- bad key
    1917     public void testMessageRequestBadKey() {
    1918         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    1919 
    1920         String val = null;
    1921 
    1922         try {
    1923             val = tagutils.message(pageContext, null, null,
    1924                     "foo.bar.does.not.exist");
    1925             assertNull(val);
    1926         } catch (JspException e) {
    1927             fail("val should be null, no exception");
    1928         }
    1929     }
    1930 
    1931     // set bundle in session scope
    1932     // -- bad key
    1933     //
    1934     // This represents a use case where the user specifically set the bundle
    1935     //  in session under Globals.MESSAGES_KEY.
    1936     // Perhaps we should check session, and throw/log a rather explicit message
    1937     // for why this is a bad idea, instead of ignoring or returning null.
    1938     public void testMessageSessionBadKey() {
    1939         putBundleInScope(PageContext.SESSION_SCOPE, true);
    1940 
    1941         String val = null;
    1942 
    1943         try {
    1944             val = tagutils.message(pageContext, null, null,
    1945                     "foo.bar.does.not.exist");
    1946             fail("MessageResources should never be put in session scope.");
    1947         } catch (JspException e) {
    1948             assertNull(val);
    1949         }
    1950     }
    1951 
    1952     // set bundle in application scope
    1953     // -- bad key
    1954     public void testMessageApplicationBadKey() {
    1955         putBundleInScope(PageContext.APPLICATION_SCOPE, true);
    1956 
    1957         String val = null;
    1958 
    1959         try {
    1960             val = tagutils.message(pageContext, null, null,
    1961                     "foo.bar.does.not.exist");
    1962             assertNull(val);
    1963         } catch (JspException e) {
    1964             fail("val should be null, no exception");
    1965         }
    1966     }
    1967 
    1968     // set bundle in request scope
    1969     // -- good key
    1970     public void testMessageRequestGoodKey() {
    1971         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    1972 
    1973         String val = null;
    1974 
    1975         try {
    1976             val = tagutils.message(pageContext, null, null, "foo");
    1977             assertTrue("Validate message value", "bar".equals(val));
    1978         } catch (JspException e) {
    1979             fail("val should be \"bar\"");
    1980         }
    1981     }
    1982 
    1983     // set bundle in application scope
    1984     // -- good key
    1985     public void testMessageApplicationGoodKey() {
    1986         putBundleInScope(PageContext.APPLICATION_SCOPE, true);
    1987 
    1988         String val = null;
    1989 
    1990         try {
    1991             val = tagutils.message(pageContext, null, null, "foo");
    1992             assertTrue("Validate message value", "bar".equals(val));
    1993         } catch (JspException e) {
    1994             fail("val should be \"bar\"");
    1995         }
    1996     }
    1997 
    1998     /**
    1999      * Tests for:
    2000      *
    2001      * public String message( PageContext pageContext, String bundle, String
    2002      * locale, String key, Object args[]) throws JspException
    2003      */
    2004     public void testMessageRequestGoodKeyWithNullParams() {
    2005         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2006 
    2007         String[] args = null;
    2008 
    2009         String val = null;
    2010 
    2011         try {
    2012             val = tagutils.message(pageContext, null, null, "foo", args);
    2013             assertTrue("Validate message value", "bar".equals(val));
    2014         } catch (JspException e) {
    2015             fail("val should be \"bar\"");
    2016         }
    2017     }
    2018 
    2019     public void testMessageApplicationGoodKeyWithNullParams() {
    2020         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2021 
    2022         String[] args = null;
    2023 
    2024         String val = null;
    2025 
    2026         try {
    2027             val = tagutils.message(pageContext, null, null, "foo", args);
    2028             assertTrue("Validate message value", "bar".equals(val));
    2029         } catch (JspException e) {
    2030             fail("val should be \"bar\"");
    2031         }
    2032     }
    2033 
    2034     public void testMessageRequestGoodKeyWithParams() {
    2035         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2036 
    2037         String[] args = { "I love this" };
    2038 
    2039         String val = null;
    2040 
    2041         try {
    2042             val = tagutils.message(pageContext, null, null, "foo.bar", args);
    2043             assertTrue("Validate message value", "I love this bar".equals(val));
    2044         } catch (JspException e) {
    2045             fail("val should be \"bar\"");
    2046         }
    2047     }
    2048 
    2049     public void testMessageApplicationGoodKeyWithParams() {
    2050         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2051 
    2052         String[] args = { "I love this" };
    2053 
    2054         String val = null;
    2055 
    2056         try {
    2057             val = tagutils.message(pageContext, null, null, "foo.bar", args);
    2058             assertTrue("Validate message value", "I love this bar".equals(val));
    2059         } catch (JspException e) {
    2060             fail("val should be \"bar\"");
    2061         }
    2062     }
    2063 
    2064     /**
    2065      * Tests for: public boolean present( PageContext pageContext, String
    2066      * bundle, String locale, String key) throws JspException {
    2067      */
    2068     public void testPresentNulls() {
    2069         boolean result = false;
    2070 
    2071         try {
    2072             result = tagutils.present(null, null, null, null);
    2073             fail("An exception should have been thrown");
    2074         } catch (JspException e) {
    2075             fail("An npe should have been thrown");
    2076         } catch (NullPointerException e) {
    2077             assertFalse("Correct behaviour", result);
    2078         }
    2079     }
    2080 
    2081     public void testPresentBadKey() {
    2082         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2083 
    2084         boolean result = false;
    2085 
    2086         try {
    2087             result =
    2088                 tagutils.present(pageContext, null, null, "foo.bar.not.exist");
    2089             assertFalse("Value should be null", result);
    2090         } catch (JspException e) {
    2091             fail("An npe should have been thrown");
    2092         } catch (NullPointerException e) {
    2093             assertFalse("Correct behaviour", result);
    2094         }
    2095     }
    2096 
    2097     public void testPresentGoodKey() {
    2098         putBundleInScope(PageContext.REQUEST_SCOPE, true);
    2099 
    2100         boolean result = false;
    2101 
    2102         try {
    2103             result = tagutils.present(pageContext, null, null, "foo");
    2104             assertTrue("Key should have been found", result);
    2105         } catch (JspException e) {
    2106             fail("An exception should have been thrown");
    2107         }
    2108     }
    2109 
    2110     /**
    2111      * public void write(PageContext pageContext, String text) throws
    2112      * JspException {
    2113      */
    2114     public void testWriteNullParams() {
    2115         try {
    2116             tagutils.write(null, null);
    2117             fail("NullPointerException should have been thrown");
    2118         } catch (JspException e) {
    2119             fail("NullPointerException should have been thrown");
    2120         } catch (NullPointerException e) {
    2121             // pass
    2122         }
    2123     }
    2124 
    2125     public void testWrite() {
    2126         MockPageContext pg = new MockPageContext(false, false);
    2127 
    2128         try {
    2129             tagutils.write(pg, null);
    2130         } catch (JspException e) {
    2131             fail("JspException should not have been thrown");
    2132         }
    2133     }
    2134 
    2135     public void testWriteThrowException() {
    2136         MockPageContext pg = new MockPageContext(true, false);
    2137 
    2138         try {
    2139             tagutils.write(pg, null);
    2140             fail("JspException should have been thrown");
    2141         } catch (JspException e) {
    2142             // success
    2143         }
    2144     }
    2145 
    2146     public void testWritePrevious() {
    2147         MockPageContext pg = new MockPageContext(false, false);
    2148 
    2149         try {
    2150             tagutils.writePrevious(pg, null);
    2151         } catch (JspException e) {
    2152             fail("JspException should not have been thrown");
    2153         }
    2154     }
    2155 
    2156     public void testWritePreviousThrowException() {
    2157         MockPageContext pg = new MockPageContext(true, false);
    2158 
    2159         try {
    2160             tagutils.writePrevious(pg, null);
    2161             fail("JspException should have been thrown");
    2162         } catch (JspException e) {
    2163             // success
    2164         }
    2165     }
    2166 
    2167     public void testWritePreviousBody() {
    2168         MockPageContext pg = new MockPageContext(false, true);
    2169 
    2170         try {
    2171             tagutils.writePrevious(pg, null);
    2172         } catch (JspException e) {
    2173             fail("JspException should not have been thrown");
    2174         }
    2175     }
    2176 
    2177     public void testOverrideInstance(){
    2178 
    2179         class CustomTagUtils extends TagUtils{
    2180             public String filter(String value) {
    2181                 return "I HAVE BEEN OVERRIDDEN!";
    2182             }
    2183         }
    2184         // verify original logic
    2185         assertNull("Filter Test", TagUtils.getInstance().filter(null));
    2186 
    2187         // set the custom instance
    2188         TagUtils.setInstance(new CustomTagUtils());
    2189         assertEquals("Custom Instance Test", TagUtils.getInstance().filter(null), "I HAVE BEEN OVERRIDDEN!");
    2190 
    2191         // reset back to the cached instance
    2192         TagUtils.setInstance(tagutils);
    2193         assertNull("Filter Test", TagUtils.getInstance().filter(null));
    2194 
    2195     }
    2196 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
