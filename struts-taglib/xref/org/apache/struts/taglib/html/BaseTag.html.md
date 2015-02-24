[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/BaseTag.html)


    1   /*
    2    * $Id: BaseTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  import org.apache.struts.util.RequestUtils;
    27  
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.jsp.JspException;
    30  import javax.servlet.jsp.JspWriter;
    31  import javax.servlet.jsp.PageContext;
    32  import javax.servlet.jsp.tagext.TagSupport;
    33  
    34  import java.io.IOException;
    35  
    36  import java.util.StringTokenizer;
    37  
    38  /**
    39   * Renders an HTML <base> element with an href attribute pointing to the
    40   * absolute location of the enclosing JSP page. This tag is only valid when
    41   * nested inside a head tag body. The presence of this tag allows the browser
    42   * to resolve relative URL's to images, CSS stylesheets  and other resources
    43   * in a manner independent of the URL used to call the ActionServlet.
    44   *
    45   * @version $Rev: 471754 $ $Date: 2005-09-20 02:29:01 -0400 (Tue, 20 Sep 2005)
    46   *          $
    47   */
    48  public class BaseTag extends TagSupport {
    49      /**
    50       * The message resources for this package.
    51       */
    52      protected static MessageResources messages =
    53          MessageResources.getMessageResources(Constants.Package
    54              + ".LocalStrings");
    55      protected final String REF_SITE = "site";
    56      protected final String REF_PAGE = "page";
    57  
    58      /**
    59       * The server name to use instead of request.getServerName().
    60       */
    61      protected String server = null;
    62  
    63      /**
    64       * The target window for this base reference.
    65       */
    66      protected String target = null;
    67  
    68      /**
    69       * The reference to which the base will created.
    70       */
    71      protected String ref = REF_PAGE;
    72  
    73      /**
    74       * Gets the reference to which the base will be created
    75       */
    76      public String getRef() {
    77          return (this.ref);
    78      }
    79  
    80      /**
    81       * Sets the reference to which the base will be created.
    82       *
    83       * @param ref Either "page" to render the base as the jsp path located, or
    84       *            "site" as the application's context
    85       */
    86      public void setRef(String ref) {
    87          if (ref == null) {
    88              throw new IllegalArgumentException("Ref attribute cannot be null");
    89          }
    90  
    91          ref = ref.toLowerCase();
    92  
    93          if (ref.equals(REF_PAGE) || ref.equals(REF_SITE)) {
    94              this.ref = ref;
    95          } else {
    96              throw new IllegalArgumentException("Ref attribute must either be "
    97                  + "'" + REF_PAGE + "' or '" + REF_SITE + "'");
    98          }
    99      }
    100 
    101     public String getTarget() {
    102         return (this.target);
    103     }
    104 
    105     public void setTarget(String target) {
    106         this.target = target;
    107     }
    108 
    109     /**
    110      * Process the start of this tag.
    111      *
    112      * @throws JspException if a JSP exception has occurred
    113      */
    114     public int doStartTag() throws JspException {
    115         HttpServletRequest request =
    116             (HttpServletRequest) pageContext.getRequest();
    117         String serverName =
    118             (this.server == null) ? request.getServerName() : this.server;
    119 
    120         int port = request.getServerPort();
    121         String headerHost = request.getHeader("Host");
    122 
    123         if ((serverName == null) && (headerHost != null)) {
    124             StringTokenizer tokenizer = new StringTokenizer(headerHost, ":");
    125 
    126             serverName = tokenizer.nextToken();
    127 
    128             if (tokenizer.hasMoreTokens()) {
    129                 String portS = tokenizer.nextToken();
    130 
    131                 try {
    132                     port = Integer.parseInt(portS);
    133                 } catch (Exception e) {
    134                     port = 80;
    135                 }
    136             } else {
    137                 port = 80;
    138             }
    139         }
    140 
    141         String baseTag =
    142             renderBaseElement(request.getScheme(), serverName, port,
    143                 request.getRequestURI());
    144 
    145         JspWriter out = pageContext.getOut();
    146 
    147         try {
    148             out.write(baseTag);
    149         } catch (IOException e) {
    150             pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    151                 PageContext.REQUEST_SCOPE);
    152             throw new JspException(messages.getMessage("common.io", e.toString()));
    153         }
    154 
    155         return EVAL_BODY_INCLUDE;
    156     }
    157 
    158     /**
    159      * Render a fully formed HTML &lt;base&gt; element and return it as a
    160      * String.
    161      *
    162      * @param scheme     The scheme used in the url (ie. http or https).
    163      * @param serverName
    164      * @param port
    165      * @param uri        The portion of the url from the protocol name up to
    166      *                   the query string.
    167      * @return String An HTML &lt;base&gt; element.
    168      * @since Struts 1.1
    169      */
    170     protected String renderBaseElement(String scheme, String serverName,
    171         int port, String uri) {
    172         StringBuffer tag = new StringBuffer("<base href=\"");
    173 
    174         if (ref.equals(REF_SITE)) {
    175             StringBuffer contextBase =
    176                 new StringBuffer(((HttpServletRequest) pageContext.getRequest())
    177                     .getContextPath());
    178 
    179             contextBase.append("/");
    180             tag.append(RequestUtils.createServerUriStringBuffer(scheme,
    181                     serverName, port, contextBase.toString()).toString());
    182         } else {
    183             tag.append(RequestUtils.createServerUriStringBuffer(scheme,
    184                     serverName, port, uri).toString());
    185         }
    186 
    187         tag.append("\"");
    188 
    189         if (this.target != null) {
    190             tag.append(" target=\"");
    191             tag.append(this.target);
    192             tag.append("\"");
    193         }
    194 
    195         if (TagUtils.getInstance().is.html.md(this.pageContext)) {
    196             tag.append(" />");
    197         } else {
    198             tag.append(">");
    199         }
    200 
    201         return tag.toString();
    202     }
    203 
    204     /**
    205      * Returns the server.
    206      *
    207      * @return String
    208      */
    209     public String getServer() {
    210         return this.server;
    211     }
    212 
    213     /**
    214      * Sets the server.
    215      *
    216      * @param server The server to set
    217      */
    218     public void setServer(String server) {
    219         this.server = server;
    220     }
    221 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
