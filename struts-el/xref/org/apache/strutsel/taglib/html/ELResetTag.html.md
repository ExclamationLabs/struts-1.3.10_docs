[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELResetTag.html)


    1   /*
    2    * $Id: ELResetTag.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.ResetTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for input fields of type "reset". <p> This class is a subclass of the
    30   * class <code>org.apache.struts.taglib.html.md.ResetTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 479635 $
    36   */
    37  public class ELResetTag extends ResetTag {
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
    75       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String langExpr;
    79  
    80      /**
    81       * Instance variable mapped to "onblur" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String onblurExpr;
    85  
    86      /**
    87       * Instance variable mapped to "onchange" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String onchangeExpr;
    91  
    92      /**
    93       * Instance variable mapped to "onclick" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String onclickExpr;
    97  
    98      /**
    99       * Instance variable mapped to "ondblclick" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String ondblclickExpr;
    103 
    104     /**
    105      * Instance variable mapped to "onfocus" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String onfocusExpr;
    109 
    110     /**
    111      * Instance variable mapped to "onkeydown" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String onkeydownExpr;
    115 
    116     /**
    117      * Instance variable mapped to "onkeypress" tag attribute. (Mapping set in
    118      * associated BeanInfo class.)
    119      */
    120     private String onkeypressExpr;
    121 
    122     /**
    123      * Instance variable mapped to "onkeyup" tag attribute. (Mapping set in
    124      * associated BeanInfo class.)
    125      */
    126     private String onkeyupExpr;
    127 
    128     /**
    129      * Instance variable mapped to "onmousedown" tag attribute. (Mapping set
    130      * in associated BeanInfo class.)
    131      */
    132     private String onmousedownExpr;
    133 
    134     /**
    135      * Instance variable mapped to "onmousemove" tag attribute. (Mapping set
    136      * in associated BeanInfo class.)
    137      */
    138     private String onmousemoveExpr;
    139 
    140     /**
    141      * Instance variable mapped to "onmouseout" tag attribute. (Mapping set in
    142      * associated BeanInfo class.)
    143      */
    144     private String onmouseoutExpr;
    145 
    146     /**
    147      * Instance variable mapped to "onmouseover" tag attribute. (Mapping set
    148      * in associated BeanInfo class.)
    149      */
    150     private String onmouseoverExpr;
    151 
    152     /**
    153      * Instance variable mapped to "onmouseup" tag attribute. (Mapping set in
    154      * associated BeanInfo class.)
    155      */
    156     private String onmouseupExpr;
    157 
    158     /**
    159      * Instance variable mapped to "property" tag attribute. (Mapping set in
    160      * associated BeanInfo class.)
    161      */
    162     private String propertyExpr;
    163 
    164     /**
    165      * Instance variable mapped to "style" tag attribute. (Mapping set in
    166      * associated BeanInfo class.)
    167      */
    168     private String styleExpr;
    169 
    170     /**
    171      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    172      * associated BeanInfo class.)
    173      */
    174     private String styleClassExpr;
    175 
    176     /**
    177      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    178      * associated BeanInfo class.)
    179      */
    180     private String styleIdExpr;
    181 
    182     /**
    183      * Instance variable mapped to "tabindex" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     private String tabindexExpr;
    187 
    188     /**
    189      * Instance variable mapped to "title" tag attribute. (Mapping set in
    190      * associated BeanInfo class.)
    191      */
    192     private String titleExpr;
    193 
    194     /**
    195      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     private String titleKeyExpr;
    199 
    200     /**
    201      * Instance variable mapped to "value" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     private String valueExpr;
    205 
    206     /**
    207      * Getter method for "accessKey" tag attribute. (Mapping set in associated
    208      * BeanInfo class.)
    209      */
    210     public String getAccesskeyExpr() {
    211         return (accessKeyExpr);
    212     }
    213 
    214     /**
    215      * Getter method for "alt" tag attribute. (Mapping set in associated
    216      * BeanInfo class.)
    217      */
    218     public String getAltExpr() {
    219         return (altExpr);
    220     }
    221 
    222     /**
    223      * Getter method for "altKey" tag attribute. (Mapping set in associated
    224      * BeanInfo class.)
    225      */
    226     public String getAltKeyExpr() {
    227         return (altKeyExpr);
    228     }
    229 
    230     /**
    231      * Getter method for "bundle" tag attribute. (Mapping set in associated
    232      * BeanInfo class.)
    233      */
    234     public String getBundleExpr() {
    235         return (bundleExpr);
    236     }
    237 
    238     /**
    239      * Getter method for "dir" tag attribute. (Mapping set in associated
    240      * BeanInfo class.)
    241      */
    242     public String getDirExpr() {
    243         return (dirExpr);
    244     }
    245 
    246     /**
    247      * Getter method for "disabled" tag attribute. (Mapping set in associated
    248      * BeanInfo class.)
    249      */
    250     public String getDisabledExpr() {
    251         return (disabledExpr);
    252     }
    253 
    254     /**
    255      * Getter method for "lang" tag attribute. (Mapping set in associated
    256      * BeanInfo class.)
    257      */
    258     public String getLangExpr() {
    259         return (langExpr);
    260     }
    261 
    262     /**
    263      * Getter method for "onblur" tag attribute. (Mapping set in associated
    264      * BeanInfo class.)
    265      */
    266     public String getOnblurExpr() {
    267         return (onblurExpr);
    268     }
    269 
    270     /**
    271      * Getter method for "onchange" tag attribute. (Mapping set in associated
    272      * BeanInfo class.)
    273      */
    274     public String getOnchangeExpr() {
    275         return (onchangeExpr);
    276     }
    277 
    278     /**
    279      * Getter method for "onclick" tag attribute. (Mapping set in associated
    280      * BeanInfo class.)
    281      */
    282     public String getOnclickExpr() {
    283         return (onclickExpr);
    284     }
    285 
    286     /**
    287      * Getter method for "ondblclick" tag attribute. (Mapping set in
    288      * associated BeanInfo class.)
    289      */
    290     public String getOndblclickExpr() {
    291         return (ondblclickExpr);
    292     }
    293 
    294     /**
    295      * Getter method for "onfocus" tag attribute. (Mapping set in associated
    296      * BeanInfo class.)
    297      */
    298     public String getOnfocusExpr() {
    299         return (onfocusExpr);
    300     }
    301 
    302     /**
    303      * Getter method for "onkeydown" tag attribute. (Mapping set in associated
    304      * BeanInfo class.)
    305      */
    306     public String getOnkeydownExpr() {
    307         return (onkeydownExpr);
    308     }
    309 
    310     /**
    311      * Getter method for "onkeypress" tag attribute. (Mapping set in
    312      * associated BeanInfo class.)
    313      */
    314     public String getOnkeypressExpr() {
    315         return (onkeypressExpr);
    316     }
    317 
    318     /**
    319      * Getter method for "onkeyup" tag attribute. (Mapping set in associated
    320      * BeanInfo class.)
    321      */
    322     public String getOnkeyupExpr() {
    323         return (onkeyupExpr);
    324     }
    325 
    326     /**
    327      * Getter method for "onmousedown" tag attribute. (Mapping set in
    328      * associated BeanInfo class.)
    329      */
    330     public String getOnmousedownExpr() {
    331         return (onmousedownExpr);
    332     }
    333 
    334     /**
    335      * Getter method for "onmousemove" tag attribute. (Mapping set in
    336      * associated BeanInfo class.)
    337      */
    338     public String getOnmousemoveExpr() {
    339         return (onmousemoveExpr);
    340     }
    341 
    342     /**
    343      * Getter method for "onmouseout" tag attribute. (Mapping set in
    344      * associated BeanInfo class.)
    345      */
    346     public String getOnmouseoutExpr() {
    347         return (onmouseoutExpr);
    348     }
    349 
    350     /**
    351      * Getter method for "onmouseover" tag attribute. (Mapping set in
    352      * associated BeanInfo class.)
    353      */
    354     public String getOnmouseoverExpr() {
    355         return (onmouseoverExpr);
    356     }
    357 
    358     /**
    359      * Getter method for "onmouseup" tag attribute. (Mapping set in associated
    360      * BeanInfo class.)
    361      */
    362     public String getOnmouseupExpr() {
    363         return (onmouseupExpr);
    364     }
    365 
    366     /**
    367      * Getter method for "property" tag attribute. (Mapping set in associated
    368      * BeanInfo class.)
    369      */
    370     public String getPropertyExpr() {
    371         return (propertyExpr);
    372     }
    373 
    374     /**
    375      * Getter method for "style" tag attribute. (Mapping set in associated
    376      * BeanInfo class.)
    377      */
    378     public String getStyleExpr() {
    379         return (styleExpr);
    380     }
    381 
    382     /**
    383      * Getter method for "styleClass" tag attribute. (Mapping set in
    384      * associated BeanInfo class.)
    385      */
    386     public String getStyleClassExpr() {
    387         return (styleClassExpr);
    388     }
    389 
    390     /**
    391      * Getter method for "styleId" tag attribute. (Mapping set in associated
    392      * BeanInfo class.)
    393      */
    394     public String getStyleIdExpr() {
    395         return (styleIdExpr);
    396     }
    397 
    398     /**
    399      * Getter method for "tabindex" tag attribute. (Mapping set in associated
    400      * BeanInfo class.)
    401      */
    402     public String getTabindexExpr() {
    403         return (tabindexExpr);
    404     }
    405 
    406     /**
    407      * Getter method for "title" tag attribute. (Mapping set in associated
    408      * BeanInfo class.)
    409      */
    410     public String getTitleExpr() {
    411         return (titleExpr);
    412     }
    413 
    414     /**
    415      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    416      * BeanInfo class.)
    417      */
    418     public String getTitleKeyExpr() {
    419         return (titleKeyExpr);
    420     }
    421 
    422     /**
    423      * Getter method for "value" tag attribute. (Mapping set in associated
    424      * BeanInfo class.)
    425      */
    426     public String getValueExpr() {
    427         return (valueExpr);
    428     }
    429 
    430     /**
    431      * Setter method for "accessKey" tag attribute. (Mapping set in associated
    432      * BeanInfo class.)
    433      */
    434     public void setAccesskeyExpr(String accessKeyExpr) {
    435         this.accessKeyExpr = accessKeyExpr;
    436     }
    437 
    438     /**
    439      * Setter method for "alt" tag attribute. (Mapping set in associated
    440      * BeanInfo class.)
    441      */
    442     public void setAltExpr(String altExpr) {
    443         this.altExpr = altExpr;
    444     }
    445 
    446     /**
    447      * Setter method for "altKey" tag attribute. (Mapping set in associated
    448      * BeanInfo class.)
    449      */
    450     public void setAltKeyExpr(String altKeyExpr) {
    451         this.altKeyExpr = altKeyExpr;
    452     }
    453 
    454     /**
    455      * Setter method for "bundle" tag attribute. (Mapping set in associated
    456      * BeanInfo class.)
    457      */
    458     public void setBundleExpr(String bundleExpr) {
    459         this.bundleExpr = bundleExpr;
    460     }
    461 
    462     /**
    463      * Setter method for "dir" tag attribute. (Mapping set in associated
    464      * BeanInfo class.)
    465      */
    466     public void setDirExpr(String dirExpr) {
    467         this.dirExpr = dirExpr;
    468     }
    469 
    470     /**
    471      * Setter method for "disabled" tag attribute. (Mapping set in associated
    472      * BeanInfo class.)
    473      */
    474     public void setDisabledExpr(String disabledExpr) {
    475         this.disabledExpr = disabledExpr;
    476     }
    477 
    478     /**
    479      * Setter method for "lang" tag attribute. (Mapping set in associated
    480      * BeanInfo class.)
    481      */
    482     public void setLangExpr(String langExpr) {
    483         this.langExpr = langExpr;
    484     }
    485 
    486     /**
    487      * Setter method for "onblur" tag attribute. (Mapping set in associated
    488      * BeanInfo class.)
    489      */
    490     public void setOnblurExpr(String onblurExpr) {
    491         this.onblurExpr = onblurExpr;
    492     }
    493 
    494     /**
    495      * Setter method for "onchange" tag attribute. (Mapping set in associated
    496      * BeanInfo class.)
    497      */
    498     public void setOnchangeExpr(String onchangeExpr) {
    499         this.onchangeExpr = onchangeExpr;
    500     }
    501 
    502     /**
    503      * Setter method for "onclick" tag attribute. (Mapping set in associated
    504      * BeanInfo class.)
    505      */
    506     public void setOnclickExpr(String onclickExpr) {
    507         this.onclickExpr = onclickExpr;
    508     }
    509 
    510     /**
    511      * Setter method for "ondblclick" tag attribute. (Mapping set in
    512      * associated BeanInfo class.)
    513      */
    514     public void setOndblclickExpr(String ondblclickExpr) {
    515         this.ondblclickExpr = ondblclickExpr;
    516     }
    517 
    518     /**
    519      * Setter method for "onfocus" tag attribute. (Mapping set in associated
    520      * BeanInfo class.)
    521      */
    522     public void setOnfocusExpr(String onfocusExpr) {
    523         this.onfocusExpr = onfocusExpr;
    524     }
    525 
    526     /**
    527      * Setter method for "onkeydown" tag attribute. (Mapping set in associated
    528      * BeanInfo class.)
    529      */
    530     public void setOnkeydownExpr(String onkeydownExpr) {
    531         this.onkeydownExpr = onkeydownExpr;
    532     }
    533 
    534     /**
    535      * Setter method for "onkeypress" tag attribute. (Mapping set in
    536      * associated BeanInfo class.)
    537      */
    538     public void setOnkeypressExpr(String onkeypressExpr) {
    539         this.onkeypressExpr = onkeypressExpr;
    540     }
    541 
    542     /**
    543      * Setter method for "onkeyup" tag attribute. (Mapping set in associated
    544      * BeanInfo class.)
    545      */
    546     public void setOnkeyupExpr(String onkeyupExpr) {
    547         this.onkeyupExpr = onkeyupExpr;
    548     }
    549 
    550     /**
    551      * Setter method for "onmousedown" tag attribute. (Mapping set in
    552      * associated BeanInfo class.)
    553      */
    554     public void setOnmousedownExpr(String onmousedownExpr) {
    555         this.onmousedownExpr = onmousedownExpr;
    556     }
    557 
    558     /**
    559      * Setter method for "onmousemove" tag attribute. (Mapping set in
    560      * associated BeanInfo class.)
    561      */
    562     public void setOnmousemoveExpr(String onmousemoveExpr) {
    563         this.onmousemoveExpr = onmousemoveExpr;
    564     }
    565 
    566     /**
    567      * Setter method for "onmouseout" tag attribute. (Mapping set in
    568      * associated BeanInfo class.)
    569      */
    570     public void setOnmouseoutExpr(String onmouseoutExpr) {
    571         this.onmouseoutExpr = onmouseoutExpr;
    572     }
    573 
    574     /**
    575      * Setter method for "onmouseover" tag attribute. (Mapping set in
    576      * associated BeanInfo class.)
    577      */
    578     public void setOnmouseoverExpr(String onmouseoverExpr) {
    579         this.onmouseoverExpr = onmouseoverExpr;
    580     }
    581 
    582     /**
    583      * Setter method for "onmouseup" tag attribute. (Mapping set in associated
    584      * BeanInfo class.)
    585      */
    586     public void setOnmouseupExpr(String onmouseupExpr) {
    587         this.onmouseupExpr = onmouseupExpr;
    588     }
    589 
    590     /**
    591      * Setter method for "property" tag attribute. (Mapping set in associated
    592      * BeanInfo class.)
    593      */
    594     public void setPropertyExpr(String propertyExpr) {
    595         this.propertyExpr = propertyExpr;
    596     }
    597 
    598     /**
    599      * Setter method for "style" tag attribute. (Mapping set in associated
    600      * BeanInfo class.)
    601      */
    602     public void setStyleExpr(String styleExpr) {
    603         this.styleExpr = styleExpr;
    604     }
    605 
    606     /**
    607      * Setter method for "styleClass" tag attribute. (Mapping set in
    608      * associated BeanInfo class.)
    609      */
    610     public void setStyleClassExpr(String styleClassExpr) {
    611         this.styleClassExpr = styleClassExpr;
    612     }
    613 
    614     /**
    615      * Setter method for "styleId" tag attribute. (Mapping set in associated
    616      * BeanInfo class.)
    617      */
    618     public void setStyleIdExpr(String styleIdExpr) {
    619         this.styleIdExpr = styleIdExpr;
    620     }
    621 
    622     /**
    623      * Setter method for "tabindex" tag attribute. (Mapping set in associated
    624      * BeanInfo class.)
    625      */
    626     public void setTabindexExpr(String tabindexExpr) {
    627         this.tabindexExpr = tabindexExpr;
    628     }
    629 
    630     /**
    631      * Setter method for "title" tag attribute. (Mapping set in associated
    632      * BeanInfo class.)
    633      */
    634     public void setTitleExpr(String titleExpr) {
    635         this.titleExpr = titleExpr;
    636     }
    637 
    638     /**
    639      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    640      * BeanInfo class.)
    641      */
    642     public void setTitleKeyExpr(String titleKeyExpr) {
    643         this.titleKeyExpr = titleKeyExpr;
    644     }
    645 
    646     /**
    647      * Setter method for "value" tag attribute. (Mapping set in associated
    648      * BeanInfo class.)
    649      */
    650     public void setValueExpr(String valueExpr) {
    651         this.valueExpr = valueExpr;
    652     }
    653 
    654     /**
    655      * Resets attribute values for tag reuse.
    656      */
    657     public void release() {
    658         super.release();
    659         setAccesskeyExpr(null);
    660         setAltExpr(null);
    661         setAltKeyExpr(null);
    662         setBundleExpr(null);
    663         setDirExpr(null);
    664         setDisabledExpr(null);
    665         setLangExpr(null);
    666         setOnblurExpr(null);
    667         setOnchangeExpr(null);
    668         setOnclickExpr(null);
    669         setOndblclickExpr(null);
    670         setOnfocusExpr(null);
    671         setOnkeydownExpr(null);
    672         setOnkeypressExpr(null);
    673         setOnkeyupExpr(null);
    674         setOnmousedownExpr(null);
    675         setOnmousemoveExpr(null);
    676         setOnmouseoutExpr(null);
    677         setOnmouseoverExpr(null);
    678         setOnmouseupExpr(null);
    679         setPropertyExpr(null);
    680         setStyleExpr(null);
    681         setStyleClassExpr(null);
    682         setStyleIdExpr(null);
    683         setTabindexExpr(null);
    684         setTitleExpr(null);
    685         setTitleKeyExpr(null);
    686         setValueExpr(null);
    687     }
    688 
    689     /**
    690      * Process the start tag.
    691      *
    692      * @throws JspException if a JSP exception has occurred
    693      */
    694     public int doStartTag() throws JspException {
    695         evaluateExpressions();
    696 
    697         return (super.doStartTag());
    698     }
    699 
    700     /**
    701      * Processes all attribute values which use the JSTL expression evaluation
    702      * engine to determine their values.
    703      *
    704      * @throws JspException if a JSP exception has occurred
    705      */
    706     private void evaluateExpressions()
    707         throws JspException {
    708         String string = null;
    709         Boolean bool = null;
    710 
    711         if ((string =
    712                 EvalHelper.evalString("accessKey", getAccesskeyExpr(), this,
    713                     pageContext)) != null) {
    714             setAccesskey(string);
    715         }
    716 
    717         if ((string =
    718                 EvalHelper.evalString("alt", getAltExpr(), this, pageContext)) != null) {
    719             setAlt(string);
    720         }
    721 
    722         if ((string =
    723                 EvalHelper.evalString("altKey", getAltKeyExpr(), this,
    724                     pageContext)) != null) {
    725             setAltKey(string);
    726         }
    727 
    728         if ((string =
    729                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    730                     pageContext)) != null) {
    731             setBundle(string);
    732         }
    733 
    734         if ((string =
    735                  EvalHelper.evalString("dir", getDirExpr(), this,
    736                          pageContext)) != null) {
    737          setDir(string);
    738         }
    739         
    740         if ((bool =
    741                 EvalHelper.evalBoolean("disabled", getDisabledExpr(), this,
    742                     pageContext)) != null) {
    743             setDisabled(bool.booleanValue());
    744         }
    745 
    746         if ((string =
    747                  EvalHelper.evalString("lang", getLangExpr(), this,
    748                          pageContext)) != null) {
    749          setLang(string);
    750         }
    751 
    752         if ((string =
    753                 EvalHelper.evalString("onblur", getOnblurExpr(), this,
    754                     pageContext)) != null) {
    755             setOnblur(string);
    756         }
    757 
    758         if ((string =
    759                 EvalHelper.evalString("onchange", getOnchangeExpr(), this,
    760                     pageContext)) != null) {
    761             setOnchange(string);
    762         }
    763 
    764         if ((string =
    765                 EvalHelper.evalString("onclick", getOnclickExpr(), this,
    766                     pageContext)) != null) {
    767             setOnclick(string);
    768         }
    769 
    770         if ((string =
    771                 EvalHelper.evalString("ondblclick", getOndblclickExpr(), this,
    772                     pageContext)) != null) {
    773             setOndblclick(string);
    774         }
    775 
    776         if ((string =
    777                 EvalHelper.evalString("onfocus", getOnfocusExpr(), this,
    778                     pageContext)) != null) {
    779             setOnfocus(string);
    780         }
    781 
    782         if ((string =
    783                 EvalHelper.evalString("onkeydown", getOnkeydownExpr(), this,
    784                     pageContext)) != null) {
    785             setOnkeydown(string);
    786         }
    787 
    788         if ((string =
    789                 EvalHelper.evalString("onkeypress", getOnkeypressExpr(), this,
    790                     pageContext)) != null) {
    791             setOnkeypress(string);
    792         }
    793 
    794         if ((string =
    795                 EvalHelper.evalString("onkeyup", getOnkeyupExpr(), this,
    796                     pageContext)) != null) {
    797             setOnkeyup(string);
    798         }
    799 
    800         if ((string =
    801                 EvalHelper.evalString("onmousedown", getOnmousedownExpr(),
    802                     this, pageContext)) != null) {
    803             setOnmousedown(string);
    804         }
    805 
    806         if ((string =
    807                 EvalHelper.evalString("onmousemove", getOnmousemoveExpr(),
    808                     this, pageContext)) != null) {
    809             setOnmousemove(string);
    810         }
    811 
    812         if ((string =
    813                 EvalHelper.evalString("onmouseout", getOnmouseoutExpr(), this,
    814                     pageContext)) != null) {
    815             setOnmouseout(string);
    816         }
    817 
    818         if ((string =
    819                 EvalHelper.evalString("onmouseover", getOnmouseoverExpr(),
    820                     this, pageContext)) != null) {
    821             setOnmouseover(string);
    822         }
    823 
    824         if ((string =
    825                 EvalHelper.evalString("onmouseup", getOnmouseupExpr(), this,
    826                     pageContext)) != null) {
    827             setOnmouseup(string);
    828         }
    829 
    830         if ((string =
    831                 EvalHelper.evalString("property", getPropertyExpr(), this,
    832                     pageContext)) != null) {
    833             setProperty(string);
    834         }
    835 
    836         if ((string =
    837                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    838             setStyle(string);
    839         }
    840 
    841         if ((string =
    842                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    843                     pageContext)) != null) {
    844             setStyleClass(string);
    845         }
    846 
    847         if ((string =
    848                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    849                     pageContext)) != null) {
    850             setStyleId(string);
    851         }
    852 
    853         if ((string =
    854                 EvalHelper.evalString("tabindex", getTabindexExpr(), this,
    855                     pageContext)) != null) {
    856             setTabindex(string);
    857         }
    858 
    859         if ((string =
    860                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    861             setTitle(string);
    862         }
    863 
    864         if ((string =
    865                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    866                     pageContext)) != null) {
    867             setTitleKey(string);
    868         }
    869 
    870         if ((string =
    871                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    872             setValue(string);
    873         }
    874     }
    875 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
