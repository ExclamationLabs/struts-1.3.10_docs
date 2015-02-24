[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedRootTag.html.md)


    1   /*
    2    * $Id: NestedRootTag.java 471754 2006-11-06 14:55:09Z husted $
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
    30   * NestedRootTag.
    31   *
    32   * The only other addition in this nested suite of tags. This tag allows for a
    33   * nested structure to start without relying on the bean and workings of the
    34   * FormTag. Useful for view pages that don't update when returning to the
    35   * server, or use hyperlinks rather than form submits.
    36   *
    37   * The Bean that it uses can come out of a jsp:useBean tag or define another
    38   * bean that's already in scope. As long as the other Struts tags can find the
    39   * bean by name, it'll work.
    40   *
    41   * It's simply recognised by the helper class and it's property is added to
    42   * the nesting list.
    43   *
    44   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    45   *          $
    46   * @since Struts 1.1
    47   */
    48  public class NestedRootTag extends BodyTagSupport implements NestedNameSupport {
    49      /* usual member variables */
    50      private String name = null;
    51      private String originalName = "";
    52      private String originalNesting = "";
    53      private String originalNestingName = "";
    54  
    55      /**
    56       * Getter method for the <i>property</i> property
    57       *
    58       * @return String value of the property property
    59       */
    60      public String getProperty() {
    61          return "";
    62      }
    63  
    64      /**
    65       * Setter method for the <i>property</i> property
    66       *
    67       * @param property new value for the property property
    68       */
    69      public void setProperty(String property) {
    70      }
    71  
    72      /**
    73       * Getter method for the <i>name</i> property
    74       *
    75       * @return String value of the name property
    76       */
    77      public String getName() {
    78          return this.name;
    79      }
    80  
    81      /**
    82       * Setter method for the <i>name</i> property
    83       *
    84       * @param name new value for the name property
    85       */
    86      public void setName(String name) {
    87          this.name = name;
    88      }
    89  
    90      /**
    91       * Overriding method of the heart of the tag. Gets the relative property
    92       * and tells the JSP engine to evaluate its body content.
    93       *
    94       * @return int JSP continuation directive.
    95       */
    96      public int doStartTag() throws JspException {
    97          /* set the nested reference for possible inclusions etc */
    98          HttpServletRequest request =
    99              (HttpServletRequest) pageContext.getRequest();
    100 
    101         // get al the originals
    102         originalName = name;
    103         originalNesting = NestedPropertyHelper.getCurrentProperty(request);
    104         originalNestingName =
    105             NestedPropertyHelper.getCurrentName(request, this);
    106 
    107         // set what we have to
    108         if (name != null) {
    109             NestedPropertyHelper.setProperty(request, "");
    110             NestedPropertyHelper.setName(request, this.name);
    111         }
    112 
    113         // do the JSP thing
    114         return (EVAL_BODY_TAG);
    115     }
    116 
    117     /**
    118      * Render the resulting content evaluation.
    119      *
    120      * @return int JSP continuation directive.
    121      */
    122     public int doAfterBody() throws JspException {
    123         /* Render the output */
    124         if (bodyContent != null) {
    125             TagUtils.getInstance().writePrevious(pageContext,
    126                 bodyContent.getString());
    127             bodyContent.clearBody();
    128         }
    129 
    130         return (SKIP_BODY);
    131     }
    132 
    133     /**
    134      * Evaluate the rest of the page
    135      *
    136      * @return int JSP continuation directive.
    137      */
    138     public int doEndTag() throws JspException {
    139         /* reset the reference */
    140         HttpServletRequest request =
    141             (HttpServletRequest) pageContext.getRequest();
    142 
    143         if (originalNesting == null) {
    144             NestedPropertyHelper.deleteReference(request);
    145         } else {
    146             NestedPropertyHelper.setName(request, originalNestingName);
    147             NestedPropertyHelper.setProperty(request, originalNesting);
    148         }
    149 
    150         this.name = originalName;
    151 
    152         return (EVAL_PAGE);
    153     }
    154 
    155     /**
    156      * JSP method to release all resources held by the tag.
    157      */
    158     public void release() {
    159         super.release();
    160         this.name = null;
    161         this.originalName = null;
    162         this.originalNesting = null;
    163         this.originalNestingName = null;
    164     }
    165 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
