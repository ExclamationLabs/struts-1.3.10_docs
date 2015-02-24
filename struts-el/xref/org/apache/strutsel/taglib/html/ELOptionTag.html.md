[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELOptionTag.html)


    1   /*
    2    * $Id: ELOptionTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.OptionTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for select options.  The body of this tag is presented to the user in
    30   * the option list, while the value attribute is the value returned to the
    31   * server if this option is selected. <p> This class is a subclass of the
    32   * class <code>org.apache.struts.taglib.html.md.OptionTag</code> which provides
    33   * most of the described functionality.  This subclass allows all attribute
    34   * values to be specified as expressions utilizing the JavaServer Pages
    35   * Standard Library expression language.
    36   *
    37   * @version $Rev: 479635 $
    38   */
    39  public class ELOptionTag extends OptionTag {
    40      /**
    41       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String bundleExpr;
    45  
    46      /**
    47       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    48       * associated BeanInfo class.)
    49       */
    50      private String dirExpr;
    51  
    52      /**
    53       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String disabledExpr;
    57  
    58      /**
    59       * Instance variable mapped to "filter" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String filterExpr;
    63  
    64      /**
    65       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String langExpr;
    69  
    70      /**
    71       * Instance variable mapped to "key" tag attribute. (Mapping set in
    72       * associated BeanInfo class.)
    73       */
    74      private String keyExpr;
    75  
    76      /**
    77       * Instance variable mapped to "locale" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String localeExpr;
    81  
    82      /**
    83       * Instance variable mapped to "style" tag attribute. (Mapping set in
    84       * associated BeanInfo class.)
    85       */
    86      private String styleExpr;
    87  
    88      /**
    89       * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    90       * associated BeanInfo class.)
    91       */
    92      private String styleClassExpr;
    93  
    94      /**
    95       * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String styleIdExpr;
    99  
    100     /**
    101      * Instance variable mapped to "value" tag attribute. (Mapping set in
    102      * associated BeanInfo class.)
    103      */
    104     private String valueExpr;
    105 
    106     /**
    107      * Getter method for "bundle" tag attribute. (Mapping set in associated
    108      * BeanInfo class.)
    109      */
    110     public String getBundleExpr() {
    111         return (bundleExpr);
    112     }
    113 
    114     /**
    115      * Getter method for "dir" tag attribute. (Mapping set in associated
    116      * BeanInfo class.)
    117      */
    118     public String getDirExpr() {
    119         return (dirExpr);
    120     }
    121 
    122     /**
    123      * Getter method for "disabled" tag attribute. (Mapping set in associated
    124      * BeanInfo class.)
    125      */
    126     public String getDisabledExpr() {
    127         return (disabledExpr);
    128     }
    129 
    130     /**
    131      * Getter method for "filter" tag attribute. (Mapping set in associated
    132      * BeanInfo class.)
    133      */
    134     public String getFilterExpr() {
    135         return (filterExpr);
    136     }
    137 
    138     /**
    139      * Getter method for "lang" tag attribute. (Mapping set in associated
    140      * BeanInfo class.)
    141      */
    142     public String getLangExpr() {
    143         return (langExpr);
    144     }
    145 
    146     /**
    147      * Getter method for "key" tag attribute. (Mapping set in associated
    148      * BeanInfo class.)
    149      */
    150     public String getKeyExpr() {
    151         return (keyExpr);
    152     }
    153 
    154     /**
    155      * Getter method for "locale" tag attribute. (Mapping set in associated
    156      * BeanInfo class.)
    157      */
    158     public String getLocaleExpr() {
    159         return (localeExpr);
    160     }
    161 
    162     /**
    163      * Getter method for "style" tag attribute. (Mapping set in associated
    164      * BeanInfo class.)
    165      */
    166     public String getStyleExpr() {
    167         return (styleExpr);
    168     }
    169 
    170     /**
    171      * Getter method for "styleClass" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     public String getStyleClassExpr() {
    175         return (styleClassExpr);
    176     }
    177 
    178     /**
    179      * Getter method for "styleId" tag attribute. (Mapping set in associated
    180      * BeanInfo class.)
    181      */
    182     public String getStyleIdExpr() {
    183         return (styleIdExpr);
    184     }
    185 
    186     /**
    187      * Getter method for "value" tag attribute. (Mapping set in associated
    188      * BeanInfo class.)
    189      */
    190     public String getValueExpr() {
    191         return (valueExpr);
    192     }
    193 
    194     /**
    195      * Setter method for "bundle" tag attribute. (Mapping set in associated
    196      * BeanInfo class.)
    197      */
    198     public void setBundleExpr(String bundleExpr) {
    199         this.bundleExpr = bundleExpr;
    200     }
    201 
    202     /**
    203      * Setter method for "dir" tag attribute. (Mapping set in associated
    204      * BeanInfo class.)
    205      */
    206     public void setDirExpr(String dirExpr) {
    207         this.dirExpr = dirExpr;
    208     }
    209 
    210     /**
    211      * Setter method for "disabled" tag attribute. (Mapping set in associated
    212      * BeanInfo class.)
    213      */
    214     public void setDisabledExpr(String disabledExpr) {
    215         this.disabledExpr = disabledExpr;
    216     }
    217 
    218     /**
    219      * Setter method for "filter" tag attribute. (Mapping set in associated
    220      * BeanInfo class.)
    221      */
    222     public void setFilterExpr(String filterExpr) {
    223         this.filterExpr = filterExpr;
    224     }
    225 
    226     /**
    227      * Setter method for "key" tag attribute. (Mapping set in associated
    228      * BeanInfo class.)
    229      */
    230     public void setKeyExpr(String keyExpr) {
    231         this.keyExpr = keyExpr;
    232     }
    233 
    234     /**
    235      * Setter method for "lang" tag attribute. (Mapping set in associated
    236      * BeanInfo class.)
    237      */
    238     public void setLangExpr(String langExpr) {
    239         this.langExpr = langExpr;
    240     }
    241 
    242     /**
    243      * Setter method for "locale" tag attribute. (Mapping set in associated
    244      * BeanInfo class.)
    245      */
    246     public void setLocaleExpr(String localeExpr) {
    247         this.localeExpr = localeExpr;
    248     }
    249 
    250     /**
    251      * Setter method for "style" tag attribute. (Mapping set in associated
    252      * BeanInfo class.)
    253      */
    254     public void setStyleExpr(String styleExpr) {
    255         this.styleExpr = styleExpr;
    256     }
    257 
    258     /**
    259      * Setter method for "styleClass" tag attribute. (Mapping set in
    260      * associated BeanInfo class.)
    261      */
    262     public void setStyleClassExpr(String styleClassExpr) {
    263         this.styleClassExpr = styleClassExpr;
    264     }
    265 
    266     /**
    267      * Setter method for "styleId" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public void setStyleIdExpr(String styleIdExpr) {
    271         this.styleIdExpr = styleIdExpr;
    272     }
    273 
    274     /**
    275      * Setter method for "value" tag attribute. (Mapping set in associated
    276      * BeanInfo class.)
    277      */
    278     public void setValueExpr(String valueExpr) {
    279         this.valueExpr = valueExpr;
    280     }
    281 
    282     /**
    283      * Resets attribute values for tag reuse.
    284      */
    285     public void release() {
    286         super.release();
    287         setBundleExpr(null);
    288         setDirExpr(null);
    289         setDisabledExpr(null);
    290         setFilterExpr(null);
    291         setLangExpr(null);
    292         setKeyExpr(null);
    293         setLocaleExpr(null);
    294         setStyleExpr(null);
    295         setStyleClassExpr(null);
    296         setStyleIdExpr(null);
    297         setValueExpr(null);
    298     }
    299 
    300     /**
    301      * Process the start tag.
    302      *
    303      * @throws JspException if a JSP exception has occurred
    304      */
    305     public int doStartTag() throws JspException {
    306         evaluateExpressions();
    307 
    308         return (super.doStartTag());
    309     }
    310 
    311     /**
    312      * Processes all attribute values which use the JSTL expression evaluation
    313      * engine to determine their values.
    314      *
    315      * @throws JspException if a JSP exception has occurred
    316      */
    317     private void evaluateExpressions()
    318         throws JspException {
    319         String string = null;
    320         Boolean bool = null;
    321 
    322         if ((string =
    323                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    324                     pageContext)) != null) {
    325             setBundle(string);
    326         }
    327 
    328         if ((string =
    329                  EvalHelper.evalString("dir", getDirExpr(), this,
    330                          pageContext)) != null) {
    331          setDir(string);
    332         }
    333         
    334         if ((bool =
    335                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    336                     pageContext)) != null) {
    337             setDisabled(bool.booleanValue());
    338         }
    339 
    340         if ((bool =
    341                 EvalHelper.evalBoolean("filter", getFilterExpr(), this,
    342                     pageContext)) != null) {
    343             setFilter(bool.booleanValue());
    344         }
    345 
    346         if ((string =
    347                  EvalHelper.evalString("lang", getLangExpr(), this,
    348                          pageContext)) != null) {
    349          setLang(string);
    350         }
    351 
    352         if ((string =
    353                 EvalHelper.evalString("key", getKeyExpr(), this, pageContext)) != null) {
    354             setKey(string);
    355         }
    356 
    357         if ((string =
    358                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    359                     pageContext)) != null) {
    360             setLocale(string);
    361         }
    362 
    363         if ((string =
    364                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    365             setStyle(string);
    366         }
    367 
    368         if ((string =
    369                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    370                     pageContext)) != null) {
    371             setStyleClass(string);
    372         }
    373 
    374         if ((string =
    375                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    376                     pageContext)) != null) {
    377             setStyleId(string);
    378         }
    379 
    380         if ((string =
    381                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    382             setValue(string);
    383         }
    384     }
    385 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
