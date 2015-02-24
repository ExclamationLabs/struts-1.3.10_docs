[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/ConditionalTagBase.html.md)


    1   /*
    2    * $Id: ConditionalTagBase.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.util.MessageResources;
    24  
    25  import javax.servlet.jsp.JspException;
    26  import javax.servlet.jsp.tagext.TagSupport;
    27  
    28  /**
    29   * Abstract base class for the various conditional evaluation tags.
    30   *
    31   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    32   *          $
    33   */
    34  public abstract class ConditionalTagBase extends TagSupport {
    35      /**
    36       * The message resources for this package.
    37       */
    38      protected static MessageResources messages =
    39          MessageResources.getMessageResources(
    40              "org.apache.struts.taglib.logic.LocalStrings");
    41  
    42      // ------------------------------------------------------------- Properties
    43  
    44      /**
    45       * The name of the cookie to be used as a variable.
    46       */
    47      protected String cookie = null;
    48  
    49      /**
    50       * The name of the HTTP request header to be used as a variable.
    51       */
    52      protected String header = null;
    53  
    54      /**
    55       * The name of the JSP bean to be used as a variable (if
    56       * <code>property</code> is not specified), or whose property is to be
    57       * accessed (if <code>property</code> is specified).
    58       */
    59      protected String name = null;
    60  
    61      /**
    62       * The name of the HTTP request parameter to be used as a variable.
    63       */
    64      protected String parameter = null;
    65  
    66      /**
    67       * The name of the bean property to be used as a variable.
    68       */
    69      protected String property = null;
    70  
    71      /**
    72       * The name of the security role to be checked for.
    73       */
    74      protected String role = null;
    75  
    76      /**
    77       * The scope to search for the bean named by the name property, or "any
    78       * scope" if null.
    79       */
    80      protected String scope = null;
    81  
    82      /**
    83       * The user principal name to be checked for.
    84       */
    85      protected String user = null;
    86  
    87      public String getCookie() {
    88          return (this.cookie);
    89      }
    90  
    91      public void setCookie(String cookie) {
    92          this.cookie = cookie;
    93      }
    94  
    95      public String getHeader() {
    96          return (this.header);
    97      }
    98  
    99      public void setHeader(String header) {
    100         this.header = header;
    101     }
    102 
    103     public String getName() {
    104         return (this.name);
    105     }
    106 
    107     public void setName(String name) {
    108         this.name = name;
    109     }
    110 
    111     public String getParameter() {
    112         return (this.parameter);
    113     }
    114 
    115     public void setParameter(String parameter) {
    116         this.parameter = parameter;
    117     }
    118 
    119     public String getProperty() {
    120         return (this.property);
    121     }
    122 
    123     public void setProperty(String property) {
    124         this.property = property;
    125     }
    126 
    127     public String getRole() {
    128         return (this.role);
    129     }
    130 
    131     public void setRole(String role) {
    132         this.role = role;
    133     }
    134 
    135     public String getScope() {
    136         return (this.scope);
    137     }
    138 
    139     public void setScope(String scope) {
    140         this.scope = scope;
    141     }
    142 
    143     public String getUser() {
    144         return (this.user);
    145     }
    146 
    147     public void setUser(String user) {
    148         this.user = user;
    149     }
    150 
    151     // --------------------------------------------------------- Public Methods
    152 
    153     /**
    154      * Perform the test required for this particular tag, and either evaluate
    155      * or skip the body of this tag.
    156      *
    157      * @throws JspException if a JSP exception occurs
    158      */
    159     public int doStartTag() throws JspException {
    160         if (condition()) {
    161             return (EVAL_BODY_INCLUDE);
    162         } else {
    163             return (SKIP_BODY);
    164         }
    165     }
    166 
    167     /**
    168      * Evaluate the remainder of the current page normally.
    169      *
    170      * @throws JspException if a JSP exception occurs
    171      */
    172     public int doEndTag() throws JspException {
    173         return (EVAL_PAGE);
    174     }
    175 
    176     /**
    177      * Release all allocated resources.
    178      */
    179     public void release() {
    180         super.release();
    181         cookie = null;
    182         header = null;
    183         name = null;
    184         parameter = null;
    185         property = null;
    186         role = null;
    187         scope = null;
    188         user = null;
    189     }
    190 
    191     // ------------------------------------------------------ Protected Methods
    192 
    193     /**
    194      * Evaluate the condition that is being tested by this particular tag, and
    195      * return <code>true</code> if the nested body content of this tag should
    196      * be evaluated, or <code>false</code> if it should be skipped. This
    197      * method must be implemented by concrete subclasses.
    198      *
    199      * @throws JspException if a JSP exception occurs
    200      */
    201     protected abstract boolean condition()
    202         throws JspException;
    203 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
