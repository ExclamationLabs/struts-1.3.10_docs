[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELJavascriptValidatorTag.html)


    1   /*
    2    * $Id: ELJavascriptValidatorTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.html.md;
    22  
    23  import org.apache.struts.taglib.html.md.JavascriptValidatorTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that generates JavaScript for client side validation based on
    30   * the validation rules loaded by the <code>ValidatorPlugIn</code> defined in
    31   * the struts-config.xml file. <p> This class is a subclass of the class
    32   * <code>org.apache.struts.taglib.html.md.JavascriptValidatorTag</code> which
    33   * provides most of the described functionality.  This subclass allows all
    34   * attribute values to be specified as expressions utilizing the JavaServer
    35   * Pages Standard Library expression language.
    36   *
    37   * @version $Rev: 471754 $
    38   */
    39  public class ELJavascriptValidatorTag extends JavascriptValidatorTag {
    40      /**
    41       * Instance variable mapped to "cdata" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String cdataExpr;
    45  
    46      /**
    47       * Instance variable mapped to "dynamicJavascript" tag attribute. (Mapping
    48       * set in associated BeanInfo class.)
    49       */
    50      private String dynamicJavascriptExpr;
    51  
    52      /**
    53       * Instance variable mapped to "formName" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String formNameExpr;
    57  
    58      /**
    59       * Instance variable mapped to "method" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String methodExpr;
    63  
    64      /**
    65       * Instance variable mapped to "page" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String pageExpr;
    69  
    70      /**
    71       * Instance variable mapped to "scriptLanguage" tag attribute. (Mapping
    72       * set in associated BeanInfo class.)
    73       */
    74      private String scriptLanguageExpr;
    75  
    76      /**
    77       * Instance variable mapped to "src" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String srcExpr;
    81  
    82      /**
    83       * Instance variable mapped to "staticJavascript" tag attribute. (Mapping
    84       * set in associated BeanInfo class.)
    85       */
    86      private String staticJavascriptExpr;
    87  
    88      /**
    89       * Instance variable mapped to .html.mdComment" tag attribute. (Mapping set
    90       * in associated BeanInfo class.)
    91       */
    92      private String.html.mdCommentExpr;
    93  
    94      /**
    95       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String bundleExpr;
    99  
    100     /**
    101      * Getter method for "cdata" tag attribute. (Mapping set in associated
    102      * BeanInfo class.)
    103      */
    104     public String getCdataExpr() {
    105         return (cdataExpr);
    106     }
    107 
    108     /**
    109      * Getter method for "dynamicJavascript" tag attribute. (Mapping set in
    110      * associated BeanInfo class.)
    111      */
    112     public String getDynamicJavascriptExpr() {
    113         return (dynamicJavascriptExpr);
    114     }
    115 
    116     /**
    117      * Getter method for "formName" tag attribute. (Mapping set in associated
    118      * BeanInfo class.)
    119      */
    120     public String getFormNameExpr() {
    121         return (formNameExpr);
    122     }
    123 
    124     /**
    125      * Getter method for "method" tag attribute. (Mapping set in associated
    126      * BeanInfo class.)
    127      */
    128     public String getMethodExpr() {
    129         return (methodExpr);
    130     }
    131 
    132     /**
    133      * Getter method for "page" tag attribute. (Mapping set in associated
    134      * BeanInfo class.)
    135      */
    136     public String getPageExpr() {
    137         return (pageExpr);
    138     }
    139 
    140     /**
    141      * Getter method for "scriptLanguage" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     public String getScriptLanguageExpr() {
    145         return (scriptLanguageExpr);
    146     }
    147 
    148     /**
    149      * Getter method for "src" tag attribute. (Mapping set in associated
    150      * BeanInfo class.)
    151      */
    152     public String getSrcExpr() {
    153         return (srcExpr);
    154     }
    155 
    156     /**
    157      * Getter method for "staticJavascript" tag attribute. (Mapping set in
    158      * associated BeanInfo class.)
    159      */
    160     public String getStaticJavascriptExpr() {
    161         return (staticJavascriptExpr);
    162     }
    163 
    164     /**
    165      * Getter method for .html.mdComment" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     public String getHtmlCommentExpr() {
    169         return .html.mdCommentExpr);
    170     }
    171 
    172     /**
    173      * Getter method for "bundle" tag attribute. (Mapping set in associated
    174      * BeanInfo class.)
    175      */
    176     public String getBundleExpr() {
    177         return (bundleExpr);
    178     }
    179 
    180     /**
    181      * Setter method for "cdata" tag attribute. (Mapping set in associated
    182      * BeanInfo class.)
    183      */
    184     public void setCdataExpr(String cdataExpr) {
    185         this.cdataExpr = cdataExpr;
    186     }
    187 
    188     /**
    189      * Setter method for "dynamicJavascript" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     public void setDynamicJavascriptExpr(String dynamicJavascriptExpr) {
    193         this.dynamicJavascriptExpr = dynamicJavascriptExpr;
    194     }
    195 
    196     /**
    197      * Setter method for "formName" tag attribute. (Mapping set in associated
    198      * BeanInfo class.)
    199      */
    200     public void setFormNameExpr(String formNameExpr) {
    201         this.formNameExpr = formNameExpr;
    202     }
    203 
    204     /**
    205      * Setter method for "method" tag attribute. (Mapping set in associated
    206      * BeanInfo class.)
    207      */
    208     public void setMethodExpr(String methodExpr) {
    209         this.methodExpr = methodExpr;
    210     }
    211 
    212     /**
    213      * Setter method for "page" tag attribute. (Mapping set in associated
    214      * BeanInfo class.)
    215      */
    216     public void setPageExpr(String pageExpr) {
    217         this.pageExpr = pageExpr;
    218     }
    219 
    220     /**
    221      * Setter method for "scriptLanguage" tag attribute. (Mapping set in
    222      * associated BeanInfo class.)
    223      */
    224     public void setScriptLanguageExpr(String scriptLanguageExpr) {
    225         this.scriptLanguageExpr = scriptLanguageExpr;
    226     }
    227 
    228     /**
    229      * Setter method for "src" tag attribute. (Mapping set in associated
    230      * BeanInfo class.)
    231      */
    232     public void setSrcExpr(String srcExpr) {
    233         this.srcExpr = srcExpr;
    234     }
    235 
    236     /**
    237      * Setter method for "staticJavascript" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     public void setStaticJavascriptExpr(String staticJavascriptExpr) {
    241         this.staticJavascriptExpr = staticJavascriptExpr;
    242     }
    243 
    244     /**
    245      * Setter method for .html.mdComment" tag attribute. (Mapping set in
    246      * associated BeanInfo class.)
    247      */
    248     public void setHtmlCommentExpr(String.html.mdCommentExpr) {
    249         this.html.mdCommentExpr = htmlCommentExpr;
    250     }
    251 
    252     /**
    253      * Setter method for "bundle" tag attribute. (Mapping set in associated
    254      * BeanInfo class.)
    255      */
    256     public void setBundleExpr(String bundleExpr) {
    257         this.bundleExpr = bundleExpr;
    258     }
    259 
    260     /**
    261      * Resets attribute values for tag reuse.
    262      */
    263     public void release() {
    264         super.release();
    265         setCdataExpr(null);
    266         setDynamicJavascriptExpr(null);
    267         setFormNameExpr(null);
    268         setMethodExpr(null);
    269         setPageExpr(null);
    270         setScriptLanguageExpr(null);
    271         setSrcExpr(null);
    272         setStaticJavascriptExpr(null);
    273         setHtmlCommentExpr(null);
    274         setBundleExpr(null);
    275     }
    276 
    277     /**
    278      * Process the start tag.
    279      *
    280      * @throws JspException if a JSP exception has occurred
    281      */
    282     public int doStartTag() throws JspException {
    283         evaluateExpressions();
    284 
    285         return (super.doStartTag());
    286     }
    287 
    288     /**
    289      * Processes all attribute values which use the JSTL expression evaluation
    290      * engine to determine their values.
    291      *
    292      * @throws JspException if a JSP exception has occurred
    293      */
    294     private void evaluateExpressions()
    295         throws JspException {
    296         String string = null;
    297         Integer integer = null;
    298         Boolean bool = null;
    299 
    300         if ((string =
    301                 EvalHelper.evalString("cdata", getCdataExpr(), this, pageContext)) != null) {
    302             setCdata(string);
    303         }
    304 
    305         if ((string =
    306                 EvalHelper.evalString("dynamicJavascript",
    307                     getDynamicJavascriptExpr(), this, pageContext)) != null) {
    308             setDynamicJavascript(string);
    309         }
    310 
    311         if ((string =
    312                 EvalHelper.evalString("formName", getFormNameExpr(), this,
    313                     pageContext)) != null) {
    314             setFormName(string);
    315         }
    316 
    317         if ((string =
    318                 EvalHelper.evalString("method", getMethodExpr(), this,
    319                     pageContext)) != null) {
    320             setMethod(string);
    321         }
    322 
    323         if ((integer =
    324                 EvalHelper.evalInteger("page", getPageExpr(), this, pageContext)) != null) {
    325             setPage(integer.intValue());
    326         }
    327 
    328         if ((bool =
    329                 EvalHelper.evalBoolean("scriptLanguage",
    330                     getScriptLanguageExpr(), this, pageContext)) != null) {
    331             setScriptLanguage(bool.booleanValue());
    332         }
    333 
    334         if ((string =
    335                 EvalHelper.evalString("src", getSrcExpr(), this, pageContext)) != null) {
    336             setSrc(string);
    337         }
    338 
    339         if ((string =
    340                 EvalHelper.evalString("staticJavascript",
    341                     getStaticJavascriptExpr(), this, pageContext)) != null) {
    342             setStaticJavascript(string);
    343         }
    344 
    345         if ((string =
    346                 EvalHelper.evalString(.html.mdComment", getHtmlCommentExpr(),
    347                     this, pageContext)) != null) {
    348             setHtmlComment(string);
    349         }
    350 
    351         if ((string =
    352                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    353                     pageContext)) != null) {
    354             setBundle(string);
    355         }
    356     }
    357 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
