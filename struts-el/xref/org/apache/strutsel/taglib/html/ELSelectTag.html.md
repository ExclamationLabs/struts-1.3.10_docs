[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELSelectTag.html)


    1   /*
    2    * $Id: ELSelectTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.SelectTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that represents an HTML select element, associated with a bean
    30   * property specified by our attributes.  This tag must be nested inside a
    31   * form tag. <p> This class is a subclass of the class
    32   * <code>org.apache.struts.taglib.html.md.SelectTag</code> which provides most of
    33   * the described functionality.  This subclass allows all attribute values to
    34   * be specified as expressions utilizing the JavaServer Pages Standard Library
    35   * expression language.
    36   *
    37   * @version $Rev: 479635 $
    38   */
    39  public class ELSelectTag extends SelectTag {
    40      /**
    41       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String altExpr;
    45  
    46      /**
    47       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    48       * associated BeanInfo class.)
    49       */
    50      private String altKeyExpr;
    51  
    52      /**
    53       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String bundleExpr;
    57  
    58      /**
    59       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String dirExpr;
    63  
    64      /**
    65       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String disabledExpr;
    69  
    70      /**
    71       * Instance variable mapped to "errorKey" tag attribute. (Mapping set in
    72       * associated BeanInfo class.)
    73       */
    74      private String errorKeyExpr;
    75  
    76      /**
    77       * Instance variable mapped to "errorStyle" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String errorStyleExpr;
    81  
    82      /**
    83       * Instance variable mapped to "errorStyleClass" tag attribute. (Mapping
    84       * set in associated BeanInfo class.)
    85       */
    86      private String errorStyleClassExpr;
    87  
    88      /**
    89       * Instance variable mapped to "errorStyleId" tag attribute. (Mapping set
    90       * in associated BeanInfo class.)
    91       */
    92      private String errorStyleIdExpr;
    93  
    94      /**
    95       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String indexedExpr;
    99  
    100     /**
    101      * Instance variable mapped to "lang" tag attribute. (Mapping set in
    102      * associated BeanInfo class.)
    103      */
    104     private String langExpr;
    105 
    106     /**
    107      * Instance variable mapped to "multiple" tag attribute. (Mapping set in
    108      * associated BeanInfo class.)
    109      */
    110     private String multipleExpr;
    111 
    112     /**
    113      * Instance variable mapped to "name" tag attribute. (Mapping set in
    114      * associated BeanInfo class.)
    115      */
    116     private String nameExpr;
    117 
    118     /**
    119      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    120      * associated BeanInfo class.)
    121      */
    122     private String onblurExpr;
    123 
    124     /**
    125      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    126      * associated BeanInfo class.)
    127      */
    128     private String onchangeExpr;
    129 
    130     /**
    131      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    132      * associated BeanInfo class.)
    133      */
    134     private String onclickExpr;
    135 
    136     /**
    137      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    138      * associated BeanInfo class.)
    139      */
    140     private String ondblclickExpr;
    141 
    142     /**
    143      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    144      * associated BeanInfo class.)
    145      */
    146     private String onfocusExpr;
    147 
    148     /**
    149      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    150      * associated BeanInfo class.)
    151      */
    152     private String onkeydownExpr;
    153 
    154     /**
    155      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    156      * associated BeanInfo class.)
    157      */
    158     private String onkeypressExpr;
    159 
    160     /**
    161      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    162      * associated BeanInfo class.)
    163      */
    164     private String onkeyupExpr;
    165 
    166     /**
    167      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    168      * in associated BeanInfo class.)
    169      */
    170     private String onmousedownExpr;
    171 
    172     /**
    173      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    174      * in associated BeanInfo class.)
    175      */
    176     private String onmousemoveExpr;
    177 
    178     /**
    179      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    180      * associated BeanInfo class.)
    181      */
    182     private String onmouseoutExpr;
    183 
    184     /**
    185      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    186      * in associated BeanInfo class.)
    187      */
    188     private String onmouseoverExpr;
    189 
    190     /**
    191      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    192      * associated BeanInfo class.)
    193      */
    194     private String onmouseupExpr;
    195 
    196     /**
    197      * Instance variable mapped to "property" tag attribute. (Mapping set in
    198      * associated BeanInfo class.)
    199      */
    200     private String propertyExpr;
    201 
    202     /**
    203      * Instance variable mapped to "size" tag attribute. (Mapping set in
    204      * associated BeanInfo class.)
    205      */
    206     private String sizeExpr;
    207 
    208     /**
    209      * Instance variable mapped to "style" tag attribute. (Mapping set in
    210      * associated BeanInfo class.)
    211      */
    212     private String styleExpr;
    213 
    214     /**
    215      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    216      * associated BeanInfo class.)
    217      */
    218     private String styleClassExpr;
    219 
    220     /**
    221      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    222      * associated BeanInfo class.)
    223      */
    224     private String styleIdExpr;
    225 
    226     /**
    227      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    228      * associated BeanInfo class.)
    229      */
    230     private String tabindexExpr;
    231 
    232     /**
    233      * Instance variable mapped to "title" tag attribute. (Mapping set in
    234      * associated BeanInfo class.)
    235      */
    236     private String titleExpr;
    237 
    238     /**
    239      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    240      * associated BeanInfo class.)
    241      */
    242     private String titleKeyExpr;
    243 
    244     /**
    245      * Instance variable mapped to "value" tag attribute. (Mapping set in
    246      * associated BeanInfo class.)
    247      */
    248     private String valueExpr;
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
    339      * Getter method for "multiple" tag attribute. (Mapping set in associated
    340      * BeanInfo class.)
    341      */
    342     public String getMultipleExpr() {
    343         return (multipleExpr);
    344     }
    345 
    346     /**
    347      * Getter method for "name" tag attribute. (Mapping set in associated
    348      * BeanInfo class.)
    349      */
    350     public String getNameExpr() {
    351         return (nameExpr);
    352     }
    353 
    354     /**
    355      * Getter method for "onblur" tag attribute. (Mapping set in associated
    356      * BeanInfo class.)
    357      */
    358     public String getOnblurExpr() {
    359         return (onblurExpr);
    360     }
    361 
    362     /**
    363      * Getter method for "onchange" tag attribute. (Mapping set in associated
    364      * BeanInfo class.)
    365      */
    366     public String getOnchangeExpr() {
    367         return (onchangeExpr);
    368     }
    369 
    370     /**
    371      * Getter method for "onclick" tag attribute. (Mapping set in associated
    372      * BeanInfo class.)
    373      */
    374     public String getOnclickExpr() {
    375         return (onclickExpr);
    376     }
    377 
    378     /**
    379      * Getter method for "ondblclick" tag attribute. (Mapping set in
    380      * associated BeanInfo class.)
    381      */
    382     public String getOndblclickExpr() {
    383         return (ondblclickExpr);
    384     }
    385 
    386     /**
    387      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    388      * BeanInfo class.)
    389      */
    390     public String getOnfocusExpr() {
    391         return (onfocusExpr);
    392     }
    393 
    394     /**
    395      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    396      * BeanInfo class.)
    397      */
    398     public String getOnkeydownExpr() {
    399         return (onkeydownExpr);
    400     }
    401 
    402     /**
    403      * Getter method for "onkeypress" tag attribute. (Mapping set in
    404      * associated BeanInfo class.)
    405      */
    406     public String getOnkeypressExpr() {
    407         return (onkeypressExpr);
    408     }
    409 
    410     /**
    411      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    412      * BeanInfo class.)
    413      */
    414     public String getOnkeyupExpr() {
    415         return (onkeyupExpr);
    416     }
    417 
    418     /**
    419      * Getter method for "onmousedown" tag attribute. (Mapping set in
    420      * associated BeanInfo class.)
    421      */
    422     public String getOnmousedownExpr() {
    423         return (onmousedownExpr);
    424     }
    425 
    426     /**
    427      * Getter method for "onmousemove" tag attribute. (Mapping set in
    428      * associated BeanInfo class.)
    429      */
    430     public String getOnmousemoveExpr() {
    431         return (onmousemoveExpr);
    432     }
    433 
    434     /**
    435      * Getter method for "onmouseout" tag attribute. (Mapping set in
    436      * associated BeanInfo class.)
    437      */
    438     public String getOnmouseoutExpr() {
    439         return (onmouseoutExpr);
    440     }
    441 
    442     /**
    443      * Getter method for "onmouseover" tag attribute. (Mapping set in
    444      * associated BeanInfo class.)
    445      */
    446     public String getOnmouseoverExpr() {
    447         return (onmouseoverExpr);
    448     }
    449 
    450     /**
    451      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    452      * BeanInfo class.)
    453      */
    454     public String getOnmouseupExpr() {
    455         return (onmouseupExpr);
    456     }
    457 
    458     /**
    459      * Getter method for "property" tag attribute. (Mapping set in associated
    460      * BeanInfo class.)
    461      */
    462     public String getPropertyExpr() {
    463         return (propertyExpr);
    464     }
    465 
    466     /**
    467      * Getter method for "size" tag attribute. (Mapping set in associated
    468      * BeanInfo class.)
    469      */
    470     public String getSizeExpr() {
    471         return (sizeExpr);
    472     }
    473 
    474     /**
    475      * Getter method for "style" tag attribute. (Mapping set in associated
    476      * BeanInfo class.)
    477      */
    478     public String getStyleExpr() {
    479         return (styleExpr);
    480     }
    481 
    482     /**
    483      * Getter method for "styleClass" tag attribute. (Mapping set in
    484      * associated BeanInfo class.)
    485      */
    486     public String getStyleClassExpr() {
    487         return (styleClassExpr);
    488     }
    489 
    490     /**
    491      * Getter method for "styleId" tag attribute. (Mapping set in associated
    492      * BeanInfo class.)
    493      */
    494     public String getStyleIdExpr() {
    495         return (styleIdExpr);
    496     }
    497 
    498     /**
    499      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    500      * BeanInfo class.)
    501      */
    502     public String getTabindexExpr() {
    503         return (tabindexExpr);
    504     }
    505 
    506     /**
    507      * Getter method for "title" tag attribute. (Mapping set in associated
    508      * BeanInfo class.)
    509      */
    510     public String getTitleExpr() {
    511         return (titleExpr);
    512     }
    513 
    514     /**
    515      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    516      * BeanInfo class.)
    517      */
    518     public String getTitleKeyExpr() {
    519         return (titleKeyExpr);
    520     }
    521 
    522     /**
    523      * Getter method for "value" tag attribute. (Mapping set in associated
    524      * BeanInfo class.)
    525      */
    526     public String getValueExpr() {
    527         return (valueExpr);
    528     }
    529 
    530     /**
    531      * Setter method for "alt" tag attribute. (Mapping set in associated
    532      * BeanInfo class.)
    533      */
    534     public void setAltExpr(String altExpr) {
    535         this.altExpr = altExpr;
    536     }
    537 
    538     /**
    539      * Setter method for "altKey" tag attribute. (Mapping set in associated
    540      * BeanInfo class.)
    541      */
    542     public void setAltKeyExpr(String altKeyExpr) {
    543         this.altKeyExpr = altKeyExpr;
    544     }
    545 
    546     /**
    547      * Setter method for "bundle" tag attribute. (Mapping set in associated
    548      * BeanInfo class.)
    549      */
    550     public void setBundleExpr(String bundleExpr) {
    551         this.bundleExpr = bundleExpr;
    552     }
    553 
    554     /**
    555      * Setter method for "dir" tag attribute. (Mapping set in associated
    556      * BeanInfo class.)
    557      */
    558     public void setDirExpr(String dirExpr) {
    559         this.dirExpr = dirExpr;
    560     }
    561 
    562     /**
    563      * Setter method for "disabled" tag attribute. (Mapping set in associated
    564      * BeanInfo class.)
    565      */
    566     public void setDisabledExpr(String disabledExpr) {
    567         this.disabledExpr = disabledExpr;
    568     }
    569 
    570     /**
    571      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    572      * BeanInfo class.)
    573      */
    574     public void setErrorKeyExpr(String errorKeyExpr) {
    575         this.errorKeyExpr = errorKeyExpr;
    576     }
    577 
    578     /**
    579      * Setter method for "errorStyle" tag attribute. (Mapping set in
    580      * associated BeanInfo class.)
    581      */
    582     public void setErrorStyleExpr(String errorStyleExpr) {
    583         this.errorStyleExpr = errorStyleExpr;
    584     }
    585 
    586     /**
    587      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    588      * associated BeanInfo class.)
    589      */
    590     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    591         this.errorStyleClassExpr = errorStyleClassExpr;
    592     }
    593 
    594     /**
    595      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    596      * associated BeanInfo class.)
    597      */
    598     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    599         this.errorStyleIdExpr = errorStyleIdExpr;
    600     }
    601 
    602     /**
    603      * Setter method for "indexed" tag attribute. (Mapping set in associated
    604      * BeanInfo class.)
    605      */
    606     public void setIndexedExpr(String indexedExpr) {
    607         this.indexedExpr = indexedExpr;
    608     }
    609 
    610     /**
    611      * Setter method for "lang" tag attribute. (Mapping set in associated
    612      * BeanInfo class.)
    613      */
    614     public void setLangExpr(String langExpr) {
    615         this.langExpr = langExpr;
    616     }
    617 
    618     /**
    619      * Setter method for "multiple" tag attribute. (Mapping set in associated
    620      * BeanInfo class.)
    621      */
    622     public void setMultipleExpr(String multipleExpr) {
    623         this.multipleExpr = multipleExpr;
    624     }
    625 
    626     /**
    627      * Setter method for "name" tag attribute. (Mapping set in associated
    628      * BeanInfo class.)
    629      */
    630     public void setNameExpr(String nameExpr) {
    631         this.nameExpr = nameExpr;
    632     }
    633 
    634     /**
    635      * Setter method for "onblur" tag attribute. (Mapping set in associated
    636      * BeanInfo class.)
    637      */
    638     public void setOnblurExpr(String onblurExpr) {
    639         this.onblurExpr = onblurExpr;
    640     }
    641 
    642     /**
    643      * Setter method for "onchange" tag attribute. (Mapping set in associated
    644      * BeanInfo class.)
    645      */
    646     public void setOnchangeExpr(String onchangeExpr) {
    647         this.onchangeExpr = onchangeExpr;
    648     }
    649 
    650     /**
    651      * Setter method for "onclick" tag attribute. (Mapping set in associated
    652      * BeanInfo class.)
    653      */
    654     public void setOnclickExpr(String onclickExpr) {
    655         this.onclickExpr = onclickExpr;
    656     }
    657 
    658     /**
    659      * Setter method for "ondblclick" tag attribute. (Mapping set in
    660      * associated BeanInfo class.)
    661      */
    662     public void setOndblclickExpr(String ondblclickExpr) {
    663         this.ondblclickExpr = ondblclickExpr;
    664     }
    665 
    666     /**
    667      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    668      * BeanInfo class.)
    669      */
    670     public void setOnfocusExpr(String onfocusExpr) {
    671         this.onfocusExpr = onfocusExpr;
    672     }
    673 
    674     /**
    675      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    676      * BeanInfo class.)
    677      */
    678     public void setOnkeydownExpr(String onkeydownExpr) {
    679         this.onkeydownExpr = onkeydownExpr;
    680     }
    681 
    682     /**
    683      * Setter method for "onkeypress" tag attribute. (Mapping set in
    684      * associated BeanInfo class.)
    685      */
    686     public void setOnkeypressExpr(String onkeypressExpr) {
    687         this.onkeypressExpr = onkeypressExpr;
    688     }
    689 
    690     /**
    691      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    692      * BeanInfo class.)
    693      */
    694     public void setOnkeyupExpr(String onkeyupExpr) {
    695         this.onkeyupExpr = onkeyupExpr;
    696     }
    697 
    698     /**
    699      * Setter method for "onmousedown" tag attribute. (Mapping set in
    700      * associated BeanInfo class.)
    701      */
    702     public void setOnmousedownExpr(String onmousedownExpr) {
    703         this.onmousedownExpr = onmousedownExpr;
    704     }
    705 
    706     /**
    707      * Setter method for "onmousemove" tag attribute. (Mapping set in
    708      * associated BeanInfo class.)
    709      */
    710     public void setOnmousemoveExpr(String onmousemoveExpr) {
    711         this.onmousemoveExpr = onmousemoveExpr;
    712     }
    713 
    714     /**
    715      * Setter method for "onmouseout" tag attribute. (Mapping set in
    716      * associated BeanInfo class.)
    717      */
    718     public void setOnmouseoutExpr(String onmouseoutExpr) {
    719         this.onmouseoutExpr = onmouseoutExpr;
    720     }
    721 
    722     /**
    723      * Setter method for "onmouseover" tag attribute. (Mapping set in
    724      * associated BeanInfo class.)
    725      */
    726     public void setOnmouseoverExpr(String onmouseoverExpr) {
    727         this.onmouseoverExpr = onmouseoverExpr;
    728     }
    729 
    730     /**
    731      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    732      * BeanInfo class.)
    733      */
    734     public void setOnmouseupExpr(String onmouseupExpr) {
    735         this.onmouseupExpr = onmouseupExpr;
    736     }
    737 
    738     /**
    739      * Setter method for "property" tag attribute. (Mapping set in associated
    740      * BeanInfo class.)
    741      */
    742     public void setPropertyExpr(String propertyExpr) {
    743         this.propertyExpr = propertyExpr;
    744     }
    745 
    746     /**
    747      * Setter method for "size" tag attribute. (Mapping set in associated
    748      * BeanInfo class.)
    749      */
    750     public void setSizeExpr(String sizeExpr) {
    751         this.sizeExpr = sizeExpr;
    752     }
    753 
    754     /**
    755      * Setter method for "style" tag attribute. (Mapping set in associated
    756      * BeanInfo class.)
    757      */
    758     public void setStyleExpr(String styleExpr) {
    759         this.styleExpr = styleExpr;
    760     }
    761 
    762     /**
    763      * Setter method for "styleClass" tag attribute. (Mapping set in
    764      * associated BeanInfo class.)
    765      */
    766     public void setStyleClassExpr(String styleClassExpr) {
    767         this.styleClassExpr = styleClassExpr;
    768     }
    769 
    770     /**
    771      * Setter method for "styleId" tag attribute. (Mapping set in associated
    772      * BeanInfo class.)
    773      */
    774     public void setStyleIdExpr(String styleIdExpr) {
    775         this.styleIdExpr = styleIdExpr;
    776     }
    777 
    778     /**
    779      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    780      * BeanInfo class.)
    781      */
    782     public void setTabindexExpr(String tabindexExpr) {
    783         this.tabindexExpr = tabindexExpr;
    784     }
    785 
    786     /**
    787      * Setter method for "title" tag attribute. (Mapping set in associated
    788      * BeanInfo class.)
    789      */
    790     public void setTitleExpr(String titleExpr) {
    791         this.titleExpr = titleExpr;
    792     }
    793 
    794     /**
    795      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    796      * BeanInfo class.)
    797      */
    798     public void setTitleKeyExpr(String titleKeyExpr) {
    799         this.titleKeyExpr = titleKeyExpr;
    800     }
    801 
    802     /**
    803      * Setter method for "value" tag attribute. (Mapping set in associated
    804      * BeanInfo class.)
    805      */
    806     public void setValueExpr(String valueExpr) {
    807         this.valueExpr = valueExpr;
    808     }
    809 
    810     /**
    811      * Resets attribute values for tag reuse.
    812      */
    813     public void release() {
    814         super.release();
    815         setAltExpr(null);
    816         setAltKeyExpr(null);
    817         setBundleExpr(null);
    818         setDirExpr(null);
    819         setDisabledExpr(null);
    820         setErrorKeyExpr(null);
    821         setErrorStyleExpr(null);
    822         setErrorStyleClassExpr(null);
    823         setErrorStyleIdExpr(null);
    824         setIndexedExpr(null);
    825         setLangExpr(null);
    826         setMultipleExpr(null);
    827         setNameExpr(null);
    828         setOnblurExpr(null);
    829         setOnchangeExpr(null);
    830         setOnclickExpr(null);
    831         setOndblclickExpr(null);
    832         setOnfocusExpr(null);
    833         setOnkeydownExpr(null);
    834         setOnkeypressExpr(null);
    835         setOnkeyupExpr(null);
    836         setOnmousedownExpr(null);
    837         setOnmousemoveExpr(null);
    838         setOnmouseoutExpr(null);
    839         setOnmouseoverExpr(null);
    840         setOnmouseupExpr(null);
    841         setPropertyExpr(null);
    842         setSizeExpr(null);
    843         setStyleExpr(null);
    844         setStyleClassExpr(null);
    845         setStyleIdExpr(null);
    846         setTabindexExpr(null);
    847         setTitleExpr(null);
    848         setTitleKeyExpr(null);
    849         setValueExpr(null);
    850     }
    851 
    852     /**
    853      * Process the start tag.
    854      *
    855      * @throws JspException if a JSP exception has occurred
    856      */
    857     public int doStartTag() throws JspException {
    858         evaluateExpressions();
    859 
    860         return (super.doStartTag());
    861     }
    862 
    863     /**
    864      * Processes all attribute values which use the JSTL expression evaluation
    865      * engine to determine their values.
    866      *
    867      * @throws JspException if a JSP exception has occurred
    868      */
    869     private void evaluateExpressions()
    870         throws JspException {
    871         String string = null;
    872         Boolean bool = null;
    873 
    874         if ((string =
    875                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    876             setAlt(string);
    877         }
    878 
    879         if ((string =
    880                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    881                     pageContext)) != null) {
    882             setAltKey(string);
    883         }
    884 
    885         if ((string =
    886                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    887                     pageContext)) != null) {
    888             setBundle(string);
    889         }
    890 
    891         if ((string =
    892                  EvalHelper.evalString("dir", getDirExpr(), this,
    893                          pageContext)) != null) {
    894          setDir(string);
    895         }
    896 
    897         if ((bool =
    898                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    899                     pageContext)) != null) {
    900             setDisabled(bool.booleanValue());
    901         }
    902 
    903         if ((string =
    904                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    905                     pageContext)) != null) {
    906             setErrorKey(string);
    907         }
    908 
    909         if ((string =
    910                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    911                     pageContext)) != null) {
    912             setErrorStyle(string);
    913         }
    914 
    915         if ((string =
    916                 EvalHelper.evalString("errorStyleClass",
    917                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    918             setErrorStyleClass(string);
    919         }
    920 
    921         if ((string =
    922                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    923                     this, pageContext)) != null) {
    924             setErrorStyleId(string);
    925         }
    926 
    927         if ((bool =
    928                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    929                     pageContext)) != null) {
    930             setIndexed(bool.booleanValue());
    931         }
    932 
    933         if ((string =
    934                  EvalHelper.evalString("lang", getLangExpr(), this,
    935                          pageContext)) != null) {
    936          setLang(string);
    937         }
    938 
    939         if ((string =
    940                 EvalHelper.evalString("multiple", getMultipleExpr(), this,
    941                     pageContext)) != null) {
    942             setMultiple(string);
    943         }
    944 
    945         if ((string =
    946                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    947             setName(string);
    948         }
    949 
    950         if ((string =
    951                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    952                     pageContext)) != null) {
    953             setOnblur(string);
    954         }
    955 
    956         if ((string =
    957                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    958                     pageContext)) != null) {
    959             setOnchange(string);
    960         }
    961 
    962         if ((string =
    963                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    964                     pageContext)) != null) {
    965             setOnclick(string);
    966         }
    967 
    968         if ((string =
    969                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    970                     pageContext)) != null) {
    971             setOndblclick(string);
    972         }
    973 
    974         if ((string =
    975                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    976                     pageContext)) != null) {
    977             setOnfocus(string);
    978         }
    979 
    980         if ((string =
    981                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    982                     pageContext)) != null) {
    983             setOnkeydown(string);
    984         }
    985 
    986         if ((string =
    987                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    988                     pageContext)) != null) {
    989             setOnkeypress(string);
    990         }
    991 
    992         if ((string =
    993                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    994                     pageContext)) != null) {
    995             setOnkeyup(string);
    996         }
    997 
    998         if ((string =
    999                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1000                     this, pageContext)) != null) {
    1001             setOnmousedown(string);
    1002         }
    1003 
    1004         if ((string =
    1005                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1006                     this, pageContext)) != null) {
    1007             setOnmousemove(string);
    1008         }
    1009 
    1010         if ((string =
    1011                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1012                     pageContext)) != null) {
    1013             setOnmouseout(string);
    1014         }
    1015 
    1016         if ((string =
    1017                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1018                     this, pageContext)) != null) {
    1019             setOnmouseover(string);
    1020         }
    1021 
    1022         if ((string =
    1023                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1024                     pageContext)) != null) {
    1025             setOnmouseup(string);
    1026         }
    1027 
    1028         if ((string =
    1029                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1030                     pageContext)) != null) {
    1031             setProperty(string);
    1032         }
    1033 
    1034         if ((string =
    1035                 EvalHelper.evalString("size", getSizeExpr(), this, pageContext)) != null) {
    1036             setSize(string);
    1037         }
    1038 
    1039         if ((string =
    1040                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1041             setStyle(string);
    1042         }
    1043 
    1044         if ((string =
    1045                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1046                     pageContext)) != null) {
    1047             setStyleClass(string);
    1048         }
    1049 
    1050         if ((string =
    1051                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1052                     pageContext)) != null) {
    1053             setStyleId(string);
    1054         }
    1055 
    1056         if ((string =
    1057                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1058                     pageContext)) != null) {
    1059             setTabindex(string);
    1060         }
    1061 
    1062         if ((string =
    1063                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1064             setTitle(string);
    1065         }
    1066 
    1067         if ((string =
    1068                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1069                     pageContext)) != null) {
    1070             setTitleKey(string);
    1071         }
    1072 
    1073         if ((string =
    1074                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1075             setValue(string);
    1076         }
    1077     }
    1078 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
