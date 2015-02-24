[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/bean/ELResourceTag.html.md)


    1   /*
    2    * $Id: ELResourceTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.bean.ResourceTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Define a scripting variable based on the contents of the specified web
    30   * application resource. <p> This class is a subclass of the class
    31   * <code>org.apache.struts.taglib.bean.ResourceTag</code> which provides most
    32   * of the described functionality.  This subclass allows all attribute values
    33   * to be specified as expressions utilizing the JavaServer Pages Standard
    34   * Library expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELResourceTag extends ResourceTag {
    39      /**
    40       * Instance variable mapped to "id" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String idExpr;
    44  
    45      /**
    46       * Instance variable mapped to "input" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String inputExpr;
    50  
    51      /**
    52       * Instance variable mapped to "name" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String nameExpr;
    56  
    57      /**
    58       * Getter method for "id" tag attribute. (Mapping set in associated
    59       * BeanInfo class.)
    60       */
    61      public String getIdExpr() {
    62          return (idExpr);
    63      }
    64  
    65      /**
    66       * Getter method for "input" tag attribute. (Mapping set in associated
    67       * BeanInfo class.)
    68       */
    69      public String getInputExpr() {
    70          return (inputExpr);
    71      }
    72  
    73      /**
    74       * Getter method for "name" tag attribute. (Mapping set in associated
    75       * BeanInfo class.)
    76       */
    77      public String getNameExpr() {
    78          return (nameExpr);
    79      }
    80  
    81      /**
    82       * Setter method for "id" tag attribute. (Mapping set in associated
    83       * BeanInfo class.)
    84       */
    85      public void setIdExpr(String idExpr) {
    86          this.idExpr = idExpr;
    87      }
    88  
    89      /**
    90       * Setter method for "input" tag attribute. (Mapping set in associated
    91       * BeanInfo class.)
    92       */
    93      public void setInputExpr(String inputExpr) {
    94          this.inputExpr = inputExpr;
    95      }
    96  
    97      /**
    98       * Setter method for "name" tag attribute. (Mapping set in associated
    99       * BeanInfo class.)
    100      */
    101     public void setNameExpr(String nameExpr) {
    102         this.nameExpr = nameExpr;
    103     }
    104 
    105     /**
    106      * Resets attribute values for tag reuse.
    107      */
    108     public void release() {
    109         super.release();
    110         setIdExpr(null);
    111         setInputExpr(null);
    112         setNameExpr(null);
    113     }
    114 
    115     /**
    116      * Process the start tag.
    117      *
    118      * @throws JspException if a JSP exception has occurred
    119      */
    120     public int doStartTag() throws JspException {
    121         evaluateExpressions();
    122 
    123         return (super.doStartTag());
    124     }
    125 
    126     /**
    127      * Processes all attribute values which use the JSTL expression evaluation
    128      * engine to determine their values.
    129      *
    130      * @throws JspException if a JSP exception has occurred
    131      */
    132     private void evaluateExpressions()
    133         throws JspException {
    134         String string = null;
    135 
    136         if ((string =
    137                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    138             setId(string);
    139         }
    140 
    141         if ((string =
    142                 EvalHelper.evalString("input", getInputExpr(), this, pageContext)) != null) {
    143             setInput(string);
    144         }
    145 
    146         if ((string =
    147                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    148             setName(string);
    149         }
    150     }
    151 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
