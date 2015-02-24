[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELAddTag.html.md)


    1   /*
    2    * $Id: ELAddTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.tiles;
    22  
    23  import org.apache.struts.tiles.taglib.AddTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Adds an element to the surrounding list tag.  Same syntax as
    30   * <code>&lt;put&gt;</code>. <p> This class is a subclass of the class
    31   * <code>org.apache.struts.taglib.tiles.AddTag</code> which provides most of
    32   * the described functionality.  This subclass allows all attribute values to
    33   * be specified as expressions utilizing the JavaServer Pages Standard Library
    34   * expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELAddTag extends AddTag {
    39      /**
    40       * Instance variable mapped to "value" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String valueExpr;
    44  
    45      /**
    46       * Instance variable mapped to "content" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String contentExpr;
    50  
    51      /**
    52       * Instance variable mapped to "direct" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String directExpr;
    56  
    57      /**
    58       * Instance variable mapped to "type" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String typeExpr;
    62  
    63      /**
    64       * Instance variable mapped to "beanName" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String beanNameExpr;
    68  
    69      /**
    70       * Instance variable mapped to "beanProperty" tag attribute. (Mapping set
    71       * in associated BeanInfo class.)
    72       */
    73      private String beanPropertyExpr;
    74  
    75      /**
    76       * Instance variable mapped to "beanScope" tag attribute. (Mapping set in
    77       * associated BeanInfo class.)
    78       */
    79      private String beanScopeExpr;
    80  
    81      /**
    82       * Instance variable mapped to "role" tag attribute. (Mapping set in
    83       * associated BeanInfo class.)
    84       */
    85      private String roleExpr;
    86  
    87      /**
    88       * Getter method for "value" tag attribute. (Mapping set in associated
    89       * BeanInfo class.)
    90       */
    91      public String getValueExpr() {
    92          return (valueExpr);
    93      }
    94  
    95      /**
    96       * Getter method for "content" tag attribute. (Mapping set in associated
    97       * BeanInfo class.)
    98       */
    99      public String getContentExpr() {
    100         return (contentExpr);
    101     }
    102 
    103     /**
    104      * Getter method for "direct" tag attribute. (Mapping set in associated
    105      * BeanInfo class.)
    106      */
    107     public String getDirectExpr() {
    108         return (directExpr);
    109     }
    110 
    111     /**
    112      * Getter method for "type" tag attribute. (Mapping set in associated
    113      * BeanInfo class.)
    114      */
    115     public String getTypeExpr() {
    116         return (typeExpr);
    117     }
    118 
    119     /**
    120      * Getter method for "beanName" tag attribute. (Mapping set in associated
    121      * BeanInfo class.)
    122      */
    123     public String getBeanNameExpr() {
    124         return (beanNameExpr);
    125     }
    126 
    127     /**
    128      * Getter method for "beanProperty" tag attribute. (Mapping set in
    129      * associated BeanInfo class.)
    130      */
    131     public String getBeanPropertyExpr() {
    132         return (beanPropertyExpr);
    133     }
    134 
    135     /**
    136      * Getter method for "beanScope" tag attribute. (Mapping set in associated
    137      * BeanInfo class.)
    138      */
    139     public String getBeanScopeExpr() {
    140         return (beanScopeExpr);
    141     }
    142 
    143     /**
    144      * Getter method for "role" tag attribute. (Mapping set in associated
    145      * BeanInfo class.)
    146      */
    147     public String getRoleExpr() {
    148         return (roleExpr);
    149     }
    150 
    151     /**
    152      * Setter method for "value" tag attribute. (Mapping set in associated
    153      * BeanInfo class.)
    154      */
    155     public void setValueExpr(String valueExpr) {
    156         this.valueExpr = valueExpr;
    157     }
    158 
    159     /**
    160      * Setter method for "content" tag attribute. (Mapping set in associated
    161      * BeanInfo class.)
    162      */
    163     public void setContentExpr(String contentExpr) {
    164         this.contentExpr = contentExpr;
    165     }
    166 
    167     /**
    168      * Setter method for "direct" tag attribute. (Mapping set in associated
    169      * BeanInfo class.)
    170      */
    171     public void setDirectExpr(String directExpr) {
    172         this.directExpr = directExpr;
    173     }
    174 
    175     /**
    176      * Setter method for "type" tag attribute. (Mapping set in associated
    177      * BeanInfo class.)
    178      */
    179     public void setTypeExpr(String typeExpr) {
    180         this.typeExpr = typeExpr;
    181     }
    182 
    183     /**
    184      * Setter method for "beanName" tag attribute. (Mapping set in associated
    185      * BeanInfo class.)
    186      */
    187     public void setBeanNameExpr(String beanNameExpr) {
    188         this.beanNameExpr = beanNameExpr;
    189     }
    190 
    191     /**
    192      * Setter method for "beanProperty" tag attribute. (Mapping set in
    193      * associated BeanInfo class.)
    194      */
    195     public void setBeanPropertyExpr(String beanPropertyExpr) {
    196         this.beanPropertyExpr = beanPropertyExpr;
    197     }
    198 
    199     /**
    200      * Setter method for "beanScope" tag attribute. (Mapping set in associated
    201      * BeanInfo class.)
    202      */
    203     public void setBeanScopeExpr(String beanScopeExpr) {
    204         this.beanScopeExpr = beanScopeExpr;
    205     }
    206 
    207     /**
    208      * Setter method for "role" tag attribute. (Mapping set in associated
    209      * BeanInfo class.)
    210      */
    211     public void setRoleExpr(String roleExpr) {
    212         this.roleExpr = roleExpr;
    213     }
    214 
    215     /**
    216      * Resets attribute values for tag reuse.
    217      */
    218     public void release() {
    219         super.release();
    220         setValueExpr(null);
    221         setContentExpr(null);
    222         setDirectExpr(null);
    223         setTypeExpr(null);
    224         setBeanNameExpr(null);
    225         setBeanPropertyExpr(null);
    226         setBeanScopeExpr(null);
    227         setRoleExpr(null);
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
    252                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    253             setValue(string);
    254         }
    255 
    256         if ((string =
    257                 EvalHelper.evalString("content", getContentExpr(), this,
    258                     pageContext)) != null) {
    259             setContent(string);
    260         }
    261 
    262         if ((string =
    263                 EvalHelper.evalString("direct", getDirectExpr(), this,
    264                     pageContext)) != null) {
    265             setDirect(string);
    266         }
    267 
    268         if ((string =
    269                 EvalHelper.evalString("type", getTypeExpr(), this, pageContext)) != null) {
    270             setType(string);
    271         }
    272 
    273         if ((string =
    274                 EvalHelper.evalString("beanName", getBeanNameExpr(), this,
    275                     pageContext)) != null) {
    276             setBeanName(string);
    277         }
    278 
    279         if ((string =
    280                 EvalHelper.evalString("beanProperty", getBeanPropertyExpr(),
    281                     this, pageContext)) != null) {
    282             setBeanProperty(string);
    283         }
    284 
    285         if ((string =
    286                 EvalHelper.evalString("beanScope", getBeanScopeExpr(), this,
    287                     pageContext)) != null) {
    288             setBeanScope(string);
    289         }
    290 
    291         if ((string =
    292                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    293             setRole(string);
    294         }
    295     }
    296 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
