[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELDefinitionTag.html.md)


    1   /*
    2    * $Id: ELDefinitionTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.tiles;
    22  
    23  import org.apache.struts.tiles.taglib.DefinitionTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * This is the tag handler for &lt;tiles:definition&gt;, which defines a tiles
    30   * (or template / component). Definition is put in requested context and can
    31   * be used in &lt;tiles:insert&gt. <p> This class is a subclass of the class
    32   * <code>org.apache.struts.taglib.tiles.DefinitionTag</code> which provides
    33   * most of the described functionality.  This subclass allows all attribute
    34   * values to be specified as expressions utilizing the JavaServer Pages
    35   * Standard Library expression language.
    36   *
    37   * @version $Rev: 471754 $
    38   */
    39  public class ELDefinitionTag extends DefinitionTag {
    40      /**
    41       * Instance variable mapped to "id" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String idExpr;
    45  
    46      /**
    47       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    48       * associated BeanInfo class.)
    49       */
    50      private String scopeExpr;
    51  
    52      /**
    53       * Instance variable mapped to "template" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String templateExpr;
    57  
    58      /**
    59       * Instance variable mapped to "page" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String pageExpr;
    63  
    64      /**
    65       * Instance variable mapped to "role" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String roleExpr;
    69  
    70      /**
    71       * Instance variable mapped to "extends" tag attribute. (Mapping set in
    72       * associated BeanInfo class.)
    73       */
    74      private String extendsExpr;
    75  
    76      /**
    77       * Getter method for "id" tag attribute. (Mapping set in associated
    78       * BeanInfo class.)
    79       */
    80      public String getIdExpr() {
    81          return (idExpr);
    82      }
    83  
    84      /**
    85       * Getter method for "scope" tag attribute. (Mapping set in associated
    86       * BeanInfo class.)
    87       */
    88      public String getScopeExpr() {
    89          return (scopeExpr);
    90      }
    91  
    92      /**
    93       * Getter method for "template" tag attribute. (Mapping set in associated
    94       * BeanInfo class.)
    95       */
    96      public String getTemplateExpr() {
    97          return (templateExpr);
    98      }
    99  
    100     /**
    101      * Getter method for "page" tag attribute. (Mapping set in associated
    102      * BeanInfo class.)
    103      */
    104     public String getPageExpr() {
    105         return (pageExpr);
    106     }
    107 
    108     /**
    109      * Getter method for "role" tag attribute. (Mapping set in associated
    110      * BeanInfo class.)
    111      */
    112     public String getRoleExpr() {
    113         return (roleExpr);
    114     }
    115 
    116     /**
    117      * Getter method for "extends" tag attribute. (Mapping set in associated
    118      * BeanInfo class.)
    119      */
    120     public String getExtendsExpr() {
    121         return (extendsExpr);
    122     }
    123 
    124     /**
    125      * Setter method for "id" tag attribute. (Mapping set in associated
    126      * BeanInfo class.)
    127      */
    128     public void setIdExpr(String idExpr) {
    129         this.idExpr = idExpr;
    130     }
    131 
    132     /**
    133      * Setter method for "scope" tag attribute. (Mapping set in associated
    134      * BeanInfo class.)
    135      */
    136     public void setScopeExpr(String scopeExpr) {
    137         this.scopeExpr = scopeExpr;
    138     }
    139 
    140     /**
    141      * Setter method for "template" tag attribute. (Mapping set in associated
    142      * BeanInfo class.)
    143      */
    144     public void setTemplateExpr(String templateExpr) {
    145         this.templateExpr = templateExpr;
    146     }
    147 
    148     /**
    149      * Setter method for "page" tag attribute. (Mapping set in associated
    150      * BeanInfo class.)
    151      */
    152     public void setPageExpr(String pageExpr) {
    153         this.pageExpr = pageExpr;
    154     }
    155 
    156     /**
    157      * Setter method for "role" tag attribute. (Mapping set in associated
    158      * BeanInfo class.)
    159      */
    160     public void setRoleExpr(String roleExpr) {
    161         this.roleExpr = roleExpr;
    162     }
    163 
    164     /**
    165      * Setter method for "extends" tag attribute. (Mapping set in associated
    166      * BeanInfo class.)
    167      */
    168     public void setExtendsExpr(String extendsExpr) {
    169         this.extendsExpr = extendsExpr;
    170     }
    171 
    172     /**
    173      * Resets attribute values for tag reuse.
    174      */
    175     public void release() {
    176         super.release();
    177         setIdExpr(null);
    178         setScopeExpr(null);
    179         setTemplateExpr(null);
    180         setPageExpr(null);
    181         setRoleExpr(null);
    182         setExtendsExpr(null);
    183     }
    184 
    185     /**
    186      * Process the start tag.
    187      *
    188      * @throws JspException if a JSP exception has occurred
    189      */
    190     public int doStartTag() throws JspException {
    191         evaluateExpressions();
    192 
    193         return (super.doStartTag());
    194     }
    195 
    196     /**
    197      * Processes all attribute values which use the JSTL expression evaluation
    198      * engine to determine their values.
    199      *
    200      * @throws JspException if a JSP exception has occurred
    201      */
    202     private void evaluateExpressions()
    203         throws JspException {
    204         String string = null;
    205 
    206         if ((string =
    207                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    208             setId(string);
    209         }
    210 
    211         if ((string =
    212                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    213             setScope(string);
    214         }
    215 
    216         if ((string =
    217                 EvalHelper.evalString("template", getTemplateExpr(), this,
    218                     pageContext)) != null) {
    219             setTemplate(string);
    220         }
    221 
    222         if ((string =
    223                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    224             setPage(string);
    225         }
    226 
    227         if ((string =
    228                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    229             setRole(string);
    230         }
    231 
    232         if ((string =
    233                 EvalHelper.evalString("extends", getExtendsExpr(), this,
    234                     pageContext)) != null) {
    235             setExtends(string);
    236         }
    237     }
    238 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
