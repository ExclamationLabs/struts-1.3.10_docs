[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/examples/CustomFormBean.html.md)


    1   /*
    2    * $Id: CustomFormBean.java 471754 2006-11-06 14:55:09Z husted $
    3    *
    4    * Copyright 1999-2004 The Apache Software Foundation.
    5    *
    6    * Licensed under the Apache License, Version 2.0 (the "License");
    7    * you may not use this file except in compliance with the License.
    8    * You may obtain a copy of the License at
    9    *
    10   *      http://www.apache.org/licenses/LICENSE-2.0
    11   *
    12   * Unless required by applicable law or agreed to in writing, software
    13   * distributed under the License is distributed on an "AS IS" BASIS,
    14   * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    15   * See the License for the specific language governing permissions and
    16   * limitations under the License.
    17   */
    18  
    19  package org.apache.struts.webapp.examples;
    20  
    21  import org.apache.struts.config.FormBeanConfig;
    22  
    23  /**
    24   * Custom FormBeanConfig to demonstrate usage.
    25   *
    26   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    27   */
    28  
    29  public final class CustomFormBean extends FormBeanConfig {
    30  
    31  
    32      // --------------------------------------------------- Instance Variables
    33  
    34  
    35      /**
    36       * An example String property.
    37       */
    38      private String example = "";
    39  
    40  
    41      // ----------------------------------------------------------- Properties
    42  
    43  
    44      /**
    45       * Return the example String.
    46       */
    47      public String getExample() {
    48  
    49          return (this.example);
    50  
    51      }
    52  
    53  
    54      /**
    55       * Set the example String.
    56       *
    57       * @param example The new example String.
    58       */
    59      public void setExample(String example) {
    60  
    61          this.example = example;
    62  
    63      }
    64  
    65  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)