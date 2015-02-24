[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockHttpSession.html.md)


    1   /*
    2    * $Id: MockHttpSession.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import javax.servlet.ServletContext;
    24  import javax.servlet.http.HttpSession;
    25  import javax.servlet.http.HttpSessionContext;
    26  
    27  import java.util.Enumeration;
    28  import java.util.HashMap;
    29  
    30  /**
    31   * <p>Mock <strong>HttpSession</strong> object for low-level unit tests of
    32   * Struts controller components.  Coarser grained tests should be implemented
    33   * in terms of the Cactus framework, instead of the mock object classes.</p>
    34   *
    35   * <p><strong>WARNING</strong> - Only the minimal set of methods needed to
    36   * create unit tests is provided, plus additional methods to configure this
    37   * object as necessary.  Methods for unsupported operations will throw
    38   * <code>UnsupportedOperationException</code>.</p>
    39   *
    40   * <p><strong>WARNING</strong> - Because unit tests operate in a single
    41   * threaded environment, no synchronization is performed.</p>
    42   *
    43   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    44   *          $
    45   */
    46  public class MockHttpSession implements HttpSession {
    47      // ----------------------------------------------------- Instance Variables
    48  
    49      /**
    50       * <p> The set of session attributes. </p>
    51       */
    52      protected HashMap attributes = new HashMap();
    53  
    54      /**
    55       * <p> The ServletContext with which we are associated. </p>
    56       */
    57      protected ServletContext servletContext = null;
    58  
    59      // ----------------------------------------------------------- Constructors
    60      public MockHttpSession() {
    61          super();
    62      }
    63  
    64      public MockHttpSession(ServletContext servletContext) {
    65          super();
    66          setServletContext(servletContext);
    67      }
    68  
    69      // --------------------------------------------------------- Public Methods
    70      public void setServletContext(ServletContext servletContext) {
    71          this.servletContext = servletContext;
    72      }
    73  
    74      // ---------------------------------------------------- HttpSession Methods
    75      public Object getAttribute(String name) {
    76          return (attributes.get(name));
    77      }
    78  
    79      public Enumeration getAttributeNames() {
    80          return (new MockEnumeration(attributes.keySet().iterator()));
    81      }
    82  
    83      public long getCreationTime() {
    84          throw new UnsupportedOperationException();
    85      }
    86  
    87      public String getId() {
    88          throw new UnsupportedOperationException();
    89      }
    90  
    91      public long getLastAccessedTime() {
    92          throw new UnsupportedOperationException();
    93      }
    94  
    95      public int getMaxInactiveInterval() {
    96          throw new UnsupportedOperationException();
    97      }
    98  
    99      public ServletContext getServletContext() {
    100         return (this.servletContext);
    101     }
    102 
    103     public HttpSessionContext getSessionContext() {
    104         throw new UnsupportedOperationException();
    105     }
    106 
    107     public Object getValue(String name) {
    108         throw new UnsupportedOperationException();
    109     }
    110 
    111     public String[] getValueNames() {
    112         throw new UnsupportedOperationException();
    113     }
    114 
    115     public void invalidate() {
    116         throw new UnsupportedOperationException();
    117     }
    118 
    119     public boolean isNew() {
    120         throw new UnsupportedOperationException();
    121     }
    122 
    123     public void putValue(String name, Object value) {
    124         throw new UnsupportedOperationException();
    125     }
    126 
    127     public void removeAttribute(String name) {
    128         attributes.remove(name);
    129     }
    130 
    131     public void removeValue(String name) {
    132         throw new UnsupportedOperationException();
    133     }
    134 
    135     public void setAttribute(String name, Object value) {
    136         if (value == null) {
    137             attributes.remove(name);
    138         } else {
    139             attributes.put(name, value);
    140         }
    141     }
    142 
    143     public void setMaxInactiveInterval(int interval) {
    144         throw new UnsupportedOperationException();
    145     }
    146 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
