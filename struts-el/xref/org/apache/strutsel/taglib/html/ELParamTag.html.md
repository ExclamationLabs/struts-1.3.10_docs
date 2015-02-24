[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELParamTag.html)


    1   /*
    2    * $Id: ELParamTag.java 482911 2006-12-06 05:44:33Z pbenedict $
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
    23  import org.apache.struts.taglib.html.md.ParamTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Adds a new request parameter to its parent {@link ELLinkTag}. This subclass
    30   * allows all attribute values to be specified as expressions utilizing the
    31   * JavaServer Pages Standard Library expression language.
    32   * 
    33   * @version $Rev: 482911 $ $Date: 2006-12-05 23:44:33 -0600 (Tue, 05 Dec 2006) $
    34   * @since Struts 1.3.6
    35   */
    36  public class ELParamTag extends ParamTag {
    37  
    38      /**
    39       * Instance variable mapped to "name" tag attribute. (Mapping set in
    40       * associated BeanInfo class.)
    41       */
    42      private String nameExpr;
    43  
    44      /**
    45       * Instance variable mapped to "value" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String valueExpr;
    49  
    50      /**
    51       * Getter method for "name" tag attribute. (Mapping set in associated
    52       * BeanInfo class.)
    53       */
    54      public String getNameExpr() {
    55          return (nameExpr);
    56      }
    57  
    58      /**
    59       * Getter method for "value" tag attribute. (Mapping set in associated
    60       * BeanInfo class.)
    61       */
    62      public String getValueExpr() {
    63          return (valueExpr);
    64      }
    65  
    66      /**
    67       * Setter method for "name" tag attribute. (Mapping set in associated
    68       * BeanInfo class.)
    69       */
    70      public void setNameExpr(String nameExpr) {
    71          this.nameExpr = nameExpr;
    72      }
    73  
    74      /**
    75       * Setter method for "value" tag attribute. (Mapping set in associated
    76       * BeanInfo class.)
    77       */
    78      public void setValueExpr(String valueExpr) {
    79          this.valueExpr = valueExpr;
    80      }
    81  
    82      /**
    83       * Resets attribute values for tag reuse.
    84       */
    85      public void release() {
    86          super.release();
    87          setNameExpr(null);
    88          setValueExpr(null);
    89      }
    90  
    91      /**
    92       * Process the start tag.
    93       * 
    94       * @throws JspException if a JSP exception has occurred
    95       */
    96      public int doStartTag() throws JspException {
    97          evaluateExpressions();
    98  
    99          return (super.doStartTag());
    100     }
    101 
    102     /**
    103      * Processes all attribute values which use the JSTL expression evaluation
    104      * engine to determine their values.
    105      * 
    106      * @throws JspException if a JSP exception has occurred
    107      */
    108     private void evaluateExpressions() throws JspException {
    109         String string = null;
    110 
    111         if ((string = EvalHelper.evalString("name", getNameExpr(), this,
    112                 pageContext)) != null) {
    113             setName(string);
    114         }
    115 
    116         if ((string = EvalHelper.evalString("value", getValueExpr(), this,
    117                 pageContext)) != null) {
    118             setValue(string);
    119         }
    120     }
    121 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)