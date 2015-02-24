[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELTextTag.html)


    1   /*
    2    * $Id: ELTextTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.TextTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag for input fields of type "text". <p> This class is a subclass of
    30   * the class <code>org.apache.struts.taglib.html.md.TextTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELTextTag extends TextTag {
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
    111      * Instance variable mapped to "maxlength" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String maxlengthExpr;
    115 
    116     /**
    117      * Instance variable mapped to "name" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String nameExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onblurExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String onchangeExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    136      * associated BeanInfo class.)
    137      */
    138     private String onclickExpr;
    139 
    140     /**
    141      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     private String ondblclickExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    148      * associated BeanInfo class.)
    149      */
    150     private String onfocusExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onkeydownExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    160      * associated BeanInfo class.)
    161      */
    162     private String onkeypressExpr;
    163 
    164     /**
    165      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     private String onkeyupExpr;
    169 
    170     /**
    171      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    172      * in associated BeanInfo class.)
    173      */
    174     private String onmousedownExpr;
    175 
    176     /**
    177      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    178      * in associated BeanInfo class.)
    179      */
    180     private String onmousemoveExpr;
    181 
    182     /**
    183      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     private String onmouseoutExpr;
    187 
    188     /**
    189      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    190      * in associated BeanInfo class.)
    191      */
    192     private String onmouseoverExpr;
    193 
    194     /**
    195      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String onmouseupExpr;
    199 
    200     /**
    201      * Instance variable mapped to "onselect" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String onselectExpr;
    205 
    206     /**
    207      * Instance variable mapped to "property" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String propertyExpr;
    211 
    212     /**
    213      * Instance variable mapped to "readonly" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String readonlyExpr;
    217 
    218     /**
    219      * Instance variable mapped to "style" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String styleExpr;
    223 
    224     /**
    225      * Instance variable mapped to "size" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String sizeExpr;
    229 
    230     /**
    231      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    232      * associated BeanInfo class.)
    233      */
    234     private String styleClassExpr;
    235 
    236     /**
    237      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     private String styleIdExpr;
    241 
    242     /**
    243      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    244      * associated BeanInfo class.)
    245      */
    246     private String tabindexExpr;
    247 
    248     /**
    249      * Instance variable mapped to "title" tag attribute. (Mapping set in
    250      * associated BeanInfo class.)
    251      */
    252     private String titleExpr;
    253 
    254     /**
    255      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    256      * associated BeanInfo class.)
    257      */
    258     private String titleKeyExpr;
    259 
    260     /**
    261      * Instance variable mapped to "value" tag attribute. (Mapping set in
    262      * associated BeanInfo class.)
    263      */
    264     private String valueExpr;
    265 
    266     /**
    267      * Getter method for "accesskey" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public String getAccesskeyExpr() {
    271         return (accesskeyExpr);
    272     }
    273 
    274     /**
    275      * Getter method for "alt" tag attribute. (Mapping set in associated
    276      * BeanInfo class.)
    277      */
    278     public String getAltExpr() {
    279         return (altExpr);
    280     }
    281 
    282     /**
    283      * Getter method for "altKey" tag attribute. (Mapping set in associated
    284      * BeanInfo class.)
    285      */
    286     public String getAltKeyExpr() {
    287         return (altKeyExpr);
    288     }
    289 
    290     /**
    291      * Getter method for "bundle" tag attribute. (Mapping set in associated
    292      * BeanInfo class.)
    293      */
    294     public String getBundleExpr() {
    295         return (bundleExpr);
    296     }
    297 
    298     /**
    299      * Getter method for "dir" tag attribute. (Mapping set in associated
    300      * BeanInfo class.)
    301      */
    302     public String getDirExpr() {
    303         return (dirExpr);
    304     }
    305 
    306     /**
    307      * Getter method for "disabled" tag attribute. (Mapping set in associated
    308      * BeanInfo class.)
    309      */
    310     public String getDisabledExpr() {
    311         return (disabledExpr);
    312     }
    313 
    314     /**
    315      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    316      * BeanInfo class.)
    317      */
    318     public String getErrorKeyExpr() {
    319         return (errorKeyExpr);
    320     }
    321 
    322     /**
    323      * Getter method for "errorStyle" tag attribute. (Mapping set in
    324      * associated BeanInfo class.)
    325      */
    326     public String getErrorStyleExpr() {
    327         return (errorStyleExpr);
    328     }
    329 
    330     /**
    331      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    332      * associated BeanInfo class.)
    333      */
    334     public String getErrorStyleClassExpr() {
    335         return (errorStyleClassExpr);
    336     }
    337 
    338     /**
    339      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    340      * associated BeanInfo class.)
    341      */
    342     public String getErrorStyleIdExpr() {
    343         return (errorStyleIdExpr);
    344     }
    345 
    346     /**
    347      * Getter method for "indexed" tag attribute. (Mapping set in associated
    348      * BeanInfo class.)
    349      */
    350     public String getIndexedExpr() {
    351         return (indexedExpr);
    352     }
    353 
    354     /**
    355      * Getter method for "lang" tag attribute. (Mapping set in associated
    356      * BeanInfo class.)
    357      */
    358     public String getLangExpr() {
    359         return (langExpr);
    360     }
    361 
    362     /**
    363      * Getter method for "maxlength" tag attribute. (Mapping set in associated
    364      * BeanInfo class.)
    365      */
    366     public String getMaxlengthExpr() {
    367         return (maxlengthExpr);
    368     }
    369 
    370     /**
    371      * Getter method for "name" tag attribute. (Mapping set in associated
    372      * BeanInfo class.)
    373      */
    374     public String getNameExpr() {
    375         return (nameExpr);
    376     }
    377 
    378     /**
    379      * Getter method for "onblur" tag attribute. (Mapping set in associated
    380      * BeanInfo class.)
    381      */
    382     public String getOnblurExpr() {
    383         return (onblurExpr);
    384     }
    385 
    386     /**
    387      * Getter method for "onchange" tag attribute. (Mapping set in associated
    388      * BeanInfo class.)
    389      */
    390     public String getOnchangeExpr() {
    391         return (onchangeExpr);
    392     }
    393 
    394     /**
    395      * Getter method for "onclick" tag attribute. (Mapping set in associated
    396      * BeanInfo class.)
    397      */
    398     public String getOnclickExpr() {
    399         return (onclickExpr);
    400     }
    401 
    402     /**
    403      * Getter method for "ondblclick" tag attribute. (Mapping set in
    404      * associated BeanInfo class.)
    405      */
    406     public String getOndblclickExpr() {
    407         return (ondblclickExpr);
    408     }
    409 
    410     /**
    411      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    412      * BeanInfo class.)
    413      */
    414     public String getOnfocusExpr() {
    415         return (onfocusExpr);
    416     }
    417 
    418     /**
    419      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    420      * BeanInfo class.)
    421      */
    422     public String getOnkeydownExpr() {
    423         return (onkeydownExpr);
    424     }
    425 
    426     /**
    427      * Getter method for "onkeypress" tag attribute. (Mapping set in
    428      * associated BeanInfo class.)
    429      */
    430     public String getOnkeypressExpr() {
    431         return (onkeypressExpr);
    432     }
    433 
    434     /**
    435      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    436      * BeanInfo class.)
    437      */
    438     public String getOnkeyupExpr() {
    439         return (onkeyupExpr);
    440     }
    441 
    442     /**
    443      * Getter method for "onmousedown" tag attribute. (Mapping set in
    444      * associated BeanInfo class.)
    445      */
    446     public String getOnmousedownExpr() {
    447         return (onmousedownExpr);
    448     }
    449 
    450     /**
    451      * Getter method for "onmousemove" tag attribute. (Mapping set in
    452      * associated BeanInfo class.)
    453      */
    454     public String getOnmousemoveExpr() {
    455         return (onmousemoveExpr);
    456     }
    457 
    458     /**
    459      * Getter method for "onmouseout" tag attribute. (Mapping set in
    460      * associated BeanInfo class.)
    461      */
    462     public String getOnmouseoutExpr() {
    463         return (onmouseoutExpr);
    464     }
    465 
    466     /**
    467      * Getter method for "onmouseover" tag attribute. (Mapping set in
    468      * associated BeanInfo class.)
    469      */
    470     public String getOnmouseoverExpr() {
    471         return (onmouseoverExpr);
    472     }
    473 
    474     /**
    475      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    476      * BeanInfo class.)
    477      */
    478     public String getOnmouseupExpr() {
    479         return (onmouseupExpr);
    480     }
    481 
    482     /**
    483      * Getter method for "onselect" tag attribute. (Mapping set in associated
    484      * BeanInfo class.)
    485      */
    486     public String getOnselectExpr() {
    487         return (onselectExpr);
    488     }
    489 
    490     /**
    491      * Getter method for "property" tag attribute. (Mapping set in associated
    492      * BeanInfo class.)
    493      */
    494     public String getPropertyExpr() {
    495         return (propertyExpr);
    496     }
    497 
    498     /**
    499      * Getter method for "readonly" tag attribute. (Mapping set in associated
    500      * BeanInfo class.)
    501      */
    502     public String getReadonlyExpr() {
    503         return (readonlyExpr);
    504     }
    505 
    506     /**
    507      * Getter method for "style" tag attribute. (Mapping set in associated
    508      * BeanInfo class.)
    509      */
    510     public String getStyleExpr() {
    511         return (styleExpr);
    512     }
    513 
    514     /**
    515      * Getter method for "size" tag attribute. (Mapping set in associated
    516      * BeanInfo class.)
    517      */
    518     public String getSizeExpr() {
    519         return (sizeExpr);
    520     }
    521 
    522     /**
    523      * Getter method for "styleClass" tag attribute. (Mapping set in
    524      * associated BeanInfo class.)
    525      */
    526     public String getStyleClassExpr() {
    527         return (styleClassExpr);
    528     }
    529 
    530     /**
    531      * Getter method for "styleId" tag attribute. (Mapping set in associated
    532      * BeanInfo class.)
    533      */
    534     public String getStyleIdExpr() {
    535         return (styleIdExpr);
    536     }
    537 
    538     /**
    539      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    540      * BeanInfo class.)
    541      */
    542     public String getTabindexExpr() {
    543         return (tabindexExpr);
    544     }
    545 
    546     /**
    547      * Getter method for "title" tag attribute. (Mapping set in associated
    548      * BeanInfo class.)
    549      */
    550     public String getTitleExpr() {
    551         return (titleExpr);
    552     }
    553 
    554     /**
    555      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    556      * BeanInfo class.)
    557      */
    558     public String getTitleKeyExpr() {
    559         return (titleKeyExpr);
    560     }
    561 
    562     /**
    563      * Getter method for "value" tag attribute. (Mapping set in associated
    564      * BeanInfo class.)
    565      */
    566     public String getValueExpr() {
    567         return (valueExpr);
    568     }
    569 
    570     /**
    571      * Setter method for "accesskey" tag attribute. (Mapping set in associated
    572      * BeanInfo class.)
    573      */
    574     public void setAccesskeyExpr(String accesskeyExpr) {
    575         this.accesskeyExpr = accesskeyExpr;
    576     }
    577 
    578     /**
    579      * Setter method for "alt" tag attribute. (Mapping set in associated
    580      * BeanInfo class.)
    581      */
    582     public void setAltExpr(String altExpr) {
    583         this.altExpr = altExpr;
    584     }
    585 
    586     /**
    587      * Setter method for "altKey" tag attribute. (Mapping set in associated
    588      * BeanInfo class.)
    589      */
    590     public void setAltKeyExpr(String altKeyExpr) {
    591         this.altKeyExpr = altKeyExpr;
    592     }
    593 
    594     /**
    595      * Setter method for "bundle" tag attribute. (Mapping set in associated
    596      * BeanInfo class.)
    597      */
    598     public void setBundleExpr(String bundleExpr) {
    599         this.bundleExpr = bundleExpr;
    600     }
    601 
    602     /**
    603      * Setter method for "dir" tag attribute. (Mapping set in associated
    604      * BeanInfo class.)
    605      */
    606     public void setDirExpr(String dirExpr) {
    607         this.dirExpr = dirExpr;
    608     }
    609 
    610     /**
    611      * Setter method for "disabled" tag attribute. (Mapping set in associated
    612      * BeanInfo class.)
    613      */
    614     public void setDisabledExpr(String disabledExpr) {
    615         this.disabledExpr = disabledExpr;
    616     }
    617 
    618     /**
    619      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    620      * BeanInfo class.)
    621      */
    622     public void setErrorKeyExpr(String errorKeyExpr) {
    623         this.errorKeyExpr = errorKeyExpr;
    624     }
    625 
    626     /**
    627      * Setter method for "errorStyle" tag attribute. (Mapping set in
    628      * associated BeanInfo class.)
    629      */
    630     public void setErrorStyleExpr(String errorStyleExpr) {
    631         this.errorStyleExpr = errorStyleExpr;
    632     }
    633 
    634     /**
    635      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    636      * associated BeanInfo class.)
    637      */
    638     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    639         this.errorStyleClassExpr = errorStyleClassExpr;
    640     }
    641 
    642     /**
    643      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    644      * associated BeanInfo class.)
    645      */
    646     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    647         this.errorStyleIdExpr = errorStyleIdExpr;
    648     }
    649 
    650     /**
    651      * Setter method for "indexed" tag attribute. (Mapping set in associated
    652      * BeanInfo class.)
    653      */
    654     public void setIndexedExpr(String indexedExpr) {
    655         this.indexedExpr = indexedExpr;
    656     }
    657 
    658     /**
    659      * Setter method for "lang" tag attribute. (Mapping set in associated
    660      * BeanInfo class.)
    661      */
    662     public void setLangExpr(String langExpr) {
    663         this.langExpr = langExpr;
    664     }
    665 
    666     /**
    667      * Setter method for "maxlength" tag attribute. (Mapping set in associated
    668      * BeanInfo class.)
    669      */
    670     public void setMaxlengthExpr(String maxlengthExpr) {
    671         this.maxlengthExpr = maxlengthExpr;
    672     }
    673 
    674     /**
    675      * Setter method for "name" tag attribute. (Mapping set in associated
    676      * BeanInfo class.)
    677      */
    678     public void setNameExpr(String nameExpr) {
    679         this.nameExpr = nameExpr;
    680     }
    681 
    682     /**
    683      * Setter method for "onblur" tag attribute. (Mapping set in associated
    684      * BeanInfo class.)
    685      */
    686     public void setOnblurExpr(String onblurExpr) {
    687         this.onblurExpr = onblurExpr;
    688     }
    689 
    690     /**
    691      * Setter method for "onchange" tag attribute. (Mapping set in associated
    692      * BeanInfo class.)
    693      */
    694     public void setOnchangeExpr(String onchangeExpr) {
    695         this.onchangeExpr = onchangeExpr;
    696     }
    697 
    698     /**
    699      * Setter method for "onclick" tag attribute. (Mapping set in associated
    700      * BeanInfo class.)
    701      */
    702     public void setOnclickExpr(String onclickExpr) {
    703         this.onclickExpr = onclickExpr;
    704     }
    705 
    706     /**
    707      * Setter method for "ondblclick" tag attribute. (Mapping set in
    708      * associated BeanInfo class.)
    709      */
    710     public void setOndblclickExpr(String ondblclickExpr) {
    711         this.ondblclickExpr = ondblclickExpr;
    712     }
    713 
    714     /**
    715      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    716      * BeanInfo class.)
    717      */
    718     public void setOnfocusExpr(String onfocusExpr) {
    719         this.onfocusExpr = onfocusExpr;
    720     }
    721 
    722     /**
    723      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    724      * BeanInfo class.)
    725      */
    726     public void setOnkeydownExpr(String onkeydownExpr) {
    727         this.onkeydownExpr = onkeydownExpr;
    728     }
    729 
    730     /**
    731      * Setter method for "onkeypress" tag attribute. (Mapping set in
    732      * associated BeanInfo class.)
    733      */
    734     public void setOnkeypressExpr(String onkeypressExpr) {
    735         this.onkeypressExpr = onkeypressExpr;
    736     }
    737 
    738     /**
    739      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    740      * BeanInfo class.)
    741      */
    742     public void setOnkeyupExpr(String onkeyupExpr) {
    743         this.onkeyupExpr = onkeyupExpr;
    744     }
    745 
    746     /**
    747      * Setter method for "onmousedown" tag attribute. (Mapping set in
    748      * associated BeanInfo class.)
    749      */
    750     public void setOnmousedownExpr(String onmousedownExpr) {
    751         this.onmousedownExpr = onmousedownExpr;
    752     }
    753 
    754     /**
    755      * Setter method for "onmousemove" tag attribute. (Mapping set in
    756      * associated BeanInfo class.)
    757      */
    758     public void setOnmousemoveExpr(String onmousemoveExpr) {
    759         this.onmousemoveExpr = onmousemoveExpr;
    760     }
    761 
    762     /**
    763      * Setter method for "onmouseout" tag attribute. (Mapping set in
    764      * associated BeanInfo class.)
    765      */
    766     public void setOnmouseoutExpr(String onmouseoutExpr) {
    767         this.onmouseoutExpr = onmouseoutExpr;
    768     }
    769 
    770     /**
    771      * Setter method for "onmouseover" tag attribute. (Mapping set in
    772      * associated BeanInfo class.)
    773      */
    774     public void setOnmouseoverExpr(String onmouseoverExpr) {
    775         this.onmouseoverExpr = onmouseoverExpr;
    776     }
    777 
    778     /**
    779      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    780      * BeanInfo class.)
    781      */
    782     public void setOnmouseupExpr(String onmouseupExpr) {
    783         this.onmouseupExpr = onmouseupExpr;
    784     }
    785 
    786     /**
    787      * Setter method for "onselect" tag attribute. (Mapping set in associated
    788      * BeanInfo class.)
    789      */
    790     public void setOnselectExpr(String onselectExpr) {
    791         this.onselectExpr = onselectExpr;
    792     }
    793 
    794     /**
    795      * Setter method for "property" tag attribute. (Mapping set in associated
    796      * BeanInfo class.)
    797      */
    798     public void setPropertyExpr(String propertyExpr) {
    799         this.propertyExpr = propertyExpr;
    800     }
    801 
    802     /**
    803      * Setter method for "readonly" tag attribute. (Mapping set in associated
    804      * BeanInfo class.)
    805      */
    806     public void setReadonlyExpr(String readonlyExpr) {
    807         this.readonlyExpr = readonlyExpr;
    808     }
    809 
    810     /**
    811      * Setter method for "style" tag attribute. (Mapping set in associated
    812      * BeanInfo class.)
    813      */
    814     public void setStyleExpr(String styleExpr) {
    815         this.styleExpr = styleExpr;
    816     }
    817 
    818     /**
    819      * Setter method for "size" tag attribute. (Mapping set in associated
    820      * BeanInfo class.)
    821      */
    822     public void setSizeExpr(String sizeExpr) {
    823         this.sizeExpr = sizeExpr;
    824     }
    825 
    826     /**
    827      * Setter method for "styleClass" tag attribute. (Mapping set in
    828      * associated BeanInfo class.)
    829      */
    830     public void setStyleClassExpr(String styleClassExpr) {
    831         this.styleClassExpr = styleClassExpr;
    832     }
    833 
    834     /**
    835      * Setter method for "styleId" tag attribute. (Mapping set in associated
    836      * BeanInfo class.)
    837      */
    838     public void setStyleIdExpr(String styleIdExpr) {
    839         this.styleIdExpr = styleIdExpr;
    840     }
    841 
    842     /**
    843      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    844      * BeanInfo class.)
    845      */
    846     public void setTabindexExpr(String tabindexExpr) {
    847         this.tabindexExpr = tabindexExpr;
    848     }
    849 
    850     /**
    851      * Setter method for "title" tag attribute. (Mapping set in associated
    852      * BeanInfo class.)
    853      */
    854     public void setTitleExpr(String titleExpr) {
    855         this.titleExpr = titleExpr;
    856     }
    857 
    858     /**
    859      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    860      * BeanInfo class.)
    861      */
    862     public void setTitleKeyExpr(String titleKeyExpr) {
    863         this.titleKeyExpr = titleKeyExpr;
    864     }
    865 
    866     /**
    867      * Setter method for "value" tag attribute. (Mapping set in associated
    868      * BeanInfo class.)
    869      */
    870     public void setValueExpr(String valueExpr) {
    871         this.valueExpr = valueExpr;
    872     }
    873 
    874     /**
    875      * Resets attribute values for tag reuse.
    876      */
    877     public void release() {
    878         super.release();
    879         setAccesskeyExpr(null);
    880         setAltExpr(null);
    881         setAltKeyExpr(null);
    882         setBundleExpr(null);
    883         setDirExpr(null);
    884         setDisabledExpr(null);
    885         setErrorKeyExpr(null);
    886         setErrorStyleExpr(null);
    887         setErrorStyleClassExpr(null);
    888         setErrorStyleIdExpr(null);
    889         setIndexedExpr(null);
    890         setLangExpr(null);
    891         setMaxlengthExpr(null);
    892         setNameExpr(null);
    893         setOnblurExpr(null);
    894         setOnchangeExpr(null);
    895         setOnclickExpr(null);
    896         setOndblclickExpr(null);
    897         setOnfocusExpr(null);
    898         setOnkeydownExpr(null);
    899         setOnkeypressExpr(null);
    900         setOnkeyupExpr(null);
    901         setOnmousedownExpr(null);
    902         setOnmousemoveExpr(null);
    903         setOnmouseoutExpr(null);
    904         setOnmouseoverExpr(null);
    905         setOnmouseupExpr(null);
    906         setOnselectExpr(null);
    907         setPropertyExpr(null);
    908         setReadonlyExpr(null);
    909         setStyleExpr(null);
    910         setSizeExpr(null);
    911         setStyleClassExpr(null);
    912         setStyleIdExpr(null);
    913         setTabindexExpr(null);
    914         setTitleExpr(null);
    915         setTitleKeyExpr(null);
    916         setValueExpr(null);
    917     }
    918 
    919     /**
    920      * Process the start tag.
    921      *
    922      * @throws JspException if a JSP exception has occurred
    923      */
    924     public int doStartTag() throws JspException {
    925         evaluateExpressions();
    926 
    927         return (super.doStartTag());
    928     }
    929 
    930     /**
    931      * Processes all attribute values which use the JSTL expression evaluation
    932      * engine to determine their values.
    933      *
    934      * @throws JspException if a JSP exception has occurred
    935      */
    936     private void evaluateExpressions()
    937         throws JspException {
    938         String string = null;
    939         Boolean bool = null;
    940 
    941         if ((string =
    942                 EvalHelper.evalString("accesskey", getAccesskeyExpr(), this,
    943                     pageContext)) != null) {
    944             setAccesskey(string);
    945         }
    946 
    947         if ((string =
    948                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    949             setAlt(string);
    950         }
    951 
    952         if ((string =
    953                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    954                     pageContext)) != null) {
    955             setAltKey(string);
    956         }
    957 
    958         if ((string =
    959                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    960                     pageContext)) != null) {
    961             setBundle(string);
    962         }
    963 
    964         if ((string =
    965                  EvalHelper.evalString("dir", getDirExpr(), this,
    966                          pageContext)) != null) {
    967          setDir(string);
    968         }
    969         
    970         if ((bool =
    971                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    972                     pageContext)) != null) {
    973             setDisabled(bool.booleanValue());
    974         }
    975 
    976         if ((string =
    977                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    978                     pageContext)) != null) {
    979             setErrorKey(string);
    980         }
    981 
    982         if ((string =
    983                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    984                     pageContext)) != null) {
    985             setErrorStyle(string);
    986         }
    987 
    988         if ((string =
    989                 EvalHelper.evalString("errorStyleClass",
    990                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    991             setErrorStyleClass(string);
    992         }
    993 
    994         if ((string =
    995                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    996                     this, pageContext)) != null) {
    997             setErrorStyleId(string);
    998         }
    999 
    1000         if ((bool =
    1001                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    1002                     pageContext)) != null) {
    1003             setIndexed(bool.booleanValue());
    1004         }
    1005 
    1006         if ((string =
    1007               EvalHelper.evalString("lang", getLangExpr(), this,
    1008                       pageContext)) != null) {
    1009               setLang(string);
    1010         }
    1011 
    1012         if ((string =
    1013                 EvalHelper.evalString("maxlength", getMaxlengthExpr(), this,
    1014                     pageContext)) != null) {
    1015             setMaxlength(string);
    1016         }
    1017 
    1018         if ((string =
    1019                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    1020             setName(string);
    1021         }
    1022 
    1023         if ((string =
    1024                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    1025                     pageContext)) != null) {
    1026             setOnblur(string);
    1027         }
    1028 
    1029         if ((string =
    1030                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    1031                     pageContext)) != null) {
    1032             setOnchange(string);
    1033         }
    1034 
    1035         if ((string =
    1036                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1037                     pageContext)) != null) {
    1038             setOnclick(string);
    1039         }
    1040 
    1041         if ((string =
    1042                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1043                     pageContext)) != null) {
    1044             setOndblclick(string);
    1045         }
    1046 
    1047         if ((string =
    1048                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    1049                     pageContext)) != null) {
    1050             setOnfocus(string);
    1051         }
    1052 
    1053         if ((string =
    1054                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1055                     pageContext)) != null) {
    1056             setOnkeydown(string);
    1057         }
    1058 
    1059         if ((string =
    1060                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1061                     pageContext)) != null) {
    1062             setOnkeypress(string);
    1063         }
    1064 
    1065         if ((string =
    1066                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1067                     pageContext)) != null) {
    1068             setOnkeyup(string);
    1069         }
    1070 
    1071         if ((string =
    1072                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1073                     this, pageContext)) != null) {
    1074             setOnmousedown(string);
    1075         }
    1076 
    1077         if ((string =
    1078                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1079                     this, pageContext)) != null) {
    1080             setOnmousemove(string);
    1081         }
    1082 
    1083         if ((string =
    1084                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1085                     pageContext)) != null) {
    1086             setOnmouseout(string);
    1087         }
    1088 
    1089         if ((string =
    1090                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1091                     this, pageContext)) != null) {
    1092             setOnmouseover(string);
    1093         }
    1094 
    1095         if ((string =
    1096                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1097                     pageContext)) != null) {
    1098             setOnmouseup(string);
    1099         }
    1100 
    1101         if ((string =
    1102                 EvalHelper.evalString("onselect", getOnselectExpr(), this,
    1103                     pageContext)) != null) {
    1104             setOnselect(string);
    1105         }
    1106 
    1107         if ((string =
    1108                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1109                     pageContext)) != null) {
    1110             setProperty(string);
    1111         }
    1112 
    1113         if ((bool =
    1114                 EvalHelper.evalBoolean("readonly", getReadonlyExpr(), this,
    1115                     pageContext)) != null) {
    1116             setReadonly(bool.booleanValue());
    1117         }
    1118 
    1119         if ((string =
    1120                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1121             setStyle(string);
    1122         }
    1123 
    1124         if ((string =
    1125                 EvalHelper.evalString("size", getSizeExpr(), this, pageContext)) != null) {
    1126             setSize(string);
    1127         }
    1128 
    1129         if ((string =
    1130                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1131                     pageContext)) != null) {
    1132             setStyleClass(string);
    1133         }
    1134 
    1135         if ((string =
    1136                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1137                     pageContext)) != null) {
    1138             setStyleId(string);
    1139         }
    1140 
    1141         if ((string =
    1142                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1143                     pageContext)) != null) {
    1144             setTabindex(string);
    1145         }
    1146 
    1147         if ((string =
    1148                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1149             setTitle(string);
    1150         }
    1151 
    1152         if ((string =
    1153                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1154                     pageContext)) != null) {
    1155             setTitleKey(string);
    1156         }
    1157 
    1158         if ((string =
    1159                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1160             setValue(string);
    1161         }
    1162     }
    1163 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
