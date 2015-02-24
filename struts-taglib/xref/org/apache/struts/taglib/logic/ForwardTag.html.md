[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/ForwardTag.html.md)


    1   /*
    2    * $Id: ForwardTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.logic;
    22  
    23  import org.apache.struts.action.ActionForward;
    24  import org.apache.struts.config.ModuleConfig;
    25  import org.apache.struts.taglib.TagUtils;
    26  import org.apache.struts.util.MessageResources;
    27  
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.jsp.JspException;
    31  import javax.servlet.jsp.tagext.TagSupport;
    32  
    33  /**
    34   * Perform a forward or redirect to a page that is looked up in the
    35   * configuration information associated with our application.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public class ForwardTag extends TagSupport {
    41      // ----------------------------------------------------------- Properties
    42  
    43      /**
    44       * The message resources for this package.
    45       */
    46      protected static MessageResources messages =
    47          MessageResources.getMessageResources(
    48              "org.apache.struts.taglib.logic.LocalStrings");
    49  
    50      /**
    51       * The logical name of the <code>ActionForward</code> entry to be looked
    52       * up.
    53       */
    54      protected String name = null;
    55  
    56      public String getName() {
    57          return (this.name);
    58      }
    59  
    60      public void setName(String name) {
    61          this.name = name;
    62      }
    63  
    64      // ------------------------------------------------------- Public Methods
    65  
    66      /**
    67       * Defer processing until the end of this tag is encountered.
    68       *
    69       * @throws JspException if a JSP exception has occurred
    70       */
    71      public int doStartTag() throws JspException {
    72          return (SKIP_BODY);
    73      }
    74  
    75      /**
    76       * Look up the ActionForward associated with the specified name, and
    77       * perform a forward or redirect to that path as indicated.
    78       *
    79       * @throws JspException if a JSP exception has occurred
    80       */
    81      public int doEndTag() throws JspException {
    82          // Look up the desired ActionForward entry
    83          ActionForward forward = null;
    84          ModuleConfig config =
    85              TagUtils.getInstance().getModuleConfig(pageContext);
    86  
    87          if (config != null) {
    88              forward = (ActionForward) config.findForwardConfig(name);
    89          }
    90  
    91          if (forward == null) {
    92              JspException e =
    93                  new JspException(messages.getMessage("forward.lookup", name));
    94  
    95              TagUtils.getInstance().saveException(pageContext, e);
    96              throw e;
    97          }
    98  
    99          // Forward or redirect to the corresponding actual path
    100         String path = forward.getPath();
    101 
    102         path = config.getPrefix() + path;
    103 
    104         if (forward.getRedirect()) {
    105             this.doRedirect(path);
    106         } else {
    107             this.doForward(path);
    108         }
    109 
    110         // Skip the remainder of this page
    111         return (SKIP_PAGE);
    112     }
    113 
    114     /**
    115      * Forward to the given path converting exceptions to JspException.
    116      *
    117      * @param path The path to forward to.
    118      * @throws JspException
    119      * @since Struts 1.2
    120      */
    121     protected void doForward(String path)
    122         throws JspException {
    123         try {
    124             pageContext.forward(path);
    125         } catch (Exception e) {
    126             TagUtils.getInstance().saveException(pageContext, e);
    127             throw new JspException(messages.getMessage("forward.forward", name,
    128                     e.toString()));
    129         }
    130     }
    131 
    132     /**
    133      * Redirect to the given path converting exceptions to JspException.
    134      *
    135      * @param path The path to redirect to.
    136      * @throws JspException
    137      * @since Struts 1.2
    138      */
    139     protected void doRedirect(String path)
    140         throws JspException {
    141         HttpServletRequest request =
    142             (HttpServletRequest) pageContext.getRequest();
    143 
    144         HttpServletResponse response =
    145             (HttpServletResponse) pageContext.getResponse();
    146 
    147         try {
    148             if (path.startsWith("/")) {
    149                 path = request.getContextPath() + path;
    150             }
    151 
    152             response.sendRedirect(response.encodeRedirectURL(path));
    153         } catch (Exception e) {
    154             TagUtils.getInstance().saveException(pageContext, e);
    155             throw new JspException(messages.getMessage("forward.redirect",
    156                     name, e.toString()));
    157         }
    158     }
    159 
    160     /**
    161      * Release all allocated resources.
    162      */
    163     public void release() {
    164         super.release();
    165         name = null;
    166     }
    167 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
