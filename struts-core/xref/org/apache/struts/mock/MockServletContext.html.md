[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockServletContext.html.md)


    1   /*
    2    * $Id: MockServletContext.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  
    26  import javax.servlet.RequestDispatcher;
    27  import javax.servlet.Servlet;
    28  import javax.servlet.ServletContext;
    29  
    30  import java.io.InputStream;
    31  
    32  import java.net.URL;
    33  
    34  import java.util.Enumeration;
    35  import java.util.HashMap;
    36  import java.util.Set;
    37  
    38  /**
    39   * <p>Mock <strong>ServletContext</strong> object for low-level unit tests of
    40   * Struts controller components.  Coarser grained tests should be implemented
    41   * in terms of the Cactus framework, instead of the mock object classes.</p>
    42   *
    43   * <p><strong>WARNING</strong> - Only the minimal set of methods needed to
    44   * create unit tests is provided, plus additional methods to configure this
    45   * object as necessary.  Methods for unsupported operations will throw
    46   * <code>UnsupportedOperationException</code>.</p>
    47   *
    48   * <p><strong>WARNING</strong> - Because unit tests operate in a single
    49   * threaded environment, no synchronization is performed.</p>
    50   *
    51   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    52   *          $
    53   */
    54  public class MockServletContext implements ServletContext {
    55      // ----------------------------------------------------- Instance Variables
    56  
    57      /**
    58       * <p> The set of servlet context attributes. </p>
    59       */
    60      protected HashMap attributes = new HashMap();
    61  
    62      /**
    63       * <p> Default destination for <code>LOG()</code> output. </p>
    64       */
    65      protected Log log = LogFactory.getLog(MockServletContext.class);
    66  
    67      /**
    68       * <p> The set of context initialization parameters. </p>
    69       */
    70      protected HashMap parameters = new HashMap();
    71  
    72      // --------------------------------------------------------- Public Methods
    73      public void addInitParameter(String name, String value) {
    74          parameters.put(name, value);
    75      }
    76  
    77      public void setLog(Log log) {
    78          this.log = log;
    79      }
    80  
    81      // ------------------------------------------------- ServletContext Methods
    82      public Object getAttribute(String name) {
    83          return (attributes.get(name));
    84      }
    85  
    86      public Enumeration getAttributeNames() {
    87          return (new MockEnumeration(attributes.keySet().iterator()));
    88      }
    89  
    90      public ServletContext getContext(String uripath) {
    91          throw new UnsupportedOperationException();
    92      }
    93  
    94      public String getInitParameter(String name) {
    95          return ((String) parameters.get(name));
    96      }
    97  
    98      public Enumeration getInitParameterNames() {
    99          return (new MockEnumeration(parameters.keySet().iterator()));
    100     }
    101 
    102     public int getMajorVersion() {
    103         return (2);
    104     }
    105 
    106     public String getMimeType(String file) {
    107         throw new UnsupportedOperationException();
    108     }
    109 
    110     public int getMinorVersion() {
    111         return (3);
    112     }
    113 
    114     public RequestDispatcher getNamedDispatcher(String name) {
    115         throw new UnsupportedOperationException();
    116     }
    117 
    118     public String getRealPath(String path) {
    119         throw new UnsupportedOperationException();
    120     }
    121 
    122     public RequestDispatcher getRequestDispatcher(String path) {
    123         throw new UnsupportedOperationException();
    124     }
    125 
    126     public URL getResource(String path) {
    127         return this.getClass().getResource(path);
    128 
    129         //throw new UnsupportedOperationException();
    130     }
    131 
    132     public InputStream getResourceAsStream(String path) {
    133         return this.getClass().getResourceAsStream(path);
    134 
    135         //throw new UnsupportedOperationException();
    136     }
    137 
    138     public Set getResourcePaths(String path) {
    139         throw new UnsupportedOperationException();
    140     }
    141 
    142     public String getServerInfo() {
    143         return ("MockServletContext/$Version$");
    144     }
    145 
    146     public Servlet getServlet(String name) {
    147         throw new UnsupportedOperationException();
    148     }
    149 
    150     public String getServletContextName() {
    151         return (getServerInfo());
    152     }
    153 
    154     public Enumeration getServletNames() {
    155         throw new UnsupportedOperationException();
    156     }
    157 
    158     public Enumeration getServlets() {
    159         throw new UnsupportedOperationException();
    160     }
    161 
    162     public void log(Exception exception, String message) {
    163         log(message, exception);
    164     }
    165 
    166     public void log(String message) {
    167         log.info(message);
    168     }
    169 
    170     public void log(String message, Throwable throwable) {
    171         log.error(message, throwable);
    172     }
    173 
    174     public void removeAttribute(String name) {
    175         attributes.remove(name);
    176     }
    177 
    178     public void setAttribute(String name, Object value) {
    179         if (value == null) {
    180             attributes.remove(name);
    181         } else {
    182             attributes.put(name, value);
    183         }
    184     }
    185 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
