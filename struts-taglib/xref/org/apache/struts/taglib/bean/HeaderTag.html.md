[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/HeaderTag.html.md)


    1   /*
    2    * $Id: HeaderTag.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  import java.util.ArrayList;
    31  import java.util.Enumeration;
    32  
    33  /**
    34   * Define a scripting variable based on the value(s) of the specified header
    35   * received with this request.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public class HeaderTag extends TagSupport {
    41      /**
    42       * The message resources for this package.
    43       */
    44      protected static MessageResources messages =
    45          MessageResources.getMessageResources(
    46              "org.apache.struts.taglib.bean.LocalStrings");
    47  
    48      // ------------------------------------------------------------- Properties
    49  
    50      /**
    51       * The name of the scripting variable that will be exposed as a page scope
    52       * attribute.
    53       */
    54      protected String id = null;
    55  
    56      /**
    57       * Return an array of header values if <code>multiple</code> is non-null.
    58       */
    59      protected String multiple = null;
    60  
    61      /**
    62       * The name of the header whose value is to be exposed.
    63       */
    64      protected String name = null;
    65  
    66      /**
    67       * The default value to return if no header of the specified name is
    68       * found.
    69       */
    70      protected String value = null;
    71  
    72      public String getId() {
    73          return (this.id);
    74      }
    75  
    76      public void setId(String id) {
    77          this.id = id;
    78      }
    79  
    80      public String getMultiple() {
    81          return (this.multiple);
    82      }
    83  
    84      public void setMultiple(String multiple) {
    85          this.multiple = multiple;
    86      }
    87  
    88      public String getName() {
    89          return (this.name);
    90      }
    91  
    92      public void setName(String name) {
    93          this.name = name;
    94      }
    95  
    96      public String getValue() {
    97          return (this.value);
    98      }
    99  
    100     public void setValue(String value) {
    101         this.value = value;
    102     }
    103 
    104     // --------------------------------------------------------- Public Methods
    105 
    106     /**
    107      * Retrieve the required property and expose it as a scripting variable.
    108      *
    109      * @throws JspException if a JSP exception has occurred
    110      */
    111     public int doStartTag() throws JspException {
    112         if (this.multiple == null) {
    113             this.handleSingleHeader();
    114         } else {
    115             this.handleMultipleHeaders();
    116         }
    117 
    118         return SKIP_BODY;
    119     }
    120 
    121     /**
    122      * Expose an array of header values.
    123      *
    124      * @throws JspException
    125      * @since Struts 1.2
    126      */
    127     protected void handleMultipleHeaders()
    128         throws JspException {
    129         ArrayList values = new ArrayList();
    130         Enumeration items =
    131             ((HttpServletRequest) pageContext.getRequest()).getHeaders(name);
    132 
    133         while (items.hasMoreElements()) {
    134             values.add(items.nextElement());
    135         }
    136 
    137         if (values.isEmpty() && (this.value != null)) {
    138             values.add(this.value);
    139         }
    140 
    141         String[] headers = new String[values.size()];
    142 
    143         if (headers.length == 0) {
    144             JspException e =
    145                 new JspException(messages.getMessage("header.get", name));
    146 
    147             TagUtils.getInstance().saveException(pageContext, e);
    148             throw e;
    149         }
    150 
    151         pageContext.setAttribute(id, values.toArray(headers));
    152     }
    153 
    154     /**
    155      * Expose a single header value.
    156      *
    157      * @throws JspException
    158      * @since Struts 1.2
    159      */
    160     protected void handleSingleHeader()
    161         throws JspException {
    162         String value =
    163             ((HttpServletRequest) pageContext.getRequest()).getHeader(name);
    164 
    165         if ((value == null) && (this.value != null)) {
    166             value = this.value;
    167         }
    168 
    169         if (value == null) {
    170             JspException e =
    171                 new JspException(messages.getMessage("header.get", name));
    172 
    173             TagUtils.getInstance().saveException(pageContext, e);
    174             throw e;
    175         }
    176 
    177         pageContext.setAttribute(id, value);
    178     }
    179 
    180     /**
    181      * Release all allocated resources.
    182      */
    183     public void release() {
    184         super.release();
    185         id = null;
    186         multiple = null;
    187         name = null;
    188         value = null;
    189     }
    190 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
