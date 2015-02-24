
    1   /*
    2    * $Id: TestFormPropertyConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import junit.framework.TestCase;
    24  
    25  /**
    26   * Unit tests for the <code>org.apache.struts.config.FormPropertyConfig</code>
    27   * class.
    28   *
    29   * @version $Rev: 471754 $ $Date: 2005-05-21 19:06:53 -0400 (Sat, 21 May 2005)
    30   *          $
    31   */
    32  public class TestFormPropertyConfig extends TestCase {
    33      public void testBasicInherit()
    34          throws Exception {
    35          FormPropertyConfig base =
    36              new FormPropertyConfig("base", "java.lang.String[]", "", 10);
    37          String baseCount = "10";
    38  
    39          base.setProperty("count", baseCount);
    40  
    41          FormPropertyConfig sub = new FormPropertyConfig();
    42  
    43          sub.setName("base");
    44  
    45          sub.inheritFrom(base);
    46  
    47          assertEquals("Type was not inherited", base.getType(), sub.getType());
    48          assertEquals("Initial is incorrect", base.getInitial(), sub.getInitial());
    49          assertEquals("Size was not inherited", base.getSize(), sub.getSize());
    50          assertEquals("Arbitrary config property was not inherited", baseCount,
    51              sub.getProperty("count"));
    52      }
    53  
    54      public void testInheritWithInitialOverride()
    55          throws Exception {
    56          FormPropertyConfig base =
    57              new FormPropertyConfig("base", "java.lang.String", "value");
    58  
    59          FormPropertyConfig sub = new FormPropertyConfig();
    60  
    61          sub.setName("base");
    62  
    63          String initial = "otherValue";
    64  
    65          sub.setInitial(initial);
    66  
    67          sub.inheritFrom(base);
    68  
    69          assertEquals("Type was not inherited", base.getType(), sub.getType());
    70          assertEquals("Initial is incorrect", initial, sub.getInitial());
    71          assertEquals("Size is incorrect", base.getSize(), sub.getSize());
    72      }
    73  
    74      public void testInheritWithTypeOverride()
    75          throws Exception {
    76          FormPropertyConfig base =
    77              new FormPropertyConfig("base", "java.lang.String", "");
    78  
    79          FormPropertyConfig sub = new FormPropertyConfig();
    80  
    81          sub.setName("base");
    82          sub.setType("java.lang.Integer");
    83  
    84          sub.inheritFrom(base);
    85  
    86          assertEquals("Type is incorrect", "java.lang.Integer", sub.getType());
    87          assertEquals("Initial is incorrect", base.getInitial(), sub.getInitial());
    88          assertEquals("Size is incorrect", base.getSize(), sub.getSize());
    89      }
    90  
    91      public void testInheritWithTypeOverride2()
    92          throws Exception {
    93          FormPropertyConfig base =
    94              new FormPropertyConfig("base", "java.lang.String", "");
    95  
    96          FormPropertyConfig sub = new FormPropertyConfig();
    97  
    98          sub.setName("base");
    99  
    100         String type = "java.lang.Integer[]";
    101         int size = 10;
    102 
    103         sub.setType(type);
    104         sub.setSize(size);
    105 
    106         sub.inheritFrom(base);
    107 
    108         assertEquals("Type is incorrect", type, sub.getType());
    109         assertEquals("Initial is incorrect", base.getInitial(), sub.getInitial());
    110         assertEquals("Size is incorrect", size, sub.getSize());
    111     }
    112 
    113     public void testInheritWithSizeOverride()
    114         throws Exception {
    115         FormPropertyConfig base =
    116             new FormPropertyConfig("base", "java.lang.String[]", "", 20);
    117 
    118         FormPropertyConfig sub = new FormPropertyConfig();
    119 
    120         sub.setName("base");
    121 
    122         int size = 50;
    123 
    124         sub.setSize(size);
    125 
    126         sub.inheritFrom(base);
    127 
    128         assertEquals("Type was not inherited", base.getType(), sub.getType());
    129         assertEquals("Initial is incorrect", base.getInitial(), sub.getInitial());
    130         assertEquals("Size is incorrect", size, sub.getSize());
    131     }
    132 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
