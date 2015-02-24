
    1   /*
    2    * $Id: TestValidWhen.java 569606 2007-08-25 03:54:59Z pbenedict $
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
    21  package org.apache.struts.validator;
    22  
    23  import junit.framework.Test;
    24  import junit.framework.TestCase;
    25  import junit.framework.TestSuite;
    26  
    27  import org.apache.commons.logging.Log;
    28  import org.apache.commons.logging.LogFactory;
    29  import org.apache.commons.validator.util.ValidatorUtils;
    30  import org.apache.struts.validator.validwhen.ValidWhenLexer;
    31  import org.apache.struts.validator.validwhen.ValidWhenParser;
    32  
    33  import java.io.StringReader;
    34  
    35  /**
    36   * Unit tests for the ValidWhen Parser/Lexer.
    37   */
    38  public class TestValidWhen extends TestCase {
    39      /**
    40       * All logging goes through this logger
    41       */
    42      private static Log log = LogFactory.getLog(TestValidWhen.class);
    43      protected PojoBean testBean;
    44  
    45      /**
    46       * Defines the testcase name for JUnit.
    47       *
    48       * @param theName the testcase's name.
    49       */
    50      public TestValidWhen(String theName) {
    51          super(theName);
    52      }
    53  
    54      /**
    55       * Start the tests.
    56       *
    57       * @param theArgs the arguments. Not used
    58       */
    59      public static void main(String[] theArgs) {
    60          junit.awtui.TestRunner.main(new String[] { TestValidWhen.class.getName() });
    61      }
    62  
    63      /**
    64       * @return a test suite (<code>TestSuite</code>) that includes all methods
    65       *         starting with "test"
    66       */
    67      public static Test suite() {
    68          // All methods starting with "test" will be executed in the test suite.
    69          return new TestSuite(TestValidWhen.class);
    70      }
    71  
    72      public void setUp() {
    73          testBean = new PojoBean(123, 789);
    74          testBean.setStringValue1("ABC");
    75          testBean.setStringValue2(null);
    76          testBean.setBeans(new PojoBean[] {
    77                  new PojoBean(11, 12), new PojoBean(21, 22), new PojoBean(31, 42),
    78                  new PojoBean(41, 52), new PojoBean(51, 62)
    79              });
    80          testBean.setMapped("testKey", "mappedValue");
    81      }
    82  
    83      public void tearDown() {
    84          testBean = null;
    85      }
    86  
    87      /**
    88       * Test Operators.
    89       */
    90      public void testProperty() {
    91          // *this*
    92          doParse("(*this* == 123)", testBean, 0, "intValue1", true);
    93  
    94          // Named property
    95          doParse("(intValue2 == 789)", testBean, 0, "intValue1", true);
    96  
    97          // Indexed Property
    98          doParse("(beans[].intValue1 == 21)", testBean, 1, "intValue1", true);
    99          doParse("(beans[1].intValue1 == 21)", testBean, 4, "intValue1", true);
    100 
    101         // Mapped Property - *** NOT SUPPORTED ***
    102         // doParse("(mapped(mappedValue) == 'testKey')", testBean , 0, "mappedValue", true);
    103     }
    104 
    105     /**
    106      * Test Operators.
    107      */
    108     public void testOperators() {
    109         // Equal
    110         doParse("(*this* == 123)", testBean, 0, "intValue1", true);
    111 
    112         // Not Equal
    113         doParse("(*this* != 456)", testBean, 0, "intValue1", true);
    114 
    115         // Less Than
    116         doParse("(*this* < 456)", testBean, 0, "intValue1", true);
    117 
    118         // Greater Than
    119         doParse("(*this* > 100)", testBean, 0, "intValue1", true);
    120 
    121         // Less Than Equal
    122         doParse("(*this* <= 123)", testBean, 0, "intValue1", true);
    123 
    124         // Greater Than Equal
    125         doParse("(*this* >= 123)", testBean, 0, "intValue1", true);
    126     }
    127 
    128     /**
    129      * Test String values.
    130      */
    131     public void testString() {
    132         doParse("(*this* != '--')", "XX", 0, "stringValue1", true);
    133         doParse("(*this* == '--')", "--", 0, "stringValue1", true);
    134 
    135         String testValue = "dsgUOLMdLsdL";
    136 
    137         // single quote
    138         doParse("(*this* == '" + testValue + "')", testValue, 0,
    139             "stringValue1", true);
    140 
    141         // double quote
    142         doParse("(*this* == \"" + testValue + "\")", testValue, 0,
    143             "stringValue1", true);
    144 
    145         // obscure characters
    146         doParse("(*this* == \":\")", ":", 0,
    147             "stringValue1", true);
    148         doParse("(*this* == \"foo:bar\")", "foo:bar", 0,
    149             "stringValue1", true);
    150     }
    151 
    152     /**
    153      * Test Numeric values.
    154      */
    155     public void testNumeric() {
    156         // Test Zero
    157         PojoBean numberBean = new PojoBean(0, -50);
    158 
    159         doParse("(intValue1 == 0)", numberBean, 0, "intValue1", true);
    160         doParse("(intValue2 != 0)", numberBean, 0, "intValue2", true);
    161         doParse("(integerValue1 == 0)", numberBean, 0, "integerValue1", true);
    162         doParse("(integerValue2 != 0)", numberBean, 0, "integerValue2", true);
    163 
    164         // int
    165         doParse("(intValue1 == 123)", testBean, 0, "intValue1", true);
    166 
    167         // Integer
    168         doParse("(integerValue1 == 123)", testBean, 0, "integerValue1", true);
    169 
    170         // Negative Numbers
    171         doParse("((intValue2 < -10)     and (intValue2 > -60))", numberBean, 0,
    172             "intValue2", true);
    173         doParse("((integerValue2 < -10) and (integerValue2 > -60))",
    174             numberBean, 0, "integerValue2", true);
    175 
    176         // Hex
    177         doParse("(integerValue1 == 0x7B)", testBean, 0, "integerValue1", true);
    178 
    179         // Octal
    180         doParse("(integerValue1 == 0173)", testBean, 0, "integerValue1", true);
    181 
    182         // Test 'String' numbers
    183         PojoBean stringBean = new PojoBean("11", "2");
    184 
    185         doParse("(stringValue1 > stringValue2)", stringBean, 0, "stringValue1",
    186             true);
    187         doParse("(stringValue1 < stringValue2)", stringBean, 0, "stringValue1",
    188             false);
    189     }
    190 
    191     /**
    192      * Test Null.
    193      */
    194     public void testNull() {
    195         // Not Null
    196         doParse("(*this* != null)", testBean, 0, "stringValue1", true);
    197 
    198         // Null
    199         doParse("(*this* == null)", testBean, 0, "stringValue2", true);
    200 
    201         // 0-length empty string
    202         testBean.setStringValue2("");
    203         doParse("(*this* == null)", testBean, 0, "stringValue2", true);
    204 
    205         // N-length empty string
    206         testBean.setStringValue2("  ");
    207         doParse("(*this* == null)", testBean, 0, "stringValue2", true);
    208     }
    209 
    210     /**
    211      * Test Joined expressions ('and' or 'or')
    212      */
    213     public void testJoined() {
    214         // Join with 'or'
    215         doParse("((*this* == 'ABC') or (stringValue2 == null))", testBean, 0,
    216             "stringValue1", true);
    217         doParse("((*this* != 'ABC') or (stringValue2 == null))", testBean, 0,
    218             "stringValue1", true);
    219         doParse("((*this* == 'ABC') or (stringValue2 != null))", testBean, 0,
    220             "stringValue1", true);
    221         doParse("((*this* != 'ABC') or (stringValue2 != null))", testBean, 0,
    222             "stringValue1", false);
    223 
    224         // Join with 'and'
    225         doParse("((*this* == 'ABC') and (stringValue2 == null))", testBean, 0,
    226             "stringValue1", true);
    227         doParse("((*this* != 'ABC') and (stringValue2 == null))", testBean, 0,
    228             "stringValue1", false);
    229         doParse("((*this* == 'ABC') and (stringValue2 != null))", testBean, 0,
    230             "stringValue1", false);
    231         doParse("((*this* != 'ABC') and (stringValue2 != null))", testBean, 0,
    232             "stringValue1", false);
    233     }
    234 
    235     /**
    236      * Parse the expression and check that the expected result (either true or
    237      * false) occurs - fail if an exception is thrown opr the wrong result
    238      * occurs.
    239      *
    240      * @param test     Test expression
    241      * @param bean     Test Bean
    242      * @param index    index value
    243      * @param property Bean property
    244      * @param expected Expected Result
    245      */
    246     private void doParse(String test, Object bean, int index, String property,
    247         boolean expected) {
    248         boolean result = false;
    249 
    250         try {
    251             result = doParse(test, bean, index, property);
    252         } catch (Exception ex) {
    253             log.error("Parsing " + test + " for property '" + property + "'", ex);
    254             fail("Parsing " + test + " threw " + ex);
    255         }
    256 
    257         if (expected) {
    258             assertTrue(test + " didn't return TRUE for " + property, result);
    259         } else {
    260             assertFalse(test + " didn't return FALSE for " + property, result);
    261         }
    262     }
    263 
    264     /**
    265      * Parse the expression and check that an Exception is throw. Failes if no
    266      * expection is thrown.
    267      *
    268      * @param test     Test expression
    269      * @param bean     Test Bean
    270      * @param index    index value
    271      * @param property Bean property
    272      */
    273     private void doParseFail(String test, Object bean, int index,
    274         String property) {
    275         try {
    276             boolean result = doParse(test, bean, index, property);
    277 
    278             fail("Parsing " + test + " didn't throw exception as expected "
    279                 + result);
    280         } catch (Exception expected) {
    281             // ignore exception - expected result
    282         }
    283     }
    284 
    285     /**
    286      * Parse the expression returning the result
    287      *
    288      * @param test     Test expression
    289      * @param bean     Test Bean
    290      * @param index    index value
    291      * @param property Bean property
    292      */
    293     private boolean doParse(String test, Object bean, int index, String property)
    294         throws Exception {
    295         if (bean == null) {
    296             throw new NullPointerException("Bean is null for property '"
    297                 + property + "'");
    298         }
    299 
    300         String value =
    301             String.class.isInstance(bean) ? (String) bean
    302                                           : ValidatorUtils.getValueAsString(bean,
    303                 property);
    304 
    305         ValidWhenLexer lexer = new ValidWhenLexer(new StringReader(test));
    306 
    307         ValidWhenParser parser = new ValidWhenParser(lexer);
    308 
    309         parser.setForm(bean);
    310         parser.setIndex(index);
    311         parser.setValue(value);
    312 
    313         parser.expression();
    314 
    315         return parser.getResult();
    316     }
    317 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
