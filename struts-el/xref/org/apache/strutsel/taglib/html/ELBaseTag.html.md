[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELBaseTag.html)


    1   /*
    2    * $Id: ELBaseTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.BaseTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Renders an HTML <base> element with an href attribute pointing to the
    30   * absolute location of the enclosing JSP page. This tag is only valid when
    31   * nested inside a head tag body. The presence of this tag allows the browser
    32   * to resolve relative URL's to images, CSS stylesheets  and other resources
    33   * in a manner independent of the URL used to call the ActionServlet. <p> This
    34   * class is a subclass of the class <code>org.apache.struts.taglib.html.md.BaseTag</code>
    35   * which provides most of the described functionality.  This subclass allows
    36   * all attribute values to be specified as expressions utilizing the
    37   * JavaServer Pages Standard Library expression language.
    38   *
    39   * @version $Rev: 471754 $
    40   */
    41  public class ELBaseTag extends BaseTag {
    42      /**
    43       * Instance variable mapped to "target" tag attribute. (Mapping set in
    44       * associated BeanInfo class.)
    45       */
    46      private String targetExpr;
    47  
    48      /**
    49       * Instance variable mapped to "server" tag attribute. (Mapping set in
    50       * associated BeanInfo class.)
    51       */
    52      private String serverExpr;
    53  
    54      /**
    55       * Instance variable mapped to "ref" tag attribute. (Mapping set in
    56       * associated BeanInfo class.)
    57       */
    58      private String refExpr;
    59  
    60      /**
    61       * Getter method for "target" tag attribute. (Mapping set in associated
    62       * BeanInfo class.)
    63       */
    64      public String getTargetExpr() {
    65          return (targetExpr);
    66      }
    67  
    68      /**
    69       * Getter method for "server" tag attribute. (Mapping set in associated
    70       * BeanInfo class.)
    71       */
    72      public String getServerExpr() {
    73          return (serverExpr);
    74      }
    75  
    76      /**
    77       * Getter method for "ref" tag attribute. (Mapping set in associated
    78       * BeanInfo class.)
    79       */
    80      public String getRefExpr() {
    81          return (refExpr);
    82      }
    83  
    84      /**
    85       * Setter method for "target" tag attribute. (Mapping set in associated
    86       * BeanInfo class.)
    87       */
    88      public void setTargetExpr(String targetExpr) {
    89          this.targetExpr = targetExpr;
    90      }
    91  
    92      /**
    93       * Setter method for "server" tag attribute. (Mapping set in associated
    94       * BeanInfo class.)
    95       */
    96      public void setServerExpr(String serverExpr) {
    97          this.serverExpr = serverExpr;
    98      }
    99  
    100     /**
    101      * Setter method for "ref" tag attribute. (Mapping set in associated
    102      * BeanInfo class.)
    103      */
    104     public void setRefExpr(String refExpr) {
    105         this.refExpr = refExpr;
    106     }
    107 
    108     /**
    109      * Resets attribute values for tag reuse.
    110      */
    111     public void release() {
    112         super.release();
    113         setTargetExpr(null);
    114         setServerExpr(null);
    115         setRefExpr(null);
    116     }
    117 
    118     /**
    119      * Process the start tag.
    120      *
    121      * @throws JspException if a JSP exception has occurred
    122      */
    123     public int doStartTag() throws JspException {
    124         evaluateExpressions();
    125 
    126         return (super.doStartTag());
    127     }
    128 
    129     /**
    130      * Processes all attribute values which use the JSTL expression evaluation
    131      * engine to determine their values.
    132      *
    133      * @throws JspException if a JSP exception has occurred
    134      */
    135     private void evaluateExpressions()
    136         throws JspException {
    137         String string = null;
    138 
    139         if ((string =
    140                 EvalHelper.evalString("target", getTargetExpr(), this,
    141                     pageContext)) != null) {
    142             setTarget(string);
    143         }
    144 
    145         if ((string =
    146                 EvalHelper.evalString("server", getServerExpr(), this,
    147                     pageContext)) != null) {
    148             setServer(string);
    149         }
    150 
    151         if ((string =
    152                 EvalHelper.evalString("ref", getRefExpr(), this, pageContext)) != null) {
    153             setRef(string);
    154         }
    155     }
    156 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
