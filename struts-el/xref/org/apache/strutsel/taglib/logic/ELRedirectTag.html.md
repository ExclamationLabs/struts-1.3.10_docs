[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELRedirectTag.html.md)


    1   /*
    2    * $Id: ELRedirectTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.logic;
    22  
    23  import org.apache.struts.taglib.logic.RedirectTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Generate a URL-encoded redirect to the specified URI. <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.logic.RedirectTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 471754 $
    36   */
    37  public class ELRedirectTag extends RedirectTag {
    38      /**
    39       * Instance variable mapped to "action" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String actionExpr;
    43  
    44      /**
    45       * Instance variable mapped to "anchor" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String anchorExpr;
    49  
    50      /**
    51       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String forwardExpr;
    55  
    56      /**
    57       * Instance variable mapped to "href" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String hrefExpr;
    61  
    62      /**
    63       * Instance variable mapped to "name" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String nameExpr;
    67  
    68      /**
    69       * Instance variable mapped to "page" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String pageExpr;
    73  
    74      /**
    75       * Instance variable mapped to "paramId" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String paramIdExpr;
    79  
    80      /**
    81       * Instance variable mapped to "paramName" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String paramNameExpr;
    85  
    86      /**
    87       * Instance variable mapped to "paramProperty" tag attribute. (Mapping set
    88       * in associated BeanInfo class.)
    89       */
    90      private String paramPropertyExpr;
    91  
    92      /**
    93       * Instance variable mapped to "paramScope" tag attribute. (Mapping set in
    94       * associated BeanInfo class.)
    95       */
    96      private String paramScopeExpr;
    97  
    98      /**
    99       * Instance variable mapped to "property" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String propertyExpr;
    103 
    104     /**
    105      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String scopeExpr;
    109 
    110     /**
    111      * Instance variable mapped to "transaction" tag attribute. (Mapping set
    112      * in associated BeanInfo class.)
    113      */
    114     private String transactionExpr;
    115 
    116     /**
    117      * Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping
    118      * set in associated BeanInfo class.)
    119      */
    120     private String useLocalEncodingExpr;
    121 
    122     /**
    123      * Getter method for "action" tag attribute. (Mapping set in associated
    124      * BeanInfo class.)
    125      */
    126     public String getActionExpr() {
    127         return (actionExpr);
    128     }
    129 
    130     /**
    131      * Getter method for "anchor" tag attribute. (Mapping set in associated
    132      * BeanInfo class.)
    133      */
    134     public String getAnchorExpr() {
    135         return (anchorExpr);
    136     }
    137 
    138     /**
    139      * Getter method for "forward" tag attribute. (Mapping set in associated
    140      * BeanInfo class.)
    141      */
    142     public String getForwardExpr() {
    143         return (forwardExpr);
    144     }
    145 
    146     /**
    147      * Getter method for "href" tag attribute. (Mapping set in associated
    148      * BeanInfo class.)
    149      */
    150     public String getHrefExpr() {
    151         return (hrefExpr);
    152     }
    153 
    154     /**
    155      * Getter method for "name" tag attribute. (Mapping set in associated
    156      * BeanInfo class.)
    157      */
    158     public String getNameExpr() {
    159         return (nameExpr);
    160     }
    161 
    162     /**
    163      * Getter method for "page" tag attribute. (Mapping set in associated
    164      * BeanInfo class.)
    165      */
    166     public String getPageExpr() {
    167         return (pageExpr);
    168     }
    169 
    170     /**
    171      * Getter method for "paramId" tag attribute. (Mapping set in associated
    172      * BeanInfo class.)
    173      */
    174     public String getParamIdExpr() {
    175         return (paramIdExpr);
    176     }
    177 
    178     /**
    179      * Getter method for "paramName" tag attribute. (Mapping set in associated
    180      * BeanInfo class.)
    181      */
    182     public String getParamNameExpr() {
    183         return (paramNameExpr);
    184     }
    185 
    186     /**
    187      * Getter method for "paramProperty" tag attribute. (Mapping set in
    188      * associated BeanInfo class.)
    189      */
    190     public String getParamPropertyExpr() {
    191         return (paramPropertyExpr);
    192     }
    193 
    194     /**
    195      * Getter method for "paramScope" tag attribute. (Mapping set in
    196      * associated BeanInfo class.)
    197      */
    198     public String getParamScopeExpr() {
    199         return (paramScopeExpr);
    200     }
    201 
    202     /**
    203      * Getter method for "property" tag attribute. (Mapping set in associated
    204      * BeanInfo class.)
    205      */
    206     public String getPropertyExpr() {
    207         return (propertyExpr);
    208     }
    209 
    210     /**
    211      * Getter method for "scope" tag attribute. (Mapping set in associated
    212      * BeanInfo class.)
    213      */
    214     public String getScopeExpr() {
    215         return (scopeExpr);
    216     }
    217 
    218     /**
    219      * Getter method for "transaction" tag attribute. (Mapping set in
    220      * associated BeanInfo class.)
    221      */
    222     public String getTransactionExpr() {
    223         return (transactionExpr);
    224     }
    225 
    226     /**
    227      * Getter method for "useLocalEncoding" tag attribute. (Mapping set in
    228      * associated BeanInfo class.)
    229      */
    230     public String getUseLocalEncodingExpr() {
    231         return (useLocalEncodingExpr);
    232     }
    233 
    234     /**
    235      * Setter method for "action" tag attribute. (Mapping set in associated
    236      * BeanInfo class.)
    237      */
    238     public void setActionExpr(String actionExpr) {
    239         this.actionExpr = actionExpr;
    240     }
    241 
    242     /**
    243      * Setter method for "anchor" tag attribute. (Mapping set in associated
    244      * BeanInfo class.)
    245      */
    246     public void setAnchorExpr(String anchorExpr) {
    247         this.anchorExpr = anchorExpr;
    248     }
    249 
    250     /**
    251      * Setter method for "forward" tag attribute. (Mapping set in associated
    252      * BeanInfo class.)
    253      */
    254     public void setForwardExpr(String forwardExpr) {
    255         this.forwardExpr = forwardExpr;
    256     }
    257 
    258     /**
    259      * Setter method for "href" tag attribute. (Mapping set in associated
    260      * BeanInfo class.)
    261      */
    262     public void setHrefExpr(String hrefExpr) {
    263         this.hrefExpr = hrefExpr;
    264     }
    265 
    266     /**
    267      * Setter method for "name" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public void setNameExpr(String nameExpr) {
    271         this.nameExpr = nameExpr;
    272     }
    273 
    274     /**
    275      * Setter method for "page" tag attribute. (Mapping set in associated
    276      * BeanInfo class.)
    277      */
    278     public void setPageExpr(String pageExpr) {
    279         this.pageExpr = pageExpr;
    280     }
    281 
    282     /**
    283      * Setter method for "paramId" tag attribute. (Mapping set in associated
    284      * BeanInfo class.)
    285      */
    286     public void setParamIdExpr(String paramIdExpr) {
    287         this.paramIdExpr = paramIdExpr;
    288     }
    289 
    290     /**
    291      * Setter method for "paramName" tag attribute. (Mapping set in associated
    292      * BeanInfo class.)
    293      */
    294     public void setParamNameExpr(String paramNameExpr) {
    295         this.paramNameExpr = paramNameExpr;
    296     }
    297 
    298     /**
    299      * Setter method for "paramProperty" tag attribute. (Mapping set in
    300      * associated BeanInfo class.)
    301      */
    302     public void setParamPropertyExpr(String paramPropertyExpr) {
    303         this.paramPropertyExpr = paramPropertyExpr;
    304     }
    305 
    306     /**
    307      * Setter method for "paramScope" tag attribute. (Mapping set in
    308      * associated BeanInfo class.)
    309      */
    310     public void setParamScopeExpr(String paramScopeExpr) {
    311         this.paramScopeExpr = paramScopeExpr;
    312     }
    313 
    314     /**
    315      * Setter method for "property" tag attribute. (Mapping set in associated
    316      * BeanInfo class.)
    317      */
    318     public void setPropertyExpr(String propertyExpr) {
    319         this.propertyExpr = propertyExpr;
    320     }
    321 
    322     /**
    323      * Setter method for "scope" tag attribute. (Mapping set in associated
    324      * BeanInfo class.)
    325      */
    326     public void setScopeExpr(String scopeExpr) {
    327         this.scopeExpr = scopeExpr;
    328     }
    329 
    330     /**
    331      * Setter method for "transaction" tag attribute. (Mapping set in
    332      * associated BeanInfo class.)
    333      */
    334     public void setTransactionExpr(String transactionExpr) {
    335         this.transactionExpr = transactionExpr;
    336     }
    337 
    338     /**
    339      * Setter method for "useLocalEncoding" tag attribute. (Mapping set in
    340      * associated BeanInfo class.)
    341      */
    342     public void setUseLocalEncodingExpr(String useLocalEncodingExpr) {
    343         this.useLocalEncodingExpr = useLocalEncodingExpr;
    344     }
    345 
    346     /**
    347      * Resets attribute values for tag reuse.
    348      */
    349     public void release() {
    350         super.release();
    351         setActionExpr(null);
    352         setAnchorExpr(null);
    353         setForwardExpr(null);
    354         setHrefExpr(null);
    355         setNameExpr(null);
    356         setPageExpr(null);
    357         setParamIdExpr(null);
    358         setParamNameExpr(null);
    359         setParamPropertyExpr(null);
    360         setParamScopeExpr(null);
    361         setPropertyExpr(null);
    362         setScopeExpr(null);
    363         setTransactionExpr(null);
    364         setUseLocalEncodingExpr(null);
    365     }
    366 
    367     /**
    368      * Process the start tag.
    369      *
    370      * @throws JspException if a JSP exception has occurred
    371      */
    372     public int doStartTag() throws JspException {
    373         evaluateExpressions();
    374 
    375         return (super.doStartTag());
    376     }
    377 
    378     /**
    379      * Processes all attribute values which use the JSTL expression evaluation
    380      * engine to determine their values.
    381      *
    382      * @throws JspException if a JSP exception has occurred
    383      */
    384     private void evaluateExpressions()
    385         throws JspException {
    386         String string = null;
    387         Boolean bool = null;
    388 
    389         if ((string =
    390                 EvalHelper.evalString("action", getActionExpr(), this,
    391                     pageContext)) != null) {
    392             setAction(string);
    393         }
    394 
    395         if ((string =
    396                 EvalHelper.evalString("anchor", getAnchorExpr(), this,
    397                     pageContext)) != null) {
    398             setAnchor(string);
    399         }
    400 
    401         if ((string =
    402                 EvalHelper.evalString("forward", getForwardExpr(), this,
    403                     pageContext)) != null) {
    404             setForward(string);
    405         }
    406 
    407         if ((string =
    408                 EvalHelper.evalString("href", getHrefExpr(), this, pageContext)) != null) {
    409             setHref(string);
    410         }
    411 
    412         if ((string =
    413                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    414             setName(string);
    415         }
    416 
    417         if ((string =
    418                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    419             setPage(string);
    420         }
    421 
    422         if ((string =
    423                 EvalHelper.evalString("paramId", getParamIdExpr(), this,
    424                     pageContext)) != null) {
    425             setParamId(string);
    426         }
    427 
    428         if ((string =
    429                 EvalHelper.evalString("paramName", getParamNameExpr(), this,
    430                     pageContext)) != null) {
    431             setParamName(string);
    432         }
    433 
    434         if ((string =
    435                 EvalHelper.evalString("paramProperty", getParamPropertyExpr(),
    436                     this, pageContext)) != null) {
    437             setParamProperty(string);
    438         }
    439 
    440         if ((string =
    441                 EvalHelper.evalString("paramScope", getParamScopeExpr(), this,
    442                     pageContext)) != null) {
    443             setParamScope(string);
    444         }
    445 
    446         if ((string =
    447                 EvalHelper.evalString("property", getPropertyExpr(), this,
    448                     pageContext)) != null) {
    449             setProperty(string);
    450         }
    451 
    452         if ((string =
    453                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    454             setScope(string);
    455         }
    456 
    457         if ((bool =
    458                 EvalHelper.evalBoolean("transaction", getTransactionExpr(),
    459                     this, pageContext)) != null) {
    460             setTransaction(bool.booleanValue());
    461         }
    462 
    463         if ((bool =
    464                 EvalHelper.evalBoolean("useLocalEncoding",
    465                     getUseLocalEncodingExpr(), this, pageContext)) != null) {
    466             setUseLocalEncoding(bool.booleanValue());
    467         }
    468     }
    469 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
