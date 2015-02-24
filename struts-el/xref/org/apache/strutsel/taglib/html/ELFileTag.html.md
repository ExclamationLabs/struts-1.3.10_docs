[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELFileTag.html)


    1   /*
    2    * $Id: ELFileTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.FileTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag for input fields of type "file". <p> This class is a subclass of
    30   * the class <code>org.apache.struts.taglib.html.md.FileTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELFileTag extends FileTag {
    38      /**
    39       * Instance variable mapped to "accesskey" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String accesskeyExpr;
    43  
    44      /**
    45       * Instance variable mapped to "accept" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String acceptExpr;
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
    63       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String bundleExpr;
    67  
    68      /**
    69       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String dirExpr;
    73  
    74      /**
    75       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String disabledExpr;
    79  
    80      /**
    81       * Instance variable mapped to "errorKey" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String errorKeyExpr;
    85  
    86      /**
    87       * Instance variable mapped to "errorStyle" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String errorStyleExpr;
    91  
    92      /**
    93       * Instance variable mapped to "errorStyleClass" tag attribute. (Mapping
    94       * set in associated BeanInfo class.)
    95       */
    96      private String errorStyleClassExpr;
    97  
    98      /**
    99       * Instance variable mapped to "errorStyleId" tag attribute. (Mapping set
    100      * in associated BeanInfo class.)
    101      */
    102     private String errorStyleIdExpr;
    103 
    104     /**
    105      * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String indexedExpr;
    109 
    110     /**
    111      * Instance variable mapped to "lang" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String langExpr;
    115 
    116     /**
    117      * Instance variable mapped to "maxlength" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String maxlengthExpr;
    121 
    122     /**
    123      * Instance variable mapped to "name" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String nameExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String onblurExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    136      * associated BeanInfo class.)
    137      */
    138     private String onchangeExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     private String onclickExpr;
    145 
    146     /**
    147      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    148      * associated BeanInfo class.)
    149      */
    150     private String ondblclickExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onfocusExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    160      * associated BeanInfo class.)
    161      */
    162     private String onkeydownExpr;
    163 
    164     /**
    165      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     private String onkeypressExpr;
    169 
    170     /**
    171      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     private String onkeyupExpr;
    175 
    176     /**
    177      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    178      * in associated BeanInfo class.)
    179      */
    180     private String onmousedownExpr;
    181 
    182     /**
    183      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    184      * in associated BeanInfo class.)
    185      */
    186     private String onmousemoveExpr;
    187 
    188     /**
    189      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String onmouseoutExpr;
    193 
    194     /**
    195      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    196      * in associated BeanInfo class.)
    197      */
    198     private String onmouseoverExpr;
    199 
    200     /**
    201      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String onmouseupExpr;
    205 
    206     /**
    207      * Instance variable mapped to "property" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String propertyExpr;
    211 
    212     /**
    213      * Instance variable mapped to "size" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String sizeExpr;
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
    261      * Getter method for "accesskey" tag attribute. (Mapping set in associated
    262      * BeanInfo class.)
    263      */
    264     public String getAccesskeyExpr() {
    265         return (accesskeyExpr);
    266     }
    267 
    268     /**
    269      * Getter method for "accept" tag attribute. (Mapping set in associated
    270      * BeanInfo class.)
    271      */
    272     public String getAcceptExpr() {
    273         return (acceptExpr);
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
    293      * Getter method for "bundle" tag attribute. (Mapping set in associated
    294      * BeanInfo class.)
    295      */
    296     public String getBundleExpr() {
    297         return (bundleExpr);
    298     }
    299 
    300     /**
    301      * Getter method for "dir" tag attribute. (Mapping set in associated
    302      * BeanInfo class.)
    303      */
    304     public String getDirExpr() {
    305         return (dirExpr);
    306     }
    307 
    308     /**
    309      * Getter method for "disabled" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public String getDisabledExpr() {
    313         return (disabledExpr);
    314     }
    315 
    316     /**
    317      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getErrorKeyExpr() {
    321         return (errorKeyExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "errorStyle" tag attribute. (Mapping set in
    326      * associated BeanInfo class.)
    327      */
    328     public String getErrorStyleExpr() {
    329         return (errorStyleExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    334      * associated BeanInfo class.)
    335      */
    336     public String getErrorStyleClassExpr() {
    337         return (errorStyleClassExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    342      * associated BeanInfo class.)
    343      */
    344     public String getErrorStyleIdExpr() {
    345         return (errorStyleIdExpr);
    346     }
    347 
    348     /**
    349      * Getter method for "indexed" tag attribute. (Mapping set in associated
    350      * BeanInfo class.)
    351      */
    352     public String getIndexedExpr() {
    353         return (indexedExpr);
    354     }
    355 
    356     /**
    357      * Getter method for "lang" tag attribute. (Mapping set in associated
    358      * BeanInfo class.)
    359      */
    360     public String getLangExpr() {
    361         return (langExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "maxlength" tag attribute. (Mapping set in associated
    366      * BeanInfo class.)
    367      */
    368     public String getMaxlengthExpr() {
    369         return (maxlengthExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "name" tag attribute. (Mapping set in associated
    374      * BeanInfo class.)
    375      */
    376     public String getNameExpr() {
    377         return (nameExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "onblur" tag attribute. (Mapping set in associated
    382      * BeanInfo class.)
    383      */
    384     public String getOnblurExpr() {
    385         return (onblurExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "onchange" tag attribute. (Mapping set in associated
    390      * BeanInfo class.)
    391      */
    392     public String getOnchangeExpr() {
    393         return (onchangeExpr);
    394     }
    395 
    396     /**
    397      * Getter method for "onclick" tag attribute. (Mapping set in associated
    398      * BeanInfo class.)
    399      */
    400     public String getOnclickExpr() {
    401         return (onclickExpr);
    402     }
    403 
    404     /**
    405      * Getter method for "ondblclick" tag attribute. (Mapping set in
    406      * associated BeanInfo class.)
    407      */
    408     public String getOndblclickExpr() {
    409         return (ondblclickExpr);
    410     }
    411 
    412     /**
    413      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    414      * BeanInfo class.)
    415      */
    416     public String getOnfocusExpr() {
    417         return (onfocusExpr);
    418     }
    419 
    420     /**
    421      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    422      * BeanInfo class.)
    423      */
    424     public String getOnkeydownExpr() {
    425         return (onkeydownExpr);
    426     }
    427 
    428     /**
    429      * Getter method for "onkeypress" tag attribute. (Mapping set in
    430      * associated BeanInfo class.)
    431      */
    432     public String getOnkeypressExpr() {
    433         return (onkeypressExpr);
    434     }
    435 
    436     /**
    437      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    438      * BeanInfo class.)
    439      */
    440     public String getOnkeyupExpr() {
    441         return (onkeyupExpr);
    442     }
    443 
    444     /**
    445      * Getter method for "onmousedown" tag attribute. (Mapping set in
    446      * associated BeanInfo class.)
    447      */
    448     public String getOnmousedownExpr() {
    449         return (onmousedownExpr);
    450     }
    451 
    452     /**
    453      * Getter method for "onmousemove" tag attribute. (Mapping set in
    454      * associated BeanInfo class.)
    455      */
    456     public String getOnmousemoveExpr() {
    457         return (onmousemoveExpr);
    458     }
    459 
    460     /**
    461      * Getter method for "onmouseout" tag attribute. (Mapping set in
    462      * associated BeanInfo class.)
    463      */
    464     public String getOnmouseoutExpr() {
    465         return (onmouseoutExpr);
    466     }
    467 
    468     /**
    469      * Getter method for "onmouseover" tag attribute. (Mapping set in
    470      * associated BeanInfo class.)
    471      */
    472     public String getOnmouseoverExpr() {
    473         return (onmouseoverExpr);
    474     }
    475 
    476     /**
    477      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    478      * BeanInfo class.)
    479      */
    480     public String getOnmouseupExpr() {
    481         return (onmouseupExpr);
    482     }
    483 
    484     /**
    485      * Getter method for "property" tag attribute. (Mapping set in associated
    486      * BeanInfo class.)
    487      */
    488     public String getPropertyExpr() {
    489         return (propertyExpr);
    490     }
    491 
    492     /**
    493      * Getter method for "size" tag attribute. (Mapping set in associated
    494      * BeanInfo class.)
    495      */
    496     public String getSizeExpr() {
    497         return (sizeExpr);
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
    557      * Setter method for "accesskey" tag attribute. (Mapping set in associated
    558      * BeanInfo class.)
    559      */
    560     public void setAccesskeyExpr(String accesskeyExpr) {
    561         this.accesskeyExpr = accesskeyExpr;
    562     }
    563 
    564     /**
    565      * Setter method for "accept" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public void setAcceptExpr(String acceptExpr) {
    569         this.acceptExpr = acceptExpr;
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
    589      * Setter method for "bundle" tag attribute. (Mapping set in associated
    590      * BeanInfo class.)
    591      */
    592     public void setBundleExpr(String bundleExpr) {
    593         this.bundleExpr = bundleExpr;
    594     }
    595 
    596     /**
    597      * Setter method for "dir" tag attribute. (Mapping set in associated
    598      * BeanInfo class.)
    599      */
    600     public void setDirExpr(String dirExpr) {
    601         this.dirExpr = dirExpr;
    602     }
    603 
    604     /**
    605      * Setter method for "disabled" tag attribute. (Mapping set in associated
    606      * BeanInfo class.)
    607      */
    608     public void setDisabledExpr(String disabledExpr) {
    609         this.disabledExpr = disabledExpr;
    610     }
    611 
    612     /**
    613      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public void setErrorKeyExpr(String errorKeyExpr) {
    617         this.errorKeyExpr = errorKeyExpr;
    618     }
    619 
    620     /**
    621      * Setter method for "errorStyle" tag attribute. (Mapping set in
    622      * associated BeanInfo class.)
    623      */
    624     public void setErrorStyleExpr(String errorStyleExpr) {
    625         this.errorStyleExpr = errorStyleExpr;
    626     }
    627 
    628     /**
    629      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    630      * associated BeanInfo class.)
    631      */
    632     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    633         this.errorStyleClassExpr = errorStyleClassExpr;
    634     }
    635 
    636     /**
    637      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    638      * associated BeanInfo class.)
    639      */
    640     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    641         this.errorStyleIdExpr = errorStyleIdExpr;
    642     }
    643 
    644     /**
    645      * Setter method for "indexed" tag attribute. (Mapping set in associated
    646      * BeanInfo class.)
    647      */
    648     public void setIndexedExpr(String indexedExpr) {
    649         this.indexedExpr = indexedExpr;
    650     }
    651 
    652     /**
    653      * Setter method for "lang" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public void setLangExpr(String langExpr) {
    657         this.langExpr = langExpr;
    658     }
    659 
    660     /**
    661      * Setter method for "maxlength" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public void setMaxlengthExpr(String maxlengthExpr) {
    665         this.maxlengthExpr = maxlengthExpr;
    666     }
    667 
    668     /**
    669      * Setter method for "name" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setNameExpr(String nameExpr) {
    673         this.nameExpr = nameExpr;
    674     }
    675 
    676     /**
    677      * Setter method for "onblur" tag attribute. (Mapping set in associated
    678      * BeanInfo class.)
    679      */
    680     public void setOnblurExpr(String onblurExpr) {
    681         this.onblurExpr = onblurExpr;
    682     }
    683 
    684     /**
    685      * Setter method for "onchange" tag attribute. (Mapping set in associated
    686      * BeanInfo class.)
    687      */
    688     public void setOnchangeExpr(String onchangeExpr) {
    689         this.onchangeExpr = onchangeExpr;
    690     }
    691 
    692     /**
    693      * Setter method for "onclick" tag attribute. (Mapping set in associated
    694      * BeanInfo class.)
    695      */
    696     public void setOnclickExpr(String onclickExpr) {
    697         this.onclickExpr = onclickExpr;
    698     }
    699 
    700     /**
    701      * Setter method for "ondblclick" tag attribute. (Mapping set in
    702      * associated BeanInfo class.)
    703      */
    704     public void setOndblclickExpr(String ondblclickExpr) {
    705         this.ondblclickExpr = ondblclickExpr;
    706     }
    707 
    708     /**
    709      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    710      * BeanInfo class.)
    711      */
    712     public void setOnfocusExpr(String onfocusExpr) {
    713         this.onfocusExpr = onfocusExpr;
    714     }
    715 
    716     /**
    717      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    718      * BeanInfo class.)
    719      */
    720     public void setOnkeydownExpr(String onkeydownExpr) {
    721         this.onkeydownExpr = onkeydownExpr;
    722     }
    723 
    724     /**
    725      * Setter method for "onkeypress" tag attribute. (Mapping set in
    726      * associated BeanInfo class.)
    727      */
    728     public void setOnkeypressExpr(String onkeypressExpr) {
    729         this.onkeypressExpr = onkeypressExpr;
    730     }
    731 
    732     /**
    733      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    734      * BeanInfo class.)
    735      */
    736     public void setOnkeyupExpr(String onkeyupExpr) {
    737         this.onkeyupExpr = onkeyupExpr;
    738     }
    739 
    740     /**
    741      * Setter method for "onmousedown" tag attribute. (Mapping set in
    742      * associated BeanInfo class.)
    743      */
    744     public void setOnmousedownExpr(String onmousedownExpr) {
    745         this.onmousedownExpr = onmousedownExpr;
    746     }
    747 
    748     /**
    749      * Setter method for "onmousemove" tag attribute. (Mapping set in
    750      * associated BeanInfo class.)
    751      */
    752     public void setOnmousemoveExpr(String onmousemoveExpr) {
    753         this.onmousemoveExpr = onmousemoveExpr;
    754     }
    755 
    756     /**
    757      * Setter method for "onmouseout" tag attribute. (Mapping set in
    758      * associated BeanInfo class.)
    759      */
    760     public void setOnmouseoutExpr(String onmouseoutExpr) {
    761         this.onmouseoutExpr = onmouseoutExpr;
    762     }
    763 
    764     /**
    765      * Setter method for "onmouseover" tag attribute. (Mapping set in
    766      * associated BeanInfo class.)
    767      */
    768     public void setOnmouseoverExpr(String onmouseoverExpr) {
    769         this.onmouseoverExpr = onmouseoverExpr;
    770     }
    771 
    772     /**
    773      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    774      * BeanInfo class.)
    775      */
    776     public void setOnmouseupExpr(String onmouseupExpr) {
    777         this.onmouseupExpr = onmouseupExpr;
    778     }
    779 
    780     /**
    781      * Setter method for "property" tag attribute. (Mapping set in associated
    782      * BeanInfo class.)
    783      */
    784     public void setPropertyExpr(String propertyExpr) {
    785         this.propertyExpr = propertyExpr;
    786     }
    787 
    788     /**
    789      * Setter method for "size" tag attribute. (Mapping set in associated
    790      * BeanInfo class.)
    791      */
    792     public void setSizeExpr(String sizeExpr) {
    793         this.sizeExpr = sizeExpr;
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
    858         setAcceptExpr(null);
    859         setAltExpr(null);
    860         setAltKeyExpr(null);
    861         setBundleExpr(null);
    862         setDirExpr(null);
    863         setDisabledExpr(null);
    864         setErrorKeyExpr(null);
    865         setErrorStyleExpr(null);
    866         setErrorStyleClassExpr(null);
    867         setErrorStyleIdExpr(null);
    868         setIndexedExpr(null);
    869         setLangExpr(null);
    870         setMaxlengthExpr(null);
    871         setNameExpr(null);
    872         setOnblurExpr(null);
    873         setOnchangeExpr(null);
    874         setOnclickExpr(null);
    875         setOndblclickExpr(null);
    876         setOnfocusExpr(null);
    877         setOnkeydownExpr(null);
    878         setOnkeypressExpr(null);
    879         setOnkeyupExpr(null);
    880         setOnmousedownExpr(null);
    881         setOnmousemoveExpr(null);
    882         setOnmouseoutExpr(null);
    883         setOnmouseoverExpr(null);
    884         setOnmouseupExpr(null);
    885         setPropertyExpr(null);
    886         setSizeExpr(null);
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
    919                 EvalHelper.evalString("accesskey", getAccesskeyExpr(), this,
    920                     pageContext)) != null) {
    921             setAccesskey(string);
    922         }
    923 
    924         if ((string =
    925                 EvalHelper.evalString("accept", getAcceptExpr(), this,
    926                     pageContext)) != null) {
    927             setAccept(string);
    928         }
    929 
    930         if ((string =
    931                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    932             setAlt(string);
    933         }
    934 
    935         if ((string =
    936                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    937                     pageContext)) != null) {
    938             setAltKey(string);
    939         }
    940 
    941         if ((string =
    942                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    943                     pageContext)) != null) {
    944             setBundle(string);
    945         }
    946 
    947         if ((string =
    948                  EvalHelper.evalString("dir", getDirExpr(), this,
    949                          pageContext)) != null) {
    950          setDir(string);
    951         }
    952         
    953         if ((bool =
    954                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    955                     pageContext)) != null) {
    956             setDisabled(bool.booleanValue());
    957         }
    958 
    959         if ((string =
    960                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    961                     pageContext)) != null) {
    962             setErrorKey(string);
    963         }
    964 
    965         if ((string =
    966                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    967                     pageContext)) != null) {
    968             setErrorStyle(string);
    969         }
    970 
    971         if ((string =
    972                 EvalHelper.evalString("errorStyleClass",
    973                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    974             setErrorStyleClass(string);
    975         }
    976 
    977         if ((string =
    978                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    979                     this, pageContext)) != null) {
    980             setErrorStyleId(string);
    981         }
    982 
    983         if ((bool =
    984                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    985                     pageContext)) != null) {
    986             setIndexed(bool.booleanValue());
    987         }
    988 
    989         if ((string =
    990                  EvalHelper.evalString("lang", getLangExpr(), this,
    991                          pageContext)) != null) {
    992          setLang(string);
    993         }
    994 
    995         if ((string =
    996                 EvalHelper.evalString("maxlength", getMaxlengthExpr(), this,
    997                     pageContext)) != null) {
    998             setMaxlength(string);
    999         }
    1000 
    1001         if ((string =
    1002                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    1003             setName(string);
    1004         }
    1005 
    1006         if ((string =
    1007                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    1008                     pageContext)) != null) {
    1009             setOnblur(string);
    1010         }
    1011 
    1012         if ((string =
    1013                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    1014                     pageContext)) != null) {
    1015             setOnchange(string);
    1016         }
    1017 
    1018         if ((string =
    1019                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1020                     pageContext)) != null) {
    1021             setOnclick(string);
    1022         }
    1023 
    1024         if ((string =
    1025                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1026                     pageContext)) != null) {
    1027             setOndblclick(string);
    1028         }
    1029 
    1030         if ((string =
    1031                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    1032                     pageContext)) != null) {
    1033             setOnfocus(string);
    1034         }
    1035 
    1036         if ((string =
    1037                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1038                     pageContext)) != null) {
    1039             setOnkeydown(string);
    1040         }
    1041 
    1042         if ((string =
    1043                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1044                     pageContext)) != null) {
    1045             setOnkeypress(string);
    1046         }
    1047 
    1048         if ((string =
    1049                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1050                     pageContext)) != null) {
    1051             setOnkeyup(string);
    1052         }
    1053 
    1054         if ((string =
    1055                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1056                     this, pageContext)) != null) {
    1057             setOnmousedown(string);
    1058         }
    1059 
    1060         if ((string =
    1061                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1062                     this, pageContext)) != null) {
    1063             setOnmousemove(string);
    1064         }
    1065 
    1066         if ((string =
    1067                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1068                     pageContext)) != null) {
    1069             setOnmouseout(string);
    1070         }
    1071 
    1072         if ((string =
    1073                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1074                     this, pageContext)) != null) {
    1075             setOnmouseover(string);
    1076         }
    1077 
    1078         if ((string =
    1079                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1080                     pageContext)) != null) {
    1081             setOnmouseup(string);
    1082         }
    1083 
    1084         if ((string =
    1085                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1086                     pageContext)) != null) {
    1087             setProperty(string);
    1088         }
    1089 
    1090         if ((string =
    1091                 EvalHelper.evalString("size", getSizeExpr(), this, pageContext)) != null) {
    1092             setSize(string);
    1093         }
    1094 
    1095         if ((string =
    1096                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1097             setStyle(string);
    1098         }
    1099 
    1100         if ((string =
    1101                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1102                     pageContext)) != null) {
    1103             setStyleClass(string);
    1104         }
    1105 
    1106         if ((string =
    1107                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1108                     pageContext)) != null) {
    1109             setStyleId(string);
    1110         }
    1111 
    1112         if ((string =
    1113                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1114                     pageContext)) != null) {
    1115             setTabindex(string);
    1116         }
    1117 
    1118         if ((string =
    1119                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1120             setTitle(string);
    1121         }
    1122 
    1123         if ((string =
    1124                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1125                     pageContext)) != null) {
    1126             setTitleKey(string);
    1127         }
    1128 
    1129         if ((string =
    1130                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1131             setValue(string);
    1132         }
    1133     }
    1134 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
