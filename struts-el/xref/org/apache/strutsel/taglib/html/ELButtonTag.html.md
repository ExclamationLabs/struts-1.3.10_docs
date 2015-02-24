[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELButtonTag.html)


    1   /*
    2    * $Id: ELButtonTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.ButtonTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Renders an HTML BUTTON tag within the Struts framework. <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.html.md.ButtonTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELButtonTag extends ButtonTag {
    38      /**
    39       * Instance variable mapped to "accessKey" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String accessKeyExpr;
    43  
    44      /**
    45       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String altExpr;
    49  
    50      /**
    51       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String altKeyExpr;
    55  
    56      /**
    57       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String bundleExpr;
    61  
    62      /**
    63       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String dirExpr;
    67  
    68      /**
    69       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String disabledExpr;
    73  
    74      /**
    75       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String indexedExpr;
    79  
    80      /**
    81       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String langExpr;
    85  
    86      /**
    87       * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String onblurExpr;
    91  
    92      /**
    93       * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String onchangeExpr;
    97  
    98      /**
    99       * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String onclickExpr;
    103 
    104     /**
    105      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String ondblclickExpr;
    109 
    110     /**
    111      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String onfocusExpr;
    115 
    116     /**
    117      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String onkeydownExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onkeypressExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String onkeyupExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    136      * in associated BeanInfo class.)
    137      */
    138     private String onmousedownExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    142      * in associated BeanInfo class.)
    143      */
    144     private String onmousemoveExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    148      * associated BeanInfo class.)
    149      */
    150     private String onmouseoutExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    154      * in associated BeanInfo class.)
    155      */
    156     private String onmouseoverExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    160      * associated BeanInfo class.)
    161      */
    162     private String onmouseupExpr;
    163 
    164     /**
    165      * Instance variable mapped to "property" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     private String propertyExpr;
    169 
    170     /**
    171      * Instance variable mapped to "style" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     private String styleExpr;
    175 
    176     /**
    177      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    178      * associated BeanInfo class.)
    179      */
    180     private String styleClassExpr;
    181 
    182     /**
    183      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     private String styleIdExpr;
    187 
    188     /**
    189      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String tabindexExpr;
    193 
    194     /**
    195      * Instance variable mapped to "title" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String titleExpr;
    199 
    200     /**
    201      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String titleKeyExpr;
    205 
    206     /**
    207      * Instance variable mapped to "value" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String valueExpr;
    211 
    212     /**
    213      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    214      * BeanInfo class.)
    215      */
    216     public String getAccesskeyExpr() {
    217         return (accessKeyExpr);
    218     }
    219 
    220     /**
    221      * Getter method for "alt" tag attribute. (Mapping set in associated
    222      * BeanInfo class.)
    223      */
    224     public String getAltExpr() {
    225         return (altExpr);
    226     }
    227 
    228     /**
    229      * Getter method for "altKey" tag attribute. (Mapping set in associated
    230      * BeanInfo class.)
    231      */
    232     public String getAltKeyExpr() {
    233         return (altKeyExpr);
    234     }
    235 
    236     /**
    237      * Getter method for "bundle" tag attribute. (Mapping set in associated
    238      * BeanInfo class.)
    239      */
    240     public String getBundleExpr() {
    241         return (bundleExpr);
    242     }
    243 
    244     /**
    245      * Getter method for "dir" tag attribute. (Mapping set in associated
    246      * BeanInfo class.)
    247      */
    248     public String getDirExpr() {
    249         return (dirExpr);
    250     }
    251 
    252     /**
    253      * Getter method for "disabled" tag attribute. (Mapping set in associated
    254      * BeanInfo class.)
    255      */
    256     public String getDisabledExpr() {
    257         return (disabledExpr);
    258     }
    259 
    260     /**
    261      * Getter method for "indexed" tag attribute. (Mapping set in associated
    262      * BeanInfo class.)
    263      */
    264     public String getIndexedExpr() {
    265         return (indexedExpr);
    266     }
    267 
    268     /**
    269      * Getter method for "lang" tag attribute. (Mapping set in associated
    270      * BeanInfo class.)
    271      */
    272     public String getLangExpr() {
    273         return (langExpr);
    274     }
    275 
    276     /**
    277      * Getter method for "onblur" tag attribute. (Mapping set in associated
    278      * BeanInfo class.)
    279      */
    280     public String getOnblurExpr() {
    281         return (onblurExpr);
    282     }
    283 
    284     /**
    285      * Getter method for "onchange" tag attribute. (Mapping set in associated
    286      * BeanInfo class.)
    287      */
    288     public String getOnchangeExpr() {
    289         return (onchangeExpr);
    290     }
    291 
    292     /**
    293      * Getter method for "onclick" tag attribute. (Mapping set in associated
    294      * BeanInfo class.)
    295      */
    296     public String getOnclickExpr() {
    297         return (onclickExpr);
    298     }
    299 
    300     /**
    301      * Getter method for "ondblclick" tag attribute. (Mapping set in
    302      * associated BeanInfo class.)
    303      */
    304     public String getOndblclickExpr() {
    305         return (ondblclickExpr);
    306     }
    307 
    308     /**
    309      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public String getOnfocusExpr() {
    313         return (onfocusExpr);
    314     }
    315 
    316     /**
    317      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getOnkeydownExpr() {
    321         return (onkeydownExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "onkeypress" tag attribute. (Mapping set in
    326      * associated BeanInfo class.)
    327      */
    328     public String getOnkeypressExpr() {
    329         return (onkeypressExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    334      * BeanInfo class.)
    335      */
    336     public String getOnkeyupExpr() {
    337         return (onkeyupExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "onmousedown" tag attribute. (Mapping set in
    342      * associated BeanInfo class.)
    343      */
    344     public String getOnmousedownExpr() {
    345         return (onmousedownExpr);
    346     }
    347 
    348     /**
    349      * Getter method for "onmousemove" tag attribute. (Mapping set in
    350      * associated BeanInfo class.)
    351      */
    352     public String getOnmousemoveExpr() {
    353         return (onmousemoveExpr);
    354     }
    355 
    356     /**
    357      * Getter method for "onmouseout" tag attribute. (Mapping set in
    358      * associated BeanInfo class.)
    359      */
    360     public String getOnmouseoutExpr() {
    361         return (onmouseoutExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "onmouseover" tag attribute. (Mapping set in
    366      * associated BeanInfo class.)
    367      */
    368     public String getOnmouseoverExpr() {
    369         return (onmouseoverExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    374      * BeanInfo class.)
    375      */
    376     public String getOnmouseupExpr() {
    377         return (onmouseupExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "property" tag attribute. (Mapping set in associated
    382      * BeanInfo class.)
    383      */
    384     public String getPropertyExpr() {
    385         return (propertyExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "style" tag attribute. (Mapping set in associated
    390      * BeanInfo class.)
    391      */
    392     public String getStyleExpr() {
    393         return (styleExpr);
    394     }
    395 
    396     /**
    397      * Getter method for "styleClass" tag attribute. (Mapping set in
    398      * associated BeanInfo class.)
    399      */
    400     public String getStyleClassExpr() {
    401         return (styleClassExpr);
    402     }
    403 
    404     /**
    405      * Getter method for "styleId" tag attribute. (Mapping set in associated
    406      * BeanInfo class.)
    407      */
    408     public String getStyleIdExpr() {
    409         return (styleIdExpr);
    410     }
    411 
    412     /**
    413      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    414      * BeanInfo class.)
    415      */
    416     public String getTabindexExpr() {
    417         return (tabindexExpr);
    418     }
    419 
    420     /**
    421      * Getter method for "title" tag attribute. (Mapping set in associated
    422      * BeanInfo class.)
    423      */
    424     public String getTitleExpr() {
    425         return (titleExpr);
    426     }
    427 
    428     /**
    429      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    430      * BeanInfo class.)
    431      */
    432     public String getTitleKeyExpr() {
    433         return (titleKeyExpr);
    434     }
    435 
    436     /**
    437      * Getter method for "value" tag attribute. (Mapping set in associated
    438      * BeanInfo class.)
    439      */
    440     public String getValueExpr() {
    441         return (valueExpr);
    442     }
    443 
    444     /**
    445      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    446      * BeanInfo class.)
    447      */
    448     public void setAccesskeyExpr(String accessKeyExpr) {
    449         this.accessKeyExpr = accessKeyExpr;
    450     }
    451 
    452     /**
    453      * Setter method for "alt" tag attribute. (Mapping set in associated
    454      * BeanInfo class.)
    455      */
    456     public void setAltExpr(String altExpr) {
    457         this.altExpr = altExpr;
    458     }
    459 
    460     /**
    461      * Setter method for "altKey" tag attribute. (Mapping set in associated
    462      * BeanInfo class.)
    463      */
    464     public void setAltKeyExpr(String altKeyExpr) {
    465         this.altKeyExpr = altKeyExpr;
    466     }
    467 
    468     /**
    469      * Setter method for "bundle" tag attribute. (Mapping set in associated
    470      * BeanInfo class.)
    471      */
    472     public void setBundleExpr(String bundleExpr) {
    473         this.bundleExpr = bundleExpr;
    474     }
    475 
    476     /**
    477      * Setter method for "dir" tag attribute. (Mapping set in associated
    478      * BeanInfo class.)
    479      */
    480     public void setDirExpr(String dirExpr) {
    481         this.dirExpr = dirExpr;
    482     }
    483 
    484     /**
    485      * Setter method for "disabled" tag attribute. (Mapping set in associated
    486      * BeanInfo class.)
    487      */
    488     public void setDisabledExpr(String disabledExpr) {
    489         this.disabledExpr = disabledExpr;
    490     }
    491 
    492     /**
    493      * Setter method for "indexed" tag attribute. (Mapping set in associated
    494      * BeanInfo class.)
    495      */
    496     public void setIndexedExpr(String indexedExpr) {
    497         this.indexedExpr = indexedExpr;
    498     }
    499 
    500     /**
    501      * Setter method for "lang" tag attribute. (Mapping set in associated
    502      * BeanInfo class.)
    503      */
    504     public void setLangExpr(String langExpr) {
    505         this.langExpr = langExpr;
    506     }
    507 
    508     /**
    509      * Setter method for "onblur" tag attribute. (Mapping set in associated
    510      * BeanInfo class.)
    511      */
    512     public void setOnblurExpr(String onblurExpr) {
    513         this.onblurExpr = onblurExpr;
    514     }
    515 
    516     /**
    517      * Setter method for "onchange" tag attribute. (Mapping set in associated
    518      * BeanInfo class.)
    519      */
    520     public void setOnchangeExpr(String onchangeExpr) {
    521         this.onchangeExpr = onchangeExpr;
    522     }
    523 
    524     /**
    525      * Setter method for "onclick" tag attribute. (Mapping set in associated
    526      * BeanInfo class.)
    527      */
    528     public void setOnclickExpr(String onclickExpr) {
    529         this.onclickExpr = onclickExpr;
    530     }
    531 
    532     /**
    533      * Setter method for "ondblclick" tag attribute. (Mapping set in
    534      * associated BeanInfo class.)
    535      */
    536     public void setOndblclickExpr(String ondblclickExpr) {
    537         this.ondblclickExpr = ondblclickExpr;
    538     }
    539 
    540     /**
    541      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    542      * BeanInfo class.)
    543      */
    544     public void setOnfocusExpr(String onfocusExpr) {
    545         this.onfocusExpr = onfocusExpr;
    546     }
    547 
    548     /**
    549      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    550      * BeanInfo class.)
    551      */
    552     public void setOnkeydownExpr(String onkeydownExpr) {
    553         this.onkeydownExpr = onkeydownExpr;
    554     }
    555 
    556     /**
    557      * Setter method for "onkeypress" tag attribute. (Mapping set in
    558      * associated BeanInfo class.)
    559      */
    560     public void setOnkeypressExpr(String onkeypressExpr) {
    561         this.onkeypressExpr = onkeypressExpr;
    562     }
    563 
    564     /**
    565      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public void setOnkeyupExpr(String onkeyupExpr) {
    569         this.onkeyupExpr = onkeyupExpr;
    570     }
    571 
    572     /**
    573      * Setter method for "onmousedown" tag attribute. (Mapping set in
    574      * associated BeanInfo class.)
    575      */
    576     public void setOnmousedownExpr(String onmousedownExpr) {
    577         this.onmousedownExpr = onmousedownExpr;
    578     }
    579 
    580     /**
    581      * Setter method for "onmousemove" tag attribute. (Mapping set in
    582      * associated BeanInfo class.)
    583      */
    584     public void setOnmousemoveExpr(String onmousemoveExpr) {
    585         this.onmousemoveExpr = onmousemoveExpr;
    586     }
    587 
    588     /**
    589      * Setter method for "onmouseout" tag attribute. (Mapping set in
    590      * associated BeanInfo class.)
    591      */
    592     public void setOnmouseoutExpr(String onmouseoutExpr) {
    593         this.onmouseoutExpr = onmouseoutExpr;
    594     }
    595 
    596     /**
    597      * Setter method for "onmouseover" tag attribute. (Mapping set in
    598      * associated BeanInfo class.)
    599      */
    600     public void setOnmouseoverExpr(String onmouseoverExpr) {
    601         this.onmouseoverExpr = onmouseoverExpr;
    602     }
    603 
    604     /**
    605      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    606      * BeanInfo class.)
    607      */
    608     public void setOnmouseupExpr(String onmouseupExpr) {
    609         this.onmouseupExpr = onmouseupExpr;
    610     }
    611 
    612     /**
    613      * Setter method for "property" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public void setPropertyExpr(String propertyExpr) {
    617         this.propertyExpr = propertyExpr;
    618     }
    619 
    620     /**
    621      * Setter method for "style" tag attribute. (Mapping set in associated
    622      * BeanInfo class.)
    623      */
    624     public void setStyleExpr(String styleExpr) {
    625         this.styleExpr = styleExpr;
    626     }
    627 
    628     /**
    629      * Setter method for "styleClass" tag attribute. (Mapping set in
    630      * associated BeanInfo class.)
    631      */
    632     public void setStyleClassExpr(String styleClassExpr) {
    633         this.styleClassExpr = styleClassExpr;
    634     }
    635 
    636     /**
    637      * Setter method for "styleId" tag attribute. (Mapping set in associated
    638      * BeanInfo class.)
    639      */
    640     public void setStyleIdExpr(String styleIdExpr) {
    641         this.styleIdExpr = styleIdExpr;
    642     }
    643 
    644     /**
    645      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    646      * BeanInfo class.)
    647      */
    648     public void setTabindexExpr(String tabindexExpr) {
    649         this.tabindexExpr = tabindexExpr;
    650     }
    651 
    652     /**
    653      * Setter method for "title" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public void setTitleExpr(String titleExpr) {
    657         this.titleExpr = titleExpr;
    658     }
    659 
    660     /**
    661      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public void setTitleKeyExpr(String titleKeyExpr) {
    665         this.titleKeyExpr = titleKeyExpr;
    666     }
    667 
    668     /**
    669      * Setter method for "value" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setValueExpr(String valueExpr) {
    673         this.valueExpr = valueExpr;
    674     }
    675 
    676     /**
    677      * Resets attribute values for tag reuse.
    678      */
    679     public void release() {
    680         super.release();
    681         setAccesskeyExpr(null);
    682         setAltExpr(null);
    683         setAltKeyExpr(null);
    684         setBundleExpr(null);
    685         setDirExpr(null);
    686         setDisabledExpr(null);
    687         setIndexedExpr(null);
    688         setLangExpr(null);
    689         setOnblurExpr(null);
    690         setOnchangeExpr(null);
    691         setOnclickExpr(null);
    692         setOndblclickExpr(null);
    693         setOnfocusExpr(null);
    694         setOnkeydownExpr(null);
    695         setOnkeypressExpr(null);
    696         setOnkeyupExpr(null);
    697         setOnmousedownExpr(null);
    698         setOnmousemoveExpr(null);
    699         setOnmouseoutExpr(null);
    700         setOnmouseoverExpr(null);
    701         setOnmouseupExpr(null);
    702         setPropertyExpr(null);
    703         setStyleExpr(null);
    704         setStyleClassExpr(null);
    705         setStyleIdExpr(null);
    706         setTabindexExpr(null);
    707         setTitleExpr(null);
    708         setTitleKeyExpr(null);
    709         setValueExpr(null);
    710     }
    711 
    712     /**
    713      * Process the start tag.
    714      *
    715      * @throws JspException if a JSP exception has occurred
    716      */
    717     public int doStartTag() throws JspException {
    718         evaluateExpressions();
    719 
    720         return (super.doStartTag());
    721     }
    722 
    723     /**
    724      * Processes all attribute values which use the JSTL expression evaluation
    725      * engine to determine their values.
    726      *
    727      * @throws JspException if a JSP exception has occurred
    728      */
    729     private void evaluateExpressions()
    730         throws JspException {
    731         String string = null;
    732         Boolean bool = null;
    733 
    734         if ((string =
    735                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    736                     pageContext)) != null) {
    737             setAccesskey(string);
    738         }
    739 
    740         if ((string =
    741                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    742             setAlt(string);
    743         }
    744 
    745         if ((string =
    746                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    747                     pageContext)) != null) {
    748             setAltKey(string);
    749         }
    750 
    751         if ((string =
    752                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    753                     pageContext)) != null) {
    754             setBundle(string);
    755         }
    756 
    757         if ((string =
    758                  EvalHelper.evalString("dir", getDirExpr(), this,
    759                          pageContext)) != null) {
    760          setDir(string);
    761         }
    762         
    763         if ((bool =
    764                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    765                     pageContext)) != null) {
    766             setDisabled(bool.booleanValue());
    767         }
    768 
    769         if ((bool =
    770                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    771                     pageContext)) != null) {
    772             setIndexed(bool.booleanValue());
    773         }
    774 
    775         if ((string =
    776                  EvalHelper.evalString("lang", getLangExpr(), this,
    777                          pageContext)) != null) {
    778          setLang(string);
    779         }
    780 
    781         if ((string =
    782                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    783                     pageContext)) != null) {
    784             setOnblur(string);
    785         }
    786 
    787         if ((string =
    788                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    789                     pageContext)) != null) {
    790             setOnchange(string);
    791         }
    792 
    793         if ((string =
    794                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    795                     pageContext)) != null) {
    796             setOnclick(string);
    797         }
    798 
    799         if ((string =
    800                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    801                     pageContext)) != null) {
    802             setOndblclick(string);
    803         }
    804 
    805         if ((string =
    806                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    807                     pageContext)) != null) {
    808             setOnfocus(string);
    809         }
    810 
    811         if ((string =
    812                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    813                     pageContext)) != null) {
    814             setOnkeydown(string);
    815         }
    816 
    817         if ((string =
    818                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    819                     pageContext)) != null) {
    820             setOnkeypress(string);
    821         }
    822 
    823         if ((string =
    824                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    825                     pageContext)) != null) {
    826             setOnkeyup(string);
    827         }
    828 
    829         if ((string =
    830                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    831                     this, pageContext)) != null) {
    832             setOnmousedown(string);
    833         }
    834 
    835         if ((string =
    836                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    837                     this, pageContext)) != null) {
    838             setOnmousemove(string);
    839         }
    840 
    841         if ((string =
    842                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    843                     pageContext)) != null) {
    844             setOnmouseout(string);
    845         }
    846 
    847         if ((string =
    848                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    849                     this, pageContext)) != null) {
    850             setOnmouseover(string);
    851         }
    852 
    853         if ((string =
    854                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    855                     pageContext)) != null) {
    856             setOnmouseup(string);
    857         }
    858 
    859         if ((string =
    860                 EvalHelper.evalString("property", getPropertyExpr(), this,
    861                     pageContext)) != null) {
    862             setProperty(string);
    863         }
    864 
    865         if ((string =
    866                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    867             setStyle(string);
    868         }
    869 
    870         if ((string =
    871                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    872                     pageContext)) != null) {
    873             setStyleClass(string);
    874         }
    875 
    876         if ((string =
    877                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    878                     pageContext)) != null) {
    879             setStyleId(string);
    880         }
    881 
    882         if ((string =
    883                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    884                     pageContext)) != null) {
    885             setTabindex(string);
    886         }
    887 
    888         if ((string =
    889                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    890             setTitle(string);
    891         }
    892 
    893         if ((string =
    894                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    895                     pageContext)) != null) {
    896             setTitleKey(string);
    897         }
    898 
    899         if ((string =
    900                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    901             setValue(string);
    902         }
    903     }
    904 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
