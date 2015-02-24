[View Javadoc](../../../../../apidocs/org/apache/struts/util/PropertyMessageResourcesFactory.html.md)


    1   /*
    2    * $Id: PropertyMessageResourcesFactory.java 480549 2006-11-29 12:16:15Z niallp $
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
    23  
    24  /**
    25   * Factory for <code>PropertyMessageResources</code> instances.  The
    26   * configuration paramter for such instances is the base Java package name of
    27   * the resources entries from which our keys and values will be loaded.
    28   *
    29   * @version $Rev: 480549 $ $Date: 2006-11-29 06:16:15 -0600 (Wed, 29 Nov 2006) $
    30   */
    31  public class PropertyMessageResourcesFactory extends MessageResourcesFactory {
    32      // --------------------------------------------------------- Public Methods
    33  
    34      /**
    35       * Create and return a newly instansiated <code>MessageResources</code>.
    36       * This method must be implemented by concrete subclasses.
    37       *
    38       * @param config Configuration parameter(s) for the requested bundle
    39       */
    40      public MessageResources createResources(String config) {
    41          PropertyMessageResources messageResources =
    42                 new PropertyMessageResources(this, config, this.returnNull);
    43          String mode = null;
    44          if (getConfig() != null) {
    45              mode = getConfig().getProperty("mode");
    46          }
    47          messageResources.setMode(mode);
    48          return messageResources;
    49      }
    50  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)