[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/bean/ELIncludeTag.html.md)


    1   /*
    2    * $Id: ELIncludeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.bean;
    22  
    23  import org.apache.struts.taglib.bean.IncludeTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Generate a URL-encoded include to the specified URI. <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.bean.IncludeTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 471754 $
    36   */
    37  public class ELIncludeTag extends IncludeTag {
    38      /**
    39       * Instance variable mapped to "anchor" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String anchorExpr;
    43  
    44      /**
    45       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String forwardExpr;
    49  
    50      /**
    51       * Instance variable mapped to "href" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String hrefExpr;
    55  
    56      /**
    57       * Instance variable mapped to "id" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String idExpr;
    61  
    62      /**
    63       * Instance variable mapped to "page" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String pageExpr;
    67  
    68      /**
    69       * Instance variable mapped to "transaction" tag attribute. (Mapping set
    70       * in associated BeanInfo class.)
    71       */
    72      private String transactionExpr;
    73  
    74      /**
    75       * Getter method for "anchor" tag attribute. (Mapping set in associated
    76       * BeanInfo class.)
    77       */
    78      public String getAnchorExpr() {
    79          return (anchorExpr);
    80      }
    81  
    82      /**
    83       * Getter method for "forward" tag attribute. (Mapping set in associated
    84       * BeanInfo class.)
    85       */
    86      public String getForwardExpr() {
    87          return (forwardExpr);
    88      }
    89  
    90      /**
    91       * Getter method for "href" tag attribute. (Mapping set in associated
    92       * BeanInfo class.)
    93       */
    94      public String getHrefExpr() {
    95          return (hrefExpr);
    96      }
    97  
    98      /**
    99       * Getter method for "id" tag attribute. (Mapping set in associated
    100      * BeanInfo class.)
    101      */
    102     public String getIdExpr() {
    103         return (idExpr);
    104     }
    105 
    106     /**
    107      * Getter method for "page" tag attribute. (Mapping set in associated
    108      * BeanInfo class.)
    109      */
    110     public String getPageExpr() {
    111         return (pageExpr);
    112     }
    113 
    114     /**
    115      * Getter method for "transaction" tag attribute. (Mapping set in
    116      * associated BeanInfo class.)
    117      */
    118     public String getTransactionExpr() {
    119         return (transactionExpr);
    120     }
    121 
    122     /**
    123      * Setter method for "anchor" tag attribute. (Mapping set in associated
    124      * BeanInfo class.)
    125      */
    126     public void setAnchorExpr(String anchorExpr) {
    127         this.anchorExpr = anchorExpr;
    128     }
    129 
    130     /**
    131      * Setter method for "forward" tag attribute. (Mapping set in associated
    132      * BeanInfo class.)
    133      */
    134     public void setForwardExpr(String forwardExpr) {
    135         this.forwardExpr = forwardExpr;
    136     }
    137 
    138     /**
    139      * Setter method for "href" tag attribute. (Mapping set in associated
    140      * BeanInfo class.)
    141      */
    142     public void setHrefExpr(String hrefExpr) {
    143         this.hrefExpr = hrefExpr;
    144     }
    145 
    146     /**
    147      * Setter method for "id" tag attribute. (Mapping set in associated
    148      * BeanInfo class.)
    149      */
    150     public void setIdExpr(String idExpr) {
    151         this.idExpr = idExpr;
    152     }
    153 
    154     /**
    155      * Setter method for "page" tag attribute. (Mapping set in associated
    156      * BeanInfo class.)
    157      */
    158     public void setPageExpr(String pageExpr) {
    159         this.pageExpr = pageExpr;
    160     }
    161 
    162     /**
    163      * Setter method for "transaction" tag attribute. (Mapping set in
    164      * associated BeanInfo class.)
    165      */
    166     public void setTransactionExpr(String transactionExpr) {
    167         this.transactionExpr = transactionExpr;
    168     }
    169 
    170     /**
    171      * Resets attribute values for tag reuse.
    172      */
    173     public void release() {
    174         super.release();
    175         setAnchorExpr(null);
    176         setForwardExpr(null);
    177         setHrefExpr(null);
    178         setIdExpr(null);
    179         setPageExpr(null);
    180         setTransactionExpr(null);
    181     }
    182 
    183     /**
    184      * Process the start tag.
    185      *
    186      * @throws JspException if a JSP exception has occurred
    187      */
    188     public int doStartTag() throws JspException {
    189         evaluateExpressions();
    190 
    191         return (super.doStartTag());
    192     }
    193 
    194     /**
    195      * Processes all attribute values which use the JSTL expression evaluation
    196      * engine to determine their values.
    197      *
    198      * @throws JspException if a JSP exception has occurred
    199      */
    200     private void evaluateExpressions()
    201         throws JspException {
    202         String string = null;
    203         Boolean bool = null;
    204 
    205         if ((string =
    206                 EvalHelper.evalString("anchor", getAnchorExpr(), this,
    207                     pageContext)) != null) {
    208             setAnchor(string);
    209         }
    210 
    211         if ((string =
    212                 EvalHelper.evalString("forward", getForwardExpr(), this,
    213                     pageContext)) != null) {
    214             setForward(string);
    215         }
    216 
    217         if ((string =
    218                 EvalHelper.evalString("href", getHrefExpr(), this, pageContext)) != null) {
    219             setHref(string);
    220         }
    221 
    222         if ((string =
    223                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    224             setId(string);
    225         }
    226 
    227         if ((string =
    228                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    229             setPage(string);
    230         }
    231 
    232         if ((bool =
    233                 EvalHelper.evalBoolean("transaction", getTransactionExpr(),
    234                     this, pageContext)) != null) {
    235             setTransaction(bool.booleanValue());
    236         }
    237     }
    238 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
