[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELPresentTag.html.md)


    1   /*
    2    * $Id: ELPresentTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.logic;
    22  
    23  import org.apache.struts.taglib.logic.PresentTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Evaluates the nested body content of this tag if the specified value is
    30   * present for this request. <p> This class is a subclass of the class
    31   * <code>org.apache.struts.taglib.logic.PresentTag</code> which provides most
    32   * of the described functionality.  This subclass allows all attribute values
    33   * to be specified as expressions utilizing the JavaServer Pages Standard
    34   * Library expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELPresentTag extends PresentTag {
    39      /**
    40       * Instance variable mapped to "cookie" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String cookieExpr;
    44  
    45      /**
    46       * Instance variable mapped to "header" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String headerExpr;
    50  
    51      /**
    52       * Instance variable mapped to "name" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String nameExpr;
    56  
    57      /**
    58       * Instance variable mapped to "parameter" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String parameterExpr;
    62  
    63      /**
    64       * Instance variable mapped to "property" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String propertyExpr;
    68  
    69      /**
    70       * Instance variable mapped to "role" tag attribute. (Mapping set in
    71       * associated BeanInfo class.)
    72       */
    73      private String roleExpr;
    74  
    75      /**
    76       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    77       * associated BeanInfo class.)
    78       */
    79      private String scopeExpr;
    80  
    81      /**
    82       * Instance variable mapped to "user" tag attribute. (Mapping set in
    83       * associated BeanInfo class.)
    84       */
    85      private String userExpr;
    86  
    87      /**
    88       * Getter method for "cookie" tag attribute. (Mapping set in associated
    89       * BeanInfo class.)
    90       */
    91      public String getCookieExpr() {
    92          return (cookieExpr);
    93      }
    94  
    95      /**
    96       * Getter method for "header" tag attribute. (Mapping set in associated
    97       * BeanInfo class.)
    98       */
    99      public String getHeaderExpr() {
    100         return (headerExpr);
    101     }
    102 
    103     /**
    104      * Getter method for "name" tag attribute. (Mapping set in associated
    105      * BeanInfo class.)
    106      */
    107     public String getNameExpr() {
    108         return (nameExpr);
    109     }
    110 
    111     /**
    112      * Getter method for "parameter" tag attribute. (Mapping set in associated
    113      * BeanInfo class.)
    114      */
    115     public String getParameterExpr() {
    116         return (parameterExpr);
    117     }
    118 
    119     /**
    120      * Getter method for "property" tag attribute. (Mapping set in associated
    121      * BeanInfo class.)
    122      */
    123     public String getPropertyExpr() {
    124         return (propertyExpr);
    125     }
    126 
    127     /**
    128      * Getter method for "role" tag attribute. (Mapping set in associated
    129      * BeanInfo class.)
    130      */
    131     public String getRoleExpr() {
    132         return (roleExpr);
    133     }
    134 
    135     /**
    136      * Getter method for "scope" tag attribute. (Mapping set in associated
    137      * BeanInfo class.)
    138      */
    139     public String getScopeExpr() {
    140         return (scopeExpr);
    141     }
    142 
    143     /**
    144      * Getter method for "user" tag attribute. (Mapping set in associated
    145      * BeanInfo class.)
    146      */
    147     public String getUserExpr() {
    148         return (userExpr);
    149     }
    150 
    151     /**
    152      * Setter method for "cookie" tag attribute. (Mapping set in associated
    153      * BeanInfo class.)
    154      */
    155     public void setCookieExpr(String cookieExpr) {
    156         this.cookieExpr = cookieExpr;
    157     }
    158 
    159     /**
    160      * Setter method for "header" tag attribute. (Mapping set in associated
    161      * BeanInfo class.)
    162      */
    163     public void setHeaderExpr(String headerExpr) {
    164         this.headerExpr = headerExpr;
    165     }
    166 
    167     /**
    168      * Setter method for "name" tag attribute. (Mapping set in associated
    169      * BeanInfo class.)
    170      */
    171     public void setNameExpr(String nameExpr) {
    172         this.nameExpr = nameExpr;
    173     }
    174 
    175     /**
    176      * Setter method for "parameter" tag attribute. (Mapping set in associated
    177      * BeanInfo class.)
    178      */
    179     public void setParameterExpr(String parameterExpr) {
    180         this.parameterExpr = parameterExpr;
    181     }
    182 
    183     /**
    184      * Setter method for "property" tag attribute. (Mapping set in associated
    185      * BeanInfo class.)
    186      */
    187     public void setPropertyExpr(String propertyExpr) {
    188         this.propertyExpr = propertyExpr;
    189     }
    190 
    191     /**
    192      * Setter method for "role" tag attribute. (Mapping set in associated
    193      * BeanInfo class.)
    194      */
    195     public void setRoleExpr(String roleExpr) {
    196         this.roleExpr = roleExpr;
    197     }
    198 
    199     /**
    200      * Setter method for "scope" tag attribute. (Mapping set in associated
    201      * BeanInfo class.)
    202      */
    203     public void setScopeExpr(String scopeExpr) {
    204         this.scopeExpr = scopeExpr;
    205     }
    206 
    207     /**
    208      * Setter method for "user" tag attribute. (Mapping set in associated
    209      * BeanInfo class.)
    210      */
    211     public void setUserExpr(String userExpr) {
    212         this.userExpr = userExpr;
    213     }
    214 
    215     /**
    216      * Resets attribute values for tag reuse.
    217      */
    218     public void release() {
    219         super.release();
    220         setCookieExpr(null);
    221         setHeaderExpr(null);
    222         setNameExpr(null);
    223         setParameterExpr(null);
    224         setPropertyExpr(null);
    225         setRoleExpr(null);
    226         setScopeExpr(null);
    227         setUserExpr(null);
    228     }
    229 
    230     /**
    231      * Process the start tag.
    232      *
    233      * @throws JspException if a JSP exception has occurred
    234      */
    235     public int doStartTag() throws JspException {
    236         evaluateExpressions();
    237 
    238         return (super.doStartTag());
    239     }
    240 
    241     /**
    242      * Processes all attribute values which use the JSTL expression evaluation
    243      * engine to determine their values.
    244      *
    245      * @throws JspException if a JSP exception has occurred
    246      */
    247     private void evaluateExpressions()
    248         throws JspException {
    249         String string = null;
    250 
    251         if ((string =
    252                 EvalHelper.evalString("cookie", getCookieExpr(), this,
    253                     pageContext)) != null) {
    254             setCookie(string);
    255         }
    256 
    257         if ((string =
    258                 EvalHelper.evalString("header", getHeaderExpr(), this,
    259                     pageContext)) != null) {
    260             setHeader(string);
    261         }
    262 
    263         if ((string =
    264                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    265             setName(string);
    266         }
    267 
    268         if ((string =
    269                 EvalHelper.evalString("parameter", getParameterExpr(), this,
    270                     pageContext)) != null) {
    271             setParameter(string);
    272         }
    273 
    274         if ((string =
    275                 EvalHelper.evalString("property", getPropertyExpr(), this,
    276                     pageContext)) != null) {
    277             setProperty(string);
    278         }
    279 
    280         if ((string =
    281                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    282             setRole(string);
    283         }
    284 
    285         if ((string =
    286                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    287             setScope(string);
    288         }
    289 
    290         if ((string =
    291                 EvalHelper.evalString("user", getUserExpr(), this, pageContext)) != null) {
    292             setUser(string);
    293         }
    294     }
    295 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
