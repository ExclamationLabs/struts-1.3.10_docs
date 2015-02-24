[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/bean/ELMessageTag.html.md)


    1   /*
    2    * $Id: ELMessageTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.bean;
    22  
    23  import org.apache.struts.taglib.bean.MessageTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that retrieves an internationalized messages string (with
    30   * optional parametric replacement) from the <code>ActionResources</code>
    31   * object stored as a context attribute by our associated
    32   * <code>ActionServlet</code> implementation. <p> This class is a subclass of
    33   * the class <code>org.apache.struts.taglib.bean.MessageTag</code> which
    34   * provides most of the described functionality.  This subclass allows all
    35   * attribute values to be specified as expressions utilizing the JavaServer
    36   * Pages Standard Library expression language.
    37   *
    38   * @version $Rev: 471754 $
    39   */
    40  public class ELMessageTag extends MessageTag {
    41      /**
    42       * Instance variable mapped to "arg0" tag attribute. (Mapping set in
    43       * associated BeanInfo class.)
    44       */
    45      private String arg0Expr;
    46  
    47      /**
    48       * Instance variable mapped to "arg1" tag attribute. (Mapping set in
    49       * associated BeanInfo class.)
    50       */
    51      private String arg1Expr;
    52  
    53      /**
    54       * Instance variable mapped to "arg2" tag attribute. (Mapping set in
    55       * associated BeanInfo class.)
    56       */
    57      private String arg2Expr;
    58  
    59      /**
    60       * Instance variable mapped to "arg3" tag attribute. (Mapping set in
    61       * associated BeanInfo class.)
    62       */
    63      private String arg3Expr;
    64  
    65      /**
    66       * Instance variable mapped to "arg4" tag attribute. (Mapping set in
    67       * associated BeanInfo class.)
    68       */
    69      private String arg4Expr;
    70  
    71      /**
    72       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    73       * associated BeanInfo class.)
    74       */
    75      private String bundleExpr;
    76  
    77      /**
    78       * Instance variable mapped to "key" tag attribute. (Mapping set in
    79       * associated BeanInfo class.)
    80       */
    81      private String keyExpr;
    82  
    83      /**
    84       * Instance variable mapped to "locale" tag attribute. (Mapping set in
    85       * associated BeanInfo class.)
    86       */
    87      private String localeExpr;
    88  
    89      /**
    90       * Instance variable mapped to "name" tag attribute. (Mapping set in
    91       * associated BeanInfo class.)
    92       */
    93      private String nameExpr;
    94  
    95      /**
    96       * Instance variable mapped to "property" tag attribute. (Mapping set in
    97       * associated BeanInfo class.)
    98       */
    99      private String propertyExpr;
    100 
    101     /**
    102      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    103      * associated BeanInfo class.)
    104      */
    105     private String scopeExpr;
    106 
    107     /**
    108      * Getter method for "arg0" tag attribute. (Mapping set in associated
    109      * BeanInfo class.)
    110      */
    111     public String getArg0Expr() {
    112         return (arg0Expr);
    113     }
    114 
    115     /**
    116      * Getter method for "arg1" tag attribute. (Mapping set in associated
    117      * BeanInfo class.)
    118      */
    119     public String getArg1Expr() {
    120         return (arg1Expr);
    121     }
    122 
    123     /**
    124      * Getter method for "arg2" tag attribute. (Mapping set in associated
    125      * BeanInfo class.)
    126      */
    127     public String getArg2Expr() {
    128         return (arg2Expr);
    129     }
    130 
    131     /**
    132      * Getter method for "arg3" tag attribute. (Mapping set in associated
    133      * BeanInfo class.)
    134      */
    135     public String getArg3Expr() {
    136         return (arg3Expr);
    137     }
    138 
    139     /**
    140      * Getter method for "arg4" tag attribute. (Mapping set in associated
    141      * BeanInfo class.)
    142      */
    143     public String getArg4Expr() {
    144         return (arg4Expr);
    145     }
    146 
    147     /**
    148      * Getter method for "bundle" tag attribute. (Mapping set in associated
    149      * BeanInfo class.)
    150      */
    151     public String getBundleExpr() {
    152         return (bundleExpr);
    153     }
    154 
    155     /**
    156      * Getter method for "key" tag attribute. (Mapping set in associated
    157      * BeanInfo class.)
    158      */
    159     public String getKeyExpr() {
    160         return (keyExpr);
    161     }
    162 
    163     /**
    164      * Getter method for "locale" tag attribute. (Mapping set in associated
    165      * BeanInfo class.)
    166      */
    167     public String getLocaleExpr() {
    168         return (localeExpr);
    169     }
    170 
    171     /**
    172      * Getter method for "name" tag attribute. (Mapping set in associated
    173      * BeanInfo class.)
    174      */
    175     public String getNameExpr() {
    176         return (nameExpr);
    177     }
    178 
    179     /**
    180      * Getter method for "property" tag attribute. (Mapping set in associated
    181      * BeanInfo class.)
    182      */
    183     public String getPropertyExpr() {
    184         return (propertyExpr);
    185     }
    186 
    187     /**
    188      * Getter method for "scope" tag attribute. (Mapping set in associated
    189      * BeanInfo class.)
    190      */
    191     public String getScopeExpr() {
    192         return (scopeExpr);
    193     }
    194 
    195     /**
    196      * Setter method for "arg0" tag attribute. (Mapping set in associated
    197      * BeanInfo class.)
    198      */
    199     public void setArg0Expr(String arg0Expr) {
    200         this.arg0Expr = arg0Expr;
    201     }
    202 
    203     /**
    204      * Setter method for "arg1" tag attribute. (Mapping set in associated
    205      * BeanInfo class.)
    206      */
    207     public void setArg1Expr(String arg1Expr) {
    208         this.arg1Expr = arg1Expr;
    209     }
    210 
    211     /**
    212      * Setter method for "arg2" tag attribute. (Mapping set in associated
    213      * BeanInfo class.)
    214      */
    215     public void setArg2Expr(String arg2Expr) {
    216         this.arg2Expr = arg2Expr;
    217     }
    218 
    219     /**
    220      * Setter method for "arg3" tag attribute. (Mapping set in associated
    221      * BeanInfo class.)
    222      */
    223     public void setArg3Expr(String arg3Expr) {
    224         this.arg3Expr = arg3Expr;
    225     }
    226 
    227     /**
    228      * Setter method for "arg4" tag attribute. (Mapping set in associated
    229      * BeanInfo class.)
    230      */
    231     public void setArg4Expr(String arg4Expr) {
    232         this.arg4Expr = arg4Expr;
    233     }
    234 
    235     /**
    236      * Setter method for "bundle" tag attribute. (Mapping set in associated
    237      * BeanInfo class.)
    238      */
    239     public void setBundleExpr(String bundleExpr) {
    240         this.bundleExpr = bundleExpr;
    241     }
    242 
    243     /**
    244      * Setter method for "key" tag attribute. (Mapping set in associated
    245      * BeanInfo class.)
    246      */
    247     public void setKeyExpr(String keyExpr) {
    248         this.keyExpr = keyExpr;
    249     }
    250 
    251     /**
    252      * Setter method for "locale" tag attribute. (Mapping set in associated
    253      * BeanInfo class.)
    254      */
    255     public void setLocaleExpr(String localeExpr) {
    256         this.localeExpr = localeExpr;
    257     }
    258 
    259     /**
    260      * Setter method for "name" tag attribute. (Mapping set in associated
    261      * BeanInfo class.)
    262      */
    263     public void setNameExpr(String nameExpr) {
    264         this.nameExpr = nameExpr;
    265     }
    266 
    267     /**
    268      * Setter method for "property" tag attribute. (Mapping set in associated
    269      * BeanInfo class.)
    270      */
    271     public void setPropertyExpr(String propertyExpr) {
    272         this.propertyExpr = propertyExpr;
    273     }
    274 
    275     /**
    276      * Setter method for "scope" tag attribute. (Mapping set in associated
    277      * BeanInfo class.)
    278      */
    279     public void setScopeExpr(String scopeExpr) {
    280         this.scopeExpr = scopeExpr;
    281     }
    282 
    283     /**
    284      * Resets attribute values for tag reuse.
    285      */
    286     public void release() {
    287         super.release();
    288         setArg0Expr(null);
    289         setArg1Expr(null);
    290         setArg2Expr(null);
    291         setArg3Expr(null);
    292         setArg4Expr(null);
    293         setBundleExpr(null);
    294         setKeyExpr(null);
    295         setLocaleExpr(null);
    296         setNameExpr(null);
    297         setPropertyExpr(null);
    298         setScopeExpr(null);
    299     }
    300 
    301     /**
    302      * Process the start tag.
    303      *
    304      * @throws JspException if a JSP exception has occurred
    305      */
    306     public int doStartTag() throws JspException {
    307         evaluateExpressions();
    308 
    309         return (super.doStartTag());
    310     }
    311 
    312     /**
    313      * Processes all attribute values which use the JSTL expression evaluation
    314      * engine to determine their values.
    315      *
    316      * @throws JspException if a JSP exception has occurred
    317      */
    318     private void evaluateExpressions()
    319         throws JspException {
    320         String string = null;
    321 
    322         if ((string =
    323                 EvalHelper.evalString("arg0", getArg0Expr(), this, pageContext)) != null) {
    324             setArg0(string);
    325         }
    326 
    327         if ((string =
    328                 EvalHelper.evalString("arg1", getArg1Expr(), this, pageContext)) != null) {
    329             setArg1(string);
    330         }
    331 
    332         if ((string =
    333                 EvalHelper.evalString("arg2", getArg2Expr(), this, pageContext)) != null) {
    334             setArg2(string);
    335         }
    336 
    337         if ((string =
    338                 EvalHelper.evalString("arg3", getArg3Expr(), this, pageContext)) != null) {
    339             setArg3(string);
    340         }
    341 
    342         if ((string =
    343                 EvalHelper.evalString("arg4", getArg4Expr(), this, pageContext)) != null) {
    344             setArg4(string);
    345         }
    346 
    347         if ((string =
    348                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    349                     pageContext)) != null) {
    350             setBundle(string);
    351         }
    352 
    353         if ((string =
    354                 EvalHelper.evalString("key", getKeyExpr(), this, pageContext)) != null) {
    355             setKey(string);
    356         }
    357 
    358         if ((string =
    359                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    360                     pageContext)) != null) {
    361             setLocale(string);
    362         }
    363 
    364         if ((string =
    365                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    366             setName(string);
    367         }
    368 
    369         if ((string =
    370                 EvalHelper.evalString("property", getPropertyExpr(), this,
    371                     pageContext)) != null) {
    372             setProperty(string);
    373         }
    374 
    375         if ((string =
    376                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    377             setScope(string);
    378         }
    379     }
    380 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
