[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockPageContext.html.md)


    1   /*
    2    * $Id: MockPageContext.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import javax.servlet.Servlet;
    24  import javax.servlet.ServletConfig;
    25  import javax.servlet.ServletContext;
    26  import javax.servlet.ServletRequest;
    27  import javax.servlet.ServletResponse;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpSession;
    30  import javax.servlet.jsp.JspWriter;
    31  import javax.servlet.jsp.PageContext;
    32  import javax.servlet.jsp.tagext.BodyContent;
    33  
    34  import java.io.IOException;
    35  import java.io.Reader;
    36  import java.io.Writer;
    37  
    38  import java.util.Collections;
    39  import java.util.Enumeration;
    40  import java.util.HashMap;
    41  
    42  /**
    43   * <p>Mock <strong>ServletContext</strong> object for low-level unit tests of
    44   * Struts controller components.  Coarser grained tests should be implemented
    45   * in terms of the Cactus framework, instead of the mock object classes.</p>
    46   *
    47   * <p><strong>WARNING</strong> - Only the minimal set of methods needed to
    48   * create unit tests is provided, plus additional methods to configure this
    49   * object as necessary.  Methods for unsupported operations will throw
    50   * <code>UnsupportedOperationException</code>.</p>
    51   *
    52   * <p><strong>WARNING</strong> - Because unit tests operate in a single
    53   * threaded environment, no synchronization is performed.</p>
    54   *
    55   * @version $Rev: 471754 $ $Date: 2005-05-07 12:45:39 -0400 (Sat, 07 May 2005)
    56   *          $
    57   */
    58  public class MockPageContext extends PageContext {
    59      // ----------------------------------------------------- Instance Variables
    60      protected ServletContext application = null;
    61      protected HashMap attributes = new HashMap(); // Page scope attributes
    62      protected ServletConfig config = null;
    63      protected ServletRequest request = null;
    64      protected ServletResponse response = null;
    65      protected HttpSession session = null;
    66      private boolean throwIOException;
    67      private boolean returnBodyContent;
    68  
    69      // ----------------------------------------------------------- Constructors
    70      public MockPageContext() {
    71          super();
    72      }
    73  
    74      public MockPageContext(ServletConfig config, ServletRequest request,
    75          ServletResponse response) {
    76          super();
    77          setValues(config, request, response);
    78      }
    79  
    80      /**
    81       * <p> Construct a new PageContext impl. </p>
    82       *
    83       * @param throwIOException Determines if the returned JspWriter should
    84       *                         throw an IOException on any method call.
    85       * @param returnBody       Determines if getOut() should return a new
    86       *                         <code>JspWriter</code> or a <code>BodyContent</code>.
    87       */
    88      public MockPageContext(boolean throwIOException, boolean returnBody) {
    89          this.throwIOException = throwIOException;
    90          this.returnBodyContent = returnBody;
    91      }
    92  
    93      private void checkAndThrow()
    94          throws IOException {
    95          if (throwIOException) {
    96              throw new IOException();
    97          }
    98      }
    99  
    100     // --------------------------------------------------------- Public Methods
    101     public void setValues(ServletConfig config, ServletRequest request,
    102         ServletResponse response) {
    103         this.config = config;
    104 
    105         if (config != null) {
    106             this.application = config.getServletContext();
    107         } else {
    108             this.application = null;
    109         }
    110 
    111         this.request = request;
    112         this.response = response;
    113 
    114         if (request != null) {
    115             session = ((HttpServletRequest) request).getSession(false);
    116         } else {
    117             this.session = null;
    118         }
    119     }
    120 
    121     // ---------------------------------------------------- PageContext Methods
    122     public Object findAttribute(String name) {
    123         Object value = getAttribute(name, PageContext.PAGE_SCOPE);
    124 
    125         if (value == null) {
    126             value = getAttribute(name, PageContext.REQUEST_SCOPE);
    127         }
    128 
    129         if (value == null) {
    130             value = getAttribute(name, PageContext.SESSION_SCOPE);
    131         }
    132 
    133         if (value == null) {
    134             value = getAttribute(name, PageContext.APPLICATION_SCOPE);
    135         }
    136 
    137         return (value);
    138     }
    139 
    140     public void forward(String path) {
    141         throw new UnsupportedOperationException();
    142     }
    143 
    144     public Object getAttribute(String name) {
    145         return (getAttribute(name, PageContext.PAGE_SCOPE));
    146     }
    147 
    148     public Object getAttribute(String name, int scope) {
    149         if (scope == PageContext.PAGE_SCOPE) {
    150             return (attributes.get(name));
    151         } else if (scope == PageContext.REQUEST_SCOPE) {
    152             if (request != null) {
    153                 return (request.getAttribute(name));
    154             }
    155 
    156             return (null);
    157         } else if (scope == PageContext.SESSION_SCOPE) {
    158             if (session != null) {
    159                 return (session.getAttribute(name));
    160             }
    161 
    162             return (null);
    163         } else if (scope == PageContext.APPLICATION_SCOPE) {
    164             if (application != null) {
    165                 return (application.getAttribute(name));
    166             }
    167 
    168             return (null);
    169         } else {
    170             throw new IllegalArgumentException("Invalid scope " + scope);
    171         }
    172     }
    173 
    174     public Enumeration getAttributeNamesInScope(int scope) {
    175         if (scope == PageContext.PAGE_SCOPE) {
    176             return (new MockEnumeration(attributes.keySet().iterator()));
    177         } else if (scope == PageContext.REQUEST_SCOPE) {
    178             if (request != null) {
    179                 return (request.getAttributeNames());
    180             }
    181 
    182             return (new MockEnumeration(Collections.EMPTY_LIST.iterator()));
    183         } else if (scope == PageContext.SESSION_SCOPE) {
    184             if (session != null) {
    185                 return (session.getAttributeNames());
    186             }
    187 
    188             return (new MockEnumeration(Collections.EMPTY_LIST.iterator()));
    189         } else if (scope == PageContext.APPLICATION_SCOPE) {
    190             if (application != null) {
    191                 return (application.getAttributeNames());
    192             }
    193 
    194             return new MockEnumeration(Collections.EMPTY_LIST.iterator());
    195         } else {
    196             throw new IllegalArgumentException("Invalid scope " + scope);
    197         }
    198     }
    199 
    200     public int getAttributesScope(String name) {
    201         if (attributes.get(name) != null) {
    202             return (PageContext.PAGE_SCOPE);
    203         } else if ((request != null) && (request.getAttribute(name) != null)) {
    204             return (PageContext.REQUEST_SCOPE);
    205         } else if ((session != null) && (session.getAttribute(name) != null)) {
    206             return (PageContext.SESSION_SCOPE);
    207         } else if ((application != null)
    208             && (application.getAttribute(name) != null)) {
    209             return (PageContext.APPLICATION_SCOPE);
    210         } else {
    211             return (0);
    212         }
    213     }
    214 
    215     public Exception getException() {
    216         throw new UnsupportedOperationException();
    217     }
    218 
    219     /**
    220      * <p> Custom JspWriter that throws the specified exception (supplied on
    221      * the constructor...if any), else it simply returns. </p>
    222      */
    223     public JspWriter getOut() {
    224         JspWriter jspWriter =
    225             new JspWriter(0, false) {
    226                 public void print(String s)
    227                     throws IOException {
    228                     checkAndThrow();
    229                 }
    230 
    231                 public void newLine()
    232                     throws IOException {
    233                     checkAndThrow();
    234                 }
    235 
    236                 public void print(boolean b)
    237                     throws IOException {
    238                     checkAndThrow();
    239                 }
    240 
    241                 public void print(char c)
    242                     throws IOException {
    243                     checkAndThrow();
    244                 }
    245 
    246                 public void print(int i)
    247                     throws IOException {
    248                     checkAndThrow();
    249                 }
    250 
    251                 public void print(long l)
    252                     throws IOException {
    253                     checkAndThrow();
    254                 }
    255 
    256                 public void print(float f)
    257                     throws IOException {
    258                     checkAndThrow();
    259                 }
    260 
    261                 public void print(double d)
    262                     throws IOException {
    263                     checkAndThrow();
    264                 }
    265 
    266                 public void print(char[] s)
    267                     throws IOException {
    268                     checkAndThrow();
    269                 }
    270 
    271                 public void print(Object obj)
    272                     throws IOException {
    273                     checkAndThrow();
    274                 }
    275 
    276                 public void println()
    277                     throws IOException {
    278                     checkAndThrow();
    279                 }
    280 
    281                 public void println(boolean x)
    282                     throws IOException {
    283                     checkAndThrow();
    284                 }
    285 
    286                 public void println(char x)
    287                     throws IOException {
    288                     checkAndThrow();
    289                 }
    290 
    291                 public void println(int x)
    292                     throws IOException {
    293                     checkAndThrow();
    294                 }
    295 
    296                 public void println(long x)
    297                     throws IOException {
    298                     checkAndThrow();
    299                 }
    300 
    301                 public void println(float x)
    302                     throws IOException {
    303                     checkAndThrow();
    304                 }
    305 
    306                 public void println(double x)
    307                     throws IOException {
    308                     checkAndThrow();
    309                 }
    310 
    311                 public void println(char[] x)
    312                     throws IOException {
    313                     checkAndThrow();
    314                 }
    315 
    316                 public void println(String x)
    317                     throws IOException {
    318                     checkAndThrow();
    319                 }
    320 
    321                 public void println(Object x)
    322                     throws IOException {
    323                     checkAndThrow();
    324                 }
    325 
    326                 public void clear()
    327                     throws IOException {
    328                     checkAndThrow();
    329                 }
    330 
    331                 public void clearBuffer()
    332                     throws IOException {
    333                     checkAndThrow();
    334                 }
    335 
    336                 public void flush()
    337                     throws IOException {
    338                     checkAndThrow();
    339                 }
    340 
    341                 public void close()
    342                     throws IOException {
    343                     checkAndThrow();
    344                 }
    345 
    346                 public int getRemaining() {
    347                     return 0;
    348                 }
    349 
    350                 public void write(char[] cbuf, int off, int len)
    351                     throws IOException {
    352                     checkAndThrow();
    353                 }
    354             };
    355 
    356         if (returnBodyContent) {
    357             return new BodyContent(jspWriter) {
    358                     public Reader getReader() {
    359                         return null;
    360                     }
    361 
    362                     public String getString() {
    363                         return null;
    364                     }
    365 
    366                     public void writeOut(Writer out)
    367                         throws IOException {
    368                         checkAndThrow();
    369                     }
    370 
    371                     public void newLine()
    372                         throws IOException {
    373                         checkAndThrow();
    374                     }
    375 
    376                     public void print(boolean b)
    377                         throws IOException {
    378                         checkAndThrow();
    379                     }
    380 
    381                     public void print(char c)
    382                         throws IOException {
    383                         checkAndThrow();
    384                     }
    385 
    386                     public void print(int i)
    387                         throws IOException {
    388                         checkAndThrow();
    389                     }
    390 
    391                     public void print(long l)
    392                         throws IOException {
    393                         checkAndThrow();
    394                     }
    395 
    396                     public void print(float f)
    397                         throws IOException {
    398                         checkAndThrow();
    399                     }
    400 
    401                     public void print(double d)
    402                         throws IOException {
    403                         checkAndThrow();
    404                     }
    405 
    406                     public void print(char[] s)
    407                         throws IOException {
    408                         checkAndThrow();
    409                     }
    410 
    411                     public void print(String s)
    412                         throws IOException {
    413                         checkAndThrow();
    414                     }
    415 
    416                     public void print(Object obj)
    417                         throws IOException {
    418                         checkAndThrow();
    419                     }
    420 
    421                     public void println()
    422                         throws IOException {
    423                         checkAndThrow();
    424                     }
    425 
    426                     public void println(boolean x)
    427                         throws IOException {
    428                         checkAndThrow();
    429                     }
    430 
    431                     public void println(char x)
    432                         throws IOException {
    433                         checkAndThrow();
    434                     }
    435 
    436                     public void println(int x)
    437                         throws IOException {
    438                         checkAndThrow();
    439                     }
    440 
    441                     public void println(long x)
    442                         throws IOException {
    443                         checkAndThrow();
    444                     }
    445 
    446                     public void println(float x)
    447                         throws IOException {
    448                         checkAndThrow();
    449                     }
    450 
    451                     public void println(double x)
    452                         throws IOException {
    453                         checkAndThrow();
    454                     }
    455 
    456                     public void println(char[] x)
    457                         throws IOException {
    458                         checkAndThrow();
    459                     }
    460 
    461                     public void println(String x)
    462                         throws IOException {
    463                         checkAndThrow();
    464                     }
    465 
    466                     public void println(Object x)
    467                         throws IOException {
    468                         checkAndThrow();
    469                     }
    470 
    471                     public void clear()
    472                         throws IOException {
    473                         checkAndThrow();
    474                     }
    475 
    476                     public void clearBuffer()
    477                         throws IOException {
    478                         checkAndThrow();
    479                     }
    480 
    481                     public void close()
    482                         throws IOException {
    483                         checkAndThrow();
    484                     }
    485 
    486                     public int getRemaining() {
    487                         return 0;
    488                     }
    489 
    490                     public void write(char[] cbuf, int off, int len)
    491                         throws IOException {
    492                         checkAndThrow();
    493                     }
    494                 };
    495         }
    496 
    497         return jspWriter;
    498     }
    499 
    500     public Object getPage() {
    501         throw new UnsupportedOperationException();
    502     }
    503 
    504     public ServletRequest getRequest() {
    505         return (this.request);
    506     }
    507 
    508     public ServletResponse getResponse() {
    509         return (this.response);
    510     }
    511 
    512     public ServletConfig getServletConfig() {
    513         return (this.config);
    514     }
    515 
    516     public ServletContext getServletContext() {
    517         return (this.application);
    518     }
    519 
    520     public HttpSession getSession() {
    521         return (this.session);
    522     }
    523 
    524     public void handlePageException(Exception e) {
    525         throw new UnsupportedOperationException();
    526     }
    527 
    528     public void handlePageException(Throwable t) {
    529         throw new UnsupportedOperationException();
    530     }
    531 
    532     public void include(String path) {
    533         throw new UnsupportedOperationException();
    534     }
    535 
    536     public void initialize(Servlet servlet, ServletRequest request,
    537         ServletResponse response, String errorPageURL, boolean needsSession,
    538         int bufferSize, boolean autoFlush) {
    539         throw new UnsupportedOperationException();
    540     }
    541 
    542     public JspWriter popBody() {
    543         throw new UnsupportedOperationException();
    544     }
    545 
    546     public BodyContent pushBody() {
    547         throw new UnsupportedOperationException();
    548     }
    549 
    550     public void release() {
    551         throw new UnsupportedOperationException();
    552     }
    553 
    554     public void removeAttribute(String name) {
    555         int scope = getAttributesScope(name);
    556 
    557         if (scope != 0) {
    558             removeAttribute(name, scope);
    559         }
    560     }
    561 
    562     public void removeAttribute(String name, int scope) {
    563         if (scope == PageContext.PAGE_SCOPE) {
    564             attributes.remove(name);
    565         } else if (scope == PageContext.REQUEST_SCOPE) {
    566             if (request != null) {
    567                 request.removeAttribute(name);
    568             }
    569         } else if (scope == PageContext.SESSION_SCOPE) {
    570             if (session != null) {
    571                 session.removeAttribute(name);
    572             }
    573         } else if (scope == PageContext.APPLICATION_SCOPE) {
    574             if (application != null) {
    575                 application.removeAttribute(name);
    576             }
    577         } else {
    578             throw new IllegalArgumentException("Invalid scope " + scope);
    579         }
    580     }
    581 
    582     public void setAttribute(String name, Object value) {
    583         setAttribute(name, value, PageContext.PAGE_SCOPE);
    584     }
    585 
    586     public void setAttribute(String name, Object value, int scope) {
    587         if (scope == PageContext.PAGE_SCOPE) {
    588             attributes.put(name, value);
    589         } else if (scope == PageContext.REQUEST_SCOPE) {
    590             if (request != null) {
    591                 request.setAttribute(name, value);
    592             }
    593         } else if (scope == PageContext.SESSION_SCOPE) {
    594             if (session != null) {
    595                 session.setAttribute(name, value);
    596             }
    597         } else if (scope == PageContext.APPLICATION_SCOPE) {
    598             if (application != null) {
    599                 application.setAttribute(name, value);
    600             }
    601         } else {
    602             throw new IllegalArgumentException("Invalid scope " + scope);
    603         }
    604     }
    605 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
