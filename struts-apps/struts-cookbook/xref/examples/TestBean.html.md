[View Javadoc](../../apidocs/examples/TestBean.html.md)


    1   /*
    2    * $Id: TestBean.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples;
    23  
    24  import java.io.Serializable;
    25  
    26  
    27  /**
    28   * An example bean for Bean Examples
    29   *
    30   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    31   */
    32  public class TestBean implements Serializable {
    33  
    34      // ------------------------------------------------------ Instance Variables
    35  
    36      /** A boolean value */
    37      private boolean booleanValue = false;
    38  
    39      /** A double value */
    40      private double doubleValue = 45213.451;
    41  
    42      /** A float value */
    43      private float floatValue = -123.582F;
    44  
    45      /** An integer value */
    46      private int intValue = 256;
    47  
    48      /** A long integer value */
    49      private long longValue = 1321546L;
    50  
    51      /** A short integer value */
    52      private short shortValue = 257;
    53  
    54      /** A string value */
    55      private String stringValue = "Hello, world!";
    56  
    57      /** A dateValue value */
    58      private java.util.Date dateValue = new java.util.Date();
    59  
    60      // ------------------------------------------------------------ Constructors
    61  
    62      /**
    63       * Constructor for TestBean.
    64       */
    65      public TestBean() {
    66          super();
    67      }
    68  
    69      // -------------------------------------------------------------- Properties
    70  
    71      /**
    72       * Returns the booleanValue.
    73       * @return boolean
    74       */
    75      public boolean isBooleanValue() {
    76          return booleanValue;
    77      }
    78  
    79      /**
    80       * Returns the doubleValue.
    81       * @return double
    82       */
    83      public double getDoubleValue() {
    84          return doubleValue;
    85      }
    86  
    87      /**
    88       * Returns the floatValue.
    89       * @return float
    90       */
    91      public float getFloatValue() {
    92          return floatValue;
    93      }
    94  
    95      /**
    96       * Returns the intValue.
    97       * @return int
    98       */
    99      public int getIntValue() {
    100         return intValue;
    101     }
    102 
    103     /**
    104      * Returns the longValue.
    105      * @return long
    106      */
    107     public long getLongValue() {
    108         return longValue;
    109     }
    110 
    111     /**
    112      * Returns the shortValue.
    113      * @return short
    114      */
    115     public short getShortValue() {
    116         return shortValue;
    117     }
    118 
    119     /**
    120      * Returns the stringValue.
    121      * @return String
    122      */
    123     public String getStringValue() {
    124         return stringValue;
    125     }
    126 
    127     /**
    128      * Sets the booleanValue.
    129      * @param booleanValue The booleanValue to set
    130      */
    131     public void setBooleanValue(boolean booleanValue) {
    132         this.booleanValue = booleanValue;
    133     }
    134 
    135     /**
    136      * Sets the doubleValue.
    137      * @param doubleValue The doubleValue to set
    138      */
    139     public void setDoubleValue(double doubleValue) {
    140         this.doubleValue = doubleValue;
    141     }
    142 
    143     /**
    144      * Sets the floatValue.
    145      * @param floatValue The floatValue to set
    146      */
    147     public void setFloatValue(float floatValue) {
    148         this.floatValue = floatValue;
    149     }
    150 
    151     /**
    152      * Sets the intValue.
    153      * @param intValue The intValue to set
    154      */
    155     public void setIntValue(int intValue) {
    156         this.intValue = intValue;
    157     }
    158 
    159     /**
    160      * Sets the longValue.
    161      * @param longValue The longValue to set
    162      */
    163     public void setLongValue(long longValue) {
    164         this.longValue = longValue;
    165     }
    166 
    167     /**
    168      * Sets the shortValue.
    169      * @param shortValue The shortValue to set
    170      */
    171     public void setShortValue(short shortValue) {
    172         this.shortValue = shortValue;
    173     }
    174 
    175     /**
    176      * Sets the stringValue.
    177      * @param stringValue The stringValue to set
    178      */
    179     public void setStringValue(String stringValue) {
    180         this.stringValue = stringValue;
    181     }
    182 
    183     /**
    184      * Returns the dateValue.
    185      * @return java.util.Date
    186      */
    187     public java.util.Date getDateValue() {
    188         return dateValue;
    189     }
    190 
    191     /**
    192      * Sets the dateValue.
    193      * @param date The date to set
    194      */
    195     public void setDateValue(java.util.Date date) {
    196         this.dateValue = date;
    197     }
    198 
    199 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
