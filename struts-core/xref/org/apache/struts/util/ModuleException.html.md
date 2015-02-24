[View Javadoc](../../../../../apidocs/org/apache/struts/util/ModuleException.html.md)


    1   /*
    2    * $Id: ModuleException.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import org.apache.struts.action.ActionMessage;
    24  
    25  /**
    26   * Used for specialized exception handling.
    27   */
    28  public class ModuleException extends Exception {
    29      protected String property = null;
    30  
    31      /**
    32       * The ActionMessage associated with this exception.
    33       *
    34       * @since Struts 1.2
    35       */
    36      protected ActionMessage message = null;
    37  
    38      /**
    39       * Construct an module exception with no replacement values.
    40       *
    41       * @param key Message key for this error message
    42       */
    43      public ModuleException(String key) {
    44          super(key);
    45          message = new ActionMessage(key);
    46      }
    47  
    48      /**
    49       * Construct an module exception with the specified replacement values.
    50       *
    51       * @param key   Message key for this error message
    52       * @param value First replacement value
    53       */
    54      public ModuleException(String key, Object value) {
    55          super(key);
    56          message = new ActionMessage(key, value);
    57      }
    58  
    59      /**
    60       * Construct an module exception with the specified replacement values.
    61       *
    62       * @param key    Message key for this error message
    63       * @param value0 First replacement value
    64       * @param value1 Second replacement value
    65       */
    66      public ModuleException(String key, Object value0, Object value1) {
    67          super(key);
    68          message = new ActionMessage(key, value0, value1);
    69      }
    70  
    71      /**
    72       * Construct an module exception with the specified replacement values.
    73       *
    74       * @param key    Message key for this error message
    75       * @param value0 First replacement value
    76       * @param value1 Second replacement value
    77       * @param value2 Third replacement value
    78       */
    79      public ModuleException(String key, Object value0, Object value1,
    80          Object value2) {
    81          super(key);
    82          message = new ActionMessage(key, value0, value1, value2);
    83      }
    84  
    85      /**
    86       * Construct an module exception with the specified replacement values.
    87       *
    88       * @param key    Message key for this error message
    89       * @param value0 First replacement value
    90       * @param value1 Second replacement value
    91       * @param value2 Third replacement value
    92       * @param value3 Fourth replacement value
    93       */
    94      public ModuleException(String key, Object value0, Object value1,
    95          Object value2, Object value3) {
    96          super(key);
    97          message = new ActionMessage(key, value0, value1, value2, value3);
    98      }
    99  
    100     /**
    101      * Construct an error with the specified replacement values.
    102      *
    103      * @param key    Message key for this message
    104      * @param values Array of replacement values
    105      */
    106     public ModuleException(String key, Object[] values) {
    107         super(key);
    108         message = new ActionMessage(key, values);
    109     }
    110 
    111     /**
    112      * Returns the property associated with the exception.
    113      *
    114      * @return Value of property.
    115      */
    116     public String getProperty() {
    117         return (property != null) ? property : message.getKey();
    118     }
    119 
    120     /**
    121      * Set the property associated with the exception. It can be a name of the
    122      * edit field, which 'caused' the exception.
    123      */
    124     public void setProperty(String property) {
    125         this.property = property;
    126     }
    127 
    128     /**
    129      * Returns the error associated with the exception.
    130      *
    131      * @return Value of property error.
    132      * @since Struts 1.2
    133      */
    134     public ActionMessage getActionMessage() {
    135         return this.message;
    136     }
    137 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
