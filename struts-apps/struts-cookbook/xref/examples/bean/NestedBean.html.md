[View Javadoc](../../../apidocs/examples/bean/NestedBean.html.md)


    1   /*
    2    * $Id: NestedBean.java 471754 2006-11-06 14:55:09Z husted $
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
    25  
    26  
    27  /**
    28   * Another Example Bean
    29   *
    30   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    31   */
    32  public class NestedBean implements Serializable {
    33  
    34      // ------------------------------------------------------ Instance Variables
    35  
    36      /** A string value */
    37      private String stringValue = "This is a string from NestedBean";
    38  
    39      // ------------------------------------------------------------ Constructors
    40  
    41      /**
    42       * Constructor for NestedBean.
    43       */
    44      public NestedBean() {
    45          super();
    46      }
    47  
    48      // -------------------------------------------------------------- Properties
    49  
    50  
    51      /**
    52       * Returns the stringValue.
    53       * @return String
    54       */
    55      public String getStringValue() {
    56          return stringValue;
    57      }
    58  
    59      /**
    60       * Sets the stringValue.
    61       * @param stringValue The stringValue to set
    62       */
    63      public void setStringValue(String stringValue) {
    64          this.stringValue = stringValue;
    65      }
    66  
    67   }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
