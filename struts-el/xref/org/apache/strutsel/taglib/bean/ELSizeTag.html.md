[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/bean/ELSizeTag.html.md)


    1   /*
    2    * $Id: ELSizeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.bean.SizeTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Define a scripting variable that will contain the number of elements found
    30   * in a specified array, Collection, or Map. <p> This class is a subclass of
    31   * the class <code>org.apache.struts.taglib.bean.SizeTag</code> which provides
    32   * most of the described functionality.  This subclass allows all attribute
    33   * values to be specified as expressions utilizing the JavaServer Pages
    34   * Standard Library expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELSizeTag extends SizeTag {
    39      /**
    40       * Instance variable mapped to "collection" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String collectionExpr;
    44  
    45      /**
    46       * Instance variable mapped to "id" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String idExpr;
    50  
    51      /**
    52       * Instance variable mapped to "name" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String nameExpr;
    56  
    57      /**
    58       * Instance variable mapped to "property" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String propertyExpr;
    62  
    63      /**
    64       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String scopeExpr;
    68  
    69      /**
    70       * Getter method for "collection" tag attribute. (Mapping set in
    71       * associated BeanInfo class.)
    72       */
    73      public String getCollectionExpr() {
    74          return (collectionExpr);
    75      }
    76  
    77      /**
    78       * Getter method for "id" tag attribute. (Mapping set in associated
    79       * BeanInfo class.)
    80       */
    81      public String getIdExpr() {
    82          return (idExpr);
    83      }
    84  
    85      /**
    86       * Getter method for "name" tag attribute. (Mapping set in associated
    87       * BeanInfo class.)
    88       */
    89      public String getNameExpr() {
    90          return (nameExpr);
    91      }
    92  
    93      /**
    94       * Getter method for "property" tag attribute. (Mapping set in associated
    95       * BeanInfo class.)
    96       */
    97      public String getPropertyExpr() {
    98          return (propertyExpr);
    99      }
    100 
    101     /**
    102      * Getter method for "scope" tag attribute. (Mapping set in associated
    103      * BeanInfo class.)
    104      */
    105     public String getScopeExpr() {
    106         return (scopeExpr);
    107     }
    108 
    109     /**
    110      * Setter method for "collection" tag attribute. (Mapping set in
    111      * associated BeanInfo class.)
    112      */
    113     public void setCollectionExpr(String collectionExpr) {
    114         this.collectionExpr = collectionExpr;
    115     }
    116 
    117     /**
    118      * Setter method for "id" tag attribute. (Mapping set in associated
    119      * BeanInfo class.)
    120      */
    121     public void setIdExpr(String idExpr) {
    122         this.idExpr = idExpr;
    123     }
    124 
    125     /**
    126      * Setter method for "name" tag attribute. (Mapping set in associated
    127      * BeanInfo class.)
    128      */
    129     public void setNameExpr(String nameExpr) {
    130         this.nameExpr = nameExpr;
    131     }
    132 
    133     /**
    134      * Setter method for "property" tag attribute. (Mapping set in associated
    135      * BeanInfo class.)
    136      */
    137     public void setPropertyExpr(String propertyExpr) {
    138         this.propertyExpr = propertyExpr;
    139     }
    140 
    141     /**
    142      * Setter method for "scope" tag attribute. (Mapping set in associated
    143      * BeanInfo class.)
    144      */
    145     public void setScopeExpr(String scopeExpr) {
    146         this.scopeExpr = scopeExpr;
    147     }
    148 
    149     /**
    150      * Releases state of custom tag so this instance can be reused.
    151      */
    152     public void release() {
    153         super.release();
    154         setCollectionExpr(null);
    155         setIdExpr(null);
    156         setNameExpr(null);
    157         setPropertyExpr(null);
    158         setScopeExpr(null);
    159     }
    160 
    161     /**
    162      * Process the start tag.
    163      *
    164      * @throws JspException if a JSP exception has occurred
    165      */
    166     public int doStartTag() throws JspException {
    167         evaluateExpressions();
    168 
    169         return (super.doStartTag());
    170     }
    171 
    172     /**
    173      * Processes all attribute values which use the JSTL expression evaluation
    174      * engine to determine their values.
    175      *
    176      * @throws JspException if a JSP exception has occurred
    177      */
    178     private void evaluateExpressions()
    179         throws JspException {
    180         String string = null;
    181         Object object = null;
    182 
    183         if ((object =
    184                 EvalHelper.eval("collection", getCollectionExpr(), this,
    185                     pageContext)) != null) {
    186             setCollection(object);
    187         }
    188 
    189         if ((string =
    190                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    191             setId(string);
    192         }
    193 
    194         if ((string =
    195                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    196             setName(string);
    197         }
    198 
    199         if ((string =
    200                 EvalHelper.evalString("property", getPropertyExpr(), this,
    201                     pageContext)) != null) {
    202             setProperty(string);
    203         }
    204 
    205         if ((string =
    206                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    207             setScope(string);
    208         }
    209     }
    210 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
