[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedPropertyTag.html.md)


    1   /*
    2    * $Id: NestedPropertyTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  
    25  import javax.servlet.http.HttpServletRequest;
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.tagext.BodyTagSupport;
    28  
    29  /**
    30   * NestedPropertyTag.
    31   *
    32   * The one of only two additions in this nested suite of tags. This is so that
    33   * you can specify extra levels of nesting in one elegant tag rather than
    34   * having to propagate and manage an extra dot notated property in nested
    35   * child tags.
    36   *
    37   * It's simply recognised by the helper class and it's property is added to
    38   * the nesting list.
    39   *
    40   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    41   *          $
    42   * @since Struts 1.1
    43   */
    44  public class NestedPropertyTag extends BodyTagSupport
    45      implements NestedNameSupport {
    46      /* the usual private member variable */
    47      private String property = null;
    48      private String originalNest = null;
    49      private String originalName = null;
    50      private String originalProperty = null;
    51  
    52      public String getName() {
    53          return null;
    54      }
    55  
    56      public void setName(String newNamed) {
    57      }
    58  
    59      /**
    60       * Getter method for the <i>property</i> property
    61       *
    62       * @return String value of the property property
    63       */
    64      public String getProperty() {
    65          return this.property;
    66      }
    67  
    68      /**
    69       * Setter method for the <i>property</i> property Also, only setting the
    70       * original property value to those values not set by the nested logic.
    71       *
    72       * @param newProperty new value for the property property
    73       */
    74      public void setProperty(String newProperty) {
    75          property = newProperty;
    76      }
    77  
    78      /**
    79       * Overriding method of the heart of the tag. Gets the relative property
    80       * and tells the JSP engine to evaluate its body content.
    81       *
    82       * @return int JSP continuation directive.
    83       */
    84      public int doStartTag() throws JspException {
    85          originalProperty = property;
    86  
    87          HttpServletRequest request =
    88              (HttpServletRequest) pageContext.getRequest();
    89  
    90          originalNest = NestedPropertyHelper.getCurrentProperty(request);
    91          originalName = NestedPropertyHelper.getCurrentName(request, this);
    92  
    93          String nested =
    94              NestedPropertyHelper.getAdjustedProperty(request, originalProperty);
    95  
    96          NestedPropertyHelper.setProperty(request, nested);
    97          NestedPropertyHelper.setName(request, originalName);
    98  
    99          // run the body part
    100         return (EVAL_BODY_TAG);
    101     }
    102 
    103     /**
    104      * Render the resulting content evaluation.
    105      *
    106      * @return int JSP continuation directive.
    107      */
    108     public int doAfterBody() throws JspException {
    109         /* Render the output */
    110         if (bodyContent != null) {
    111             TagUtils.getInstance().writePrevious(pageContext,
    112                 bodyContent.getString());
    113             bodyContent.clearBody();
    114         }
    115 
    116         return (SKIP_BODY);
    117     }
    118 
    119     /**
    120      * Evaluate the rest of the page
    121      *
    122      * @return int JSP continuation directive.
    123      */
    124     public int doEndTag() throws JspException {
    125         /* set the reference back */
    126         HttpServletRequest request =
    127             (HttpServletRequest) pageContext.getRequest();
    128 
    129         if ((originalNest == null) && (originalName == null)) {
    130             NestedPropertyHelper.deleteReference(request);
    131         } else {
    132             NestedPropertyHelper.setName(request, originalName);
    133             NestedPropertyHelper.setProperty(request, originalNest);
    134         }
    135 
    136         property = originalProperty;
    137 
    138         return (EVAL_PAGE);
    139     }
    140 
    141     /**
    142      * JSP method to release all resources held by the tag.
    143      */
    144     public void release() {
    145         super.release();
    146         this.property = null;
    147         this.originalNest = null;
    148         this.originalName = null;
    149         this.originalProperty = null;
    150     }
    151 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
