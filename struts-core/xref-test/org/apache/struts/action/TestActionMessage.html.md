
    1   /*
    2    * $Id: TestActionMessage.java 471754 2006-11-06 14:55:09Z husted $
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
    27  /**
    28   * Unit tests for the <code>org.apache.struts.action.ActionMessage</code>
    29   * class.
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-05-19 23:50:06 -0400 (Thu, 19 May 2005)
    32   *          $
    33   */
    34  public class TestActionMessage extends TestCase {
    35      protected ActionMessage amWithNoValue = null;
    36      protected ActionMessage amWithOneValue = null;
    37      protected ActionMessage amWithTwoValues = null;
    38      protected ActionMessage amWithThreeValues = null;
    39      protected ActionMessage amWithFourValues = null;
    40      protected ActionMessage amWithArrayValues = null;
    41      protected ActionMessage amWithTwoIntegerValues = null;
    42      protected ActionMessage amNoResource = null;
    43      protected Object[] test_values =
    44          new Object[] {
    45              "stringValue1", "stringValue2", "stringValue3", "stringValue4"
    46          };
    47  
    48      /**
    49       * Defines the testcase name for JUnit.
    50       *
    51       * @param theName the testcase's name.
    52       */
    53      public TestActionMessage(String theName) {
    54          super(theName);
    55      }
    56  
    57      /**
    58       * Start the tests.
    59       *
    60       * @param theArgs the arguments. Not used
    61       */
    62      public static void main(String[] theArgs) {
    63          junit.awtui.TestRunner.main(new String[] {
    64                  TestActionMessage.class.getName()
    65              });
    66      }
    67  
    68      /**
    69       * @return a test suite (<code>TestSuite</code>) that includes all methods
    70       *         starting with "test"
    71       */
    72      public static Test suite() {
    73          // All methods starting with "test" will be executed in the test suite.
    74          return new TestSuite(TestActionMessage.class);
    75      }
    76  
    77      public void setUp() {
    78          amWithNoValue = new ActionMessage("amWithNoValue");
    79          amWithOneValue =
    80              new ActionMessage("amWithOneValue", new String("stringValue"));
    81          amWithTwoValues =
    82              new ActionMessage("amWithTwoValues", new String("stringValue1"),
    83                  new String("stringValue2"));
    84          amWithThreeValues =
    85              new ActionMessage("amWithThreeValues", new String("stringValue1"),
    86                  new String("stringValue2"), new String("stringValue3"));
    87          amWithFourValues =
    88              new ActionMessage("amWithFourValues", new String("stringValue1"),
    89                  new String("stringValue2"), new String("stringValue3"),
    90                  new String("stringValue4"));
    91          amWithArrayValues = new ActionMessage("amWithArrayValues", test_values);
    92          amWithTwoIntegerValues =
    93              new ActionMessage("amWithTwoIntegerValues", new Integer(5),
    94                  new Integer(10));
    95          amNoResource = new ActionMessage("amNoResource", false);
    96      }
    97  
    98      public void tearDown() {
    99          amWithNoValue = null;
    100         amWithOneValue = null;
    101         amWithTwoValues = null;
    102         amWithThreeValues = null;
    103         amWithFourValues = null;
    104         amWithArrayValues = null;
    105         amWithTwoIntegerValues = null;
    106         amNoResource = null;
    107     }
    108 
    109     public void testActionMessageWithNoValue() {
    110         assertTrue(amWithNoValue.getValues() == null);
    111         assertTrue(amWithNoValue.isResource());
    112         assertTrue(amWithNoValue.getKey() == "amWithNoValue");
    113         assertTrue(amWithNoValue.toString().equals("amWithNoValue[]"));
    114     }
    115 
    116     public void testActionMessageWithAStringValue() {
    117         Object[] values = amWithOneValue.getValues();
    118 
    119         assertTrue(values != null);
    120         assertTrue(values.length == 1);
    121         assertTrue(values[0].equals("stringValue"));
    122         assertTrue(amWithOneValue.isResource());
    123         assertTrue(amWithOneValue.getKey() == "amWithOneValue");
    124         assertTrue(amWithOneValue.toString().equals("amWithOneValue[stringValue]"));
    125     }
    126 
    127     public void testActionMessageWithTwoValues() {
    128         Object[] values = amWithTwoValues.getValues();
    129 
    130         assertTrue(values != null);
    131         assertTrue(values.length == 2);
    132         assertTrue(values[0].equals("stringValue1"));
    133         assertTrue(values[1].equals("stringValue2"));
    134         assertTrue(amWithTwoValues.isResource());
    135         assertTrue(amWithTwoValues.getKey() == "amWithTwoValues");
    136         assertTrue(amWithTwoValues.toString().equals("amWithTwoValues[stringValue1, stringValue2]"));
    137     }
    138 
    139     public void testActionMessageWithThreeValues() {
    140         Object[] values = amWithThreeValues.getValues();
    141 
    142         assertTrue(values != null);
    143         assertTrue(values.length == 3);
    144         assertTrue(values[0].equals("stringValue1"));
    145         assertTrue(values[1].equals("stringValue2"));
    146         assertTrue(values[2].equals("stringValue3"));
    147         assertTrue(amWithThreeValues.getKey() == "amWithThreeValues");
    148         assertTrue(amWithThreeValues.isResource());
    149         assertTrue(amWithThreeValues.toString().equals("amWithThreeValues[stringValue1, stringValue2, stringValue3]"));
    150     }
    151 
    152     public void testActionMessageWithFourValues() {
    153         Object[] values = amWithFourValues.getValues();
    154 
    155         assertTrue(values != null);
    156         assertTrue(values.length == 4);
    157         assertTrue(values[0].equals("stringValue1"));
    158         assertTrue(values[1].equals("stringValue2"));
    159         assertTrue(values[2].equals("stringValue3"));
    160         assertTrue(values[3].equals("stringValue4"));
    161         assertTrue(amWithFourValues.isResource());
    162         assertTrue(amWithFourValues.getKey() == "amWithFourValues");
    163         assertTrue(amWithFourValues.toString().equals("amWithFourValues[stringValue1, stringValue2, stringValue3, stringValue4]"));
    164     }
    165 
    166     public void testActionMessageWithArrayValues() {
    167         Object[] values = amWithArrayValues.getValues();
    168 
    169         assertTrue(values != null);
    170         assertTrue(values.length == test_values.length);
    171 
    172         for (int i = 0; i < values.length; i++) {
    173             assertTrue(values[i] == test_values[i]);
    174         }
    175 
    176         assertTrue(amWithArrayValues.isResource());
    177         assertTrue(amWithArrayValues.getKey() == "amWithArrayValues");
    178         assertTrue(amWithArrayValues.toString().equals("amWithArrayValues[stringValue1, stringValue2, stringValue3, stringValue4]"));
    179     }
    180 
    181     public void testActionWithTwoIntegers() {
    182         Object[] values = amWithTwoIntegerValues.getValues();
    183 
    184         assertTrue(values != null);
    185         assertTrue(values.length == 2);
    186         assertTrue(values[0] instanceof Integer);
    187         assertTrue(values[0].toString().equals("5"));
    188         assertTrue(values[1] instanceof Integer);
    189         assertTrue(values[1].toString().equals("10"));
    190         assertTrue(amWithTwoIntegerValues.isResource());
    191         assertTrue(amWithTwoIntegerValues.getKey() == "amWithTwoIntegerValues");
    192         assertTrue(amWithTwoIntegerValues.toString().equals("amWithTwoIntegerValues[5, 10]"));
    193     }
    194 
    195     public void testActionNoResource() {
    196         assertTrue(amNoResource.getValues() == null);
    197         assertTrue(amNoResource.isResource() == false);
    198         assertTrue(amNoResource.getKey() == "amNoResource");
    199         assertTrue(amNoResource.toString().equals("amNoResource[]"));
    200     }
    201 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
