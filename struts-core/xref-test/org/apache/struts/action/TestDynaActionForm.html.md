
    1   /*
    2    * $Id: TestDynaActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import junit.framework.TestSuite;
    25  
    26  import org.apache.commons.beanutils.DynaProperty;
    27  import org.apache.commons.logging.Log;
    28  import org.apache.commons.logging.LogFactory;
    29  import org.apache.struts.config.FormBeanConfig;
    30  import org.apache.struts.config.ModuleConfig;
    31  import org.apache.struts.config.impl.ModuleConfigImpl;
    32  import org.apache.struts.mock.MockHttpServletRequest;
    33  
    34  import java.util.ArrayList;
    35  import java.util.HashMap;
    36  import java.util.List;
    37  import java.util.Map;
    38  
    39  /**
    40   * Suite of unit tests for the <code>org.apache.struts.action.DynaActionForm</code>
    41   * class.
    42   */
    43  public class TestDynaActionForm extends TestDynaActionFormClass {
    44      /**
    45       * The set of property names we expect to have returned when calling
    46       * <code>getDynaProperties()</code>.  You should update this list when new
    47       * properties are added to TestBean.
    48       */
    49      protected final static String[] properties =
    50          {
    51              "booleanProperty", "booleanSecond", "doubleProperty",
    52              "floatProperty", "intArray", "intIndexed", "intProperty",
    53              "listIndexed", "longProperty", "mappedProperty", "mappedIntProperty",
    54  
    55  
    56              //        "nullProperty",
    57              "shortProperty", "stringArray", "stringIndexed", "stringProperty",
    58          };
    59  
    60      // ----------------------------------------------------- Instance Variables
    61  
    62      /**
    63       * Dummy ModuleConfig for calls to reset() and validate().
    64       */
    65      protected ModuleConfig moduleConfig = null;
    66  
    67      /**
    68       * The basic <code>DynaActionForm</code> to use for testing.
    69       */
    70      protected DynaActionForm dynaForm = null;
    71  
    72      /**
    73       * Dummy ActionMapping for calls to reset() and validate().
    74       */
    75      protected ActionMapping mapping = null;
    76      protected Log log = null;
    77  
    78      /**
    79       * Defines the testcase name for JUnit.
    80       *
    81       * @param theName the testcase's name.
    82       */
    83      public TestDynaActionForm(String theName) {
    84          super(theName);
    85      }
    86  
    87      /**
    88       * Start the tests.
    89       *
    90       * @param theArgs the arguments. Not used
    91       */
    92      public static void main(String[] theArgs) {
    93          junit.awtui.TestRunner.main(new String[] {
    94                  TestDynaActionForm.class.getName()
    95              });
    96      }
    97  
    98      /**
    99       * @return a test suite (<code>TestSuite</code>) that includes all methods
    100      *         starting with "test"
    101      */
    102     public static Test suite() {
    103         // All methods starting with "test" will be executed in the test suite.
    104         return new TestSuite(TestDynaActionForm.class);
    105     }
    106 
    107     // ----------------------------------------------------- Setup and Teardown
    108     public void setUp() {
    109         super.setUp();
    110 
    111         try {
    112             dynaForm = (DynaActionForm) dynaClass.newInstance();
    113         } catch (IllegalAccessException e) {
    114             throw new RuntimeException(e.getMessage());
    115         } catch (InstantiationException e) {
    116             throw new RuntimeException(e.getMessage());
    117         }
    118 
    119         setupComplexProperties();
    120         moduleConfig = new DynaActionFormConfig(beanConfig);
    121         mapping = new DynaActionFormMapping(moduleConfig);
    122         log = LogFactory.getLog(this.getClass().getName() + "."
    123                 + this.getName());
    124     }
    125 
    126     public void tearDown() {
    127         super.tearDown();
    128         moduleConfig = null;
    129         dynaForm = null;
    130         mapping = null;
    131     }
    132 
    133     // --------------------------------------------- Create New DynaActionForms
    134     // Test basic form bean properties on creation
    135     public void testBeanCreate() {
    136         assertEquals("booleanProperty", Boolean.TRUE,
    137             (Boolean) dynaForm.get("booleanProperty"));
    138         assertEquals("booleanSecond", Boolean.TRUE,
    139             (Boolean) dynaForm.get("booleanSecond"));
    140         assertEquals("doubleProperty", new Double(321.0),
    141             (Double) dynaForm.get("doubleProperty"));
    142         assertEquals("floatProperty", new Float((float) 123.0),
    143             (Float) dynaForm.get("floatProperty"));
    144         assertEquals("intProperty", new Integer(123),
    145             (Integer) dynaForm.get("intProperty"));
    146 
    147         // FIXME - listIndexed
    148         assertEquals("longProperty", new Long((long) 321),
    149             (Long) dynaForm.get("longProperty"));
    150 
    151         // FIXME - mappedProperty
    152         // FIXME - mappedIntProperty
    153         //        assertEquals("nullProperty", (String) null,
    154         //                     (String) dynaForm.get("nullProperty"));
    155         assertEquals("shortProperty", new Short((short) 987),
    156             (Short) dynaForm.get("shortProperty"));
    157         assertEquals("stringProperty", "This is a string",
    158             (String) dynaForm.get("stringProperty"));
    159     }
    160 
    161     // Test initialize() method on indexed values to ensure that the
    162     // result returned by FormPropertyConfig().initial() is never clobbered
    163     public void testIndexedInitialize() {
    164         // Update some values in the indexed properties
    165         dynaForm.set("intArray", 1, new Integer(111));
    166         assertEquals("intArray[1]", new Integer(111),
    167             (Integer) dynaForm.get("intArray", 1));
    168         dynaForm.set("intIndexed", 2, new Integer(222));
    169         assertEquals("intIndexed[2]", new Integer(222),
    170             (Integer) dynaForm.get("intIndexed", 2));
    171         dynaForm.set("stringArray", 3, "New String 3");
    172         assertEquals("stringArray[3]", "New String 3",
    173             (String) dynaForm.get("stringArray", 3));
    174         dynaForm.set("stringIndexed", 4, "New String 4");
    175         assertEquals("stringIndexed[4]", "New String 4",
    176             (String) dynaForm.get("stringIndexed", 4));
    177 
    178         // Perform initialize() and revalidate the original values
    179         // while ensuring our initial values did not get corrupted
    180         dynaForm.initialize(mapping);
    181         setupComplexProperties();
    182         testGetIndexedValues();
    183     }
    184 
    185     // Test initialize() method going back to initial values
    186     public void testScalarInitialize() {
    187         // Update a bunch of scalar properties to new values
    188         dynaForm.set("booleanProperty", Boolean.FALSE);
    189         assertEquals("booleanProperty", Boolean.FALSE,
    190             (Boolean) dynaForm.get("booleanProperty"));
    191         dynaForm.set("booleanSecond", Boolean.FALSE);
    192         dynaForm.set("doubleProperty", new Double(654.0));
    193         dynaForm.set("floatProperty", new Float((float) 543.0));
    194         dynaForm.set("intProperty", new Integer(555));
    195         dynaForm.set("longProperty", new Long((long) 777));
    196         dynaForm.set("shortProperty", new Short((short) 222));
    197         dynaForm.set("stringProperty", "New String Value");
    198         assertEquals("stringProperty", "New String Value",
    199             (String) dynaForm.get("stringProperty"));
    200 
    201         // Perform initialize() and revalidate the original values
    202         dynaForm.initialize(mapping);
    203         setupComplexProperties();
    204         testBeanCreate();
    205     }
    206 
    207     // --------------------------------------- Tests from BasicDynaBeanTestCase
    208 
    209     /**
    210      * Corner cases on getDynaProperty invalid arguments.
    211      */
    212     public void testGetDescriptorArguments() {
    213         DynaProperty descriptor =
    214             dynaForm.getDynaClass().getDynaProperty("unknown");
    215 
    216         assertNull("Unknown property descriptor should be null", descriptor);
    217 
    218         try {
    219             dynaForm.getDynaClass().getDynaProperty(null);
    220             fail("Should throw IllegalArgumentException");
    221         } catch (IllegalArgumentException e) {
    222             ; // Expected response
    223         }
    224     }
    225 
    226     /**
    227      * Positive getDynaProperty on property <code>booleanProperty</code>.
    228      */
    229     public void testGetDescriptorBoolean() {
    230         testGetDescriptorBase("booleanProperty", Boolean.TYPE);
    231     }
    232 
    233     /**
    234      * Positive getDynaProperty on property <code>doubleProperty</code>.
    235      */
    236     public void testGetDescriptorDouble() {
    237         testGetDescriptorBase("doubleProperty", Double.TYPE);
    238     }
    239 
    240     /**
    241      * Positive getDynaProperty on property <code>floatProperty</code>.
    242      */
    243     public void testGetDescriptorFloat() {
    244         testGetDescriptorBase("floatProperty", Float.TYPE);
    245     }
    246 
    247     /**
    248      * Positive getDynaProperty on property <code>intProperty</code>.
    249      */
    250     public void testGetDescriptorInt() {
    251         testGetDescriptorBase("intProperty", Integer.TYPE);
    252     }
    253 
    254     /**
    255      * Positive getDynaProperty on property <code>longProperty</code>.
    256      */
    257     public void testGetDescriptorLong() {
    258         testGetDescriptorBase("longProperty", Long.TYPE);
    259     }
    260 
    261     /**
    262      * Positive getDynaProperty on property <code>booleanSecond</code> that
    263      * uses an "is" method as the getter.
    264      */
    265     public void testGetDescriptorSecond() {
    266         testGetDescriptorBase("booleanSecond", Boolean.TYPE);
    267     }
    268 
    269     /**
    270      * Positive getDynaProperty on property <code>shortProperty</code>.
    271      */
    272     public void testGetDescriptorShort() {
    273         testGetDescriptorBase("shortProperty", Short.TYPE);
    274     }
    275 
    276     /**
    277      * Positive getDynaProperty on property <code>stringProperty</code>.
    278      */
    279     public void testGetDescriptorString() {
    280         testGetDescriptorBase("stringProperty", String.class);
    281     }
    282 
    283     /**
    284      * Positive test for getDynaPropertys().  Each property name listed in
    285      * <code>properties</code> should be returned exactly once.
    286      */
    287     public void testGetDescriptors() {
    288         DynaProperty[] pd = dynaForm.getDynaClass().getDynaProperties();
    289 
    290         assertNotNull("Got descriptors", pd);
    291 
    292         int[] count = new int[properties.length];
    293 
    294         for (int i = 0; i < pd.length; i++) {
    295             String name = pd[i].getName();
    296 
    297             for (int j = 0; j < properties.length; j++) {
    298                 if (name.equals(properties[j])) {
    299                     count[j]++;
    300                 }
    301             }
    302         }
    303 
    304         for (int j = 0; j < properties.length; j++) {
    305             if (count[j] < 0) {
    306                 fail("Missing property " + properties[j]);
    307             } else if (count[j] > 1) {
    308                 fail("Duplicate property " + properties[j]);
    309             }
    310         }
    311     }
    312 
    313     /**
    314      * Corner cases on getIndexedProperty invalid arguments.
    315      */
    316     public void testGetIndexedArguments() {
    317         try {
    318             dynaForm.get("intArray", -1);
    319             fail("Should throw IndexOutOfBoundsException");
    320         } catch (IndexOutOfBoundsException e) {
    321             ; // Expected response
    322         }
    323     }
    324 
    325     /**
    326      * Positive and negative tests on getIndexedProperty valid arguments.
    327      */
    328     public void testGetIndexedValues() {
    329         Object value = null;
    330 
    331         for (int i = 0; i < 5; i++) {
    332             value = dynaForm.get("intArray", i);
    333             assertNotNull("intArray returned value " + i, value);
    334             assertTrue("intArray returned Integer " + i,
    335                 value instanceof Integer);
    336             assertEquals("intArray returned correct " + i, i * 10,
    337                 ((Integer) value).intValue());
    338 
    339             value = dynaForm.get("intIndexed", i);
    340             assertNotNull("intIndexed returned value " + i, value);
    341             assertTrue("intIndexed returned Integer " + i,
    342                 value instanceof Integer);
    343             assertEquals("intIndexed returned correct " + i, i * 100,
    344                 ((Integer) value).intValue());
    345 
    346             value = dynaForm.get("listIndexed", i);
    347             assertNotNull("listIndexed returned value " + i, value);
    348             assertTrue("list returned String " + i, value instanceof String);
    349             assertEquals("listIndexed returned correct " + i, "String " + i,
    350                 (String) value);
    351 
    352             value = dynaForm.get("stringArray", i);
    353             assertNotNull("stringArray returned value " + i, value);
    354             assertTrue("stringArray returned String " + i,
    355                 value instanceof String);
    356             assertEquals("stringArray returned correct " + i, "String " + i,
    357                 (String) value);
    358 
    359             value = dynaForm.get("stringIndexed", i);
    360             assertNotNull("stringIndexed returned value " + i, value);
    361             assertTrue("stringIndexed returned String " + i,
    362                 value instanceof String);
    363             assertEquals("stringIndexed returned correct " + i, "String " + i,
    364                 (String) value);
    365         }
    366     }
    367 
    368     /**
    369      * Corner cases on getMappedProperty invalid arguments.
    370      */
    371     public void testGetMappedArguments() {
    372         Object value = dynaForm.get("mappedProperty", "unknown");
    373 
    374         assertNull("Should not return a value", value);
    375     }
    376 
    377     /**
    378      * Positive and negative tests on getMappedProperty valid arguments.
    379      */
    380     public void testGetMappedValues() {
    381         Object value = null;
    382 
    383         value = dynaForm.get("mappedProperty", "First Key");
    384         assertEquals("Can find first value", "First Value", value);
    385 
    386         value = dynaForm.get("mappedProperty", "Second Key");
    387         assertEquals("Can find second value", "Second Value", value);
    388 
    389         value = dynaForm.get("mappedProperty", "Third Key");
    390         assertNull("Can not find third value", value);
    391     }
    392 
    393     /**
    394      * Corner cases on getSimpleProperty invalid arguments.
    395      */
    396     public void testGetSimpleArguments() {
    397         try {
    398             dynaForm.get(null);
    399             fail("Should throw IllegalArgumentException");
    400         } catch (IllegalArgumentException e) {
    401             ; // Expected response
    402         }
    403     }
    404 
    405     /**
    406      * Test getSimpleProperty on a boolean property.
    407      */
    408     public void testGetSimpleBoolean() {
    409         Object value = dynaForm.get("booleanProperty");
    410 
    411         assertNotNull("Got a value", value);
    412         assertTrue("Got correct type", (value instanceof Boolean));
    413         assertTrue("Got correct value", ((Boolean) value).booleanValue() == true);
    414     }
    415 
    416     /**
    417      * Test getSimpleProperty on a double property.
    418      */
    419     public void testGetSimpleDouble() {
    420         Object value = dynaForm.get("doubleProperty");
    421 
    422         assertNotNull("Got a value", value);
    423         assertTrue("Got correct type", (value instanceof Double));
    424         assertEquals("Got correct value", ((Double) value).doubleValue(),
    425             (double) 321.0, (double) 0.005);
    426     }
    427 
    428     /**
    429      * Test getSimpleProperty on a float property.
    430      */
    431     public void testGetSimpleFloat() {
    432         Object value = dynaForm.get("floatProperty");
    433 
    434         assertNotNull("Got a value", value);
    435         assertTrue("Got correct type", (value instanceof Float));
    436         assertEquals("Got correct value", ((Float) value).floatValue(),
    437             (float) 123.0, (float) 0.005);
    438     }
    439 
    440     /**
    441      * Test getSimpleProperty on a int property.
    442      */
    443     public void testGetSimpleInt() {
    444         Object value = dynaForm.get("intProperty");
    445 
    446         assertNotNull("Got a value", value);
    447         assertTrue("Got correct type", (value instanceof Integer));
    448         assertEquals("Got correct value", ((Integer) value).intValue(),
    449             (int) 123);
    450     }
    451 
    452     /**
    453      * Test getSimpleProperty on a long property.
    454      */
    455     public void testGetSimpleLong() {
    456         Object value = dynaForm.get("longProperty");
    457 
    458         assertNotNull("Got a value", value);
    459         assertTrue("Got correct type", (value instanceof Long));
    460         assertEquals("Got correct value", ((Long) value).longValue(), (long) 321);
    461     }
    462 
    463     /**
    464      * Test getSimpleProperty on a short property.
    465      */
    466     public void testGetSimpleShort() {
    467         Object value = dynaForm.get("shortProperty");
    468 
    469         assertNotNull("Got a value", value);
    470         assertTrue("Got correct type", (value instanceof Short));
    471         assertEquals("Got correct value", ((Short) value).shortValue(),
    472             (short) 987);
    473     }
    474 
    475     /**
    476      * Test getSimpleProperty on a String property.
    477      */
    478     public void testGetSimpleString() {
    479         Object value = dynaForm.get("stringProperty");
    480 
    481         assertNotNull("Got a value", value);
    482         assertTrue("Got correct type", (value instanceof String));
    483         assertEquals("Got correct value", (String) value, "This is a string");
    484     }
    485 
    486     /**
    487      * Test <code>contains()</code> method for mapped properties.
    488      */
    489     public void testMappedContains() {
    490         assertTrue("Can see first key",
    491             dynaForm.contains("mappedProperty", "First Key"));
    492 
    493         assertTrue("Can not see unknown key",
    494             !dynaForm.contains("mappedProperty", "Unknown Key"));
    495     }
    496 
    497     /**
    498      * Test <code>remove()</code> method for mapped properties.
    499      */
    500     public void testMappedRemove() {
    501         assertTrue("Can see first key",
    502             dynaForm.contains("mappedProperty", "First Key"));
    503         dynaForm.remove("mappedProperty", "First Key");
    504         assertTrue("Can not see first key",
    505             !dynaForm.contains("mappedProperty", "First Key"));
    506 
    507         assertTrue("Can not see unknown key",
    508             !dynaForm.contains("mappedProperty", "Unknown Key"));
    509         dynaForm.remove("mappedProperty", "Unknown Key");
    510         assertTrue("Can not see unknown key",
    511             !dynaForm.contains("mappedProperty", "Unknown Key"));
    512     }
    513 
    514     /**
    515      * Test the reset method when the request method is GET.
    516      */
    517     public void testResetGet() {
    518         // set a choice set of props with non-initial values
    519         dynaForm.set("booleanProperty", Boolean.FALSE);
    520         dynaForm.set("booleanSecond", Boolean.FALSE);
    521         dynaForm.set("doubleProperty", new Double(456.0));
    522         dynaForm.set("floatProperty", new Float((float) 456.0));
    523         dynaForm.set("intProperty", new Integer(456));
    524 
    525         MockHttpServletRequest request = new MockHttpServletRequest();
    526 
    527         request.setMethod("GET");
    528         dynaForm.reset(mapping, request);
    529 
    530         assertEquals("booleanProperty should be reset", Boolean.TRUE,
    531             (Boolean) dynaForm.get("booleanProperty"));
    532         assertEquals("booleanSecond should be reset", Boolean.TRUE,
    533             (Boolean) dynaForm.get("booleanSecond"));
    534         assertEquals("doubleProperty should be reset", new Double(321.0),
    535             (Double) dynaForm.get("doubleProperty"));
    536         assertEquals("floatProperty should NOT be reset",
    537             new Float((float) 456.0), (Float) dynaForm.get("floatProperty"));
    538         assertEquals("intProperty should NOT be reset", new Integer(456),
    539             (Integer) dynaForm.get("intProperty"));
    540     }
    541 
    542     /**
    543      * Test the reset method when the request method is GET.
    544      */
    545     public void testResetPost() {
    546         // set a choice set of props with non-initial values
    547         dynaForm.set("booleanProperty", Boolean.FALSE);
    548         dynaForm.set("booleanSecond", Boolean.FALSE);
    549         dynaForm.set("doubleProperty", new Double(456.0));
    550         dynaForm.set("floatProperty", new Float((float) 456.0));
    551         dynaForm.set("intProperty", new Integer(456));
    552 
    553         MockHttpServletRequest request = new MockHttpServletRequest();
    554 
    555         request.setMethod("POST");
    556         dynaForm.reset(mapping, request);
    557 
    558         assertEquals("booleanProperty should be reset", Boolean.TRUE,
    559             (Boolean) dynaForm.get("booleanProperty"));
    560         assertEquals("booleanSecond should be reset", Boolean.TRUE,
    561             (Boolean) dynaForm.get("booleanSecond"));
    562         assertEquals("doubleProperty should NOT be reset", new Double(456),
    563             (Double) dynaForm.get("doubleProperty"));
    564         assertEquals("floatProperty should be reset", new Float((float) 123.0),
    565             (Float) dynaForm.get("floatProperty"));
    566         assertEquals("intProperty should NOT be reset", new Integer(456),
    567             (Integer) dynaForm.get("intProperty"));
    568     }
    569 
    570     /**
    571      * Corner cases on setIndexedProperty invalid arguments.
    572      */
    573     public void testSetIndexedArguments() {
    574         try {
    575             dynaForm.set("intArray", -1, new Integer(0));
    576             fail("Should throw IndexOutOfBoundsException");
    577         } catch (IndexOutOfBoundsException e) {
    578             ; // Expected response
    579         }
    580     }
    581 
    582     /**
    583      * Positive and negative tests on setIndexedProperty valid arguments.
    584      */
    585     public void testSetIndexedValues() {
    586         Object value = null;
    587 
    588         dynaForm.set("intArray", 0, new Integer(1));
    589         value = (Integer) dynaForm.get("intArray", 0);
    590         assertNotNull("Returned new value 0", value);
    591         assertTrue("Returned Integer new value 0", value instanceof Integer);
    592         assertEquals("Returned correct new value 0", 1,
    593             ((Integer) value).intValue());
    594 
    595         dynaForm.set("intIndexed", 1, new Integer(11));
    596         value = (Integer) dynaForm.get("intIndexed", 1);
    597         assertNotNull("Returned new value 1", value);
    598         assertTrue("Returned Integer new value 1", value instanceof Integer);
    599         assertEquals("Returned correct new value 1", 11,
    600             ((Integer) value).intValue());
    601         dynaForm.set("listIndexed", 2, "New Value 2");
    602         value = (String) dynaForm.get("listIndexed", 2);
    603         assertNotNull("Returned new value 2", value);
    604         assertTrue("Returned String new value 2", value instanceof String);
    605         assertEquals("Returned correct new value 2", "New Value 2",
    606             (String) value);
    607 
    608         dynaForm.set("stringArray", 3, "New Value 3");
    609         value = (String) dynaForm.get("stringArray", 3);
    610         assertNotNull("Returned new value 3", value);
    611         assertTrue("Returned String new value 3", value instanceof String);
    612         assertEquals("Returned correct new value 3", "New Value 3",
    613             (String) value);
    614 
    615         dynaForm.set("stringIndexed", 4, "New Value 4");
    616         value = (String) dynaForm.get("stringIndexed", 4);
    617         assertNotNull("Returned new value 4", value);
    618         assertTrue("Returned String new value 4", value instanceof String);
    619         assertEquals("Returned correct new value 4", "New Value 4",
    620             (String) value);
    621     }
    622 
    623     /**
    624      * Positive and negative tests on setMappedProperty valid arguments.
    625      */
    626     public void testSetMappedValues() {
    627         dynaForm.set("mappedProperty", "First Key", "New First Value");
    628         assertEquals("Can replace old value", "New First Value",
    629             (String) dynaForm.get("mappedProperty", "First Key"));
    630 
    631         dynaForm.set("mappedProperty", "Fourth Key", "Fourth Value");
    632         assertEquals("Can set new value", "Fourth Value",
    633             (String) dynaForm.get("mappedProperty", "Fourth Key"));
    634     }
    635 
    636     /**
    637      * Test setSimpleProperty on a boolean property.
    638      */
    639     public void testSetSimpleBoolean() {
    640         boolean oldValue =
    641             ((Boolean) dynaForm.get("booleanProperty")).booleanValue();
    642         boolean newValue = !oldValue;
    643 
    644         dynaForm.set("booleanProperty", new Boolean(newValue));
    645         assertTrue("Matched new value",
    646             newValue == ((Boolean) dynaForm.get("booleanProperty"))
    647             .booleanValue());
    648     }
    649 
    650     /**
    651      * Test setSimpleProperty on a double property.
    652      */
    653     public void testSetSimpleDouble() {
    654         double oldValue =
    655             ((Double) dynaForm.get("doubleProperty")).doubleValue();
    656         double newValue = oldValue + 1.0;
    657 
    658         dynaForm.set("doubleProperty", new Double(newValue));
    659         assertEquals("Matched new value", newValue,
    660             ((Double) dynaForm.get("doubleProperty")).doubleValue(),
    661             (double) 0.005);
    662     }
    663 
    664     /**
    665      * Test setSimpleProperty on a float property.
    666      */
    667     public void testSetSimpleFloat() {
    668         float oldValue = ((Float) dynaForm.get("floatProperty")).floatValue();
    669         float newValue = oldValue + (float) 1.0;
    670 
    671         dynaForm.set("floatProperty", new Float(newValue));
    672         assertEquals("Matched new value", newValue,
    673             ((Float) dynaForm.get("floatProperty")).floatValue(), (float) 0.005);
    674     }
    675 
    676     /**
    677      * Test setSimpleProperty on a int property.
    678      */
    679     public void testSetSimpleInt() {
    680         int oldValue = ((Integer) dynaForm.get("intProperty")).intValue();
    681         int newValue = oldValue + 1;
    682 
    683         dynaForm.set("intProperty", new Integer(newValue));
    684         assertEquals("Matched new value", newValue,
    685             ((Integer) dynaForm.get("intProperty")).intValue());
    686     }
    687 
    688     /**
    689      * Test setSimpleProperty on a long property.
    690      */
    691     public void testSetSimpleLong() {
    692         long oldValue = ((Long) dynaForm.get("longProperty")).longValue();
    693         long newValue = oldValue + 1;
    694 
    695         dynaForm.set("longProperty", new Long(newValue));
    696         assertEquals("Matched new value", newValue,
    697             ((Long) dynaForm.get("longProperty")).longValue());
    698     }
    699 
    700     /**
    701      * Test setSimpleProperty on a short property.
    702      */
    703     public void testSetSimpleShort() {
    704         short oldValue = ((Short) dynaForm.get("shortProperty")).shortValue();
    705         short newValue = (short) (oldValue + 1);
    706 
    707         dynaForm.set("shortProperty", new Short(newValue));
    708         assertEquals("Matched new value", newValue,
    709             ((Short) dynaForm.get("shortProperty")).shortValue());
    710     }
    711 
    712     /**
    713      * Test setSimpleProperty on a String property.
    714      */
    715     public void testSetSimpleString() {
    716         String oldValue = (String) dynaForm.get("stringProperty");
    717         String newValue = oldValue + " Extra Value";
    718 
    719         dynaForm.set("stringProperty", newValue);
    720         assertEquals("Matched new value", newValue,
    721             (String) dynaForm.get("stringProperty"));
    722     }
    723 
    724     // ------------------------------------------------------ Protected Methods
    725 
    726     /**
    727      * Set up the complex properties that cannot be configured from the
    728      * initial value expression.
    729      */
    730     protected void setupComplexProperties() {
    731         List listIndexed = new ArrayList();
    732 
    733         listIndexed.add("String 0");
    734         listIndexed.add("String 1");
    735         listIndexed.add("String 2");
    736         listIndexed.add("String 3");
    737         listIndexed.add("String 4");
    738         dynaForm.set("listIndexed", listIndexed);
    739 
    740         Map mappedProperty = new HashMap();
    741 
    742         mappedProperty.put("First Key", "First Value");
    743         mappedProperty.put("Second Key", "Second Value");
    744         dynaForm.set("mappedProperty", mappedProperty);
    745 
    746         Map mappedIntProperty = new HashMap();
    747 
    748         mappedIntProperty.put("One", new Integer(1));
    749         mappedIntProperty.put("Two", new Integer(2));
    750         dynaForm.set("mappedIntProperty", mappedIntProperty);
    751     }
    752 
    753     /**
    754      * Base for testGetDescriptorXxxxx() series of tests.
    755      *
    756      * @param name Name of the property to be retrieved
    757      * @param type Expected class type of this property
    758      */
    759     protected void testGetDescriptorBase(String name, Class type) {
    760         DynaProperty descriptor = dynaForm.getDynaClass().getDynaProperty(name);
    761 
    762         assertNotNull("Got descriptor", descriptor);
    763         assertEquals("Got correct type", type, descriptor.getType());
    764     }
    765 }
    766 
    767 
    768 class DynaActionFormMapping extends ActionMapping {
    769     private ModuleConfig appConfig = null;
    770 
    771     public DynaActionFormMapping(ModuleConfig appConfig) {
    772         this.appConfig = appConfig;
    773     }
    774 
    775     public ModuleConfig getModuleConfig() {
    776         return (this.appConfig);
    777     }
    778 
    779     public String getName() {
    780         return ("dynaForm");
    781     }
    782 }
    783 
    784 
    785 class DynaActionFormConfig extends ModuleConfigImpl {
    786     private FormBeanConfig beanConfig = null;
    787 
    788     public DynaActionFormConfig(FormBeanConfig beanConfig) {
    789         super("");
    790         this.beanConfig = beanConfig;
    791     }
    792 
    793     public FormBeanConfig findFormBeanConfig(String name) {
    794         return (this.beanConfig);
    795     }
    796 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
