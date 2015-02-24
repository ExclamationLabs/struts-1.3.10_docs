[View Javadoc](../../../../../../../apidocs/org/apache/struts/taglib/nested.html.md/NestedFormTag.html)


    1   /*
    2    * $Id: NestedFormTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.nested.html.md;
    22  
    23  import org.apache.struts.taglib.html.md.FormTag;
    24  import org.apache.struts.taglib.nested.NestedNameSupport;
    25  import org.apache.struts.taglib.nested.NestedPropertyHelper;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  
    30  /**
    31   * NestedFormTag.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   * @since Struts 1.1
    36   */
    37  public class NestedFormTag extends FormTag implements NestedNameSupport {
    38      //TODO: name property was removed from FormTag but appears to be required
    39      //      for the nested version to work. See if it can be removed
    40      //      from here altogether.
    41  
    42      /**
    43       * The name
    44       */
    45      protected String name = null;
    46  
    47      // original nesting environment
    48      private String originalNesting = null;
    49      private String originalNestingName = null;
    50  
    51      /**
    52       * Return the name.
    53       */
    54      public String getName() {
    55          return (this.name);
    56      }
    57  
    58      /**
    59       * Set the name.
    60       *
    61       * @param name The new name
    62       */
    63      public void setName(String name) {
    64          this.name = name;
    65      }
    66  
    67      /**
    68       * Get the string value of the "property" property.
    69       *
    70       * @return the property property
    71       */
    72      public String getProperty() {
    73          return "";
    74      }
    75  
    76      /**
    77       * Setter for the "property" property
    78       *
    79       * @param newProperty new value for the property
    80       */
    81      public void setProperty(String newProperty) {
    82      }
    83  
    84      /**
    85       * Overriding to allow the chance to set the details of the system, so
    86       * that dynamic includes can be possible
    87       *
    88       * @return int JSP continuation directive.
    89       */
    90      public int doStartTag() throws JspException {
    91          // store original result
    92          int temp = super.doStartTag();
    93  
    94          HttpServletRequest request =
    95              (HttpServletRequest) pageContext.getRequest();
    96  
    97          // original nesting details
    98          originalNesting = NestedPropertyHelper.getCurrentProperty(request);
    99          originalNestingName =
    100             NestedPropertyHelper.getCurrentName(request, this);
    101 
    102         // some new details
    103         NestedPropertyHelper.setProperty(request, null);
    104         NestedPropertyHelper.setName(request, super.getBeanName());
    105 
    106         // continue
    107         return temp;
    108     }
    109 
    110     /**
    111      * This is only overriden to clean up the include reference
    112      *
    113      * @return int JSP continuation directive.
    114      */
    115     public int doEndTag() throws JspException {
    116         // super result
    117         int temp = super.doEndTag();
    118 
    119         // all done. clean up
    120         HttpServletRequest request =
    121             (HttpServletRequest) pageContext.getRequest();
    122 
    123         // reset the original nesting values
    124         if (originalNesting == null) {
    125             NestedPropertyHelper.deleteReference(request);
    126         } else {
    127             NestedPropertyHelper.setProperty(request, originalNesting);
    128             NestedPropertyHelper.setName(request, originalNestingName);
    129         }
    130 
    131         // return the super result
    132         return temp;
    133     }
    134 
    135     /**
    136      * Release the tag's resources and reset the values.
    137      */
    138     public void release() {
    139         // let the super release
    140         super.release();
    141 
    142         // reset the original value place holders
    143         originalNesting = null;
    144         originalNestingName = null;
    145     }
    146 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
