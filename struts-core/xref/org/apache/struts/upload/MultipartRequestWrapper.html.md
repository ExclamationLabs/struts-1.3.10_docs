[View Javadoc](../../../../../apidocs/org/apache/struts/upload/MultipartRequestWrapper.html.md)


    1   /*
    2    * $Id: MultipartRequestWrapper.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.upload;
    22  
    23  import javax.servlet.http.HttpServletRequest;
    24  import javax.servlet.http.HttpServletRequestWrapper;
    25  
    26  import java.util.Collection;
    27  import java.util.Collections;
    28  import java.util.Enumeration;
    29  import java.util.HashMap;
    30  import java.util.Iterator;
    31  import java.util.Map;
    32  import java.util.Vector;
    33  
    34  /**
    35   * <p> This class functions as a wrapper around HttpServletRequest to provide
    36   * working getParameter methods for multipart requests. </p>
    37   */
    38  public class MultipartRequestWrapper extends HttpServletRequestWrapper {
    39      /**
    40       * <p> The parameters for this multipart request </p>
    41       */
    42      protected Map parameters;
    43  
    44      public MultipartRequestWrapper(HttpServletRequest request) {
    45          super(request);
    46          this.parameters = new HashMap();
    47      }
    48  
    49      /**
    50       * <p> Sets a parameter for this request.  The parameter is actually
    51       * separate from the request parameters, but calling on the getParameter()
    52       * methods of this class will work as if they weren't. </p>
    53       */
    54      public void setParameter(String name, String value) {
    55          String[] mValue = (String[]) parameters.get(name);
    56  
    57          if (mValue == null) {
    58              mValue = new String[0];
    59          }
    60  
    61          String[] newValue = new String[mValue.length + 1];
    62  
    63          System.arraycopy(mValue, 0, newValue, 0, mValue.length);
    64          newValue[mValue.length] = value;
    65  
    66          parameters.put(name, newValue);
    67      }
    68  
    69      /**
    70       * <p> Attempts to get a parameter for this request.  It first looks in
    71       * the underlying HttpServletRequest object for the parameter, and if that
    72       * doesn't exist it looks for the parameters retrieved from the multipart
    73       * request </p>
    74       */
    75      public String getParameter(String name) {
    76          String value = getRequest().getParameter(name);
    77  
    78          if (value == null) {
    79              String[] mValue = (String[]) parameters.get(name);
    80  
    81              if ((mValue != null) && (mValue.length > 0)) {
    82                  value = mValue[0];
    83              }
    84          }
    85  
    86          return value;
    87      }
    88  
    89      /**
    90       * <p> Returns the names of the parameters for this request. The
    91       * enumeration consists of the normal request parameter names plus the
    92       * parameters read from the multipart request </p>
    93       */
    94      public Enumeration getParameterNames() {
    95          Enumeration baseParams = getRequest().getParameterNames();
    96          Vector list = new Vector();
    97  
    98          while (baseParams.hasMoreElements()) {
    99              list.add(baseParams.nextElement());
    100         }
    101 
    102         Collection multipartParams = parameters.keySet();
    103         Iterator iterator = multipartParams.iterator();
    104 
    105         while (iterator.hasNext()) {
    106             list.add(iterator.next());
    107         }
    108 
    109         return Collections.enumeration(list);
    110     }
    111 
    112     /**
    113      * <p> Returns the values of a parameter in this request. It first looks
    114      * in the underlying HttpServletRequest object for the parameter, and if
    115      * that doesn't exist it looks for the parameter retrieved from the
    116      * multipart request. </p>
    117      */
    118     public String[] getParameterValues(String name) {
    119         String[] value = getRequest().getParameterValues(name);
    120 
    121         if (value == null) {
    122             value = (String[]) parameters.get(name);
    123         }
    124 
    125         return value;
    126     }
    127 
    128     /**
    129      * <p> Combines the parameters stored here with those in the underlying
    130      * request. If paramater values in the underlying request take precedence
    131      * over those stored here. </p>
    132      */
    133     public Map getParameterMap() {
    134         Map map = new HashMap(parameters);
    135 
    136         map.putAll(getRequest().getParameterMap());
    137 
    138         return map;
    139     }
    140 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
