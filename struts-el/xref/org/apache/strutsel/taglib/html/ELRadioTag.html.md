[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELRadioTag.html)


    1   /*
    2    * $Id: ELRadioTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.RadioTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for input fields of type "radio". <p> This class is a subclass of the
    30   * class <code>org.apache.struts.taglib.html.md.RadioTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELRadioTag extends RadioTag {
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
    99       * Instance variable mapped to "idName" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String idNameExpr;
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
    201      * Instance variable mapped to "property" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String propertyExpr;
    205 
    206     /**
    207      * Instance variable mapped to "style" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String styleExpr;
    211 
    212     /**
    213      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String styleClassExpr;
    217 
    218     /**
    219      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String styleIdExpr;
    223 
    224     /**
    225      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String tabindexExpr;
    229 
    230     /**
    231      * Instance variable mapped to "title" tag attribute. (Mapping set in
    232      * associated BeanInfo class.)
    233      */
    234     private String titleExpr;
    235 
    236     /**
    237      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     private String titleKeyExpr;
    241 
    242     /**
    243      * Instance variable mapped to "value" tag attribute. (Mapping set in
    244      * associated BeanInfo class.)
    245      */
    246     private String valueExpr;
    247 
    248     /**
    249      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    250      * BeanInfo class.)
    251      */
    252     public String getAccesskeyExpr() {
    253         return (accessKeyExpr);
    254     }
    255 
    256     /**
    257      * Getter method for "alt" tag attribute. (Mapping set in associated
    258      * BeanInfo class.)
    259      */
    260     public String getAltExpr() {
    261         return (altExpr);
    262     }
    263 
    264     /**
    265      * Getter method for "altKey" tag attribute. (Mapping set in associated
    266      * BeanInfo class.)
    267      */
    268     public String getAltKeyExpr() {
    269         return (altKeyExpr);
    270     }
    271 
    272     /**
    273      * Getter method for "bundle" tag attribute. (Mapping set in associated
    274      * BeanInfo class.)
    275      */
    276     public String getBundleExpr() {
    277         return (bundleExpr);
    278     }
    279 
    280     /**
    281      * Getter method for "dir" tag attribute. (Mapping set in associated
    282      * BeanInfo class.)
    283      */
    284     public String getDirExpr() {
    285         return (dirExpr);
    286     }
    287 
    288     /**
    289      * Getter method for "disabled" tag attribute. (Mapping set in associated
    290      * BeanInfo class.)
    291      */
    292     public String getDisabledExpr() {
    293         return (disabledExpr);
    294     }
    295 
    296     /**
    297      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    298      * BeanInfo class.)
    299      */
    300     public String getErrorKeyExpr() {
    301         return (errorKeyExpr);
    302     }
    303 
    304     /**
    305      * Getter method for "errorStyle" tag attribute. (Mapping set in
    306      * associated BeanInfo class.)
    307      */
    308     public String getErrorStyleExpr() {
    309         return (errorStyleExpr);
    310     }
    311 
    312     /**
    313      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    314      * associated BeanInfo class.)
    315      */
    316     public String getErrorStyleClassExpr() {
    317         return (errorStyleClassExpr);
    318     }
    319 
    320     /**
    321      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    322      * associated BeanInfo class.)
    323      */
    324     public String getErrorStyleIdExpr() {
    325         return (errorStyleIdExpr);
    326     }
    327 
    328     /**
    329      * Getter method for "lang" tag attribute. (Mapping set in associated
    330      * BeanInfo class.)
    331      */
    332     public String getLangExpr() {
    333         return (langExpr);
    334     }
    335 
    336     /**
    337      * Getter method for "idName" tag attribute. (Mapping set in associated
    338      * BeanInfo class.)
    339      */
    340     public String getIdNameExpr() {
    341         return (idNameExpr);
    342     }
    343 
    344     /**
    345      * Getter method for "indexed" tag attribute. (Mapping set in associated
    346      * BeanInfo class.)
    347      */
    348     public String getIndexedExpr() {
    349         return (indexedExpr);
    350     }
    351 
    352     /**
    353      * Getter method for "name" tag attribute. (Mapping set in associated
    354      * BeanInfo class.)
    355      */
    356     public String getNameExpr() {
    357         return (nameExpr);
    358     }
    359 
    360     /**
    361      * Getter method for "onblur" tag attribute. (Mapping set in associated
    362      * BeanInfo class.)
    363      */
    364     public String getOnblurExpr() {
    365         return (onblurExpr);
    366     }
    367 
    368     /**
    369      * Getter method for "onchange" tag attribute. (Mapping set in associated
    370      * BeanInfo class.)
    371      */
    372     public String getOnchangeExpr() {
    373         return (onchangeExpr);
    374     }
    375 
    376     /**
    377      * Getter method for "onclick" tag attribute. (Mapping set in associated
    378      * BeanInfo class.)
    379      */
    380     public String getOnclickExpr() {
    381         return (onclickExpr);
    382     }
    383 
    384     /**
    385      * Getter method for "ondblclick" tag attribute. (Mapping set in
    386      * associated BeanInfo class.)
    387      */
    388     public String getOndblclickExpr() {
    389         return (ondblclickExpr);
    390     }
    391 
    392     /**
    393      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    394      * BeanInfo class.)
    395      */
    396     public String getOnfocusExpr() {
    397         return (onfocusExpr);
    398     }
    399 
    400     /**
    401      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    402      * BeanInfo class.)
    403      */
    404     public String getOnkeydownExpr() {
    405         return (onkeydownExpr);
    406     }
    407 
    408     /**
    409      * Getter method for "onkeypress" tag attribute. (Mapping set in
    410      * associated BeanInfo class.)
    411      */
    412     public String getOnkeypressExpr() {
    413         return (onkeypressExpr);
    414     }
    415 
    416     /**
    417      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    418      * BeanInfo class.)
    419      */
    420     public String getOnkeyupExpr() {
    421         return (onkeyupExpr);
    422     }
    423 
    424     /**
    425      * Getter method for "onmousedown" tag attribute. (Mapping set in
    426      * associated BeanInfo class.)
    427      */
    428     public String getOnmousedownExpr() {
    429         return (onmousedownExpr);
    430     }
    431 
    432     /**
    433      * Getter method for "onmousemove" tag attribute. (Mapping set in
    434      * associated BeanInfo class.)
    435      */
    436     public String getOnmousemoveExpr() {
    437         return (onmousemoveExpr);
    438     }
    439 
    440     /**
    441      * Getter method for "onmouseout" tag attribute. (Mapping set in
    442      * associated BeanInfo class.)
    443      */
    444     public String getOnmouseoutExpr() {
    445         return (onmouseoutExpr);
    446     }
    447 
    448     /**
    449      * Getter method for "onmouseover" tag attribute. (Mapping set in
    450      * associated BeanInfo class.)
    451      */
    452     public String getOnmouseoverExpr() {
    453         return (onmouseoverExpr);
    454     }
    455 
    456     /**
    457      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    458      * BeanInfo class.)
    459      */
    460     public String getOnmouseupExpr() {
    461         return (onmouseupExpr);
    462     }
    463 
    464     /**
    465      * Getter method for "property" tag attribute. (Mapping set in associated
    466      * BeanInfo class.)
    467      */
    468     public String getPropertyExpr() {
    469         return (propertyExpr);
    470     }
    471 
    472     /**
    473      * Getter method for "style" tag attribute. (Mapping set in associated
    474      * BeanInfo class.)
    475      */
    476     public String getStyleExpr() {
    477         return (styleExpr);
    478     }
    479 
    480     /**
    481      * Getter method for "styleClass" tag attribute. (Mapping set in
    482      * associated BeanInfo class.)
    483      */
    484     public String getStyleClassExpr() {
    485         return (styleClassExpr);
    486     }
    487 
    488     /**
    489      * Getter method for "styleId" tag attribute. (Mapping set in associated
    490      * BeanInfo class.)
    491      */
    492     public String getStyleIdExpr() {
    493         return (styleIdExpr);
    494     }
    495 
    496     /**
    497      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    498      * BeanInfo class.)
    499      */
    500     public String getTabindexExpr() {
    501         return (tabindexExpr);
    502     }
    503 
    504     /**
    505      * Getter method for "title" tag attribute. (Mapping set in associated
    506      * BeanInfo class.)
    507      */
    508     public String getTitleExpr() {
    509         return (titleExpr);
    510     }
    511 
    512     /**
    513      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    514      * BeanInfo class.)
    515      */
    516     public String getTitleKeyExpr() {
    517         return (titleKeyExpr);
    518     }
    519 
    520     /**
    521      * Getter method for "value" tag attribute. (Mapping set in associated
    522      * BeanInfo class.)
    523      */
    524     public String getValueExpr() {
    525         return (valueExpr);
    526     }
    527 
    528     /**
    529      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    530      * BeanInfo class.)
    531      */
    532     public void setAccesskeyExpr(String accessKeyExpr) {
    533         this.accessKeyExpr = accessKeyExpr;
    534     }
    535 
    536     /**
    537      * Setter method for "alt" tag attribute. (Mapping set in associated
    538      * BeanInfo class.)
    539      */
    540     public void setAltExpr(String altExpr) {
    541         this.altExpr = altExpr;
    542     }
    543 
    544     /**
    545      * Setter method for "altKey" tag attribute. (Mapping set in associated
    546      * BeanInfo class.)
    547      */
    548     public void setAltKeyExpr(String altKeyExpr) {
    549         this.altKeyExpr = altKeyExpr;
    550     }
    551 
    552     /**
    553      * Setter method for "bundle" tag attribute. (Mapping set in associated
    554      * BeanInfo class.)
    555      */
    556     public void setBundleExpr(String bundleExpr) {
    557         this.bundleExpr = bundleExpr;
    558     }
    559 
    560     /**
    561      * Setter method for "dir" tag attribute. (Mapping set in associated
    562      * BeanInfo class.)
    563      */
    564     public void setDirExpr(String dirExpr) {
    565         this.dirExpr = dirExpr;
    566     }
    567 
    568     /**
    569      * Setter method for "disabled" tag attribute. (Mapping set in associated
    570      * BeanInfo class.)
    571      */
    572     public void setDisabledExpr(String disabledExpr) {
    573         this.disabledExpr = disabledExpr;
    574     }
    575 
    576     /**
    577      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    578      * BeanInfo class.)
    579      */
    580     public void setErrorKeyExpr(String errorKeyExpr) {
    581         this.errorKeyExpr = errorKeyExpr;
    582     }
    583 
    584     /**
    585      * Setter method for "errorStyle" tag attribute. (Mapping set in
    586      * associated BeanInfo class.)
    587      */
    588     public void setErrorStyleExpr(String errorStyleExpr) {
    589         this.errorStyleExpr = errorStyleExpr;
    590     }
    591 
    592     /**
    593      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    594      * associated BeanInfo class.)
    595      */
    596     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    597         this.errorStyleClassExpr = errorStyleClassExpr;
    598     }
    599 
    600     /**
    601      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    602      * associated BeanInfo class.)
    603      */
    604     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    605         this.errorStyleIdExpr = errorStyleIdExpr;
    606     }
    607 
    608     /**
    609      * Setter method for "idName" tag attribute. (Mapping set in associated
    610      * BeanInfo class.)
    611      */
    612     public void setIdNameExpr(String idNameExpr) {
    613         this.idNameExpr = idNameExpr;
    614     }
    615 
    616     /**
    617      * Setter method for "indexed" tag attribute. (Mapping set in associated
    618      * BeanInfo class.)
    619      */
    620     public void setIndexedExpr(String indexedExpr) {
    621         this.indexedExpr = indexedExpr;
    622     }
    623 
    624     /**
    625      * Setter method for "lang" tag attribute. (Mapping set in associated
    626      * BeanInfo class.)
    627      */
    628     public void setLangExpr(String langExpr) {
    629         this.langExpr = langExpr;
    630     }
    631 
    632     /**
    633      * Setter method for "name" tag attribute. (Mapping set in associated
    634      * BeanInfo class.)
    635      */
    636     public void setNameExpr(String nameExpr) {
    637         this.nameExpr = nameExpr;
    638     }
    639 
    640     /**
    641      * Setter method for "onblur" tag attribute. (Mapping set in associated
    642      * BeanInfo class.)
    643      */
    644     public void setOnblurExpr(String onblurExpr) {
    645         this.onblurExpr = onblurExpr;
    646     }
    647 
    648     /**
    649      * Setter method for "onchange" tag attribute. (Mapping set in associated
    650      * BeanInfo class.)
    651      */
    652     public void setOnchangeExpr(String onchangeExpr) {
    653         this.onchangeExpr = onchangeExpr;
    654     }
    655 
    656     /**
    657      * Setter method for "onclick" tag attribute. (Mapping set in associated
    658      * BeanInfo class.)
    659      */
    660     public void setOnclickExpr(String onclickExpr) {
    661         this.onclickExpr = onclickExpr;
    662     }
    663 
    664     /**
    665      * Setter method for "ondblclick" tag attribute. (Mapping set in
    666      * associated BeanInfo class.)
    667      */
    668     public void setOndblclickExpr(String ondblclickExpr) {
    669         this.ondblclickExpr = ondblclickExpr;
    670     }
    671 
    672     /**
    673      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    674      * BeanInfo class.)
    675      */
    676     public void setOnfocusExpr(String onfocusExpr) {
    677         this.onfocusExpr = onfocusExpr;
    678     }
    679 
    680     /**
    681      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    682      * BeanInfo class.)
    683      */
    684     public void setOnkeydownExpr(String onkeydownExpr) {
    685         this.onkeydownExpr = onkeydownExpr;
    686     }
    687 
    688     /**
    689      * Setter method for "onkeypress" tag attribute. (Mapping set in
    690      * associated BeanInfo class.)
    691      */
    692     public void setOnkeypressExpr(String onkeypressExpr) {
    693         this.onkeypressExpr = onkeypressExpr;
    694     }
    695 
    696     /**
    697      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    698      * BeanInfo class.)
    699      */
    700     public void setOnkeyupExpr(String onkeyupExpr) {
    701         this.onkeyupExpr = onkeyupExpr;
    702     }
    703 
    704     /**
    705      * Setter method for "onmousedown" tag attribute. (Mapping set in
    706      * associated BeanInfo class.)
    707      */
    708     public void setOnmousedownExpr(String onmousedownExpr) {
    709         this.onmousedownExpr = onmousedownExpr;
    710     }
    711 
    712     /**
    713      * Setter method for "onmousemove" tag attribute. (Mapping set in
    714      * associated BeanInfo class.)
    715      */
    716     public void setOnmousemoveExpr(String onmousemoveExpr) {
    717         this.onmousemoveExpr = onmousemoveExpr;
    718     }
    719 
    720     /**
    721      * Setter method for "onmouseout" tag attribute. (Mapping set in
    722      * associated BeanInfo class.)
    723      */
    724     public void setOnmouseoutExpr(String onmouseoutExpr) {
    725         this.onmouseoutExpr = onmouseoutExpr;
    726     }
    727 
    728     /**
    729      * Setter method for "onmouseover" tag attribute. (Mapping set in
    730      * associated BeanInfo class.)
    731      */
    732     public void setOnmouseoverExpr(String onmouseoverExpr) {
    733         this.onmouseoverExpr = onmouseoverExpr;
    734     }
    735 
    736     /**
    737      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    738      * BeanInfo class.)
    739      */
    740     public void setOnmouseupExpr(String onmouseupExpr) {
    741         this.onmouseupExpr = onmouseupExpr;
    742     }
    743 
    744     /**
    745      * Setter method for "property" tag attribute. (Mapping set in associated
    746      * BeanInfo class.)
    747      */
    748     public void setPropertyExpr(String propertyExpr) {
    749         this.propertyExpr = propertyExpr;
    750     }
    751 
    752     /**
    753      * Setter method for "style" tag attribute. (Mapping set in associated
    754      * BeanInfo class.)
    755      */
    756     public void setStyleExpr(String styleExpr) {
    757         this.styleExpr = styleExpr;
    758     }
    759 
    760     /**
    761      * Setter method for "styleClass" tag attribute. (Mapping set in
    762      * associated BeanInfo class.)
    763      */
    764     public void setStyleClassExpr(String styleClassExpr) {
    765         this.styleClassExpr = styleClassExpr;
    766     }
    767 
    768     /**
    769      * Setter method for "styleId" tag attribute. (Mapping set in associated
    770      * BeanInfo class.)
    771      */
    772     public void setStyleIdExpr(String styleIdExpr) {
    773         this.styleIdExpr = styleIdExpr;
    774     }
    775 
    776     /**
    777      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    778      * BeanInfo class.)
    779      */
    780     public void setTabindexExpr(String tabindexExpr) {
    781         this.tabindexExpr = tabindexExpr;
    782     }
    783 
    784     /**
    785      * Setter method for "title" tag attribute. (Mapping set in associated
    786      * BeanInfo class.)
    787      */
    788     public void setTitleExpr(String titleExpr) {
    789         this.titleExpr = titleExpr;
    790     }
    791 
    792     /**
    793      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    794      * BeanInfo class.)
    795      */
    796     public void setTitleKeyExpr(String titleKeyExpr) {
    797         this.titleKeyExpr = titleKeyExpr;
    798     }
    799 
    800     /**
    801      * Setter method for "value" tag attribute. (Mapping set in associated
    802      * BeanInfo class.)
    803      */
    804     public void setValueExpr(String valueExpr) {
    805         this.valueExpr = valueExpr;
    806     }
    807 
    808     /**
    809      * Resets attribute values for tag reuse.
    810      */
    811     public void release() {
    812         super.release();
    813         setAccesskeyExpr(null);
    814         setAltExpr(null);
    815         setAltKeyExpr(null);
    816         setBundleExpr(null);
    817         setDirExpr(null);
    818         setDisabledExpr(null);
    819         setErrorKeyExpr(null);
    820         setErrorStyleExpr(null);
    821         setErrorStyleClassExpr(null);
    822         setErrorStyleIdExpr(null);
    823         setIdNameExpr(null);
    824         setIndexedExpr(null);
    825         setLangExpr(null);
    826         setNameExpr(null);
    827         setOnblurExpr(null);
    828         setOnchangeExpr(null);
    829         setOnclickExpr(null);
    830         setOndblclickExpr(null);
    831         setOnfocusExpr(null);
    832         setOnkeydownExpr(null);
    833         setOnkeypressExpr(null);
    834         setOnkeyupExpr(null);
    835         setOnmousedownExpr(null);
    836         setOnmousemoveExpr(null);
    837         setOnmouseoutExpr(null);
    838         setOnmouseoverExpr(null);
    839         setOnmouseupExpr(null);
    840         setPropertyExpr(null);
    841         setStyleExpr(null);
    842         setStyleClassExpr(null);
    843         setStyleIdExpr(null);
    844         setTabindexExpr(null);
    845         setTitleExpr(null);
    846         setTitleKeyExpr(null);
    847         setValueExpr(null);
    848     }
    849 
    850     /**
    851      * Process the start tag.
    852      *
    853      * @throws JspException if a JSP exception has occurred
    854      */
    855     public int doStartTag() throws JspException {
    856         evaluateExpressions();
    857 
    858         return (super.doStartTag());
    859     }
    860 
    861     /**
    862      * Processes all attribute values which use the JSTL expression evaluation
    863      * engine to determine their values.
    864      *
    865      * @throws JspException if a JSP exception has occurred
    866      */
    867     private void evaluateExpressions()
    868         throws JspException {
    869         String string = null;
    870         Boolean bool = null;
    871 
    872         if ((string =
    873                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    874                     pageContext)) != null) {
    875             setAccesskey(string);
    876         }
    877 
    878         if ((string =
    879                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    880             setAlt(string);
    881         }
    882 
    883         if ((string =
    884                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    885                     pageContext)) != null) {
    886             setAltKey(string);
    887         }
    888 
    889         if ((string =
    890                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    891                     pageContext)) != null) {
    892             setBundle(string);
    893         }
    894 
    895         if ((string =
    896                  EvalHelper.evalString("dir", getDirExpr(), this,
    897                          pageContext)) != null) {
    898          setDir(string);
    899         }
    900         
    901         if ((bool =
    902                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    903                     pageContext)) != null) {
    904             setDisabled(bool.booleanValue());
    905         }
    906 
    907         if ((string =
    908                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    909                     pageContext)) != null) {
    910             setErrorKey(string);
    911         }
    912 
    913         if ((string =
    914                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    915                     pageContext)) != null) {
    916             setErrorStyle(string);
    917         }
    918 
    919         if ((string =
    920                 EvalHelper.evalString("errorStyleClass",
    921                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    922             setErrorStyleClass(string);
    923         }
    924 
    925         if ((string =
    926                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    927                     this, pageContext)) != null) {
    928             setErrorStyleId(string);
    929         }
    930 
    931         if ((string =
    932                 EvalHelper.evalString("idName", getIdNameExpr(), this,
    933                     pageContext)) != null) {
    934             setIdName(string);
    935         }
    936 
    937         if ((bool =
    938                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    939                     pageContext)) != null) {
    940             setIndexed(bool.booleanValue());
    941         }
    942 
    943         if ((string =
    944                  EvalHelper.evalString("lang", getLangExpr(), this,
    945                          pageContext)) != null) {
    946          setLang(string);
    947         }
    948 
    949         if ((string =
    950                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    951             setName(string);
    952         }
    953 
    954         if ((string =
    955                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    956                     pageContext)) != null) {
    957             setOnblur(string);
    958         }
    959 
    960         if ((string =
    961                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    962                     pageContext)) != null) {
    963             setOnchange(string);
    964         }
    965 
    966         if ((string =
    967                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    968                     pageContext)) != null) {
    969             setOnclick(string);
    970         }
    971 
    972         if ((string =
    973                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    974                     pageContext)) != null) {
    975             setOndblclick(string);
    976         }
    977 
    978         if ((string =
    979                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    980                     pageContext)) != null) {
    981             setOnfocus(string);
    982         }
    983 
    984         if ((string =
    985                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    986                     pageContext)) != null) {
    987             setOnkeydown(string);
    988         }
    989 
    990         if ((string =
    991                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    992                     pageContext)) != null) {
    993             setOnkeypress(string);
    994         }
    995 
    996         if ((string =
    997                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    998                     pageContext)) != null) {
    999             setOnkeyup(string);
    1000         }
    1001 
    1002         if ((string =
    1003                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1004                     this, pageContext)) != null) {
    1005             setOnmousedown(string);
    1006         }
    1007 
    1008         if ((string =
    1009                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1010                     this, pageContext)) != null) {
    1011             setOnmousemove(string);
    1012         }
    1013 
    1014         if ((string =
    1015                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1016                     pageContext)) != null) {
    1017             setOnmouseout(string);
    1018         }
    1019 
    1020         if ((string =
    1021                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1022                     this, pageContext)) != null) {
    1023             setOnmouseover(string);
    1024         }
    1025 
    1026         if ((string =
    1027                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1028                     pageContext)) != null) {
    1029             setOnmouseup(string);
    1030         }
    1031 
    1032         if ((string =
    1033                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1034                     pageContext)) != null) {
    1035             setProperty(string);
    1036         }
    1037 
    1038         if ((string =
    1039                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1040             setStyle(string);
    1041         }
    1042 
    1043         if ((string =
    1044                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1045                     pageContext)) != null) {
    1046             setStyleClass(string);
    1047         }
    1048 
    1049         if ((string =
    1050                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1051                     pageContext)) != null) {
    1052             setStyleId(string);
    1053         }
    1054 
    1055         if ((string =
    1056                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1057                     pageContext)) != null) {
    1058             setTabindex(string);
    1059         }
    1060 
    1061         if ((string =
    1062                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1063             setTitle(string);
    1064         }
    1065 
    1066         if ((string =
    1067                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1068                     pageContext)) != null) {
    1069             setTitleKey(string);
    1070         }
    1071 
    1072         if ((string =
    1073                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1074             setValue(string);
    1075         }
    1076     }
    1077 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
