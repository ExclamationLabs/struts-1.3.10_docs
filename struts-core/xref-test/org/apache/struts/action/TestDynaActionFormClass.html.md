
    1   /*
    2    * $Id: TestDynaActionFormClass.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import org.apache.commons.beanutils.DynaProperty;
    28  import org.apache.struts.config.FormBeanConfig;
    29  import org.apache.struts.config.FormPropertyConfig;
    30  
    31  /**
    32   * Suite of unit tests for the <code>org.apache.struts.action.DynaActionFormClass</code>
    33   * class.
    34   */
    35  public class TestDynaActionFormClass extends TestCase {
    36      /**
    37       * The set of <code>FormPropertyConfig</code> objects to use when creating
    38       * our <code>FormBeanConfig</code>.
    39       */
    40      protected static final FormPropertyConfig[] dynaProperties =
    41          {
    42              new FormPropertyConfig("booleanProperty", "boolean", "true", "true"),
    43              new FormPropertyConfig("booleanSecond", "boolean", "true", "true"),
    44              new FormPropertyConfig("doubleProperty", "double", "321.0", "GET"),
    45              new FormPropertyConfig("floatProperty", "float", "123.0",
    46                  "POST, HEAD"),
    47              new FormPropertyConfig("intArray", "int[]",
    48                  "{ 0, 10,20, \"30\" '40' }"),
    49              new FormPropertyConfig("intIndexed", "int[]",
    50                  " 0 100, 200, 300, 400 "),
    51              new FormPropertyConfig("intProperty", "int", "123"),
    52              new FormPropertyConfig("listIndexed", "java.util.List", null),
    53              new FormPropertyConfig("longProperty", "long", "321"),
    54              new FormPropertyConfig("mappedProperty", "java.util.Map", null),
    55              new FormPropertyConfig("mappedIntProperty", "java.util.Map", null),
    56  
    57  
    58              //        new FormPropertyConfig("nullProperty", "java.lang.String", null),
    59              new FormPropertyConfig("shortProperty", "short", "987"),
    60              new FormPropertyConfig("stringArray", "java.lang.String[]",
    61                  "{ 'String 0', 'String 1', 'String 2', 'String 3', 'String 4'}"),
    62              new FormPropertyConfig("stringIndexed", "java.lang.String[]",
    63                  "{ 'String 0', 'String 1', 'String 2', 'String 3', 'String 4'}"),
    64              new FormPropertyConfig("stringProperty", "java.lang.String",
    65                  "This is a string"),
    66          };
    67  
    68      // ----------------------------------------------------- Instance Variables
    69  
    70      /**
    71       * The <code>FormBeanConfig</code> structure for the form bean we will be
    72       * creating.
    73       */
    74      protected FormBeanConfig beanConfig = null;
    75  
    76      /**
    77       * The <code>DynaActionFormClass</code> to use for testing.
    78       */
    79      protected DynaActionFormClass dynaClass = null;
    80  
    81      /**
    82       * Defines the testcase name for JUnit.
    83       *
    84       * @param theName the testcase's name.
    85       */
    86      public TestDynaActionFormClass(String theName) {
    87          super(theName);
    88      }
    89  
    90      /**
    91       * Start the tests.
    92       *
    93       * @param theArgs the arguments. Not used
    94       */
    95      public static void main(String[] theArgs) {
    96          junit.awtui.TestRunner.main(new String[] {
    97                  TestDynaActionFormClass.class.getName()
    98              });
    99      }
    100 
    101     /**
    102      * @return a test suite (<code>TestSuite</code>) that includes all methods
    103      *         starting with "test"
    104      */
    105     public static Test suite() {
    106         // All methods starting with "test" will be executed in the test suite.
    107         return new TestSuite(TestDynaActionFormClass.class);
    108     }
    109 
    110     // ----------------------------------------------------- Setup and Teardown
    111     public void setUp() {
    112         // Construct a FormBeanConfig to be used
    113         beanConfig = new FormBeanConfig();
    114         beanConfig.setName("dynaForm");
    115         beanConfig.setType("org.apache.struts.action.DynaActionForm");
    116 
    117         // Add relevant property definitions
    118         for (int i = 0; i < dynaProperties.length; i++) {
    119             beanConfig.addFormPropertyConfig(dynaProperties[i]);
    120         }
    121 
    122         // Construct a corresponding DynaActionFormClass
    123         dynaClass = new DynaActionFormClass(beanConfig);
    124     }
    125 
    126     public void tearDown() {
    127         dynaClass = null;
    128         beanConfig = null;
    129     }
    130 
    131     // -------------------------------------------------- Verify FormBeanConfig
    132     // Check for ability to add a property before and after freezing
    133     public void testConfigAdd() {
    134         FormPropertyConfig prop = null;
    135 
    136         // Before freezing
    137         prop = beanConfig.findFormPropertyConfig("fooProperty");
    138         assertNull("fooProperty not found", prop);
    139         beanConfig.addFormPropertyConfig(new FormPropertyConfig("fooProperty",
    140                 "java.lang.String", ""));
    141         prop = beanConfig.findFormPropertyConfig("fooProperty");
    142         assertNotNull("fooProperty found", prop);
    143 
    144         // after freezing
    145         beanConfig.freeze();
    146         prop = beanConfig.findFormPropertyConfig("barProperty");
    147         assertNull("barProperty not found", prop);
    148 
    149         try {
    150             beanConfig.addFormPropertyConfig(new FormPropertyConfig(
    151                     "barProperty", "java.lang.String", ""));
    152             fail("barProperty add not prevented");
    153         } catch (IllegalStateException e) {
    154             ; // Expected result
    155         }
    156     }
    157 
    158     // Check basic FormBeanConfig properties
    159     public void testConfigCreate() {
    160         assertTrue("dynamic is correct", beanConfig.getDynamic());
    161         assertEquals("name is correct", "dynaForm", beanConfig.getName());
    162         assertEquals("type is correct",
    163             "org.apache.struts.action.DynaActionForm", beanConfig.getType());
    164     }
    165 
    166     // Check attempts to add a duplicate property name
    167     public void testConfigDuplicate() {
    168         FormPropertyConfig prop = null;
    169 
    170         assertNull("booleanProperty is found", prop);
    171 
    172         try {
    173             beanConfig.addFormPropertyConfig(new FormPropertyConfig(
    174                     "booleanProperty", "java.lang.String", ""));
    175             fail("Adding duplicate property not prevented");
    176         } catch (IllegalArgumentException e) {
    177             ; // Expected result
    178         }
    179     }
    180 
    181     // Check the configured FormPropertyConfig element initial values
    182     public void testConfigInitialValues() {
    183         assertEquals("booleanProperty value", Boolean.TRUE,
    184             beanConfig.findFormPropertyConfig("booleanProperty").initial());
    185         assertEquals("booleanSecond value", Boolean.TRUE,
    186             beanConfig.findFormPropertyConfig("booleanSecond").initial());
    187         assertEquals("doubleProperty value", new Double(321.0),
    188             beanConfig.findFormPropertyConfig("doubleProperty").initial());
    189         assertEquals("floatProperty value", new Float((float) 123.0),
    190             beanConfig.findFormPropertyConfig("floatProperty").initial());
    191         assertEquals("intProperty value", new Integer(123),
    192             beanConfig.findFormPropertyConfig("intProperty").initial());
    193 
    194         // FIXME - listIndexed
    195         assertEquals("longProperty value", new Long(321),
    196             beanConfig.findFormPropertyConfig("longProperty").initial());
    197 
    198         // FIXME - mappedProperty
    199         // FIXME - mappedIntProperty
    200         //        assertNull("nullProperty value",
    201         //                   beanConfig.findFormPropertyConfig("nullProperty").initial());
    202         assertEquals("shortProperty value", new Short((short) 987),
    203             beanConfig.findFormPropertyConfig("shortProperty").initial());
    204 
    205         // FIXME - stringArray
    206         // FIXME - stringIndexed
    207         assertEquals("stringProperty value", "This is a string",
    208             beanConfig.findFormPropertyConfig("stringProperty").initial());
    209     }
    210 
    211     // Check the configured FormPropertyConfig element properties
    212     public void testConfigProperties() {
    213         for (int i = 0; i < dynaProperties.length; i++) {
    214             FormPropertyConfig dynaProperty =
    215                 beanConfig.findFormPropertyConfig(dynaProperties[i].getName());
    216 
    217             assertNotNull("Found dynaProperty " + dynaProperties[i].getName(),
    218                 dynaProperty);
    219             assertEquals("dynaProperty name for " + dynaProperties[i].getName(),
    220                 dynaProperties[i].getName(), dynaProperty.getName());
    221             assertEquals("dynaProperty type for " + dynaProperties[i].getName(),
    222                 dynaProperties[i].getType(), dynaProperty.getType());
    223             assertEquals("dynaProperty initial for "
    224                 + dynaProperties[i].getName(), dynaProperties[i].getInitial(),
    225                 dynaProperty.getInitial());
    226         }
    227     }
    228 
    229     // Check for ability to remove a property before and after freezing
    230     public void testConfigRemove() {
    231         FormPropertyConfig prop = null;
    232 
    233         // Before freezing
    234         prop = beanConfig.findFormPropertyConfig("booleanProperty");
    235         assertNotNull("booleanProperty found", prop);
    236         beanConfig.removeFormPropertyConfig(prop);
    237         prop = beanConfig.findFormPropertyConfig("booleanProperty");
    238         assertNull("booleanProperty not deleted", prop);
    239 
    240         // after freezing
    241         beanConfig.freeze();
    242         prop = beanConfig.findFormPropertyConfig("booleanSecond");
    243         assertNotNull("booleanSecond found", prop);
    244 
    245         try {
    246             beanConfig.removeFormPropertyConfig(prop);
    247             fail("booleanSecond remove not prevented");
    248         } catch (IllegalStateException e) {
    249             ; // Expected result
    250         }
    251     }
    252 
    253     // --------------------------------------------- Create DynaActionFormClass
    254     // Test basic DynaActionFormClass name and properties
    255     public void testClassCreate() {
    256         assertEquals("name", "dynaForm", dynaClass.getName());
    257 
    258         for (int i = 0; i < dynaProperties.length; i++) {
    259             DynaProperty prop =
    260                 dynaClass.getDynaProperty(dynaProperties[i].getName());
    261 
    262             assertNotNull("Found property " + dynaProperties[i].getName());
    263             assertEquals("Class for property " + dynaProperties[i].getName(),
    264                 dynaProperties[i].getTypeClass(), prop.getType());
    265         }
    266     }
    267 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
