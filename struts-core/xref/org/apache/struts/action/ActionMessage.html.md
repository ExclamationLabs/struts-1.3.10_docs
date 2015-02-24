[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionMessage.html.md)


    1   /*
    2    * $Id: ActionMessage.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.io.Serializable;
    24  
    25  /**
    26   * <p>An encapsulation of an individual message returned by the
    27   * <code>validate</code> method of an <code>ActionForm</code>, consisting of a
    28   * message key (to be used to look up message text in an appropriate message
    29   * resources database) plus up to four placeholder objects that can be used
    30   * for parametric replacement in the message text.</p>
    31   *
    32   * @version $Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005)
    33   *          $
    34   * @since Struts 1.1
    35   */
    36  public class ActionMessage implements Serializable {
    37      // ----------------------------------------------------- Instance Variables
    38  
    39      /**
    40       * <p>The message key for this message.</p>
    41       */
    42      protected String key = null;
    43  
    44      /**
    45       * <p>The replacement values for this mesasge.</p>
    46       */
    47      protected Object[] values = null;
    48  
    49      /**
    50       * <p>Indicates whether the key is taken to be as a  bundle key [true] or
    51       * literal value [false].</p>
    52       */
    53      protected boolean resource = true;
    54  
    55      // ----------------------------------------------------------- Constructors
    56  
    57      /**
    58       * <p>Construct an action message with no replacement values.</p>
    59       *
    60       * @param key Message key for this message
    61       */
    62      public ActionMessage(String key) {
    63          this(key, null);
    64      }
    65  
    66      /**
    67       * <p>Construct an action message with the specified replacement
    68       * values.</p>
    69       *
    70       * @param key    Message key for this message
    71       * @param value0 First replacement value
    72       */
    73      public ActionMessage(String key, Object value0) {
    74          this(key, new Object[] { value0 });
    75      }
    76  
    77      /**
    78       * <p>Construct an action message with the specified replacement
    79       * values.</p>
    80       *
    81       * @param key    Message key for this message
    82       * @param value0 First replacement value
    83       * @param value1 Second replacement value
    84       */
    85      public ActionMessage(String key, Object value0, Object value1) {
    86          this(key, new Object[] { value0, value1 });
    87      }
    88  
    89      /**
    90       * <p>Construct an action message with the specified replacement
    91       * values.</p>
    92       *
    93       * @param key    Message key for this message
    94       * @param value0 First replacement value
    95       * @param value1 Second replacement value
    96       * @param value2 Third replacement value
    97       */
    98      public ActionMessage(String key, Object value0, Object value1, Object value2) {
    99          this(key, new Object[] { value0, value1, value2 });
    100     }
    101 
    102     /**
    103      * <p>Construct an action message with the specified replacement
    104      * values.</p>
    105      *
    106      * @param key    Message key for this message
    107      * @param value0 First replacement value
    108      * @param value1 Second replacement value
    109      * @param value2 Third replacement value
    110      * @param value3 Fourth replacement value
    111      */
    112     public ActionMessage(String key, Object value0, Object value1,
    113         Object value2, Object value3) {
    114         this(key, new Object[] { value0, value1, value2, value3 });
    115     }
    116 
    117     /**
    118      * <p>Construct an action message with the specified replacement
    119      * values.</p>
    120      *
    121      * @param key    Message key for this message
    122      * @param values Array of replacement values
    123      */
    124     public ActionMessage(String key, Object[] values) {
    125         this.key = key;
    126         this.values = values;
    127         this.resource = true;
    128     }
    129 
    130     /**
    131      * <p>Construct an action message with the specified replacement
    132      * values.</p>
    133      *
    134      * @param key      Message key for this message
    135      * @param resource Indicates whether the key is a bundle key or literal
    136      *                 value
    137      */
    138     public ActionMessage(String key, boolean resource) {
    139         this.key = key;
    140         this.resource = resource;
    141     }
    142 
    143     // --------------------------------------------------------- Public Methods
    144 
    145     /**
    146      * <p>Get the message key for this message.</p>
    147      *
    148      * @return The message key for this message.
    149      */
    150     public String getKey() {
    151         return (this.key);
    152     }
    153 
    154     /**
    155      * <p>Get the replacement values for this message.</p>
    156      *
    157      * @return The replacement values for this message.
    158      */
    159     public Object[] getValues() {
    160         return (this.values);
    161     }
    162 
    163     /**
    164      * <p>Indicate whether the key is taken to be as a  bundle key [true] or
    165      * literal value [false].</p>
    166      *
    167      * @return <code>true</code> if the key is a bundle key;
    168      *         <code>false</code> otherwise.
    169      */
    170     public boolean isResource() {
    171         return (this.resource);
    172     }
    173 
    174     /**
    175      * <p>Returns a String in the format: key[value1, value2, etc].</p>
    176      *
    177      * @return String representation of this message
    178      * @see java.lang.Object#toString()
    179      */
    180     public String toString() {
    181         StringBuffer buff = new StringBuffer();
    182 
    183         buff.append(this.key);
    184         buff.append("[");
    185 
    186         if (this.values != null) {
    187             for (int i = 0; i < this.values.length; i++) {
    188                 buff.append(this.values[i]);
    189 
    190                 // don't append comma to last entry
    191                 if (i < (this.values.length - 1)) {
    192                     buff.append(", ");
    193                 }
    194             }
    195         }
    196 
    197         buff.append("]");
    198 
    199         return buff.toString();
    200     }
    201 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
