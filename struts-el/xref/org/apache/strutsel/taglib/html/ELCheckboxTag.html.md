[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELCheckboxTag.html)


    1   /*
    2    * $Id: ELCheckboxTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.CheckboxTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for input fields of type "checkbox". <p> This class is a subclass of
    30   * the class <code>org.apache.struts.taglib.html.md.CheckboxTag</code> which
    31   * provides most of the described functionality.  This subclass allows all
    32   * attribute values to be specified as expressions utilizing the JavaServer
    33   * Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELCheckboxTag extends CheckboxTag {
    38      /**
    39       * Instance variable mapped to "accesskey" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String accesskeyExpr;
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
    75       * Instance variable mapped to "errorKey" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String errorKeyExpr;
    79  
    80      /**
    81       * Instance variable mapped to "errorStyle" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String errorStyleExpr;
    85  
    86      /**
    87       * Instance variable mapped to "errorStyleClass" tag attribute. (Mapping
    88       * set in associated BeanInfo class.)
    89       */
    90      private String errorStyleClassExpr;
    91  
    92      /**
    93       * Instance variable mapped to "errorStyleId" tag attribute. (Mapping set
    94       * in associated BeanInfo class.)
    95       */
    96      private String errorStyleIdExpr;
    97  
    98      /**
    99       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String indexedExpr;
    103 
    104     /**
    105      * Instance variable mapped to "lang" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String langExpr;
    109 
    110     /**
    111      * Instance variable mapped to "name" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String nameExpr;
    115 
    116     /**
    117      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String onblurExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onchangeExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String onclickExpr;
    133 
    134     /**
    135      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    136      * associated BeanInfo class.)
    137      */
    138     private String ondblclickExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     private String onfocusExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    148      * associated BeanInfo class.)
    149      */
    150     private String onkeydownExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onkeypressExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    160      * associated BeanInfo class.)
    161      */
    162     private String onkeyupExpr;
    163 
    164     /**
    165      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    166      * in associated BeanInfo class.)
    167      */
    168     private String onmousedownExpr;
    169 
    170     /**
    171      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    172      * in associated BeanInfo class.)
    173      */
    174     private String onmousemoveExpr;
    175 
    176     /**
    177      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    178      * associated BeanInfo class.)
    179      */
    180     private String onmouseoutExpr;
    181 
    182     /**
    183      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    184      * in associated BeanInfo class.)
    185      */
    186     private String onmouseoverExpr;
    187 
    188     /**
    189      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String onmouseupExpr;
    193 
    194     /**
    195      * Instance variable mapped to "property" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String propertyExpr;
    199 
    200     /**
    201      * Instance variable mapped to "style" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String styleExpr;
    205 
    206     /**
    207      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String styleClassExpr;
    211 
    212     /**
    213      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String styleIdExpr;
    217 
    218     /**
    219      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String tabindexExpr;
    223 
    224     /**
    225      * Instance variable mapped to "title" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String titleExpr;
    229 
    230     /**
    231      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    232      * associated BeanInfo class.)
    233      */
    234     private String titleKeyExpr;
    235 
    236     /**
    237      * Instance variable mapped to "value" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     private String valueExpr;
    241 
    242     /**
    243      * Getter method for "accesskey" tag attribute. (Mapping set in associated
    244      * BeanInfo class.)
    245      */
    246     public String getAccesskeyExpr() {
    247         return (accesskeyExpr);
    248     }
    249 
    250     /**
    251      * Getter method for "alt" tag attribute. (Mapping set in associated
    252      * BeanInfo class.)
    253      */
    254     public String getAltExpr() {
    255         return (altExpr);
    256     }
    257 
    258     /**
    259      * Getter method for "altKey" tag attribute. (Mapping set in associated
    260      * BeanInfo class.)
    261      */
    262     public String getAltKeyExpr() {
    263         return (altKeyExpr);
    264     }
    265 
    266     /**
    267      * Getter method for "bundle" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public String getBundleExpr() {
    271         return (bundleExpr);
    272     }
    273 
    274     /**
    275      * Getter method for "dir" tag attribute. (Mapping set in associated
    276      * BeanInfo class.)
    277      */
    278     public String getDirExpr() {
    279         return (dirExpr);
    280     }
    281 
    282     /**
    283      * Getter method for "disabled" tag attribute. (Mapping set in associated
    284      * BeanInfo class.)
    285      */
    286     public String getDisabledExpr() {
    287         return (disabledExpr);
    288     }
    289 
    290     /**
    291      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    292      * BeanInfo class.)
    293      */
    294     public String getErrorKeyExpr() {
    295         return (errorKeyExpr);
    296     }
    297 
    298     /**
    299      * Getter method for "errorStyle" tag attribute. (Mapping set in
    300      * associated BeanInfo class.)
    301      */
    302     public String getErrorStyleExpr() {
    303         return (errorStyleExpr);
    304     }
    305 
    306     /**
    307      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    308      * associated BeanInfo class.)
    309      */
    310     public String getErrorStyleClassExpr() {
    311         return (errorStyleClassExpr);
    312     }
    313 
    314     /**
    315      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    316      * associated BeanInfo class.)
    317      */
    318     public String getErrorStyleIdExpr() {
    319         return (errorStyleIdExpr);
    320     }
    321 
    322     /**
    323      * Getter method for "indexed" tag attribute. (Mapping set in associated
    324      * BeanInfo class.)
    325      */
    326     public String getIndexedExpr() {
    327         return (indexedExpr);
    328     }
    329 
    330     /**
    331      * Getter method for "lang" tag attribute. (Mapping set in associated
    332      * BeanInfo class.)
    333      */
    334     public String getLangExpr() {
    335         return (langExpr);
    336     }
    337 
    338     /**
    339      * Getter method for "name" tag attribute. (Mapping set in associated
    340      * BeanInfo class.)
    341      */
    342     public String getNameExpr() {
    343         return (nameExpr);
    344     }
    345 
    346     /**
    347      * Getter method for "onblur" tag attribute. (Mapping set in associated
    348      * BeanInfo class.)
    349      */
    350     public String getOnblurExpr() {
    351         return (onblurExpr);
    352     }
    353 
    354     /**
    355      * Getter method for "onchange" tag attribute. (Mapping set in associated
    356      * BeanInfo class.)
    357      */
    358     public String getOnchangeExpr() {
    359         return (onchangeExpr);
    360     }
    361 
    362     /**
    363      * Getter method for "onclick" tag attribute. (Mapping set in associated
    364      * BeanInfo class.)
    365      */
    366     public String getOnclickExpr() {
    367         return (onclickExpr);
    368     }
    369 
    370     /**
    371      * Getter method for "ondblclick" tag attribute. (Mapping set in
    372      * associated BeanInfo class.)
    373      */
    374     public String getOndblclickExpr() {
    375         return (ondblclickExpr);
    376     }
    377 
    378     /**
    379      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    380      * BeanInfo class.)
    381      */
    382     public String getOnfocusExpr() {
    383         return (onfocusExpr);
    384     }
    385 
    386     /**
    387      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    388      * BeanInfo class.)
    389      */
    390     public String getOnkeydownExpr() {
    391         return (onkeydownExpr);
    392     }
    393 
    394     /**
    395      * Getter method for "onkeypress" tag attribute. (Mapping set in
    396      * associated BeanInfo class.)
    397      */
    398     public String getOnkeypressExpr() {
    399         return (onkeypressExpr);
    400     }
    401 
    402     /**
    403      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    404      * BeanInfo class.)
    405      */
    406     public String getOnkeyupExpr() {
    407         return (onkeyupExpr);
    408     }
    409 
    410     /**
    411      * Getter method for "onmousedown" tag attribute. (Mapping set in
    412      * associated BeanInfo class.)
    413      */
    414     public String getOnmousedownExpr() {
    415         return (onmousedownExpr);
    416     }
    417 
    418     /**
    419      * Getter method for "onmousemove" tag attribute. (Mapping set in
    420      * associated BeanInfo class.)
    421      */
    422     public String getOnmousemoveExpr() {
    423         return (onmousemoveExpr);
    424     }
    425 
    426     /**
    427      * Getter method for "onmouseout" tag attribute. (Mapping set in
    428      * associated BeanInfo class.)
    429      */
    430     public String getOnmouseoutExpr() {
    431         return (onmouseoutExpr);
    432     }
    433 
    434     /**
    435      * Getter method for "onmouseover" tag attribute. (Mapping set in
    436      * associated BeanInfo class.)
    437      */
    438     public String getOnmouseoverExpr() {
    439         return (onmouseoverExpr);
    440     }
    441 
    442     /**
    443      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    444      * BeanInfo class.)
    445      */
    446     public String getOnmouseupExpr() {
    447         return (onmouseupExpr);
    448     }
    449 
    450     /**
    451      * Getter method for "property" tag attribute. (Mapping set in associated
    452      * BeanInfo class.)
    453      */
    454     public String getPropertyExpr() {
    455         return (propertyExpr);
    456     }
    457 
    458     /**
    459      * Getter method for "style" tag attribute. (Mapping set in associated
    460      * BeanInfo class.)
    461      */
    462     public String getStyleExpr() {
    463         return (styleExpr);
    464     }
    465 
    466     /**
    467      * Getter method for "styleClass" tag attribute. (Mapping set in
    468      * associated BeanInfo class.)
    469      */
    470     public String getStyleClassExpr() {
    471         return (styleClassExpr);
    472     }
    473 
    474     /**
    475      * Getter method for "styleId" tag attribute. (Mapping set in associated
    476      * BeanInfo class.)
    477      */
    478     public String getStyleIdExpr() {
    479         return (styleIdExpr);
    480     }
    481 
    482     /**
    483      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    484      * BeanInfo class.)
    485      */
    486     public String getTabindexExpr() {
    487         return (tabindexExpr);
    488     }
    489 
    490     /**
    491      * Getter method for "title" tag attribute. (Mapping set in associated
    492      * BeanInfo class.)
    493      */
    494     public String getTitleExpr() {
    495         return (titleExpr);
    496     }
    497 
    498     /**
    499      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    500      * BeanInfo class.)
    501      */
    502     public String getTitleKeyExpr() {
    503         return (titleKeyExpr);
    504     }
    505 
    506     /**
    507      * Getter method for "value" tag attribute. (Mapping set in associated
    508      * BeanInfo class.)
    509      */
    510     public String getValueExpr() {
    511         return (valueExpr);
    512     }
    513 
    514     /**
    515      * Setter method for "accesskey" tag attribute. (Mapping set in associated
    516      * BeanInfo class.)
    517      */
    518     public void setAccesskeyExpr(String accesskeyExpr) {
    519         this.accesskeyExpr = accesskeyExpr;
    520     }
    521 
    522     /**
    523      * Setter method for "alt" tag attribute. (Mapping set in associated
    524      * BeanInfo class.)
    525      */
    526     public void setAltExpr(String altExpr) {
    527         this.altExpr = altExpr;
    528     }
    529 
    530     /**
    531      * Setter method for "altKey" tag attribute. (Mapping set in associated
    532      * BeanInfo class.)
    533      */
    534     public void setAltKeyExpr(String altKeyExpr) {
    535         this.altKeyExpr = altKeyExpr;
    536     }
    537 
    538     /**
    539      * Setter method for "bundle" tag attribute. (Mapping set in associated
    540      * BeanInfo class.)
    541      */
    542     public void setBundleExpr(String bundleExpr) {
    543         this.bundleExpr = bundleExpr;
    544     }
    545 
    546     /**
    547      * Setter method for "dir" tag attribute. (Mapping set in associated
    548      * BeanInfo class.)
    549      */
    550     public void setDirExpr(String dirExpr) {
    551         this.dirExpr = dirExpr;
    552     }
    553 
    554     /**
    555      * Setter method for "disabled" tag attribute. (Mapping set in associated
    556      * BeanInfo class.)
    557      */
    558     public void setDisabledExpr(String disabledExpr) {
    559         this.disabledExpr = disabledExpr;
    560     }
    561 
    562     /**
    563      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    564      * BeanInfo class.)
    565      */
    566     public void setErrorKeyExpr(String errorKeyExpr) {
    567         this.errorKeyExpr = errorKeyExpr;
    568     }
    569 
    570     /**
    571      * Setter method for "errorStyle" tag attribute. (Mapping set in
    572      * associated BeanInfo class.)
    573      */
    574     public void setErrorStyleExpr(String errorStyleExpr) {
    575         this.errorStyleExpr = errorStyleExpr;
    576     }
    577 
    578     /**
    579      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    580      * associated BeanInfo class.)
    581      */
    582     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    583         this.errorStyleClassExpr = errorStyleClassExpr;
    584     }
    585 
    586     /**
    587      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    588      * associated BeanInfo class.)
    589      */
    590     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    591         this.errorStyleIdExpr = errorStyleIdExpr;
    592     }
    593 
    594     /**
    595      * Setter method for "indexed" tag attribute. (Mapping set in associated
    596      * BeanInfo class.)
    597      */
    598     public void setIndexedExpr(String indexedExpr) {
    599         this.indexedExpr = indexedExpr;
    600     }
    601 
    602     /**
    603      * Setter method for "lang" tag attribute. (Mapping set in associated
    604      * BeanInfo class.)
    605      */
    606     public void setLangExpr(String langExpr) {
    607         this.langExpr = langExpr;
    608     }
    609 
    610     /**
    611      * Setter method for "name" tag attribute. (Mapping set in associated
    612      * BeanInfo class.)
    613      */
    614     public void setNameExpr(String nameExpr) {
    615         this.nameExpr = nameExpr;
    616     }
    617 
    618     /**
    619      * Setter method for "onblur" tag attribute. (Mapping set in associated
    620      * BeanInfo class.)
    621      */
    622     public void setOnblurExpr(String onblurExpr) {
    623         this.onblurExpr = onblurExpr;
    624     }
    625 
    626     /**
    627      * Setter method for "onchange" tag attribute. (Mapping set in associated
    628      * BeanInfo class.)
    629      */
    630     public void setOnchangeExpr(String onchangeExpr) {
    631         this.onchangeExpr = onchangeExpr;
    632     }
    633 
    634     /**
    635      * Setter method for "onclick" tag attribute. (Mapping set in associated
    636      * BeanInfo class.)
    637      */
    638     public void setOnclickExpr(String onclickExpr) {
    639         this.onclickExpr = onclickExpr;
    640     }
    641 
    642     /**
    643      * Setter method for "ondblclick" tag attribute. (Mapping set in
    644      * associated BeanInfo class.)
    645      */
    646     public void setOndblclickExpr(String ondblclickExpr) {
    647         this.ondblclickExpr = ondblclickExpr;
    648     }
    649 
    650     /**
    651      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    652      * BeanInfo class.)
    653      */
    654     public void setOnfocusExpr(String onfocusExpr) {
    655         this.onfocusExpr = onfocusExpr;
    656     }
    657 
    658     /**
    659      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    660      * BeanInfo class.)
    661      */
    662     public void setOnkeydownExpr(String onkeydownExpr) {
    663         this.onkeydownExpr = onkeydownExpr;
    664     }
    665 
    666     /**
    667      * Setter method for "onkeypress" tag attribute. (Mapping set in
    668      * associated BeanInfo class.)
    669      */
    670     public void setOnkeypressExpr(String onkeypressExpr) {
    671         this.onkeypressExpr = onkeypressExpr;
    672     }
    673 
    674     /**
    675      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    676      * BeanInfo class.)
    677      */
    678     public void setOnkeyupExpr(String onkeyupExpr) {
    679         this.onkeyupExpr = onkeyupExpr;
    680     }
    681 
    682     /**
    683      * Setter method for "onmousedown" tag attribute. (Mapping set in
    684      * associated BeanInfo class.)
    685      */
    686     public void setOnmousedownExpr(String onmousedownExpr) {
    687         this.onmousedownExpr = onmousedownExpr;
    688     }
    689 
    690     /**
    691      * Setter method for "onmousemove" tag attribute. (Mapping set in
    692      * associated BeanInfo class.)
    693      */
    694     public void setOnmousemoveExpr(String onmousemoveExpr) {
    695         this.onmousemoveExpr = onmousemoveExpr;
    696     }
    697 
    698     /**
    699      * Setter method for "onmouseout" tag attribute. (Mapping set in
    700      * associated BeanInfo class.)
    701      */
    702     public void setOnmouseoutExpr(String onmouseoutExpr) {
    703         this.onmouseoutExpr = onmouseoutExpr;
    704     }
    705 
    706     /**
    707      * Setter method for "onmouseover" tag attribute. (Mapping set in
    708      * associated BeanInfo class.)
    709      */
    710     public void setOnmouseoverExpr(String onmouseoverExpr) {
    711         this.onmouseoverExpr = onmouseoverExpr;
    712     }
    713 
    714     /**
    715      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    716      * BeanInfo class.)
    717      */
    718     public void setOnmouseupExpr(String onmouseupExpr) {
    719         this.onmouseupExpr = onmouseupExpr;
    720     }
    721 
    722     /**
    723      * Setter method for "property" tag attribute. (Mapping set in associated
    724      * BeanInfo class.)
    725      */
    726     public void setPropertyExpr(String propertyExpr) {
    727         this.propertyExpr = propertyExpr;
    728     }
    729 
    730     /**
    731      * Setter method for "style" tag attribute. (Mapping set in associated
    732      * BeanInfo class.)
    733      */
    734     public void setStyleExpr(String styleExpr) {
    735         this.styleExpr = styleExpr;
    736     }
    737 
    738     /**
    739      * Setter method for "styleClass" tag attribute. (Mapping set in
    740      * associated BeanInfo class.)
    741      */
    742     public void setStyleClassExpr(String styleClassExpr) {
    743         this.styleClassExpr = styleClassExpr;
    744     }
    745 
    746     /**
    747      * Setter method for "styleId" tag attribute. (Mapping set in associated
    748      * BeanInfo class.)
    749      */
    750     public void setStyleIdExpr(String styleIdExpr) {
    751         this.styleIdExpr = styleIdExpr;
    752     }
    753 
    754     /**
    755      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    756      * BeanInfo class.)
    757      */
    758     public void setTabindexExpr(String tabindexExpr) {
    759         this.tabindexExpr = tabindexExpr;
    760     }
    761 
    762     /**
    763      * Setter method for "title" tag attribute. (Mapping set in associated
    764      * BeanInfo class.)
    765      */
    766     public void setTitleExpr(String titleExpr) {
    767         this.titleExpr = titleExpr;
    768     }
    769 
    770     /**
    771      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    772      * BeanInfo class.)
    773      */
    774     public void setTitleKeyExpr(String titleKeyExpr) {
    775         this.titleKeyExpr = titleKeyExpr;
    776     }
    777 
    778     /**
    779      * Setter method for "value" tag attribute. (Mapping set in associated
    780      * BeanInfo class.)
    781      */
    782     public void setValueExpr(String valueExpr) {
    783         this.valueExpr = valueExpr;
    784     }
    785 
    786     /**
    787      * Resets attribute values for tag reuse.
    788      */
    789     public void release() {
    790         super.release();
    791         setAccesskeyExpr(null);
    792         setAltExpr(null);
    793         setAltKeyExpr(null);
    794         setBundleExpr(null);
    795         setDirExpr(null);
    796         setDisabledExpr(null);
    797         setErrorKeyExpr(null);
    798         setErrorStyleExpr(null);
    799         setErrorStyleClassExpr(null);
    800         setErrorStyleIdExpr(null);
    801         setIndexedExpr(null);
    802         setLangExpr(null);
    803         setNameExpr(null);
    804         setOnblurExpr(null);
    805         setOnchangeExpr(null);
    806         setOnclickExpr(null);
    807         setOndblclickExpr(null);
    808         setOnfocusExpr(null);
    809         setOnkeydownExpr(null);
    810         setOnkeypressExpr(null);
    811         setOnkeyupExpr(null);
    812         setOnmousedownExpr(null);
    813         setOnmousemoveExpr(null);
    814         setOnmouseoutExpr(null);
    815         setOnmouseoverExpr(null);
    816         setOnmouseupExpr(null);
    817         setPropertyExpr(null);
    818         setStyleExpr(null);
    819         setStyleClassExpr(null);
    820         setStyleIdExpr(null);
    821         setTabindexExpr(null);
    822         setTitleExpr(null);
    823         setTitleKeyExpr(null);
    824         setValueExpr(null);
    825     }
    826 
    827     /**
    828      * Process the start tag.
    829      *
    830      * @throws JspException if a JSP exception has occurred
    831      */
    832     public int doStartTag() throws JspException {
    833         evaluateExpressions();
    834 
    835         return (super.doStartTag());
    836     }
    837 
    838     /**
    839      * Processes all attribute values which use the JSTL expression evaluation
    840      * engine to determine their values.
    841      *
    842      * @throws JspException if a JSP exception has occurred
    843      */
    844     private void evaluateExpressions()
    845         throws JspException {
    846         String string = null;
    847         Boolean bool = null;
    848 
    849         if ((string =
    850                 EvalHelper.evalString("accesskey", getAccesskeyExpr(), this,
    851                     pageContext)) != null) {
    852             setAccesskey(string);
    853         }
    854 
    855         if ((string =
    856                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    857             setAlt(string);
    858         }
    859 
    860         if ((string =
    861                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    862                     pageContext)) != null) {
    863             setAltKey(string);
    864         }
    865 
    866         if ((string =
    867                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    868                     pageContext)) != null) {
    869             setBundle(string);
    870         }
    871 
    872         if ((string =
    873                  EvalHelper.evalString("dir", getDirExpr(), this,
    874                          pageContext)) != null) {
    875          setDir(string);
    876         }
    877         
    878         if ((bool =
    879                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    880                     pageContext)) != null) {
    881             setDisabled(bool.booleanValue());
    882         }
    883 
    884         if ((string =
    885                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    886                     pageContext)) != null) {
    887             setErrorKey(string);
    888         }
    889 
    890         if ((string =
    891                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    892                     pageContext)) != null) {
    893             setErrorStyle(string);
    894         }
    895 
    896         if ((string =
    897                 EvalHelper.evalString("errorStyleClass",
    898                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    899             setErrorStyleClass(string);
    900         }
    901 
    902         if ((string =
    903                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    904                     this, pageContext)) != null) {
    905             setErrorStyleId(string);
    906         }
    907 
    908         if ((bool =
    909                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    910                     pageContext)) != null) {
    911             setIndexed(bool.booleanValue());
    912         }
    913 
    914         if ((string =
    915                  EvalHelper.evalString("lang", getLangExpr(), this,
    916                          pageContext)) != null) {
    917          setLang(string);
    918         }
    919 
    920         if ((string =
    921                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    922             setName(string);
    923         }
    924 
    925         if ((string =
    926                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    927                     pageContext)) != null) {
    928             setOnblur(string);
    929         }
    930 
    931         if ((string =
    932                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    933                     pageContext)) != null) {
    934             setOnchange(string);
    935         }
    936 
    937         if ((string =
    938                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    939                     pageContext)) != null) {
    940             setOnclick(string);
    941         }
    942 
    943         if ((string =
    944                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    945                     pageContext)) != null) {
    946             setOndblclick(string);
    947         }
    948 
    949         if ((string =
    950                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    951                     pageContext)) != null) {
    952             setOnfocus(string);
    953         }
    954 
    955         if ((string =
    956                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    957                     pageContext)) != null) {
    958             setOnkeydown(string);
    959         }
    960 
    961         if ((string =
    962                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    963                     pageContext)) != null) {
    964             setOnkeypress(string);
    965         }
    966 
    967         if ((string =
    968                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    969                     pageContext)) != null) {
    970             setOnkeyup(string);
    971         }
    972 
    973         if ((string =
    974                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    975                     this, pageContext)) != null) {
    976             setOnmousedown(string);
    977         }
    978 
    979         if ((string =
    980                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    981                     this, pageContext)) != null) {
    982             setOnmousemove(string);
    983         }
    984 
    985         if ((string =
    986                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    987                     pageContext)) != null) {
    988             setOnmouseout(string);
    989         }
    990 
    991         if ((string =
    992                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    993                     this, pageContext)) != null) {
    994             setOnmouseover(string);
    995         }
    996 
    997         if ((string =
    998                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    999                     pageContext)) != null) {
    1000             setOnmouseup(string);
    1001         }
    1002 
    1003         if ((string =
    1004                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1005                     pageContext)) != null) {
    1006             setProperty(string);
    1007         }
    1008 
    1009         if ((string =
    1010                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1011             setStyle(string);
    1012         }
    1013 
    1014         if ((string =
    1015                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1016                     pageContext)) != null) {
    1017             setStyleClass(string);
    1018         }
    1019 
    1020         if ((string =
    1021                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1022                     pageContext)) != null) {
    1023             setStyleId(string);
    1024         }
    1025 
    1026         if ((string =
    1027                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1028                     pageContext)) != null) {
    1029             setTabindex(string);
    1030         }
    1031 
    1032         if ((string =
    1033                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1034             setTitle(string);
    1035         }
    1036 
    1037         if ((string =
    1038                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1039                     pageContext)) != null) {
    1040             setTitleKey(string);
    1041         }
    1042 
    1043         if ((string =
    1044                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1045             setValue(string);
    1046         }
    1047     }
    1048 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
