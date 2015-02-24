[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELGetTag.html.md)


    1   /*
    2    * $Id: ELGetTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.tiles.taglib.GetTag;
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
    37   * <code>org.apache.struts.taglib.tiles.GetTag</code> which provides most of
    38   * the described functionality.  This subclass allows all attribute values to
    39   * be specified as expressions utilizing the JavaServer Pages Standard Library
    40   * expression language.
    41   *
    42   * @version $Rev: 471754 $
    43   */
    44  public class ELGetTag extends GetTag {
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
    58       * Instance variable mapped to "flush" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String flushExpr;
    62  
    63      /**
    64       * Instance variable mapped to "role" tag attribute. (Mapping set in
    65       * associated BeanInfo class.)
    66       */
    67      private String roleExpr;
    68  
    69      /**
    70       * Getter method for "name" tag attribute. (Mapping set in associated
    71       * BeanInfo class.)
    72       */
    73      public String getNameExpr() {
    74          return (nameExpr);
    75      }
    76  
    77      /**
    78       * Getter method for "ignore" tag attribute. (Mapping set in associated
    79       * BeanInfo class.)
    80       */
    81      public String getIgnoreExpr() {
    82          return (ignoreExpr);
    83      }
    84  
    85      /**
    86       * Getter method for "flush" tag attribute. (Mapping set in associated
    87       * BeanInfo class.)
    88       */
    89      public String getFlushExpr() {
    90          return (flushExpr);
    91      }
    92  
    93      /**
    94       * Getter method for "role" tag attribute. (Mapping set in associated
    95       * BeanInfo class.)
    96       */
    97      public String getRoleExpr() {
    98          return (roleExpr);
    99      }
    100 
    101     /**
    102      * Setter method for "name" tag attribute. (Mapping set in associated
    103      * BeanInfo class.)
    104      */
    105     public void setNameExpr(String nameExpr) {
    106         this.nameExpr = nameExpr;
    107     }
    108 
    109     /**
    110      * Setter method for "ignore" tag attribute. (Mapping set in associated
    111      * BeanInfo class.)
    112      */
    113     public void setIgnoreExpr(String ignoreExpr) {
    114         this.ignoreExpr = ignoreExpr;
    115     }
    116 
    117     /**
    118      * Setter method for "flush" tag attribute. (Mapping set in associated
    119      * BeanInfo class.)
    120      */
    121     public void setFlushExpr(String flushExpr) {
    122         this.flushExpr = flushExpr;
    123     }
    124 
    125     /**
    126      * Setter method for "role" tag attribute. (Mapping set in associated
    127      * BeanInfo class.)
    128      */
    129     public void setRoleExpr(String roleExpr) {
    130         this.roleExpr = roleExpr;
    131     }
    132 
    133     /**
    134      * Resets attribute values for tag reuse.
    135      */
    136     public void release() {
    137         super.release();
    138         setNameExpr(null);
    139         setIgnoreExpr(null);
    140         setFlushExpr(null);
    141         setRoleExpr(null);
    142     }
    143 
    144     /**
    145      * Process the start tag.
    146      *
    147      * @throws JspException if a JSP exception has occurred
    148      */
    149     public int doStartTag() throws JspException {
    150         evaluateExpressions();
    151 
    152         return (super.doStartTag());
    153     }
    154 
    155     /**
    156      * Processes all attribute values which use the JSTL expression evaluation
    157      * engine to determine their values.
    158      *
    159      * @throws JspException if a JSP exception has occurred
    160      */
    161     private void evaluateExpressions()
    162         throws JspException {
    163         String string = null;
    164         Boolean bool = null;
    165 
    166         if ((string =
    167                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    168             setName(string);
    169         }
    170 
    171         if ((bool =
    172                 EvalHelper.evalBoolean("ignore", getIgnoreExpr(), this,
    173                     pageContext)) != null) {
    174             setIgnore(bool.booleanValue());
    175         }
    176 
    177         if ((string =
    178                 EvalHelper.evalString("flush", getFlushExpr(), this, pageContext)) != null) {
    179             setFlush(string);
    180         }
    181 
    182         if ((string =
    183                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    184             setRole(string);
    185         }
    186     }
    187 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
