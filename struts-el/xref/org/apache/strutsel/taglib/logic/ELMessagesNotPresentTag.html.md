[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELMessagesNotPresentTag.html.md)


    1   /*
    2    * $Id: ELMessagesNotPresentTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.logic;
    22  
    23  import org.apache.struts.taglib.logic.MessagesNotPresentTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Evalute to <code>false</code> if an <code>ActionMessages</code> class or a
    30   * class that can be converted to an <code>ActionMessages</code> class is in
    31   * request scope under the specified key and there is at least one message in
    32   * the class or for the property specified. <p> This class is a subclass of
    33   * the class <code>org.apache.struts.taglib.logic.MessagesNotPresentTag</code>
    34   * which provides most of the described functionality.  This subclass allows
    35   * all attribute values to be specified as expressions utilizing the
    36   * JavaServer Pages Standard Library expression language.
    37   *
    38   * @version $Rev: 471754 $
    39   */
    40  public class ELMessagesNotPresentTag extends MessagesNotPresentTag {
    41      /**
    42       * Instance variable mapped to "name" tag attribute. (Mapping set in
    43       * associated BeanInfo class.)
    44       */
    45      private String nameExpr;
    46  
    47      /**
    48       * Instance variable mapped to "property" tag attribute. (Mapping set in
    49       * associated BeanInfo class.)
    50       */
    51      private String propertyExpr;
    52  
    53      /**
    54       * Instance variable mapped to "message" tag attribute. (Mapping set in
    55       * associated BeanInfo class.)
    56       */
    57      private String messageExpr;
    58  
    59      /**
    60       * Getter method for "name" tag attribute. (Mapping set in associated
    61       * BeanInfo class.)
    62       */
    63      public String getNameExpr() {
    64          return (nameExpr);
    65      }
    66  
    67      /**
    68       * Getter method for "property" tag attribute. (Mapping set in associated
    69       * BeanInfo class.)
    70       */
    71      public String getPropertyExpr() {
    72          return (propertyExpr);
    73      }
    74  
    75      /**
    76       * Getter method for "message" tag attribute. (Mapping set in associated
    77       * BeanInfo class.)
    78       */
    79      public String getMessageExpr() {
    80          return (messageExpr);
    81      }
    82  
    83      /**
    84       * Setter method for "name" tag attribute. (Mapping set in associated
    85       * BeanInfo class.)
    86       */
    87      public void setNameExpr(String nameExpr) {
    88          this.nameExpr = nameExpr;
    89      }
    90  
    91      /**
    92       * Setter method for "property" tag attribute. (Mapping set in associated
    93       * BeanInfo class.)
    94       */
    95      public void setPropertyExpr(String propertyExpr) {
    96          this.propertyExpr = propertyExpr;
    97      }
    98  
    99      /**
    100      * Setter method for "message" tag attribute. (Mapping set in associated
    101      * BeanInfo class.)
    102      */
    103     public void setMessageExpr(String messageExpr) {
    104         this.messageExpr = messageExpr;
    105     }
    106 
    107     /**
    108      * Releases state of custom tag so this instance can be reused.
    109      */
    110     public void release() {
    111         super.release();
    112         setNameExpr(null);
    113         setPropertyExpr(null);
    114         setMessageExpr(null);
    115     }
    116 
    117     /**
    118      * Process the start tag.
    119      *
    120      * @throws JspException if a JSP exception has occurred
    121      */
    122     public int doStartTag() throws JspException {
    123         evaluateExpressions();
    124 
    125         return (super.doStartTag());
    126     }
    127 
    128     /**
    129      * Processes all attribute values which use the JSTL expression evaluation
    130      * engine to determine their values.
    131      *
    132      * @throws JspException if a JSP exception has occurred
    133      */
    134     private void evaluateExpressions()
    135         throws JspException {
    136         String string = null;
    137 
    138         if ((string =
    139                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    140             setName(string);
    141         }
    142 
    143         if ((string =
    144                 EvalHelper.evalString("property", getPropertyExpr(), this,
    145                     pageContext)) != null) {
    146             setProperty(string);
    147         }
    148 
    149         if ((string =
    150                 EvalHelper.evalString("message", getMessageExpr(), this,
    151                     pageContext)) != null) {
    152             setMessage(string);
    153         }
    154     }
    155 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
