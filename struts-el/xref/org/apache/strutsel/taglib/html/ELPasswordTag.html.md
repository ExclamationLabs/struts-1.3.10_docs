[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELPasswordTag.html)


    1   /*
    2    * $Id: ELPasswordTag.java 558599 2007-07-23 04:36:07Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.PasswordTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag for input fields of type "password". <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.html.md.PasswordTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 558599 $
    36   */
    37  public class ELPasswordTag extends PasswordTag {
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
    219      * Instance variable mapped to "redisplay" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String redisplayExpr;
    223 
    224     /**
    225      * Instance variable mapped to "style" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String styleExpr;
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
    243      * Instance variable mapped to "size" tag attribute. (Mapping set in
    244      * associated BeanInfo class.)
    245      */
    246     private String sizeExpr;
    247 
    248     /**
    249      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    250      * associated BeanInfo class.)
    251      */
    252     private String tabindexExpr;
    253 
    254     /**
    255      * Instance variable mapped to "title" tag attribute. (Mapping set in
    256      * associated BeanInfo class.)
    257      */
    258     private String titleExpr;
    259 
    260     /**
    261      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    262      * associated BeanInfo class.)
    263      */
    264     private String titleKeyExpr;
    265 
    266     /**
    267      * Instance variable mapped to "value" tag attribute. (Mapping set in
    268      * associated BeanInfo class.)
    269      */
    270     private String valueExpr;
    271 
    272     /**
    273      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    274      * BeanInfo class.)
    275      */
    276     public String getAccesskeyExpr() {
    277         return (accessKeyExpr);
    278     }
    279 
    280     /**
    281      * Getter method for "alt" tag attribute. (Mapping set in associated
    282      * BeanInfo class.)
    283      */
    284     public String getAltExpr() {
    285         return (altExpr);
    286     }
    287 
    288     /**
    289      * Getter method for "altKey" tag attribute. (Mapping set in associated
    290      * BeanInfo class.)
    291      */
    292     public String getAltKeyExpr() {
    293         return (altKeyExpr);
    294     }
    295 
    296     /**
    297      * Getter method for "bundle" tag attribute. (Mapping set in associated
    298      * BeanInfo class.)
    299      */
    300     public String getBundleExpr() {
    301         return (bundleExpr);
    302     }
    303 
    304     /**
    305      * Getter method for "dir" tag attribute. (Mapping set in associated
    306      * BeanInfo class.)
    307      */
    308     public String getDirExpr() {
    309         return (dirExpr);
    310     }
    311 
    312     /**
    313      * Getter method for "disabled" tag attribute. (Mapping set in associated
    314      * BeanInfo class.)
    315      */
    316     public String getDisabledExpr() {
    317         return (disabledExpr);
    318     }
    319 
    320     /**
    321      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    322      * BeanInfo class.)
    323      */
    324     public String getErrorKeyExpr() {
    325         return (errorKeyExpr);
    326     }
    327 
    328     /**
    329      * Getter method for "errorStyle" tag attribute. (Mapping set in
    330      * associated BeanInfo class.)
    331      */
    332     public String getErrorStyleExpr() {
    333         return (errorStyleExpr);
    334     }
    335 
    336     /**
    337      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    338      * associated BeanInfo class.)
    339      */
    340     public String getErrorStyleClassExpr() {
    341         return (errorStyleClassExpr);
    342     }
    343 
    344     /**
    345      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    346      * associated BeanInfo class.)
    347      */
    348     public String getErrorStyleIdExpr() {
    349         return (errorStyleIdExpr);
    350     }
    351 
    352     /**
    353      * Getter method for "indexed" tag attribute. (Mapping set in associated
    354      * BeanInfo class.)
    355      */
    356     public String getIndexedExpr() {
    357         return (indexedExpr);
    358     }
    359 
    360     /**
    361      * Getter method for "lang" tag attribute. (Mapping set in associated
    362      * BeanInfo class.)
    363      */
    364     public String getLangExpr() {
    365         return (langExpr);
    366     }
    367 
    368     /**
    369      * Getter method for "maxlength" tag attribute. (Mapping set in associated
    370      * BeanInfo class.)
    371      */
    372     public String getMaxlengthExpr() {
    373         return (maxlengthExpr);
    374     }
    375 
    376     /**
    377      * Getter method for "name" tag attribute. (Mapping set in associated
    378      * BeanInfo class.)
    379      */
    380     public String getNameExpr() {
    381         return (nameExpr);
    382     }
    383 
    384     /**
    385      * Getter method for "onblur" tag attribute. (Mapping set in associated
    386      * BeanInfo class.)
    387      */
    388     public String getOnblurExpr() {
    389         return (onblurExpr);
    390     }
    391 
    392     /**
    393      * Getter method for "onchange" tag attribute. (Mapping set in associated
    394      * BeanInfo class.)
    395      */
    396     public String getOnchangeExpr() {
    397         return (onchangeExpr);
    398     }
    399 
    400     /**
    401      * Getter method for "onclick" tag attribute. (Mapping set in associated
    402      * BeanInfo class.)
    403      */
    404     public String getOnclickExpr() {
    405         return (onclickExpr);
    406     }
    407 
    408     /**
    409      * Getter method for "ondblclick" tag attribute. (Mapping set in
    410      * associated BeanInfo class.)
    411      */
    412     public String getOndblclickExpr() {
    413         return (ondblclickExpr);
    414     }
    415 
    416     /**
    417      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    418      * BeanInfo class.)
    419      */
    420     public String getOnfocusExpr() {
    421         return (onfocusExpr);
    422     }
    423 
    424     /**
    425      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    426      * BeanInfo class.)
    427      */
    428     public String getOnkeydownExpr() {
    429         return (onkeydownExpr);
    430     }
    431 
    432     /**
    433      * Getter method for "onkeypress" tag attribute. (Mapping set in
    434      * associated BeanInfo class.)
    435      */
    436     public String getOnkeypressExpr() {
    437         return (onkeypressExpr);
    438     }
    439 
    440     /**
    441      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    442      * BeanInfo class.)
    443      */
    444     public String getOnkeyupExpr() {
    445         return (onkeyupExpr);
    446     }
    447 
    448     /**
    449      * Getter method for "onmousedown" tag attribute. (Mapping set in
    450      * associated BeanInfo class.)
    451      */
    452     public String getOnmousedownExpr() {
    453         return (onmousedownExpr);
    454     }
    455 
    456     /**
    457      * Getter method for "onmousemove" tag attribute. (Mapping set in
    458      * associated BeanInfo class.)
    459      */
    460     public String getOnmousemoveExpr() {
    461         return (onmousemoveExpr);
    462     }
    463 
    464     /**
    465      * Getter method for "onmouseout" tag attribute. (Mapping set in
    466      * associated BeanInfo class.)
    467      */
    468     public String getOnmouseoutExpr() {
    469         return (onmouseoutExpr);
    470     }
    471 
    472     /**
    473      * Getter method for "onmouseover" tag attribute. (Mapping set in
    474      * associated BeanInfo class.)
    475      */
    476     public String getOnmouseoverExpr() {
    477         return (onmouseoverExpr);
    478     }
    479 
    480     /**
    481      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    482      * BeanInfo class.)
    483      */
    484     public String getOnmouseupExpr() {
    485         return (onmouseupExpr);
    486     }
    487 
    488     /**
    489      * Getter method for "onselect" tag attribute. (Mapping set in associated
    490      * BeanInfo class.)
    491      */
    492     public String getOnselectExpr() {
    493         return (onselectExpr);
    494     }
    495 
    496     /**
    497      * Getter method for "property" tag attribute. (Mapping set in associated
    498      * BeanInfo class.)
    499      */
    500     public String getPropertyExpr() {
    501         return (propertyExpr);
    502     }
    503 
    504     /**
    505      * Getter method for "readonly" tag attribute. (Mapping set in associated
    506      * BeanInfo class.)
    507      */
    508     public String getReadonlyExpr() {
    509         return (readonlyExpr);
    510     }
    511 
    512     /**
    513      * Getter method for "redisplay" tag attribute. (Mapping set in associated
    514      * BeanInfo class.)
    515      */
    516     public String getRedisplayExpr() {
    517         return (redisplayExpr);
    518     }
    519 
    520     /**
    521      * Getter method for "style" tag attribute. (Mapping set in associated
    522      * BeanInfo class.)
    523      */
    524     public String getStyleExpr() {
    525         return (styleExpr);
    526     }
    527 
    528     /**
    529      * Getter method for "styleClass" tag attribute. (Mapping set in
    530      * associated BeanInfo class.)
    531      */
    532     public String getStyleClassExpr() {
    533         return (styleClassExpr);
    534     }
    535 
    536     /**
    537      * Getter method for "styleId" tag attribute. (Mapping set in associated
    538      * BeanInfo class.)
    539      */
    540     public String getStyleIdExpr() {
    541         return (styleIdExpr);
    542     }
    543 
    544     /**
    545      * Getter method for "size" tag attribute. (Mapping set in associated
    546      * BeanInfo class.)
    547      */
    548     public String getSizeExpr() {
    549         return (sizeExpr);
    550     }
    551 
    552     /**
    553      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    554      * BeanInfo class.)
    555      */
    556     public String getTabindexExpr() {
    557         return (tabindexExpr);
    558     }
    559 
    560     /**
    561      * Getter method for "title" tag attribute. (Mapping set in associated
    562      * BeanInfo class.)
    563      */
    564     public String getTitleExpr() {
    565         return (titleExpr);
    566     }
    567 
    568     /**
    569      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    570      * BeanInfo class.)
    571      */
    572     public String getTitleKeyExpr() {
    573         return (titleKeyExpr);
    574     }
    575 
    576     /**
    577      * Getter method for "value" tag attribute. (Mapping set in associated
    578      * BeanInfo class.)
    579      */
    580     public String getValueExpr() {
    581         return (valueExpr);
    582     }
    583 
    584     /**
    585      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    586      * BeanInfo class.)
    587      */
    588     public void setAccesskeyExpr(String accessKeyExpr) {
    589         this.accessKeyExpr = accessKeyExpr;
    590     }
    591 
    592     /**
    593      * Setter method for "alt" tag attribute. (Mapping set in associated
    594      * BeanInfo class.)
    595      */
    596     public void setAltExpr(String altExpr) {
    597         this.altExpr = altExpr;
    598     }
    599 
    600     /**
    601      * Setter method for "altKey" tag attribute. (Mapping set in associated
    602      * BeanInfo class.)
    603      */
    604     public void setAltKeyExpr(String altKeyExpr) {
    605         this.altKeyExpr = altKeyExpr;
    606     }
    607 
    608     /**
    609      * Setter method for "bundle" tag attribute. (Mapping set in associated
    610      * BeanInfo class.)
    611      */
    612     public void setBundleExpr(String bundleExpr) {
    613         this.bundleExpr = bundleExpr;
    614     }
    615 
    616     /**
    617      * Setter method for "dir" tag attribute. (Mapping set in associated
    618      * BeanInfo class.)
    619      */
    620     public void setDirExpr(String dirExpr) {
    621         this.dirExpr = dirExpr;
    622     }
    623 
    624     /**
    625      * Setter method for "disabled" tag attribute. (Mapping set in associated
    626      * BeanInfo class.)
    627      */
    628     public void setDisabledExpr(String disabledExpr) {
    629         this.disabledExpr = disabledExpr;
    630     }
    631 
    632     /**
    633      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    634      * BeanInfo class.)
    635      */
    636     public void setErrorKeyExpr(String errorKeyExpr) {
    637         this.errorKeyExpr = errorKeyExpr;
    638     }
    639 
    640     /**
    641      * Setter method for "errorStyle" tag attribute. (Mapping set in
    642      * associated BeanInfo class.)
    643      */
    644     public void setErrorStyleExpr(String errorStyleExpr) {
    645         this.errorStyleExpr = errorStyleExpr;
    646     }
    647 
    648     /**
    649      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    650      * associated BeanInfo class.)
    651      */
    652     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    653         this.errorStyleClassExpr = errorStyleClassExpr;
    654     }
    655 
    656     /**
    657      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    658      * associated BeanInfo class.)
    659      */
    660     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    661         this.errorStyleIdExpr = errorStyleIdExpr;
    662     }
    663 
    664     /**
    665      * Setter method for "indexed" tag attribute. (Mapping set in associated
    666      * BeanInfo class.)
    667      */
    668     public void setIndexedExpr(String indexedExpr) {
    669         this.indexedExpr = indexedExpr;
    670     }
    671 
    672     /**
    673      * Setter method for "lang" tag attribute. (Mapping set in associated
    674      * BeanInfo class.)
    675      */
    676     public void setLangExpr(String langExpr) {
    677         this.langExpr = langExpr;
    678     }
    679 
    680     /**
    681      * Setter method for "maxlength" tag attribute. (Mapping set in associated
    682      * BeanInfo class.)
    683      */
    684     public void setMaxlengthExpr(String maxlengthExpr) {
    685         this.maxlengthExpr = maxlengthExpr;
    686     }
    687 
    688     /**
    689      * Setter method for "name" tag attribute. (Mapping set in associated
    690      * BeanInfo class.)
    691      */
    692     public void setNameExpr(String nameExpr) {
    693         this.nameExpr = nameExpr;
    694     }
    695 
    696     /**
    697      * Setter method for "onblur" tag attribute. (Mapping set in associated
    698      * BeanInfo class.)
    699      */
    700     public void setOnblurExpr(String onblurExpr) {
    701         this.onblurExpr = onblurExpr;
    702     }
    703 
    704     /**
    705      * Setter method for "onchange" tag attribute. (Mapping set in associated
    706      * BeanInfo class.)
    707      */
    708     public void setOnchangeExpr(String onchangeExpr) {
    709         this.onchangeExpr = onchangeExpr;
    710     }
    711 
    712     /**
    713      * Setter method for "onclick" tag attribute. (Mapping set in associated
    714      * BeanInfo class.)
    715      */
    716     public void setOnclickExpr(String onclickExpr) {
    717         this.onclickExpr = onclickExpr;
    718     }
    719 
    720     /**
    721      * Setter method for "ondblclick" tag attribute. (Mapping set in
    722      * associated BeanInfo class.)
    723      */
    724     public void setOndblclickExpr(String ondblclickExpr) {
    725         this.ondblclickExpr = ondblclickExpr;
    726     }
    727 
    728     /**
    729      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    730      * BeanInfo class.)
    731      */
    732     public void setOnfocusExpr(String onfocusExpr) {
    733         this.onfocusExpr = onfocusExpr;
    734     }
    735 
    736     /**
    737      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    738      * BeanInfo class.)
    739      */
    740     public void setOnkeydownExpr(String onkeydownExpr) {
    741         this.onkeydownExpr = onkeydownExpr;
    742     }
    743 
    744     /**
    745      * Setter method for "onkeypress" tag attribute. (Mapping set in
    746      * associated BeanInfo class.)
    747      */
    748     public void setOnkeypressExpr(String onkeypressExpr) {
    749         this.onkeypressExpr = onkeypressExpr;
    750     }
    751 
    752     /**
    753      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    754      * BeanInfo class.)
    755      */
    756     public void setOnkeyupExpr(String onkeyupExpr) {
    757         this.onkeyupExpr = onkeyupExpr;
    758     }
    759 
    760     /**
    761      * Setter method for "onmousedown" tag attribute. (Mapping set in
    762      * associated BeanInfo class.)
    763      */
    764     public void setOnmousedownExpr(String onmousedownExpr) {
    765         this.onmousedownExpr = onmousedownExpr;
    766     }
    767 
    768     /**
    769      * Setter method for "onmousemove" tag attribute. (Mapping set in
    770      * associated BeanInfo class.)
    771      */
    772     public void setOnmousemoveExpr(String onmousemoveExpr) {
    773         this.onmousemoveExpr = onmousemoveExpr;
    774     }
    775 
    776     /**
    777      * Setter method for "onmouseout" tag attribute. (Mapping set in
    778      * associated BeanInfo class.)
    779      */
    780     public void setOnmouseoutExpr(String onmouseoutExpr) {
    781         this.onmouseoutExpr = onmouseoutExpr;
    782     }
    783 
    784     /**
    785      * Setter method for "onmouseover" tag attribute. (Mapping set in
    786      * associated BeanInfo class.)
    787      */
    788     public void setOnmouseoverExpr(String onmouseoverExpr) {
    789         this.onmouseoverExpr = onmouseoverExpr;
    790     }
    791 
    792     /**
    793      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    794      * BeanInfo class.)
    795      */
    796     public void setOnmouseupExpr(String onmouseupExpr) {
    797         this.onmouseupExpr = onmouseupExpr;
    798     }
    799 
    800     /**
    801      * Setter method for "onselect" tag attribute. (Mapping set in associated
    802      * BeanInfo class.)
    803      */
    804     public void setOnselectExpr(String onselectExpr) {
    805         this.onselectExpr = onselectExpr;
    806     }
    807 
    808     /**
    809      * Setter method for "property" tag attribute. (Mapping set in associated
    810      * BeanInfo class.)
    811      */
    812     public void setPropertyExpr(String propertyExpr) {
    813         this.propertyExpr = propertyExpr;
    814     }
    815 
    816     /**
    817      * Setter method for "readonly" tag attribute. (Mapping set in associated
    818      * BeanInfo class.)
    819      */
    820     public void setReadonlyExpr(String readonlyExpr) {
    821         this.readonlyExpr = readonlyExpr;
    822     }
    823 
    824     /**
    825      * Setter method for "redisplay" tag attribute. (Mapping set in associated
    826      * BeanInfo class.)
    827      */
    828     public void setRedisplayExpr(String redisplayExpr) {
    829         this.redisplayExpr = redisplayExpr;
    830     }
    831 
    832     /**
    833      * Setter method for "style" tag attribute. (Mapping set in associated
    834      * BeanInfo class.)
    835      */
    836     public void setStyleExpr(String styleExpr) {
    837         this.styleExpr = styleExpr;
    838     }
    839 
    840     /**
    841      * Setter method for "styleClass" tag attribute. (Mapping set in
    842      * associated BeanInfo class.)
    843      */
    844     public void setStyleClassExpr(String styleClassExpr) {
    845         this.styleClassExpr = styleClassExpr;
    846     }
    847 
    848     /**
    849      * Setter method for "styleId" tag attribute. (Mapping set in associated
    850      * BeanInfo class.)
    851      */
    852     public void setStyleIdExpr(String styleIdExpr) {
    853         this.styleIdExpr = styleIdExpr;
    854     }
    855 
    856     /**
    857      * Setter method for "size" tag attribute. (Mapping set in associated
    858      * BeanInfo class.)
    859      */
    860     public void setSizeExpr(String sizeExpr) {
    861         this.sizeExpr = sizeExpr;
    862     }
    863 
    864     /**
    865      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    866      * BeanInfo class.)
    867      */
    868     public void setTabindexExpr(String tabindexExpr) {
    869         this.tabindexExpr = tabindexExpr;
    870     }
    871 
    872     /**
    873      * Setter method for "title" tag attribute. (Mapping set in associated
    874      * BeanInfo class.)
    875      */
    876     public void setTitleExpr(String titleExpr) {
    877         this.titleExpr = titleExpr;
    878     }
    879 
    880     /**
    881      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    882      * BeanInfo class.)
    883      */
    884     public void setTitleKeyExpr(String titleKeyExpr) {
    885         this.titleKeyExpr = titleKeyExpr;
    886     }
    887 
    888     /**
    889      * Setter method for "value" tag attribute. (Mapping set in associated
    890      * BeanInfo class.)
    891      */
    892     public void setValueExpr(String valueExpr) {
    893         this.valueExpr = valueExpr;
    894     }
    895 
    896     /**
    897      * Resets attribute values for tag reuse.
    898      */
    899     public void release() {
    900         super.release();
    901         setAccesskeyExpr(null);
    902         setAltExpr(null);
    903         setAltKeyExpr(null);
    904         setBundleExpr(null);
    905         setDirExpr(null);
    906         setDisabledExpr(null);
    907         setErrorKeyExpr(null);
    908         setErrorStyleExpr(null);
    909         setErrorStyleClassExpr(null);
    910         setErrorStyleIdExpr(null);
    911         setIndexedExpr(null);
    912         setLangExpr(null);
    913         setMaxlengthExpr(null);
    914         setNameExpr(null);
    915         setOnblurExpr(null);
    916         setOnchangeExpr(null);
    917         setOnclickExpr(null);
    918         setOndblclickExpr(null);
    919         setOnfocusExpr(null);
    920         setOnkeydownExpr(null);
    921         setOnkeypressExpr(null);
    922         setOnkeyupExpr(null);
    923         setOnmousedownExpr(null);
    924         setOnmousemoveExpr(null);
    925         setOnmouseoutExpr(null);
    926         setOnmouseoverExpr(null);
    927         setOnmouseupExpr(null);
    928         setOnselectExpr(null);
    929         setPropertyExpr(null);
    930         setReadonlyExpr(null);
    931         setRedisplayExpr(null);
    932         setStyleExpr(null);
    933         setStyleClassExpr(null);
    934         setStyleIdExpr(null);
    935         setSizeExpr(null);
    936         setTabindexExpr(null);
    937         setTitleExpr(null);
    938         setTitleKeyExpr(null);
    939         setValueExpr(null);
    940     }
    941 
    942     /**
    943      * Process the start tag.
    944      *
    945      * @throws JspException if a JSP exception has occurred
    946      */
    947     public int doStartTag() throws JspException {
    948         evaluateExpressions();
    949 
    950         return (super.doStartTag());
    951     }
    952 
    953     /**
    954      * Processes all attribute values which use the JSTL expression evaluation
    955      * engine to determine their values.
    956      *
    957      * @throws JspException if a JSP exception has occurred
    958      */
    959     private void evaluateExpressions()
    960         throws JspException {
    961         String string = null;
    962         Boolean bool = null;
    963 
    964         if ((string =
    965                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    966                     pageContext)) != null) {
    967             setAccesskey(string);
    968         }
    969 
    970         if ((string =
    971                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    972             setAlt(string);
    973         }
    974 
    975         if ((string =
    976                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    977                     pageContext)) != null) {
    978             setAltKey(string);
    979         }
    980 
    981         if ((string =
    982                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    983                     pageContext)) != null) {
    984             setBundle(string);
    985         }
    986 
    987         if ((string =
    988                  EvalHelper.evalString("dir", getDirExpr(), this,
    989                          pageContext)) != null) {
    990          setDir(string);
    991         }
    992         
    993         if ((bool =
    994                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    995                     pageContext)) != null) {
    996             setDisabled(bool.booleanValue());
    997         }
    998 
    999         if ((string =
    1000                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    1001                     pageContext)) != null) {
    1002             setErrorKey(string);
    1003         }
    1004 
    1005         if ((string =
    1006                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    1007                     pageContext)) != null) {
    1008             setErrorStyle(string);
    1009         }
    1010 
    1011         if ((string =
    1012                 EvalHelper.evalString("errorStyleClass",
    1013                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    1014             setErrorStyleClass(string);
    1015         }
    1016 
    1017         if ((string =
    1018                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    1019                     this, pageContext)) != null) {
    1020             setErrorStyleId(string);
    1021         }
    1022 
    1023         if ((bool =
    1024                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    1025                     pageContext)) != null) {
    1026             setIndexed(bool.booleanValue());
    1027         }
    1028 
    1029         if ((string =
    1030               EvalHelper.evalString("lang", getLangExpr(), this,
    1031                       pageContext)) != null) {
    1032               setLang(string);
    1033         }
    1034 
    1035         if ((string =
    1036                 EvalHelper.evalString("maxlength", getMaxlengthExpr(), this,
    1037                     pageContext)) != null) {
    1038             setMaxlength(string);
    1039         }
    1040 
    1041         if ((string =
    1042                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    1043             setName(string);
    1044         }
    1045 
    1046         if ((string =
    1047                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    1048                     pageContext)) != null) {
    1049             setOnblur(string);
    1050         }
    1051 
    1052         if ((string =
    1053                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    1054                     pageContext)) != null) {
    1055             setOnchange(string);
    1056         }
    1057 
    1058         if ((string =
    1059                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1060                     pageContext)) != null) {
    1061             setOnclick(string);
    1062         }
    1063 
    1064         if ((string =
    1065                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1066                     pageContext)) != null) {
    1067             setOndblclick(string);
    1068         }
    1069 
    1070         if ((string =
    1071                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    1072                     pageContext)) != null) {
    1073             setOnfocus(string);
    1074         }
    1075 
    1076         if ((string =
    1077                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1078                     pageContext)) != null) {
    1079             setOnkeydown(string);
    1080         }
    1081 
    1082         if ((string =
    1083                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1084                     pageContext)) != null) {
    1085             setOnkeypress(string);
    1086         }
    1087 
    1088         if ((string =
    1089                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1090                     pageContext)) != null) {
    1091             setOnkeyup(string);
    1092         }
    1093 
    1094         if ((string =
    1095                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1096                     this, pageContext)) != null) {
    1097             setOnmousedown(string);
    1098         }
    1099 
    1100         if ((string =
    1101                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1102                     this, pageContext)) != null) {
    1103             setOnmousemove(string);
    1104         }
    1105 
    1106         if ((string =
    1107                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1108                     pageContext)) != null) {
    1109             setOnmouseout(string);
    1110         }
    1111 
    1112         if ((string =
    1113                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1114                     this, pageContext)) != null) {
    1115             setOnmouseover(string);
    1116         }
    1117 
    1118         if ((string =
    1119                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1120                     pageContext)) != null) {
    1121             setOnmouseup(string);
    1122         }
    1123 
    1124         if ((string =
    1125                 EvalHelper.evalString("onselect", getOnselectExpr(), this,
    1126                     pageContext)) != null) {
    1127             setOnselect(string);
    1128         }
    1129 
    1130         if ((string =
    1131                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1132                     pageContext)) != null) {
    1133             setProperty(string);
    1134         }
    1135 
    1136         if ((bool =
    1137                 EvalHelper.evalBoolean("readonly", getReadonlyExpr(), this,
    1138                     pageContext)) != null) {
    1139             setReadonly(bool.booleanValue());
    1140         }
    1141 
    1142         if ((bool =
    1143                 EvalHelper.evalBoolean("redisplay", getRedisplayExpr(), this,
    1144                     pageContext)) != null) {
    1145             setRedisplay(bool.booleanValue());
    1146         }
    1147 
    1148         if ((string =
    1149                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1150             setStyle(string);
    1151         }
    1152 
    1153         if ((string =
    1154                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1155                     pageContext)) != null) {
    1156             setStyleClass(string);
    1157         }
    1158 
    1159         if ((string =
    1160                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1161                     pageContext)) != null) {
    1162             setStyleId(string);
    1163         }
    1164 
    1165         if ((string =
    1166                 EvalHelper.evalString("size", getSizeExpr(), this, pageContext)) != null) {
    1167             setSize(string);
    1168         }
    1169 
    1170         if ((string =
    1171                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1172                     pageContext)) != null) {
    1173             setTabindex(string);
    1174         }
    1175 
    1176         if ((string =
    1177                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1178             setTitle(string);
    1179         }
    1180 
    1181         if ((string =
    1182                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1183                     pageContext)) != null) {
    1184             setTitleKey(string);
    1185         }
    1186 
    1187         if ((string =
    1188                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1189             setValue(string);
    1190         }
    1191     }
    1192 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
