[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELMessagesTag.html)


    1   /*
    2    * $Id: ELMessagesTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.MessagesTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that iterates the elements of a message collection. It defaults
    30   * to retrieving the messages from <code>Action.ERROR_KEY</code>, but if the
    31   * message attribute is set to true then the messages will be retrieved from
    32   * <code>Action.MESSAGE_KEY</code>. This is an alternative to the default
    33   * <code>ErrorsTag</code>. <p> This class is a subclass of the class
    34   * <code>org.apache.struts.taglib.html.md.MessagesTag</code> which provides most
    35   * of the described functionality.  This subclass allows all attribute values
    36   * to be specified as expressions utilizing the JavaServer Pages Standard
    37   * Library expression language.
    38   *
    39   * @version $Rev: 471754 $
    40   */
    41  public class ELMessagesTag extends MessagesTag {
    42      /**
    43       * Instance variable mapped to "id" tag attribute. (Mapping set in
    44       * associated BeanInfo class.)
    45       */
    46      private String idExpr;
    47  
    48      /**
    49       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    50       * associated BeanInfo class.)
    51       */
    52      private String bundleExpr;
    53  
    54      /**
    55       * Instance variable mapped to "locale" tag attribute. (Mapping set in
    56       * associated BeanInfo class.)
    57       */
    58      private String localeExpr;
    59  
    60      /**
    61       * Instance variable mapped to "name" tag attribute. (Mapping set in
    62       * associated BeanInfo class.)
    63       */
    64      private String nameExpr;
    65  
    66      /**
    67       * Instance variable mapped to "property" tag attribute. (Mapping set in
    68       * associated BeanInfo class.)
    69       */
    70      private String propertyExpr;
    71  
    72      /**
    73       * Instance variable mapped to "header" tag attribute. (Mapping set in
    74       * associated BeanInfo class.)
    75       */
    76      private String headerExpr;
    77  
    78      /**
    79       * Instance variable mapped to "footer" tag attribute. (Mapping set in
    80       * associated BeanInfo class.)
    81       */
    82      private String footerExpr;
    83  
    84      /**
    85       * Instance variable mapped to "message" tag attribute. (Mapping set in
    86       * associated BeanInfo class.)
    87       */
    88      private String messageExpr;
    89  
    90      /**
    91       * Getter method for "id" tag attribute. (Mapping set in associated
    92       * BeanInfo class.)
    93       */
    94      public String getIdExpr() {
    95          return (idExpr);
    96      }
    97  
    98      /**
    99       * Getter method for "bundle" tag attribute. (Mapping set in associated
    100      * BeanInfo class.)
    101      */
    102     public String getBundleExpr() {
    103         return (bundleExpr);
    104     }
    105 
    106     /**
    107      * Getter method for "locale" tag attribute. (Mapping set in associated
    108      * BeanInfo class.)
    109      */
    110     public String getLocaleExpr() {
    111         return (localeExpr);
    112     }
    113 
    114     /**
    115      * Getter method for "name" tag attribute. (Mapping set in associated
    116      * BeanInfo class.)
    117      */
    118     public String getNameExpr() {
    119         return (nameExpr);
    120     }
    121 
    122     /**
    123      * Getter method for "property" tag attribute. (Mapping set in associated
    124      * BeanInfo class.)
    125      */
    126     public String getPropertyExpr() {
    127         return (propertyExpr);
    128     }
    129 
    130     /**
    131      * Getter method for "header" tag attribute. (Mapping set in associated
    132      * BeanInfo class.)
    133      */
    134     public String getHeaderExpr() {
    135         return (headerExpr);
    136     }
    137 
    138     /**
    139      * Getter method for "footer" tag attribute. (Mapping set in associated
    140      * BeanInfo class.)
    141      */
    142     public String getFooterExpr() {
    143         return (footerExpr);
    144     }
    145 
    146     /**
    147      * Getter method for "message" tag attribute. (Mapping set in associated
    148      * BeanInfo class.)
    149      */
    150     public String getMessageExpr() {
    151         return (messageExpr);
    152     }
    153 
    154     /**
    155      * Setter method for "id" tag attribute. (Mapping set in associated
    156      * BeanInfo class.)
    157      */
    158     public void setIdExpr(String idExpr) {
    159         this.idExpr = idExpr;
    160     }
    161 
    162     /**
    163      * Setter method for "bundle" tag attribute. (Mapping set in associated
    164      * BeanInfo class.)
    165      */
    166     public void setBundleExpr(String bundleExpr) {
    167         this.bundleExpr = bundleExpr;
    168     }
    169 
    170     /**
    171      * Setter method for "locale" tag attribute. (Mapping set in associated
    172      * BeanInfo class.)
    173      */
    174     public void setLocaleExpr(String localeExpr) {
    175         this.localeExpr = localeExpr;
    176     }
    177 
    178     /**
    179      * Setter method for "name" tag attribute. (Mapping set in associated
    180      * BeanInfo class.)
    181      */
    182     public void setNameExpr(String nameExpr) {
    183         this.nameExpr = nameExpr;
    184     }
    185 
    186     /**
    187      * Setter method for "property" tag attribute. (Mapping set in associated
    188      * BeanInfo class.)
    189      */
    190     public void setPropertyExpr(String propertyExpr) {
    191         this.propertyExpr = propertyExpr;
    192     }
    193 
    194     /**
    195      * Setter method for "header" tag attribute. (Mapping set in associated
    196      * BeanInfo class.)
    197      */
    198     public void setHeaderExpr(String headerExpr) {
    199         this.headerExpr = headerExpr;
    200     }
    201 
    202     /**
    203      * Setter method for "footer" tag attribute. (Mapping set in associated
    204      * BeanInfo class.)
    205      */
    206     public void setFooterExpr(String footerExpr) {
    207         this.footerExpr = footerExpr;
    208     }
    209 
    210     /**
    211      * Setter method for "message" tag attribute. (Mapping set in associated
    212      * BeanInfo class.)
    213      */
    214     public void setMessageExpr(String messageExpr) {
    215         this.messageExpr = messageExpr;
    216     }
    217 
    218     /**
    219      * Resets attribute values for tag reuse.
    220      */
    221     public void release() {
    222         super.release();
    223         setIdExpr(null);
    224         setBundleExpr(null);
    225         setLocaleExpr(null);
    226         setNameExpr(null);
    227         setPropertyExpr(null);
    228         setHeaderExpr(null);
    229         setFooterExpr(null);
    230         setMessageExpr(null);
    231     }
    232 
    233     /**
    234      * Process the start tag.
    235      *
    236      * @throws JspException if a JSP exception has occurred
    237      */
    238     public int doStartTag() throws JspException {
    239         evaluateExpressions();
    240 
    241         return (super.doStartTag());
    242     }
    243 
    244     /**
    245      * Processes all attribute values which use the JSTL expression evaluation
    246      * engine to determine their values.
    247      *
    248      * @throws JspException if a JSP exception has occurred
    249      */
    250     private void evaluateExpressions()
    251         throws JspException {
    252         String string = null;
    253 
    254         if ((string =
    255                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    256             setId(string);
    257         }
    258 
    259         if ((string =
    260                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    261                     pageContext)) != null) {
    262             setBundle(string);
    263         }
    264 
    265         if ((string =
    266                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    267                     pageContext)) != null) {
    268             setLocale(string);
    269         }
    270 
    271         if ((string =
    272                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    273             setName(string);
    274         }
    275 
    276         if ((string =
    277                 EvalHelper.evalString("property", getPropertyExpr(), this,
    278                     pageContext)) != null) {
    279             setProperty(string);
    280         }
    281 
    282         if ((string =
    283                 EvalHelper.evalString("header", getHeaderExpr(), this,
    284                     pageContext)) != null) {
    285             setHeader(string);
    286         }
    287 
    288         if ((string =
    289                 EvalHelper.evalString("footer", getFooterExpr(), this,
    290                     pageContext)) != null) {
    291             setFooter(string);
    292         }
    293 
    294         if ((string =
    295                 EvalHelper.evalString("message", getMessageExpr(), this,
    296                     pageContext)) != null) {
    297             setMessage(string);
    298         }
    299     }
    300 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
