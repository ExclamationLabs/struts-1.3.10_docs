[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELHtmlTag.html)


    1   /*
    2    * $Id: ELHtmlTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.HtmlTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Renders an HTML .html.md> element with appropriate language attributes if
    30   * there is a current Locale available in the user's session. <p> This class
    31   * is a subclass of the class <code>org.apache.struts.taglib.html.md.HtmlTag</code>
    32   * which provides most of the described functionality.  This subclass allows
    33   * all attribute values to be specified as expressions utilizing the
    34   * JavaServer Pages Standard Library expression language.
    35   *
    36   * @version $Rev: 471754 $
    37   */
    38  public class ELHtmlTag extends HtmlTag {
    39      /**
    40       * Instance variable mapped to "lang" tag attribute. (Mapping set in
    41       * associated BeanInfo class.)
    42       */
    43      private String langExpr;
    44  
    45      /**
    46       * Instance variable mapped to ".html.md" tag attribute. (Mapping set in
    47       * associated BeanInfo class.)
    48       */
    49      private String .html.mdExpr;
    50  
    51      /**
    52       * Getter method for "lang" tag attribute. (Mapping set in associated
    53       * BeanInfo class.)
    54       */
    55      public String getLangExpr() {
    56          return (langExpr);
    57      }
    58  
    59      /**
    60       * Getter method for ".html.md" tag attribute. (Mapping set in associated
    61       * BeanInfo class.)
    62       */
    63      public String get.html.mdExpr() {
    64          return (.html.mdExpr);
    65      }
    66  
    67      /**
    68       * Setter method for "lang" tag attribute. (Mapping set in associated
    69       * BeanInfo class.)
    70       */
    71      public void setLangExpr(String langExpr) {
    72          this.langExpr = langExpr;
    73      }
    74  
    75      /**
    76       * Setter method for ".html.md" tag attribute. (Mapping set in associated
    77       * BeanInfo class.)
    78       */
    79      public void set.html.mdExpr(String xhtmlExpr) {
    80          this..html.mdExpr = xhtmlExpr;
    81      }
    82  
    83      /**
    84       * Resets attribute values for tag reuse.
    85       */
    86      public void release() {
    87          super.release();
    88          setLangExpr(null);
    89          set.html.mdExpr(null);
    90      }
    91  
    92      /**
    93       * Process the start tag.
    94       *
    95       * @throws JspException if a JSP exception has occurred
    96       */
    97      public int doStartTag() throws JspException {
    98          evaluateExpressions();
    99  
    100         return (super.doStartTag());
    101     }
    102 
    103     /**
    104      * Processes all attribute values which use the JSTL expression evaluation
    105      * engine to determine their values.
    106      *
    107      * @throws JspException if a JSP exception has occurred
    108      */
    109     private void evaluateExpressions()
    110         throws JspException {
    111         Boolean bool = null;
    112         String string = null;
    113 
    114         if ((bool =
    115                 EvalHelper.evalBoolean("lang", getLangExpr(), this, pageContext)) != null) {
    116             setLang(bool.booleanValue());
    117         }
    118 
    119         if ((bool =
    120                 EvalHelper.evalBoolean(".html.md", getXhtmlExpr(), this,
    121                     pageContext)) != null) {
    122             set.html.md(bool.booleanValue());
    123         }
    124     }
    125 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
