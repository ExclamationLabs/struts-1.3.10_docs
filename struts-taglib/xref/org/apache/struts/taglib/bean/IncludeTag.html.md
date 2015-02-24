[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/IncludeTag.html.md)


    1   /*
    2    * $Id: IncludeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import org.apache.struts.util.RequestUtils;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.tagext.TagSupport;
    30  
    31  import java.io.BufferedInputStream;
    32  import java.io.InputStreamReader;
    33  
    34  import java.net.HttpURLConnection;
    35  import java.net.MalformedURLException;
    36  import java.net.URL;
    37  import java.net.URLConnection;
    38  
    39  import java.util.Map;
    40  
    41  /**
    42   * Define the contents of a specified intra-application request as a page
    43   * scope attribute of type <code>java.lang.String</code>.  If the current
    44   * request is part of a session, the session identifier will be included in
    45   * the generated request, so it will be part of the same session. <p>
    46   * <strong>FIXME</strong>:  In a servlet 2.3 environment, we can use a wrapped
    47   * response passed to RequestDispatcher.include().
    48   *
    49   * @version $Rev: 471754 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005)
    50   *          $
    51   */
    52  public class IncludeTag extends TagSupport {
    53      // ------------------------------------------------------------- Properties
    54  
    55      /**
    56       * Buffer size to use when reading the input stream.
    57       */
    58      protected static final int BUFFER_SIZE = 256;
    59  
    60      /**
    61       * The message resources for this package.
    62       */
    63      protected static MessageResources messages =
    64          MessageResources.getMessageResources(
    65              "org.apache.struts.taglib.bean.LocalStrings");
    66  
    67      /**
    68       * The anchor to be added to the end of the generated hyperlink.
    69       */
    70      protected String anchor = null;
    71  
    72      /**
    73       * The name of the global <code>ActionForward</code> that contains a path
    74       * to our requested resource.
    75       */
    76      protected String forward = null;
    77  
    78      /**
    79       * The absolute URL to the resource to be included.
    80       */
    81      protected String href = null;
    82  
    83      /**
    84       * The name of the scripting variable that will be exposed as a page scope
    85       * attribute.
    86       */
    87      protected String id = null;
    88  
    89      /**
    90       * The context-relative URI of the page or servlet to be included.
    91       */
    92      protected String page = null;
    93  
    94      /**
    95       * Include transaction token (if any) in the hyperlink?
    96       */
    97      protected boolean transaction = false;
    98      protected boolean useLocalEncoding = false;
    99  
    100     public String getAnchor() {
    101         return (this.anchor);
    102     }
    103 
    104     public void setAnchor(String anchor) {
    105         this.anchor = anchor;
    106     }
    107 
    108     public String getForward() {
    109         return (this.forward);
    110     }
    111 
    112     public void setForward(String forward) {
    113         this.forward = forward;
    114     }
    115 
    116     public String getHref() {
    117         return (this.href);
    118     }
    119 
    120     public void setHref(String href) {
    121         this.href = href;
    122     }
    123 
    124     public String getId() {
    125         return (this.id);
    126     }
    127 
    128     public void setId(String id) {
    129         this.id = id;
    130     }
    131 
    132     public String getPage() {
    133         return (this.page);
    134     }
    135 
    136     public void setPage(String page) {
    137         this.page = page;
    138     }
    139 
    140     public boolean getTransaction() {
    141         return (this.transaction);
    142     }
    143 
    144     public void setTransaction(boolean transaction) {
    145         this.transaction = transaction;
    146     }
    147 
    148     public boolean isUseLocalEncoding() {
    149         return useLocalEncoding;
    150     }
    151 
    152     public void setUseLocalEncoding(boolean b) {
    153         useLocalEncoding = b;
    154     }
    155 
    156     // --------------------------------------------------------- Public Methods
    157 
    158     /**
    159      * Define the contents returned for the specified resource as a page scope
    160      * attribute.
    161      *
    162      * @throws JspException if a JSP error occurs
    163      */
    164     public int doStartTag() throws JspException {
    165         // Set up a URLConnection to read the requested resource
    166         Map params =
    167             TagUtils.getInstance().computeParameters(pageContext, null, null,
    168                 null, null, null, null, null, transaction);
    169 
    170         // FIXME - .html.md:link> attributes
    171         String urlString = null;
    172         URL url = null;
    173 
    174         try {
    175             urlString =
    176                 TagUtils.getInstance().computeURLWithCharEncoding(pageContext,
    177                     forward, href, page, null, null, params, anchor, false,
    178                     useLocalEncoding);
    179 
    180             if (urlString.indexOf(':') < 0) {
    181                 HttpServletRequest request =
    182                     (HttpServletRequest) pageContext.getRequest();
    183 
    184                 url = new URL(RequestUtils.requestURL(request), urlString);
    185             } else {
    186                 url = new URL(urlString);
    187             }
    188         } catch (MalformedURLException e) {
    189             TagUtils.getInstance().saveException(pageContext, e);
    190             throw new JspException(messages.getMessage("include.url",
    191                     e.toString()));
    192         }
    193 
    194         URLConnection conn = null;
    195 
    196         try {
    197             // Set up the basic connection
    198             conn = url.openConnection();
    199             conn.setAllowUserInteraction(false);
    200             conn.setDoInput(true);
    201             conn.setDoOutput(false);
    202 
    203             // Add a session id cookie if appropriate
    204             HttpServletRequest request =
    205                 (HttpServletRequest) pageContext.getRequest();
    206 
    207             addCookie(conn, urlString, request);
    208 
    209             // Connect to the requested resource
    210             conn.connect();
    211         } catch (Exception e) {
    212             TagUtils.getInstance().saveException(pageContext, e);
    213             throw new JspException(messages.getMessage("include.open",
    214                     url.toString(), e.toString()));
    215         }
    216 
    217         // Copy the contents of this URL
    218         StringBuffer sb = new StringBuffer();
    219 
    220         try {
    221             BufferedInputStream is =
    222                 new BufferedInputStream(conn.getInputStream());
    223             InputStreamReader in = new InputStreamReader(is); // FIXME- encoding
    224             char[] buffer = new char[BUFFER_SIZE];
    225             int n = 0;
    226 
    227             while (true) {
    228                 n = in.read(buffer);
    229 
    230                 if (n < 1) {
    231                     break;
    232                 }
    233 
    234                 sb.append(buffer, 0, n);
    235             }
    236 
    237             in.close();
    238         } catch (Exception e) {
    239             TagUtils.getInstance().saveException(pageContext, e);
    240             throw new JspException(messages.getMessage("include.read",
    241                     url.toString(), e.toString()));
    242         }
    243 
    244         // Define the retrieved content as a page scope attribute
    245         pageContext.setAttribute(id, sb.toString());
    246 
    247         // Skip any body of this tag
    248         return (SKIP_BODY);
    249     }
    250 
    251     /**
    252      * Add a session id cookie if appropriate. Can be overloaded to support a
    253      * cluster.
    254      *
    255      * @param conn
    256      * @param urlString
    257      * @param request
    258      * @since Struts 1.2.0
    259      */
    260     protected void addCookie(URLConnection conn, String urlString,
    261         HttpServletRequest request) {
    262         if ((conn instanceof HttpURLConnection)
    263             && urlString.startsWith(request.getContextPath())
    264             && (request.getRequestedSessionId() != null)
    265             && request.isRequestedSessionIdFromCookie()) {
    266             StringBuffer sb = new StringBuffer("JSESSIONID=");
    267 
    268             sb.append(request.getRequestedSessionId());
    269             conn.setRequestProperty("Cookie", sb.toString());
    270         }
    271     }
    272 
    273     /**
    274      * Release all allocated resources.
    275      */
    276     public void release() {
    277         super.release();
    278         anchor = null;
    279         forward = null;
    280         href = null;
    281         id = null;
    282         page = null;
    283         transaction = false;
    284     }
    285 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
