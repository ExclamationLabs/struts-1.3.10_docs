[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockHttpServletRequest.html.md)


    1   /*
    2    * $Id: MockHttpServletRequest.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.mock;
    22  
    23  import javax.servlet.RequestDispatcher;
    24  import javax.servlet.ServletInputStream;
    25  import javax.servlet.http.Cookie;
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.http.HttpSession;
    28  
    29  import java.io.BufferedReader;
    30  
    31  import java.security.Principal;
    32  
    33  import java.util.Enumeration;
    34  import java.util.HashMap;
    35  import java.util.Locale;
    36  import java.util.Map;
    37  
    38  /**
    39   * <p>Mock <strong>HttpServletRequest</strong> object for low-level unit tests
    40   * of Struts controller components.  Coarser grained tests should be
    41   * implemented in terms of the Cactus framework, instead of the mock object
    42   * classes.</p>
    43   *
    44   * <p><strong>WARNING</strong> - Only the minimal set of methods needed to
    45   * create unit tests is provided, plus additional methods to configure this
    46   * object as necessary.  Methods for unsupported operations will throw
    47   * <code>UnsupportedOperationException</code>.</p>
    48   *
    49   * <p><strong>WARNING</strong> - Because unit tests operate in a single
    50   * threaded environment, no synchronization is performed.</p>
    51   *
    52   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    53   */
    54  public class MockHttpServletRequest implements HttpServletRequest {
    55      // ----------------------------------------------------- Instance Variables
    56  
    57      /**
    58       * <p> The set of request attributes. </p>
    59       */
    60      protected HashMap attributes = new HashMap();
    61  
    62      /**
    63       * <p> The context path for this request. </p>
    64       */
    65      protected String contextPath = null;
    66  
    67      /**
    68       * <p> The preferred locale for this request. </p>
    69       */
    70      protected Locale locale = null;
    71  
    72      /**
    73       * <p> The set of arrays of parameter values, keyed by parameter name.
    74       * </p>
    75       */
    76      protected HashMap parameters = new HashMap();
    77  
    78      /**
    79       * <p> The extra path information for this request. v     * </p>
    80       */
    81      protected String pathInfo = null;
    82  
    83      /**
    84       * <p> The authenticated user for this request. </p>
    85       */
    86      protected Principal principal = null;
    87  
    88      /**
    89       * <p> The query string for this request. </p>
    90       */
    91      protected String queryString = null;
    92  
    93      /**
    94       * <p> The servlet path for this request. </p>
    95       */
    96      protected String servletPath = null;
    97  
    98      /**
    99       * <p> The HttpSession with which we are associated. </p>
    100      */
    101     protected HttpSession session = null;
    102 
    103     /**
    104      * <p> The HTTP request method. </p>
    105      */
    106     protected String method = null;
    107 
    108     /**
    109      * <p> The Content Type for this request. </p>
    110      */
    111     protected String contentType = null;
    112 
    113     // ----------------------------------------------------------- Constructors
    114     public MockHttpServletRequest() {
    115         super();
    116     }
    117 
    118     public MockHttpServletRequest(HttpSession session) {
    119         super();
    120         setHttpSession(session);
    121     }
    122 
    123     public MockHttpServletRequest(String contextPath, String servletPath,
    124         String pathInfo, String queryString) {
    125         super();
    126         setPathElements(contextPath, servletPath, pathInfo, queryString);
    127     }
    128 
    129     public MockHttpServletRequest(String contextPath, String servletPath,
    130         String pathInfo, String queryString, HttpSession session) {
    131         super();
    132         setPathElements(contextPath, servletPath, pathInfo, queryString);
    133         setHttpSession(session);
    134     }
    135 
    136     // --------------------------------------------------------- Public Methods
    137     public void addParameter(String name, String value) {
    138         String[] values = (String[]) parameters.get(name);
    139 
    140         if (values == null) {
    141             String[] results = new String[] { value };
    142 
    143             parameters.put(name, results);
    144 
    145             return;
    146         }
    147 
    148         String[] results = new String[values.length + 1];
    149 
    150         System.arraycopy(values, 0, results, 0, values.length);
    151         results[values.length] = value;
    152         parameters.put(name, results);
    153     }
    154 
    155     public void setHttpSession(HttpSession session) {
    156         this.session = session;
    157     }
    158 
    159     public void setLocale(Locale locale) {
    160         this.locale = locale;
    161     }
    162 
    163     public void setMethod(String method) {
    164         this.method = method;
    165     }
    166 
    167     public void setContentType(String contentType) {
    168         this.contentType = contentType;
    169     }
    170 
    171     public void setPathElements(String contextPath, String servletPath,
    172         String pathInfo, String queryString) {
    173         this.contextPath = contextPath;
    174         this.servletPath = servletPath;
    175         this.pathInfo = pathInfo;
    176         this.queryString = queryString;
    177     }
    178 
    179     public void setUserPrincipal(Principal principal) {
    180         this.principal = principal;
    181     }
    182 
    183     // --------------------------------------------- HttpServletRequest Methods
    184     public String getAuthType() {
    185         throw new UnsupportedOperationException();
    186     }
    187 
    188     public String getContextPath() {
    189         return (contextPath);
    190     }
    191 
    192     public Cookie[] getCookies() {
    193         throw new UnsupportedOperationException();
    194     }
    195 
    196     public long getDateHeader(String name) {
    197         throw new UnsupportedOperationException();
    198     }
    199 
    200     public String getHeader(String name) {
    201         throw new UnsupportedOperationException();
    202     }
    203 
    204     public Enumeration getHeaderNames() {
    205         throw new UnsupportedOperationException();
    206     }
    207 
    208     public Enumeration getHeaders(String name) {
    209         throw new UnsupportedOperationException();
    210     }
    211 
    212     public int getIntHeader(String name) {
    213         throw new UnsupportedOperationException();
    214     }
    215 
    216     public String getMethod() {
    217         return (method);
    218     }
    219 
    220     public String getPathInfo() {
    221         return (pathInfo);
    222     }
    223 
    224     public String getPathTranslated() {
    225         throw new UnsupportedOperationException();
    226     }
    227 
    228     public String getQueryString() {
    229         return (queryString);
    230     }
    231 
    232     public String getRemoteUser() {
    233         if (principal != null) {
    234             return (principal.getName());
    235         } else {
    236             return (null);
    237         }
    238     }
    239 
    240     public String getRequestedSessionId() {
    241         throw new UnsupportedOperationException();
    242     }
    243 
    244     public String getRequestURI() {
    245         StringBuffer sb = new StringBuffer();
    246 
    247         if (contextPath != null) {
    248             sb.append(contextPath);
    249         }
    250 
    251         if (servletPath != null) {
    252             sb.append(servletPath);
    253         }
    254 
    255         if (pathInfo != null) {
    256             sb.append(pathInfo);
    257         }
    258 
    259         if (sb.length() > 0) {
    260             return (sb.toString());
    261         }
    262 
    263         throw new UnsupportedOperationException();
    264     }
    265 
    266     public StringBuffer getRequestURL() {
    267         throw new UnsupportedOperationException();
    268     }
    269 
    270     public String getServletPath() {
    271         return (servletPath);
    272     }
    273 
    274     public HttpSession getSession() {
    275         return (getSession(true));
    276     }
    277 
    278     public HttpSession getSession(boolean create) {
    279         if (create && (session == null)) {
    280             session = new MockHttpSession();
    281 
    282             // modified to act like the real deal,
    283             // call with (false) if you want null
    284             // throw new UnsupportedOperationException();
    285         }
    286 
    287         return (session);
    288     }
    289 
    290     public Principal getUserPrincipal() {
    291         return (principal);
    292     }
    293 
    294     public boolean isRequestedSessionIdFromCookie() {
    295         throw new UnsupportedOperationException();
    296     }
    297 
    298     public boolean isRequestedSessionIdFromUrl() {
    299         throw new UnsupportedOperationException();
    300     }
    301 
    302     public boolean isRequestedSessionIdFromURL() {
    303         throw new UnsupportedOperationException();
    304     }
    305 
    306     public boolean isRequestedSessionIdValid() {
    307         throw new UnsupportedOperationException();
    308     }
    309 
    310     public boolean isUserInRole(String role) {
    311         if ((principal != null) && (principal instanceof MockPrincipal)) {
    312             return (((MockPrincipal) principal).isUserInRole(role));
    313         } else {
    314             return (false);
    315         }
    316     }
    317 
    318     // ------------------------------------------------- ServletRequest Methods
    319     public Object getAttribute(String name) {
    320         return (attributes.get(name));
    321     }
    322 
    323     public Enumeration getAttributeNames() {
    324         return (new MockEnumeration(attributes.keySet().iterator()));
    325     }
    326 
    327     public String getCharacterEncoding() {
    328         throw new UnsupportedOperationException();
    329     }
    330 
    331     public int getContentLength() {
    332         throw new UnsupportedOperationException();
    333     }
    334 
    335     public String getContentType() {
    336         return (contentType);
    337     }
    338 
    339     public ServletInputStream getInputStream() {
    340         throw new UnsupportedOperationException();
    341     }
    342 
    343     public Locale getLocale() {
    344         return (locale);
    345     }
    346 
    347     public Enumeration getLocales() {
    348         throw new UnsupportedOperationException();
    349     }
    350 
    351     public String getParameter(String name) {
    352         String[] values = (String[]) parameters.get(name);
    353 
    354         if (values != null) {
    355             return (values[0]);
    356         } else {
    357             return (null);
    358         }
    359     }
    360 
    361     public Map getParameterMap() {
    362         return (parameters);
    363     }
    364 
    365     public Enumeration getParameterNames() {
    366         return (new MockEnumeration(parameters.keySet().iterator()));
    367     }
    368 
    369     public String[] getParameterValues(String name) {
    370         return ((String[]) parameters.get(name));
    371     }
    372 
    373     public String getProtocol() {
    374         throw new UnsupportedOperationException();
    375     }
    376 
    377     public BufferedReader getReader() {
    378         throw new UnsupportedOperationException();
    379     }
    380 
    381     public String getRealPath(String path) {
    382         throw new UnsupportedOperationException();
    383     }
    384 
    385     public String getRemoteAddr() {
    386         throw new UnsupportedOperationException();
    387     }
    388 
    389     public String getRemoteHost() {
    390         throw new UnsupportedOperationException();
    391     }
    392 
    393     public RequestDispatcher getRequestDispatcher(String path) {
    394         throw new UnsupportedOperationException();
    395     }
    396 
    397     public String getScheme() {
    398         return ("http");
    399     }
    400 
    401     public String getServerName() {
    402         return ("localhost");
    403     }
    404 
    405     public int getServerPort() {
    406         return (8080);
    407     }
    408 
    409     public boolean isSecure() {
    410         return (false);
    411     }
    412 
    413     public void removeAttribute(String name) {
    414         attributes.remove(name);
    415     }
    416 
    417     public void setAttribute(String name, Object value) {
    418         if (value == null) {
    419             attributes.remove(name);
    420         } else {
    421             attributes.put(name, value);
    422         }
    423     }
    424 
    425     public void setCharacterEncoding(String name) {
    426         throw new UnsupportedOperationException();
    427     }
    428 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
