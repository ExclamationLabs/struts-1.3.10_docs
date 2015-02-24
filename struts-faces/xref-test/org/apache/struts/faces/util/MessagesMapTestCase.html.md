
    1   /*
    2    * $Id: MessagesMapTestCase.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.faces.util;
    23  
    24  
    25  import java.util.Collections;
    26  import java.util.Locale;
    27  
    28  import junit.framework.Test;
    29  import junit.framework.TestCase;
    30  import junit.framework.TestSuite;
    31  
    32  import org.apache.struts.util.MessageResources;
    33  
    34  
    35  /**
    36   * <p>Unit tests for <code>MessagesMap</code>.</p>
    37   */
    38  
    39  public class MessagesMapTestCase extends TestCase {
    40  
    41  
    42      // ------------------------------------------------------ Instance Variables
    43  
    44  
    45      /**
    46       * <p>The <code>MessagesMap</code> instance to be tested.</p>
    47       */
    48      protected MessagesMap map = null;
    49  
    50  
    51      /**
    52       * <p>The <code>MessageResources</code> instance containing the messages
    53       * used for testing.</p>
    54       */
    55      protected MessageResources resources = null;
    56  
    57  
    58      // ------------------------------------------------------------ Constructors
    59  
    60  
    61      /**
    62       * <p>Construct a new instance of this test case.</p>
    63       *
    64       * @param name Name of the test case
    65       */
    66      public MessagesMapTestCase(String name) {
    67  
    68          super(name);
    69  
    70      }
    71  
    72  
    73      // ---------------------------------------------------- Overall Test Methods
    74  
    75  
    76      /**
    77       * <p>Set up instance variables required by this test case.</p>
    78       */
    79      public void setUp() throws Exception {
    80  
    81          resources =
    82              MessageResources.getMessageResources
    83              ("org.apache.struts.faces.util.Bundle");
    84          map = new MessagesMap(resources, Locale.getDefault());
    85  
    86      }
    87  
    88  
    89      /**
    90       * <p>Return the tests included in this test suite.</p>
    91       */
    92      public static Test suite() {
    93  
    94          return new TestSuite(MessagesMapTestCase.class);
    95  
    96      }
    97  
    98  
    99      /**
    100      * <p>Tear down instance variables required by this test case.</p>
    101      */
    102     public void teaDown() throws Exception {
    103 
    104         map = null;
    105         resources = null;
    106 
    107     }
    108 
    109 
    110     // -------------------------------------------------- Individal Test Methods
    111 
    112 
    113     /**
    114      * <p>Test the <code>containsKey()</code> method.</p>
    115      */
    116     public void testContainsKey() throws Exception {
    117 
    118         // Positive tests
    119         assertTrue(map.containsKey("foo"));
    120         assertTrue(map.containsKey("bar"));
    121         assertTrue(map.containsKey("baz"));
    122 
    123         // Negative tests
    124         assertTrue(!map.containsKey("bop"));
    125 
    126     }
    127 
    128 
    129     /**
    130      * <p>Test the <code>get()</code> method.</p>
    131      */
    132     public void testGet() throws Exception {
    133 
    134         // Positive tests
    135         assertEquals("This is foo", (String) map.get("foo"));
    136         assertEquals("And this is bar", (String) map.get("bar"));
    137         assertEquals("We also have baz", (String) map.get("baz"));
    138 
    139         // Negative tests
    140         assertNull(map.get("bop"));
    141 
    142     }
    143 
    144 
    145     /**
    146      * <p>Test a pristine instance, and all unsupported methods.</p>
    147      */
    148     public void testPristine() throws Exception {
    149 
    150         // clear()
    151         try {
    152             map.clear();
    153             fail("clear() should have thrown UnsupportedOperationException");
    154         } catch (UnsupportedOperationException e) {
    155             ; // Expected result
    156         }
    157 
    158         // containsValue()
    159         try {
    160             map.containsValue("foo");
    161             fail("containsValue() should have thrown UnsupportedOperationException");
    162         } catch (UnsupportedOperationException e) {
    163             ; // Expected result
    164         }
    165 
    166         // entrySet()
    167         try {
    168             map.entrySet();
    169             fail("entrySet() should have thrown UnsupportedOperationException");
    170         } catch (UnsupportedOperationException e) {
    171             ; // Expected result
    172         }
    173 
    174         // keySet()
    175         try {
    176             map.keySet();
    177             fail("keySet() should have thrown UnsupportedOperationException");
    178         } catch (UnsupportedOperationException e) {
    179             ; // Expected result
    180         }
    181 
    182         // put()
    183         try {
    184             map.put("foo", "bar");
    185             fail("put() should have thrown UnsupportedOperationException");
    186         } catch (UnsupportedOperationException e) {
    187             ; // Expected result
    188         }
    189 
    190         // putAll()
    191         try {
    192             map.putAll(Collections.EMPTY_MAP);
    193             fail("putAll() should have thrown UnsupportedOperationException");
    194         } catch (UnsupportedOperationException e) {
    195             ; // Expected result
    196         }
    197 
    198         // remove()
    199         try {
    200             map.remove("foo");
    201             fail("remove() should have thrown UnsupportedOperationException");
    202         } catch (UnsupportedOperationException e) {
    203             ; // Expected result
    204         }
    205 
    206         // size()
    207         try {
    208             map.size();
    209             fail("size() should have thrown UnsupportedOperationException");
    210         } catch (UnsupportedOperationException e) {
    211             ; // Expected result
    212         }
    213 
    214         // size()
    215         try {
    216             map.values();
    217             fail("values() should have thrown UnsupportedOperationException");
    218         } catch (UnsupportedOperationException e) {
    219             ; // Expected result
    220         }
    221 
    222     }
    223 
    224 
    225 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
