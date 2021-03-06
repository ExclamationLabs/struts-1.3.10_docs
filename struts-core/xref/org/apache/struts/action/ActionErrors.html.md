[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionErrors.html.md)


    1   /*
    2    * $Id: ActionErrors.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.io.Serializable;
    24  
    25  /**
    26   * <p>A class that encapsulates the error messages being reported by the
    27   * <code>validate()</code> method of an <code>ActionForm</code>. Validation
    28   * errors are either global to the entire <code>ActionForm</code> bean they
    29   * are associated with, or they are specific to a particular bean property
    30   * (and, therefore, a particular input field on the corresponding form).</p>
    31   *
    32   * <p>Each individual error is described by an <code>ActionMessage</code>
    33   * object, which contains a message key (to be looked up in an appropriate
    34   * message resources database), and up to four placeholder arguments used for
    35   * parametric substitution in the resulting message.</p>
    36   *
    37   * <p><strong>IMPLEMENTATION NOTE</strong> - It is assumed that these objects
    38   * are created and manipulated only within the context of a single thread.
    39   * Therefore, no synchronization is required for access to internal
    40   * collections.</p>
    41   *
    42   * @version $Rev: 471754 $ $Date: 2005-08-06 18:03:30 -0400 (Sat, 06 Aug 2005)
    43   *          $
    44   */
    45  public class ActionErrors extends ActionMessages implements Serializable {
    46      // --------------------------------------------------------- Public Methods
    47  
    48      /**
    49       * <p>Create an empty <code>ActionErrors</code> object.</p>
    50       */
    51      public ActionErrors() {
    52          super();
    53      }
    54  
    55      /**
    56       * <p>Create an <code>ActionErrors</code> object initialized with the
    57       * given messages.</p>
    58       *
    59       * @param messages The messages to be initially added to this object. This
    60       *                 parameter can be <code>null</code>.
    61       * @since Struts 1.1
    62       */
    63      public ActionErrors(ActionErrors messages) {
    64          super(messages);
    65      }
    66  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
