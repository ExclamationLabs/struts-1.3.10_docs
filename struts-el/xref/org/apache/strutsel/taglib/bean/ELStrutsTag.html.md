[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/bean/ELStrutsTag.html.md)


    1   /*
    2    * $Id: ELStrutsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.bean.StrutsTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Define a scripting variable that exposes the requested Struts internal
    30   * configuraton object. <p> This class is a subclass of the class
    31   * <code>org.apache.struts.taglib.bean.StrutsTag</code> which provides most of
    32   * the described functionality.  This subclass allows all attribute values to
    33   * be specified as expressions utilizing the JavaServer Pages Standard Library
    34   * expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELStrutsTag extends StrutsTag {
    39      /**
    40       * Instance variable mapped to "id" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String idExpr;
    44  
    45      /**
    46       * Instance variable mapped to "formBean" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String formBeanExpr;
    50  
    51      /**
    52       * Instance variable mapped to "forward" tag attribute. (Mapping set in
    53       * associated BeanInfo class.)
    54       */
    55      private String forwardExpr;
    56  
    57      /**
    58       * Instance variable mapped to "mapping" tag attribute. (Mapping set in
    59       * associated BeanInfo class.)
    60       */
    61      private String mappingExpr;
    62  
    63      /**
    64       * Getter method for "id" tag attribute. (Mapping set in associated
    65       * BeanInfo class.)
    66       */
    67      public String getIdExpr() {
    68          return (idExpr);
    69      }
    70  
    71      /**
    72       * Getter method for "formBean" tag attribute. (Mapping set in associated
    73       * BeanInfo class.)
    74       */
    75      public String getFormBeanExpr() {
    76          return (formBeanExpr);
    77      }
    78  
    79      /**
    80       * Getter method for "forward" tag attribute. (Mapping set in associated
    81       * BeanInfo class.)
    82       */
    83      public String getForwardExpr() {
    84          return (forwardExpr);
    85      }
    86  
    87      /**
    88       * Getter method for "mapping" tag attribute. (Mapping set in associated
    89       * BeanInfo class.)
    90       */
    91      public String getMappingExpr() {
    92          return (mappingExpr);
    93      }
    94  
    95      /**
    96       * Setter method for "id" tag attribute. (Mapping set in associated
    97       * BeanInfo class.)
    98       */
    99      public void setIdExpr(String idExpr) {
    100         this.idExpr = idExpr;
    101     }
    102 
    103     /**
    104      * Setter method for "formBean" tag attribute. (Mapping set in associated
    105      * BeanInfo class.)
    106      */
    107     public void setFormBeanExpr(String formBeanExpr) {
    108         this.formBeanExpr = formBeanExpr;
    109     }
    110 
    111     /**
    112      * Setter method for "forward" tag attribute. (Mapping set in associated
    113      * BeanInfo class.)
    114      */
    115     public void setForwardExpr(String forwardExpr) {
    116         this.forwardExpr = forwardExpr;
    117     }
    118 
    119     /**
    120      * Setter method for "mapping" tag attribute. (Mapping set in associated
    121      * BeanInfo class.)
    122      */
    123     public void setMappingExpr(String mappingExpr) {
    124         this.mappingExpr = mappingExpr;
    125     }
    126 
    127     /**
    128      * Resets attribute values for tag reuse.
    129      */
    130     public void release() {
    131         super.release();
    132         setIdExpr(null);
    133         setFormBeanExpr(null);
    134         setForwardExpr(null);
    135         setMappingExpr(null);
    136     }
    137 
    138     /**
    139      * Process the start tag.
    140      *
    141      * @throws JspException if a JSP exception has occurred
    142      */
    143     public int doStartTag() throws JspException {
    144         evaluateExpressions();
    145 
    146         return (super.doStartTag());
    147     }
    148 
    149     /**
    150      * Processes all attribute values which use the JSTL expression evaluation
    151      * engine to determine their values.
    152      *
    153      * @throws JspException if a JSP exception has occurred
    154      */
    155     private void evaluateExpressions()
    156         throws JspException {
    157         String string = null;
    158 
    159         if ((string =
    160                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    161             setId(string);
    162         }
    163 
    164         if ((string =
    165                 EvalHelper.evalString("formBean", getFormBeanExpr(), this,
    166                     pageContext)) != null) {
    167             setFormBean(string);
    168         }
    169 
    170         if ((string =
    171                 EvalHelper.evalString("forward", getForwardExpr(), this,
    172                     pageContext)) != null) {
    173             setForward(string);
    174         }
    175 
    176         if ((string =
    177                 EvalHelper.evalString("mapping", getMappingExpr(), this,
    178                     pageContext)) != null) {
    179             setMapping(string);
    180         }
    181     }
    182 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
