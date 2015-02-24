[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELTextareaTag.html)


    1   /*
    2    * $Id: ELTextareaTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.TextareaTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag for input fields of type "textarea".
    30   *
    31   * <p> This class is a subclass of the class <code>org.apache.struts.taglib.html.md.TextareaTag</code>
    32   * which provides most of the described functionality.  This subclass allows
    33   * all attribute values to be specified as expressions utilizing the
    34   * JavaServer Pages Standard Library expression language.
    35   *
    36   * @version $Rev: 479635 $
    37   */
    38  public class ELTextareaTag extends TextareaTag {
    39      /**
    40       * Instance variable mapped to "accessKey" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String accessKeyExpr;
    44  
    45      /**
    46       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String altExpr;
    50  
    51      /**
    52       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String altKeyExpr;
    56  
    57      /**
    58       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String bundleExpr;
    62  
    63      /**
    64       * Instance variable mapped to "cols" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String colsExpr;
    68  
    69      /**
    70       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    71       * associated BeanInfo class.)
    72       */
    73      private String dirExpr;
    74  
    75      /**
    76       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    77       * associated BeanInfo class.)
    78       */
    79      private String disabledExpr;
    80  
    81      /**
    82       * Instance variable mapped to "errorKey" tag attribute. (Mapping set in
    83       * associated BeanInfo class.)
    84       */
    85      private String errorKeyExpr;
    86  
    87      /**
    88       * Instance variable mapped to "errorStyle" tag attribute. (Mapping set in
    89       * associated BeanInfo class.)
    90       */
    91      private String errorStyleExpr;
    92  
    93      /**
    94       * Instance variable mapped to "errorStyleClass" tag attribute. (Mapping
    95       * set in associated BeanInfo class.)
    96       */
    97      private String errorStyleClassExpr;
    98  
    99      /**
    100      * Instance variable mapped to "errorStyleId" tag attribute. (Mapping set
    101      * in associated BeanInfo class.)
    102      */
    103     private String errorStyleIdExpr;
    104 
    105     /**
    106      * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    107      * associated BeanInfo class.)
    108      */
    109     private String indexedExpr;
    110 
    111     /**
    112      * Instance variable mapped to "lang" tag attribute. (Mapping set in
    113      * associated BeanInfo class.)
    114      */
    115     private String langExpr;
    116 
    117     /**
    118      * Instance variable mapped to "name" tag attribute. (Mapping set in
    119      * associated BeanInfo class.)
    120      */
    121     private String nameExpr;
    122 
    123     /**
    124      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    125      * associated BeanInfo class.)
    126      */
    127     private String onblurExpr;
    128 
    129     /**
    130      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    131      * associated BeanInfo class.)
    132      */
    133     private String onchangeExpr;
    134 
    135     /**
    136      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    137      * associated BeanInfo class.)
    138      */
    139     private String onclickExpr;
    140 
    141     /**
    142      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    143      * associated BeanInfo class.)
    144      */
    145     private String ondblclickExpr;
    146 
    147     /**
    148      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    149      * associated BeanInfo class.)
    150      */
    151     private String onfocusExpr;
    152 
    153     /**
    154      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    155      * associated BeanInfo class.)
    156      */
    157     private String onkeydownExpr;
    158 
    159     /**
    160      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    161      * associated BeanInfo class.)
    162      */
    163     private String onkeypressExpr;
    164 
    165     /**
    166      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    167      * associated BeanInfo class.)
    168      */
    169     private String onkeyupExpr;
    170 
    171     /**
    172      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    173      * in associated BeanInfo class.)
    174      */
    175     private String onmousedownExpr;
    176 
    177     /**
    178      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    179      * in associated BeanInfo class.)
    180      */
    181     private String onmousemoveExpr;
    182 
    183     /**
    184      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    185      * associated BeanInfo class.)
    186      */
    187     private String onmouseoutExpr;
    188 
    189     /**
    190      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    191      * in associated BeanInfo class.)
    192      */
    193     private String onmouseoverExpr;
    194 
    195     /**
    196      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    197      * associated BeanInfo class.)
    198      */
    199     private String onmouseupExpr;
    200 
    201     /**
    202      * Instance variable mapped to "onselect" tag attribute. (Mapping set in
    203      * associated BeanInfo class.)
    204      */
    205     private String onselectExpr;
    206 
    207     /**
    208      * Instance variable mapped to "property" tag attribute. (Mapping set in
    209      * associated BeanInfo class.)
    210      */
    211     private String propertyExpr;
    212 
    213     /**
    214      * Instance variable mapped to "readonly" tag attribute. (Mapping set in
    215      * associated BeanInfo class.)
    216      */
    217     private String readonlyExpr;
    218 
    219     /**
    220      * Instance variable mapped to "rows" tag attribute. (Mapping set in
    221      * associated BeanInfo class.)
    222      */
    223     private String rowsExpr;
    224 
    225     /**
    226      * Instance variable mapped to "style" tag attribute. (Mapping set in
    227      * associated BeanInfo class.)
    228      */
    229     private String styleExpr;
    230 
    231     /**
    232      * Instance variable mapped to "size" tag attribute. (Mapping set in
    233      * associated BeanInfo class.)
    234      */
    235     private String sizeExpr;
    236 
    237     /**
    238      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    239      * associated BeanInfo class.)
    240      */
    241     private String styleClassExpr;
    242 
    243     /**
    244      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    245      * associated BeanInfo class.)
    246      */
    247     private String styleIdExpr;
    248 
    249     /**
    250      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    251      * associated BeanInfo class.)
    252      */
    253     private String tabindexExpr;
    254 
    255     /**
    256      * Instance variable mapped to "title" tag attribute. (Mapping set in
    257      * associated BeanInfo class.)
    258      */
    259     private String titleExpr;
    260 
    261     /**
    262      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    263      * associated BeanInfo class.)
    264      */
    265     private String titleKeyExpr;
    266 
    267     /**
    268      * Instance variable mapped to "value" tag attribute. (Mapping set in
    269      * associated BeanInfo class.)
    270      */
    271     private String valueExpr;
    272 
    273     /**
    274      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    275      * BeanInfo class.)
    276      */
    277     public String getAccesskeyExpr() {
    278         return (accessKeyExpr);
    279     }
    280 
    281     /**
    282      * Getter method for "alt" tag attribute. (Mapping set in associated
    283      * BeanInfo class.)
    284      */
    285     public String getAltExpr() {
    286         return (altExpr);
    287     }
    288 
    289     /**
    290      * Getter method for "altKey" tag attribute. (Mapping set in associated
    291      * BeanInfo class.)
    292      */
    293     public String getAltKeyExpr() {
    294         return (altKeyExpr);
    295     }
    296 
    297     /**
    298      * Getter method for "bundle" tag attribute. (Mapping set in associated
    299      * BeanInfo class.)
    300      */
    301     public String getBundleExpr() {
    302         return (bundleExpr);
    303     }
    304 
    305     /**
    306      * Getter method for "cols" tag attribute. (Mapping set in associated
    307      * BeanInfo class.)
    308      */
    309     public String getColsExpr() {
    310         return (colsExpr);
    311     }
    312 
    313     /**
    314      * Getter method for "dir" tag attribute. (Mapping set in associated
    315      * BeanInfo class.)
    316      */
    317     public String getDirExpr() {
    318         return (dirExpr);
    319     }
    320 
    321     /**
    322      * Getter method for "disabled" tag attribute. (Mapping set in associated
    323      * BeanInfo class.)
    324      */
    325     public String getDisabledExpr() {
    326         return (disabledExpr);
    327     }
    328 
    329     /**
    330      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    331      * BeanInfo class.)
    332      */
    333     public String getErrorKeyExpr() {
    334         return (errorKeyExpr);
    335     }
    336 
    337     /**
    338      * Getter method for "errorStyle" tag attribute. (Mapping set in
    339      * associated BeanInfo class.)
    340      */
    341     public String getErrorStyleExpr() {
    342         return (errorStyleExpr);
    343     }
    344 
    345     /**
    346      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    347      * associated BeanInfo class.)
    348      */
    349     public String getErrorStyleClassExpr() {
    350         return (errorStyleClassExpr);
    351     }
    352 
    353     /**
    354      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    355      * associated BeanInfo class.)
    356      */
    357     public String getErrorStyleIdExpr() {
    358         return (errorStyleIdExpr);
    359     }
    360 
    361     /**
    362      * Getter method for "indexed" tag attribute. (Mapping set in associated
    363      * BeanInfo class.)
    364      */
    365     public String getIndexedExpr() {
    366         return (indexedExpr);
    367     }
    368 
    369     /**
    370      * Getter method for "lang" tag attribute. (Mapping set in associated
    371      * BeanInfo class.)
    372      */
    373     public String getLangExpr() {
    374         return (langExpr);
    375     }
    376 
    377     /**
    378      * Getter method for "name" tag attribute. (Mapping set in associated
    379      * BeanInfo class.)
    380      */
    381     public String getNameExpr() {
    382         return (nameExpr);
    383     }
    384 
    385     /**
    386      * Getter method for "onblur" tag attribute. (Mapping set in associated
    387      * BeanInfo class.)
    388      */
    389     public String getOnblurExpr() {
    390         return (onblurExpr);
    391     }
    392 
    393     /**
    394      * Getter method for "onchange" tag attribute. (Mapping set in associated
    395      * BeanInfo class.)
    396      */
    397     public String getOnchangeExpr() {
    398         return (onchangeExpr);
    399     }
    400 
    401     /**
    402      * Getter method for "onclick" tag attribute. (Mapping set in associated
    403      * BeanInfo class.)
    404      */
    405     public String getOnclickExpr() {
    406         return (onclickExpr);
    407     }
    408 
    409     /**
    410      * Getter method for "ondblclick" tag attribute. (Mapping set in
    411      * associated BeanInfo class.)
    412      */
    413     public String getOndblclickExpr() {
    414         return (ondblclickExpr);
    415     }
    416 
    417     /**
    418      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    419      * BeanInfo class.)
    420      */
    421     public String getOnfocusExpr() {
    422         return (onfocusExpr);
    423     }
    424 
    425     /**
    426      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    427      * BeanInfo class.)
    428      */
    429     public String getOnkeydownExpr() {
    430         return (onkeydownExpr);
    431     }
    432 
    433     /**
    434      * Getter method for "onkeypress" tag attribute. (Mapping set in
    435      * associated BeanInfo class.)
    436      */
    437     public String getOnkeypressExpr() {
    438         return (onkeypressExpr);
    439     }
    440 
    441     /**
    442      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    443      * BeanInfo class.)
    444      */
    445     public String getOnkeyupExpr() {
    446         return (onkeyupExpr);
    447     }
    448 
    449     /**
    450      * Getter method for "onmousedown" tag attribute. (Mapping set in
    451      * associated BeanInfo class.)
    452      */
    453     public String getOnmousedownExpr() {
    454         return (onmousedownExpr);
    455     }
    456 
    457     /**
    458      * Getter method for "onmousemove" tag attribute. (Mapping set in
    459      * associated BeanInfo class.)
    460      */
    461     public String getOnmousemoveExpr() {
    462         return (onmousemoveExpr);
    463     }
    464 
    465     /**
    466      * Getter method for "onmouseout" tag attribute. (Mapping set in
    467      * associated BeanInfo class.)
    468      */
    469     public String getOnmouseoutExpr() {
    470         return (onmouseoutExpr);
    471     }
    472 
    473     /**
    474      * Getter method for "onmouseover" tag attribute. (Mapping set in
    475      * associated BeanInfo class.)
    476      */
    477     public String getOnmouseoverExpr() {
    478         return (onmouseoverExpr);
    479     }
    480 
    481     /**
    482      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    483      * BeanInfo class.)
    484      */
    485     public String getOnmouseupExpr() {
    486         return (onmouseupExpr);
    487     }
    488 
    489     /**
    490      * Getter method for "onselect" tag attribute. (Mapping set in associated
    491      * BeanInfo class.)
    492      */
    493     public String getOnselectExpr() {
    494         return (onselectExpr);
    495     }
    496 
    497     /**
    498      * Getter method for "property" tag attribute. (Mapping set in associated
    499      * BeanInfo class.)
    500      */
    501     public String getPropertyExpr() {
    502         return (propertyExpr);
    503     }
    504 
    505     /**
    506      * Getter method for "readonly" tag attribute. (Mapping set in associated
    507      * BeanInfo class.)
    508      */
    509     public String getReadonlyExpr() {
    510         return (readonlyExpr);
    511     }
    512 
    513     /**
    514      * Getter method for "rows" tag attribute. (Mapping set in associated
    515      * BeanInfo class.)
    516      */
    517     public String getRowsExpr() {
    518         return (rowsExpr);
    519     }
    520 
    521     /**
    522      * Getter method for "style" tag attribute. (Mapping set in associated
    523      * BeanInfo class.)
    524      */
    525     public String getStyleExpr() {
    526         return (styleExpr);
    527     }
    528 
    529     /**
    530      * Getter method for "size" tag attribute. (Mapping set in associated
    531      * BeanInfo class.)
    532      */
    533     public String getSizeExpr() {
    534         return (sizeExpr);
    535     }
    536 
    537     /**
    538      * Getter method for "styleClass" tag attribute. (Mapping set in
    539      * associated BeanInfo class.)
    540      */
    541     public String getStyleClassExpr() {
    542         return (styleClassExpr);
    543     }
    544 
    545     /**
    546      * Getter method for "styleId" tag attribute. (Mapping set in associated
    547      * BeanInfo class.)
    548      */
    549     public String getStyleIdExpr() {
    550         return (styleIdExpr);
    551     }
    552 
    553     /**
    554      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    555      * BeanInfo class.)
    556      */
    557     public String getTabindexExpr() {
    558         return (tabindexExpr);
    559     }
    560 
    561     /**
    562      * Getter method for "title" tag attribute. (Mapping set in associated
    563      * BeanInfo class.)
    564      */
    565     public String getTitleExpr() {
    566         return (titleExpr);
    567     }
    568 
    569     /**
    570      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    571      * BeanInfo class.)
    572      */
    573     public String getTitleKeyExpr() {
    574         return (titleKeyExpr);
    575     }
    576 
    577     /**
    578      * Getter method for "value" tag attribute. (Mapping set in associated
    579      * BeanInfo class.)
    580      */
    581     public String getValueExpr() {
    582         return (valueExpr);
    583     }
    584 
    585     /**
    586      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    587      * BeanInfo class.)
    588      */
    589     public void setAccesskeyExpr(String accessKeyExpr) {
    590         this.accessKeyExpr = accessKeyExpr;
    591     }
    592 
    593     /**
    594      * Setter method for "alt" tag attribute. (Mapping set in associated
    595      * BeanInfo class.)
    596      */
    597     public void setAltExpr(String altExpr) {
    598         this.altExpr = altExpr;
    599     }
    600 
    601     /**
    602      * Setter method for "altKey" tag attribute. (Mapping set in associated
    603      * BeanInfo class.)
    604      */
    605     public void setAltKeyExpr(String altKeyExpr) {
    606         this.altKeyExpr = altKeyExpr;
    607     }
    608 
    609     /**
    610      * Setter method for "bundle" tag attribute. (Mapping set in associated
    611      * BeanInfo class.)
    612      */
    613     public void setBundleExpr(String bundleExpr) {
    614         this.bundleExpr = bundleExpr;
    615     }
    616 
    617     /**
    618      * Setter method for "cols" tag attribute. (Mapping set in associated
    619      * BeanInfo class.)
    620      */
    621     public void setColsExpr(String colsExpr) {
    622         this.colsExpr = colsExpr;
    623     }
    624 
    625     /**
    626      * Setter method for "dir" tag attribute. (Mapping set in associated
    627      * BeanInfo class.)
    628      */
    629     public void setDirExpr(String dirExpr) {
    630         this.dirExpr = dirExpr;
    631     }
    632 
    633     /**
    634      * Setter method for "disabled" tag attribute. (Mapping set in associated
    635      * BeanInfo class.)
    636      */
    637     public void setDisabledExpr(String disabledExpr) {
    638         this.disabledExpr = disabledExpr;
    639     }
    640 
    641     /**
    642      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    643      * BeanInfo class.)
    644      */
    645     public void setErrorKeyExpr(String errorKeyExpr) {
    646         this.errorKeyExpr = errorKeyExpr;
    647     }
    648 
    649     /**
    650      * Setter method for "errorStyle" tag attribute. (Mapping set in
    651      * associated BeanInfo class.)
    652      */
    653     public void setErrorStyleExpr(String errorStyleExpr) {
    654         this.errorStyleExpr = errorStyleExpr;
    655     }
    656 
    657     /**
    658      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    659      * associated BeanInfo class.)
    660      */
    661     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    662         this.errorStyleClassExpr = errorStyleClassExpr;
    663     }
    664 
    665     /**
    666      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    667      * associated BeanInfo class.)
    668      */
    669     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    670         this.errorStyleIdExpr = errorStyleIdExpr;
    671     }
    672 
    673     /**
    674      * Setter method for "indexed" tag attribute. (Mapping set in associated
    675      * BeanInfo class.)
    676      */
    677     public void setIndexedExpr(String indexedExpr) {
    678         this.indexedExpr = indexedExpr;
    679     }
    680 
    681     /**
    682      * Setter method for "lang" tag attribute. (Mapping set in associated
    683      * BeanInfo class.)
    684      */
    685     public void setLangExpr(String langExpr) {
    686         this.langExpr = langExpr;
    687     }
    688 
    689     /**
    690      * Setter method for "name" tag attribute. (Mapping set in associated
    691      * BeanInfo class.)
    692      */
    693     public void setNameExpr(String nameExpr) {
    694         this.nameExpr = nameExpr;
    695     }
    696 
    697     /**
    698      * Setter method for "onblur" tag attribute. (Mapping set in associated
    699      * BeanInfo class.)
    700      */
    701     public void setOnblurExpr(String onblurExpr) {
    702         this.onblurExpr = onblurExpr;
    703     }
    704 
    705     /**
    706      * Setter method for "onchange" tag attribute. (Mapping set in associated
    707      * BeanInfo class.)
    708      */
    709     public void setOnchangeExpr(String onchangeExpr) {
    710         this.onchangeExpr = onchangeExpr;
    711     }
    712 
    713     /**
    714      * Setter method for "onclick" tag attribute. (Mapping set in associated
    715      * BeanInfo class.)
    716      */
    717     public void setOnclickExpr(String onclickExpr) {
    718         this.onclickExpr = onclickExpr;
    719     }
    720 
    721     /**
    722      * Setter method for "ondblclick" tag attribute. (Mapping set in
    723      * associated BeanInfo class.)
    724      */
    725     public void setOndblclickExpr(String ondblclickExpr) {
    726         this.ondblclickExpr = ondblclickExpr;
    727     }
    728 
    729     /**
    730      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    731      * BeanInfo class.)
    732      */
    733     public void setOnfocusExpr(String onfocusExpr) {
    734         this.onfocusExpr = onfocusExpr;
    735     }
    736 
    737     /**
    738      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    739      * BeanInfo class.)
    740      */
    741     public void setOnkeydownExpr(String onkeydownExpr) {
    742         this.onkeydownExpr = onkeydownExpr;
    743     }
    744 
    745     /**
    746      * Setter method for "onkeypress" tag attribute. (Mapping set in
    747      * associated BeanInfo class.)
    748      */
    749     public void setOnkeypressExpr(String onkeypressExpr) {
    750         this.onkeypressExpr = onkeypressExpr;
    751     }
    752 
    753     /**
    754      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    755      * BeanInfo class.)
    756      */
    757     public void setOnkeyupExpr(String onkeyupExpr) {
    758         this.onkeyupExpr = onkeyupExpr;
    759     }
    760 
    761     /**
    762      * Setter method for "onmousedown" tag attribute. (Mapping set in
    763      * associated BeanInfo class.)
    764      */
    765     public void setOnmousedownExpr(String onmousedownExpr) {
    766         this.onmousedownExpr = onmousedownExpr;
    767     }
    768 
    769     /**
    770      * Setter method for "onmousemove" tag attribute. (Mapping set in
    771      * associated BeanInfo class.)
    772      */
    773     public void setOnmousemoveExpr(String onmousemoveExpr) {
    774         this.onmousemoveExpr = onmousemoveExpr;
    775     }
    776 
    777     /**
    778      * Setter method for "onmouseout" tag attribute. (Mapping set in
    779      * associated BeanInfo class.)
    780      */
    781     public void setOnmouseoutExpr(String onmouseoutExpr) {
    782         this.onmouseoutExpr = onmouseoutExpr;
    783     }
    784 
    785     /**
    786      * Setter method for "onmouseover" tag attribute. (Mapping set in
    787      * associated BeanInfo class.)
    788      */
    789     public void setOnmouseoverExpr(String onmouseoverExpr) {
    790         this.onmouseoverExpr = onmouseoverExpr;
    791     }
    792 
    793     /**
    794      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    795      * BeanInfo class.)
    796      */
    797     public void setOnmouseupExpr(String onmouseupExpr) {
    798         this.onmouseupExpr = onmouseupExpr;
    799     }
    800 
    801     /**
    802      * Setter method for "onselect" tag attribute. (Mapping set in associated
    803      * BeanInfo class.)
    804      */
    805     public void setOnselectExpr(String onselectExpr) {
    806         this.onselectExpr = onselectExpr;
    807     }
    808 
    809     /**
    810      * Setter method for "property" tag attribute. (Mapping set in associated
    811      * BeanInfo class.)
    812      */
    813     public void setPropertyExpr(String propertyExpr) {
    814         this.propertyExpr = propertyExpr;
    815     }
    816 
    817     /**
    818      * Setter method for "readonly" tag attribute. (Mapping set in associated
    819      * BeanInfo class.)
    820      */
    821     public void setReadonlyExpr(String readonlyExpr) {
    822         this.readonlyExpr = readonlyExpr;
    823     }
    824 
    825     /**
    826      * Setter method for "rows" tag attribute. (Mapping set in associated
    827      * BeanInfo class.)
    828      */
    829     public void setRowsExpr(String rowsExpr) {
    830         this.rowsExpr = rowsExpr;
    831     }
    832 
    833     /**
    834      * Setter method for "style" tag attribute. (Mapping set in associated
    835      * BeanInfo class.)
    836      */
    837     public void setStyleExpr(String styleExpr) {
    838         this.styleExpr = styleExpr;
    839     }
    840 
    841     /**
    842      * Setter method for "size" tag attribute. (Mapping set in associated
    843      * BeanInfo class.)
    844      */
    845     public void setSizeExpr(String sizeExpr) {
    846         this.sizeExpr = sizeExpr;
    847     }
    848 
    849     /**
    850      * Setter method for "styleClass" tag attribute. (Mapping set in
    851      * associated BeanInfo class.)
    852      */
    853     public void setStyleClassExpr(String styleClassExpr) {
    854         this.styleClassExpr = styleClassExpr;
    855     }
    856 
    857     /**
    858      * Setter method for "styleId" tag attribute. (Mapping set in associated
    859      * BeanInfo class.)
    860      */
    861     public void setStyleIdExpr(String styleIdExpr) {
    862         this.styleIdExpr = styleIdExpr;
    863     }
    864 
    865     /**
    866      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    867      * BeanInfo class.)
    868      */
    869     public void setTabindexExpr(String tabindexExpr) {
    870         this.tabindexExpr = tabindexExpr;
    871     }
    872 
    873     /**
    874      * Setter method for "title" tag attribute. (Mapping set in associated
    875      * BeanInfo class.)
    876      */
    877     public void setTitleExpr(String titleExpr) {
    878         this.titleExpr = titleExpr;
    879     }
    880 
    881     /**
    882      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    883      * BeanInfo class.)
    884      */
    885     public void setTitleKeyExpr(String titleKeyExpr) {
    886         this.titleKeyExpr = titleKeyExpr;
    887     }
    888 
    889     /**
    890      * Setter method for "value" tag attribute. (Mapping set in associated
    891      * BeanInfo class.)
    892      */
    893     public void setValueExpr(String valueExpr) {
    894         this.valueExpr = valueExpr;
    895     }
    896 
    897     /**
    898      * Resets attribute values for tag reuse.
    899      */
    900     public void release() {
    901         super.release();
    902         setAccesskeyExpr(null);
    903         setAltExpr(null);
    904         setAltKeyExpr(null);
    905         setBundleExpr(null);
    906         setColsExpr(null);
    907         setDirExpr(null);
    908         setDisabledExpr(null);
    909         setErrorKeyExpr(null);
    910         setErrorStyleExpr(null);
    911         setErrorStyleClassExpr(null);
    912         setErrorStyleIdExpr(null);
    913         setIndexedExpr(null);
    914         setLangExpr(null);
    915         setNameExpr(null);
    916         setOnblurExpr(null);
    917         setOnchangeExpr(null);
    918         setOnclickExpr(null);
    919         setOndblclickExpr(null);
    920         setOnfocusExpr(null);
    921         setOnkeydownExpr(null);
    922         setOnkeypressExpr(null);
    923         setOnkeyupExpr(null);
    924         setOnmousedownExpr(null);
    925         setOnmousemoveExpr(null);
    926         setOnmouseoutExpr(null);
    927         setOnmouseoverExpr(null);
    928         setOnmouseupExpr(null);
    929         setOnselectExpr(null);
    930         setPropertyExpr(null);
    931         setReadonlyExpr(null);
    932         setRowsExpr(null);
    933         setStyleExpr(null);
    934         setSizeExpr(null);
    935         setStyleClassExpr(null);
    936         setStyleIdExpr(null);
    937         setTabindexExpr(null);
    938         setTitleExpr(null);
    939         setTitleKeyExpr(null);
    940         setValueExpr(null);
    941     }
    942 
    943     /**
    944      * Process the start tag.
    945      *
    946      * @throws JspException if a JSP exception has occurred
    947      */
    948     public int doStartTag() throws JspException {
    949         evaluateExpressions();
    950 
    951         return (super.doStartTag());
    952     }
    953 
    954     /**
    955      * Processes all attribute values which use the JSTL expression evaluation
    956      * engine to determine their values.
    957      *
    958      * @throws JspException if a JSP exception has occurred
    959      */
    960     private void evaluateExpressions()
    961         throws JspException {
    962         String string = null;
    963         Boolean bool = null;
    964 
    965         if ((string =
    966                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    967                     pageContext)) != null) {
    968             setAccesskey(string);
    969         }
    970 
    971         if ((string =
    972                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    973             setAlt(string);
    974         }
    975 
    976         if ((string =
    977                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    978                     pageContext)) != null) {
    979             setAltKey(string);
    980         }
    981 
    982         if ((string =
    983                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    984                     pageContext)) != null) {
    985             setBundle(string);
    986         }
    987 
    988         if ((string =
    989                 EvalHelper.evalString("cols", getColsExpr(), this, pageContext)) != null) {
    990             setCols(string);
    991         }
    992 
    993         if ((string =
    994                  EvalHelper.evalString("dir", getDirExpr(), this,
    995                          pageContext)) != null) {
    996          setDir(string);
    997         }
    998         
    999         if ((bool =
    1000                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    1001                     pageContext)) != null) {
    1002             setDisabled(bool.booleanValue());
    1003         }
    1004 
    1005         if ((string =
    1006                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    1007                     pageContext)) != null) {
    1008             setErrorKey(string);
    1009         }
    1010 
    1011         if ((string =
    1012                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    1013                     pageContext)) != null) {
    1014             setErrorStyle(string);
    1015         }
    1016 
    1017         if ((string =
    1018                 EvalHelper.evalString("errorStyleClass",
    1019                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    1020             setErrorStyleClass(string);
    1021         }
    1022 
    1023         if ((string =
    1024                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    1025                     this, pageContext)) != null) {
    1026             setErrorStyleId(string);
    1027         }
    1028 
    1029         if ((bool =
    1030                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    1031                     pageContext)) != null) {
    1032             setIndexed(bool.booleanValue());
    1033         }
    1034 
    1035         if ((string =
    1036               EvalHelper.evalString("lang", getLangExpr(), this,
    1037                       pageContext)) != null) {
    1038               setLang(string);
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
    1142         if ((string =
    1143                 EvalHelper.evalString("rows", getRowsExpr(), this, pageContext)) != null) {
    1144             setRows(string);
    1145         }
    1146 
    1147         if ((string =
    1148                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1149             setStyle(string);
    1150         }
    1151 
    1152         if ((string =
    1153                 EvalHelper.evalString("size", getSizeExpr(), this, pageContext)) != null) {
    1154             setSize(string);
    1155         }
    1156 
    1157         if ((string =
    1158                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1159                     pageContext)) != null) {
    1160             setStyleClass(string);
    1161         }
    1162 
    1163         if ((string =
    1164                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1165                     pageContext)) != null) {
    1166             setStyleId(string);
    1167         }
    1168 
    1169         if ((string =
    1170                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1171                     pageContext)) != null) {
    1172             setTabindex(string);
    1173         }
    1174 
    1175         if ((string =
    1176                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1177             setTitle(string);
    1178         }
    1179 
    1180         if ((string =
    1181                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1182                     pageContext)) != null) {
    1183             setTitleKey(string);
    1184         }
    1185 
    1186         if ((string =
    1187                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    1188             setValue(string);
    1189         }
    1190     }
    1191 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
