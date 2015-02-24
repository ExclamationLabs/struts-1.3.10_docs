[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELRewriteTag.html)


    1   /*
    2    * $Id: ELRewriteTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.RewriteTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Generate a URL-encoded URI as a string. <p> This class is a subclass of the
    30   * class <code>org.apache.struts.taglib.html.md.RewriteTag</code> which provides
    31   * most of the described functionality.  This subclass allows all attribute
    32   * values to be specified as expressions utilizing the JavaServer Pages
    33   * Standard Library expression language.
    34   *
    35   * @version $Rev: 471754 $
    36   */
    37  public class ELRewriteTag extends RewriteTag {
    38      /**
    39       * Instance variable mapped to "action" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String actionExpr;
    43  
    44      /**
    45       * Instance variable mapped to "module" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String moduleExpr;
    49  
    50      /**
    51       * Instance variable mapped to "anchor" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String anchorExpr;
    55  
    56      /**
    57       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String forwardExpr;
    61  
    62      /**
    63       * Instance variable mapped to "href" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String hrefExpr;
    67  
    68      /**
    69       * Instance variable mapped to "name" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String nameExpr;
    73  
    74      /**
    75       * Instance variable mapped to "page" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String pageExpr;
    79  
    80      /**
    81       * Instance variable mapped to "paramId" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String paramIdExpr;
    85  
    86      /**
    87       * Instance variable mapped to "paramName" tag attribute. (Mapping set in
    88       * associated BeanInfo class.)
    89       */
    90      private String paramNameExpr;
    91  
    92      /**
    93       * Instance variable mapped to "paramProperty" tag attribute. (Mapping set
    94       * in associated BeanInfo class.)
    95       */
    96      private String paramPropertyExpr;
    97  
    98      /**
    99       * Instance variable mapped to "paramScope" tag attribute. (Mapping set in
    100      * associated BeanInfo class.)
    101      */
    102     private String paramScopeExpr;
    103 
    104     /**
    105      * Instance variable mapped to "property" tag attribute. (Mapping set in
    106      * associated BeanInfo class.)
    107      */
    108     private String propertyExpr;
    109 
    110     /**
    111      * Instance variable mapped to "scope" tag attribute. (Mapping set in
    112      * associated BeanInfo class.)
    113      */
    114     private String scopeExpr;
    115 
    116     /**
    117      * Instance variable mapped to "transaction" tag attribute. (Mapping set
    118      * in associated BeanInfo class.)
    119      */
    120     private String transactionExpr;
    121 
    122     /**
    123      * Instance variable mapped to "useLocalEncoding" tag attribute. (Mapping
    124      * set in associated BeanInfo class.)
    125      */
    126     private String useLocalEncodingExpr;
    127 
    128     /**
    129      * Getter method for "action" tag attribute. (Mapping set in associated
    130      * BeanInfo class.)
    131      */
    132     public String getActionExpr() {
    133         return (actionExpr);
    134     }
    135 
    136     /**
    137      * Getter method for "module" tag attribute. (Mapping set in associated
    138      * BeanInfo class.)
    139      */
    140     public String getModuleExpr() {
    141         return (moduleExpr);
    142     }
    143 
    144     /**
    145      * Getter method for "anchor" tag attribute. (Mapping set in associated
    146      * BeanInfo class.)
    147      */
    148     public String getAnchorExpr() {
    149         return (anchorExpr);
    150     }
    151 
    152     /**
    153      * Getter method for "forward" tag attribute. (Mapping set in associated
    154      * BeanInfo class.)
    155      */
    156     public String getForwardExpr() {
    157         return (forwardExpr);
    158     }
    159 
    160     /**
    161      * Getter method for "href" tag attribute. (Mapping set in associated
    162      * BeanInfo class.)
    163      */
    164     public String getHrefExpr() {
    165         return (hrefExpr);
    166     }
    167 
    168     /**
    169      * Getter method for "name" tag attribute. (Mapping set in associated
    170      * BeanInfo class.)
    171      */
    172     public String getNameExpr() {
    173         return (nameExpr);
    174     }
    175 
    176     /**
    177      * Getter method for "page" tag attribute. (Mapping set in associated
    178      * BeanInfo class.)
    179      */
    180     public String getPageExpr() {
    181         return (pageExpr);
    182     }
    183 
    184     /**
    185      * Getter method for "paramId" tag attribute. (Mapping set in associated
    186      * BeanInfo class.)
    187      */
    188     public String getParamIdExpr() {
    189         return (paramIdExpr);
    190     }
    191 
    192     /**
    193      * Getter method for "paramName" tag attribute. (Mapping set in associated
    194      * BeanInfo class.)
    195      */
    196     public String getParamNameExpr() {
    197         return (paramNameExpr);
    198     }
    199 
    200     /**
    201      * Getter method for "paramProperty" tag attribute. (Mapping set in
    202      * associated BeanInfo class.)
    203      */
    204     public String getParamPropertyExpr() {
    205         return (paramPropertyExpr);
    206     }
    207 
    208     /**
    209      * Getter method for "paramScope" tag attribute. (Mapping set in
    210      * associated BeanInfo class.)
    211      */
    212     public String getParamScopeExpr() {
    213         return (paramScopeExpr);
    214     }
    215 
    216     /**
    217      * Getter method for "property" tag attribute. (Mapping set in associated
    218      * BeanInfo class.)
    219      */
    220     public String getPropertyExpr() {
    221         return (propertyExpr);
    222     }
    223 
    224     /**
    225      * Getter method for "scope" tag attribute. (Mapping set in associated
    226      * BeanInfo class.)
    227      */
    228     public String getScopeExpr() {
    229         return (scopeExpr);
    230     }
    231 
    232     /**
    233      * Getter method for "transaction" tag attribute. (Mapping set in
    234      * associated BeanInfo class.)
    235      */
    236     public String getTransactionExpr() {
    237         return (transactionExpr);
    238     }
    239 
    240     /**
    241      * Getter method for "useLocalEncoding" tag attribute. (Mapping set in
    242      * associated BeanInfo class.)
    243      */
    244     public String getUseLocalEncodingExpr() {
    245         return (useLocalEncodingExpr);
    246     }
    247 
    248     /**
    249      * Setter method for "action" tag attribute. (Mapping set in associated
    250      * BeanInfo class.)
    251      */
    252     public void setActionExpr(String actionExpr) {
    253         this.actionExpr = actionExpr;
    254     }
    255 
    256     /**
    257      * Setter method for "module" tag attribute. (Mapping set in associated
    258      * BeanInfo class.)
    259      */
    260     public void setModuleExpr(String moduleExpr) {
    261         this.moduleExpr = moduleExpr;
    262     }
    263 
    264     /**
    265      * Setter method for "anchor" tag attribute. (Mapping set in associated
    266      * BeanInfo class.)
    267      */
    268     public void setAnchorExpr(String anchorExpr) {
    269         this.anchorExpr = anchorExpr;
    270     }
    271 
    272     /**
    273      * Setter method for "forward" tag attribute. (Mapping set in associated
    274      * BeanInfo class.)
    275      */
    276     public void setForwardExpr(String forwardExpr) {
    277         this.forwardExpr = forwardExpr;
    278     }
    279 
    280     /**
    281      * Setter method for "href" tag attribute. (Mapping set in associated
    282      * BeanInfo class.)
    283      */
    284     public void setHrefExpr(String hrefExpr) {
    285         this.hrefExpr = hrefExpr;
    286     }
    287 
    288     /**
    289      * Setter method for "name" tag attribute. (Mapping set in associated
    290      * BeanInfo class.)
    291      */
    292     public void setNameExpr(String nameExpr) {
    293         this.nameExpr = nameExpr;
    294     }
    295 
    296     /**
    297      * Setter method for "page" tag attribute. (Mapping set in associated
    298      * BeanInfo class.)
    299      */
    300     public void setPageExpr(String pageExpr) {
    301         this.pageExpr = pageExpr;
    302     }
    303 
    304     /**
    305      * Setter method for "paramId" tag attribute. (Mapping set in associated
    306      * BeanInfo class.)
    307      */
    308     public void setParamIdExpr(String paramIdExpr) {
    309         this.paramIdExpr = paramIdExpr;
    310     }
    311 
    312     /**
    313      * Setter method for "paramName" tag attribute. (Mapping set in associated
    314      * BeanInfo class.)
    315      */
    316     public void setParamNameExpr(String paramNameExpr) {
    317         this.paramNameExpr = paramNameExpr;
    318     }
    319 
    320     /**
    321      * Setter method for "paramProperty" tag attribute. (Mapping set in
    322      * associated BeanInfo class.)
    323      */
    324     public void setParamPropertyExpr(String paramPropertyExpr) {
    325         this.paramPropertyExpr = paramPropertyExpr;
    326     }
    327 
    328     /**
    329      * Setter method for "paramScope" tag attribute. (Mapping set in
    330      * associated BeanInfo class.)
    331      */
    332     public void setParamScopeExpr(String paramScopeExpr) {
    333         this.paramScopeExpr = paramScopeExpr;
    334     }
    335 
    336     /**
    337      * Setter method for "property" tag attribute. (Mapping set in associated
    338      * BeanInfo class.)
    339      */
    340     public void setPropertyExpr(String propertyExpr) {
    341         this.propertyExpr = propertyExpr;
    342     }
    343 
    344     /**
    345      * Setter method for "scope" tag attribute. (Mapping set in associated
    346      * BeanInfo class.)
    347      */
    348     public void setScopeExpr(String scopeExpr) {
    349         this.scopeExpr = scopeExpr;
    350     }
    351 
    352     /**
    353      * Setter method for "transaction" tag attribute. (Mapping set in
    354      * associated BeanInfo class.)
    355      */
    356     public void setTransactionExpr(String transactionExpr) {
    357         this.transactionExpr = transactionExpr;
    358     }
    359 
    360     /**
    361      * Setter method for "useLocalEncoding" tag attribute. (Mapping set in
    362      * associated BeanInfo class.)
    363      */
    364     public void setUseLocalEncodingExpr(String useLocalEncodingExpr) {
    365         this.useLocalEncodingExpr = useLocalEncodingExpr;
    366     }
    367 
    368     /**
    369      * Resets attribute values for tag reuse.
    370      */
    371     public void release() {
    372         super.release();
    373         setActionExpr(null);
    374         setModuleExpr(null);
    375         setAnchorExpr(null);
    376         setForwardExpr(null);
    377         setHrefExpr(null);
    378         setNameExpr(null);
    379         setPageExpr(null);
    380         setParamIdExpr(null);
    381         setParamNameExpr(null);
    382         setParamPropertyExpr(null);
    383         setParamScopeExpr(null);
    384         setPropertyExpr(null);
    385         setScopeExpr(null);
    386         setTransactionExpr(null);
    387         setUseLocalEncodingExpr(null);
    388     }
    389 
    390     /**
    391      * Process the start tag.
    392      *
    393      * @throws JspException if a JSP exception has occurred
    394      */
    395     public int doStartTag() throws JspException {
    396         evaluateExpressions();
    397 
    398         return (super.doStartTag());
    399     }
    400 
    401     /**
    402      * Processes all attribute values which use the JSTL expression evaluation
    403      * engine to determine their values.
    404      *
    405      * @throws JspException if a JSP exception has occurred
    406      */
    407     private void evaluateExpressions()
    408         throws JspException {
    409         String string = null;
    410         Boolean bool = null;
    411 
    412         if ((string =
    413                 EvalHelper.evalString("action", getActionExpr(), this,
    414                     pageContext)) != null) {
    415             setAction(string);
    416         }
    417 
    418         if ((string =
    419                 EvalHelper.evalString("module", getModuleExpr(), this,
    420                     pageContext)) != null) {
    421             setModule(string);
    422         }
    423 
    424         if ((string =
    425                 EvalHelper.evalString("anchor", getAnchorExpr(), this,
    426                     pageContext)) != null) {
    427             setAnchor(string);
    428         }
    429 
    430         if ((string =
    431                 EvalHelper.evalString("forward", getForwardExpr(), this,
    432                     pageContext)) != null) {
    433             setForward(string);
    434         }
    435 
    436         if ((string =
    437                 EvalHelper.evalString("href", getHrefExpr(), this, pageContext)) != null) {
    438             setHref(string);
    439         }
    440 
    441         if ((string =
    442                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    443             setName(string);
    444         }
    445 
    446         if ((string =
    447                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    448             setPage(string);
    449         }
    450 
    451         if ((string =
    452                 EvalHelper.evalString("paramId", getParamIdExpr(), this,
    453                     pageContext)) != null) {
    454             setParamId(string);
    455         }
    456 
    457         if ((string =
    458                 EvalHelper.evalString("paramName", getParamNameExpr(), this,
    459                     pageContext)) != null) {
    460             setParamName(string);
    461         }
    462 
    463         if ((string =
    464                 EvalHelper.evalString("paramProperty", getParamPropertyExpr(),
    465                     this, pageContext)) != null) {
    466             setParamProperty(string);
    467         }
    468 
    469         if ((string =
    470                 EvalHelper.evalString("paramScope", getParamScopeExpr(), this,
    471                     pageContext)) != null) {
    472             setParamScope(string);
    473         }
    474 
    475         if ((string =
    476                 EvalHelper.evalString("property", getPropertyExpr(), this,
    477                     pageContext)) != null) {
    478             setProperty(string);
    479         }
    480 
    481         if ((string =
    482                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    483             setScope(string);
    484         }
    485 
    486         if ((bool =
    487                 EvalHelper.evalBoolean("transaction", getTransactionExpr(),
    488                     this, pageContext)) != null) {
    489             setTransaction(bool.booleanValue());
    490         }
    491 
    492         if ((bool =
    493                 EvalHelper.evalBoolean("useLocalEncoding",
    494                     getUseLocalEncodingExpr(), this, pageContext)) != null) {
    495             setUseLocalEncoding(bool.booleanValue());
    496         }
    497     }
    498 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
