[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/ResetTag.html)


    1   /*
    2    * $Id: ResetTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import javax.servlet.jsp.JspException;
    24  
    25  /**
    26   * Tag for input fields of type "reset".
    27   *
    28   * @version $Rev: 471754 $ $Date: 2004-10-17 02:40:12 -0400 (Sun, 17 Oct 2004)
    29   *          $
    30   */
    31  public class ResetTag extends SubmitTag {
    32      /**
    33       * Render the opening element.
    34       *
    35       * @return The opening part of the element.
    36       */
    37      protected String getElementOpen() {
    38          return "<input type=\"reset\"";
    39      }
    40  
    41      /**
    42       * Prepare the name element
    43       *
    44       * @return The element name.
    45       */
    46      protected String prepareName()
    47          throws JspException {
    48          return property;
    49      }
    50  
    51      /**
    52       * Return the default value.
    53       *
    54       * @return The default value if none supplied.
    55       */
    56      protected String getDefaultValue() {
    57          return "Reset";
    58      }
    59  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)