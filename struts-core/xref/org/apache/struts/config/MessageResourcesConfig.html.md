[View Javadoc](../../../../../apidocs/org/apache/struts/config/MessageResourcesConfig.html.md)


    1   /*
    2    * $Id: MessageResourcesConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.Globals;
    24  
    25  /**
    26   * <p>A JavaBean representing the configuration information of a
    27   * <code>&lt;message-resources&gt;</code> element in a Struts configuration
    28   * file.</p>
    29   *
    30   * @version $Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005)
    31   *          $
    32   * @since Struts 1.1
    33   */
    34  public class MessageResourcesConfig extends BaseConfig {
    35      // ------------------------------------------------------------- Properties
    36  
    37      /**
    38       * Fully qualified Java class name of the MessageResourcesFactory class we
    39       * should use.
    40       */
    41      protected String factory =
    42          "org.apache.struts.util.PropertyMessageResourcesFactory";
    43  
    44      /**
    45       * The servlet context attributes key under which this MessageResources
    46       * instance is stored.
    47       */
    48      protected String key = Globals.MESSAGES_KEY;
    49  
    50      /**
    51       * Should we return <code>null</code> for unknown message keys?
    52       */
    53      protected boolean nullValue = true;
    54  
    55      /**
    56       * Indicates whether 'escape processing' should be performed on the error
    57       * message string.
    58       */
    59      private boolean escape = true;
    60  
    61      /**
    62       * Parameter that is passed to the <code>createResources()</code> method
    63       * of our MessageResourcesFactory implementation.
    64       */
    65      protected String parameter = null;
    66  
    67      public String getFactory() {
    68          return (this.factory);
    69      }
    70  
    71      public void setFactory(String factory) {
    72          if (configured) {
    73              throw new IllegalStateException("Configuration is frozen");
    74          }
    75  
    76          this.factory = factory;
    77      }
    78  
    79      public String getKey() {
    80          return (this.key);
    81      }
    82  
    83      public void setKey(String key) {
    84          if (configured) {
    85              throw new IllegalStateException("Configuration is frozen");
    86          }
    87  
    88          this.key = key;
    89      }
    90  
    91      public boolean getNull() {
    92          return (this.nullValue);
    93      }
    94  
    95      public void setNull(boolean nullValue) {
    96          if (configured) {
    97              throw new IllegalStateException("Configuration is frozen");
    98          }
    99  
    100         this.nullValue = nullValue;
    101     }
    102 
    103     /**
    104      * Indicates whether 'escape processing' should be performed on the error
    105      * message string.
    106      *
    107      * @since Struts 1.2.8
    108      */
    109     public boolean isEscape() {
    110         return escape;
    111     }
    112 
    113     /**
    114      * Set whether 'escape processing' should be performed on the error
    115      * message string.
    116      *
    117      * @since Struts 1.2.8
    118      */
    119     public void setEscape(boolean escape) {
    120         this.escape = escape;
    121     }
    122 
    123     public String getParameter() {
    124         return (this.parameter);
    125     }
    126 
    127     public void setParameter(String parameter) {
    128         if (configured) {
    129             throw new IllegalStateException("Configuration is frozen");
    130         }
    131 
    132         this.parameter = parameter;
    133     }
    134 
    135     // --------------------------------------------------------- Public Methods
    136 
    137     /**
    138      * Return a String representation of this object.
    139      */
    140     public String toString() {
    141         StringBuffer sb = new StringBuffer("MessageResourcesConfig[");
    142 
    143         sb.append("factory=");
    144         sb.append(this.factory);
    145         sb.append(",null=");
    146         sb.append(this.nullValue);
    147         sb.append(",escape=");
    148         sb.append(this.escape);
    149         sb.append(",parameter=");
    150         sb.append(this.parameter);
    151         sb.append("]");
    152 
    153         return (sb.toString());
    154     }
    155 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
