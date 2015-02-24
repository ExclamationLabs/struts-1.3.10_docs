[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockHttpServletResponse.html.md)


    1   /*
    2    * $Id: MockHttpServletResponse.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import javax.servlet.ServletOutputStream;
    24  import javax.servlet.http.Cookie;
    25  import javax.servlet.http.HttpServletResponse;
    26  
    27  import java.io.IOException;
    28  import java.io.PrintWriter;
    29  
    30  import java.util.Locale;
    31  
    32  /**
    33   * <p>Mock <strong>HttpServletResponse</strong> object for low-level unit
    34   * tests of Struts controller components.  Coarser grained tests should be
    35   * implemented in terms of the Cactus framework, instead of the mock object
    36   * classes.</p>
    37   *
    38   * <p><strong>WARNING</strong> - Only the minimal set of methods needed to
    39   * create unit tests is provided, plus additional methods to configure this
    40   * object as necessary.  Methods for unsupported operations will throw
    41   * <code>UnsupportedOperationException</code>.</p>
    42   *
    43   * <p><strong>WARNING</strong> - Because unit tests operate in a single
    44   * threaded environment, no synchronization is performed.</p>
    45   *
    46   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    47   *          $
    48   */
    49  public class MockHttpServletResponse implements HttpServletResponse {
    50      // ----------------------------------------------------- Instance Variables
    51      // --------------------------------------------------------- Public Methods
    52      // -------------------------------------------- HttpServletResponse Methods
    53      public void addCookie(Cookie cookie) {
    54          throw new UnsupportedOperationException();
    55      }
    56  
    57      public void addDateHeader(String name, long value) {
    58          throw new UnsupportedOperationException();
    59      }
    60  
    61      public void addHeader(String name, String value) {
    62          throw new UnsupportedOperationException();
    63      }
    64  
    65      public void addIntHeader(String name, int value) {
    66          throw new UnsupportedOperationException();
    67      }
    68  
    69      public boolean containsHeader(String name) {
    70          throw new UnsupportedOperationException();
    71      }
    72  
    73      public String encodeRedirectUrl(String url) {
    74          return (encodeRedirectURL(url));
    75      }
    76  
    77      public String encodeRedirectURL(String url) {
    78          return (url);
    79      }
    80  
    81      public String encodeUrl(String url) {
    82          return (encodeURL(url));
    83      }
    84  
    85      public String encodeURL(String url) {
    86          return (url);
    87      }
    88  
    89      public void sendError(int status) {
    90          throw new UnsupportedOperationException();
    91      }
    92  
    93      public void sendError(int status, String message) {
    94          throw new UnsupportedOperationException();
    95      }
    96  
    97      public void sendRedirect(String location) {
    98          throw new UnsupportedOperationException();
    99      }
    100 
    101     public void setDateHeader(String name, long value) {
    102         throw new UnsupportedOperationException();
    103     }
    104 
    105     public void setHeader(String name, String value) {
    106         throw new UnsupportedOperationException();
    107     }
    108 
    109     public void setIntHeader(String name, int value) {
    110         throw new UnsupportedOperationException();
    111     }
    112 
    113     public void setStatus(int status) {
    114         throw new UnsupportedOperationException();
    115     }
    116 
    117     public void setStatus(int status, String message) {
    118         throw new UnsupportedOperationException();
    119     }
    120 
    121     // ------------------------------------------------ ServletResponse Methods
    122     public void flushBuffer() {
    123         throw new UnsupportedOperationException();
    124     }
    125 
    126     public int getBufferSize() {
    127         throw new UnsupportedOperationException();
    128     }
    129 
    130     public String getCharacterEncoding() {
    131         throw new UnsupportedOperationException();
    132     }
    133 
    134     public Locale getLocale() {
    135         throw new UnsupportedOperationException();
    136     }
    137 
    138     public ServletOutputStream getOutputStream()
    139         throws IOException {
    140         throw new UnsupportedOperationException();
    141     }
    142 
    143     public PrintWriter getWriter()
    144         throws IOException {
    145         throw new UnsupportedOperationException();
    146     }
    147 
    148     public boolean isCommitted() {
    149         throw new UnsupportedOperationException();
    150     }
    151 
    152     public void reset() {
    153         throw new UnsupportedOperationException();
    154     }
    155 
    156     public void resetBuffer() {
    157         throw new UnsupportedOperationException();
    158     }
    159 
    160     public void setBufferSize(int size) {
    161         throw new UnsupportedOperationException();
    162     }
    163 
    164     public void setContentLength(int length) {
    165         throw new UnsupportedOperationException();
    166     }
    167 
    168     public void setContentType(String type) {
    169         throw new UnsupportedOperationException();
    170     }
    171 
    172     public void setLocale(Locale locale) {
    173         throw new UnsupportedOperationException();
    174     }
    175 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
