[View Javadoc](../../../../../apidocs/org/apache/struts/util/MessageResourcesFactory.html.md)


    1   /*
    2    * $Id: MessageResourcesFactory.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.config.MessageResourcesConfig;
    26  
    27  import java.io.Serializable;
    28  
    29  /**
    30   * Factory for <code>MessageResources</code> instances.  The general usage
    31   * pattern for this class is:
    32   *
    33   * <ul>
    34   *
    35   * <li>Call <code>MessageResourcesFactory().createFactory()</code> to retrieve
    36   * a <code>MessageResourcesFactory</code> instance.</li> <li>Set properties as
    37   * required to configure this factory instance to create
    38   * <code>MessageResources</code> instances with desired characteristics.</li>
    39   *
    40   * <li>Call the <code>createResources()</code> method of the factory to
    41   * retrieve a newly instantiated <code>MessageResources</code> instance.</li>
    42   *
    43   * </ul>
    44   *
    45   * @version $Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005)
    46   *          $
    47   */
    48  public abstract class MessageResourcesFactory implements Serializable {
    49      // ------------------------------------------------------ Static Properties
    50  
    51      /**
    52       * The Java class to be used for <code>MessageResourcesFactory</code>
    53       * instances.
    54       */
    55      protected static transient Class clazz = null;
    56  
    57      /**
    58       * Commons Logging instance.
    59       */
    60      private static Log LOG = LogFactory.getLog(MessageResourcesFactory.class);
    61  
    62      /**
    63       * The fully qualified class name to be used for <code>MessageResourcesFactory</code>
    64       * instances.
    65       */
    66      protected static String factoryClass =
    67          "org.apache.struts.util.PropertyMessageResourcesFactory";
    68  
    69      // ---------------------------------------------------- Instance Properties
    70  
    71      /**
    72       * Configuration information for Message Resources.
    73       */
    74      protected MessageResourcesConfig config;
    75  
    76      /**
    77       * The "return null" property value to which newly created
    78       * MessageResourcess should be initialized.
    79       */
    80      protected boolean returnNull = true;
    81  
    82      /**
    83       * Set the configuration information for Message Resources.
    84       *
    85       * @since Struts 1.2.8
    86       */
    87      public MessageResourcesConfig getConfig() {
    88          return config;
    89      }
    90  
    91      /**
    92       * Return the configuration information for Message Resources.
    93       *
    94       * @since Struts 1.2.8
    95       */
    96      public void setConfig(MessageResourcesConfig config) {
    97          this.config = config;
    98      }
    99  
    100     /**
    101      * Get default value of the "returnNull" property used to initialize newly
    102      * created MessageResourcess.
    103      *
    104      * @return default value of the "returnNull" property newly created
    105      *         MessageResourcess are initialized to.
    106      */
    107     public boolean getReturnNull() {
    108         return (this.returnNull);
    109     }
    110 
    111     /**
    112      * Set the default value of the "returnNull" property newly created
    113      * MessageResourcess are initialized to.
    114      *
    115      * @param returnNull default value of the "returnNull" MessageResourcess
    116      *                   are initialized to.
    117      */
    118     public void setReturnNull(boolean returnNull) {
    119         this.returnNull = returnNull;
    120     }
    121 
    122     // --------------------------------------------------------- Public Methods
    123 
    124     /**
    125      * Create and return a newly instansiated <code>MessageResources</code>.
    126      * This method must be implemented by concrete subclasses.
    127      *
    128      * @param config Configuration parameter(s) for the requested bundle
    129      */
    130     public abstract MessageResources createResources(String config);
    131 
    132     /**
    133      * The fully qualified class name that is used for <code>MessageResourcesFactory</code>
    134      * instances.
    135      *
    136      * @return class name that is used for <code>MessageResourcesFactory</code>
    137      *         instances
    138      */
    139     public static String getFactoryClass() {
    140         return (MessageResourcesFactory.factoryClass);
    141     }
    142 
    143     /**
    144      * Set the fully qualified class name that is used for
    145      * <code>MessageResourcesFactory</code> instances.
    146      *
    147      * @param factoryClass name that is used for <code>MessageResourcesFactory</code>
    148      *                     instances
    149      */
    150     public static void setFactoryClass(String factoryClass) {
    151         MessageResourcesFactory.factoryClass = factoryClass;
    152         MessageResourcesFactory.clazz = null;
    153     }
    154 
    155     // --------------------------------------------------------- Static Methods
    156 
    157     /**
    158      * Create and return a <code>MessageResourcesFactory</code> instance of
    159      * the appropriate class, which can be used to create customized
    160      * <code>MessageResources</code> instances.  If no such factory can be
    161      * created, return <code>null</code> instead.
    162      */
    163     public static MessageResourcesFactory createFactory() {
    164         // Construct a new instance of the specified factory class
    165         try {
    166             if (clazz == null) {
    167                 clazz = RequestUtils.applicationClass(factoryClass);
    168             }
    169 
    170             MessageResourcesFactory factory =
    171                 (MessageResourcesFactory) clazz.newInstance();
    172 
    173             return (factory);
    174         } catch (Throwable t) {
    175             LOG.error("MessageResourcesFactory.createFactory", t);
    176 
    177             return (null);
    178         }
    179     }
    180 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
