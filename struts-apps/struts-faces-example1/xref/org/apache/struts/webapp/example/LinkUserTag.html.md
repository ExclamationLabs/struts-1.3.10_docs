[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/LinkUserTag.html.md)


    1   /*
    2    * $Id: LinkUserTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  
    23  package org.apache.struts.webapp.example;
    24  
    25  
    26  import java.io.IOException;
    27  
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.jsp.JspException;
    31  import javax.servlet.jsp.JspWriter;
    32  import javax.servlet.jsp.tagext.TagSupport;
    33  
    34  import org.apache.struts.util.MessageResources;
    35  import org.apache.struts.util.ResponseUtils;
    36  
    37  
    38  /**
    39   * Generate a URL-encoded hyperlink to the specified URI, with
    40   * associated query parameters selecting a specified User.
    41   *
    42   * @author Craig R. McClanahan
    43   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    44   */
    45  
    46  public class LinkUserTag extends TagSupport {
    47  
    48  
    49      // ------------------------------------------------------ Instance Variables
    50  
    51  
    52      /**
    53       * The hyperlink URI.
    54       */
    55      protected String page = null;
    56  
    57  
    58      /**
    59       * The message resources for this package.
    60       */
    61      protected static MessageResources messages =
    62      MessageResources.getMessageResources
    63      ("org.apache.struts.webapp.example.ApplicationResources");
    64  
    65  
    66      /**
    67       * The attribute name.
    68       */
    69      private String name = "user";
    70  
    71  
    72      // ------------------------------------------------------------- Properties
    73  
    74  
    75      /**
    76       * Return the hyperlink URI.
    77       */
    78      public String getPage() {
    79  
    80      return (this.page);
    81  
    82      }
    83  
    84  
    85      /**
    86       * Set the hyperlink URI.
    87       *
    88       * @param page Set the hyperlink URI
    89       */
    90      public void setPage(String page) {
    91  
    92      this.page = page;
    93  
    94      }
    95  
    96  
    97      /**
    98       * Return the attribute name.
    99       */
    100     public String getName() {
    101 
    102     return (this.name);
    103 
    104     }
    105 
    106 
    107     /**
    108      * Set the attribute name.
    109      *
    110      * @param name The new attribute name
    111      */
    112     public void setName(String name) {
    113 
    114     this.name = name;
    115 
    116     }
    117 
    118 
    119     // --------------------------------------------------------- Public Methods
    120 
    121 
    122     /**
    123      * Render the beginning of the hyperlink.
    124      *
    125      * @exception JspException if a JSP exception has occurred
    126      */
    127     public int doStartTag() throws JspException {
    128 
    129     // Generate the URL to be encoded
    130         HttpServletRequest request =
    131             (HttpServletRequest) pageContext.getRequest();
    132         StringBuffer url = new StringBuffer(request.getContextPath());
    133         url.append(page);
    134     User user = null;
    135     try {
    136         user = (User) pageContext.findAttribute(name);
    137         } catch (ClassCastException e) {
    138         user = null;
    139     }
    140     if (user == null)
    141         throw new JspException
    142             (messages.getMessage("linkUser.noUser", name));
    143     if (page.indexOf("?") < 0)
    144         url.append("?");
    145     else
    146         url.append("&");
    147     url.append("username=");
    148     url.append(ResponseUtils.filter(user.getUsername()));
    149 
    150     // Generate the hyperlink start element
    151     HttpServletResponse response =
    152       (HttpServletResponse) pageContext.getResponse();
    153     StringBuffer results = new StringBuffer("<a href=\"");
    154     results.append(response.encodeURL(url.toString()));
    155     results.append("\">");
    156 
    157     // Print this element to our output writer
    158     JspWriter writer = pageContext.getOut();
    159     try {
    160         writer.print(results.toString());
    161     } catch (IOException e) {
    162         throw new JspException
    163         (messages.getMessage("linkUser.io", e.toString()));
    164     }
    165 
    166     // Evaluate the body of this tag
    167     return (EVAL_BODY_INCLUDE);
    168 
    169     }
    170 
    171 
    172 
    173     /**
    174      * Render the end of the hyperlink.
    175      *
    176      * @exception JspException if a JSP exception has occurred
    177      */
    178     public int doEndTag() throws JspException {
    179 
    180 
    181     // Print the ending element to our output writer
    182     JspWriter writer = pageContext.getOut();
    183     try {
    184         writer.print("</a>");
    185     } catch (IOException e) {
    186         throw new JspException
    187             (messages.getMessage("link.io", e.toString()));
    188     }
    189 
    190     return (EVAL_PAGE);
    191 
    192     }
    193 
    194 
    195     /**
    196      * Release any acquired resources.
    197      */
    198     public void release() {
    199 
    200         super.release();
    201         this.page = null;
    202         this.name = "user";
    203 
    204     }
    205 
    206 
    207 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
