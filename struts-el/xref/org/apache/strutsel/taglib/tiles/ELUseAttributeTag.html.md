[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELUseAttributeTag.html.md)


    1   /*
    2    * $Id: ELUseAttributeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.tiles.taglib.UseAttributeTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag exposing a component attribute to page. <p> This class is a
    30   * subclass of the class <code>org.apache.struts.taglib.tiles.UseAttributeTag</code>
    31   * which provides most of the described functionality.  This subclass allows
    32   * all attribute values to be specified as expressions utilizing the
    33   * JavaServer Pages Standard Library expression language.
    34   *
    35   * @version $Rev: 471754 $
    36   */
    37  public class ELUseAttributeTag extends UseAttributeTag {
    38      /**
    39       * Instance variable mapped to "id" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String idExpr;
    43  
    44      /**
    45       * Instance variable mapped to "classname" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String classnameExpr;
    49  
    50      /**
    51       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String scopeExpr;
    55  
    56      /**
    57       * Instance variable mapped to "name" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String nameExpr;
    61  
    62      /**
    63       * Instance variable mapped to "ignore" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String ignoreExpr;
    67  
    68      /**
    69       * Getter method for "id" tag attribute. (Mapping set in associated
    70       * BeanInfo class.)
    71       */
    72      public String getIdExpr() {
    73          return (idExpr);
    74      }
    75  
    76      /**
    77       * Getter method for "classname" tag attribute. (Mapping set in associated
    78       * BeanInfo class.)
    79       */
    80      public String getClassnameExpr() {
    81          return (classnameExpr);
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
    93       * Getter method for "name" tag attribute. (Mapping set in associated
    94       * BeanInfo class.)
    95       */
    96      public String getNameExpr() {
    97          return (nameExpr);
    98      }
    99  
    100     /**
    101      * Getter method for "ignore" tag attribute. (Mapping set in associated
    102      * BeanInfo class.)
    103      */
    104     public String getIgnoreExpr() {
    105         return (ignoreExpr);
    106     }
    107 
    108     /**
    109      * Setter method for "id" tag attribute. (Mapping set in associated
    110      * BeanInfo class.)
    111      */
    112     public void setIdExpr(String idExpr) {
    113         this.idExpr = idExpr;
    114     }
    115 
    116     /**
    117      * Setter method for "classname" tag attribute. (Mapping set in associated
    118      * BeanInfo class.)
    119      */
    120     public void setClassnameExpr(String classnameExpr) {
    121         this.classnameExpr = classnameExpr;
    122     }
    123 
    124     /**
    125      * Setter method for "scope" tag attribute. (Mapping set in associated
    126      * BeanInfo class.)
    127      */
    128     public void setScopeExpr(String scopeExpr) {
    129         this.scopeExpr = scopeExpr;
    130     }
    131 
    132     /**
    133      * Setter method for "name" tag attribute. (Mapping set in associated
    134      * BeanInfo class.)
    135      */
    136     public void setNameExpr(String nameExpr) {
    137         this.nameExpr = nameExpr;
    138     }
    139 
    140     /**
    141      * Setter method for "ignore" tag attribute. (Mapping set in associated
    142      * BeanInfo class.)
    143      */
    144     public void setIgnoreExpr(String ignoreExpr) {
    145         this.ignoreExpr = ignoreExpr;
    146     }
    147 
    148     /**
    149      * Resets attribute values for tag reuse.
    150      */
    151     public void release() {
    152         super.release();
    153         setIdExpr(null);
    154         setClassnameExpr(null);
    155         setScopeExpr(null);
    156         setNameExpr(null);
    157         setIgnoreExpr(null);
    158     }
    159 
    160     /**
    161      * Process the start tag.
    162      *
    163      * @throws JspException if a JSP exception has occurred
    164      */
    165     public int doStartTag() throws JspException {
    166         evaluateExpressions();
    167 
    168         return (super.doStartTag());
    169     }
    170 
    171     /**
    172      * Processes all attribute values which use the JSTL expression evaluation
    173      * engine to determine their values.
    174      *
    175      * @throws JspException if a JSP exception has occurred
    176      */
    177     private void evaluateExpressions()
    178         throws JspException {
    179         String string = null;
    180         Boolean bool = null;
    181 
    182         if ((string =
    183                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    184             setId(string);
    185         }
    186 
    187         if ((string =
    188                 EvalHelper.evalString("classname", getClassnameExpr(), this,
    189                     pageContext)) != null) {
    190             setClassname(string);
    191         }
    192 
    193         if ((string =
    194                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    195             setScope(string);
    196         }
    197 
    198         if ((string =
    199                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    200             setName(string);
    201         }
    202 
    203         if ((bool =
    204                 EvalHelper.evalBoolean("ignore", getIgnoreExpr(), this,
    205                     pageContext)) != null) {
    206             setIgnore(bool.booleanValue());
    207         }
    208     }
    209 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
