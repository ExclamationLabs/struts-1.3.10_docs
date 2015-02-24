[View Javadoc](../../../apidocs/examples/bean/ExampleBean.html.md)


    1   /*
    2    * $Id: ExampleBean.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples.bean;
    23  
    24  import java.io.Serializable;
    25  import java.util.ArrayList;
    26  import java.util.List;
    27  
    28  /**
    29   * An example bean for Bean Examples
    30   *
    31   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    32   */
    33  public class ExampleBean implements Serializable {
    34  
    35      // ------------------------------------------------------ Instance Variables
    36  
    37      /** A boolean value */
    38      private boolean booleanValue = false;
    39  
    40      /** A double value */
    41      private double doubleValue = 45213.451;
    42  
    43      /** A float value */
    44      private float floatValue = -123.582F;
    45  
    46      /** An integer value */
    47      private int intValue = 256;
    48  
    49      /** A long integer value */
    50      private long longValue = 1321546L;
    51  
    52      /** A short integer value */
    53      private short shortValue = 257;
    54  
    55      /** A string value */
    56      private String stringValue = "Hello, world!";
    57  
    58      /** A dateValue value */
    59      private java.util.Date dateValue = new java.util.Date();
    60  
    61      /** A list */
    62      private List list = new ArrayList();
    63  
    64      /** An array */
    65      private String[] array = { "Red", "Green", "Blue", "Black", "Orange" };
    66  
    67      /** A nested bean */
    68      private NestedBean nested = null;
    69  
    70      /** HTML formatted markup */
    71      private String.html.md =
    72            "<p>This is a <strong>simple</strong> example of "
    73          + "<em>HTML</em> formatted text.</p>";
    74  
    75      // ------------------------------------------------------------ Constructors
    76  
    77      /**
    78       * Constructor for TestBean.
    79       */
    80      public ExampleBean() {
    81          super();
    82      }
    83  
    84  
    85      // -------------------------------------------------------------- Properties
    86  
    87      /**
    88       * Returns the booleanValue.
    89       * @return boolean
    90       */
    91      public boolean isBooleanValue() {
    92          return booleanValue;
    93      }
    94  
    95      /**
    96       * Returns the doubleValue.
    97       * @return double
    98       */
    99      public double getDoubleValue() {
    100         return doubleValue;
    101     }
    102 
    103     /**
    104      * Returns the floatValue.
    105      * @return float
    106      */
    107     public float getFloatValue() {
    108         return floatValue;
    109     }
    110 
    111     /**
    112      * Returns the intValue.
    113      * @return int
    114      */
    115     public int getIntValue() {
    116         return intValue;
    117     }
    118 
    119     /**
    120      * Returns the longValue.
    121      * @return long
    122      */
    123     public long getLongValue() {
    124         return longValue;
    125     }
    126 
    127     /**
    128      * Returns the shortValue.
    129      * @return short
    130      */
    131     public short getShortValue() {
    132         return shortValue;
    133     }
    134 
    135     /**
    136      * Returns the stringValue.
    137      * @return String
    138      */
    139     public String getStringValue() {
    140         return stringValue;
    141     }
    142 
    143     /**
    144      * Sets the booleanValue.
    145      * @param booleanValue The booleanValue to set
    146      */
    147     public void setBooleanValue(boolean booleanValue) {
    148         this.booleanValue = booleanValue;
    149     }
    150 
    151     /**
    152      * Sets the doubleValue.
    153      * @param doubleValue The doubleValue to set
    154      */
    155     public void setDoubleValue(double doubleValue) {
    156         this.doubleValue = doubleValue;
    157     }
    158 
    159     /**
    160      * Sets the floatValue.
    161      * @param floatValue The floatValue to set
    162      */
    163     public void setFloatValue(float floatValue) {
    164         this.floatValue = floatValue;
    165     }
    166 
    167     /**
    168      * Sets the intValue.
    169      * @param intValue The intValue to set
    170      */
    171     public void setIntValue(int intValue) {
    172         this.intValue = intValue;
    173     }
    174 
    175     /**
    176      * Sets the longValue.
    177      * @param longValue The longValue to set
    178      */
    179     public void setLongValue(long longValue) {
    180         this.longValue = longValue;
    181     }
    182 
    183     /**
    184      * Sets the shortValue.
    185      * @param shortValue The shortValue to set
    186      */
    187     public void setShortValue(short shortValue) {
    188         this.shortValue = shortValue;
    189     }
    190 
    191     /**
    192      * Sets the stringValue.
    193      * @param stringValue The stringValue to set
    194      */
    195     public void setStringValue(String stringValue) {
    196         this.stringValue = stringValue;
    197     }
    198 
    199     /**
    200      * Returns the list.
    201      * @return List
    202      */
    203     public List getList() {
    204         return list;
    205     }
    206 
    207     /**
    208      * Sets the list.
    209      * @param list The list to set
    210      */
    211     public void setList(List list) {
    212         this.list = list;
    213     }
    214 
    215     /**
    216      * Returns the nested.
    217      * @return NestedBean
    218      */
    219     public NestedBean getNested() {
    220         return nested;
    221     }
    222 
    223     /**
    224      * Sets the nested.
    225      * @param nested The nested to set
    226      */
    227     public void setNested(NestedBean nested) {
    228         this.nested = nested;
    229     }
    230 
    231     /**
    232      * Returns the dateValue.
    233      * @return java.util.Date
    234      */
    235     public java.util.Date getDateValue() {
    236         return dateValue;
    237     }
    238 
    239     /**
    240      * Sets the dateValue.
    241      * @param date The date to set
    242      */
    243     public void setDateValue(java.util.Date date) {
    244         this.dateValue = date;
    245     }
    246 
    247     /**
    248      * Returns the array.
    249      * @return String[]
    250      */
    251     public String[] getArray() {
    252         return array;
    253     }
    254 
    255     /**
    256      * Sets the array.
    257      * @param array The array to set
    258      */
    259     public void setArray(String[] array) {
    260         this.array = array;
    261     }
    262 
    263     /**
    264      * Returns the.html.md.
    265      * @return String
    266      */
    267     public String getHtml() {
    268         return.html.md;
    269     }
    270 
    271     /**
    272      * Sets the.html.md.
    273      * @param.html.md The html to set
    274      */
    275     public void setHtml(String.html.md) {
    276         this.html.md = html;
    277     }
    278 
    279 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
