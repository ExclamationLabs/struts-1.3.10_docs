
    1   /*
    2    * $Id: TestModuleConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import org.apache.commons.digester.Digester;
    28  
    29  import java.io.InputStream;
    30  
    31  /**
    32   * Unit tests for the <code>org.apache.struts.config</code> package.
    33   *
    34   * @version $Rev: 471754 $ $Date: 2005-03-01 20:26:14 -0500 (Tue, 01 Mar 2005)
    35   *          $
    36   */
    37  public class TestModuleConfig extends TestCase {
    38      // ----------------------------------------------------- Instance Variables
    39  
    40      /**
    41       * The ModuleConfig we are testing.
    42       */
    43      protected ModuleConfig config = null;
    44  
    45      // ----------------------------------------------------------- Constructors
    46  
    47      /**
    48       * Construct a new instance of this test case.
    49       *
    50       * @param name Name of the test case
    51       */
    52      public TestModuleConfig(String name) {
    53          super(name);
    54      }
    55  
    56      // --------------------------------------------------------- Public Methods
    57  
    58      /**
    59       * Set up instance variables required by this test case.
    60       */
    61      public void setUp() {
    62          ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    63  
    64          config = factoryObject.createModuleConfig("");
    65      }
    66  
    67      /**
    68       * Return the tests included in this test suite.
    69       */
    70      public static Test suite() {
    71          return (new TestSuite(TestModuleConfig.class));
    72      }
    73  
    74      /**
    75       * Tear down instance variables required by this test case.
    76       */
    77      public void tearDown() {
    78          config = null;
    79      }
    80  
    81      // ------------------------------------------------ Individual Test Methods
    82      private void parseConfig(String publicId, String entityURL,
    83          String strutsConfig) {
    84          // Prepare a Digester for parsing a struts-config.xml file
    85          Digester digester = new Digester();
    86  
    87          digester.push(config);
    88          digester.setNamespaceAware(true);
    89          digester.setValidating(true);
    90          digester.addRuleSet(new ConfigRuleSet());
    91          digester.register(publicId,
    92              this.getClass().getResource(entityURL).toString());
    93  
    94          // Parse the test struts-config.xml file
    95          try {
    96              InputStream input =
    97                  this.getClass().getResourceAsStream(strutsConfig);
    98  
    99              assertNotNull("Got an input stream for " + strutsConfig, input);
    100             digester.parse(input);
    101             input.close();
    102         } catch (Throwable t) {
    103             t.printStackTrace(System.out);
    104             fail("Parsing threw exception:  " + t);
    105         }
    106     }
    107 
    108     /**
    109      * Test parsing of a struts-config.xml file.
    110      */
    111     public void testParse() {
    112         testParseBase("-//Apache Software Foundation//DTD Struts Configuration 1.2//EN",
    113             "/org/apache/struts/resources/struts-config_1_2.dtd",
    114             "/org/apache/struts/config/struts-config.xml");
    115     }
    116 
    117     public void testParse1_1() {
    118         testParseBase("-//Apache Software Foundation//DTD Struts Configuration 1.1//EN",
    119             "/org/apache/struts/resources/struts-config_1_1.dtd",
    120             "/org/apache/struts/config/struts-config-1.1.xml");
    121     }
    122 
    123     public void testParseBase(String publicId, String entityURL,
    124         String strutsConfig) {
    125         parseConfig(publicId, entityURL, strutsConfig);
    126 
    127         // Perform assertion tests on the parsed information
    128         FormBeanConfig[] fbcs = config.findFormBeanConfigs();
    129 
    130         assertNotNull("Found our form bean configurations", fbcs);
    131         assertEquals("Found three form bean configurations", 3, fbcs.length);
    132 
    133         ForwardConfig[] fcs = config.findForwardConfigs();
    134 
    135         assertNotNull("Found our forward configurations", fcs);
    136         assertEquals("Found three forward configurations", 3, fcs.length);
    137 
    138         ActionConfig logon = config.findActionConfig("/logon");
    139 
    140         assertNotNull("Found logon action configuration", logon);
    141         assertEquals("Found correct logon configuration", "logonForm",
    142             logon.getName());
    143     }
    144 
    145     /**
    146      * Tests a struts-config.xml that contains a custom mapping and property.
    147      */
    148     public void testCustomMappingParse() {
    149         // Prepare a Digester for parsing a struts-config.xml file
    150         testCustomMappingParseBase("-//Apache Software Foundation//DTD Struts Configuration 1.2//EN",
    151             "/org/apache/struts/resources/struts-config_1_2.dtd",
    152             "/org/apache/struts/config/struts-config-custom-mapping.xml");
    153     }
    154 
    155     /**
    156      * Tests a struts-config.xml that contains a custom mapping and property.
    157      */
    158     public void testCustomMappingParse1_1() {
    159         // Prepare a Digester for parsing a struts-config.xml file
    160         testCustomMappingParseBase("-//Apache Software Foundation//DTD Struts Configuration 1.1//EN",
    161             "/org/apache/struts/resources/struts-config_1_1.dtd",
    162             "/org/apache/struts/config/struts-config-custom-mapping-1.1.xml");
    163     }
    164 
    165     /**
    166      * Tests a struts-config.xml that contains a custom mapping and property.
    167      */
    168     private void testCustomMappingParseBase(String publicId, String entityURL,
    169         String strutsConfig) {
    170         parseConfig(publicId, entityURL, strutsConfig);
    171 
    172         // Perform assertion tests on the parsed information
    173         CustomMappingTest map =
    174             (CustomMappingTest) config.findActionConfig("/editRegistration");
    175 
    176         assertNotNull("Cannot find editRegistration mapping", map);
    177         assertTrue("The custom mapping attribute has not been set",
    178             map.getPublic());
    179     }
    180 
    181     /**
    182      * Test order of action mappings defined perserved.
    183      */
    184     public void testPreserveActionMappingsOrder() {
    185         parseConfig("-//Apache Software Foundation//DTD Struts Configuration 1.2//EN",
    186             "/org/apache/struts/resources/struts-config_1_2.dtd",
    187             "/org/apache/struts/config/struts-config.xml");
    188 
    189         String[] paths =
    190             new String[] {
    191                 "/editRegistration", "/editSubscription", "/logoff", "/logon",
    192                 "/saveRegistration", "/saveSubscription", "/tour"
    193             };
    194 
    195         ActionConfig[] actions = config.findActionConfigs();
    196 
    197         for (int x = 0; x < paths.length; x++) {
    198             assertTrue("Action config out of order:" + actions[x].getPath(),
    199                 paths[x].equals(actions[x].getPath()));
    200         }
    201     }
    202 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
