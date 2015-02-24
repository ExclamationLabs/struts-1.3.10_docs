[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELImportAttributeTag.html.md)


    1   /*
    2    * $Id: ELImportAttributeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.tiles.taglib.ImportAttributeTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Import attribute from component to requested scope. Attribute name and
    30   * scope are optional. If not specified, all component attributes are imported
    31   * in page scope. <p> This class is a subclass of the class
    32   * <code>org.apache.struts.taglib.tiles.ImportAttributeTag</code> which
    33   * provides most of the described functionality.  This subclass allows all
    34   * attribute values to be specified as expressions utilizing the JavaServer
    35   * Pages Standard Library expression language.
    36   *
    37   * @version $Rev: 471754 $
    38   */
    39  public class ELImportAttributeTag extends ImportAttributeTag {
    40      /**
    41       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String scopeExpr;
    45  
    46      /**
    47       * Instance variable mapped to "name" tag attribute. (Mapping set in
    48       * associated BeanInfo class.)
    49       */
    50      private String nameExpr;
    51  
    52      /**
    53       * Instance variable mapped to "ignore" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String ignoreExpr;
    57  
    58      /**
    59       * Getter method for "scope" tag attribute. (Mapping set in associated
    60       * BeanInfo class.)
    61       */
    62      public String getScopeExpr() {
    63          return (scopeExpr);
    64      }
    65  
    66      /**
    67       * Getter method for "name" tag attribute. (Mapping set in associated
    68       * BeanInfo class.)
    69       */
    70      public String getNameExpr() {
    71          return (nameExpr);
    72      }
    73  
    74      /**
    75       * Getter method for "ignore" tag attribute. (Mapping set in associated
    76       * BeanInfo class.)
    77       */
    78      public String getIgnoreExpr() {
    79          return (ignoreExpr);
    80      }
    81  
    82      /**
    83       * Setter method for "scope" tag attribute. (Mapping set in associated
    84       * BeanInfo class.)
    85       */
    86      public void setScopeExpr(String scopeExpr) {
    87          this.scopeExpr = scopeExpr;
    88      }
    89  
    90      /**
    91       * Setter method for "name" tag attribute. (Mapping set in associated
    92       * BeanInfo class.)
    93       */
    94      public void setNameExpr(String nameExpr) {
    95          this.nameExpr = nameExpr;
    96      }
    97  
    98      /**
    99       * Setter method for "ignore" tag attribute. (Mapping set in associated
    100      * BeanInfo class.)
    101      */
    102     public void setIgnoreExpr(String ignoreExpr) {
    103         this.ignoreExpr = ignoreExpr;
    104     }
    105 
    106     /**
    107      * Resets attribute values for tag reuse.
    108      */
    109     public void release() {
    110         super.release();
    111         setScopeExpr(null);
    112         setNameExpr(null);
    113         setIgnoreExpr(null);
    114     }
    115 
    116     /**
    117      * Process the start tag.
    118      *
    119      * @throws JspException if a JSP exception has occurred
    120      */
    121     public int doStartTag() throws JspException {
    122         evaluateExpressions();
    123 
    124         return (super.doStartTag());
    125     }
    126 
    127     /**
    128      * Processes all attribute values which use the JSTL expression evaluation
    129      * engine to determine their values.
    130      *
    131      * @throws JspException if a JSP exception has occurred
    132      */
    133     private void evaluateExpressions()
    134         throws JspException {
    135         String string = null;
    136         Boolean bool = null;
    137 
    138         if ((string =
    139                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    140             setScope(string);
    141         }
    142 
    143         if ((string =
    144                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    145             setName(string);
    146         }
    147 
    148         if ((bool =
    149                 EvalHelper.evalBoolean("ignore", getIgnoreExpr(), this,
    150                     pageContext)) != null) {
    151             setIgnore(bool.booleanValue());
    152         }
    153     }
    154 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
