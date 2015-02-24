[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/ParameterTag.html.md)


    1   /*
    2    * $Id: ParameterTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.bean;
    22  
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.tagext.TagSupport;
    28  
    29  /**
    30   * Define a scripting variable based on the value(s) of the specified
    31   * parameter received with this request.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   */
    36  public class ParameterTag extends TagSupport {
    37      /**
    38       * The message resources for this package.
    39       */
    40      protected static MessageResources messages =
    41          MessageResources.getMessageResources(
    42              "org.apache.struts.taglib.bean.LocalStrings");
    43  
    44      // ------------------------------------------------------------- Properties
    45  
    46      /**
    47       * The name of the scripting variable that will be exposed as a page scope
    48       * attribute.
    49       */
    50      protected String id = null;
    51  
    52      /**
    53       * Return an array of parameter values if <code>multiple</code> is
    54       * non-null.
    55       */
    56      protected String multiple = null;
    57  
    58      /**
    59       * The name of the parameter whose value is to be exposed.
    60       */
    61      protected String name = null;
    62  
    63      /**
    64       * The default value to return if no parameter of the specified name is
    65       * found.
    66       */
    67      protected String value = null;
    68  
    69      public String getId() {
    70          return (this.id);
    71      }
    72  
    73      public void setId(String id) {
    74          this.id = id;
    75      }
    76  
    77      public String getMultiple() {
    78          return (this.multiple);
    79      }
    80  
    81      public void setMultiple(String multiple) {
    82          this.multiple = multiple;
    83      }
    84  
    85      public String getName() {
    86          return (this.name);
    87      }
    88  
    89      public void setName(String name) {
    90          this.name = name;
    91      }
    92  
    93      public String getValue() {
    94          return (this.value);
    95      }
    96  
    97      public void setValue(String value) {
    98          this.value = value;
    99      }
    100 
    101     // --------------------------------------------------------- Public Methods
    102 
    103     /**
    104      * Retrieve the required property and expose it as a scripting variable.
    105      *
    106      * @throws JspException if a JSP exception has occurred
    107      */
    108     public int doStartTag() throws JspException {
    109         // Deal with a single parameter value
    110         if (multiple == null) {
    111             String value = pageContext.getRequest().getParameter(name);
    112 
    113             if ((value == null) && (this.value != null)) {
    114                 value = this.value;
    115             }
    116 
    117             if (value == null) {
    118                 JspException e =
    119                     new JspException(messages.getMessage("parameter.get", name));
    120 
    121                 TagUtils.getInstance().saveException(pageContext, e);
    122                 throw e;
    123             }
    124 
    125             pageContext.setAttribute(id, value);
    126 
    127             return (SKIP_BODY);
    128         }
    129 
    130         // Deal with multiple parameter values
    131         String[] values = pageContext.getRequest().getParameterValues(name);
    132 
    133         if ((values == null) || (values.length == 0)) {
    134             if (this.value != null) {
    135                 values = new String[] { this.value };
    136             }
    137         }
    138 
    139         if ((values == null) || (values.length == 0)) {
    140             JspException e =
    141                 new JspException(messages.getMessage("parameter.get", name));
    142 
    143             TagUtils.getInstance().saveException(pageContext, e);
    144             throw e;
    145         }
    146 
    147         pageContext.setAttribute(id, values);
    148 
    149         return (SKIP_BODY);
    150     }
    151 
    152     /**
    153      * Release all allocated resources.
    154      */
    155     public void release() {
    156         super.release();
    157         id = null;
    158         multiple = null;
    159         name = null;
    160         value = null;
    161     }
    162 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
