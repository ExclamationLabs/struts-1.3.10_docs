[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockFormBean.html.md)


    1   /*
    2    * $Id: MockFormBean.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.mock;
    22  
    23  import org.apache.struts.action.ActionForm;
    24  
    25  import java.util.HashMap;
    26  import java.util.Map;
    27  
    28  /**
    29   * <p>General purpose form bean for unit tests.</p>
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-05-07 12:45:39 -0400 (Sat, 07 May 2005)
    32   *          $
    33   */
    34  public class MockFormBean extends ActionForm {
    35      /*
    36       * <p>
    37       * Flag to indicate whether certain methods should complete properly
    38       * or throw an Exception
    39       * </p>
    40       */
    41      private boolean throwException = false;
    42      private boolean returnNulls = false;
    43      private String defaultValue;
    44      private Double defaultDouble;
    45      private int arrayCount;
    46      protected boolean booleanProperty = false;
    47      protected String stringProperty = null;
    48  
    49      // ------------------- Constructors
    50      public MockFormBean() {
    51          this(null);
    52      }
    53  
    54      public MockFormBean(boolean throwException, boolean returnNulls) {
    55          super();
    56          this.throwException = throwException;
    57          this.returnNulls = returnNulls;
    58      }
    59  
    60      public MockFormBean(boolean throwException) {
    61          this.throwException = throwException;
    62      }
    63  
    64      public MockFormBean(boolean throwException, boolean returnNulls,
    65          String defaultValue) {
    66          this(throwException, returnNulls);
    67          this.defaultValue = defaultValue;
    68      }
    69  
    70      public MockFormBean(String stringProperty) {
    71          this.stringProperty = stringProperty;
    72      }
    73  
    74      public MockFormBean(boolean throwException, boolean returnNulls,
    75          String defaultValue, int arrayCount) {
    76          this(throwException, returnNulls, defaultValue);
    77          this.arrayCount = arrayCount;
    78      }
    79  
    80      public MockFormBean(boolean throwException, boolean returnNulls,
    81          Double defaultDouble) {
    82          this(throwException, returnNulls);
    83          this.defaultDouble = defaultDouble;
    84      }
    85  
    86      // ------------------- public methods
    87      public String getJustThrowAnException()
    88          throws Exception {
    89          throw new Exception();
    90      }
    91  
    92      public Object getThrowIllegalAccessException()
    93          throws Exception {
    94          if (true) {
    95              throw new IllegalAccessException();
    96          }
    97  
    98          return null;
    99      }
    100 
    101     public String getStringValue()
    102         throws Exception {
    103         if (throwException) {
    104             throw new Exception();
    105         }
    106 
    107         if (returnNulls) {
    108             return null;
    109         }
    110 
    111         return defaultValue;
    112     }
    113 
    114     public String[] getStringArray()
    115         throws Exception {
    116         if (throwException) {
    117             throw new Exception();
    118         }
    119 
    120         if (returnNulls) {
    121             return null;
    122         }
    123 
    124         String[] rtn = new String[arrayCount];
    125 
    126         for (int i = 0; i < rtn.length; i++) {
    127             rtn[i] = defaultValue + i;
    128         }
    129 
    130         return rtn;
    131     }
    132 
    133     public Double getDoubleValue()
    134         throws Exception {
    135         if (throwException) {
    136             throw new Exception();
    137         }
    138 
    139         if (returnNulls) {
    140             return null;
    141         }
    142 
    143         return defaultDouble;
    144     }
    145 
    146     public boolean getBooleanProperty() {
    147         return (this.booleanProperty);
    148     }
    149 
    150     public void setBooleanProperty(boolean booleanProperty) {
    151         this.booleanProperty = booleanProperty;
    152     }
    153 
    154     public Map getMapProperty() {
    155         HashMap map = new HashMap();
    156 
    157         map.put("foo1", "bar1");
    158         map.put("foo2", "bar2");
    159 
    160         return (map);
    161     }
    162 
    163     public Map getMapPropertyArrayValues() {
    164         HashMap map = new HashMap();
    165 
    166         map.put("foo1", new String[] { "bar1", "baz1" });
    167         map.put("foo2", new String[] { "bar2", "baz2" });
    168 
    169         return (map);
    170     }
    171 
    172     public String getStringProperty() {
    173         return (this.stringProperty);
    174     }
    175 
    176     public void setStringProperty(String stringProperty) {
    177         this.stringProperty = stringProperty;
    178     }
    179 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
