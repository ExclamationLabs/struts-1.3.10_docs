[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/NotEmptyTag.html.md)


    1   /*
    2    * $Id: NotEmptyTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.logic;
    22  
    23  import javax.servlet.jsp.JspException;
    24  
    25  /**
    26   * Evalute the nested body content of this tag if the specified value is not
    27   * empty for this request.
    28   *
    29   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    30   *          $
    31   * @since Struts 1.1
    32   */
    33  public class NotEmptyTag extends EmptyTag {
    34      // ------------------------------------------------------ Protected Methods
    35  
    36      /**
    37       * Evaluate the condition that is being tested by this particular tag, and
    38       * return <code>true</code> if the nested body content of this tag should
    39       * be evaluated, or <code>false</code> if it should be skipped. This
    40       * method must be implemented by concrete subclasses.
    41       *
    42       * @throws JspException if a JSP exception occurs
    43       */
    44      protected boolean condition()
    45          throws JspException {
    46          return (condition(false));
    47      }
    48  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
