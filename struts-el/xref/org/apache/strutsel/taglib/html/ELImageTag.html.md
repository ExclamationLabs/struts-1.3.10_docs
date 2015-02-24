[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELImageTag.html)


    1   /*
    2    * $Id: ELImageTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.ImageTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for input fields of type "image". <p> This class is a subclass of the
    30   * class <code>org.apache.struts.taglib.html.md.ImageTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELImageTag extends ImageTag {
    38      /**
    39       * Instance variable mapped to "accessKey" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String accessKeyExpr;
    43  
    44      /**
    45       * Instance variable mapped to "align" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String alignExpr;
    49  
    50      /**
    51       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String altExpr;
    55  
    56      /**
    57       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String altKeyExpr;
    61  
    62      /**
    63       * Instance variable mapped to "border" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String borderExpr;
    67  
    68      /**
    69       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String bundleExpr;
    73  
    74      /**
    75       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String dirExpr;
    79  
    80      /**
    81       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String disabledExpr;
    85  
    86      /**
    87       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String indexedExpr;
    91  
    92      /**
    93       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String langExpr;
    97  
    98      /**
    99       * Instance variable mapped to "locale" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String localeExpr;
    103 
    104     /**
    105      * Instance variable mapped to "module" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String moduleExpr;
    109 
    110     /**
    111      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String onblurExpr;
    115 
    116     /**
    117      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String onchangeExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onclickExpr;
    127 
    128     /**
    129      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String ondblclickExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    136      * associated BeanInfo class.)
    137      */
    138     private String onfocusExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     private String onkeydownExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    148      * associated BeanInfo class.)
    149      */
    150     private String onkeypressExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onkeyupExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    160      * in associated BeanInfo class.)
    161      */
    162     private String onmousedownExpr;
    163 
    164     /**
    165      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    166      * in associated BeanInfo class.)
    167      */
    168     private String onmousemoveExpr;
    169 
    170     /**
    171      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     private String onmouseoutExpr;
    175 
    176     /**
    177      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    178      * in associated BeanInfo class.)
    179      */
    180     private String onmouseoverExpr;
    181 
    182     /**
    183      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     private String onmouseupExpr;
    187 
    188     /**
    189      * Instance variable mapped to "page" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String pageExpr;
    193 
    194     /**
    195      * Instance variable mapped to "pageKey" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String pageKeyExpr;
    199 
    200     /**
    201      * Instance variable mapped to "property" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String propertyExpr;
    205 
    206     /**
    207      * Instance variable mapped to "src" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String srcExpr;
    211 
    212     /**
    213      * Instance variable mapped to "srcKey" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String srcKeyExpr;
    217 
    218     /**
    219      * Instance variable mapped to "style" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String styleExpr;
    223 
    224     /**
    225      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String styleClassExpr;
    229 
    230     /**
    231      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    232      * associated BeanInfo class.)
    233      */
    234     private String styleIdExpr;
    235 
    236     /**
    237      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     private String tabindexExpr;
    241 
    242     /**
    243      * Instance variable mapped to "title" tag attribute. (Mapping set in
    244      * associated BeanInfo class.)
    245      */
    246     private String titleExpr;
    247 
    248     /**
    249      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    250      * associated BeanInfo class.)
    251      */
    252     private String titleKeyExpr;
    253 
    254     /**
    255      * Instance variable mapped to "value" tag attribute. (Mapping set in
    256      * associated BeanInfo class.)
    257      */
    258     private String valueExpr;
    259 
    260     /**
    261      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    262      * BeanInfo class.)
    263      */
    264     public String getAccesskeyExpr() {
    265         return (accessKeyExpr);
    266     }
    267 
    268     /**
    269      * Getter method for "align" tag attribute. (Mapping set in associated
    270      * BeanInfo class.)
    271      */
    272     public String getAlignExpr() {
    273         return (alignExpr);
    274     }
    275 
    276     /**
    277      * Getter method for "alt" tag attribute. (Mapping set in associated
    278      * BeanInfo class.)
    279      */
    280     public String getAltExpr() {
    281         return (altExpr);
    282     }
    283 
    284     /**
    285      * Getter method for "altKey" tag attribute. (Mapping set in associated
    286      * BeanInfo class.)
    287      */
    288     public String getAltKeyExpr() {
    289         return (altKeyExpr);
    290     }
    291 
    292     /**
    293      * Getter method for "border" tag attribute. (Mapping set in associated
    294      * BeanInfo class.)
    295      */
    296     public String getBorderExpr() {
    297         return (borderExpr);
    298     }
    299 
    300     /**
    301      * Getter method for "bundle" tag attribute. (Mapping set in associated
    302      * BeanInfo class.)
    303      */
    304     public String getBundleExpr() {
    305         return (bundleExpr);
    306     }
    307 
    308     /**
    309      * Getter method for "dir" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public String getDirExpr() {
    313         return (dirExpr);
    314     }
    315 
    316     /**
    317      * Getter method for "disabled" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getDisabledExpr() {
    321         return (disabledExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "indexed" tag attribute. (Mapping set in associated
    326      * BeanInfo class.)
    327      */
    328     public String getIndexedExpr() {
    329         return (indexedExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "lang" tag attribute. (Mapping set in associated
    334      * BeanInfo class.)
    335      */
    336     public String getLangExpr() {
    337         return (langExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "locale" tag attribute. (Mapping set in associated
    342      * BeanInfo class.)
    343      */
    344     public String getLocaleExpr() {
    345         return (localeExpr);
    346     }
    347 
    348     /**
    349      * Getter method for "module" tag attribute. (Mapping set in associated
    350      * BeanInfo class.)
    351      */
    352     public String getModuleExpr() {
    353         return (moduleExpr);
    354     }
    355 
    356     /**
    357      * Getter method for "onblur" tag attribute. (Mapping set in associated
    358      * BeanInfo class.)
    359      */
    360     public String getOnblurExpr() {
    361         return (onblurExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "onchange" tag attribute. (Mapping set in associated
    366      * BeanInfo class.)
    367      */
    368     public String getOnchangeExpr() {
    369         return (onchangeExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "onclick" tag attribute. (Mapping set in associated
    374      * BeanInfo class.)
    375      */
    376     public String getOnclickExpr() {
    377         return (onclickExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "ondblclick" tag attribute. (Mapping set in
    382      * associated BeanInfo class.)
    383      */
    384     public String getOndblclickExpr() {
    385         return (ondblclickExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    390      * BeanInfo class.)
    391      */
    392     public String getOnfocusExpr() {
    393         return (onfocusExpr);
    394     }
    395 
    396     /**
    397      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    398      * BeanInfo class.)
    399      */
    400     public String getOnkeydownExpr() {
    401         return (onkeydownExpr);
    402     }
    403 
    404     /**
    405      * Getter method for "onkeypress" tag attribute. (Mapping set in
    406      * associated BeanInfo class.)
    407      */
    408     public String getOnkeypressExpr() {
    409         return (onkeypressExpr);
    410     }
    411 
    412     /**
    413      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    414      * BeanInfo class.)
    415      */
    416     public String getOnkeyupExpr() {
    417         return (onkeyupExpr);
    418     }
    419 
    420     /**
    421      * Getter method for "onmousedown" tag attribute. (Mapping set in
    422      * associated BeanInfo class.)
    423      */
    424     public String getOnmousedownExpr() {
    425         return (onmousedownExpr);
    426     }
    427 
    428     /**
    429      * Getter method for "onmousemove" tag attribute. (Mapping set in
    430      * associated BeanInfo class.)
    431      */
    432     public String getOnmousemoveExpr() {
    433         return (onmousemoveExpr);
    434     }
    435 
    436     /**
    437      * Getter method for "onmouseout" tag attribute. (Mapping set in
    438      * associated BeanInfo class.)
    439      */
    440     public String getOnmouseoutExpr() {
    441         return (onmouseoutExpr);
    442     }
    443 
    444     /**
    445      * Getter method for "onmouseover" tag attribute. (Mapping set in
    446      * associated BeanInfo class.)
    447      */
    448     public String getOnmouseoverExpr() {
    449         return (onmouseoverExpr);
    450     }
    451 
    452     /**
    453      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    454      * BeanInfo class.)
    455      */
    456     public String getOnmouseupExpr() {
    457         return (onmouseupExpr);
    458     }
    459 
    460     /**
    461      * Getter method for "page" tag attribute. (Mapping set in associated
    462      * BeanInfo class.)
    463      */
    464     public String getPageExpr() {
    465         return (pageExpr);
    466     }
    467 
    468     /**
    469      * Getter method for "pageKey" tag attribute. (Mapping set in associated
    470      * BeanInfo class.)
    471      */
    472     public String getPageKeyExpr() {
    473         return (pageKeyExpr);
    474     }
    475 
    476     /**
    477      * Getter method for "property" tag attribute. (Mapping set in associated
    478      * BeanInfo class.)
    479      */
    480     public String getPropertyExpr() {
    481         return (propertyExpr);
    482     }
    483 
    484     /**
    485      * Getter method for "src" tag attribute. (Mapping set in associated
    486      * BeanInfo class.)
    487      */
    488     public String getSrcExpr() {
    489         return (srcExpr);
    490     }
    491 
    492     /**
    493      * Getter method for "srcKey" tag attribute. (Mapping set in associated
    494      * BeanInfo class.)
    495      */
    496     public String getSrcKeyExpr() {
    497         return (srcKeyExpr);
    498     }
    499 
    500     /**
    501      * Getter method for "style" tag attribute. (Mapping set in associated
    502      * BeanInfo class.)
    503      */
    504     public String getStyleExpr() {
    505         return (styleExpr);
    506     }
    507 
    508     /**
    509      * Getter method for "styleClass" tag attribute. (Mapping set in
    510      * associated BeanInfo class.)
    511      */
    512     public String getStyleClassExpr() {
    513         return (styleClassExpr);
    514     }
    515 
    516     /**
    517      * Getter method for "styleId" tag attribute. (Mapping set in associated
    518      * BeanInfo class.)
    519      */
    520     public String getStyleIdExpr() {
    521         return (styleIdExpr);
    522     }
    523 
    524     /**
    525      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    526      * BeanInfo class.)
    527      */
    528     public String getTabindexExpr() {
    529         return (tabindexExpr);
    530     }
    531 
    532     /**
    533      * Getter method for "title" tag attribute. (Mapping set in associated
    534      * BeanInfo class.)
    535      */
    536     public String getTitleExpr() {
    537         return (titleExpr);
    538     }
    539 
    540     /**
    541      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    542      * BeanInfo class.)
    543      */
    544     public String getTitleKeyExpr() {
    545         return (titleKeyExpr);
    546     }
    547 
    548     /**
    549      * Getter method for "value" tag attribute. (Mapping set in associated
    550      * BeanInfo class.)
    551      */
    552     public String getValueExpr() {
    553         return (valueExpr);
    554     }
    555 
    556     /**
    557      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    558      * BeanInfo class.)
    559      */
    560     public void setAccesskeyExpr(String accessKeyExpr) {
    561         this.accessKeyExpr = accessKeyExpr;
    562     }
    563 
    564     /**
    565      * Setter method for "align" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public void setAlignExpr(String alignExpr) {
    569         this.alignExpr = alignExpr;
    570     }
    571 
    572     /**
    573      * Setter method for "alt" tag attribute. (Mapping set in associated
    574      * BeanInfo class.)
    575      */
    576     public void setAltExpr(String altExpr) {
    577         this.altExpr = altExpr;
    578     }
    579 
    580     /**
    581      * Setter method for "altKey" tag attribute. (Mapping set in associated
    582      * BeanInfo class.)
    583      */
    584     public void setAltKeyExpr(String altKeyExpr) {
    585         this.altKeyExpr = altKeyExpr;
    586     }
    587 
    588     /**
    589      * Setter method for "border" tag attribute. (Mapping set in associated
    590      * BeanInfo class.)
    591      */
    592     public void setBorderExpr(String borderExpr) {
    593         this.borderExpr = borderExpr;
    594     }
    595 
    596     /**
    597      * Setter method for "bundle" tag attribute. (Mapping set in associated
    598      * BeanInfo class.)
    599      */
    600     public void setBundleExpr(String bundleExpr) {
    601         this.bundleExpr = bundleExpr;
    602     }
    603 
    604     /**
    605      * Setter method for "dir" tag attribute. (Mapping set in associated
    606      * BeanInfo class.)
    607      */
    608     public void setDirExpr(String dirExpr) {
    609         this.dirExpr = dirExpr;
    610     }
    611 
    612     /**
    613      * Setter method for "disabled" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public void setDisabledExpr(String disabledExpr) {
    617         this.disabledExpr = disabledExpr;
    618     }
    619 
    620     /**
    621      * Setter method for "indexed" tag attribute. (Mapping set in associated
    622      * BeanInfo class.)
    623      */
    624     public void setIndexedExpr(String indexedExpr) {
    625         this.indexedExpr = indexedExpr;
    626     }
    627 
    628     /**
    629      * Setter method for "lang" tag attribute. (Mapping set in associated
    630      * BeanInfo class.)
    631      */
    632     public void setLangExpr(String langExpr) {
    633         this.langExpr = langExpr;
    634     }
    635 
    636     /**
    637      * Setter method for "locale" tag attribute. (Mapping set in associated
    638      * BeanInfo class.)
    639      */
    640     public void setLocaleExpr(String localeExpr) {
    641         this.localeExpr = localeExpr;
    642     }
    643 
    644     /**
    645      * Setter method for "module" tag attribute. (Mapping set in associated
    646      * BeanInfo class.)
    647      */
    648     public void setModuleExpr(String moduleExpr) {
    649         this.moduleExpr = moduleExpr;
    650     }
    651 
    652     /**
    653      * Setter method for "onblur" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public void setOnblurExpr(String onblurExpr) {
    657         this.onblurExpr = onblurExpr;
    658     }
    659 
    660     /**
    661      * Setter method for "onchange" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public void setOnchangeExpr(String onchangeExpr) {
    665         this.onchangeExpr = onchangeExpr;
    666     }
    667 
    668     /**
    669      * Setter method for "onclick" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setOnclickExpr(String onclickExpr) {
    673         this.onclickExpr = onclickExpr;
    674     }
    675 
    676     /**
    677      * Setter method for "ondblclick" tag attribute. (Mapping set in
    678      * associated BeanInfo class.)
    679      */
    680     public void setOndblclickExpr(String ondblclickExpr) {
    681         this.ondblclickExpr = ondblclickExpr;
    682     }
    683 
    684     /**
    685      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    686      * BeanInfo class.)
    687      */
    688     public void setOnfocusExpr(String onfocusExpr) {
    689         this.onfocusExpr = onfocusExpr;
    690     }
    691 
    692     /**
    693      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    694      * BeanInfo class.)
    695      */
    696     public void setOnkeydownExpr(String onkeydownExpr) {
    697         this.onkeydownExpr = onkeydownExpr;
    698     }
    699 
    700     /**
    701      * Setter method for "onkeypress" tag attribute. (Mapping set in
    702      * associated BeanInfo class.)
    703      */
    704     public void setOnkeypressExpr(String onkeypressExpr) {
    705         this.onkeypressExpr = onkeypressExpr;
    706     }
    707 
    708     /**
    709      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    710      * BeanInfo class.)
    711      */
    712     public void setOnkeyupExpr(String onkeyupExpr) {
    713         this.onkeyupExpr = onkeyupExpr;
    714     }
    715 
    716     /**
    717      * Setter method for "onmousedown" tag attribute. (Mapping set in
    718      * associated BeanInfo class.)
    719      */
    720     public void setOnmousedownExpr(String onmousedownExpr) {
    721         this.onmousedownExpr = onmousedownExpr;
    722     }
    723 
    724     /**
    725      * Setter method for "onmousemove" tag attribute. (Mapping set in
    726      * associated BeanInfo class.)
    727      */
    728     public void setOnmousemoveExpr(String onmousemoveExpr) {
    729         this.onmousemoveExpr = onmousemoveExpr;
    730     }
    731 
    732     /**
    733      * Setter method for "onmouseout" tag attribute. (Mapping set in
    734      * associated BeanInfo class.)
    735      */
    736     public void setOnmouseoutExpr(String onmouseoutExpr) {
    737         this.onmouseoutExpr = onmouseoutExpr;
    738     }
    739 
    740     /**
    741      * Setter method for "onmouseover" tag attribute. (Mapping set in
    742      * associated BeanInfo class.)
    743      */
    744     public void setOnmouseoverExpr(String onmouseoverExpr) {
    745         this.onmouseoverExpr = onmouseoverExpr;
    746     }
    747 
    748     /**
    749      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    750      * BeanInfo class.)
    751      */
    752     public void setOnmouseupExpr(String onmouseupExpr) {
    753         this.onmouseupExpr = onmouseupExpr;
    754     }
    755 
    756     /**
    757      * Setter method for "page" tag attribute. (Mapping set in associated
    758      * BeanInfo class.)
    759      */
    760     public void setPageExpr(String pageExpr) {
    761         this.pageExpr = pageExpr;
    762     }
    763 
    764     /**
    765      * Setter method for "pageKey" tag attribute. (Mapping set in associated
    766      * BeanInfo class.)
    767      */
    768     public void setPageKeyExpr(String pageKeyExpr) {
    769         this.pageKeyExpr = pageKeyExpr;
    770     }
    771 
    772     /**
    773      * Setter method for "property" tag attribute. (Mapping set in associated
    774      * BeanInfo class.)
    775      */
    776     public void setPropertyExpr(String propertyExpr) {
    777         this.propertyExpr = propertyExpr;
    778     }
    779 
    780     /**
    781      * Setter method for "src" tag attribute. (Mapping set in associated
    782      * BeanInfo class.)
    783      */
    784     public void setSrcExpr(String srcExpr) {
    785         this.srcExpr = srcExpr;
    786     }
    787 
    788     /**
    789      * Setter method for "srcKey" tag attribute. (Mapping set in associated
    790      * BeanInfo class.)
    791      */
    792     public void setSrcKeyExpr(String srcKeyExpr) {
    793         this.srcKeyExpr = srcKeyExpr;
    794     }
    795 
    796     /**
    797      * Setter method for "style" tag attribute. (Mapping set in associated
    798      * BeanInfo class.)
    799      */
    800     public void setStyleExpr(String styleExpr) {
    801         this.styleExpr = styleExpr;
    802     }
    803 
    804     /**
    805      * Setter method for "styleClass" tag attribute. (Mapping set in
    806      * associated BeanInfo class.)
    807      */
    808     public void setStyleClassExpr(String styleClassExpr) {
    809         this.styleClassExpr = styleClassExpr;
    810     }
    811 
    812     /**
    813      * Setter method for "styleId" tag attribute. (Mapping set in associated
    814      * BeanInfo class.)
    815      */
    816     public void setStyleIdExpr(String styleIdExpr) {
    817         this.styleIdExpr = styleIdExpr;
    818     }
    819 
    820     /**
    821      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    822      * BeanInfo class.)
    823      */
    824     public void setTabindexExpr(String tabindexExpr) {
    825         this.tabindexExpr = tabindexExpr;
    826     }
    827 
    828     /**
    829      * Setter method for "title" tag attribute. (Mapping set in associated
    830      * BeanInfo class.)
    831      */
    832     public void setTitleExpr(String titleExpr) {
    833         this.titleExpr = titleExpr;
    834     }
    835 
    836     /**
    837      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    838      * BeanInfo class.)
    839      */
    840     public void setTitleKeyExpr(String titleKeyExpr) {
    841         this.titleKeyExpr = titleKeyExpr;
    842     }
    843 
    844     /**
    845      * Setter method for "value" tag attribute. (Mapping set in associated
    846      * BeanInfo class.)
    847      */
    848     public void setValueExpr(String valueExpr) {
    849         this.valueExpr = valueExpr;
    850     }
    851 
    852     /**
    853      * Resets attribute values for tag reuse.
    854      */
    855     public void release() {
    856         super.release();
    857         setAccesskeyExpr(null);
    858         setAlignExpr(null);
    859         setAltExpr(null);
    860         setAltKeyExpr(null);
    861         setBorderExpr(null);
    862         setBundleExpr(null);
    863         setDirExpr(null);
    864         setDisabledExpr(null);
    865         setIndexedExpr(null);
    866         setLangExpr(null);
    867         setLocaleExpr(null);
    868         setModuleExpr(null);
    869         setOnblurExpr(null);
    870         setOnchangeExpr(null);
    871         setOnclickExpr(null);
    872         setOndblclickExpr(null);
    873         setOnfocusExpr(null);
    874         setOnkeydownExpr(null);
    875         setOnkeypressExpr(null);
    876         setOnkeyupExpr(null);
    877         setOnmousedownExpr(null);
    878         setOnmousemoveExpr(null);
    879         setOnmouseoutExpr(null);
    880         setOnmouseoverExpr(null);
    881         setOnmouseupExpr(null);
    882         setPageExpr(null);
    883         setPageKeyExpr(null);
    884         setPropertyExpr(null);
    885         setSrcExpr(null);
    886         setSrcKeyExpr(null);
    887         setStyleExpr(null);
    888         setStyleClassExpr(null);
    889         setStyleIdExpr(null);
    890         setTabindexExpr(null);
    891         setTitleExpr(null);
    892         setTitleKeyExpr(null);
    893         setValueExpr(null);
    894     }
    895 
    896     /**
    897      * Process the start tag.
    898      *
    899      * @throws JspException if a JSP exception has occurred
    900      */
    901     public int doStartTag() throws JspException {
    902         evaluateExpressions();
    903 
    904         return (super.doStartTag());
    905     }
    906 
    907     /**
    908      * Processes all attribute values which use the JSTL expression evaluation
    909      * engine to determine their values.
    910      *
    911      * @throws JspException if a JSP exception has occurred
    912      */
    913     private void evaluateExpressions()
    914         throws JspException {
    915         String string = null;
    916         Boolean bool = null;
    917 
    918         if ((string =
    919                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    920                     pageContext)) != null) {
    921             setAccesskey(string);
    922         }
    923 
    924         //  The "align" attribute is deprecated.  This needs to be removed when
    925         //  the "align" attribute is finally removed.
    926         if ((string =
    927                 EvalHelper.evalString("align", getAlignExpr(), this, pageContext)) != null) {
    928             setAlign(string);
    929         }
    930 
    931         if ((string =
    932                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    933             setAlt(string);
    934         }
    935 
    936         if ((string =
    937                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    938                     pageContext)) != null) {
    939             setAltKey(string);
    940         }
    941 
    942         if ((string =
    943                 EvalHelper.evalString("border", getBorderExpr(), this,
    944                     pageContext)) != null) {
    945             setBorder(string);
    946         }
    947 
    948         if ((string =
    949                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    950                     pageContext)) != null) {
    951             setBundle(string);
    952         }
    953 
    954         if ((string =
    955                  EvalHelper.evalString("dir", getDirExpr(), this,
    956                          pageContext)) != null) {
    957          setDir(string);
    958         }
    959         
    960         if ((bool =
    961                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    962                     pageContext)) != null) {
    963             setDisabled(bool.booleanValue());
    964         }
    965 
    966         if ((bool =
    967                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    968                     pageContext)) != null) {
    969             setIndexed(bool.booleanValue());
    970         }
    971 
    972         if ((string =
    973                  EvalHelper.evalString("lang", getLangExpr(), this,
    974                          pageContext)) != null) {
    975          setLang(string);
    976         }
    977 
    978         if ((string =
    979                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    980                     pageContext)) != null) {
    981             setLocale(string);
    982         }
    983 
    984         if ((string =
    985                 EvalHelper.evalString("module", getModuleExpr(), this,
    986                     pageContext)) != null) {
    987             setModule(string);
    988         }
    989 
    990         if ((string =
    991                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    992                     pageContext)) != null) {
    993             setOnblur(string);
    994         }
    995 
    996         if ((string =
    997                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    998                     pageContext)) != null) {
    999             setOnchange(string);
    1000         }
    1001 
    1002         if ((string =
    1003                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1004                     pageContext)) != null) {
    1005             setOnclick(string);
    1006         }
    1007 
    1008         if ((string =
    1009                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1010                     pageContext)) != null) {
    1011             setOndblclick(string);
    1012         }
    1013 
    1014         if ((string =
    1015                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    1016                     pageContext)) != null) {
    1017             setOnfocus(string);
    1018         }
    1019 
    1020         if ((string =
    1021                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1022                     pageContext)) != null) {
    1023             setOnkeydown(string);
    1024         }
    1025 
    1026         if ((string =
    1027                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1028                     pageContext)) != null) {
    1029             setOnkeypress(string);
    1030         }
    1031 
    1032         if ((string =
    1033                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1034                     pageContext)) != null) {
    1035             setOnkeyup(string);
    1036         }
    1037 
    1038         if ((string =
    1039                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1040                     this, pageContext)) != null) {
    1041             setOnmousedown(string);
    1042         }
    1043 
    1044         if ((string =
    1045                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1046                     this, pageContext)) != null) {
    1047             setOnmousemove(string);
    1048         }
    1049 
    1050         if ((string =
    1051                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1052                     pageContext)) != null) {
    1053             setOnmouseout(string);
    1054         }
    1055 
    1056         if ((string =
    1057                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1058                     this, pageContext)) != null) {
    1059             setOnmouseover(string);
    1060         }
    1061 
    1062         if ((string =
    1063                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1064                     pageContext)) != null) {
    1065             setOnmouseup(string);
    1066         }
    1067 
    1068         if ((string =
    1069                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    1070             setPage(string);
    1071         }
    1072 
    1073         if ((string =
    1074                 EvalHelper.evalString("pageKey", getPageKeyExpr(), this,
    1075                     pageContext)) != null) {
    1076             setPageKey(string);
    1077         }
    1078 
    1079         if ((string =
    1080                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1081                     pageContext)) != null) {
    1082             setProperty(string);
    1083         }
    1084 
    1085         if ((string =
    1086                 EvalHelper.evalString("src", getSrcExpr(), this, pageContext)) != null) {
    1087             setSrc(string);
    1088         }
    1089 
    1090         if ((string =
    1091                 EvalHelper.evalString("srcKey", getSrcKeyExpr(), this,
    1092                     pageContext)) != null) {
    1093             setSrcKey(string);
    1094         }
    1095 
    1096         if ((string =
    1097                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1098             setStyle(string);
    1099         }
    1100 
    1101         if ((string =
    1102                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1103                     pageContext)) != null) {
    1104             setStyleClass(string);
    1105         }
    1106 
    1107         if ((string =
    1108                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1109                     pageContext)) != null) {
    1110             setStyleId(string);
    1111         }
    1112 
    1113         if ((string =
    1114                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1115                     pageContext)) != null) {
    1116             setTabindex(string);
    1117         }
    1118 
    1119         if ((string =
    1120                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1121             setTitle(string);
    1122         }
    1123 
    1124         if ((string =
    1125                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1126                     pageContext)) != null) {
    1127             setTitleKey(string);
    1128         }
    1129 
    1130         if ((string =
    1131                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1132             setValue(string);
    1133         }
    1134     }
    1135 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
