[View Javadoc](../../../../../../../apidocs/org/apache/struts/taglib/nested/logic/NestedIterateTag.html.md)


    1   /*
    2    * $Id: NestedIterateTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.nested.logic;
    22  
    23  import org.apache.struts.taglib.logic.IterateTag;
    24  import org.apache.struts.taglib.nested.NestedNameSupport;
    25  import org.apache.struts.taglib.nested.NestedPropertyHelper;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  
    30  import java.util.Map;
    31  
    32  /**
    33   * NestedIterateTag. Slightly more complex that the other extensions. This one
    34   * has to yield a proper index property. Very taxing.
    35   *
    36   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    37   *          $
    38   * @since Struts 1.1
    39   */
    40  public class NestedIterateTag extends IterateTag implements NestedNameSupport {
    41      // The current nesting
    42      private String nesting = null;
    43  
    44      // original tag properties
    45      private String originalName = null;
    46      private String originalProperty = null;
    47  
    48      // original nesting environment
    49      private String originalNesting = null;
    50      private String originalNestingName = null;
    51  
    52      /**
    53       * Overriding method of the heart of the matter. Gets the relative
    54       * property and leaves the rest up to the original tag implementation.
    55       * Sweet.
    56       *
    57       * @return int JSP continuation directive. This is in the hands of the
    58       *         super class.
    59       */
    60      public int doStartTag() throws JspException {
    61          // original values
    62          originalName = getName();
    63          originalProperty = getProperty();
    64  
    65          // set the ID to make the super tag happy
    66          if ((id == null) || (id.trim().length() == 0)) {
    67              id = property;
    68          }
    69  
    70          // the request object
    71          HttpServletRequest request =
    72              (HttpServletRequest) pageContext.getRequest();
    73  
    74          // original nesting details
    75          originalNesting = NestedPropertyHelper.getCurrentProperty(request);
    76          originalNestingName =
    77              NestedPropertyHelper.getCurrentName(request, this);
    78  
    79          // set the bean if it's been provided
    80          // (the bean that's been provided! get it!?... nevermind)
    81          if (getName() == null) {
    82              // the qualified nesting value
    83              nesting =
    84                  NestedPropertyHelper.getAdjustedProperty(request, getProperty());
    85          } else {
    86              // it's just the property
    87              nesting = getProperty();
    88          }
    89  
    90          // set the properties
    91          NestedPropertyHelper.setNestedProperties(request, this);
    92  
    93          // get the original result
    94          int temp = super.doStartTag();
    95  
    96          // set the new reference (including the index etc)
    97          NestedPropertyHelper.setName(request, getName());
    98          NestedPropertyHelper.setProperty(request, deriveNestedProperty());
    99  
    100         // return the result
    101         return temp;
    102     }
    103 
    104     /**
    105      * The only added property to the class. For use in proper nesting.
    106      *
    107      * @return String value of the property and the current index or mapping.
    108      */
    109     private String deriveNestedProperty() {
    110         Object idObj = pageContext.getAttribute(id);
    111 
    112         if (idObj instanceof Map.Entry) {
    113             return nesting + "(" + ((Map.Entry) idObj).getKey() + ")";
    114         } else {
    115             return nesting + "[" + this.getIndex() + "]";
    116         }
    117     }
    118 
    119     /**
    120      * This is only overriden as the include reference will need it's index
    121      * updated.
    122      *
    123      * @return int JSP continuation directive.
    124      */
    125     public int doAfterBody() throws JspException {
    126         // store original result
    127         int temp = super.doAfterBody();
    128         HttpServletRequest request =
    129             (HttpServletRequest) pageContext.getRequest();
    130 
    131         if (temp != SKIP_BODY) {
    132             // set the new reference
    133             NestedPropertyHelper.setProperty(request, deriveNestedProperty());
    134         }
    135 
    136         // return super result
    137         return temp;
    138     }
    139 
    140     /**
    141      * Complete the processing of the tag. The nested tags here will restore
    142      * all the original value for the tag itself and the nesting context.
    143      *
    144      * @return int to describe the next step for the JSP processor
    145      * @throws JspException for the bad things JSP's do
    146      */
    147     public int doEndTag() throws JspException {
    148         // the super's thing
    149         int i = super.doEndTag();
    150 
    151         // request
    152         HttpServletRequest request =
    153             (HttpServletRequest) pageContext.getRequest();
    154 
    155         // reset the original tag values
    156         super.setName(originalName);
    157         super.setProperty(originalProperty);
    158 
    159         // reset the original nesting values
    160         if (originalNesting == null) {
    161             NestedPropertyHelper.deleteReference(request);
    162         } else {
    163             NestedPropertyHelper.setProperty(request, originalNesting);
    164             NestedPropertyHelper.setName(request, originalNestingName);
    165         }
    166 
    167         // job done
    168         return i;
    169     }
    170 
    171     /**
    172      * Release the tag's resources and reset the values.
    173      */
    174     public void release() {
    175         // let the super release
    176         super.release();
    177 
    178         // reset the original value place holders
    179         originalName = null;
    180         originalProperty = null;
    181         originalNesting = null;
    182         originalNestingName = null;
    183     }
    184 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
