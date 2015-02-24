[View Javadoc](../../../../../../../apidocs/org/apache/struts/taglib/nested.html.md/NestedLinkTag.html)


    1   /*
    2    * $Id: NestedLinkTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.LinkTag;
    24  import org.apache.struts.taglib.nested.NestedNameSupport;
    25  import org.apache.struts.taglib.nested.NestedPropertyHelper;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  
    30  /**
    31   * NestedLinkTag.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   * @since Struts 1.1
    36   */
    37  public class NestedLinkTag extends LinkTag implements NestedNameSupport {
    38      /* hold original property */
    39      private String origName = null;
    40      private String origProperty = null;
    41      private String origParamProperty = null;
    42  
    43      /**
    44       * Overriding method of the heart of the matter. Gets the relative
    45       * property and leaves the rest up to the original tag implementation.
    46       * Sweet.
    47       *
    48       * @return int JSP continuation directive. This is in the hands of the
    49       *         super class.
    50       */
    51      public int doStartTag() throws JspException {
    52          origName = super.getName();
    53          origProperty = super.getProperty();
    54          origParamProperty = super.getParamProperty();
    55  
    56          /* decide the incoming options. Always two there are */
    57          boolean doProperty =
    58              ((origProperty != null) && (origProperty.length() > 0));
    59          boolean doParam =
    60              ((origParamProperty != null) && (origParamProperty.length() > 0));
    61  
    62          // request
    63          HttpServletRequest request =
    64              (HttpServletRequest) pageContext.getRequest();
    65  
    66          boolean hasName =
    67              ((getName() != null) && (getName().trim().length() > 0));
    68          String currentName;
    69  
    70          if (hasName) {
    71              currentName = getName();
    72          } else {
    73              currentName = NestedPropertyHelper.getCurrentName(request, this);
    74          }
    75  
    76          // set the bean name
    77          super.setName(currentName);
    78  
    79          // set property details
    80          if (doProperty && !hasName) {
    81              super.setProperty(NestedPropertyHelper.getAdjustedProperty(
    82                      request, origProperty));
    83          }
    84  
    85          // do the param property details
    86          if (doParam) {
    87              super.setName(null);
    88              super.setParamName(currentName);
    89              super.setParamProperty(NestedPropertyHelper.getAdjustedProperty(
    90                      request, origParamProperty));
    91          }
    92  
    93          /* do the tag */
    94          return super.doStartTag();
    95      }
    96  
    97      /**
    98       * Complete the processing of the tag. The nested tags here will restore
    99       * all the original value for the tag itself and the nesting context.
    100      *
    101      * @return int to describe the next step for the JSP processor
    102      * @throws JspException for the bad things JSP's do
    103      */
    104     public int doEndTag() throws JspException {
    105         // do the super's ending part
    106         int i = super.doEndTag();
    107 
    108         // reset the properties
    109         setName(origName);
    110         setProperty(origProperty);
    111         setParamProperty(origParamProperty);
    112 
    113         // continue
    114         return i;
    115     }
    116 
    117     /**
    118      * Release the tag's resources and reset the values.
    119      */
    120     public void release() {
    121         super.release();
    122 
    123         // reset the originals
    124         origName = null;
    125         origProperty = null;
    126         origParamProperty = null;
    127     }
    128 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
