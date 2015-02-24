[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/MatchTag.html.md)


    1   /*
    2    * $Id: MatchTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  
    25  import javax.servlet.http.Cookie;
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.jsp.JspException;
    28  
    29  /**
    30   * Evalute the nested body content of this tag if the specified value is a
    31   * substring of the specified variable.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   */
    36  public class MatchTag extends ConditionalTagBase {
    37      // ------------------------------------------------------------- Properties
    38  
    39      /**
    40       * The location where the match must exist (<code>start</code> or
    41       * <code>end</code>), or <code>null</code> for anywhere.
    42       */
    43      protected String location = null;
    44  
    45      /**
    46       * The value to which the variable specified by other attributes of this
    47       * tag will be matched.
    48       */
    49      protected String value = null;
    50  
    51      public String getLocation() {
    52          return (this.location);
    53      }
    54  
    55      public void setLocation(String location) {
    56          this.location = location;
    57      }
    58  
    59      public String getValue() {
    60          return (this.value);
    61      }
    62  
    63      public void setValue(String value) {
    64          this.value = value;
    65      }
    66  
    67      // --------------------------------------------------------- Public Methods
    68  
    69      /**
    70       * Release all allocated resources.
    71       */
    72      public void release() {
    73          super.release();
    74          location = null;
    75          value = null;
    76      }
    77  
    78      // ------------------------------------------------------ Protected Methods
    79  
    80      /**
    81       * Evaluate the condition that is being tested by this particular tag, and
    82       * return <code>true</code> if the nested body content of this tag should
    83       * be evaluated, or <code>false</code> if it should be skipped. This
    84       * method must be implemented by concrete subclasses.
    85       *
    86       * @throws JspException if a JSP exception occurs
    87       */
    88      protected boolean condition()
    89          throws JspException {
    90          return (condition(true));
    91      }
    92  
    93      /**
    94       * Evaluate the condition that is being tested by this particular tag, and
    95       * return <code>true</code> if the nested body content of this tag should
    96       * be evaluated, or <code>false</code> if it should be skipped. This
    97       * method must be implemented by concrete subclasses.
    98       *
    99       * @param desired Desired value for a true result
    100      * @throws JspException if a JSP exception occurs
    101      */
    102     protected boolean condition(boolean desired)
    103         throws JspException {
    104         // Acquire the specified variable
    105         String variable = null;
    106 
    107         if (cookie != null) {
    108             Cookie[] cookies =
    109                 ((HttpServletRequest) pageContext.getRequest()).getCookies();
    110 
    111             if (cookies == null) {
    112                 cookies = new Cookie[0];
    113             }
    114 
    115             for (int i = 0; i < cookies.length; i++) {
    116                 if (cookie.equals(cookies[i].getName())) {
    117                     variable = cookies[i].getValue();
    118 
    119                     break;
    120                 }
    121             }
    122         } else if (header != null) {
    123             variable =
    124                 ((HttpServletRequest) pageContext.getRequest()).getHeader(header);
    125         } else if (name != null) {
    126             Object value =
    127                 TagUtils.getInstance().lookup(pageContext, name, property, scope);
    128 
    129             if (value != null) {
    130                 variable = value.toString();
    131             }
    132         } else if (parameter != null) {
    133             variable = pageContext.getRequest().getParameter(parameter);
    134         } else {
    135             JspException e =
    136                 new JspException(messages.getMessage("logic.selector"));
    137 
    138             TagUtils.getInstance().saveException(pageContext, e);
    139             throw e;
    140         }
    141 
    142         if (variable == null) {
    143             JspException e =
    144                 new JspException(messages.getMessage("logic.variable", value));
    145 
    146             TagUtils.getInstance().saveException(pageContext, e);
    147             throw e;
    148         }
    149 
    150         // Perform the comparison requested by the location attribute
    151         boolean matched = false;
    152 
    153         if (location == null) {
    154             matched = (variable.indexOf(value) >= 0);
    155         } else if (location.equals("start")) {
    156             matched = variable.startsWith(value);
    157         } else if (location.equals("end")) {
    158             matched = variable.endsWith(value);
    159         } else {
    160             JspException e =
    161                 new JspException(messages.getMessage("logic.location", location));
    162 
    163             TagUtils.getInstance().saveException(pageContext, e);
    164             throw e;
    165         }
    166 
    167         // Return the final result
    168         return (matched == desired);
    169     }
    170 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
