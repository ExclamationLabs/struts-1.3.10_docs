[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELFrameTag.html)


    1   /*
    2    * $Id: ELFrameTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.FrameTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Generate an HTML <code>&lt;frame&gt;</code> tag with similar capabilities
    30   * as those the <code>&lt.html.md:link&gt;</code> tag provides for hyperlink
    31   * elements.  The <code>src</code> element is rendered using the same
    32   * technique that {@link org.apache.struts.taglib.html.md.LinkTag LinkTag} uses
    33   * to render the <code>href</code> attribute of a hyperlink.  Additionally,
    34   * the HTML 4.0 frame tag attributes <code>noresize</code>,
    35   * <code>scrolling</code>, <code>marginheight</code>, <code>marginwidth</code>,
    36   * <code>frameborder</code>, and <code>longdesc</code> are supported.  The
    37   * frame <code>name</code> attribute is rendered based on the
    38   * <code>frameName</code> property. <p> Note that the value of
    39   * <code>longdesc</code> is intended to be a URI, but currently no rewriting
    40   * is supported.  The attribute is set directly from the property value. <p>
    41   * This class is a subclass of the class <code>org.apache.struts.taglib.html.md.FrameTag</code>
    42   * which provides most of the described functionality.  This subclass allows
    43   * all attribute values to be specified as expressions utilizing the
    44   * JavaServer Pages Standard Library expression language.
    45   *
    46   * @version $Rev: 471754 $
    47   */
    48  public class ELFrameTag extends FrameTag {
    49      /**
    50       * Instance variable mapped to "action" tag attribute. (Mapping set in
    51       * associated BeanInfo class.)
    52       */
    53      private String actionExpr;
    54  
    55      /**
    56       * Instance variable mapped to "module" tag attribute. (Mapping set in
    57       * associated BeanInfo class.)
    58       */
    59      private String moduleExpr;
    60  
    61      /**
    62       * Instance variable mapped to "anchor" tag attribute. (Mapping set in
    63       * associated BeanInfo class.)
    64       */
    65      private String anchorExpr;
    66  
    67      /**
    68       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    69       * associated BeanInfo class.)
    70       */
    71      private String bundleExpr;
    72  
    73      /**
    74       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    75       * associated BeanInfo class.)
    76       */
    77      private String forwardExpr;
    78  
    79      /**
    80       * Instance variable mapped to "frameborder" tag attribute. (Mapping set
    81       * in associated BeanInfo class.)
    82       */
    83      private String frameborderExpr;
    84  
    85      /**
    86       * Instance variable mapped to "frameName" tag attribute. (Mapping set in
    87       * associated BeanInfo class.)
    88       */
    89      private String frameNameExpr;
    90  
    91      /**
    92       * Instance variable mapped to "href" tag attribute. (Mapping set in
    93       * associated BeanInfo class.)
    94       */
    95      private String hrefExpr;
    96  
    97      /**
    98       * Instance variable mapped to "longdesc" tag attribute. (Mapping set in
    99       * associated BeanInfo class.)
    100      */
    101     private String longdescExpr;
    102 
    103     /**
    104      * Instance variable mapped to "marginheight" tag attribute. (Mapping set
    105      * in associated BeanInfo class.)
    106      */
    107     private String marginheightExpr;
    108 
    109     /**
    110      * Instance variable mapped to "marginwidth" tag attribute. (Mapping set
    111      * in associated BeanInfo class.)
    112      */
    113     private String marginwidthExpr;
    114 
    115     /**
    116      * Instance variable mapped to "name" tag attribute. (Mapping set in
    117      * associated BeanInfo class.)
    118      */
    119     private String nameExpr;
    120 
    121     /**
    122      * Instance variable mapped to "noresize" tag attribute. (Mapping set in
    123      * associated BeanInfo class.)
    124      */
    125     private String noresizeExpr;
    126 
    127     /**
    128      * Instance variable mapped to "page" tag attribute. (Mapping set in
    129      * associated BeanInfo class.)
    130      */
    131     private String pageExpr;
    132 
    133     /**
    134      * Instance variable mapped to "paramId" tag attribute. (Mapping set in
    135      * associated BeanInfo class.)
    136      */
    137     private String paramIdExpr;
    138 
    139     /**
    140      * Instance variable mapped to "paramName" tag attribute. (Mapping set in
    141      * associated BeanInfo class.)
    142      */
    143     private String paramNameExpr;
    144 
    145     /**
    146      * Instance variable mapped to "paramProperty" tag attribute. (Mapping set
    147      * in associated BeanInfo class.)
    148      */
    149     private String paramPropertyExpr;
    150 
    151     /**
    152      * Instance variable mapped to "paramScope" tag attribute. (Mapping set in
    153      * associated BeanInfo class.)
    154      */
    155     private String paramScopeExpr;
    156 
    157     /**
    158      * Instance variable mapped to "property" tag attribute. (Mapping set in
    159      * associated BeanInfo class.)
    160      */
    161     private String propertyExpr;
    162 
    163     /**
    164      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    165      * associated BeanInfo class.)
    166      */
    167     private String scopeExpr;
    168 
    169     /**
    170      * Instance variable mapped to "scrolling" tag attribute. (Mapping set in
    171      * associated BeanInfo class.)
    172      */
    173     private String scrollingExpr;
    174 
    175     /**
    176      * Instance variable mapped to "style" tag attribute. (Mapping set in
    177      * associated BeanInfo class.)
    178      */
    179     private String styleExpr;
    180 
    181     /**
    182      * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    183      * associated BeanInfo class.)
    184      */
    185     private String styleClassExpr;
    186 
    187     /**
    188      * Instance variable mapped to "styleId" tag attribute. (Mapping set in
    189      * associated BeanInfo class.)
    190      */
    191     private String styleIdExpr;
    192 
    193     /**
    194      * Instance variable mapped to "title" tag attribute. (Mapping set in
    195      * associated BeanInfo class.)
    196      */
    197     private String titleExpr;
    198 
    199     /**
    200      * Instance variable mapped to "titleKey" tag attribute. (Mapping set in
    201      * associated BeanInfo class.)
    202      */
    203     private String titleKeyExpr;
    204 
    205     /**
    206      * Instance variable mapped to "transaction" tag attribute. (Mapping set
    207      * in associated BeanInfo class.)
    208      */
    209     private String transactionExpr;
    210 
    211     /**
    212      * Getter method for "action" tag attribute. (Mapping set in associated
    213      * BeanInfo class.)
    214      */
    215     public String getActionExpr() {
    216         return (actionExpr);
    217     }
    218 
    219     /**
    220      * Getter method for "module" tag attribute. (Mapping set in associated
    221      * BeanInfo class.)
    222      */
    223     public String getModuleExpr() {
    224         return (moduleExpr);
    225     }
    226 
    227     /**
    228      * Getter method for "anchor" tag attribute. (Mapping set in associated
    229      * BeanInfo class.)
    230      */
    231     public String getAnchorExpr() {
    232         return (anchorExpr);
    233     }
    234 
    235     /**
    236      * Getter method for "bundle" tag attribute. (Mapping set in associated
    237      * BeanInfo class.)
    238      */
    239     public String getBundleExpr() {
    240         return (bundleExpr);
    241     }
    242 
    243     /**
    244      * Getter method for "forward" tag attribute. (Mapping set in associated
    245      * BeanInfo class.)
    246      */
    247     public String getForwardExpr() {
    248         return (forwardExpr);
    249     }
    250 
    251     /**
    252      * Getter method for "frameborder" tag attribute. (Mapping set in
    253      * associated BeanInfo class.)
    254      */
    255     public String getFrameborderExpr() {
    256         return (frameborderExpr);
    257     }
    258 
    259     /**
    260      * Getter method for "frameName" tag attribute. (Mapping set in associated
    261      * BeanInfo class.)
    262      */
    263     public String getFrameNameExpr() {
    264         return (frameNameExpr);
    265     }
    266 
    267     /**
    268      * Getter method for "href" tag attribute. (Mapping set in associated
    269      * BeanInfo class.)
    270      */
    271     public String getHrefExpr() {
    272         return (hrefExpr);
    273     }
    274 
    275     /**
    276      * Getter method for "longdesc" tag attribute. (Mapping set in associated
    277      * BeanInfo class.)
    278      */
    279     public String getLongdescExpr() {
    280         return (longdescExpr);
    281     }
    282 
    283     /**
    284      * Getter method for "marginheight" tag attribute. (Mapping set in
    285      * associated BeanInfo class.)
    286      */
    287     public String getMarginheightExpr() {
    288         return (marginheightExpr);
    289     }
    290 
    291     /**
    292      * Getter method for "marginwidth" tag attribute. (Mapping set in
    293      * associated BeanInfo class.)
    294      */
    295     public String getMarginwidthExpr() {
    296         return (marginwidthExpr);
    297     }
    298 
    299     /**
    300      * Getter method for "name" tag attribute. (Mapping set in associated
    301      * BeanInfo class.)
    302      */
    303     public String getNameExpr() {
    304         return (nameExpr);
    305     }
    306 
    307     /**
    308      * Getter method for "noresize" tag attribute. (Mapping set in associated
    309      * BeanInfo class.)
    310      */
    311     public String getNoresizeExpr() {
    312         return (noresizeExpr);
    313     }
    314 
    315     /**
    316      * Getter method for "page" tag attribute. (Mapping set in associated
    317      * BeanInfo class.)
    318      */
    319     public String getPageExpr() {
    320         return (pageExpr);
    321     }
    322 
    323     /**
    324      * Getter method for "paramId" tag attribute. (Mapping set in associated
    325      * BeanInfo class.)
    326      */
    327     public String getParamIdExpr() {
    328         return (paramIdExpr);
    329     }
    330 
    331     /**
    332      * Getter method for "paramName" tag attribute. (Mapping set in associated
    333      * BeanInfo class.)
    334      */
    335     public String getParamNameExpr() {
    336         return (paramNameExpr);
    337     }
    338 
    339     /**
    340      * Getter method for "paramProperty" tag attribute. (Mapping set in
    341      * associated BeanInfo class.)
    342      */
    343     public String getParamPropertyExpr() {
    344         return (paramPropertyExpr);
    345     }
    346 
    347     /**
    348      * Getter method for "paramScope" tag attribute. (Mapping set in
    349      * associated BeanInfo class.)
    350      */
    351     public String getParamScopeExpr() {
    352         return (paramScopeExpr);
    353     }
    354 
    355     /**
    356      * Getter method for "property" tag attribute. (Mapping set in associated
    357      * BeanInfo class.)
    358      */
    359     public String getPropertyExpr() {
    360         return (propertyExpr);
    361     }
    362 
    363     /**
    364      * Getter method for "scope" tag attribute. (Mapping set in associated
    365      * BeanInfo class.)
    366      */
    367     public String getScopeExpr() {
    368         return (scopeExpr);
    369     }
    370 
    371     /**
    372      * Getter method for "scrolling" tag attribute. (Mapping set in associated
    373      * BeanInfo class.)
    374      */
    375     public String getScrollingExpr() {
    376         return (scrollingExpr);
    377     }
    378 
    379     /**
    380      * Getter method for "style" tag attribute. (Mapping set in associated
    381      * BeanInfo class.)
    382      */
    383     public String getStyleExpr() {
    384         return (styleExpr);
    385     }
    386 
    387     /**
    388      * Getter method for "styleClass" tag attribute. (Mapping set in
    389      * associated BeanInfo class.)
    390      */
    391     public String getStyleClassExpr() {
    392         return (styleClassExpr);
    393     }
    394 
    395     /**
    396      * Getter method for "styleId" tag attribute. (Mapping set in associated
    397      * BeanInfo class.)
    398      */
    399     public String getStyleIdExpr() {
    400         return (styleIdExpr);
    401     }
    402 
    403     /**
    404      * Getter method for "title" tag attribute. (Mapping set in associated
    405      * BeanInfo class.)
    406      */
    407     public String getTitleExpr() {
    408         return (titleExpr);
    409     }
    410 
    411     /**
    412      * Getter method for "titleKey" tag attribute. (Mapping set in associated
    413      * BeanInfo class.)
    414      */
    415     public String getTitleKeyExpr() {
    416         return (titleKeyExpr);
    417     }
    418 
    419     /**
    420      * Getter method for "transaction" tag attribute. (Mapping set in
    421      * associated BeanInfo class.)
    422      */
    423     public String getTransactionExpr() {
    424         return (transactionExpr);
    425     }
    426 
    427     /**
    428      * Setter method for "action" tag attribute. (Mapping set in associated
    429      * BeanInfo class.)
    430      */
    431     public void setActionExpr(String actionExpr) {
    432         this.actionExpr = actionExpr;
    433     }
    434 
    435     /**
    436      * Setter method for "module" tag attribute. (Mapping set in associated
    437      * BeanInfo class.)
    438      */
    439     public void setModuleExpr(String moduleExpr) {
    440         this.moduleExpr = moduleExpr;
    441     }
    442 
    443     /**
    444      * Setter method for "anchor" tag attribute. (Mapping set in associated
    445      * BeanInfo class.)
    446      */
    447     public void setAnchorExpr(String anchorExpr) {
    448         this.anchorExpr = anchorExpr;
    449     }
    450 
    451     /**
    452      * Setter method for "bundle" tag attribute. (Mapping set in associated
    453      * BeanInfo class.)
    454      */
    455     public void setBundleExpr(String bundleExpr) {
    456         this.bundleExpr = bundleExpr;
    457     }
    458 
    459     /**
    460      * Setter method for "forward" tag attribute. (Mapping set in associated
    461      * BeanInfo class.)
    462      */
    463     public void setForwardExpr(String forwardExpr) {
    464         this.forwardExpr = forwardExpr;
    465     }
    466 
    467     /**
    468      * Setter method for "frameborder" tag attribute. (Mapping set in
    469      * associated BeanInfo class.)
    470      */
    471     public void setFrameborderExpr(String frameborderExpr) {
    472         this.frameborderExpr = frameborderExpr;
    473     }
    474 
    475     /**
    476      * Setter method for "frameName" tag attribute. (Mapping set in associated
    477      * BeanInfo class.)
    478      */
    479     public void setFrameNameExpr(String frameNameExpr) {
    480         this.frameNameExpr = frameNameExpr;
    481     }
    482 
    483     /**
    484      * Setter method for "href" tag attribute. (Mapping set in associated
    485      * BeanInfo class.)
    486      */
    487     public void setHrefExpr(String hrefExpr) {
    488         this.hrefExpr = hrefExpr;
    489     }
    490 
    491     /**
    492      * Setter method for "longdesc" tag attribute. (Mapping set in associated
    493      * BeanInfo class.)
    494      */
    495     public void setLongdescExpr(String longdescExpr) {
    496         this.longdescExpr = longdescExpr;
    497     }
    498 
    499     /**
    500      * Setter method for "marginheight" tag attribute. (Mapping set in
    501      * associated BeanInfo class.)
    502      */
    503     public void setMarginheightExpr(String marginheightExpr) {
    504         this.marginheightExpr = marginheightExpr;
    505     }
    506 
    507     /**
    508      * Setter method for "marginwidth" tag attribute. (Mapping set in
    509      * associated BeanInfo class.)
    510      */
    511     public void setMarginwidthExpr(String marginwidthExpr) {
    512         this.marginwidthExpr = marginwidthExpr;
    513     }
    514 
    515     /**
    516      * Setter method for "name" tag attribute. (Mapping set in associated
    517      * BeanInfo class.)
    518      */
    519     public void setNameExpr(String nameExpr) {
    520         this.nameExpr = nameExpr;
    521     }
    522 
    523     /**
    524      * Setter method for "noresize" tag attribute. (Mapping set in associated
    525      * BeanInfo class.)
    526      */
    527     public void setNoresizeExpr(String noresizeExpr) {
    528         this.noresizeExpr = noresizeExpr;
    529     }
    530 
    531     /**
    532      * Setter method for "page" tag attribute. (Mapping set in associated
    533      * BeanInfo class.)
    534      */
    535     public void setPageExpr(String pageExpr) {
    536         this.pageExpr = pageExpr;
    537     }
    538 
    539     /**
    540      * Setter method for "paramId" tag attribute. (Mapping set in associated
    541      * BeanInfo class.)
    542      */
    543     public void setParamIdExpr(String paramIdExpr) {
    544         this.paramIdExpr = paramIdExpr;
    545     }
    546 
    547     /**
    548      * Setter method for "paramName" tag attribute. (Mapping set in associated
    549      * BeanInfo class.)
    550      */
    551     public void setParamNameExpr(String paramNameExpr) {
    552         this.paramNameExpr = paramNameExpr;
    553     }
    554 
    555     /**
    556      * Setter method for "paramProperty" tag attribute. (Mapping set in
    557      * associated BeanInfo class.)
    558      */
    559     public void setParamPropertyExpr(String paramPropertyExpr) {
    560         this.paramPropertyExpr = paramPropertyExpr;
    561     }
    562 
    563     /**
    564      * Setter method for "paramScope" tag attribute. (Mapping set in
    565      * associated BeanInfo class.)
    566      */
    567     public void setParamScopeExpr(String paramScopeExpr) {
    568         this.paramScopeExpr = paramScopeExpr;
    569     }
    570 
    571     /**
    572      * Setter method for "property" tag attribute. (Mapping set in associated
    573      * BeanInfo class.)
    574      */
    575     public void setPropertyExpr(String propertyExpr) {
    576         this.propertyExpr = propertyExpr;
    577     }
    578 
    579     /**
    580      * Setter method for "scope" tag attribute. (Mapping set in associated
    581      * BeanInfo class.)
    582      */
    583     public void setScopeExpr(String scopeExpr) {
    584         this.scopeExpr = scopeExpr;
    585     }
    586 
    587     /**
    588      * Setter method for "scrolling" tag attribute. (Mapping set in associated
    589      * BeanInfo class.)
    590      */
    591     public void setScrollingExpr(String scrollingExpr) {
    592         this.scrollingExpr = scrollingExpr;
    593     }
    594 
    595     /**
    596      * Setter method for "style" tag attribute. (Mapping set in associated
    597      * BeanInfo class.)
    598      */
    599     public void setStyleExpr(String styleExpr) {
    600         this.styleExpr = styleExpr;
    601     }
    602 
    603     /**
    604      * Setter method for "styleClass" tag attribute. (Mapping set in
    605      * associated BeanInfo class.)
    606      */
    607     public void setStyleClassExpr(String styleClassExpr) {
    608         this.styleClassExpr = styleClassExpr;
    609     }
    610 
    611     /**
    612      * Setter method for "styleId" tag attribute. (Mapping set in associated
    613      * BeanInfo class.)
    614      */
    615     public void setStyleIdExpr(String styleIdExpr) {
    616         this.styleIdExpr = styleIdExpr;
    617     }
    618 
    619     /**
    620      * Setter method for "title" tag attribute. (Mapping set in associated
    621      * BeanInfo class.)
    622      */
    623     public void setTitleExpr(String titleExpr) {
    624         this.titleExpr = titleExpr;
    625     }
    626 
    627     /**
    628      * Setter method for "titleKey" tag attribute. (Mapping set in associated
    629      * BeanInfo class.)
    630      */
    631     public void setTitleKeyExpr(String titleKeyExpr) {
    632         this.titleKeyExpr = titleKeyExpr;
    633     }
    634 
    635     /**
    636      * Setter method for "transaction" tag attribute. (Mapping set in
    637      * associated BeanInfo class.)
    638      */
    639     public void setTransactionExpr(String transactionExpr) {
    640         this.transactionExpr = transactionExpr;
    641     }
    642 
    643     /**
    644      * Resets attribute values for tag reuse.
    645      */
    646     public void release() {
    647         super.release();
    648         setActionExpr(null);
    649         setModuleExpr(null);
    650         setAnchorExpr(null);
    651         setBundleExpr(null);
    652         setForwardExpr(null);
    653         setFrameborderExpr(null);
    654         setFrameNameExpr(null);
    655         setHrefExpr(null);
    656         setLongdescExpr(null);
    657         setMarginheightExpr(null);
    658         setMarginwidthExpr(null);
    659         setNameExpr(null);
    660         setNoresizeExpr(null);
    661         setPageExpr(null);
    662         setParamIdExpr(null);
    663         setParamNameExpr(null);
    664         setParamPropertyExpr(null);
    665         setParamScopeExpr(null);
    666         setPropertyExpr(null);
    667         setScopeExpr(null);
    668         setScrollingExpr(null);
    669         setStyleExpr(null);
    670         setStyleClassExpr(null);
    671         setStyleIdExpr(null);
    672         setTitleExpr(null);
    673         setTitleKeyExpr(null);
    674         setTransactionExpr(null);
    675     }
    676 
    677     /**
    678      * Process the start tag.
    679      *
    680      * @throws JspException if a JSP exception has occurred
    681      */
    682     public int doStartTag() throws JspException {
    683         evaluateExpressions();
    684 
    685         return (super.doStartTag());
    686     }
    687 
    688     /**
    689      * Processes all attribute values which use the JSTL expression evaluation
    690      * engine to determine their values.
    691      *
    692      * @throws JspException if a JSP exception has occurred
    693      */
    694     private void evaluateExpressions()
    695         throws JspException {
    696         String string = null;
    697         Integer integer = null;
    698         Boolean bool = null;
    699 
    700         if ((string =
    701                 EvalHelper.evalString("action", getActionExpr(), this,
    702                     pageContext)) != null) {
    703             setAction(string);
    704         }
    705 
    706         if ((string =
    707                 EvalHelper.evalString("module", getModuleExpr(), this,
    708                     pageContext)) != null) {
    709             setModule(string);
    710         }
    711 
    712         if ((string =
    713                 EvalHelper.evalString("anchor", getAnchorExpr(), this,
    714                     pageContext)) != null) {
    715             setAnchor(string);
    716         }
    717 
    718         if ((string =
    719                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    720                     pageContext)) != null) {
    721             setBundle(string);
    722         }
    723 
    724         if ((string =
    725                 EvalHelper.evalString("forward", getForwardExpr(), this,
    726                     pageContext)) != null) {
    727             setForward(string);
    728         }
    729 
    730         if ((string =
    731                 EvalHelper.evalString("frameborder", getFrameborderExpr(),
    732                     this, pageContext)) != null) {
    733             setFrameborder(string);
    734         }
    735 
    736         if ((string =
    737                 EvalHelper.evalString("frameName", getFrameNameExpr(), this,
    738                     pageContext)) != null) {
    739             setFrameName(string);
    740         }
    741 
    742         if ((string =
    743                 EvalHelper.evalString("href", getHrefExpr(), this, pageContext)) != null) {
    744             setHref(string);
    745         }
    746 
    747         if ((string =
    748                 EvalHelper.evalString("longdesc", getLongdescExpr(), this,
    749                     pageContext)) != null) {
    750             setLongdesc(string);
    751         }
    752 
    753         if ((integer =
    754                 EvalHelper.evalInteger("marginheight", getMarginheightExpr(),
    755                     this, pageContext)) != null) {
    756             setMarginheight(integer);
    757         }
    758 
    759         if ((integer =
    760                 EvalHelper.evalInteger("marginwidth", getMarginwidthExpr(),
    761                     this, pageContext)) != null) {
    762             setMarginwidth(integer);
    763         }
    764 
    765         if ((string =
    766                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    767             setName(string);
    768         }
    769 
    770         if ((bool =
    771                 EvalHelper.evalBoolean("noresize", getNoresizeExpr(), this,
    772                     pageContext)) != null) {
    773             setNoresize(bool.booleanValue());
    774         }
    775 
    776         if ((string =
    777                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    778             setPage(string);
    779         }
    780 
    781         if ((string =
    782                 EvalHelper.evalString("paramId", getParamIdExpr(), this,
    783                     pageContext)) != null) {
    784             setParamId(string);
    785         }
    786 
    787         if ((string =
    788                 EvalHelper.evalString("paramName", getParamNameExpr(), this,
    789                     pageContext)) != null) {
    790             setParamName(string);
    791         }
    792 
    793         if ((string =
    794                 EvalHelper.evalString("paramProperty", getParamPropertyExpr(),
    795                     this, pageContext)) != null) {
    796             setParamProperty(string);
    797         }
    798 
    799         if ((string =
    800                 EvalHelper.evalString("paramScope", getParamScopeExpr(), this,
    801                     pageContext)) != null) {
    802             setParamScope(string);
    803         }
    804 
    805         if ((string =
    806                 EvalHelper.evalString("property", getPropertyExpr(), this,
    807                     pageContext)) != null) {
    808             setProperty(string);
    809         }
    810 
    811         if ((string =
    812                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    813             setScope(string);
    814         }
    815 
    816         if ((string =
    817                 EvalHelper.evalString("scrolling", getScrollingExpr(), this,
    818                     pageContext)) != null) {
    819             setScrolling(string);
    820         }
    821 
    822         if ((string =
    823                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    824             setStyle(string);
    825         }
    826 
    827         if ((string =
    828                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    829                     pageContext)) != null) {
    830             setStyleClass(string);
    831         }
    832 
    833         if ((string =
    834                 EvalHelper.evalString("styleId", getStyleIdExpr(), this,
    835                     pageContext)) != null) {
    836             setStyleId(string);
    837         }
    838 
    839         if ((string =
    840                 EvalHelper.evalString("title", getTitleExpr(), this, pageContext)) != null) {
    841             setTitle(string);
    842         }
    843 
    844         if ((string =
    845                 EvalHelper.evalString("titleKey", getTitleKeyExpr(), this,
    846                     pageContext)) != null) {
    847             setTitleKey(string);
    848         }
    849 
    850         if ((bool =
    851                 EvalHelper.evalBoolean("transaction", getTransactionExpr(),
    852                     this, pageContext)) != null) {
    853             setTransaction(bool.booleanValue());
    854         }
    855     }
    856 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
