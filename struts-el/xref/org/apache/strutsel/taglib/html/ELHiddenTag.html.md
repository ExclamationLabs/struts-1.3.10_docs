[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELHiddenTag.html)


    1   /*
    2    * $Id: ELHiddenTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.HiddenTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag for input fields of type "hidden". <p> This class is a subclass
    30   * of the class <code>org.apache.struts.taglib.html.md.HiddenTag</code> which
    31   * provides most of the described functionality.  This subclass allows all
    32   * attribute values to be specified as expressions utilizing the JavaServer
    33   * Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELHiddenTag extends HiddenTag {
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
    75       * Instance variable mapped to "indexed" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String indexedExpr;
    79  
    80      /**
    81       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String langExpr;
    85  
    86      /**
    87       * Instance variable mapped to "name" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String nameExpr;
    91  
    92      /**
    93       * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String onblurExpr;
    97  
    98      /**
    99       * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String onchangeExpr;
    103 
    104     /**
    105      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String onclickExpr;
    109 
    110     /**
    111      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String ondblclickExpr;
    115 
    116     /**
    117      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String onfocusExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onkeydownExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    130      * associated BeanInfo class.)
    131      */
    132     private String onkeypressExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    136      * associated BeanInfo class.)
    137      */
    138     private String onkeyupExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    142      * in associated BeanInfo class.)
    143      */
    144     private String onmousedownExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    148      * in associated BeanInfo class.)
    149      */
    150     private String onmousemoveExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onmouseoutExpr;
    157 
    158     /**
    159      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    160      * in associated BeanInfo class.)
    161      */
    162     private String onmouseoverExpr;
    163 
    164     /**
    165      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     private String onmouseupExpr;
    169 
    170     /**
    171      * Instance variable mapped to "property" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     private String propertyExpr;
    175 
    176     /**
    177      * Instance variable mapped to "style" tag attribute. (Mapping set in
    178      * associated BeanInfo class.)
    179      */
    180     private String styleExpr;
    181 
    182     /**
    183      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     private String styleClassExpr;
    187 
    188     /**
    189      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String styleIdExpr;
    193 
    194     /**
    195      * Instance variable mapped to "title" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String titleExpr;
    199 
    200     /**
    201      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String titleKeyExpr;
    205 
    206     /**
    207      * Instance variable mapped to "value" tag attribute. (Mapping set in
    208      * associated BeanInfo class.)
    209      */
    210     private String valueExpr;
    211 
    212     /**
    213      * Instance variable mapped to "write" tag attribute. (Mapping set in
    214      * associated BeanInfo class.)
    215      */
    216     private String writeExpr;
    217 
    218     /**
    219      * Getter method for "accesskey" tag attribute. (Mapping set in associated
    220      * BeanInfo class.)
    221      */
    222     public String getAccesskeyExpr() {
    223         return (accesskeyExpr);
    224     }
    225 
    226     /**
    227      * Getter method for "alt" tag attribute. (Mapping set in associated
    228      * BeanInfo class.)
    229      */
    230     public String getAltExpr() {
    231         return (altExpr);
    232     }
    233 
    234     /**
    235      * Getter method for "altKey" tag attribute. (Mapping set in associated
    236      * BeanInfo class.)
    237      */
    238     public String getAltKeyExpr() {
    239         return (altKeyExpr);
    240     }
    241 
    242     /**
    243      * Getter method for "bundle" tag attribute. (Mapping set in associated
    244      * BeanInfo class.)
    245      */
    246     public String getBundleExpr() {
    247         return (bundleExpr);
    248     }
    249 
    250     /**
    251      * Getter method for "dir" tag attribute. (Mapping set in associated
    252      * BeanInfo class.)
    253      */
    254     public String getDirExpr() {
    255         return (dirExpr);
    256     }
    257 
    258     /**
    259      * Getter method for "disabled" tag attribute. (Mapping set in associated
    260      * BeanInfo class.)
    261      */
    262     public String getDisabledExpr() {
    263         return (disabledExpr);
    264     }
    265 
    266     /**
    267      * Getter method for "indexed" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public String getIndexedExpr() {
    271         return (indexedExpr);
    272     }
    273 
    274     /**
    275      * Getter method for "lang" tag attribute. (Mapping set in associated
    276      * BeanInfo class.)
    277      */
    278     public String getLangExpr() {
    279         return (langExpr);
    280     }
    281 
    282     /**
    283      * Getter method for "name" tag attribute. (Mapping set in associated
    284      * BeanInfo class.)
    285      */
    286     public String getNameExpr() {
    287         return (nameExpr);
    288     }
    289 
    290     /**
    291      * Getter method for "onblur" tag attribute. (Mapping set in associated
    292      * BeanInfo class.)
    293      */
    294     public String getOnblurExpr() {
    295         return (onblurExpr);
    296     }
    297 
    298     /**
    299      * Getter method for "onchange" tag attribute. (Mapping set in associated
    300      * BeanInfo class.)
    301      */
    302     public String getOnchangeExpr() {
    303         return (onchangeExpr);
    304     }
    305 
    306     /**
    307      * Getter method for "onclick" tag attribute. (Mapping set in associated
    308      * BeanInfo class.)
    309      */
    310     public String getOnclickExpr() {
    311         return (onclickExpr);
    312     }
    313 
    314     /**
    315      * Getter method for "ondblclick" tag attribute. (Mapping set in
    316      * associated BeanInfo class.)
    317      */
    318     public String getOndblclickExpr() {
    319         return (ondblclickExpr);
    320     }
    321 
    322     /**
    323      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    324      * BeanInfo class.)
    325      */
    326     public String getOnfocusExpr() {
    327         return (onfocusExpr);
    328     }
    329 
    330     /**
    331      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    332      * BeanInfo class.)
    333      */
    334     public String getOnkeydownExpr() {
    335         return (onkeydownExpr);
    336     }
    337 
    338     /**
    339      * Getter method for "onkeypress" tag attribute. (Mapping set in
    340      * associated BeanInfo class.)
    341      */
    342     public String getOnkeypressExpr() {
    343         return (onkeypressExpr);
    344     }
    345 
    346     /**
    347      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    348      * BeanInfo class.)
    349      */
    350     public String getOnkeyupExpr() {
    351         return (onkeyupExpr);
    352     }
    353 
    354     /**
    355      * Getter method for "onmousedown" tag attribute. (Mapping set in
    356      * associated BeanInfo class.)
    357      */
    358     public String getOnmousedownExpr() {
    359         return (onmousedownExpr);
    360     }
    361 
    362     /**
    363      * Getter method for "onmousemove" tag attribute. (Mapping set in
    364      * associated BeanInfo class.)
    365      */
    366     public String getOnmousemoveExpr() {
    367         return (onmousemoveExpr);
    368     }
    369 
    370     /**
    371      * Getter method for "onmouseout" tag attribute. (Mapping set in
    372      * associated BeanInfo class.)
    373      */
    374     public String getOnmouseoutExpr() {
    375         return (onmouseoutExpr);
    376     }
    377 
    378     /**
    379      * Getter method for "onmouseover" tag attribute. (Mapping set in
    380      * associated BeanInfo class.)
    381      */
    382     public String getOnmouseoverExpr() {
    383         return (onmouseoverExpr);
    384     }
    385 
    386     /**
    387      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    388      * BeanInfo class.)
    389      */
    390     public String getOnmouseupExpr() {
    391         return (onmouseupExpr);
    392     }
    393 
    394     /**
    395      * Getter method for "property" tag attribute. (Mapping set in associated
    396      * BeanInfo class.)
    397      */
    398     public String getPropertyExpr() {
    399         return (propertyExpr);
    400     }
    401 
    402     /**
    403      * Getter method for "style" tag attribute. (Mapping set in associated
    404      * BeanInfo class.)
    405      */
    406     public String getStyleExpr() {
    407         return (styleExpr);
    408     }
    409 
    410     /**
    411      * Getter method for "styleClass" tag attribute. (Mapping set in
    412      * associated BeanInfo class.)
    413      */
    414     public String getStyleClassExpr() {
    415         return (styleClassExpr);
    416     }
    417 
    418     /**
    419      * Getter method for "styleId" tag attribute. (Mapping set in associated
    420      * BeanInfo class.)
    421      */
    422     public String getStyleIdExpr() {
    423         return (styleIdExpr);
    424     }
    425 
    426     /**
    427      * Getter method for "title" tag attribute. (Mapping set in associated
    428      * BeanInfo class.)
    429      */
    430     public String getTitleExpr() {
    431         return (titleExpr);
    432     }
    433 
    434     /**
    435      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    436      * BeanInfo class.)
    437      */
    438     public String getTitleKeyExpr() {
    439         return (titleKeyExpr);
    440     }
    441 
    442     /**
    443      * Getter method for "value" tag attribute. (Mapping set in associated
    444      * BeanInfo class.)
    445      */
    446     public String getValueExpr() {
    447         return (valueExpr);
    448     }
    449 
    450     /**
    451      * Getter method for "write" tag attribute. (Mapping set in associated
    452      * BeanInfo class.)
    453      */
    454     public String getWriteExpr() {
    455         return (writeExpr);
    456     }
    457 
    458     /**
    459      * Setter method for "accesskey" tag attribute. (Mapping set in associated
    460      * BeanInfo class.)
    461      */
    462     public void setAccesskeyExpr(String accesskeyExpr) {
    463         this.accesskeyExpr = accesskeyExpr;
    464     }
    465 
    466     /**
    467      * Setter method for "alt" tag attribute. (Mapping set in associated
    468      * BeanInfo class.)
    469      */
    470     public void setAltExpr(String altExpr) {
    471         this.altExpr = altExpr;
    472     }
    473 
    474     /**
    475      * Setter method for "altKey" tag attribute. (Mapping set in associated
    476      * BeanInfo class.)
    477      */
    478     public void setAltKeyExpr(String altKeyExpr) {
    479         this.altKeyExpr = altKeyExpr;
    480     }
    481 
    482     /**
    483      * Setter method for "bundle" tag attribute. (Mapping set in associated
    484      * BeanInfo class.)
    485      */
    486     public void setBundleExpr(String bundleExpr) {
    487         this.bundleExpr = bundleExpr;
    488     }
    489 
    490     /**
    491      * Setter method for "dir" tag attribute. (Mapping set in associated
    492      * BeanInfo class.)
    493      */
    494     public void setDirExpr(String dirExpr) {
    495         this.dirExpr = dirExpr;
    496     }
    497 
    498     /**
    499      * Setter method for "disabled" tag attribute. (Mapping set in associated
    500      * BeanInfo class.)
    501      */
    502     public void setDisabledExpr(String disabledExpr) {
    503         this.disabledExpr = disabledExpr;
    504     }
    505 
    506     /**
    507      * Setter method for "indexed" tag attribute. (Mapping set in associated
    508      * BeanInfo class.)
    509      */
    510     public void setIndexedExpr(String indexedExpr) {
    511         this.indexedExpr = indexedExpr;
    512     }
    513 
    514     /**
    515      * Setter method for "lang" tag attribute. (Mapping set in associated
    516      * BeanInfo class.)
    517      */
    518     public void setLangExpr(String langExpr) {
    519         this.langExpr = langExpr;
    520     }
    521 
    522     /**
    523      * Setter method for "name" tag attribute. (Mapping set in associated
    524      * BeanInfo class.)
    525      */
    526     public void setNameExpr(String nameExpr) {
    527         this.nameExpr = nameExpr;
    528     }
    529 
    530     /**
    531      * Setter method for "onblur" tag attribute. (Mapping set in associated
    532      * BeanInfo class.)
    533      */
    534     public void setOnblurExpr(String onblurExpr) {
    535         this.onblurExpr = onblurExpr;
    536     }
    537 
    538     /**
    539      * Setter method for "onchange" tag attribute. (Mapping set in associated
    540      * BeanInfo class.)
    541      */
    542     public void setOnchangeExpr(String onchangeExpr) {
    543         this.onchangeExpr = onchangeExpr;
    544     }
    545 
    546     /**
    547      * Setter method for "onclick" tag attribute. (Mapping set in associated
    548      * BeanInfo class.)
    549      */
    550     public void setOnclickExpr(String onclickExpr) {
    551         this.onclickExpr = onclickExpr;
    552     }
    553 
    554     /**
    555      * Setter method for "ondblclick" tag attribute. (Mapping set in
    556      * associated BeanInfo class.)
    557      */
    558     public void setOndblclickExpr(String ondblclickExpr) {
    559         this.ondblclickExpr = ondblclickExpr;
    560     }
    561 
    562     /**
    563      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    564      * BeanInfo class.)
    565      */
    566     public void setOnfocusExpr(String onfocusExpr) {
    567         this.onfocusExpr = onfocusExpr;
    568     }
    569 
    570     /**
    571      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    572      * BeanInfo class.)
    573      */
    574     public void setOnkeydownExpr(String onkeydownExpr) {
    575         this.onkeydownExpr = onkeydownExpr;
    576     }
    577 
    578     /**
    579      * Setter method for "onkeypress" tag attribute. (Mapping set in
    580      * associated BeanInfo class.)
    581      */
    582     public void setOnkeypressExpr(String onkeypressExpr) {
    583         this.onkeypressExpr = onkeypressExpr;
    584     }
    585 
    586     /**
    587      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    588      * BeanInfo class.)
    589      */
    590     public void setOnkeyupExpr(String onkeyupExpr) {
    591         this.onkeyupExpr = onkeyupExpr;
    592     }
    593 
    594     /**
    595      * Setter method for "onmousedown" tag attribute. (Mapping set in
    596      * associated BeanInfo class.)
    597      */
    598     public void setOnmousedownExpr(String onmousedownExpr) {
    599         this.onmousedownExpr = onmousedownExpr;
    600     }
    601 
    602     /**
    603      * Setter method for "onmousemove" tag attribute. (Mapping set in
    604      * associated BeanInfo class.)
    605      */
    606     public void setOnmousemoveExpr(String onmousemoveExpr) {
    607         this.onmousemoveExpr = onmousemoveExpr;
    608     }
    609 
    610     /**
    611      * Setter method for "onmouseout" tag attribute. (Mapping set in
    612      * associated BeanInfo class.)
    613      */
    614     public void setOnmouseoutExpr(String onmouseoutExpr) {
    615         this.onmouseoutExpr = onmouseoutExpr;
    616     }
    617 
    618     /**
    619      * Setter method for "onmouseover" tag attribute. (Mapping set in
    620      * associated BeanInfo class.)
    621      */
    622     public void setOnmouseoverExpr(String onmouseoverExpr) {
    623         this.onmouseoverExpr = onmouseoverExpr;
    624     }
    625 
    626     /**
    627      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    628      * BeanInfo class.)
    629      */
    630     public void setOnmouseupExpr(String onmouseupExpr) {
    631         this.onmouseupExpr = onmouseupExpr;
    632     }
    633 
    634     /**
    635      * Setter method for "property" tag attribute. (Mapping set in associated
    636      * BeanInfo class.)
    637      */
    638     public void setPropertyExpr(String propertyExpr) {
    639         this.propertyExpr = propertyExpr;
    640     }
    641 
    642     /**
    643      * Setter method for "style" tag attribute. (Mapping set in associated
    644      * BeanInfo class.)
    645      */
    646     public void setStyleExpr(String styleExpr) {
    647         this.styleExpr = styleExpr;
    648     }
    649 
    650     /**
    651      * Setter method for "styleClass" tag attribute. (Mapping set in
    652      * associated BeanInfo class.)
    653      */
    654     public void setStyleClassExpr(String styleClassExpr) {
    655         this.styleClassExpr = styleClassExpr;
    656     }
    657 
    658     /**
    659      * Setter method for "styleId" tag attribute. (Mapping set in associated
    660      * BeanInfo class.)
    661      */
    662     public void setStyleIdExpr(String styleIdExpr) {
    663         this.styleIdExpr = styleIdExpr;
    664     }
    665 
    666     /**
    667      * Setter method for "title" tag attribute. (Mapping set in associated
    668      * BeanInfo class.)
    669      */
    670     public void setTitleExpr(String titleExpr) {
    671         this.titleExpr = titleExpr;
    672     }
    673 
    674     /**
    675      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    676      * BeanInfo class.)
    677      */
    678     public void setTitleKeyExpr(String titleKeyExpr) {
    679         this.titleKeyExpr = titleKeyExpr;
    680     }
    681 
    682     /**
    683      * Setter method for "value" tag attribute. (Mapping set in associated
    684      * BeanInfo class.)
    685      */
    686     public void setValueExpr(String valueExpr) {
    687         this.valueExpr = valueExpr;
    688     }
    689 
    690     /**
    691      * Setter method for "write" tag attribute. (Mapping set in associated
    692      * BeanInfo class.)
    693      */
    694     public void setWriteExpr(String writeExpr) {
    695         this.writeExpr = writeExpr;
    696     }
    697 
    698     /**
    699      * Resets attribute values for tag reuse.
    700      */
    701     public void release() {
    702         super.release();
    703         setAccesskeyExpr(null);
    704         setAltExpr(null);
    705         setAltKeyExpr(null);
    706         setBundleExpr(null);
    707         setDirExpr(null);
    708         setDisabledExpr(null);
    709         setIndexedExpr(null);
    710         setLangExpr(null);
    711         setNameExpr(null);
    712         setOnblurExpr(null);
    713         setOnchangeExpr(null);
    714         setOnclickExpr(null);
    715         setOndblclickExpr(null);
    716         setOnfocusExpr(null);
    717         setOnkeydownExpr(null);
    718         setOnkeypressExpr(null);
    719         setOnkeyupExpr(null);
    720         setOnmousedownExpr(null);
    721         setOnmousemoveExpr(null);
    722         setOnmouseoutExpr(null);
    723         setOnmouseoverExpr(null);
    724         setOnmouseupExpr(null);
    725         setPropertyExpr(null);
    726         setStyleExpr(null);
    727         setStyleClassExpr(null);
    728         setStyleIdExpr(null);
    729         setTitleExpr(null);
    730         setTitleKeyExpr(null);
    731         setValueExpr(null);
    732         setWriteExpr(null);
    733     }
    734 
    735     /**
    736      * Process the start tag.
    737      *
    738      * @throws JspException if a JSP exception has occurred
    739      */
    740     public int doStartTag() throws JspException {
    741         evaluateExpressions();
    742 
    743         return (super.doStartTag());
    744     }
    745 
    746     /**
    747      * Processes all attribute values which use the JSTL expression evaluation
    748      * engine to determine their values.
    749      *
    750      * @throws JspException if a JSP exception has occurred
    751      */
    752     private void evaluateExpressions()
    753         throws JspException {
    754         String string = null;
    755         Boolean bool = null;
    756 
    757         if ((string =
    758                 EvalHelper.evalString("accesskey", getAccesskeyExpr(), this,
    759                     pageContext)) != null) {
    760             setAccesskey(string);
    761         }
    762 
    763         if ((string =
    764                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    765             setAlt(string);
    766         }
    767 
    768         if ((string =
    769                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    770                     pageContext)) != null) {
    771             setAltKey(string);
    772         }
    773 
    774         if ((string =
    775                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    776                     pageContext)) != null) {
    777             setBundle(string);
    778         }
    779 
    780         if ((string =
    781                  EvalHelper.evalString("dir", getDirExpr(), this,
    782                          pageContext)) != null) {
    783          setDir(string);
    784         }
    785         
    786         if ((bool =
    787                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    788                     pageContext)) != null) {
    789             setDisabled(bool.booleanValue());
    790         }
    791 
    792         if ((bool =
    793                 EvalHelper.evalBoolean("indexed", getIndexedExpr(), this,
    794                     pageContext)) != null) {
    795             setIndexed(bool.booleanValue());
    796         }
    797 
    798         if ((string =
    799                  EvalHelper.evalString("lang", getLangExpr(), this,
    800                          pageContext)) != null) {
    801          setLang(string);
    802         }
    803 
    804         if ((string =
    805                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    806             setName(string);
    807         }
    808 
    809         if ((string =
    810                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    811                     pageContext)) != null) {
    812             setOnblur(string);
    813         }
    814 
    815         if ((string =
    816                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    817                     pageContext)) != null) {
    818             setOnchange(string);
    819         }
    820 
    821         if ((string =
    822                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    823                     pageContext)) != null) {
    824             setOnclick(string);
    825         }
    826 
    827         if ((string =
    828                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    829                     pageContext)) != null) {
    830             setOndblclick(string);
    831         }
    832 
    833         if ((string =
    834                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    835                     pageContext)) != null) {
    836             setOnfocus(string);
    837         }
    838 
    839         if ((string =
    840                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    841                     pageContext)) != null) {
    842             setOnkeydown(string);
    843         }
    844 
    845         if ((string =
    846                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    847                     pageContext)) != null) {
    848             setOnkeypress(string);
    849         }
    850 
    851         if ((string =
    852                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    853                     pageContext)) != null) {
    854             setOnkeyup(string);
    855         }
    856 
    857         if ((string =
    858                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    859                     this, pageContext)) != null) {
    860             setOnmousedown(string);
    861         }
    862 
    863         if ((string =
    864                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    865                     this, pageContext)) != null) {
    866             setOnmousemove(string);
    867         }
    868 
    869         if ((string =
    870                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    871                     pageContext)) != null) {
    872             setOnmouseout(string);
    873         }
    874 
    875         if ((string =
    876                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    877                     this, pageContext)) != null) {
    878             setOnmouseover(string);
    879         }
    880 
    881         if ((string =
    882                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    883                     pageContext)) != null) {
    884             setOnmouseup(string);
    885         }
    886 
    887         if ((string =
    888                 EvalHelper.evalString("property", getPropertyExpr(), this,
    889                     pageContext)) != null) {
    890             setProperty(string);
    891         }
    892 
    893         if ((string =
    894                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    895             setStyle(string);
    896         }
    897 
    898         if ((string =
    899                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    900                     pageContext)) != null) {
    901             setStyleClass(string);
    902         }
    903 
    904         if ((string =
    905                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    906                     pageContext)) != null) {
    907             setStyleId(string);
    908         }
    909 
    910         if ((string =
    911                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    912             setTitle(string);
    913         }
    914 
    915         if ((string =
    916                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    917                     pageContext)) != null) {
    918             setTitleKey(string);
    919         }
    920 
    921         if ((string =
    922                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    923             setValue(string);
    924         }
    925 
    926         if ((bool =
    927                 EvalHelper.evalBoolean("write", getWriteExpr(), this,
    928                     pageContext)) != null) {
    929             setWrite(bool.booleanValue());
    930         }
    931     }
    932 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
