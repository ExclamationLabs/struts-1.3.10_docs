[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELGetAttributeTag.html.md)


    1   /*
    2    * $Id: ELGetAttributeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.tiles.taglib.GetAttributeTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * This is the tag handler for &lt;tiles-el:get&gt;, which gets content from
    30   * the request scope and either includes the content or prints it, depending
    31   * upon the value of the content's <code>direct</code> attribute. <p> This tag
    32   * is intended to be compatible with the same tag from Templates (David
    33   * Geary).  Implementation extends InsertTag for facility (no so well). The
    34   * only difference is the default value of attribute 'ignore', which is
    35   * <code>true</code> for this tag (default behavior of David Geary's
    36   * templates). <p> This class is a subclass of the class
    37   * <code>org.apache.struts.taglib.tiles.GetAttributeTag</code> which provides
    38   * most of the described functionality.  This subclass allows all attribute
    39   * values to be specified as expressions utilizing the JavaServer Pages
    40   * Standard Library expression language.
    41   *
    42   * @version $Rev: 471754 $
    43   */
    44  public class ELGetAttributeTag extends GetAttributeTag {
    45      /**
    46       * Instance variable mapped to "name" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String nameExpr;
    50  
    51      /**
    52       * Instance variable mapped to "ignore" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String ignoreExpr;
    56  
    57      /**
    58       * Instance variable mapped to "role" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String roleExpr;
    62  
    63      /**
    64       * Getter method for "name" tag attribute. (Mapping set in associated
    65       * BeanInfo class.)
    66       */
    67      public String getNameExpr() {
    68          return (nameExpr);
    69      }
    70  
    71      /**
    72       * Getter method for "ignore" tag attribute. (Mapping set in associated
    73       * BeanInfo class.)
    74       */
    75      public String getIgnoreExpr() {
    76          return (ignoreExpr);
    77      }
    78  
    79      /**
    80       * Getter method for "role" tag attribute. (Mapping set in associated
    81       * BeanInfo class.)
    82       */
    83      public String getRoleExpr() {
    84          return (roleExpr);
    85      }
    86  
    87      /**
    88       * Setter method for "name" tag attribute. (Mapping set in associated
    89       * BeanInfo class.)
    90       */
    91      public void setNameExpr(String nameExpr) {
    92          this.nameExpr = nameExpr;
    93      }
    94  
    95      /**
    96       * Setter method for "ignore" tag attribute. (Mapping set in associated
    97       * BeanInfo class.)
    98       */
    99      public void setIgnoreExpr(String ignoreExpr) {
    100         this.ignoreExpr = ignoreExpr;
    101     }
    102 
    103     /**
    104      * Setter method for "role" tag attribute. (Mapping set in associated
    105      * BeanInfo class.)
    106      */
    107     public void setRoleExpr(String roleExpr) {
    108         this.roleExpr = roleExpr;
    109     }
    110 
    111     /**
    112      * Resets attribute values for tag reuse.
    113      */
    114     public void release() {
    115         super.release();
    116         setNameExpr(null);
    117         setIgnoreExpr(null);
    118         setRoleExpr(null);
    119     }
    120 
    121     /**
    122      * Process the start tag.
    123      *
    124      * @throws JspException if a JSP exception has occurred
    125      */
    126     public int doStartTag() throws JspException {
    127         evaluateExpressions();
    128 
    129         return (super.doStartTag());
    130     }
    131 
    132     /**
    133      * Processes all attribute values which use the JSTL expression evaluation
    134      * engine to determine their values.
    135      *
    136      * @throws JspException if a JSP exception has occurred
    137      */
    138     private void evaluateExpressions()
    139         throws JspException {
    140         String string = null;
    141         Boolean bool = null;
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
    153 
    154         if ((string =
    155                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    156             setRole(string);
    157         }
    158     }
    159 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
