[View Javadoc](../../../../../apidocs/org/apache/struts/config/BaseConfig.html.md)


    1   /*
    2    * $Id: BaseConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.io.Serializable;
    24  
    25  import java.util.Enumeration;
    26  import java.util.Properties;
    27  
    28  /**
    29   * <p> A abstract base class for all config classes.  Provide basic support
    30   * for arbitrary properties </p>
    31   *
    32   * @since Struts 1.3
    33   */
    34  public abstract class BaseConfig implements Serializable {
    35      /**
    36       * Indicates if configuration of this component been completed. TODO
    37       * change protected to private and use methods provided by extenders?
    38       */
    39      protected boolean configured = false;
    40  
    41      /**
    42       * A map of arbitrary properties configured for this component.
    43       *
    44       * @since Struts 1.3
    45       */
    46      private Properties properties = new Properties();
    47  
    48      /**
    49       * Freeze the configuration of this action.
    50       */
    51      public void freeze() {
    52          configured = true;
    53      }
    54  
    55      /**
    56       * Throw <code>IllegalStateException</code> if configuration is frozen.
    57       *
    58       * @throws IllegalStateException if configuration is frozen
    59       */
    60      public void throwIfConfigured() {
    61          if (configured) {
    62              throw new IllegalStateException("Configuration is frozen");
    63          }
    64      }
    65  
    66      /**
    67       * <p> Set an arbitary key/value pair which can be retrieved by this
    68       * config class. This facility should eliminate many use cases for
    69       * subclassing <code>*Config</code> classes by providing a mechanism to
    70       * pass any amount of arbitrary configuration information into an config
    71       * class. <p /> This method must not be called after configuration is
    72       * complete, or an <code>IllegalStateException</code> will be thrown.</p>
    73       *
    74       * <p><b>Example</b>
    75       * <code><pre>
    76       * &lt;action path="/example" type="com.example.MyAction"&gt;
    77       *    &lt;set-property key="foo" property="bar" /&gt;
    78       * &lt;/action&gt;
    79       * </pre></code>
    80       * </p>
    81       *
    82       * @param key   the key by which this value will be retrieved
    83       * @param value the value to store with the supplied key
    84       * @throws IllegalStateException if this module configuration has been
    85       *                               frozen
    86       * @since Struts 1.3
    87       */
    88      public void setProperty(String key, String value) {
    89          throwIfConfigured();
    90          properties.setProperty(key, value);
    91      }
    92  
    93      /**
    94       * Return the property-value for the specified key, if any; otherwise
    95       * return <code>null</code>.
    96       *
    97       * @param key a key specified in the <code>struts-config</code> file
    98       * @return the value stored with the supplied key
    99       * @since Struts 1.3
    100      */
    101     public String getProperty(String key) {
    102         return properties.getProperty(key);
    103     }
    104 
    105     /**
    106      * <p> Return the entire set of properties configured for this object. At
    107      * this time, this only needs to be exposed to support inheritance, so
    108      * choosing a conservative access modifier ("protected"). </p>
    109      *
    110      * @return set of properties configured for this object
    111      */
    112     protected Properties getProperties() {
    113         return this.properties;
    114     }
    115 
    116     /**
    117      * Set the entire set of properties configured for this object. At this
    118      * time, this only needs to be exposed to support inheritance, so choosing
    119      * a conservative access modifier ("protected").
    120      */
    121     protected void setProperties(Properties properties) {
    122         this.properties = properties;
    123     }
    124 
    125     /**
    126      * <p>Compare the properties of this config with that of the given and
    127      * copy those that are not present.  This method is used by subclasses
    128      * that support configuration inheritance.</p>
    129      *
    130      * @param baseConfig The config object to copy properties from.
    131      */
    132     protected void inheritProperties(BaseConfig baseConfig) {
    133         throwIfConfigured();
    134 
    135         // Inherit forward properties
    136         Properties baseProperties = baseConfig.getProperties();
    137         Enumeration keys = baseProperties.propertyNames();
    138 
    139         while (keys.hasMoreElements()) {
    140             String key = (String) keys.nextElement();
    141 
    142             // Check if we have this property before copying it
    143             String value = this.getProperty(key);
    144 
    145             if (value == null) {
    146                 value = baseProperties.getProperty(key);
    147                 setProperty(key, value);
    148             }
    149         }
    150     }
    151 
    152     /**
    153      * <p>Return a copy of the properties held by this object.</p>
    154      */
    155     protected Properties copyProperties() {
    156         Properties copy = new Properties();
    157 
    158         Enumeration keys = properties.propertyNames();
    159 
    160         while (keys.hasMoreElements()) {
    161             String key = (String) keys.nextElement();
    162 
    163             copy.setProperty(key, properties.getProperty(key));
    164         }
    165 
    166         return copy;
    167     }
    168 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
