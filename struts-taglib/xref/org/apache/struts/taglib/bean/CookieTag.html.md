[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/CookieTag.html.md)


    1   /*
    2    * $Id: CookieTag.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.servlet.http.Cookie;
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.tagext.TagSupport;
    30  
    31  import java.util.ArrayList;
    32  
    33  /**
    34   * Define a scripting variable based on the value(s) of the specified cookie
    35   * received with this request.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public class CookieTag extends TagSupport {
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
    57       * Return an array of Cookies if <code>multiple</code> is non-null.
    58       */
    59      protected String multiple = null;
    60  
    61      /**
    62       * The name of the cookie whose value is to be exposed.
    63       */
    64      protected String name = null;
    65  
    66      /**
    67       * The default value to return if no cookie of the specified name is
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
    112         // Retrieve the required cookie value(s)
    113         ArrayList values = new ArrayList();
    114         Cookie[] cookies =
    115             ((HttpServletRequest) pageContext.getRequest()).getCookies();
    116 
    117         if (cookies == null) {
    118             cookies = new Cookie[0];
    119         }
    120 
    121         for (int i = 0; i < cookies.length; i++) {
    122             if (name.equals(cookies[i].getName())) {
    123                 values.add(cookies[i]);
    124             }
    125         }
    126 
    127         if ((values.size() < 1) && (value != null)) {
    128             values.add(new Cookie(name, value));
    129         }
    130 
    131         if (values.size() < 1) {
    132             JspException e =
    133                 new JspException(messages.getMessage("cookie.get", name));
    134 
    135             TagUtils.getInstance().saveException(pageContext, e);
    136             throw e;
    137         }
    138 
    139         // Expose an appropriate variable containing these results
    140         if (multiple == null) {
    141             Cookie cookie = (Cookie) values.get(0);
    142 
    143             pageContext.setAttribute(id, cookie);
    144         } else {
    145             cookies = new Cookie[values.size()];
    146             pageContext.setAttribute(id, values.toArray(cookies));
    147         }
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
