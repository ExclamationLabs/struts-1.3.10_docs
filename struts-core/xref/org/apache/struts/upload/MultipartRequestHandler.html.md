[View Javadoc](../../../../../apidocs/org/apache/struts/upload/MultipartRequestHandler.html.md)


    1   /*
    2    * $Id: MultipartRequestHandler.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.action.ActionMapping;
    24  import org.apache.struts.action.ActionServlet;
    25  
    26  import javax.servlet.ServletException;
    27  import javax.servlet.http.HttpServletRequest;
    28  
    29  import java.util.Hashtable;
    30  
    31  /**
    32   * <p> MultipartRequestHandler provides an standard interface for struts to
    33   * deal with file uploads from forms with enctypes of "multipart/form-data".
    34   * Providers must provide a no-argument constructor for initialization. </p>
    35   */
    36  public interface MultipartRequestHandler {
    37      /**
    38       * <p> This is the ServletRequest attribute that should be set when a
    39       * multipart request is being read and the maximum length is exceeded. The
    40       * value is a Boolean. If the maximum length isn't exceeded, this
    41       * attribute shouldn't be put in the ServletRequest. It's the job of the
    42       * implementation to put this attribute in the request if the maximum
    43       * length is exceeded; in the handleRequest(HttpServletRequest) method.
    44       * </p>
    45       */
    46      public static final String ATTRIBUTE_MAX_LENGTH_EXCEEDED =
    47          "org.apache.struts.upload.MaxLengthExceeded";
    48  
    49      /**
    50       * <p> Convienience method to set a reference to a working ActionServlet
    51       * instance. </p>
    52       */
    53      public void setServlet(ActionServlet servlet);
    54  
    55      /**
    56       * <p> Convienience method to set a reference to a working ActionMapping
    57       * instance. </p>
    58       */
    59      public void setMapping(ActionMapping mapping);
    60  
    61      /**
    62       * <p> Get the ActionServlet instance </p>
    63       */
    64      public ActionServlet getServlet();
    65  
    66      /**
    67       * <p> Get the ActionMapping instance for this request </p>
    68       */
    69      public ActionMapping getMapping();
    70  
    71      /**
    72       * <p> After constructed, this is the first method called on by
    73       * ActionServlet. Use this method for all your data-parsing of the
    74       * ServletInputStream in the request </p>
    75       *
    76       * @throws ServletException thrown if something goes wrong
    77       */
    78      public void handleRequest(HttpServletRequest request)
    79          throws ServletException;
    80  
    81      /**
    82       * <p> This method is called on to retrieve all the text input elements of
    83       * the request. </p>
    84       *
    85       * @return A Hashtable where the keys and values are the names and values
    86       *         of the request input parameters
    87       */
    88      public Hashtable getTextElements();
    89  
    90      /**
    91       * <p> This method is called on to retrieve all the FormFile input
    92       * elements of the request. </p>
    93       *
    94       * @return A Hashtable where the keys are the input names of the files and
    95       *         the values are FormFile objects
    96       * @see FormFile
    97       */
    98      public Hashtable getFileElements();
    99  
    100     /**
    101      * <p> This method returns all elements of a multipart request. </p>
    102      *
    103      * @return A Hashtable where the keys are input names and values are
    104      *         either String arrays or FormFiles
    105      */
    106     public Hashtable getAllElements();
    107 
    108     /**
    109      * <p> This method is called on when there's some sort of problem and the
    110      * form post needs to be rolled back.  Providers should remove any
    111      * FormFiles used to hold information by setting them to null and also
    112      * physically delete them if the implementation calls for writing directly
    113      * to disk. NOTE: Currently implemented but not automatically supported,
    114      * ActionForm implementors must call rollback() manually for rolling back
    115      * file uploads. </p>
    116      */
    117     public void rollback();
    118 
    119     /**
    120      * <p> This method is called on when a successful form post has been made.
    121      * Some implementations will use this to destroy temporary files or write
    122      * to a database or something of that nature. </p>
    123      */
    124     public void finish();
    125 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
