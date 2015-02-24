[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELMultiboxTag.html)


    1   /*
    2    * $Id: ELMultiboxTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.MultiboxTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for input fields of type "checkbox".  This differs from CheckboxTag
    30   * because it assumes that the underlying property is an array getter (of any
    31   * supported primitive type, or String), and the checkbox is initialized to
    32   * "checked" if the value listed for the "value" attribute is present in the
    33   * values returned by the property getter. <p> This class is a subclass of the
    34   * class <code>org.apache.struts.taglib.html.md.MultiboxTag</code> which provides
    35   * most of the described functionality.  This subclass allows all attribute
    36   * values to be specified as expressions utilizing the JavaServer Pages
    37   * Standard Library expression language.
    38   *
    39   * @version $Rev: 471754 $
    40   */
    41  public class ELMultiboxTag extends MultiboxTag {
    42      /**
    43       * Instance variable mapped to "accessKey" tag attribute. (Mapping set in
    44       * associated BeanInfo class.)
    45       */
    46      private String accessKeyExpr;
    47  
    48      /**
    49       * Instance variable mapped to "alt" tag attribute. (Mapping set in
    50       * associated BeanInfo class.)
    51       */
    52      private String altExpr;
    53  
    54      /**
    55       * Instance variable mapped to "altKey" tag attribute. (Mapping set in
    56       * associated BeanInfo class.)
    57       */
    58      private String altKeyExpr;
    59  
    60      /**
    61       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    62       * associated BeanInfo class.)
    63       */
    64      private String bundleExpr;
    65  
    66      /**
    67       * Instance variable mapped to "disabled" tag attribute. (Mapping set in
    68       * associated BeanInfo class.)
    69       */
    70      private String disabledExpr;
    71  
    72      /**
    73       * Instance variable mapped to "errorKey" tag attribute. (Mapping set in
    74       * associated BeanInfo class.)
    75       */
    76      private String errorKeyExpr;
    77  
    78      /**
    79       * Instance variable mapped to "errorStyle" tag attribute. (Mapping set in
    80       * associated BeanInfo class.)
    81       */
    82      private String errorStyleExpr;
    83  
    84      /**
    85       * Instance variable mapped to "errorStyleClass" tag attribute. (Mapping
    86       * set in associated BeanInfo class.)
    87       */
    88      private String errorStyleClassExpr;
    89  
    90      /**
    91       * Instance variable mapped to "errorStyleId" tag attribute. (Mapping set
    92       * in associated BeanInfo class.)
    93       */
    94      private String errorStyleIdExpr;
    95  
    96      /**
    97       * Instance variable mapped to "name" tag attribute. (Mapping set in
    98       * associated BeanInfo class.)
    99       */
    100     private String nameExpr;
    101 
    102     /**
    103      * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    104      * associated BeanInfo class.)
    105      */
    106     private String onblurExpr;
    107 
    108     /**
    109      * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    110      * associated BeanInfo class.)
    111      */
    112     private String onchangeExpr;
    113 
    114     /**
    115      * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    116      * associated BeanInfo class.)
    117      */
    118     private String onclickExpr;
    119 
    120     /**
    121      * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    122      * associated BeanInfo class.)
    123      */
    124     private String ondblclickExpr;
    125 
    126     /**
    127      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    128      * associated BeanInfo class.)
    129      */
    130     private String onfocusExpr;
    131 
    132     /**
    133      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    134      * associated BeanInfo class.)
    135      */
    136     private String onkeydownExpr;
    137 
    138     /**
    139      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    140      * associated BeanInfo class.)
    141      */
    142     private String onkeypressExpr;
    143 
    144     /**
    145      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    146      * associated BeanInfo class.)
    147      */
    148     private String onkeyupExpr;
    149 
    150     /**
    151      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    152      * in associated BeanInfo class.)
    153      */
    154     private String onmousedownExpr;
    155 
    156     /**
    157      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    158      * in associated BeanInfo class.)
    159      */
    160     private String onmousemoveExpr;
    161 
    162     /**
    163      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    164      * associated BeanInfo class.)
    165      */
    166     private String onmouseoutExpr;
    167 
    168     /**
    169      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    170      * in associated BeanInfo class.)
    171      */
    172     private String onmouseoverExpr;
    173 
    174     /**
    175      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    176      * associated BeanInfo class.)
    177      */
    178     private String onmouseupExpr;
    179 
    180     /**
    181      * Instance variable mapped to "property" tag attribute. (Mapping set in
    182      * associated BeanInfo class.)
    183      */
    184     private String propertyExpr;
    185 
    186     /**
    187      * Instance variable mapped to "style" tag attribute. (Mapping set in
    188      * associated BeanInfo class.)
    189      */
    190     private String styleExpr;
    191 
    192     /**
    193      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    194      * associated BeanInfo class.)
    195      */
    196     private String styleClassExpr;
    197 
    198     /**
    199      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    200      * associated BeanInfo class.)
    201      */
    202     private String styleIdExpr;
    203 
    204     /**
    205      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    206      * associated BeanInfo class.)
    207      */
    208     private String tabindexExpr;
    209 
    210     /**
    211      * Instance variable mapped to "title" tag attribute. (Mapping set in
    212      * associated BeanInfo class.)
    213      */
    214     private String titleExpr;
    215 
    216     /**
    217      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    218      * associated BeanInfo class.)
    219      */
    220     private String titleKeyExpr;
    221 
    222     /**
    223      * Instance variable mapped to "value" tag attribute. (Mapping set in
    224      * associated BeanInfo class.)
    225      */
    226     private String valueExpr;
    227 
    228     /**
    229      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    230      * BeanInfo class.)
    231      */
    232     public String getAccesskeyExpr() {
    233         return (accessKeyExpr);
    234     }
    235 
    236     /**
    237      * Getter method for "alt" tag attribute. (Mapping set in associated
    238      * BeanInfo class.)
    239      */
    240     public String getAltExpr() {
    241         return (altExpr);
    242     }
    243 
    244     /**
    245      * Getter method for "altKey" tag attribute. (Mapping set in associated
    246      * BeanInfo class.)
    247      */
    248     public String getAltKeyExpr() {
    249         return (altKeyExpr);
    250     }
    251 
    252     /**
    253      * Getter method for "bundle" tag attribute. (Mapping set in associated
    254      * BeanInfo class.)
    255      */
    256     public String getBundleExpr() {
    257         return (bundleExpr);
    258     }
    259 
    260     /**
    261      * Getter method for "disabled" tag attribute. (Mapping set in associated
    262      * BeanInfo class.)
    263      */
    264     public String getDisabledExpr() {
    265         return (disabledExpr);
    266     }
    267 
    268     /**
    269      * Getter method for "errorKey" tag attribute. (Mapping set in associated
    270      * BeanInfo class.)
    271      */
    272     public String getErrorKeyExpr() {
    273         return (errorKeyExpr);
    274     }
    275 
    276     /**
    277      * Getter method for "errorStyle" tag attribute. (Mapping set in
    278      * associated BeanInfo class.)
    279      */
    280     public String getErrorStyleExpr() {
    281         return (errorStyleExpr);
    282     }
    283 
    284     /**
    285      * Getter method for "errorStyleClass" tag attribute. (Mapping set in
    286      * associated BeanInfo class.)
    287      */
    288     public String getErrorStyleClassExpr() {
    289         return (errorStyleClassExpr);
    290     }
    291 
    292     /**
    293      * Getter method for "errorStyleId" tag attribute. (Mapping set in
    294      * associated BeanInfo class.)
    295      */
    296     public String getErrorStyleIdExpr() {
    297         return (errorStyleIdExpr);
    298     }
    299 
    300     /**
    301      * Getter method for "name" tag attribute. (Mapping set in associated
    302      * BeanInfo class.)
    303      */
    304     public String getNameExpr() {
    305         return (nameExpr);
    306     }
    307 
    308     /**
    309      * Getter method for "onblur" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public String getOnblurExpr() {
    313         return (onblurExpr);
    314     }
    315 
    316     /**
    317      * Getter method for "onchange" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public String getOnchangeExpr() {
    321         return (onchangeExpr);
    322     }
    323 
    324     /**
    325      * Getter method for "onclick" tag attribute. (Mapping set in associated
    326      * BeanInfo class.)
    327      */
    328     public String getOnclickExpr() {
    329         return (onclickExpr);
    330     }
    331 
    332     /**
    333      * Getter method for "ondblclick" tag attribute. (Mapping set in
    334      * associated BeanInfo class.)
    335      */
    336     public String getOndblclickExpr() {
    337         return (ondblclickExpr);
    338     }
    339 
    340     /**
    341      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    342      * BeanInfo class.)
    343      */
    344     public String getOnfocusExpr() {
    345         return (onfocusExpr);
    346     }
    347 
    348     /**
    349      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    350      * BeanInfo class.)
    351      */
    352     public String getOnkeydownExpr() {
    353         return (onkeydownExpr);
    354     }
    355 
    356     /**
    357      * Getter method for "onkeypress" tag attribute. (Mapping set in
    358      * associated BeanInfo class.)
    359      */
    360     public String getOnkeypressExpr() {
    361         return (onkeypressExpr);
    362     }
    363 
    364     /**
    365      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    366      * BeanInfo class.)
    367      */
    368     public String getOnkeyupExpr() {
    369         return (onkeyupExpr);
    370     }
    371 
    372     /**
    373      * Getter method for "onmousedown" tag attribute. (Mapping set in
    374      * associated BeanInfo class.)
    375      */
    376     public String getOnmousedownExpr() {
    377         return (onmousedownExpr);
    378     }
    379 
    380     /**
    381      * Getter method for "onmousemove" tag attribute. (Mapping set in
    382      * associated BeanInfo class.)
    383      */
    384     public String getOnmousemoveExpr() {
    385         return (onmousemoveExpr);
    386     }
    387 
    388     /**
    389      * Getter method for "onmouseout" tag attribute. (Mapping set in
    390      * associated BeanInfo class.)
    391      */
    392     public String getOnmouseoutExpr() {
    393         return (onmouseoutExpr);
    394     }
    395 
    396     /**
    397      * Getter method for "onmouseover" tag attribute. (Mapping set in
    398      * associated BeanInfo class.)
    399      */
    400     public String getOnmouseoverExpr() {
    401         return (onmouseoverExpr);
    402     }
    403 
    404     /**
    405      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    406      * BeanInfo class.)
    407      */
    408     public String getOnmouseupExpr() {
    409         return (onmouseupExpr);
    410     }
    411 
    412     /**
    413      * Getter method for "property" tag attribute. (Mapping set in associated
    414      * BeanInfo class.)
    415      */
    416     public String getPropertyExpr() {
    417         return (propertyExpr);
    418     }
    419 
    420     /**
    421      * Getter method for "style" tag attribute. (Mapping set in associated
    422      * BeanInfo class.)
    423      */
    424     public String getStyleExpr() {
    425         return (styleExpr);
    426     }
    427 
    428     /**
    429      * Getter method for "styleClass" tag attribute. (Mapping set in
    430      * associated BeanInfo class.)
    431      */
    432     public String getStyleClassExpr() {
    433         return (styleClassExpr);
    434     }
    435 
    436     /**
    437      * Getter method for "styleId" tag attribute. (Mapping set in associated
    438      * BeanInfo class.)
    439      */
    440     public String getStyleIdExpr() {
    441         return (styleIdExpr);
    442     }
    443 
    444     /**
    445      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    446      * BeanInfo class.)
    447      */
    448     public String getTabindexExpr() {
    449         return (tabindexExpr);
    450     }
    451 
    452     /**
    453      * Getter method for "title" tag attribute. (Mapping set in associated
    454      * BeanInfo class.)
    455      */
    456     public String getTitleExpr() {
    457         return (titleExpr);
    458     }
    459 
    460     /**
    461      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    462      * BeanInfo class.)
    463      */
    464     public String getTitleKeyExpr() {
    465         return (titleKeyExpr);
    466     }
    467 
    468     /**
    469      * Getter method for "value" tag attribute. (Mapping set in associated
    470      * BeanInfo class.)
    471      */
    472     public String getValueExpr() {
    473         return (valueExpr);
    474     }
    475 
    476     /**
    477      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    478      * BeanInfo class.)
    479      */
    480     public void setAccesskeyExpr(String accessKeyExpr) {
    481         this.accessKeyExpr = accessKeyExpr;
    482     }
    483 
    484     /**
    485      * Setter method for "alt" tag attribute. (Mapping set in associated
    486      * BeanInfo class.)
    487      */
    488     public void setAltExpr(String altExpr) {
    489         this.altExpr = altExpr;
    490     }
    491 
    492     /**
    493      * Setter method for "altKey" tag attribute. (Mapping set in associated
    494      * BeanInfo class.)
    495      */
    496     public void setAltKeyExpr(String altKeyExpr) {
    497         this.altKeyExpr = altKeyExpr;
    498     }
    499 
    500     /**
    501      * Setter method for "bundle" tag attribute. (Mapping set in associated
    502      * BeanInfo class.)
    503      */
    504     public void setBundleExpr(String bundleExpr) {
    505         this.bundleExpr = bundleExpr;
    506     }
    507 
    508     /**
    509      * Setter method for "disabled" tag attribute. (Mapping set in associated
    510      * BeanInfo class.)
    511      */
    512     public void setDisabledExpr(String disabledExpr) {
    513         this.disabledExpr = disabledExpr;
    514     }
    515 
    516     /**
    517      * Setter method for "errorKey" tag attribute. (Mapping set in associated
    518      * BeanInfo class.)
    519      */
    520     public void setErrorKeyExpr(String errorKeyExpr) {
    521         this.errorKeyExpr = errorKeyExpr;
    522     }
    523 
    524     /**
    525      * Setter method for "errorStyle" tag attribute. (Mapping set in
    526      * associated BeanInfo class.)
    527      */
    528     public void setErrorStyleExpr(String errorStyleExpr) {
    529         this.errorStyleExpr = errorStyleExpr;
    530     }
    531 
    532     /**
    533      * Setter method for "errorStyleClass" tag attribute. (Mapping set in
    534      * associated BeanInfo class.)
    535      */
    536     public void setErrorStyleClassExpr(String errorStyleClassExpr) {
    537         this.errorStyleClassExpr = errorStyleClassExpr;
    538     }
    539 
    540     /**
    541      * Setter method for "errorStyleId" tag attribute. (Mapping set in
    542      * associated BeanInfo class.)
    543      */
    544     public void setErrorStyleIdExpr(String errorStyleIdExpr) {
    545         this.errorStyleIdExpr = errorStyleIdExpr;
    546     }
    547 
    548     /**
    549      * Setter method for "name" tag attribute. (Mapping set in associated
    550      * BeanInfo class.)
    551      */
    552     public void setNameExpr(String nameExpr) {
    553         this.nameExpr = nameExpr;
    554     }
    555 
    556     /**
    557      * Setter method for "onblur" tag attribute. (Mapping set in associated
    558      * BeanInfo class.)
    559      */
    560     public void setOnblurExpr(String onblurExpr) {
    561         this.onblurExpr = onblurExpr;
    562     }
    563 
    564     /**
    565      * Setter method for "onchange" tag attribute. (Mapping set in associated
    566      * BeanInfo class.)
    567      */
    568     public void setOnchangeExpr(String onchangeExpr) {
    569         this.onchangeExpr = onchangeExpr;
    570     }
    571 
    572     /**
    573      * Setter method for "onclick" tag attribute. (Mapping set in associated
    574      * BeanInfo class.)
    575      */
    576     public void setOnclickExpr(String onclickExpr) {
    577         this.onclickExpr = onclickExpr;
    578     }
    579 
    580     /**
    581      * Setter method for "ondblclick" tag attribute. (Mapping set in
    582      * associated BeanInfo class.)
    583      */
    584     public void setOndblclickExpr(String ondblclickExpr) {
    585         this.ondblclickExpr = ondblclickExpr;
    586     }
    587 
    588     /**
    589      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    590      * BeanInfo class.)
    591      */
    592     public void setOnfocusExpr(String onfocusExpr) {
    593         this.onfocusExpr = onfocusExpr;
    594     }
    595 
    596     /**
    597      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    598      * BeanInfo class.)
    599      */
    600     public void setOnkeydownExpr(String onkeydownExpr) {
    601         this.onkeydownExpr = onkeydownExpr;
    602     }
    603 
    604     /**
    605      * Setter method for "onkeypress" tag attribute. (Mapping set in
    606      * associated BeanInfo class.)
    607      */
    608     public void setOnkeypressExpr(String onkeypressExpr) {
    609         this.onkeypressExpr = onkeypressExpr;
    610     }
    611 
    612     /**
    613      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    614      * BeanInfo class.)
    615      */
    616     public void setOnkeyupExpr(String onkeyupExpr) {
    617         this.onkeyupExpr = onkeyupExpr;
    618     }
    619 
    620     /**
    621      * Setter method for "onmousedown" tag attribute. (Mapping set in
    622      * associated BeanInfo class.)
    623      */
    624     public void setOnmousedownExpr(String onmousedownExpr) {
    625         this.onmousedownExpr = onmousedownExpr;
    626     }
    627 
    628     /**
    629      * Setter method for "onmousemove" tag attribute. (Mapping set in
    630      * associated BeanInfo class.)
    631      */
    632     public void setOnmousemoveExpr(String onmousemoveExpr) {
    633         this.onmousemoveExpr = onmousemoveExpr;
    634     }
    635 
    636     /**
    637      * Setter method for "onmouseout" tag attribute. (Mapping set in
    638      * associated BeanInfo class.)
    639      */
    640     public void setOnmouseoutExpr(String onmouseoutExpr) {
    641         this.onmouseoutExpr = onmouseoutExpr;
    642     }
    643 
    644     /**
    645      * Setter method for "onmouseover" tag attribute. (Mapping set in
    646      * associated BeanInfo class.)
    647      */
    648     public void setOnmouseoverExpr(String onmouseoverExpr) {
    649         this.onmouseoverExpr = onmouseoverExpr;
    650     }
    651 
    652     /**
    653      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    654      * BeanInfo class.)
    655      */
    656     public void setOnmouseupExpr(String onmouseupExpr) {
    657         this.onmouseupExpr = onmouseupExpr;
    658     }
    659 
    660     /**
    661      * Setter method for "property" tag attribute. (Mapping set in associated
    662      * BeanInfo class.)
    663      */
    664     public void setPropertyExpr(String propertyExpr) {
    665         this.propertyExpr = propertyExpr;
    666     }
    667 
    668     /**
    669      * Setter method for "style" tag attribute. (Mapping set in associated
    670      * BeanInfo class.)
    671      */
    672     public void setStyleExpr(String styleExpr) {
    673         this.styleExpr = styleExpr;
    674     }
    675 
    676     /**
    677      * Setter method for "styleClass" tag attribute. (Mapping set in
    678      * associated BeanInfo class.)
    679      */
    680     public void setStyleClassExpr(String styleClassExpr) {
    681         this.styleClassExpr = styleClassExpr;
    682     }
    683 
    684     /**
    685      * Setter method for "styleId" tag attribute. (Mapping set in associated
    686      * BeanInfo class.)
    687      */
    688     public void setStyleIdExpr(String styleIdExpr) {
    689         this.styleIdExpr = styleIdExpr;
    690     }
    691 
    692     /**
    693      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    694      * BeanInfo class.)
    695      */
    696     public void setTabindexExpr(String tabindexExpr) {
    697         this.tabindexExpr = tabindexExpr;
    698     }
    699 
    700     /**
    701      * Setter method for "title" tag attribute. (Mapping set in associated
    702      * BeanInfo class.)
    703      */
    704     public void setTitleExpr(String titleExpr) {
    705         this.titleExpr = titleExpr;
    706     }
    707 
    708     /**
    709      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    710      * BeanInfo class.)
    711      */
    712     public void setTitleKeyExpr(String titleKeyExpr) {
    713         this.titleKeyExpr = titleKeyExpr;
    714     }
    715 
    716     /**
    717      * Setter method for "value" tag attribute. (Mapping set in associated
    718      * BeanInfo class.)
    719      */
    720     public void setValueExpr(String valueExpr) {
    721         this.valueExpr = valueExpr;
    722     }
    723 
    724     /**
    725      * Resets attribute values for tag reuse.
    726      */
    727     public void release() {
    728         super.release();
    729         setAccesskeyExpr(null);
    730         setAltExpr(null);
    731         setAltKeyExpr(null);
    732         setBundleExpr(null);
    733         setDisabledExpr(null);
    734         setErrorKeyExpr(null);
    735         setErrorStyleExpr(null);
    736         setErrorStyleClassExpr(null);
    737         setErrorStyleIdExpr(null);
    738         setNameExpr(null);
    739         setOnblurExpr(null);
    740         setOnchangeExpr(null);
    741         setOnclickExpr(null);
    742         setOndblclickExpr(null);
    743         setOnfocusExpr(null);
    744         setOnkeydownExpr(null);
    745         setOnkeypressExpr(null);
    746         setOnkeyupExpr(null);
    747         setOnmousedownExpr(null);
    748         setOnmousemoveExpr(null);
    749         setOnmouseoutExpr(null);
    750         setOnmouseoverExpr(null);
    751         setOnmouseupExpr(null);
    752         setPropertyExpr(null);
    753         setStyleExpr(null);
    754         setStyleClassExpr(null);
    755         setStyleIdExpr(null);
    756         setTabindexExpr(null);
    757         setTitleExpr(null);
    758         setTitleKeyExpr(null);
    759         setValueExpr(null);
    760     }
    761 
    762     /**
    763      * Process the start tag.
    764      *
    765      * @throws JspException if a JSP exception has occurred
    766      */
    767     public int doStartTag() throws JspException {
    768         evaluateExpressions();
    769 
    770         return (super.doStartTag());
    771     }
    772 
    773     /**
    774      * Processes all attribute values which use the JSTL expression evaluation
    775      * engine to determine their values.
    776      *
    777      * @throws JspException if a JSP exception has occurred
    778      */
    779     private void evaluateExpressions()
    780         throws JspException {
    781         String string = null;
    782         Boolean bool = null;
    783 
    784         if ((string =
    785                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    786                     pageContext)) != null) {
    787             setAccesskey(string);
    788         }
    789 
    790         if ((string =
    791                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    792             setAlt(string);
    793         }
    794 
    795         if ((string =
    796                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    797                     pageContext)) != null) {
    798             setAltKey(string);
    799         }
    800 
    801         if ((string =
    802                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    803                     pageContext)) != null) {
    804             setBundle(string);
    805         }
    806 
    807         if ((bool =
    808                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    809                     pageContext)) != null) {
    810             setDisabled(bool.booleanValue());
    811         }
    812 
    813         if ((string =
    814                 EvalHelper.evalString("errorKey", getErrorKeyExpr(), this,
    815                     pageContext)) != null) {
    816             setErrorKey(string);
    817         }
    818 
    819         if ((string =
    820                 EvalHelper.evalString("errorStyle", getErrorStyleExpr(), this,
    821                     pageContext)) != null) {
    822             setErrorStyle(string);
    823         }
    824 
    825         if ((string =
    826                 EvalHelper.evalString("errorStyleClass",
    827                     getErrorStyleClassExpr(), this, pageContext)) != null) {
    828             setErrorStyleClass(string);
    829         }
    830 
    831         if ((string =
    832                 EvalHelper.evalString("errorStyleId", getErrorStyleIdExpr(),
    833                     this, pageContext)) != null) {
    834             setErrorStyleId(string);
    835         }
    836 
    837         if ((string =
    838                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    839             setName(string);
    840         }
    841 
    842         if ((string =
    843                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    844                     pageContext)) != null) {
    845             setOnblur(string);
    846         }
    847 
    848         if ((string =
    849                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    850                     pageContext)) != null) {
    851             setOnchange(string);
    852         }
    853 
    854         if ((string =
    855                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    856                     pageContext)) != null) {
    857             setOnclick(string);
    858         }
    859 
    860         if ((string =
    861                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    862                     pageContext)) != null) {
    863             setOndblclick(string);
    864         }
    865 
    866         if ((string =
    867                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    868                     pageContext)) != null) {
    869             setOnfocus(string);
    870         }
    871 
    872         if ((string =
    873                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    874                     pageContext)) != null) {
    875             setOnkeydown(string);
    876         }
    877 
    878         if ((string =
    879                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    880                     pageContext)) != null) {
    881             setOnkeypress(string);
    882         }
    883 
    884         if ((string =
    885                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    886                     pageContext)) != null) {
    887             setOnkeyup(string);
    888         }
    889 
    890         if ((string =
    891                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    892                     this, pageContext)) != null) {
    893             setOnmousedown(string);
    894         }
    895 
    896         if ((string =
    897                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    898                     this, pageContext)) != null) {
    899             setOnmousemove(string);
    900         }
    901 
    902         if ((string =
    903                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    904                     pageContext)) != null) {
    905             setOnmouseout(string);
    906         }
    907 
    908         if ((string =
    909                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    910                     this, pageContext)) != null) {
    911             setOnmouseover(string);
    912         }
    913 
    914         if ((string =
    915                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    916                     pageContext)) != null) {
    917             setOnmouseup(string);
    918         }
    919 
    920         if ((string =
    921                 EvalHelper.evalString("property", getPropertyExpr(), this,
    922                     pageContext)) != null) {
    923             setProperty(string);
    924         }
    925 
    926         if ((string =
    927                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    928             setStyle(string);
    929         }
    930 
    931         if ((string =
    932                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    933                     pageContext)) != null) {
    934             setStyleClass(string);
    935         }
    936 
    937         if ((string =
    938                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    939                     pageContext)) != null) {
    940             setStyleId(string);
    941         }
    942 
    943         if ((string =
    944                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    945                     pageContext)) != null) {
    946             setTabindex(string);
    947         }
    948 
    949         if ((string =
    950                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    951             setTitle(string);
    952         }
    953 
    954         if ((string =
    955                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    956                     pageContext)) != null) {
    957             setTitleKey(string);
    958         }
    959 
    960         if ((string =
    961                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    962             setValue(string);
    963         }
    964     }
    965 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
