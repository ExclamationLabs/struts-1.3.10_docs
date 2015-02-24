
    1   /*
    2    * $Id: PojoBean.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.util.HashMap;
    24  import java.util.Map;
    25  
    26  /**
    27   * Test Bean class.
    28   */
    29  public class PojoBean {
    30      protected String stringValue1;
    31      protected String stringValue2;
    32      protected int intValue1;
    33      protected int intValue2;
    34      protected Integer integerValue1;
    35      protected Integer integerValue2;
    36      protected PojoBean[] beans;
    37      protected Map map = new HashMap();
    38  
    39      /**
    40       * Default Constructor
    41       */
    42      public PojoBean() {
    43      }
    44  
    45      /**
    46       * Construct Bean with a pair of String values.
    47       */
    48      public PojoBean(String stringValue1, String stringValue2) {
    49          setStringValue1(stringValue1);
    50          setStringValue2(stringValue2);
    51      }
    52  
    53      /**
    54       * Construct Bean with a pair of integer values.
    55       */
    56      public PojoBean(int intValue1, int intValue2) {
    57          setIntValue1(intValue1);
    58          setIntValue2(intValue2);
    59          setIntegerValue1(new Integer(intValue1));
    60          setIntegerValue2(new Integer(intValue2));
    61      }
    62  
    63      /**
    64       * Set the stringValue1.
    65       */
    66      public void setStringValue1(String stringValue1) {
    67          this.stringValue1 = stringValue1;
    68      }
    69  
    70      /**
    71       * Return stringValue1.
    72       */
    73      public String getStringValue1() {
    74          return stringValue1;
    75      }
    76  
    77      /**
    78       * Set the stringValue2.
    79       */
    80      public void setStringValue2(String stringValue2) {
    81          this.stringValue2 = stringValue2;
    82      }
    83  
    84      /**
    85       * Return stringValue2.
    86       */
    87      public String getStringValue2() {
    88          return stringValue2;
    89      }
    90  
    91      /**
    92       * Set the intValue1.
    93       */
    94      public void setIntValue1(int intValue1) {
    95          this.intValue1 = intValue1;
    96      }
    97  
    98      /**
    99       * Return intValue1.
    100      */
    101     public int getIntValue1() {
    102         return intValue1;
    103     }
    104 
    105     /**
    106      * Set the intValue2.
    107      */
    108     public void setIntValue2(int intValue2) {
    109         this.intValue2 = intValue2;
    110     }
    111 
    112     /**
    113      * Return intValue2.
    114      */
    115     public int getIntValue2() {
    116         return intValue2;
    117     }
    118 
    119     /**
    120      * Set the integerValue1.
    121      */
    122     public void setIntegerValue1(Integer integerValue1) {
    123         this.integerValue1 = integerValue1;
    124     }
    125 
    126     /**
    127      * Return integerValue1.
    128      */
    129     public Integer getIntegerValue1() {
    130         return integerValue1;
    131     }
    132 
    133     /**
    134      * Set the integerValue2.
    135      */
    136     public void setIntegerValue2(Integer integerValue2) {
    137         this.integerValue2 = integerValue2;
    138     }
    139 
    140     /**
    141      * Return integerValue2.
    142      */
    143     public Integer getIntegerValue2() {
    144         return integerValue2;
    145     }
    146 
    147     /**
    148      * Set the PojoBean[].
    149      */
    150     public void setBeans(PojoBean[] beans) {
    151         this.beans = beans;
    152     }
    153 
    154     /**
    155      * Return PojoBean[].
    156      */
    157     public PojoBean[] getBeans() {
    158         return beans;
    159     }
    160 
    161     /**
    162      * Return and indexed Bean
    163      */
    164     public PojoBean getBean(int index) {
    165         return beans[index];
    166     }
    167 
    168     /**
    169      * Return the Map
    170      */
    171     public Object getMap() {
    172         return map;
    173     }
    174 
    175     /**
    176      * Return the Map
    177      */
    178     public void setMap(Map map) {
    179         this.map = map;
    180     }
    181 
    182     /**
    183      * Set a  Mapped property
    184      */
    185     public void setMapped(String key, Object value) {
    186         map.put(key, value);
    187     }
    188 
    189     /**
    190      * Set a  Mapped property
    191      */
    192     public Object getMapped(String key) {
    193         return map.get(key);
    194     }
    195 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
