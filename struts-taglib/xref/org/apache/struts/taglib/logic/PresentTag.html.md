[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/PresentTag.html.md)


    1   /*
    2    * $Id: PresentTag.java 471754 2006-11-06 14:55:09Z husted $
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
    29  import java.security.Principal;
    30  
    31  import java.util.StringTokenizer;
    32  
    33  /**
    34   * Evalute the nested body content of this tag if the specified value is
    35   * present for this request.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public class PresentTag extends ConditionalTagBase {
    41      public static final String ROLE_DELIMITER = ",";
    42  
    43      // ------------------------------------------------------ Protected Methods
    44  
    45      /**
    46       * Evaluate the condition that is being tested by this particular tag, and
    47       * return <code>true</code> if the nested body content of this tag should
    48       * be evaluated, or <code>false</code> if it should be skipped. This
    49       * method must be implemented by concrete subclasses.
    50       *
    51       * @throws JspException if a JSP exception occurs
    52       */
    53      protected boolean condition()
    54          throws JspException {
    55          return (condition(true));
    56      }
    57  
    58      /**
    59       * Evaluate the condition that is being tested by this particular tag, and
    60       * return <code>true</code> if the nested body content of this tag should
    61       * be evaluated, or <code>false</code> if it should be skipped. This
    62       * method must be implemented by concrete subclasses.
    63       *
    64       * @param desired Desired outcome for a true result
    65       * @throws JspException if a JSP exception occurs
    66       */
    67      protected boolean condition(boolean desired)
    68          throws JspException {
    69          // Evaluate the presence of the specified value
    70          boolean present = false;
    71          HttpServletRequest request =
    72              (HttpServletRequest) pageContext.getRequest();
    73  
    74          if (cookie != null) {
    75              present = this.isCookiePresent(request);
    76          } else if (header != null) {
    77              String value = request.getHeader(header);
    78  
    79              present = (value != null);
    80          } else if (name != null) {
    81              present = this.isBeanPresent();
    82          } else if (parameter != null) {
    83              String value = request.getParameter(parameter);
    84  
    85              present = (value != null);
    86          } else if (role != null) {
    87              StringTokenizer st =
    88                  new StringTokenizer(role, ROLE_DELIMITER, false);
    89  
    90              while (!present && st.hasMoreTokens()) {
    91                  present = request.isUserInRole(st.nextToken());
    92              }
    93          } else if (user != null) {
    94              Principal principal = request.getUserPrincipal();
    95  
    96              present = (principal != null) && user.equals(principal.getName());
    97          } else {
    98              JspException e =
    99                  new JspException(messages.getMessage("logic.selector"));
    100 
    101             TagUtils.getInstance().saveException(pageContext, e);
    102             throw e;
    103         }
    104 
    105         return (present == desired);
    106     }
    107 
    108     /**
    109      * Returns true if the bean given in the <code>name</code> attribute is
    110      * found.
    111      *
    112      * @since Struts 1.2
    113      */
    114     protected boolean isBeanPresent() {
    115         Object value = null;
    116 
    117         try {
    118             if (this.property != null) {
    119                 value =
    120                     TagUtils.getInstance().lookup(pageContext, name,
    121                         this.property, scope);
    122             } else {
    123                 value = TagUtils.getInstance().lookup(pageContext, name, scope);
    124             }
    125         } catch (JspException e) {
    126             value = null;
    127         }
    128 
    129         return (value != null);
    130     }
    131 
    132     /**
    133      * Returns true if the cookie is present in the request.
    134      *
    135      * @since Struts 1.2
    136      */
    137     protected boolean isCookiePresent(HttpServletRequest request) {
    138         Cookie[] cookies = request.getCookies();
    139 
    140         if (cookies == null) {
    141             return false;
    142         }
    143 
    144         for (int i = 0; i < cookies.length; i++) {
    145             if (this.cookie.equals(cookies[i].getName())) {
    146                 return true;
    147             }
    148         }
    149 
    150         return false;
    151     }
    152 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
