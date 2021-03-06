[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/taglib/MessageTag.html.md)


    1   /*
    2    * $Id: MessageTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.faces.taglib;
    23  
    24  
    25  import javax.faces.component.UIComponent;
    26  
    27  
    28  /**
    29   * <p>Render a localized message, with optional substitution parameters, for
    30   * the <em>Struts-Faces Integration Library</em>.</p>
    31   *
    32   *
    33   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    34   */
    35  
    36  public class MessageTag extends AbstractFacesTag {
    37  
    38  
    39      // ---------------------------------------------------------- Tag Attributes
    40  
    41  
    42      /**
    43       * <p>Flag indicating that rendered content should be filtered for
    44       * characters that are sensitive in HTML.</p>
    45       */
    46      private String filter = null;
    47  
    48      public void setFilter(String filter) {
    49          this.filter = filter;
    50      }
    51  
    52  
    53      /**
    54       * <p>Message key used to retrieve the requested message
    55       */
    56      private String key = null;
    57  
    58      public void setKey(String key) {
    59          this.key = key;
    60      }
    61  
    62  
    63      // ------------------------------------------------------------- Tag Methods
    64  
    65  
    66      /**
    67       * <p>Release any allocated resources.
    68       */
    69      public void release() {
    70  
    71          super.release();
    72          filter = null;
    73          key = null;
    74  
    75      }
    76  
    77  
    78      // ---------------------------------------------------------- Public Methods
    79  
    80  
    81      /**
    82       * <p>Return the type of component to be created for this tag.</p>
    83       */
    84      public String getComponentType() {
    85  
    86          return ("org.apache.struts.faces.Message");
    87  
    88      }
    89  
    90  
    91      /**
    92       * <p>Return the <code>rendererType</code> to be used for rendering
    93       * our component.</p>
    94       */
    95      public String getRendererType() {
    96  
    97          return ("org.apache.struts.faces.Message");
    98  
    99      }
    100 
    101 
    102     // ------------------------------------------------------- Protected Methods
    103 
    104 
    105     /**
    106      * <p>Override attributes set on this tag instance.</p>
    107      *
    108      * @param component Component whose attributes should be overridden
    109      */
    110     protected void setProperties(UIComponent component) {
    111 
    112         super.setProperties(component);
    113         setBooleanAttribute(component, "filter", filter);
    114         setStringAttribute(component, "key", key);
    115 
    116     }
    117 
    118 
    119 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
