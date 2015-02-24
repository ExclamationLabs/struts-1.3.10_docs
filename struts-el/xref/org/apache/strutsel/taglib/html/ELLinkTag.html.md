[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELLinkTag.html)


    1   /*
    2    * $Id: ELLinkTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.LinkTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Generate a URL-encoded hyperlink to the specified URI. <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.html.md.LinkTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELLinkTag extends LinkTag {
    38      /**
    39       * Instance variable mapped to "accessKey" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String accessKeyExpr;
    43  
    44      /**
    45       * Instance variable mapped to "action" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String actionExpr;
    49  
    50      /**
    51       * Instance variable mapped to "module" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String moduleExpr;
    55  
    56      /**
    57       * Instance variable mapped to "anchor" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String anchorExpr;
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
    75       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String forwardExpr;
    79  
    80      /**
    81       * Instance variable mapped to "href" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String hrefExpr;
    85  
    86      /**
    87       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String indexedExpr;
    91  
    92      /**
    93       * Instance variable mapped to "indexId" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String indexIdExpr;
    97  
    98      /**
    99       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String langExpr;
    103 
    104     /**
    105      * Instance variable mapped to "linkName" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String linkNameExpr;
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
    195      * Instance variable mapped to "paramId" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String paramIdExpr;
    199 
    200     /**
    201      * Instance variable mapped to "paramName" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String paramNameExpr;
    205 
    206     /**
    207      * Instance variable mapped to "paramProperty" tag attribute. (Mapping set
    208      * in associated BeanInfo class.)
    209      */
    210     private String paramPropertyExpr;
    211 
    212     /**
    213      * Instance variable mapped to "paramScope" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String paramScopeExpr;
    217 
    218     /**
    219      * Instance variable mapped to "property" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     private String propertyExpr;
    223 
    224     /**
    225      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    226      * associated BeanInfo class.)
    227      */
    228     private String scopeExpr;
    229 
    230     /**
    231      * Instance variable mapped to "style" tag attribute. (Mapping set in
    232      * associated BeanInfo class.)
    233      */
    234     private String styleExpr;
    235 
    236     /**
    237      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    238      * associated BeanInfo class.)
    239      */
    240     private String styleClassExpr;
    241 
    242     /**
    243      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    244      * associated BeanInfo class.)
    245      */
    246     private String styleIdExpr;
    247 
    248     /**
    249      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    250      * associated BeanInfo class.)
    251      */
    252     private String tabindexExpr;
    253 
    254     /**
    255      * Instance variable mapped to "target" tag attribute. (Mapping set in
    256      * associated BeanInfo class.)
    257      */
    258     private String targetExpr;
    259 
    260     /**
    261      * Instance variable mapped to "title" tag attribute. (Mapping set in
    262      * associated BeanInfo class.)
    263      */
    264     private String titleExpr;
    265 
    266     /**
    267      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    268      * associated BeanInfo class.)
    269      */
    270     private String titleKeyExpr;
    271 
    272     /**
    273      * Instance variable mapped to "transaction" tag attribute. (Mapping set
    274      * in associated BeanInfo class.)
    275      */
    276     private String transactionExpr;
    277 
    278     /**
    279      * Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping
    280      * set in associated BeanInfo class.)
    281      */
    282     private String useLocalEncodingExpr;
    283 
    284     /**
    285      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    286      * BeanInfo class.)
    287      */
    288     public String getAccesskeyExpr() {
    289         return (accessKeyExpr);
    290     }
    291 
    292     /**
    293      * Getter method for "action" tag attribute. (Mapping set in associated
    294      * BeanInfo class.)
    295      */
    296     public String getActionExpr() {
    297         return (actionExpr);
    298     }
    299 
    300     /**
    301      * Getter method for "module" tag attribute. (Mapping set in associated
    302      * BeanInfo class.)
    303      */
    304     public String getModuleExpr() {
    305         return (moduleExpr);
    306     }
    307 
    308     /**
    309      * Getter method for "anchor" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public String getAnchorExpr() {
    313         return (anchorExpr);
    314     }
    315 
    316     /**
    317      * Getter method for "bundle" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getBundleExpr() {
    321         return (bundleExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "dir" tag attribute. (Mapping set in associated
    326      * BeanInfo class.)
    327      */
    328     public String getDirExpr() {
    329         return (dirExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "forward" tag attribute. (Mapping set in associated
    334      * BeanInfo class.)
    335      */
    336     public String getForwardExpr() {
    337         return (forwardExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "href" tag attribute. (Mapping set in associated
    342      * BeanInfo class.)
    343      */
    344     public String getHrefExpr() {
    345         return (hrefExpr);
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
    357      * Getter method for "indexId" tag attribute. (Mapping set in associated
    358      * BeanInfo class.)
    359      */
    360     public String getIndexIdExpr() {
    361         return (indexIdExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "lang" tag attribute. (Mapping set in associated
    366      * BeanInfo class.)
    367      */
    368     public String getLangExpr() {
    369         return (langExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "linkName" tag attribute. (Mapping set in associated
    374      * BeanInfo class.)
    375      */
    376     public String getLinkNameExpr() {
    377         return (linkNameExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "name" tag attribute. (Mapping set in associated
    382      * BeanInfo class.)
    383      */
    384     public String getNameExpr() {
    385         return (nameExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "onblur" tag attribute. (Mapping set in associated
    390      * BeanInfo class.)
    391      */
    392     public String getOnblurExpr() {
    393         return (onblurExpr);
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
    485      * Getter method for "page" tag attribute. (Mapping set in associated
    486      * BeanInfo class.)
    487      */
    488     public String getPageExpr() {
    489         return (pageExpr);
    490     }
    491 
    492     /**
    493      * Getter method for "paramId" tag attribute. (Mapping set in associated
    494      * BeanInfo class.)
    495      */
    496     public String getParamIdExpr() {
    497         return (paramIdExpr);
    498     }
    499 
    500     /**
    501      * Getter method for "paramName" tag attribute. (Mapping set in associated
    502      * BeanInfo class.)
    503      */
    504     public String getParamNameExpr() {
    505         return (paramNameExpr);
    506     }
    507 
    508     /**
    509      * Getter method for "paramProperty" tag attribute. (Mapping set in
    510      * associated BeanInfo class.)
    511      */
    512     public String getParamPropertyExpr() {
    513         return (paramPropertyExpr);
    514     }
    515 
    516     /**
    517      * Getter method for "paramScope" tag attribute. (Mapping set in
    518      * associated BeanInfo class.)
    519      */
    520     public String getParamScopeExpr() {
    521         return (paramScopeExpr);
    522     }
    523 
    524     /**
    525      * Getter method for "property" tag attribute. (Mapping set in associated
    526      * BeanInfo class.)
    527      */
    528     public String getPropertyExpr() {
    529         return (propertyExpr);
    530     }
    531 
    532     /**
    533      * Getter method for "scope" tag attribute. (Mapping set in associated
    534      * BeanInfo class.)
    535      */
    536     public String getScopeExpr() {
    537         return (scopeExpr);
    538     }
    539 
    540     /**
    541      * Getter method for "style" tag attribute. (Mapping set in associated
    542      * BeanInfo class.)
    543      */
    544     public String getStyleExpr() {
    545         return (styleExpr);
    546     }
    547 
    548     /**
    549      * Getter method for "styleClass" tag attribute. (Mapping set in
    550      * associated BeanInfo class.)
    551      */
    552     public String getStyleClassExpr() {
    553         return (styleClassExpr);
    554     }
    555 
    556     /**
    557      * Getter method for "styleId" tag attribute. (Mapping set in associated
    558      * BeanInfo class.)
    559      */
    560     public String getStyleIdExpr() {
    561         return (styleIdExpr);
    562     }
    563 
    564     /**
    565      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public String getTabindexExpr() {
    569         return (tabindexExpr);
    570     }
    571 
    572     /**
    573      * Getter method for "target" tag attribute. (Mapping set in associated
    574      * BeanInfo class.)
    575      */
    576     public String getTargetExpr() {
    577         return (targetExpr);
    578     }
    579 
    580     /**
    581      * Getter method for "title" tag attribute. (Mapping set in associated
    582      * BeanInfo class.)
    583      */
    584     public String getTitleExpr() {
    585         return (titleExpr);
    586     }
    587 
    588     /**
    589      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    590      * BeanInfo class.)
    591      */
    592     public String getTitleKeyExpr() {
    593         return (titleKeyExpr);
    594     }
    595 
    596     /**
    597      * Getter method for "transaction" tag attribute. (Mapping set in
    598      * associated BeanInfo class.)
    599      */
    600     public String getTransactionExpr() {
    601         return (transactionExpr);
    602     }
    603 
    604     /**
    605      * Getter method for "useLocalEncoding" tag attribute. (Mapping set in
    606      * associated BeanInfo class.)
    607      */
    608     public String getUseLocalEncodingExpr() {
    609         return (useLocalEncodingExpr);
    610     }
    611 
    612     /**
    613      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public void setAccesskeyExpr(String accessKeyExpr) {
    617         this.accessKeyExpr = accessKeyExpr;
    618     }
    619 
    620     /**
    621      * Setter method for "action" tag attribute. (Mapping set in associated
    622      * BeanInfo class.)
    623      */
    624     public void setActionExpr(String actionExpr) {
    625         this.actionExpr = actionExpr;
    626     }
    627 
    628     /**
    629      * Setter method for "module" tag attribute. (Mapping set in associated
    630      * BeanInfo class.)
    631      */
    632     public void setModuleExpr(String moduleExpr) {
    633         this.moduleExpr = moduleExpr;
    634     }
    635 
    636     /**
    637      * Setter method for "anchor" tag attribute. (Mapping set in associated
    638      * BeanInfo class.)
    639      */
    640     public void setAnchorExpr(String anchorExpr) {
    641         this.anchorExpr = anchorExpr;
    642     }
    643 
    644     /**
    645      * Setter method for "bundle" tag attribute. (Mapping set in associated
    646      * BeanInfo class.)
    647      */
    648     public void setBundleExpr(String bundleExpr) {
    649         this.bundleExpr = bundleExpr;
    650     }
    651 
    652     /**
    653      * Setter method for "dir" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public void setDirExpr(String dirExpr) {
    657         this.dirExpr = dirExpr;
    658     }
    659 
    660     /**
    661      * Setter method for "forward" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public void setForwardExpr(String forwardExpr) {
    665         this.forwardExpr = forwardExpr;
    666     }
    667 
    668     /**
    669      * Setter method for "href" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setHrefExpr(String hrefExpr) {
    673         this.hrefExpr = hrefExpr;
    674     }
    675 
    676     /**
    677      * Setter method for "indexed" tag attribute. (Mapping set in associated
    678      * BeanInfo class.)
    679      */
    680     public void setIndexedExpr(String indexedExpr) {
    681         this.indexedExpr = indexedExpr;
    682     }
    683 
    684     /**
    685      * Setter method for "indexId" tag attribute. (Mapping set in associated
    686      * BeanInfo class.)
    687      */
    688     public void setIndexIdExpr(String indexIdExpr) {
    689         this.indexIdExpr = indexIdExpr;
    690     }
    691 
    692     /**
    693      * Setter method for "lang" tag attribute. (Mapping set in associated
    694      * BeanInfo class.)
    695      */
    696     public void setLangExpr(String langExpr) {
    697         this.langExpr = langExpr;
    698     }
    699 
    700     /**
    701      * Setter method for "linkName" tag attribute. (Mapping set in associated
    702      * BeanInfo class.)
    703      */
    704     public void setLinkNameExpr(String linkNameExpr) {
    705         this.linkNameExpr = linkNameExpr;
    706     }
    707 
    708     /**
    709      * Setter method for "name" tag attribute. (Mapping set in associated
    710      * BeanInfo class.)
    711      */
    712     public void setNameExpr(String nameExpr) {
    713         this.nameExpr = nameExpr;
    714     }
    715 
    716     /**
    717      * Setter method for "onblur" tag attribute. (Mapping set in associated
    718      * BeanInfo class.)
    719      */
    720     public void setOnblurExpr(String onblurExpr) {
    721         this.onblurExpr = onblurExpr;
    722     }
    723 
    724     /**
    725      * Setter method for "onclick" tag attribute. (Mapping set in associated
    726      * BeanInfo class.)
    727      */
    728     public void setOnclickExpr(String onclickExpr) {
    729         this.onclickExpr = onclickExpr;
    730     }
    731 
    732     /**
    733      * Setter method for "ondblclick" tag attribute. (Mapping set in
    734      * associated BeanInfo class.)
    735      */
    736     public void setOndblclickExpr(String ondblclickExpr) {
    737         this.ondblclickExpr = ondblclickExpr;
    738     }
    739 
    740     /**
    741      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    742      * BeanInfo class.)
    743      */
    744     public void setOnfocusExpr(String onfocusExpr) {
    745         this.onfocusExpr = onfocusExpr;
    746     }
    747 
    748     /**
    749      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    750      * BeanInfo class.)
    751      */
    752     public void setOnkeydownExpr(String onkeydownExpr) {
    753         this.onkeydownExpr = onkeydownExpr;
    754     }
    755 
    756     /**
    757      * Setter method for "onkeypress" tag attribute. (Mapping set in
    758      * associated BeanInfo class.)
    759      */
    760     public void setOnkeypressExpr(String onkeypressExpr) {
    761         this.onkeypressExpr = onkeypressExpr;
    762     }
    763 
    764     /**
    765      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    766      * BeanInfo class.)
    767      */
    768     public void setOnkeyupExpr(String onkeyupExpr) {
    769         this.onkeyupExpr = onkeyupExpr;
    770     }
    771 
    772     /**
    773      * Setter method for "onmousedown" tag attribute. (Mapping set in
    774      * associated BeanInfo class.)
    775      */
    776     public void setOnmousedownExpr(String onmousedownExpr) {
    777         this.onmousedownExpr = onmousedownExpr;
    778     }
    779 
    780     /**
    781      * Setter method for "onmousemove" tag attribute. (Mapping set in
    782      * associated BeanInfo class.)
    783      */
    784     public void setOnmousemoveExpr(String onmousemoveExpr) {
    785         this.onmousemoveExpr = onmousemoveExpr;
    786     }
    787 
    788     /**
    789      * Setter method for "onmouseout" tag attribute. (Mapping set in
    790      * associated BeanInfo class.)
    791      */
    792     public void setOnmouseoutExpr(String onmouseoutExpr) {
    793         this.onmouseoutExpr = onmouseoutExpr;
    794     }
    795 
    796     /**
    797      * Setter method for "onmouseover" tag attribute. (Mapping set in
    798      * associated BeanInfo class.)
    799      */
    800     public void setOnmouseoverExpr(String onmouseoverExpr) {
    801         this.onmouseoverExpr = onmouseoverExpr;
    802     }
    803 
    804     /**
    805      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    806      * BeanInfo class.)
    807      */
    808     public void setOnmouseupExpr(String onmouseupExpr) {
    809         this.onmouseupExpr = onmouseupExpr;
    810     }
    811 
    812     /**
    813      * Setter method for "page" tag attribute. (Mapping set in associated
    814      * BeanInfo class.)
    815      */
    816     public void setPageExpr(String pageExpr) {
    817         this.pageExpr = pageExpr;
    818     }
    819 
    820     /**
    821      * Setter method for "paramId" tag attribute. (Mapping set in associated
    822      * BeanInfo class.)
    823      */
    824     public void setParamIdExpr(String paramIdExpr) {
    825         this.paramIdExpr = paramIdExpr;
    826     }
    827 
    828     /**
    829      * Setter method for "paramName" tag attribute. (Mapping set in associated
    830      * BeanInfo class.)
    831      */
    832     public void setParamNameExpr(String paramNameExpr) {
    833         this.paramNameExpr = paramNameExpr;
    834     }
    835 
    836     /**
    837      * Setter method for "paramProperty" tag attribute. (Mapping set in
    838      * associated BeanInfo class.)
    839      */
    840     public void setParamPropertyExpr(String paramPropertyExpr) {
    841         this.paramPropertyExpr = paramPropertyExpr;
    842     }
    843 
    844     /**
    845      * Setter method for "paramScope" tag attribute. (Mapping set in
    846      * associated BeanInfo class.)
    847      */
    848     public void setParamScopeExpr(String paramScopeExpr) {
    849         this.paramScopeExpr = paramScopeExpr;
    850     }
    851 
    852     /**
    853      * Setter method for "property" tag attribute. (Mapping set in associated
    854      * BeanInfo class.)
    855      */
    856     public void setPropertyExpr(String propertyExpr) {
    857         this.propertyExpr = propertyExpr;
    858     }
    859 
    860     /**
    861      * Setter method for "scope" tag attribute. (Mapping set in associated
    862      * BeanInfo class.)
    863      */
    864     public void setScopeExpr(String scopeExpr) {
    865         this.scopeExpr = scopeExpr;
    866     }
    867 
    868     /**
    869      * Setter method for "style" tag attribute. (Mapping set in associated
    870      * BeanInfo class.)
    871      */
    872     public void setStyleExpr(String styleExpr) {
    873         this.styleExpr = styleExpr;
    874     }
    875 
    876     /**
    877      * Setter method for "styleClass" tag attribute. (Mapping set in
    878      * associated BeanInfo class.)
    879      */
    880     public void setStyleClassExpr(String styleClassExpr) {
    881         this.styleClassExpr = styleClassExpr;
    882     }
    883 
    884     /**
    885      * Setter method for "styleId" tag attribute. (Mapping set in associated
    886      * BeanInfo class.)
    887      */
    888     public void setStyleIdExpr(String styleIdExpr) {
    889         this.styleIdExpr = styleIdExpr;
    890     }
    891 
    892     /**
    893      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    894      * BeanInfo class.)
    895      */
    896     public void setTabindexExpr(String tabindexExpr) {
    897         this.tabindexExpr = tabindexExpr;
    898     }
    899 
    900     /**
    901      * Setter method for "target" tag attribute. (Mapping set in associated
    902      * BeanInfo class.)
    903      */
    904     public void setTargetExpr(String targetExpr) {
    905         this.targetExpr = targetExpr;
    906     }
    907 
    908     /**
    909      * Setter method for "title" tag attribute. (Mapping set in associated
    910      * BeanInfo class.)
    911      */
    912     public void setTitleExpr(String titleExpr) {
    913         this.titleExpr = titleExpr;
    914     }
    915 
    916     /**
    917      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    918      * BeanInfo class.)
    919      */
    920     public void setTitleKeyExpr(String titleKeyExpr) {
    921         this.titleKeyExpr = titleKeyExpr;
    922     }
    923 
    924     /**
    925      * Setter method for "transaction" tag attribute. (Mapping set in
    926      * associated BeanInfo class.)
    927      */
    928     public void setTransactionExpr(String transactionExpr) {
    929         this.transactionExpr = transactionExpr;
    930     }
    931 
    932     /**
    933      * Setter method for "useLocalEncoding" tag attribute. (Mapping set in
    934      * associated BeanInfo class.)
    935      */
    936     public void setUseLocalEncodingExpr(String useLocalEncodingExpr) {
    937         this.useLocalEncodingExpr = useLocalEncodingExpr;
    938     }
    939 
    940     /**
    941      * Resets attribute values for tag reuse.
    942      */
    943     public void release() {
    944         super.release();
    945         setAccesskeyExpr(null);
    946         setActionExpr(null);
    947         setModuleExpr(null);
    948         setAnchorExpr(null);
    949         setBundleExpr(null);
    950         setDirExpr(null);
    951         setForwardExpr(null);
    952         setHrefExpr(null);
    953         setIndexedExpr(null);
    954         setIndexIdExpr(null);
    955         setLangExpr(null);
    956         setLinkNameExpr(null);
    957         setNameExpr(null);
    958         setOnblurExpr(null);
    959         setOnclickExpr(null);
    960         setOndblclickExpr(null);
    961         setOnfocusExpr(null);
    962         setOnkeydownExpr(null);
    963         setOnkeypressExpr(null);
    964         setOnkeyupExpr(null);
    965         setOnmousedownExpr(null);
    966         setOnmousemoveExpr(null);
    967         setOnmouseoutExpr(null);
    968         setOnmouseoverExpr(null);
    969         setOnmouseupExpr(null);
    970         setPageExpr(null);
    971         setParamIdExpr(null);
    972         setParamNameExpr(null);
    973         setParamPropertyExpr(null);
    974         setParamScopeExpr(null);
    975         setPropertyExpr(null);
    976         setScopeExpr(null);
    977         setStyleExpr(null);
    978         setStyleClassExpr(null);
    979         setStyleIdExpr(null);
    980         setTabindexExpr(null);
    981         setTargetExpr(null);
    982         setTitleExpr(null);
    983         setTitleKeyExpr(null);
    984         setTransactionExpr(null);
    985         setUseLocalEncodingExpr(null);
    986     }
    987 
    988     /**
    989      * Process the start tag.
    990      *
    991      * @throws JspException if a JSP exception has occurred
    992      */
    993     public int doStartTag() throws JspException {
    994         evaluateExpressions();
    995 
    996         return (super.doStartTag());
    997     }
    998 
    999     /**
    1000      * Processes all attribute values which use the JSTL expression evaluation
    1001      * engine to determine their values.
    1002      *
    1003      * @throws JspException if a JSP exception has occurred
    1004      */
    1005     private void evaluateExpressions()
    1006         throws JspException {
    1007         String string = null;
    1008         Boolean bool = null;
    1009 
    1010         if ((string =
    1011                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    1012                     pageContext)) != null) {
    1013             setAccesskey(string);
    1014         }
    1015 
    1016         if ((string =
    1017                 EvalHelper.evalString("action", getActionExpr(), this,
    1018                     pageContext)) != null) {
    1019             setAction(string);
    1020         }
    1021 
    1022         if ((string =
    1023                 EvalHelper.evalString("module", getModuleExpr(), this,
    1024                     pageContext)) != null) {
    1025             setModule(string);
    1026         }
    1027 
    1028         if ((string =
    1029                 EvalHelper.evalString("anchor", getAnchorExpr(), this,
    1030                     pageContext)) != null) {
    1031             setAnchor(string);
    1032         }
    1033 
    1034         if ((string =
    1035                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    1036                     pageContext)) != null) {
    1037             setBundle(string);
    1038         }
    1039 
    1040         if ((string =
    1041                       EvalHelper.evalString("dir", getDirExpr(), this,
    1042                               pageContext)) != null) {
    1043               setDir(string);
    1044         }
    1045         
    1046         if ((string =
    1047                 EvalHelper.evalString("forward", getForwardExpr(), this,
    1048                     pageContext)) != null) {
    1049             setForward(string);
    1050         }
    1051 
    1052         if ((string =
    1053                 EvalHelper.evalString("href", getHrefExpr(), this, pageContext)) != null) {
    1054             setHref(string);
    1055         }
    1056 
    1057         if ((bool =
    1058                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    1059                     pageContext)) != null) {
    1060             setIndexed(bool.booleanValue());
    1061         }
    1062 
    1063         if ((string =
    1064                 EvalHelper.evalString("indexId", getIndexIdExpr(), this,
    1065                     pageContext)) != null) {
    1066             setIndexId(string);
    1067         }
    1068 
    1069         if ((string =
    1070               EvalHelper.evalString("lang", getLangExpr(), this,
    1071                       pageContext)) != null) {
    1072               setLang(string);
    1073         }
    1074 
    1075         if ((string =
    1076                 EvalHelper.evalString("linkName", getLinkNameExpr(), this,
    1077                     pageContext)) != null) {
    1078             setLinkName(string);
    1079         }
    1080 
    1081         if ((string =
    1082                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    1083             setName(string);
    1084         }
    1085 
    1086         if ((string =
    1087                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    1088                     pageContext)) != null) {
    1089             setOnblur(string);
    1090         }
    1091 
    1092         if ((string =
    1093                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1094                     pageContext)) != null) {
    1095             setOnclick(string);
    1096         }
    1097 
    1098         if ((string =
    1099                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1100                     pageContext)) != null) {
    1101             setOndblclick(string);
    1102         }
    1103 
    1104         if ((string =
    1105                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    1106                     pageContext)) != null) {
    1107             setOnfocus(string);
    1108         }
    1109 
    1110         if ((string =
    1111                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1112                     pageContext)) != null) {
    1113             setOnkeydown(string);
    1114         }
    1115 
    1116         if ((string =
    1117                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1118                     pageContext)) != null) {
    1119             setOnkeypress(string);
    1120         }
    1121 
    1122         if ((string =
    1123                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1124                     pageContext)) != null) {
    1125             setOnkeyup(string);
    1126         }
    1127 
    1128         if ((string =
    1129                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1130                     this, pageContext)) != null) {
    1131             setOnmousedown(string);
    1132         }
    1133 
    1134         if ((string =
    1135                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1136                     this, pageContext)) != null) {
    1137             setOnmousemove(string);
    1138         }
    1139 
    1140         if ((string =
    1141                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1142                     pageContext)) != null) {
    1143             setOnmouseout(string);
    1144         }
    1145 
    1146         if ((string =
    1147                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1148                     this, pageContext)) != null) {
    1149             setOnmouseover(string);
    1150         }
    1151 
    1152         if ((string =
    1153                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1154                     pageContext)) != null) {
    1155             setOnmouseup(string);
    1156         }
    1157 
    1158         if ((string =
    1159                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    1160             setPage(string);
    1161         }
    1162 
    1163         if ((string =
    1164                 EvalHelper.evalString("paramId", getParamIdExpr(), this,
    1165                     pageContext)) != null) {
    1166             setParamId(string);
    1167         }
    1168 
    1169         if ((string =
    1170                 EvalHelper.evalString("paramName", getParamNameExpr(), this,
    1171                     pageContext)) != null) {
    1172             setParamName(string);
    1173         }
    1174 
    1175         if ((string =
    1176                 EvalHelper.evalString("paramProperty", getParamPropertyExpr(),
    1177                     this, pageContext)) != null) {
    1178             setParamProperty(string);
    1179         }
    1180 
    1181         if ((string =
    1182                 EvalHelper.evalString("paramScope", getParamScopeExpr(), this,
    1183                     pageContext)) != null) {
    1184             setParamScope(string);
    1185         }
    1186 
    1187         if ((string =
    1188                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1189                     pageContext)) != null) {
    1190             setProperty(string);
    1191         }
    1192 
    1193         if ((string =
    1194                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    1195             setScope(string);
    1196         }
    1197 
    1198         if ((string =
    1199                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1200             setStyle(string);
    1201         }
    1202 
    1203         if ((string =
    1204                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1205                     pageContext)) != null) {
    1206             setStyleClass(string);
    1207         }
    1208 
    1209         if ((string =
    1210                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1211                     pageContext)) != null) {
    1212             setStyleId(string);
    1213         }
    1214 
    1215         if ((string =
    1216                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    1217                     pageContext)) != null) {
    1218             setTabindex(string);
    1219         }
    1220 
    1221         if ((string =
    1222                 EvalHelper.evalString("target", getTargetExpr(), this,
    1223                     pageContext)) != null) {
    1224             setTarget(string);
    1225         }
    1226 
    1227         if ((string =
    1228                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1229             setTitle(string);
    1230         }
    1231 
    1232         if ((string =
    1233                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1234                     pageContext)) != null) {
    1235             setTitleKey(string);
    1236         }
    1237 
    1238         if ((bool =
    1239                 EvalHelper.evalBoolean("transaction", getTransactionExpr(),
    1240                     this, pageContext)) != null) {
    1241             setTransaction(bool.booleanValue());
    1242         }
    1243 
    1244         if ((bool =
    1245                 EvalHelper.evalBoolean("useLocalEncoding",
    1246                     getUseLocalEncodingExpr(), this, pageContext)) != null) {
    1247             setUseLocalEncoding(bool.booleanValue());
    1248         }
    1249     }
    1250 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
