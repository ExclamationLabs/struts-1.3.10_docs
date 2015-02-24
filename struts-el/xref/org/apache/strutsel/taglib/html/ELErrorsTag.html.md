[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELErrorsTag.html)


    1   /*
    2    * $Id: ELErrorsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.ErrorsTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * <p>Custom tag that renders error messages if an appropriate request
    30   * attribute has been created.  The tag looks for a request attribute with a
    31   * reserved key, and assumes that it is either a String, a String array,
    32   * containing message keys to be looked up in the module's MessageResources,
    33   * or an object of type <code>org.apache.struts.action.ActionErrors</code>.
    34   * <p> The following optional message keys will be utilized if corresponding
    35   * messages exist for them in the application resources:</p>
    36   *
    37   * <ul>
    38   *
    39   * <li><b>errors.header</b> - If present, the corresponding message will be
    40   * rendered prior to the individual list of error messages.</li>
    41   *
    42   * <li><b>errors.footer</b> - If present, the corresponding message will be
    43   * rendered following the individual list of error messages.</li>
    44   *
    45   * <li><b>errors.prefix</b> - If present, the corresponding message will be
    46   * rendered before each individual error message.</li>
    47   *
    48   * <li><b>errors.suffix</b> - If present, the corresponding message will be
    49   * rendered after each individual error message.</li>
    50   *
    51   * </ul>
    52   *
    53   * <p> This class is a subclass of the class <code>org.apache.struts.taglib.html.md.ErrorsTag</code>
    54   * which provides most of the described functionality.  This subclass allows
    55   * all attribute values to be specified as expressions utilizing the
    56   * JavaServer Pages Standard Library expression language.
    57   *
    58   * @version $Rev: 471754 $
    59   */
    60  public class ELErrorsTag extends ErrorsTag {
    61      /**
    62       * Instance variable mapped to "bundle" tag attribute. (Mapping set in
    63       * associated BeanInfo class.)
    64       */
    65      private String bundleExpr;
    66  
    67      /**
    68       * Instance variable mapped to "footer" tag attribute. (Mapping set in
    69       * associated BeanInfo class.)
    70       */
    71      private String footerExpr;
    72  
    73      /**
    74       * Instance variable mapped to "header" tag attribute. (Mapping set in
    75       * associated BeanInfo class.)
    76       */
    77      private String headerExpr;
    78  
    79      /**
    80       * Instance variable mapped to "locale" tag attribute. (Mapping set in
    81       * associated BeanInfo class.)
    82       */
    83      private String localeExpr;
    84  
    85      /**
    86       * Instance variable mapped to "name" tag attribute. (Mapping set in
    87       * associated BeanInfo class.)
    88       */
    89      private String nameExpr;
    90  
    91      /**
    92       * Instance variable mapped to "prefix" tag attribute. (Mapping set in
    93       * associated BeanInfo class.)
    94       */
    95      private String prefixExpr;
    96  
    97      /**
    98       * Instance variable mapped to "property" tag attribute. (Mapping set in
    99       * associated BeanInfo class.)
    100      */
    101     private String propertyExpr;
    102 
    103     /**
    104      * Instance variable mapped to "suffix" tag attribute. (Mapping set in
    105      * associated BeanInfo class.)
    106      */
    107     private String suffixExpr;
    108 
    109     /**
    110      * Getter method for "bundle" tag attribute. (Mapping set in associated
    111      * BeanInfo class.)
    112      */
    113     public String getBundleExpr() {
    114         return (bundleExpr);
    115     }
    116 
    117     /**
    118      * Getter method for "footer" tag attribute. (Mapping set in associated
    119      * BeanInfo class.)
    120      */
    121     public String getFooterExpr() {
    122         return (footerExpr);
    123     }
    124 
    125     /**
    126      * Getter method for "header" tag attribute. (Mapping set in associated
    127      * BeanInfo class.)
    128      */
    129     public String getHeaderExpr() {
    130         return (headerExpr);
    131     }
    132 
    133     /**
    134      * Getter method for "locale" tag attribute. (Mapping set in associated
    135      * BeanInfo class.)
    136      */
    137     public String getLocaleExpr() {
    138         return (localeExpr);
    139     }
    140 
    141     /**
    142      * Getter method for "name" tag attribute. (Mapping set in associated
    143      * BeanInfo class.)
    144      */
    145     public String getNameExpr() {
    146         return (nameExpr);
    147     }
    148 
    149     /**
    150      * Getter method for "prefix" tag attribute. (Mapping set in associated
    151      * BeanInfo class.)
    152      */
    153     public String getPrefixExpr() {
    154         return (prefixExpr);
    155     }
    156 
    157     /**
    158      * Getter method for "property" tag attribute. (Mapping set in associated
    159      * BeanInfo class.)
    160      */
    161     public String getPropertyExpr() {
    162         return (propertyExpr);
    163     }
    164 
    165     /**
    166      * Getter method for "suffix" tag attribute. (Mapping set in associated
    167      * BeanInfo class.)
    168      */
    169     public String getSuffixExpr() {
    170         return (suffixExpr);
    171     }
    172 
    173     /**
    174      * Setter method for "bundle" tag attribute. (Mapping set in associated
    175      * BeanInfo class.)
    176      */
    177     public void setBundleExpr(String bundleExpr) {
    178         this.bundleExpr = bundleExpr;
    179     }
    180 
    181     /**
    182      * Setter method for "footer" tag attribute. (Mapping set in associated
    183      * BeanInfo class.)
    184      */
    185     public void setFooterExpr(String footerExpr) {
    186         this.footerExpr = footerExpr;
    187     }
    188 
    189     /**
    190      * Setter method for "header" tag attribute. (Mapping set in associated
    191      * BeanInfo class.)
    192      */
    193     public void setHeaderExpr(String headerExpr) {
    194         this.headerExpr = headerExpr;
    195     }
    196 
    197     /**
    198      * Setter method for "locale" tag attribute. (Mapping set in associated
    199      * BeanInfo class.)
    200      */
    201     public void setLocaleExpr(String localeExpr) {
    202         this.localeExpr = localeExpr;
    203     }
    204 
    205     /**
    206      * Setter method for "name" tag attribute. (Mapping set in associated
    207      * BeanInfo class.)
    208      */
    209     public void setNameExpr(String nameExpr) {
    210         this.nameExpr = nameExpr;
    211     }
    212 
    213     /**
    214      * Setter method for "prefix" tag attribute. (Mapping set in associated
    215      * BeanInfo class.)
    216      */
    217     public void setPrefixExpr(String prefixExpr) {
    218         this.prefixExpr = prefixExpr;
    219     }
    220 
    221     /**
    222      * Setter method for "property" tag attribute. (Mapping set in associated
    223      * BeanInfo class.)
    224      */
    225     public void setPropertyExpr(String propertyExpr) {
    226         this.propertyExpr = propertyExpr;
    227     }
    228 
    229     /**
    230      * Setter method for "suffix" tag attribute. (Mapping set in associated
    231      * BeanInfo class.)
    232      */
    233     public void setSuffixExpr(String suffixExpr) {
    234         this.suffixExpr = suffixExpr;
    235     }
    236 
    237     /**
    238      * Resets attribute values for tag reuse.
    239      */
    240     public void release() {
    241         super.release();
    242         setBundleExpr(null);
    243         setFooterExpr(null);
    244         setHeaderExpr(null);
    245         setLocaleExpr(null);
    246         setNameExpr(null);
    247         setPrefixExpr(null);
    248         setPropertyExpr(null);
    249         setSuffixExpr(null);
    250     }
    251 
    252     /**
    253      * Process the start tag.
    254      *
    255      * @throws JspException if a JSP exception has occurred
    256      */
    257     public int doStartTag() throws JspException {
    258         evaluateExpressions();
    259 
    260         return (super.doStartTag());
    261     }
    262 
    263     /**
    264      * Processes all attribute values which use the JSTL expression evaluation
    265      * engine to determine their values.
    266      *
    267      * @throws JspException if a JSP exception has occurred
    268      */
    269     private void evaluateExpressions()
    270         throws JspException {
    271         String string = null;
    272 
    273         if ((string =
    274                 EvalHelper.evalString("bundle", getBundleExpr(), this,
    275                     pageContext)) != null) {
    276             setBundle(string);
    277         }
    278 
    279         if ((string =
    280                 EvalHelper.evalString("footer", getFooterExpr(), this,
    281                     pageContext)) != null) {
    282             setFooter(string);
    283         }
    284 
    285         if ((string =
    286                 EvalHelper.evalString("header", getHeaderExpr(), this,
    287                     pageContext)) != null) {
    288             setHeader(string);
    289         }
    290 
    291         if ((string =
    292                 EvalHelper.evalString("locale", getLocaleExpr(), this,
    293                     pageContext)) != null) {
    294             setLocale(string);
    295         }
    296 
    297         if ((string =
    298                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    299             setName(string);
    300         }
    301 
    302         if ((string =
    303                 EvalHelper.evalString("prefix", getPrefixExpr(), this,
    304                     pageContext)) != null) {
    305             setPrefix(string);
    306         }
    307 
    308         if ((string =
    309                 EvalHelper.evalString("property", getPropertyExpr(), this,
    310                     pageContext)) != null) {
    311             setProperty(string);
    312         }
    313 
    314         if ((string =
    315                 EvalHelper.evalString("suffix", getSuffixExpr(), this,
    316                     pageContext)) != null) {
    317             setSuffix(string);
    318         }
    319     }
    320 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
