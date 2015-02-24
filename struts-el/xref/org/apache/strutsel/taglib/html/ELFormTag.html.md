[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELFormTag.html)


    1   /*
    2    * $Id: ELFormTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.FormTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that represents an input form, associated with a bean whose
    30   * properties correspond to the various fields of the form. <p> This class is
    31   * a subclass of the class <code>org.apache.struts.taglib.html.md.FormTag</code>
    32   * which provides most of the described functionality.  This subclass allows
    33   * all attribute values to be specified as expressions utilizing the
    34   * JavaServer Pages Standard Library expression language.
    35   *
    36   * @version $Rev: 479635 $
    37   */
    38  public class ELFormTag extends FormTag {
    39      /**
    40       * Instance variable mapped to "action" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String actionExpr;
    44  
    45      /**
    46       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String dirExpr;
    50  
    51      /**
    52       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String disabledExpr;
    56  
    57      /**
    58       * Instance variable mapped to "enctype" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String enctypeExpr;
    62  
    63      /**
    64       * Instance variable mapped to "focus" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String focusExpr;
    68  
    69      /**
    70       * Instance variable mapped to "focusIndex" tag attribute. (Mapping set in
    71       * associated BeanInfo class.)
    72       */
    73      private String focusIndexExpr;
    74  
    75      /**
    76       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    77       * associated BeanInfo class.)
    78       */
    79      private String langExpr;
    80  
    81      /**
    82       * Instance variable mapped to "method" tag attribute. (Mapping set in
    83       * associated BeanInfo class.)
    84       */
    85      private String methodExpr;
    86  
    87      /**
    88       * Instance variable mapped to "onreset" tag attribute. (Mapping set in
    89       * associated BeanInfo class.)
    90       */
    91      private String onresetExpr;
    92  
    93      /**
    94       * Instance variable mapped to "onsubmit" tag attribute. (Mapping set in
    95       * associated BeanInfo class.)
    96       */
    97      private String onsubmitExpr;
    98  
    99      /**
    100      * Instance variable mapped to "readonly" tag attribute. (Mapping set in
    101      * associated BeanInfo class.)
    102      */
    103     private String readonlyExpr;
    104 
    105     /**
    106      * Instance variable mapped to "scriptLanguage" tag attribute. (Mapping
    107      * set in associated BeanInfo class.)
    108      */
    109     private String scriptLanguageExpr;
    110 
    111     /**
    112      * Instance variable mapped to "style" tag attribute. (Mapping set in
    113      * associated BeanInfo class.)
    114      */
    115     private String styleExpr;
    116 
    117     /**
    118      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    119      * associated BeanInfo class.)
    120      */
    121     private String styleClassExpr;
    122 
    123     /**
    124      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    125      * associated BeanInfo class.)
    126      */
    127     private String styleIdExpr;
    128 
    129     /**
    130      * Instance variable mapped to "target" tag attribute. (Mapping set in
    131      * associated BeanInfo class.)
    132      */
    133     private String targetExpr;
    134 
    135     /**
    136      * Instance variable mapped to "acceptCharset" tag attribute. (Mapping set
    137      * in associated BeanInfo class.)
    138      */
    139     private String acceptCharsetExpr;
    140 
    141     /**
    142      * Getter method for "action" tag attribute. (Mapping set in associated
    143      * BeanInfo class.)
    144      */
    145     public String getActionExpr() {
    146         return (actionExpr);
    147     }
    148 
    149     /**
    150      * Getter method for "dir" tag attribute. (Mapping set in associated
    151      * BeanInfo class.)
    152      */
    153     public String getDirExpr() {
    154         return (dirExpr);
    155     }
    156 
    157     /**
    158      * Getter method for "disabled" tag attribute. (Mapping set in associated
    159      * BeanInfo class.)
    160      */
    161     public String getDisabledExpr() {
    162         return (disabledExpr);
    163     }
    164 
    165     /**
    166      * Getter method for "enctype" tag attribute. (Mapping set in associated
    167      * BeanInfo class.)
    168      */
    169     public String getEnctypeExpr() {
    170         return (enctypeExpr);
    171     }
    172 
    173     /**
    174      * Getter method for "focus" tag attribute. (Mapping set in associated
    175      * BeanInfo class.)
    176      */
    177     public String getFocusExpr() {
    178         return (focusExpr);
    179     }
    180 
    181     /**
    182      * Getter method for "focusIndex" tag attribute. (Mapping set in
    183      * associated BeanInfo class.)
    184      */
    185     public String getFocusIndexExpr() {
    186         return (focusIndexExpr);
    187     }
    188 
    189     /**
    190      * Getter method for "lang" tag attribute. (Mapping set in associated
    191      * BeanInfo class.)
    192      */
    193     public String getLangExpr() {
    194         return (langExpr);
    195     }
    196 
    197     /**
    198      * Getter method for "method" tag attribute. (Mapping set in associated
    199      * BeanInfo class.)
    200      */
    201     public String getMethodExpr() {
    202         return (methodExpr);
    203     }
    204 
    205     /**
    206      * Getter method for "onreset" tag attribute. (Mapping set in associated
    207      * BeanInfo class.)
    208      */
    209     public String getOnresetExpr() {
    210         return (onresetExpr);
    211     }
    212 
    213     /**
    214      * Getter method for "onsubmit" tag attribute. (Mapping set in associated
    215      * BeanInfo class.)
    216      */
    217     public String getOnsubmitExpr() {
    218         return (onsubmitExpr);
    219     }
    220 
    221     /**
    222      * Getter method for "readonly" tag attribute. (Mapping set in associated
    223      * BeanInfo class.)
    224      */
    225     public String getReadonlyExpr() {
    226         return (readonlyExpr);
    227     }
    228 
    229     /**
    230      * Getter method for "scriptLanguage" tag attribute. (Mapping set in
    231      * associated BeanInfo class.)
    232      */
    233     public String getScriptLanguageExpr() {
    234         return (scriptLanguageExpr);
    235     }
    236 
    237     /**
    238      * Getter method for "style" tag attribute. (Mapping set in associated
    239      * BeanInfo class.)
    240      */
    241     public String getStyleExpr() {
    242         return (styleExpr);
    243     }
    244 
    245     /**
    246      * Getter method for "styleClass" tag attribute. (Mapping set in
    247      * associated BeanInfo class.)
    248      */
    249     public String getStyleClassExpr() {
    250         return (styleClassExpr);
    251     }
    252 
    253     /**
    254      * Getter method for "styleId" tag attribute. (Mapping set in associated
    255      * BeanInfo class.)
    256      */
    257     public String getStyleIdExpr() {
    258         return (styleIdExpr);
    259     }
    260 
    261     /**
    262      * Getter method for "target" tag attribute. (Mapping set in associated
    263      * BeanInfo class.)
    264      */
    265     public String getTargetExpr() {
    266         return (targetExpr);
    267     }
    268 
    269     /**
    270      * Getter method for "acceptCharset" tag attribute. (Mapping set in
    271      * associated BeanInfo class.)
    272      */
    273     public String getAcceptCharsetExpr() {
    274         return (acceptCharsetExpr);
    275     }
    276 
    277     /**
    278      * Setter method for "action" tag attribute. (Mapping set in associated
    279      * BeanInfo class.)
    280      */
    281     public void setActionExpr(String actionExpr) {
    282         this.actionExpr = actionExpr;
    283     }
    284 
    285     /**
    286      * Setter method for "dir" tag attribute. (Mapping set in associated
    287      * BeanInfo class.)
    288      */
    289     public void setDirExpr(String dirExpr) {
    290         this.dirExpr = dirExpr;
    291     }
    292 
    293     /**
    294      * Setter method for "disabled" tag attribute. (Mapping set in associated
    295      * BeanInfo class.)
    296      */
    297     public void setDisabledExpr(String disabledExpr) {
    298         this.disabledExpr = disabledExpr;
    299     }
    300 
    301     /**
    302      * Setter method for "enctype" tag attribute. (Mapping set in associated
    303      * BeanInfo class.)
    304      */
    305     public void setEnctypeExpr(String enctypeExpr) {
    306         this.enctypeExpr = enctypeExpr;
    307     }
    308 
    309     /**
    310      * Setter method for "focus" tag attribute. (Mapping set in associated
    311      * BeanInfo class.)
    312      */
    313     public void setFocusExpr(String focusExpr) {
    314         this.focusExpr = focusExpr;
    315     }
    316 
    317     /**
    318      * Setter method for "focusIndex" tag attribute. (Mapping set in
    319      * associated BeanInfo class.)
    320      */
    321     public void setFocusIndexExpr(String focusIndexExpr) {
    322         this.focusIndexExpr = focusIndexExpr;
    323     }
    324 
    325     /**
    326      * Setter method for "lang" tag attribute. (Mapping set in associated
    327      * BeanInfo class.)
    328      */
    329     public void setLangExpr(String langExpr) {
    330         this.langExpr = langExpr;
    331     }
    332 
    333     /**
    334      * Setter method for "method" tag attribute. (Mapping set in associated
    335      * BeanInfo class.)
    336      */
    337     public void setMethodExpr(String methodExpr) {
    338         this.methodExpr = methodExpr;
    339     }
    340 
    341     /**
    342      * Setter method for "onreset" tag attribute. (Mapping set in associated
    343      * BeanInfo class.)
    344      */
    345     public void setOnresetExpr(String onresetExpr) {
    346         this.onresetExpr = onresetExpr;
    347     }
    348 
    349     /**
    350      * Setter method for "onsubmit" tag attribute. (Mapping set in associated
    351      * BeanInfo class.)
    352      */
    353     public void setOnsubmitExpr(String onsubmitExpr) {
    354         this.onsubmitExpr = onsubmitExpr;
    355     }
    356 
    357     /**
    358      * Setter method for "readonly" tag attribute. (Mapping set in associated
    359      * BeanInfo class.)
    360      */
    361     public void setReadonlyExpr(String readonlyExpr) {
    362         this.readonlyExpr = readonlyExpr;
    363     }
    364 
    365     /**
    366      * Setter method for "scriptLanguage" tag attribute. (Mapping set in
    367      * associated BeanInfo class.)
    368      */
    369     public void setScriptLanguageExpr(String scriptLanguageExpr) {
    370         this.scriptLanguageExpr = scriptLanguageExpr;
    371     }
    372 
    373     /**
    374      * Setter method for "style" tag attribute. (Mapping set in associated
    375      * BeanInfo class.)
    376      */
    377     public void setStyleExpr(String styleExpr) {
    378         this.styleExpr = styleExpr;
    379     }
    380 
    381     /**
    382      * Setter method for "styleClass" tag attribute. (Mapping set in
    383      * associated BeanInfo class.)
    384      */
    385     public void setStyleClassExpr(String styleClassExpr) {
    386         this.styleClassExpr = styleClassExpr;
    387     }
    388 
    389     /**
    390      * Setter method for "styleId" tag attribute. (Mapping set in associated
    391      * BeanInfo class.)
    392      */
    393     public void setStyleIdExpr(String styleIdExpr) {
    394         this.styleIdExpr = styleIdExpr;
    395     }
    396 
    397     /**
    398      * Setter method for "target" tag attribute. (Mapping set in associated
    399      * BeanInfo class.)
    400      */
    401     public void setTargetExpr(String targetExpr) {
    402         this.targetExpr = targetExpr;
    403     }
    404 
    405     /**
    406      * Setter method for "acceptCharset" tag attribute. (Mapping set in
    407      * associated BeanInfo class.)
    408      */
    409     public void setAcceptCharsetExpr(String acceptCharsetExpr) {
    410         this.acceptCharsetExpr = acceptCharsetExpr;
    411     }
    412 
    413     /**
    414      * Resets attribute values for tag reuse.
    415      */
    416     public void release() {
    417         super.release();
    418         setActionExpr(null);
    419         setDirExpr(null);
    420         setDisabledExpr(null);
    421         setEnctypeExpr(null);
    422         setFocusExpr(null);
    423         setFocusIndexExpr(null);
    424         setLangExpr(null);
    425         setMethodExpr(null);
    426         setOnresetExpr(null);
    427         setOnsubmitExpr(null);
    428         setReadonlyExpr(null);
    429         setScriptLanguageExpr(null);
    430         setStyleExpr(null);
    431         setStyleClassExpr(null);
    432         setStyleIdExpr(null);
    433         setTargetExpr(null);
    434         setAcceptCharsetExpr(null);
    435     }
    436 
    437     /**
    438      * Process the start tag.
    439      *
    440      * @throws JspException if a JSP exception has occurred
    441      */
    442     public int doStartTag() throws JspException {
    443         evaluateExpressions();
    444 
    445         return (super.doStartTag());
    446     }
    447 
    448     /**
    449      * Processes all attribute values which use the JSTL expression evaluation
    450      * engine to determine their values.
    451      *
    452      * @throws JspException if a JSP exception has occurred
    453      */
    454     private void evaluateExpressions()
    455         throws JspException {
    456         String string = null;
    457         Boolean bool = null;
    458 
    459         if ((string =
    460                 EvalHelper.evalString("action", getActionExpr(), this,
    461                     pageContext)) != null) {
    462             setAction(string);
    463         }
    464 
    465         if ((string =
    466                  EvalHelper.evalString("dir", getDirExpr(), this,
    467                          pageContext)) != null) {
    468          setDir(string);
    469         }
    470         
    471         if ((bool =
    472                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    473                     pageContext)) != null) {
    474             setDisabled(bool.booleanValue());
    475         }
    476 
    477         if ((string =
    478                 EvalHelper.evalString("enctype", getEnctypeExpr(), this,
    479                     pageContext)) != null) {
    480             setEnctype(string);
    481         }
    482 
    483         if ((string =
    484                 EvalHelper.evalString("focus", getFocusExpr(), this, pageContext)) != null) {
    485             setFocus(string);
    486         }
    487 
    488         if ((string =
    489                 EvalHelper.evalString("focusIndex", getFocusIndexExpr(), this,
    490                     pageContext)) != null) {
    491             setFocusIndex(string);
    492         }
    493 
    494         if ((string =
    495                  EvalHelper.evalString("lang", getLangExpr(), this,
    496                          pageContext)) != null) {
    497          setLang(string);
    498         }
    499 
    500         if ((string =
    501                 EvalHelper.evalString("method", getMethodExpr(), this,
    502                     pageContext)) != null) {
    503             setMethod(string);
    504         }
    505 
    506         if ((string =
    507                 EvalHelper.evalString("onreset", getOnresetExpr(), this,
    508                     pageContext)) != null) {
    509             setOnreset(string);
    510         }
    511 
    512         if ((string =
    513                 EvalHelper.evalString("onsubmit", getOnsubmitExpr(), this,
    514                     pageContext)) != null) {
    515             setOnsubmit(string);
    516         }
    517 
    518         if ((bool =
    519                 EvalHelper.evalBoolean("readonly", getReadonlyExpr(), this,
    520                     pageContext)) != null) {
    521             setReadonly(bool.booleanValue());
    522         }
    523 
    524         if ((bool =
    525                 EvalHelper.evalBoolean("scriptLanguage",
    526                     getScriptLanguageExpr(), this, pageContext)) != null) {
    527             setScriptLanguage(bool.booleanValue());
    528         }
    529 
    530         if ((string =
    531                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    532             setStyle(string);
    533         }
    534 
    535         if ((string =
    536                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    537                     pageContext)) != null) {
    538             setStyleClass(string);
    539         }
    540 
    541         if ((string =
    542                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    543                     pageContext)) != null) {
    544             setStyleId(string);
    545         }
    546 
    547         if ((string =
    548                 EvalHelper.evalString("target", getTargetExpr(), this,
    549                     pageContext)) != null) {
    550             setTarget(string);
    551         }
    552 
    553         if ((string =
    554                 EvalHelper.evalString("acceptCharset", getAcceptCharsetExpr(),
    555                     this, pageContext)) != null) {
    556             setAcceptCharset(string);
    557         }
    558     }
    559 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
