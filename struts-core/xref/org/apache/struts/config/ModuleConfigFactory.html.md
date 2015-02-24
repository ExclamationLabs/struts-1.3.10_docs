[View Javadoc](../../../../../apidocs/org/apache/struts/config/ModuleConfigFactory.html.md)


    1   /*
    2    * $Id: ModuleConfigFactory.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.util.RequestUtils;
    26  
    27  /**
    28   * A factory interface for creating {@link ModuleConfig}s.
    29   *
    30   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    31   *          $
    32   * @see ModuleConfig
    33   */
    34  public abstract class ModuleConfigFactory {
    35      /**
    36       * The Java class to be used for <code>ModuleConfigFactory</code>
    37       * instances.
    38       */
    39      protected static Class clazz = null;
    40  
    41      /**
    42       * Commons Logging instance.
    43       */
    44      private static final Log LOG = LogFactory.getLog(ModuleConfigFactory.class);
    45  
    46      /**
    47       * The fully qualified class name to be used for <code>ModuleConfigFactory</code>
    48       * instances.
    49       */
    50      protected static String factoryClass =
    51          "org.apache.struts.config.impl.DefaultModuleConfigFactory";
    52  
    53      /**
    54       * Create and return a newly instansiated {@link ModuleConfig}. This
    55       * method must be implemented by concrete subclasses.
    56       *
    57       * @param prefix Module prefix for Configuration
    58       */
    59      public abstract ModuleConfig createModuleConfig(String prefix);
    60  
    61      // ------------------------------------------------------ Static Properties
    62  
    63      /**
    64       * The fully qualified class name that is used for <code>ModuleConfigFactory</code>
    65       * instances.
    66       *
    67       * @return class name that is used for <code>ModuleConfigFactory</code>
    68       *         instances
    69       */
    70      public static String getFactoryClass() {
    71          return (ModuleConfigFactory.factoryClass);
    72      }
    73  
    74      /**
    75       * Set the fully qualified class name that is used for
    76       * <code>ModuleConfigFactory</code> instances.
    77       *
    78       * @param factoryClass name that is used for <code>ModuleConfigFactory</code>
    79       *                     instances
    80       */
    81      public static void setFactoryClass(String factoryClass) {
    82          ModuleConfigFactory.factoryClass = factoryClass;
    83          ModuleConfigFactory.clazz = null;
    84      }
    85  
    86      // --------------------------------------------------------- Static Methods
    87  
    88      /**
    89       * Create and return a <code>ModuleConfigFactory</code> instance of the
    90       * appropriate class, which can be used to create customized
    91       * <code>ModuleConfig</code> instances.  If no such factory can be
    92       * created, return <code>null</code> instead.
    93       */
    94      public static ModuleConfigFactory createFactory() {
    95          ModuleConfigFactory factory = null;
    96  
    97          try {
    98              if (clazz == null) {
    99                  clazz = RequestUtils.applicationClass(factoryClass);
    100             }
    101 
    102             factory = (ModuleConfigFactory) clazz.newInstance();
    103         } catch (ClassNotFoundException e) {
    104             LOG.error("ModuleConfigFactory.createFactory()", e);
    105         } catch (InstantiationException e) {
    106             LOG.error("ModuleConfigFactory.createFactory()", e);
    107         } catch (IllegalAccessException e) {
    108             LOG.error("ModuleConfigFactory.createFactory()", e);
    109         }
    110 
    111         return factory;
    112     }
    113 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
