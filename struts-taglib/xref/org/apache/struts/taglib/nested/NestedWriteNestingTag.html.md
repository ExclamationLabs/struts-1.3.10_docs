[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedWriteNestingTag.html.md)


    1   /*
    2    * $Id: NestedWriteNestingTag.java 471754 2006-11-06 14:55:09Z husted $
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
    30   * NestedWriteNestingTag.
    31   *
    32   * Created so developers could have a more elegant way of getting to the
    33   * underlying nested property their tag properties are referencing.
    34   *
    35   * @version $Rev: 471754 $
    36   * @since Struts 1.1
    37   */
    38  public class NestedWriteNestingTag extends BodyTagSupport {
    39      /* the usual private member variables */
    40      private boolean filter = false;
    41      private String property = null;
    42      private String id = null;
    43      private String originalProperty = null;
    44  
    45      /**
    46       * Getter method for the <i>property</i> property
    47       *
    48       * @return String value of the property property
    49       */
    50      public String getProperty() {
    51          return this.property;
    52      }
    53  
    54      /**
    55       * Setter method for the <i>property</i> property
    56       *
    57       * @param newProperty new value for the property property
    58       */
    59      public void setProperty(String newProperty) {
    60          this.property = newProperty;
    61      }
    62  
    63      /**
    64       * Getter method for the <i>id</i> property
    65       *
    66       * @return String value for the id property
    67       */
    68      public String getId() {
    69          return id;
    70      }
    71  
    72      /**
    73       * Setter method for the <i>id</i> property
    74       *
    75       * @param id new value for the id property
    76       */
    77      public void setId(String id) {
    78          this.id = id;
    79      }
    80  
    81      /**
    82       * Getter method for the <i>filter</i> property
    83       *
    84       * @return String value of the filter property
    85       */
    86      public boolean getFilter() {
    87          return this.filter;
    88      }
    89  
    90      /**
    91       * Setter method for the <i>filter</i> property
    92       *
    93       * @param newFilter new value for the filter property
    94       */
    95      public void setFilter(boolean newFilter) {
    96          this.filter = newFilter;
    97      }
    98  
    99      /**
    100      * Overriding method of the heart of the tag. Gets the relative property
    101      * and tells the JSP engine to evaluate its body content.
    102      *
    103      * @return int JSP continuation directive.
    104      */
    105     public int doStartTag() throws JspException {
    106         // set the original property
    107         originalProperty = property;
    108 
    109         HttpServletRequest request =
    110             (HttpServletRequest) pageContext.getRequest();
    111         String nesting =
    112             NestedPropertyHelper.getAdjustedProperty(request, property);
    113 
    114         if (id != null) {
    115             // use it as a scripting variable instead
    116             pageContext.setAttribute(id, nesting);
    117         } else {
    118             /* write output, filtering if required */
    119             if (this.filter) {
    120                 TagUtils.getInstance().write(pageContext,
    121                     TagUtils.getInstance().filter(nesting));
    122             } else {
    123                 TagUtils.getInstance().write(pageContext, nesting);
    124             }
    125         }
    126 
    127         /* continue with page processing */
    128         return (SKIP_BODY);
    129     }
    130 
    131     public int doEndTag() throws JspException {
    132         // do the super thing
    133         int i = super.doEndTag();
    134 
    135         // reset the property
    136         property = originalProperty;
    137 
    138         // complete
    139         return i;
    140     }
    141 
    142     /**
    143      * JSP method to release all resources held by the tag.
    144      */
    145     public void release() {
    146         super.release();
    147         this.filter = false;
    148         this.property = null;
    149         this.originalProperty = null;
    150     }
    151 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
