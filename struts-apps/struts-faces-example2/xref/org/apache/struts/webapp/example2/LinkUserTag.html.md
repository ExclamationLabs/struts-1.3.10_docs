[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/LinkUserTag.html.md)


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
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import java.io.IOException;
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  import javax.servlet.jsp.JspException;
    30  import javax.servlet.jsp.JspWriter;
    31  import javax.servlet.jsp.tagext.TagSupport;
    32  import org.apache.struts.util.MessageResources;
    33  import org.apache.struts.util.ResponseUtils;
    34  
    35  
    36  /**
    37   * Generate a URL-encoded hyperlink to the specified URI, with
    38   * associated query parameters selecting a specified User.
    39   *
    40   * @author Craig R. McClanahan
    41   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    42   */
    43  
    44  public class LinkUserTag extends TagSupport {
    45  
    46  
    47      // ------------------------------------------------------ Instance Variables
    48  
    49  
    50      /**
    51       * The hyperlink URI.
    52       */
    53      protected String page = null;
    54  
    55  
    56      /**
    57       * The message resources for this package.
    58       */
    59      protected static MessageResources messages =
    60      MessageResources.getMessageResources
    61      ("org.apache.struts.webapp.example.ApplicationResources");
    62  
    63  
    64      /**
    65       * The attribute name.
    66       */
    67      private String name = "user";
    68  
    69  
    70      // ------------------------------------------------------------- Properties
    71  
    72  
    73      /**
    74       * Return the hyperlink URI.
    75       */
    76      public String getPage() {
    77  
    78      return (this.page);
    79  
    80      }
    81  
    82  
    83      /**
    84       * Set the hyperlink URI.
    85       *
    86       * @param page Set the hyperlink URI
    87       */
    88      public void setPage(String page) {
    89  
    90      this.page = page;
    91  
    92      }
    93  
    94  
    95      /**
    96       * Return the attribute name.
    97       */
    98      public String getName() {
    99  
    100     return (this.name);
    101 
    102     }
    103 
    104 
    105     /**
    106      * Set the attribute name.
    107      *
    108      * @param name The new attribute name
    109      */
    110     public void setName(String name) {
    111 
    112     this.name = name;
    113 
    114     }
    115 
    116 
    117     // --------------------------------------------------------- Public Methods
    118 
    119 
    120     /**
    121      * Render the beginning of the hyperlink.
    122      *
    123      * @exception JspException if a JSP exception has occurred
    124      */
    125     public int doStartTag() throws JspException {
    126 
    127     // Generate the URL to be encoded
    128         HttpServletRequest request =
    129             (HttpServletRequest) pageContext.getRequest();
    130         StringBuffer url = new StringBuffer(request.getContextPath());
    131         url.append(page);
    132     User user = null;
    133     try {
    134         user = (User) pageContext.findAttribute(name);
    135         } catch (ClassCastException e) {
    136         user = null;
    137     }
    138     if (user == null)
    139         throw new JspException
    140             (messages.getMessage("linkUser.noUser", name));
    141     if (page.indexOf("?") < 0)
    142         url.append("?");
    143     else
    144         url.append("&");
    145     url.append("username=");
    146     url.append(ResponseUtils.filter(user.getUsername()));
    147 
    148     // Generate the hyperlink start element
    149     HttpServletResponse response =
    150       (HttpServletResponse) pageContext.getResponse();
    151     StringBuffer results = new StringBuffer("<a href=\"");
    152     results.append(response.encodeURL(url.toString()));
    153     results.append("\">");
    154 
    155     // Print this element to our output writer
    156     JspWriter writer = pageContext.getOut();
    157     try {
    158         writer.print(results.toString());
    159     } catch (IOException e) {
    160         throw new JspException
    161         (messages.getMessage("linkUser.io", e.toString()));
    162     }
    163 
    164     // Evaluate the body of this tag
    165     return (EVAL_BODY_INCLUDE);
    166 
    167     }
    168 
    169 
    170 
    171     /**
    172      * Render the end of the hyperlink.
    173      *
    174      * @exception JspException if a JSP exception has occurred
    175      */
    176     public int doEndTag() throws JspException {
    177 
    178 
    179     // Print the ending element to our output writer
    180     JspWriter writer = pageContext.getOut();
    181     try {
    182         writer.print("</a>");
    183     } catch (IOException e) {
    184         throw new JspException
    185             (messages.getMessage("link.io", e.toString()));
    186     }
    187 
    188     return (EVAL_PAGE);
    189 
    190     }
    191 
    192 
    193     /**
    194      * Release any acquired resources.
    195      */
    196     public void release() {
    197 
    198         super.release();
    199         this.page = null;
    200         this.name = "user";
    201 
    202     }
    203 
    204 
    205 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
