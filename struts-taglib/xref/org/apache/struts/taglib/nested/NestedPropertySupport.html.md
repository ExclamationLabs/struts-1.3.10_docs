[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedPropertySupport.html.md)


    1   /*
    2    * $Id: NestedPropertySupport.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.nested;
    22  
    23  
    24  /**
    25   * This interface is for managing classes of the nested extension, so they can
    26   * know to set the tag's <i>property</i> property.
    27   *
    28   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    29   *          $
    30   * @since Struts 1.1
    31   */
    32  public interface NestedPropertySupport extends NestedTagSupport {
    33      /**
    34       * The getters and setters required to set a tags <i>property</i>
    35       * property.
    36       *
    37       * @return String value of the tags' property property
    38       */
    39      public String getProperty();
    40  
    41      /**
    42       * The setter for the poroperty property
    43       *
    44       * @param newProperty new String value to set the property property to
    45       */
    46      public void setProperty(String newProperty);
    47  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)