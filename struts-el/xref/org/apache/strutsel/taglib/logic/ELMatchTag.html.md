[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELMatchTag.html.md)


    1   /*
    2    * $Id: ELMatchTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.logic.MatchTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Evalute the nested body content of this tag if the specified value is a
    30   * substring of the specified variable. <p> This class is a subclass of the
    31   * class <code>org.apache.struts.taglib.logic.MatchTag</code> which provides
    32   * most of the described functionality.  This subclass allows all attribute
    33   * values to be specified as expressions utilizing the JavaServer Pages
    34   * Standard Library expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELMatchTag extends MatchTag {
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
    52       * Instance variable mapped to "location" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String locationExpr;
    56  
    57      /**
    58       * Instance variable mapped to "name" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String nameExpr;
    62  
    63      /**
    64       * Instance variable mapped to "parameter" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String parameterExpr;
    68  
    69      /**
    70       * Instance variable mapped to "property" tag attribute. (Mapping set in
    71       * associated BeanInfo class.)
    72       */
    73      private String propertyExpr;
    74  
    75      /**
    76       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    77       * associated BeanInfo class.)
    78       */
    79      private String scopeExpr;
    80  
    81      /**
    82       * Instance variable mapped to "value" tag attribute. (Mapping set in
    83       * associated BeanInfo class.)
    84       */
    85      private String valueExpr;
    86  
    87      /**
    88       * String value of expression to be evaluated.
    89       */
    90      private String expr;
    91  
    92      /**
    93       * Evaluated value of expression.
    94       */
    95      private String exprValue;
    96  
    97      /**
    98       * Getter method for "cookie" tag attribute. (Mapping set in associated
    99       * BeanInfo class.)
    100      */
    101     public String getCookieExpr() {
    102         return (cookieExpr);
    103     }
    104 
    105     /**
    106      * Getter method for "header" tag attribute. (Mapping set in associated
    107      * BeanInfo class.)
    108      */
    109     public String getHeaderExpr() {
    110         return (headerExpr);
    111     }
    112 
    113     /**
    114      * Getter method for "location" tag attribute. (Mapping set in associated
    115      * BeanInfo class.)
    116      */
    117     public String getLocationExpr() {
    118         return (locationExpr);
    119     }
    120 
    121     /**
    122      * Getter method for "name" tag attribute. (Mapping set in associated
    123      * BeanInfo class.)
    124      */
    125     public String getNameExpr() {
    126         return (nameExpr);
    127     }
    128 
    129     /**
    130      * Getter method for "parameter" tag attribute. (Mapping set in associated
    131      * BeanInfo class.)
    132      */
    133     public String getParameterExpr() {
    134         return (parameterExpr);
    135     }
    136 
    137     /**
    138      * Getter method for "property" tag attribute. (Mapping set in associated
    139      * BeanInfo class.)
    140      */
    141     public String getPropertyExpr() {
    142         return (propertyExpr);
    143     }
    144 
    145     /**
    146      * Getter method for "scope" tag attribute. (Mapping set in associated
    147      * BeanInfo class.)
    148      */
    149     public String getScopeExpr() {
    150         return (scopeExpr);
    151     }
    152 
    153     /**
    154      * Getter method for "value" tag attribute. (Mapping set in associated
    155      * BeanInfo class.)
    156      */
    157     public String getValueExpr() {
    158         return (valueExpr);
    159     }
    160 
    161     /**
    162      * Setter method for "cookie" tag attribute. (Mapping set in associated
    163      * BeanInfo class.)
    164      */
    165     public void setCookieExpr(String cookieExpr) {
    166         this.cookieExpr = cookieExpr;
    167     }
    168 
    169     /**
    170      * Setter method for "header" tag attribute. (Mapping set in associated
    171      * BeanInfo class.)
    172      */
    173     public void setHeaderExpr(String headerExpr) {
    174         this.headerExpr = headerExpr;
    175     }
    176 
    177     /**
    178      * Setter method for "location" tag attribute. (Mapping set in associated
    179      * BeanInfo class.)
    180      */
    181     public void setLocationExpr(String locationExpr) {
    182         this.locationExpr = locationExpr;
    183     }
    184 
    185     /**
    186      * Setter method for "name" tag attribute. (Mapping set in associated
    187      * BeanInfo class.)
    188      */
    189     public void setNameExpr(String nameExpr) {
    190         this.nameExpr = nameExpr;
    191     }
    192 
    193     /**
    194      * Setter method for "parameter" tag attribute. (Mapping set in associated
    195      * BeanInfo class.)
    196      */
    197     public void setParameterExpr(String parameterExpr) {
    198         this.parameterExpr = parameterExpr;
    199     }
    200 
    201     /**
    202      * Setter method for "property" tag attribute. (Mapping set in associated
    203      * BeanInfo class.)
    204      */
    205     public void setPropertyExpr(String propertyExpr) {
    206         this.propertyExpr = propertyExpr;
    207     }
    208 
    209     /**
    210      * Setter method for "scope" tag attribute. (Mapping set in associated
    211      * BeanInfo class.)
    212      */
    213     public void setScopeExpr(String scopeExpr) {
    214         this.scopeExpr = scopeExpr;
    215     }
    216 
    217     /**
    218      * Setter method for "value" tag attribute. (Mapping set in associated
    219      * BeanInfo class.)
    220      */
    221     public void setValueExpr(String valueExpr) {
    222         this.valueExpr = valueExpr;
    223     }
    224 
    225     /**
    226      * Returns the string value of the expression.  This value will be
    227      * evaluated by the JSTL EL engine.
    228      */
    229     public String getExpr() {
    230         return (expr);
    231     }
    232 
    233     /**
    234      * Sets the string value of the expression.  This expression will be
    235      * evaluated by the JSTL EL engine.
    236      */
    237     public void setExpr(String expr) {
    238         this.expr = expr;
    239     }
    240 
    241     /**
    242      * Returns the evaluated expression.
    243      */
    244     public String getExprValue() {
    245         return (exprValue);
    246     }
    247 
    248     /**
    249      * Sets the evaluated expression.
    250      */
    251     public void setExprValue(String exprValue) {
    252         this.exprValue = exprValue;
    253     }
    254 
    255     /**
    256      * Releases state of custom tag so this instance can be reused.
    257      */
    258     public void release() {
    259         super.release();
    260         setCookieExpr(null);
    261         setHeaderExpr(null);
    262         setLocationExpr(null);
    263         setNameExpr(null);
    264         setParameterExpr(null);
    265         setPropertyExpr(null);
    266         setScopeExpr(null);
    267         setValueExpr(null);
    268         setExpr(null);
    269         setExprValue(null);
    270     }
    271 
    272     /**
    273      * Process the start tag.
    274      *
    275      * @throws JspException if a JSP exception has occurred
    276      */
    277     public int doStartTag() throws JspException {
    278         evaluateExpressions();
    279 
    280         return (super.doStartTag());
    281     }
    282 
    283     /**
    284      * Evaluates the condition that is being tested by this particular tag,
    285      * and returns <code>true</code> if the nested body content of this tag
    286      * should be evaluated, or <code>false</code> if it should be skipped.
    287      *
    288      * @param desired Desired value for a true result
    289      * @throws JspException if a JSP exception occurs
    290      */
    291     protected boolean condition(boolean desired)
    292         throws JspException {
    293         boolean result = false;
    294 
    295         if (getExprValue() != null) {
    296             result =
    297                 ELMatchSupport.condition(desired, getExprValue(), value,
    298                     location, messages, pageContext);
    299         } else {
    300             result = super.condition(desired);
    301         }
    302 
    303         return (result);
    304     }
    305 
    306     /**
    307      * Processes all attribute values which use the JSTL expression evaluation
    308      * engine to determine their values.
    309      *
    310      * @throws JspException if a JSP exception has occurred
    311      */
    312     private void evaluateExpressions()
    313         throws JspException {
    314         String string = null;
    315 
    316         if ((string =
    317                 EvalHelper.evalString("cookie", getCookieExpr(), this,
    318                     pageContext)) != null) {
    319             setCookie(string);
    320         }
    321 
    322         if ((string =
    323                 EvalHelper.evalString("expr", getExpr(), this, pageContext)) != null) {
    324             setExprValue(string);
    325         }
    326 
    327         if ((string =
    328                 EvalHelper.evalString("header", getHeaderExpr(), this,
    329                     pageContext)) != null) {
    330             setHeader(string);
    331         }
    332 
    333         if ((string =
    334                 EvalHelper.evalString("location", getLocationExpr(), this,
    335                     pageContext)) != null) {
    336             setLocation(string);
    337         }
    338 
    339         if ((string =
    340                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    341             setName(string);
    342         }
    343 
    344         if ((string =
    345                 EvalHelper.evalString("parameter", getParameterExpr(), this,
    346                     pageContext)) != null) {
    347             setParameter(string);
    348         }
    349 
    350         if ((string =
    351                 EvalHelper.evalString("property", getPropertyExpr(), this,
    352                     pageContext)) != null) {
    353             setProperty(string);
    354         }
    355 
    356         if ((string =
    357                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    358             setScope(string);
    359         }
    360 
    361         if ((string =
    362                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    363             setValue(string);
    364         }
    365     }
    366 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
