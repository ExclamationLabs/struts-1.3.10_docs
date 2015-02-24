
    1   /*
    2    * $Id: TestActionMessages.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import java.util.Iterator;
    28  
    29  /**
    30   * Unit tests for the <code>org.apache.struts.action.ActionMessages</code>
    31   * class.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:09:25 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   */
    36  public class TestActionMessages extends TestCase {
    37      protected ActionMessages aMsgs = null;
    38      protected ActionMessages anMsgs = null;
    39      protected ActionMessage msg1 = null;
    40      protected ActionMessage msg2 = null;
    41      protected ActionMessage msg3 = null;
    42      protected ActionMessage msg4 = null;
    43      protected ActionMessage msg5 = null;
    44  
    45      /**
    46       * Defines the testcase name for JUnit.
    47       *
    48       * @param theName the testcase's name.
    49       */
    50      public TestActionMessages(String theName) {
    51          super(theName);
    52      }
    53  
    54      /**
    55       * Start the tests.
    56       *
    57       * @param theArgs the arguments. Not used
    58       */
    59      public static void main(String[] theArgs) {
    60          junit.awtui.TestRunner.main(new String[] {
    61                  TestActionMessages.class.getName()
    62              });
    63      }
    64  
    65      /**
    66       * @return a test suite (<code>TestSuite</code>) that includes all methods
    67       *         starting with "test"
    68       */
    69      public static Test suite() {
    70          // All methods starting with "test" will be executed in the test suite.
    71          return new TestSuite(TestActionMessages.class);
    72      }
    73  
    74      public void setUp() {
    75          aMsgs = new ActionMessages();
    76          anMsgs = new ActionMessages();
    77  
    78          Object[] objs1 = new Object[] { "a", "b", "c", "d", "e" };
    79          Object[] objs2 = new Object[] { "f", "g", "h", "i", "j" };
    80  
    81          msg1 = new ActionMessage("aMessage", objs1);
    82          msg2 = new ActionMessage("anMessage", objs2);
    83          msg3 = new ActionMessage("msg3", "value1");
    84          msg4 = new ActionMessage("msg4", "value2");
    85          msg5 = new ActionMessage("msg5", "value3", "value4");
    86      }
    87  
    88      public void tearDown() {
    89          aMsgs = null;
    90      }
    91  
    92      public void testEmpty() {
    93          assertTrue("aMsgs is not empty!", aMsgs.isEmpty());
    94      }
    95  
    96      public void testNotEmpty() {
    97          aMsgs.add("myProp", msg1);
    98          assertTrue("aMsgs is empty!", aMsgs.isEmpty() == false);
    99      }
    100 
    101     public void testSizeWithOneProperty() {
    102         aMsgs.add("myProp", msg1);
    103         aMsgs.add("myProp", msg2);
    104         assertTrue("number of mesages is not 2", aMsgs.size("myProp") == 2);
    105     }
    106 
    107     public void testSizeWithManyProperties() {
    108         aMsgs.add("myProp1", msg1);
    109         aMsgs.add("myProp2", msg2);
    110         aMsgs.add("myProp3", msg3);
    111         aMsgs.add("myProp3", msg4);
    112         aMsgs.add("myProp4", msg5);
    113         assertTrue("number of messages for myProp1 is not 1",
    114             aMsgs.size("myProp1") == 1);
    115         assertTrue("number of messages", aMsgs.size() == 5);
    116     }
    117 
    118     public void testSizeAndEmptyAfterClear() {
    119         testSizeWithOneProperty();
    120         aMsgs.clear();
    121         testEmpty();
    122         assertTrue("number of meesages is not 0", aMsgs.size("myProp") == 0);
    123     }
    124 
    125     public void testGetWithNoProperty() {
    126         Iterator it = aMsgs.get("myProp");
    127 
    128         assertTrue("iterator is not empty!", it.hasNext() == false);
    129     }
    130 
    131     public void testGetForAProperty() {
    132         testSizeWithOneProperty();
    133 
    134         Iterator it = aMsgs.get("myProp");
    135 
    136         assertTrue("iterator is empty!", it.hasNext() == true);
    137     }
    138 
    139     /**
    140      * Tests adding an ActionMessages object to an ActionMessages object.
    141      */
    142     public void testAddMessages() {
    143         ActionMessage msg1 = new ActionMessage("key");
    144         ActionMessage msg2 = new ActionMessage("key2");
    145         ActionMessage msg3 = new ActionMessage("key3");
    146         ActionMessages msgs = new ActionMessages();
    147         ActionMessages add = new ActionMessages();
    148 
    149         msgs.add("prop1", msg1);
    150         add.add("prop1", msg2);
    151         add.add("prop3", msg3);
    152 
    153         msgs.add(add);
    154         assertTrue(msgs.size() == 3);
    155         assertTrue(msgs.size("prop1") == 2);
    156 
    157         // test message order
    158         Iterator props = msgs.get();
    159         int count = 1;
    160 
    161         while (props.hasNext()) {
    162             ActionMessage msg = (ActionMessage) props.next();
    163 
    164             if (count == 1) {
    165                 assertTrue(msg.getKey().equals("key"));
    166             } else if (count == 2) {
    167                 assertTrue(msg.getKey().equals("key2"));
    168             } else {
    169                 assertTrue(msg.getKey().equals("key3"));
    170             }
    171 
    172             count++;
    173         }
    174     }
    175 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
