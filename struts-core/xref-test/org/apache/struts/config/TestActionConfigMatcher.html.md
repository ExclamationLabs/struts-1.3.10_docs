
    1   /*
    2    * $Id: TestActionConfigMatcher.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import junit.framework.TestSuite;
    25  
    26  import org.apache.struts.action.ActionForward;
    27  import org.apache.struts.action.ActionMapping;
    28  import org.apache.struts.mock.TestMockBase;
    29  
    30  /**
    31   * <p>Unit tests for <code>org.apache.struts.util.ActionConfigMatcher</code>.</p>
    32   *
    33   * @version $Rev: 471754 $ $Date: 2005-10-27 23:25:01 -0400 (Thu, 27 Oct 2005)
    34   *          $
    35   */
    36  public class TestActionConfigMatcher extends TestMockBase {
    37      // ----------------------------------------------------------------- Basics
    38      public TestActionConfigMatcher(String name) {
    39          super(name);
    40      }
    41  
    42      public static void main(String[] args) {
    43          junit.awtui.TestRunner.main(new String[] {
    44                  TestActionConfigMatcher.class.getName()
    45              });
    46      }
    47  
    48      public static Test suite() {
    49          return (new TestSuite(TestActionConfigMatcher.class));
    50      }
    51  
    52      // ----------------------------------------------------- Instance Variables
    53      // ----------------------------------------------------- Setup and Teardown
    54      public void setUp() {
    55          super.setUp();
    56      }
    57  
    58      public void tearDown() {
    59          super.tearDown();
    60      }
    61  
    62      // ------------------------------------------------------- Individual Tests
    63      // ---------------------------------------------------------- match()
    64      public void testNoMatch() {
    65          ActionConfig[] configs = new ActionConfig[1];
    66          ActionConfig mapping = buildActionConfig("/foo");
    67  
    68          configs[0] = mapping;
    69  
    70          ActionConfigMatcher matcher = new ActionConfigMatcher(configs);
    71  
    72          assertNull("ActionConfig shouldn't be matched", matcher.match("/test"));
    73      }
    74  
    75      public void testNoWildcardMatch() {
    76          ActionConfig[] configs = new ActionConfig[1];
    77          ActionConfig mapping = buildActionConfig("/fooBar");
    78  
    79          configs[0] = mapping;
    80  
    81          ActionConfigMatcher matcher = new ActionConfigMatcher(configs);
    82  
    83          assertNull("ActionConfig shouldn't be matched", matcher.match("/fooBar"));
    84      }
    85  
    86      public void testShouldMatch() {
    87          ActionConfig[] configs = new ActionConfig[1];
    88          ActionConfig mapping = buildActionConfig("/foo*");
    89  
    90          configs[0] = mapping;
    91  
    92          ActionConfigMatcher matcher = new ActionConfigMatcher(configs);
    93  
    94          ActionConfig matched = matcher.match("/fooBar");
    95  
    96          assertNotNull("ActionConfig should be matched", matched);
    97          assertTrue("ActionConfig should have two action forward",
    98              matched.findForwardConfigs().length == 2);
    99          assertTrue("ActionConfig should have two exception forward",
    100             matched.findExceptionConfigs().length == 2);
    101         assertTrue("ActionConfig should have properties",
    102             matched.getProperties().size() == 2);
    103     }
    104 
    105     public void testCheckSubstitutionsMatch() {
    106         ActionConfig[] configs = new ActionConfig[1];
    107         ActionConfig mapping = buildActionConfig("/foo*");
    108 
    109         configs[0] = mapping;
    110 
    111         ActionConfigMatcher matcher = new ActionConfigMatcher(configs);
    112         ActionConfig m = matcher.match("/fooBar");
    113 
    114         assertTrue("Name hasn't been replaced", "name,Bar".equals(m.getName()));
    115         assertTrue("Path hasn't been replaced", "/fooBar".equals(m.getPath()));
    116         assertTrue("Scope isn't correct", "request".equals(m.getScope()));
    117         assertTrue("Unknown isn't correct", !m.getUnknown());
    118         assertTrue("Validate isn't correct", m.getValidate());
    119 
    120         assertTrue("Prefix hasn't been replaced",
    121             "foo,Bar".equals(m.getPrefix()));
    122         assertTrue("Suffix hasn't been replaced",
    123             "bar,Bar".equals(m.getSuffix()));
    124         assertTrue("Type hasn't been replaced",
    125             "foo.bar.BarAction".equals(m.getType()));
    126         assertTrue("Roles hasn't been replaced",
    127             "public,Bar".equals(m.getRoles()));
    128         assertTrue("Parameter hasn't been replaced",
    129             "param,Bar".equals(m.getParameter()));
    130         assertTrue("Attribute hasn't been replaced",
    131             "attrib,Bar".equals(m.getAttribute()));
    132         assertTrue("Forward hasn't been replaced",
    133             "fwd,Bar".equals(m.getForward()));
    134         assertTrue("Include hasn't been replaced",
    135             "include,Bar".equals(m.getInclude()));
    136         assertTrue("Input hasn't been replaced",
    137             "input,Bar".equals(m.getInput()));
    138 
    139         assertTrue("ActionConfig property not replaced",
    140             "testBar".equals(m.getProperty("testprop2")));
    141 
    142         ForwardConfig[] fConfigs = m.findForwardConfigs();
    143         boolean found = false;
    144 
    145         for (int x = 0; x < fConfigs.length; x++) {
    146             ForwardConfig cfg = fConfigs[x];
    147 
    148             if ("name".equals(cfg.getName())) {
    149                 found = true;
    150                 assertTrue("Path hasn't been replaced",
    151                     "path,Bar".equals(cfg.getPath()));
    152                 assertTrue("Property foo hasn't been replaced",
    153                     "bar,Bar".equals(cfg.getProperty("foo")));
    154                 assertTrue("Module hasn't been replaced",
    155                     "modBar".equals(cfg.getModule()));
    156             }
    157         }
    158 
    159         assertTrue("The forward config 'name' cannot be found", found);
    160     }
    161 
    162     public void testCheckMultipleSubstitutions() {
    163         ActionMapping[] mapping = new ActionMapping[1];
    164 
    165         mapping[0] = new ActionMapping();
    166         mapping[0].setPath("/foo*");
    167         mapping[0].setName("name,{1}-{1}");
    168 
    169         ActionConfigMatcher matcher = new ActionConfigMatcher(mapping);
    170         ActionConfig m = matcher.match("/fooBar");
    171 
    172         assertTrue("Name hasn't been replaced correctly: " + m.getName(),
    173             "name,Bar-Bar".equals(m.getName()));
    174     }
    175 
    176     private ActionConfig buildActionConfig(String path) {
    177         ActionMapping mapping = new ActionMapping();
    178 
    179         mapping.setName("name,{1}");
    180         mapping.setPath(path);
    181         mapping.setScope("request");
    182         mapping.setUnknown(false);
    183         mapping.setValidate(true);
    184 
    185         mapping.setPrefix("foo,{1}");
    186         mapping.setSuffix("bar,{1}");
    187 
    188         mapping.setType("foo.bar.{1}Action");
    189         mapping.setRoles("public,{1}");
    190         mapping.setParameter("param,{1}");
    191         mapping.setAttribute("attrib,{1}");
    192         mapping.setForward("fwd,{1}");
    193         mapping.setInclude("include,{1}");
    194         mapping.setInput("input,{1}");
    195 
    196         ForwardConfig cfg = new ActionForward();
    197 
    198         cfg.setName("name");
    199         cfg.setPath("path,{1}");
    200         cfg.setModule("mod{1}");
    201         cfg.setProperty("foo", "bar,{1}");
    202         mapping.addForwardConfig(cfg);
    203 
    204         cfg = new ActionForward();
    205         cfg.setName("name2");
    206         cfg.setPath("path2");
    207         cfg.setModule("mod{1}");
    208         mapping.addForwardConfig(cfg);
    209 
    210         ExceptionConfig excfg = new ExceptionConfig();
    211 
    212         excfg.setKey("foo");
    213         excfg.setType("foo.Bar");
    214         excfg.setPath("path");
    215         mapping.addExceptionConfig(excfg);
    216 
    217         excfg = new ExceptionConfig();
    218         excfg.setKey("foo2");
    219         excfg.setType("foo.Bar2");
    220         excfg.setPath("path2");
    221         mapping.addExceptionConfig(excfg);
    222 
    223         mapping.setProperty("testprop", "testval");
    224         mapping.setProperty("testprop2", "test{1}");
    225 
    226         mapping.freeze();
    227 
    228         return mapping;
    229     }
    230 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
