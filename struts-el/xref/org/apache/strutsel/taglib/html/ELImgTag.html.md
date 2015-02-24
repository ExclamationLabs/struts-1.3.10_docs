[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELImgTag.html)


    1   /*
    2    * $Id: ELImgTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.ImgTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * <p>Generate an IMG tag to the specified image URI. </p>
    30   *
    31   * <p>TODO:</p>
    32   *
    33   * <ul>
    34   *
    35   * <li>make the <strong>alt</strong> and <strong>src</strong> settable from
    36   * properties (for i18n)</li>
    37   *
    38   * <li>handle <strong>onLoad</strong>, <strong>onAbort</strong>, and
    39   * <strong>onError</strong> events (my JavaScript book is very old, there may
    40   * be more unsupported events in the past couple of IE versions) </li>
    41   *
    42   * </ul>
    43   *
    44   * <p> This class is a subclass of the class <code>org.apache.struts.taglib.html.md.ImgTag</code>
    45   * which provides most of the described functionality.  This subclass allows
    46   * all attribute values to be specified as expressions utilizing the
    47   * JavaServer Pages Standard Library expression language. </p>
    48   *
    49   * @version $Rev: 479635 $
    50   */
    51  public class ELImgTag extends ImgTag {
    52      /**
    53       * Instance variable mapped to "action" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String actionExpr;
    57  
    58      /**
    59       * Instance variable mapped to "module" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String moduleExpr;
    63  
    64      /**
    65       * Instance variable mapped to "align" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String alignExpr;
    69  
    70      /**
    71       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    72       * associated BeanInfo class.)
    73       */
    74      private String altExpr;
    75  
    76      /**
    77       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String altKeyExpr;
    81  
    82      /**
    83       * Instance variable mapped to "border" tag attribute. (Mapping set in
    84       * associated BeanInfo class.)
    85       */
    86      private String borderExpr;
    87  
    88      /**
    89       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    90       * associated BeanInfo class.)
    91       */
    92      private String bundleExpr;
    93  
    94      /**
    95       * Instance variable mapped to "dir" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String dirExpr;
    99  
    100     /**
    101      * Instance variable mapped to "height" tag attribute. (Mapping set in
    102      * associated BeanInfo class.)
    103      */
    104     private String heightExpr;
    105 
    106     /**
    107      * Instance variable mapped to "hspace" tag attribute. (Mapping set in
    108      * associated BeanInfo class.)
    109      */
    110     private String hspaceExpr;
    111 
    112     /**
    113      * Instance variable mapped to "imageName" tag attribute. (Mapping set in
    114      * associated BeanInfo class.)
    115      */
    116     private String imageNameExpr;
    117 
    118     /**
    119      * Instance variable mapped to "ismap" tag attribute. (Mapping set in
    120      * associated BeanInfo class.)
    121      */
    122     private String ismapExpr;
    123 
    124     /**
    125      * Instance variable mapped to "lang" tag attribute. (Mapping set in
    126      * associated BeanInfo class.)
    127      */
    128     private String langExpr;
    129 
    130     /**
    131      * Instance variable mapped to "locale" tag attribute. (Mapping set in
    132      * associated BeanInfo class.)
    133      */
    134     private String localeExpr;
    135 
    136     /**
    137      * Instance variable mapped to "name" tag attribute. (Mapping set in
    138      * associated BeanInfo class.)
    139      */
    140     private String nameExpr;
    141 
    142     /**
    143      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    144      * associated BeanInfo class.)
    145      */
    146     private String onclickExpr;
    147 
    148     /**
    149      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    150      * associated BeanInfo class.)
    151      */
    152     private String ondblclickExpr;
    153 
    154     /**
    155      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    156      * associated BeanInfo class.)
    157      */
    158     private String onkeydownExpr;
    159 
    160     /**
    161      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    162      * associated BeanInfo class.)
    163      */
    164     private String onkeypressExpr;
    165 
    166     /**
    167      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    168      * associated BeanInfo class.)
    169      */
    170     private String onkeyupExpr;
    171 
    172     /**
    173      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    174      * in associated BeanInfo class.)
    175      */
    176     private String onmousedownExpr;
    177 
    178     /**
    179      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    180      * in associated BeanInfo class.)
    181      */
    182     private String onmousemoveExpr;
    183 
    184     /**
    185      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    186      * associated BeanInfo class.)
    187      */
    188     private String onmouseoutExpr;
    189 
    190     /**
    191      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    192      * in associated BeanInfo class.)
    193      */
    194     private String onmouseoverExpr;
    195 
    196     /**
    197      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    198      * associated BeanInfo class.)
    199      */
    200     private String onmouseupExpr;
    201 
    202     /**
    203      * Instance variable mapped to "paramId" tag attribute. (Mapping set in
    204      * associated BeanInfo class.)
    205      */
    206     private String paramIdExpr;
    207 
    208     /**
    209      * Instance variable mapped to "page" tag attribute. (Mapping set in
    210      * associated BeanInfo class.)
    211      */
    212     private String pageExpr;
    213 
    214     /**
    215      * Instance variable mapped to "pageKey" tag attribute. (Mapping set in
    216      * associated BeanInfo class.)
    217      */
    218     private String pageKeyExpr;
    219 
    220     /**
    221      * Instance variable mapped to "paramName" tag attribute. (Mapping set in
    222      * associated BeanInfo class.)
    223      */
    224     private String paramNameExpr;
    225 
    226     /**
    227      * Instance variable mapped to "paramProperty" tag attribute. (Mapping set
    228      * in associated BeanInfo class.)
    229      */
    230     private String paramPropertyExpr;
    231 
    232     /**
    233      * Instance variable mapped to "paramScope" tag attribute. (Mapping set in
    234      * associated BeanInfo class.)
    235      */
    236     private String paramScopeExpr;
    237 
    238     /**
    239      * Instance variable mapped to "property" tag attribute. (Mapping set in
    240      * associated BeanInfo class.)
    241      */
    242     private String propertyExpr;
    243 
    244     /**
    245      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    246      * associated BeanInfo class.)
    247      */
    248     private String scopeExpr;
    249 
    250     /**
    251      * Instance variable mapped to "src" tag attribute. (Mapping set in
    252      * associated BeanInfo class.)
    253      */
    254     private String srcExpr;
    255 
    256     /**
    257      * Instance variable mapped to "srcKey" tag attribute. (Mapping set in
    258      * associated BeanInfo class.)
    259      */
    260     private String srcKeyExpr;
    261 
    262     /**
    263      * Instance variable mapped to "style" tag attribute. (Mapping set in
    264      * associated BeanInfo class.)
    265      */
    266     private String styleExpr;
    267 
    268     /**
    269      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    270      * associated BeanInfo class.)
    271      */
    272     private String styleClassExpr;
    273 
    274     /**
    275      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    276      * associated BeanInfo class.)
    277      */
    278     private String styleIdExpr;
    279 
    280     /**
    281      * Instance variable mapped to "title" tag attribute. (Mapping set in
    282      * associated BeanInfo class.)
    283      */
    284     private String titleExpr;
    285 
    286     /**
    287      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    288      * associated BeanInfo class.)
    289      */
    290     private String titleKeyExpr;
    291 
    292     /**
    293      * Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping
    294      * set in associated BeanInfo class.)
    295      */
    296     private String useLocalEncodingExpr;
    297 
    298     /**
    299      * Instance variable mapped to "usemap" tag attribute. (Mapping set in
    300      * associated BeanInfo class.)
    301      */
    302     private String usemapExpr;
    303 
    304     /**
    305      * Instance variable mapped to "vspace" tag attribute. (Mapping set in
    306      * associated BeanInfo class.)
    307      */
    308     private String vspaceExpr;
    309 
    310     /**
    311      * Instance variable mapped to "width" tag attribute. (Mapping set in
    312      * associated BeanInfo class.)
    313      */
    314     private String widthExpr;
    315 
    316     /**
    317      * Getter method for "action" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getActionExpr() {
    321         return (actionExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "module" tag attribute. (Mapping set in associated
    326      * BeanInfo class.)
    327      */
    328     public String getModuleExpr() {
    329         return (moduleExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "align" tag attribute. (Mapping set in associated
    334      * BeanInfo class.)
    335      */
    336     public String getAlignExpr() {
    337         return (alignExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "alt" tag attribute. (Mapping set in associated
    342      * BeanInfo class.)
    343      */
    344     public String getAltExpr() {
    345         return (altExpr);
    346     }
    347 
    348     /**
    349      * Getter method for "altKey" tag attribute. (Mapping set in associated
    350      * BeanInfo class.)
    351      */
    352     public String getAltKeyExpr() {
    353         return (altKeyExpr);
    354     }
    355 
    356     /**
    357      * Getter method for "border" tag attribute. (Mapping set in associated
    358      * BeanInfo class.)
    359      */
    360     public String getBorderExpr() {
    361         return (borderExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "bundle" tag attribute. (Mapping set in associated
    366      * BeanInfo class.)
    367      */
    368     public String getBundleExpr() {
    369         return (bundleExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "dir" tag attribute. (Mapping set in associated
    374      * BeanInfo class.)
    375      */
    376     public String getDirExpr() {
    377         return (dirExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "height" tag attribute. (Mapping set in associated
    382      * BeanInfo class.)
    383      */
    384     public String getHeightExpr() {
    385         return (heightExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "hspace" tag attribute. (Mapping set in associated
    390      * BeanInfo class.)
    391      */
    392     public String getHspaceExpr() {
    393         return (hspaceExpr);
    394     }
    395 
    396     /**
    397      * Getter method for "imageName" tag attribute. (Mapping set in associated
    398      * BeanInfo class.)
    399      */
    400     public String getImageNameExpr() {
    401         return (imageNameExpr);
    402     }
    403 
    404     /**
    405      * Getter method for "ismap" tag attribute. (Mapping set in associated
    406      * BeanInfo class.)
    407      */
    408     public String getIsmapExpr() {
    409         return (ismapExpr);
    410     }
    411 
    412     /**
    413      * Getter method for "lang" tag attribute. (Mapping set in associated
    414      * BeanInfo class.)
    415      */
    416     public String getLangExpr() {
    417         return (langExpr);
    418     }
    419 
    420     /**
    421      * Getter method for "locale" tag attribute. (Mapping set in associated
    422      * BeanInfo class.)
    423      */
    424     public String getLocaleExpr() {
    425         return (localeExpr);
    426     }
    427 
    428     /**
    429      * Getter method for "name" tag attribute. (Mapping set in associated
    430      * BeanInfo class.)
    431      */
    432     public String getNameExpr() {
    433         return (nameExpr);
    434     }
    435 
    436     /**
    437      * Getter method for "onclick" tag attribute. (Mapping set in associated
    438      * BeanInfo class.)
    439      */
    440     public String getOnclickExpr() {
    441         return (onclickExpr);
    442     }
    443 
    444     /**
    445      * Getter method for "ondblclick" tag attribute. (Mapping set in
    446      * associated BeanInfo class.)
    447      */
    448     public String getOndblclickExpr() {
    449         return (ondblclickExpr);
    450     }
    451 
    452     /**
    453      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    454      * BeanInfo class.)
    455      */
    456     public String getOnkeydownExpr() {
    457         return (onkeydownExpr);
    458     }
    459 
    460     /**
    461      * Getter method for "onkeypress" tag attribute. (Mapping set in
    462      * associated BeanInfo class.)
    463      */
    464     public String getOnkeypressExpr() {
    465         return (onkeypressExpr);
    466     }
    467 
    468     /**
    469      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    470      * BeanInfo class.)
    471      */
    472     public String getOnkeyupExpr() {
    473         return (onkeyupExpr);
    474     }
    475 
    476     /**
    477      * Getter method for "onmousedown" tag attribute. (Mapping set in
    478      * associated BeanInfo class.)
    479      */
    480     public String getOnmousedownExpr() {
    481         return (onmousedownExpr);
    482     }
    483 
    484     /**
    485      * Getter method for "onmousemove" tag attribute. (Mapping set in
    486      * associated BeanInfo class.)
    487      */
    488     public String getOnmousemoveExpr() {
    489         return (onmousemoveExpr);
    490     }
    491 
    492     /**
    493      * Getter method for "onmouseout" tag attribute. (Mapping set in
    494      * associated BeanInfo class.)
    495      */
    496     public String getOnmouseoutExpr() {
    497         return (onmouseoutExpr);
    498     }
    499 
    500     /**
    501      * Getter method for "onmouseover" tag attribute. (Mapping set in
    502      * associated BeanInfo class.)
    503      */
    504     public String getOnmouseoverExpr() {
    505         return (onmouseoverExpr);
    506     }
    507 
    508     /**
    509      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    510      * BeanInfo class.)
    511      */
    512     public String getOnmouseupExpr() {
    513         return (onmouseupExpr);
    514     }
    515 
    516     /**
    517      * Getter method for "paramId" tag attribute. (Mapping set in associated
    518      * BeanInfo class.)
    519      */
    520     public String getParamIdExpr() {
    521         return (paramIdExpr);
    522     }
    523 
    524     /**
    525      * Getter method for "page" tag attribute. (Mapping set in associated
    526      * BeanInfo class.)
    527      */
    528     public String getPageExpr() {
    529         return (pageExpr);
    530     }
    531 
    532     /**
    533      * Getter method for "pageKey" tag attribute. (Mapping set in associated
    534      * BeanInfo class.)
    535      */
    536     public String getPageKeyExpr() {
    537         return (pageKeyExpr);
    538     }
    539 
    540     /**
    541      * Getter method for "paramName" tag attribute. (Mapping set in associated
    542      * BeanInfo class.)
    543      */
    544     public String getParamNameExpr() {
    545         return (paramNameExpr);
    546     }
    547 
    548     /**
    549      * Getter method for "paramProperty" tag attribute. (Mapping set in
    550      * associated BeanInfo class.)
    551      */
    552     public String getParamPropertyExpr() {
    553         return (paramPropertyExpr);
    554     }
    555 
    556     /**
    557      * Getter method for "paramScope" tag attribute. (Mapping set in
    558      * associated BeanInfo class.)
    559      */
    560     public String getParamScopeExpr() {
    561         return (paramScopeExpr);
    562     }
    563 
    564     /**
    565      * Getter method for "property" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public String getPropertyExpr() {
    569         return (propertyExpr);
    570     }
    571 
    572     /**
    573      * Getter method for "scope" tag attribute. (Mapping set in associated
    574      * BeanInfo class.)
    575      */
    576     public String getScopeExpr() {
    577         return (scopeExpr);
    578     }
    579 
    580     /**
    581      * Getter method for "src" tag attribute. (Mapping set in associated
    582      * BeanInfo class.)
    583      */
    584     public String getSrcExpr() {
    585         return (srcExpr);
    586     }
    587 
    588     /**
    589      * Getter method for "srcKey" tag attribute. (Mapping set in associated
    590      * BeanInfo class.)
    591      */
    592     public String getSrcKeyExpr() {
    593         return (srcKeyExpr);
    594     }
    595 
    596     /**
    597      * Getter method for "style" tag attribute. (Mapping set in associated
    598      * BeanInfo class.)
    599      */
    600     public String getStyleExpr() {
    601         return (styleExpr);
    602     }
    603 
    604     /**
    605      * Getter method for "styleClass" tag attribute. (Mapping set in
    606      * associated BeanInfo class.)
    607      */
    608     public String getStyleClassExpr() {
    609         return (styleClassExpr);
    610     }
    611 
    612     /**
    613      * Getter method for "styleId" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public String getStyleIdExpr() {
    617         return (styleIdExpr);
    618     }
    619 
    620     /**
    621      * Getter method for "title" tag attribute. (Mapping set in associated
    622      * BeanInfo class.)
    623      */
    624     public String getTitleExpr() {
    625         return (titleExpr);
    626     }
    627 
    628     /**
    629      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    630      * BeanInfo class.)
    631      */
    632     public String getTitleKeyExpr() {
    633         return (titleKeyExpr);
    634     }
    635 
    636     /**
    637      * Getter method for "useLocalEncoding" tag attribute. (Mapping set in
    638      * associated BeanInfo class.)
    639      */
    640     public String getUseLocalEncodingExpr() {
    641         return (useLocalEncodingExpr);
    642     }
    643 
    644     /**
    645      * Getter method for "usemap" tag attribute. (Mapping set in associated
    646      * BeanInfo class.)
    647      */
    648     public String getUsemapExpr() {
    649         return (usemapExpr);
    650     }
    651 
    652     /**
    653      * Getter method for "vspace" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public String getVspaceExpr() {
    657         return (vspaceExpr);
    658     }
    659 
    660     /**
    661      * Getter method for "width" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public String getWidthExpr() {
    665         return (widthExpr);
    666     }
    667 
    668     /**
    669      * Setter method for "action" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setActionExpr(String actionExpr) {
    673         this.actionExpr = actionExpr;
    674     }
    675 
    676     /**
    677      * Setter method for "module" tag attribute. (Mapping set in associated
    678      * BeanInfo class.)
    679      */
    680     public void setModuleExpr(String moduleExpr) {
    681         this.moduleExpr = moduleExpr;
    682     }
    683 
    684     /**
    685      * Setter method for "align" tag attribute. (Mapping set in associated
    686      * BeanInfo class.)
    687      */
    688     public void setAlignExpr(String alignExpr) {
    689         this.alignExpr = alignExpr;
    690     }
    691 
    692     /**
    693      * Setter method for "alt" tag attribute. (Mapping set in associated
    694      * BeanInfo class.)
    695      */
    696     public void setAltExpr(String altExpr) {
    697         this.altExpr = altExpr;
    698     }
    699 
    700     /**
    701      * Setter method for "altKey" tag attribute. (Mapping set in associated
    702      * BeanInfo class.)
    703      */
    704     public void setAltKeyExpr(String altKeyExpr) {
    705         this.altKeyExpr = altKeyExpr;
    706     }
    707 
    708     /**
    709      * Setter method for "border" tag attribute. (Mapping set in associated
    710      * BeanInfo class.)
    711      */
    712     public void setBorderExpr(String borderExpr) {
    713         this.borderExpr = borderExpr;
    714     }
    715 
    716     /**
    717      * Setter method for "bundle" tag attribute. (Mapping set in associated
    718      * BeanInfo class.)
    719      */
    720     public void setBundleExpr(String bundleExpr) {
    721         this.bundleExpr = bundleExpr;
    722     }
    723 
    724     /**
    725      * Setter method for "dir" tag attribute. (Mapping set in associated
    726      * BeanInfo class.)
    727      */
    728     public void setDirExpr(String dirExpr) {
    729         this.dirExpr = dirExpr;
    730     }
    731 
    732     /**
    733      * Setter method for "height" tag attribute. (Mapping set in associated
    734      * BeanInfo class.)
    735      */
    736     public void setHeightExpr(String heightExpr) {
    737         this.heightExpr = heightExpr;
    738     }
    739 
    740     /**
    741      * Setter method for "hspace" tag attribute. (Mapping set in associated
    742      * BeanInfo class.)
    743      */
    744     public void setHspaceExpr(String hspaceExpr) {
    745         this.hspaceExpr = hspaceExpr;
    746     }
    747 
    748     /**
    749      * Setter method for "imageName" tag attribute. (Mapping set in associated
    750      * BeanInfo class.)
    751      */
    752     public void setImageNameExpr(String imageNameExpr) {
    753         this.imageNameExpr = imageNameExpr;
    754     }
    755 
    756     /**
    757      * Setter method for "ismap" tag attribute. (Mapping set in associated
    758      * BeanInfo class.)
    759      */
    760     public void setIsmapExpr(String ismapExpr) {
    761         this.ismapExpr = ismapExpr;
    762     }
    763 
    764     /**
    765      * Setter method for "lang" tag attribute. (Mapping set in associated
    766      * BeanInfo class.)
    767      */
    768     public void setLangExpr(String langExpr) {
    769         this.langExpr = langExpr;
    770     }
    771 
    772     /**
    773      * Setter method for "locale" tag attribute. (Mapping set in associated
    774      * BeanInfo class.)
    775      */
    776     public void setLocaleExpr(String localeExpr) {
    777         this.localeExpr = localeExpr;
    778     }
    779 
    780     /**
    781      * Setter method for "name" tag attribute. (Mapping set in associated
    782      * BeanInfo class.)
    783      */
    784     public void setNameExpr(String nameExpr) {
    785         this.nameExpr = nameExpr;
    786     }
    787 
    788     /**
    789      * Setter method for "onclick" tag attribute. (Mapping set in associated
    790      * BeanInfo class.)
    791      */
    792     public void setOnclickExpr(String onclickExpr) {
    793         this.onclickExpr = onclickExpr;
    794     }
    795 
    796     /**
    797      * Setter method for "ondblclick" tag attribute. (Mapping set in
    798      * associated BeanInfo class.)
    799      */
    800     public void setOndblclickExpr(String ondblclickExpr) {
    801         this.ondblclickExpr = ondblclickExpr;
    802     }
    803 
    804     /**
    805      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    806      * BeanInfo class.)
    807      */
    808     public void setOnkeydownExpr(String onkeydownExpr) {
    809         this.onkeydownExpr = onkeydownExpr;
    810     }
    811 
    812     /**
    813      * Setter method for "onkeypress" tag attribute. (Mapping set in
    814      * associated BeanInfo class.)
    815      */
    816     public void setOnkeypressExpr(String onkeypressExpr) {
    817         this.onkeypressExpr = onkeypressExpr;
    818     }
    819 
    820     /**
    821      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    822      * BeanInfo class.)
    823      */
    824     public void setOnkeyupExpr(String onkeyupExpr) {
    825         this.onkeyupExpr = onkeyupExpr;
    826     }
    827 
    828     /**
    829      * Setter method for "onmousedown" tag attribute. (Mapping set in
    830      * associated BeanInfo class.)
    831      */
    832     public void setOnmousedownExpr(String onmousedownExpr) {
    833         this.onmousedownExpr = onmousedownExpr;
    834     }
    835 
    836     /**
    837      * Setter method for "onmousemove" tag attribute. (Mapping set in
    838      * associated BeanInfo class.)
    839      */
    840     public void setOnmousemoveExpr(String onmousemoveExpr) {
    841         this.onmousemoveExpr = onmousemoveExpr;
    842     }
    843 
    844     /**
    845      * Setter method for "onmouseout" tag attribute. (Mapping set in
    846      * associated BeanInfo class.)
    847      */
    848     public void setOnmouseoutExpr(String onmouseoutExpr) {
    849         this.onmouseoutExpr = onmouseoutExpr;
    850     }
    851 
    852     /**
    853      * Setter method for "onmouseover" tag attribute. (Mapping set in
    854      * associated BeanInfo class.)
    855      */
    856     public void setOnmouseoverExpr(String onmouseoverExpr) {
    857         this.onmouseoverExpr = onmouseoverExpr;
    858     }
    859 
    860     /**
    861      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    862      * BeanInfo class.)
    863      */
    864     public void setOnmouseupExpr(String onmouseupExpr) {
    865         this.onmouseupExpr = onmouseupExpr;
    866     }
    867 
    868     /**
    869      * Setter method for "paramId" tag attribute. (Mapping set in associated
    870      * BeanInfo class.)
    871      */
    872     public void setParamIdExpr(String paramIdExpr) {
    873         this.paramIdExpr = paramIdExpr;
    874     }
    875 
    876     /**
    877      * Setter method for "page" tag attribute. (Mapping set in associated
    878      * BeanInfo class.)
    879      */
    880     public void setPageExpr(String pageExpr) {
    881         this.pageExpr = pageExpr;
    882     }
    883 
    884     /**
    885      * Setter method for "pageKey" tag attribute. (Mapping set in associated
    886      * BeanInfo class.)
    887      */
    888     public void setPageKeyExpr(String pageKeyExpr) {
    889         this.pageKeyExpr = pageKeyExpr;
    890     }
    891 
    892     /**
    893      * Setter method for "paramName" tag attribute. (Mapping set in associated
    894      * BeanInfo class.)
    895      */
    896     public void setParamNameExpr(String paramNameExpr) {
    897         this.paramNameExpr = paramNameExpr;
    898     }
    899 
    900     /**
    901      * Setter method for "paramProperty" tag attribute. (Mapping set in
    902      * associated BeanInfo class.)
    903      */
    904     public void setParamPropertyExpr(String paramPropertyExpr) {
    905         this.paramPropertyExpr = paramPropertyExpr;
    906     }
    907 
    908     /**
    909      * Setter method for "paramScope" tag attribute. (Mapping set in
    910      * associated BeanInfo class.)
    911      */
    912     public void setParamScopeExpr(String paramScopeExpr) {
    913         this.paramScopeExpr = paramScopeExpr;
    914     }
    915 
    916     /**
    917      * Setter method for "property" tag attribute. (Mapping set in associated
    918      * BeanInfo class.)
    919      */
    920     public void setPropertyExpr(String propertyExpr) {
    921         this.propertyExpr = propertyExpr;
    922     }
    923 
    924     /**
    925      * Setter method for "scope" tag attribute. (Mapping set in associated
    926      * BeanInfo class.)
    927      */
    928     public void setScopeExpr(String scopeExpr) {
    929         this.scopeExpr = scopeExpr;
    930     }
    931 
    932     /**
    933      * Setter method for "src" tag attribute. (Mapping set in associated
    934      * BeanInfo class.)
    935      */
    936     public void setSrcExpr(String srcExpr) {
    937         this.srcExpr = srcExpr;
    938     }
    939 
    940     /**
    941      * Setter method for "srcKey" tag attribute. (Mapping set in associated
    942      * BeanInfo class.)
    943      */
    944     public void setSrcKeyExpr(String srcKeyExpr) {
    945         this.srcKeyExpr = srcKeyExpr;
    946     }
    947 
    948     /**
    949      * Setter method for "style" tag attribute. (Mapping set in associated
    950      * BeanInfo class.)
    951      */
    952     public void setStyleExpr(String styleExpr) {
    953         this.styleExpr = styleExpr;
    954     }
    955 
    956     /**
    957      * Setter method for "styleClass" tag attribute. (Mapping set in
    958      * associated BeanInfo class.)
    959      */
    960     public void setStyleClassExpr(String styleClassExpr) {
    961         this.styleClassExpr = styleClassExpr;
    962     }
    963 
    964     /**
    965      * Setter method for "styleId" tag attribute. (Mapping set in associated
    966      * BeanInfo class.)
    967      */
    968     public void setStyleIdExpr(String styleIdExpr) {
    969         this.styleIdExpr = styleIdExpr;
    970     }
    971 
    972     /**
    973      * Setter method for "title" tag attribute. (Mapping set in associated
    974      * BeanInfo class.)
    975      */
    976     public void setTitleExpr(String titleExpr) {
    977         this.titleExpr = titleExpr;
    978     }
    979 
    980     /**
    981      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    982      * BeanInfo class.)
    983      */
    984     public void setTitleKeyExpr(String titleKeyExpr) {
    985         this.titleKeyExpr = titleKeyExpr;
    986     }
    987 
    988     /**
    989      * Setter method for "useLocalEncoding" tag attribute. (Mapping set in
    990      * associated BeanInfo class.)
    991      */
    992     public void setUseLocalEncodingExpr(String useLocalEncodingExpr) {
    993         this.useLocalEncodingExpr = useLocalEncodingExpr;
    994     }
    995 
    996     /**
    997      * Setter method for "usemap" tag attribute. (Mapping set in associated
    998      * BeanInfo class.)
    999      */
    1000     public void setUsemapExpr(String usemapExpr) {
    1001         this.usemapExpr = usemapExpr;
    1002     }
    1003 
    1004     /**
    1005      * Setter method for "vspace" tag attribute. (Mapping set in associated
    1006      * BeanInfo class.)
    1007      */
    1008     public void setVspaceExpr(String vspaceExpr) {
    1009         this.vspaceExpr = vspaceExpr;
    1010     }
    1011 
    1012     /**
    1013      * Setter method for "width" tag attribute. (Mapping set in associated
    1014      * BeanInfo class.)
    1015      */
    1016     public void setWidthExpr(String widthExpr) {
    1017         this.widthExpr = widthExpr;
    1018     }
    1019 
    1020     /**
    1021      * Resets attribute values for tag reuse.
    1022      */
    1023     public void release() {
    1024         super.release();
    1025         setActionExpr(null);
    1026         setModuleExpr(null);
    1027         setAlignExpr(null);
    1028         setAltExpr(null);
    1029         setAltKeyExpr(null);
    1030         setBorderExpr(null);
    1031         setBundleExpr(null);
    1032         setDirExpr(null);
    1033         setHeightExpr(null);
    1034         setHspaceExpr(null);
    1035         setImageNameExpr(null);
    1036         setIsmapExpr(null);
    1037         setLangExpr(null);
    1038         setLocaleExpr(null);
    1039         setNameExpr(null);
    1040         setOnclickExpr(null);
    1041         setOndblclickExpr(null);
    1042         setOnkeydownExpr(null);
    1043         setOnkeypressExpr(null);
    1044         setOnkeyupExpr(null);
    1045         setOnmousedownExpr(null);
    1046         setOnmousemoveExpr(null);
    1047         setOnmouseoutExpr(null);
    1048         setOnmouseoverExpr(null);
    1049         setOnmouseupExpr(null);
    1050         setPageExpr(null);
    1051         setPageKeyExpr(null);
    1052         setParamIdExpr(null);
    1053         setParamNameExpr(null);
    1054         setParamPropertyExpr(null);
    1055         setParamScopeExpr(null);
    1056         setPropertyExpr(null);
    1057         setScopeExpr(null);
    1058         setSrcExpr(null);
    1059         setSrcKeyExpr(null);
    1060         setStyleExpr(null);
    1061         setStyleClassExpr(null);
    1062         setStyleIdExpr(null);
    1063         setTitleExpr(null);
    1064         setTitleKeyExpr(null);
    1065         setUseLocalEncodingExpr(null);
    1066         setUsemapExpr(null);
    1067         setVspaceExpr(null);
    1068         setWidthExpr(null);
    1069     }
    1070 
    1071     /**
    1072      * Process the start tag.
    1073      *
    1074      * @throws JspException if a JSP exception has occurred
    1075      */
    1076     public int doStartTag() throws JspException {
    1077         evaluateExpressions();
    1078 
    1079         return (super.doStartTag());
    1080     }
    1081 
    1082     /**
    1083      * Processes all attribute values which use the JSTL expression evaluation
    1084      * engine to determine their values.
    1085      *
    1086      * @throws JspException if a JSP exception has occurred
    1087      */
    1088     private void evaluateExpressions()
    1089         throws JspException {
    1090         String string = null;
    1091         Boolean bool = null;
    1092 
    1093         if ((string =
    1094                 EvalHelper.evalString("action", getActionExpr(), this,
    1095                     pageContext)) != null) {
    1096             setAction(string);
    1097         }
    1098 
    1099         if ((string =
    1100                 EvalHelper.evalString("module", getModuleExpr(), this,
    1101                     pageContext)) != null) {
    1102             setModule(string);
    1103         }
    1104 
    1105         if ((string =
    1106                 EvalHelper.evalString("align", getAlignExpr(), this, pageContext)) != null) {
    1107             setAlign(string);
    1108         }
    1109 
    1110         if ((string =
    1111                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    1112             setAlt(string);
    1113         }
    1114 
    1115         if ((string =
    1116                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    1117                     pageContext)) != null) {
    1118             setAltKey(string);
    1119         }
    1120 
    1121         if ((string =
    1122                 EvalHelper.evalString("border", getBorderExpr(), this,
    1123                     pageContext)) != null) {
    1124             setBorder(string);
    1125         }
    1126 
    1127         if ((string =
    1128                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    1129                     pageContext)) != null) {
    1130             setBundle(string);
    1131         }
    1132 
    1133         if ((string =
    1134                       EvalHelper.evalString("dir", getDirExpr(), this,
    1135                               pageContext)) != null) {
    1136               setDir(string);
    1137         }
    1138         
    1139         if ((string =
    1140                 EvalHelper.evalString("height", getHeightExpr(), this,
    1141                     pageContext)) != null) {
    1142             setHeight(string);
    1143         }
    1144 
    1145         if ((string =
    1146                 EvalHelper.evalString("hspace", getHspaceExpr(), this,
    1147                     pageContext)) != null) {
    1148             setHspace(string);
    1149         }
    1150 
    1151         if ((string =
    1152                 EvalHelper.evalString("imageName", getImageNameExpr(), this,
    1153                     pageContext)) != null) {
    1154             setImageName(string);
    1155         }
    1156 
    1157         if ((string =
    1158                 EvalHelper.evalString("ismap", getIsmapExpr(), this, pageContext)) != null) {
    1159             setIsmap(string);
    1160         }
    1161 
    1162         if ((string =
    1163               EvalHelper.evalString("lang", getLangExpr(), this,
    1164                       pageContext)) != null) {
    1165               setLang(string);
    1166         }
    1167 
    1168         if ((string =
    1169                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    1170                     pageContext)) != null) {
    1171             setLocale(string);
    1172         }
    1173 
    1174         if ((string =
    1175                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    1176             setName(string);
    1177         }
    1178 
    1179         if ((string =
    1180                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    1181                     pageContext)) != null) {
    1182             setOnclick(string);
    1183         }
    1184 
    1185         if ((string =
    1186                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    1187                     pageContext)) != null) {
    1188             setOndblclick(string);
    1189         }
    1190 
    1191         if ((string =
    1192                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    1193                     pageContext)) != null) {
    1194             setOnkeydown(string);
    1195         }
    1196 
    1197         if ((string =
    1198                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    1199                     pageContext)) != null) {
    1200             setOnkeypress(string);
    1201         }
    1202 
    1203         if ((string =
    1204                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    1205                     pageContext)) != null) {
    1206             setOnkeyup(string);
    1207         }
    1208 
    1209         if ((string =
    1210                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    1211                     this, pageContext)) != null) {
    1212             setOnmousedown(string);
    1213         }
    1214 
    1215         if ((string =
    1216                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    1217                     this, pageContext)) != null) {
    1218             setOnmousemove(string);
    1219         }
    1220 
    1221         if ((string =
    1222                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    1223                     pageContext)) != null) {
    1224             setOnmouseout(string);
    1225         }
    1226 
    1227         if ((string =
    1228                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    1229                     this, pageContext)) != null) {
    1230             setOnmouseover(string);
    1231         }
    1232 
    1233         if ((string =
    1234                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    1235                     pageContext)) != null) {
    1236             setOnmouseup(string);
    1237         }
    1238 
    1239         if ((string =
    1240                 EvalHelper.evalString("paramId", getParamIdExpr(), this,
    1241                     pageContext)) != null) {
    1242             setParamId(string);
    1243         }
    1244 
    1245         if ((string =
    1246                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    1247             setPage(string);
    1248         }
    1249 
    1250         if ((string =
    1251                 EvalHelper.evalString("pageKey", getPageKeyExpr(), this,
    1252                     pageContext)) != null) {
    1253             setPageKey(string);
    1254         }
    1255 
    1256         if ((string =
    1257                 EvalHelper.evalString("paramName", getParamNameExpr(), this,
    1258                     pageContext)) != null) {
    1259             setParamName(string);
    1260         }
    1261 
    1262         if ((string =
    1263                 EvalHelper.evalString("paramProperty", getParamPropertyExpr(),
    1264                     this, pageContext)) != null) {
    1265             setParamProperty(string);
    1266         }
    1267 
    1268         if ((string =
    1269                 EvalHelper.evalString("paramScope", getParamScopeExpr(), this,
    1270                     pageContext)) != null) {
    1271             setParamScope(string);
    1272         }
    1273 
    1274         if ((string =
    1275                 EvalHelper.evalString("property", getPropertyExpr(), this,
    1276                     pageContext)) != null) {
    1277             setProperty(string);
    1278         }
    1279 
    1280         if ((string =
    1281                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    1282             setScope(string);
    1283         }
    1284 
    1285         if ((string =
    1286                 EvalHelper.evalString("src", getSrcExpr(), this, pageContext)) != null) {
    1287             setSrc(string);
    1288         }
    1289 
    1290         if ((string =
    1291                 EvalHelper.evalString("srcKey", getSrcKeyExpr(), this,
    1292                     pageContext)) != null) {
    1293             setSrcKey(string);
    1294         }
    1295 
    1296         if ((string =
    1297                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    1298             setStyle(string);
    1299         }
    1300 
    1301         if ((string =
    1302                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    1303                     pageContext)) != null) {
    1304             setStyleClass(string);
    1305         }
    1306 
    1307         if ((string =
    1308                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    1309                     pageContext)) != null) {
    1310             setStyleId(string);
    1311         }
    1312 
    1313         if ((string =
    1314                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    1315             setTitle(string);
    1316         }
    1317 
    1318         if ((string =
    1319                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    1320                     pageContext)) != null) {
    1321             setTitleKey(string);
    1322         }
    1323 
    1324         if ((bool =
    1325                 EvalHelper.evalBoolean("useLocalEncoding",
    1326                     getUseLocalEncodingExpr(), this, pageContext)) != null) {
    1327             setUseLocalEncoding(bool.booleanValue());
    1328         }
    1329 
    1330         if ((string =
    1331                 EvalHelper.evalString("usemap", getUsemapExpr(), this,
    1332                     pageContext)) != null) {
    1333             setUsemap(string);
    1334         }
    1335 
    1336         if ((string =
    1337                 EvalHelper.evalString("vspace", getVspaceExpr(), this,
    1338                     pageContext)) != null) {
    1339             setVspace(string);
    1340         }
    1341 
    1342         if ((string =
    1343                 EvalHelper.evalString("width", getWidthExpr(), this, pageContext)) != null) {
    1344             setWidth(string);
    1345         }
    1346     }
    1347 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
