[View Javadoc](../../../../../apidocs/org/apache/struts/mock/MockMultipartRequestHandler.html.md)


    1   /*
    2    * $Id: MockMultipartRequestHandler.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.mock;
    23  
    24  import java.util.Enumeration;
    25  import java.util.Hashtable;
    26  import javax.servlet.ServletException;
    27  import javax.servlet.http.HttpServletRequest;
    28  import org.apache.struts.action.ActionServlet;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.upload.MultipartRequestHandler;
    31  
    32  /**
    33   * <p>Mock <strong>MultipartRequestHandler</strong> object for unit tests.</p>
    34   *
    35   * @version $Rev: 471754 $
    36   */
    37  public class MockMultipartRequestHandler implements MultipartRequestHandler {
    38  
    39      /** mock ActionServlet instance. */
    40      private ActionServlet servlet;
    41  
    42      /** mock ActionMapping instance. */
    43      private ActionMapping mapping = new ActionMapping();
    44  
    45      /** request elements. */
    46      private Hashtable elements;
    47  
    48      /**
    49       * Convienience method to set a reference to a mock
    50       * ActionServlet instance.
    51       * @param servlet Mock servlet instance.
    52       */
    53      public void setServlet(ActionServlet servlet) {
    54          this.servlet = servlet;
    55      }
    56  
    57      /**
    58       * Convienience method to set a reference to a mock
    59       * ActionMapping instance.
    60       * @param mapping Mock action mapping instance.
    61       */
    62      public void setMapping(ActionMapping mapping) {
    63          this.mapping = mapping;
    64      }
    65  
    66      /**
    67       * Get the mock ActionServlet instance.
    68       * @return The mock servlet instance.
    69       */
    70      public ActionServlet getServlet() {
    71          return this.servlet;
    72      }
    73  
    74      /**
    75       * Get the ActionMapping instance for this mock request.
    76       * @return The mock action mapping instance.
    77       */
    78      public ActionMapping getMapping() {
    79          return this.mapping;
    80      }
    81  
    82      /**
    83        * <p>Mock parsing of the ServletInputStream.</p>
    84        *
    85        * <p>Constructs a <code>Hashtable</code> of elements
    86        *    from the HttpServletRequest's parameters - no
    87        *    <code>FormFile</code> elements are created.</p>
    88        * @param request Mock request instance.
    89        * @throws ServletException If there is a problem with
    90        * processing the request.
    91        */
    92      public void handleRequest(HttpServletRequest request) throws ServletException {
    93          elements = new Hashtable();
    94          Enumeration enumer = request.getParameterNames();
    95          while (enumer.hasMoreElements()) {
    96              String key = enumer.nextElement().toString();
    97              elements.put(key, request.getParameter(key));
    98          }
    99      }
    100 
    101     /**
    102      * This method is called on to retrieve all the text
    103      * input elements of the request.
    104      *
    105      * @return A Hashtable where the keys and values are the names and
    106      *  values of the request input parameters
    107      */
    108     public Hashtable getTextElements() {
    109         return this.elements;
    110     }
    111 
    112     /**
    113      * <p>This method is called on to retrieve all the FormFile
    114      * input elements of the request.</p>
    115      *
    116      * @return This mock implementation returns an empty
    117      *    <code>Hashtable</code>
    118      */
    119     public Hashtable getFileElements() {
    120         return new Hashtable();
    121     }
    122 
    123     /**
    124      * This method returns all elements of a multipart request.
    125      * @return This mock implementation returns a Hashtable where
    126      *   the keys are input names and values are either Strings
    127      *   (no FormFile elements)
    128      */
    129     public Hashtable getAllElements() {
    130         return this.elements;
    131     }
    132 
    133     /**
    134      * Mock <code>rollback()</code> method does nothing.
    135      */
    136     public void rollback() {
    137         // ignore
    138     }
    139 
    140     /**
    141      * Mock <code>finish()</code> method does nothing.
    142      */
    143     public void finish() {
    144         // ignore
    145     }
    146 
    147 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
