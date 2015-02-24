[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/PageTag.html.md)


    1   /*
    2    * $Id: PageTag.java 471754 2006-11-06 14:55:09Z husted $
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
    30   * Define a scripting variable that exposes the requested page context item as
    31   * a scripting variable and a page scope bean.
    32   *
    33   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    34   *          $
    35   */
    36  public class PageTag extends TagSupport {
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
    53       * The name of the page context property to be retrieved.
    54       */
    55      protected String property = null;
    56  
    57      public String getId() {
    58          return (this.id);
    59      }
    60  
    61      public void setId(String id) {
    62          this.id = id;
    63      }
    64  
    65      public String getProperty() {
    66          return (this.property);
    67      }
    68  
    69      public void setProperty(String property) {
    70          this.property = property;
    71      }
    72  
    73      // --------------------------------------------------------- Public Methods
    74  
    75      /**
    76       * Retrieve the required configuration object and expose it as a scripting
    77       * variable.
    78       *
    79       * @throws JspException if a JSP exception has occurred
    80       */
    81      public int doStartTag() throws JspException {
    82          // Retrieve the requested object to be exposed
    83          Object object = null;
    84  
    85          if ("application".equalsIgnoreCase(property)) {
    86              object = pageContext.getServletContext();
    87          } else if ("config".equalsIgnoreCase(property)) {
    88              object = pageContext.getServletConfig();
    89          } else if ("request".equalsIgnoreCase(property)) {
    90              object = pageContext.getRequest();
    91          } else if ("response".equalsIgnoreCase(property)) {
    92              object = pageContext.getResponse();
    93          } else if ("session".equalsIgnoreCase(property)) {
    94              object = pageContext.getSession();
    95          } else {
    96              JspException e =
    97                  new JspException(messages.getMessage("page.selector", property));
    98  
    99              TagUtils.getInstance().saveException(pageContext, e);
    100             throw e;
    101         }
    102 
    103         // Expose this value as a scripting variable
    104         pageContext.setAttribute(id, object);
    105 
    106         return (SKIP_BODY);
    107     }
    108 
    109     /**
    110      * Release all allocated resources.
    111      */
    112     public void release() {
    113         super.release();
    114         id = null;
    115         property = null;
    116     }
    117 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)