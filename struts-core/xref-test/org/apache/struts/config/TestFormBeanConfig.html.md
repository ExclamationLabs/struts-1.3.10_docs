
    1   /*
    2    * $Id: TestFormBeanConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    30   * Unit tests for the <code>org.apache.struts.config.FormBeanConfig</code>
    31   * class.  Currently only contains code to test the methods that support
    32   * configuration inheritance.
    33   *
    34   * @version $Rev: 471754 $ $Date: 2005-05-25 19:35:00 -0400 (Wed, 25 May 2005)
    35   *          $
    36   */
    37  public class TestFormBeanConfig extends TestCase {
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
    48      protected FormBeanConfig baseForm = null;
    49  
    50      // ----------------------------------------------------------- Constructors
    51  
    52      /**
    53       * Construct a new instance of this test case.
    54       *
    55       * @param name Name of the test case
    56       */
    57      public TestFormBeanConfig(String name) {
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
    72          baseForm = new FormBeanConfig();
    73          baseForm.setName("baseForm");
    74          baseForm.setType("org.apache.struts.action.DynaActionForm");
    75  
    76          // set up id, name, and score
    77          FormPropertyConfig property = new FormPropertyConfig();
    78  
    79          property.setName("id");
    80          property.setType("java.lang.String");
    81          baseForm.addFormPropertyConfig(property);
    82  
    83          property = new FormPropertyConfig();
    84          property.setName("name");
    85          property.setType("java.lang.String");
    86          property.setProperty("count", "10");
    87          baseForm.addFormPropertyConfig(property);
    88  
    89          property = new FormPropertyConfig();
    90          property.setName("score");
    91          property.setType("java.lang.String");
    92          baseForm.addFormPropertyConfig(property);
    93  
    94          property = new FormPropertyConfig();
    95          property.setName("message");
    96          property.setType("java.lang.String");
    97          baseForm.addFormPropertyConfig(property);
    98  
    99          // register it to our config
    100         config.addFormBeanConfig(baseForm);
    101     }
    102 
    103     /**
    104      * Return the tests included in this test suite.
    105      */
    106     public static Test suite() {
    107         return (new TestSuite(TestFormBeanConfig.class));
    108     }
    109 
    110     /**
    111      * Tear down instance variables required by this test case.
    112      */
    113     public void tearDown() {
    114         config = null;
    115         baseForm = null;
    116     }
    117 
    118     // ------------------------------------------------------- Individual Tests
    119 
    120     /**
    121      * Basic check that shouldn't detect an error.
    122      */
    123     public void testCheckCircularInheritance() {
    124         FormBeanConfig child = new FormBeanConfig();
    125 
    126         child.setName("child");
    127         child.setExtends("baseForm");
    128 
    129         FormBeanConfig grandChild = new FormBeanConfig();
    130 
    131         grandChild.setName("grandChild");
    132         grandChild.setExtends("child");
    133 
    134         config.addFormBeanConfig(child);
    135         config.addFormBeanConfig(grandChild);
    136 
    137         assertTrue("Circular inheritance shouldn't have been detected",
    138             !grandChild.checkCircularInheritance(config));
    139     }
    140 
    141     /**
    142      * Basic check that SHOULD detect an error.
    143      */
    144     public void testCheckCircularInheritanceError() {
    145         FormBeanConfig child = new FormBeanConfig();
    146 
    147         child.setName("child");
    148         child.setExtends("baseForm");
    149 
    150         FormBeanConfig grandChild = new FormBeanConfig();
    151 
    152         grandChild.setName("grandChild");
    153         grandChild.setExtends("child");
    154 
    155         // establish the circular relationship with base
    156         baseForm.setExtends("grandChild");
    157 
    158         config.addFormBeanConfig(child);
    159         config.addFormBeanConfig(grandChild);
    160 
    161         assertTrue("Circular inheritance should've been detected",
    162             grandChild.checkCircularInheritance(config));
    163     }
    164 
    165     /**
    166      * Test that processExtends() makes sure that a base form's own extension
    167      * has been processed.
    168      */
    169     public void testProcessExtendsBaseFormExtends()
    170         throws Exception {
    171         CustomFormBeanConfig first = new CustomFormBeanConfig();
    172 
    173         first.setName("first");
    174 
    175         CustomFormBeanConfig second = new CustomFormBeanConfig();
    176 
    177         second.setName("second");
    178         second.setExtends("first");
    179 
    180         config.addFormBeanConfig(first);
    181         config.addFormBeanConfig(second);
    182 
    183         // set baseForm to extend second
    184         baseForm.setExtends("second");
    185 
    186         baseForm.processExtends(config);
    187 
    188         assertTrue("The first form's processExtends() wasn't called",
    189             first.processExtendsCalled);
    190         assertTrue("The second form's processExtends() wasn't called",
    191             second.processExtendsCalled);
    192     }
    193 
    194     /**
    195      * Make sure that correct exception is thrown if a base form can't be
    196      * found.
    197      */
    198     public void testProcessExtendsMissingBaseForm()
    199         throws Exception {
    200         baseForm.setExtends("someMissingForm");
    201 
    202         try {
    203             baseForm.processExtends(config);
    204             fail(
    205                 "An exception should be thrown if a super form can't be found.");
    206         } catch (NullPointerException e) {
    207             // succeed
    208         } catch (InstantiationException e) {
    209             fail("Unrecognized exception thrown.");
    210         }
    211     }
    212 
    213     /**
    214      * Test a typical form bean configuration extension where various
    215      * properties should be inherited from a base form.  This method checks
    216      * all the properties.
    217      */
    218     public void testInheritFrom()
    219         throws Exception {
    220         // give baseForm some arbitrary parameters
    221         String baseFormCount = "1";
    222 
    223         baseForm.setProperty("count", baseFormCount);
    224 
    225         // create a basic subform
    226         FormBeanConfig subForm = new FormBeanConfig();
    227         String subFormName = "subForm";
    228 
    229         subForm.setName(subFormName);
    230         subForm.setExtends("baseForm");
    231 
    232         // override score
    233         FormPropertyConfig property = new FormPropertyConfig();
    234 
    235         property.setName("score");
    236         property.setType("java.lang.Integer");
    237         subForm.addFormPropertyConfig(property);
    238 
    239         // ... and id
    240         property = new FormPropertyConfig();
    241         property.setName("id");
    242         property.setType("java.lang.String");
    243         property.setInitial("unknown");
    244         subForm.addFormPropertyConfig(property);
    245 
    246         // ... and message
    247         property = new FormPropertyConfig();
    248         property.setName("message");
    249         property.setType("java.lang.String");
    250         property.setSize(10);
    251         subForm.addFormPropertyConfig(property);
    252 
    253         config.addFormBeanConfig(subForm);
    254 
    255         subForm.inheritFrom(baseForm);
    256 
    257         // check that our subForm is still the one in the config
    258         assertSame("subForm no longer in ModuleConfig", subForm,
    259             config.findFormBeanConfig("subForm"));
    260 
    261         // check our configured sub form
    262         assertNotNull("Form bean type was not inherited", subForm.getType());
    263         assertEquals("Wrong form bean name", subFormName, subForm.getName());
    264         assertEquals("Wrong form bean type", baseForm.getType(),
    265             subForm.getType());
    266         assertEquals("Wrong restricted value", baseForm.isRestricted(),
    267             subForm.isRestricted());
    268 
    269         FormPropertyConfig[] formPropertyConfigs =
    270             subForm.findFormPropertyConfigs();
    271 
    272         assertEquals("Wrong prop count", 4, formPropertyConfigs.length);
    273 
    274         // we want to check that the form is EXACTLY as we want it, so
    275         //  here are some fine grain checks
    276         property = subForm.findFormPropertyConfig("name");
    277 
    278         FormPropertyConfig original = baseForm.findFormPropertyConfig("name");
    279 
    280         assertNotNull("'name' property was not inherited", property);
    281         assertEquals("Wrong type for name", original.getType(),
    282             property.getType());
    283         assertEquals("Wrong initial value for name", original.getInitial(),
    284             property.getInitial());
    285         assertEquals("Wrong size value for name", original.getSize(),
    286             property.getSize());
    287 
    288         property = subForm.findFormPropertyConfig("id");
    289         original = baseForm.findFormPropertyConfig("id");
    290         assertNotNull("'id' property was not found", property);
    291         assertEquals("Wrong type for id", original.getType(), property.getType());
    292         assertEquals("Wrong initial value for id", "unknown",
    293             property.getInitial());
    294         assertEquals("Wrong size value for id", original.getSize(),
    295             property.getSize());
    296 
    297         property = subForm.findFormPropertyConfig("score");
    298         original = baseForm.findFormPropertyConfig("score");
    299         assertNotNull("'score' property was not found", property);
    300         assertEquals("Wrong type for score", "java.lang.Integer",
    301             property.getType());
    302         assertEquals("Wrong initial value for score", original.getInitial(),
    303             property.getInitial());
    304         assertEquals("Wrong size value for score", original.getSize(),
    305             property.getSize());
    306 
    307         property = subForm.findFormPropertyConfig("message");
    308         original = baseForm.findFormPropertyConfig("message");
    309         assertNotNull("'message' property was not found", property);
    310         assertEquals("Wrong type for message", original.getType(),
    311             property.getType());
    312         assertEquals("Wrong initial value for message", original.getInitial(),
    313             property.getInitial());
    314         assertEquals("Wrong size value for message", 10, property.getSize());
    315 
    316         property = subForm.findFormPropertyConfig("name");
    317         original = baseForm.findFormPropertyConfig("name");
    318         assertEquals("Arbitrary property not found",
    319             original.getProperty("count"), property.getProperty("count"));
    320 
    321         String count = subForm.getProperty("count");
    322 
    323         assertEquals("Arbitrary property was not inherited", baseFormCount,
    324             count);
    325     }
    326 
    327     /**
    328      * Used to detect that FormBeanConfig is making the right calls.
    329      */
    330     public static class CustomFormBeanConfig extends FormBeanConfig {
    331         boolean processExtendsCalled = false;
    332 
    333         public void processExtends(ModuleConfig moduleConfig)
    334             throws ClassNotFoundException, IllegalAccessException,
    335                 InstantiationException, InvocationTargetException {
    336             super.processExtends(moduleConfig);
    337             processExtendsCalled = true;
    338         }
    339     }
    340 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
