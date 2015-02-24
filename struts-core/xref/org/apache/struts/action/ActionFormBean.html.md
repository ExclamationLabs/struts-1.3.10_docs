[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionFormBean.html.md)


    1   /*
    2    * $Id: ActionFormBean.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.config.FormBeanConfig;
    24  
    25  /**
    26   * <p>An <strong>ActionFormBean</strong> is the definition of a form bean that
    27   * is loaded from a <code>&lt;form-bean&gt;</code> element in the Struts
    28   * configuration file. It can be subclassed as necessary to add additional
    29   * properties.</p>
    30   *
    31   * <p>Since Struts 1.1 <code>ActionFormBean</code> extends
    32   * <code>FormBeanConfig</code>.</p>
    33   *
    34   * <p><strong>NOTE</strong> - This class would have been deprecated and
    35   * replaced by <code>org.apache.struts.config.FormBeanConfig</code> except for
    36   * the fact that it is part of the public API that existing applications are
    37   * using.</p>
    38   *
    39   * @version $Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005)
    40   *          $
    41   */
    42  public class ActionFormBean extends FormBeanConfig {
    43      /**
    44       * <p>Construct an instance with default vaslues.</p>
    45       */
    46      public ActionFormBean() {
    47          super();
    48      }
    49  
    50      /**
    51       * <p>Construct an instance with the specified values.</p>
    52       *
    53       * @param name Form bean name
    54       * @param type Fully qualified class name
    55       */
    56      public ActionFormBean(String name, String type) {
    57          super();
    58          setName(name);
    59          setType(type);
    60      }
    61  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)