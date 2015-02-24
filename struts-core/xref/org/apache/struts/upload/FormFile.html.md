[View Javadoc](../../../../../apidocs/org/apache/struts/upload/FormFile.html.md)


    1   /*
    2    * $Id: FormFile.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.io.FileNotFoundException;
    24  import java.io.IOException;
    25  import java.io.InputStream;
    26  
    27  /**
    28   * <p> This interface represents a file that has been uploaded by a client. It
    29   * is the only interface or class in upload package which is typically
    30   * referenced directly by a Struts application. </p>
    31   */
    32  public interface FormFile {
    33      /**
    34       * <p> Returns the content type for this file. </p>
    35       *
    36       * @return A String representing content type.
    37       */
    38      public String getContentType();
    39  
    40      /**
    41       * <p> Sets the content type for this file. </p>
    42       *
    43       * @param contentType The content type for the file.
    44       */
    45      public void setContentType(String contentType);
    46  
    47      /**
    48       * <p> Returns the size of this file. </p>
    49       *
    50       * @return The size of the file, in bytes.
    51       */
    52      public int getFileSize();
    53  
    54      /**
    55       * <p> Sets the file size. </p>
    56       *
    57       * @param fileSize The size of the file, in bytes,
    58       */
    59      public void setFileSize(int fileSize);
    60  
    61      /**
    62       * <p> Returns the file name of this file. This is the base name of the
    63       * file, as supplied by the user when the file was uploaded. </p>
    64       *
    65       * @return The base file name.
    66       */
    67      public String getFileName();
    68  
    69      /**
    70       * <p> Sets the file name of this file. </p>
    71       *
    72       * @param fileName The base file name.
    73       */
    74      public void setFileName(String fileName);
    75  
    76      /**
    77       * <p> Returns the data for the entire file as byte array. Care is needed
    78       * when using this method, since a large upload could easily exhaust
    79       * available memory. The preferred method for accessing the file data is
    80       * {@link #getInputStream() getInputStream}. </p>
    81       *
    82       * @return The file data as a byte array.
    83       * @throws FileNotFoundException if the uploaded file is not found.
    84       * @throws IOException           if an error occurred while reading the
    85       *                               file.
    86       */
    87      public byte[] getFileData()
    88          throws FileNotFoundException, IOException;
    89  
    90      /**
    91       * <p> Returns an input stream for this file. The caller must close the
    92       * stream when it is no longer needed. </p>
    93       *
    94       * @throws FileNotFoundException if the uploaded file is not found.
    95       * @throws IOException           if an error occurred while reading the
    96       *                               file.
    97       */
    98      public InputStream getInputStream()
    99          throws FileNotFoundException, IOException;
    100 
    101     /**
    102      * <p> Destroys all content for the uploaded file, including any
    103      * underlying data files. </p>
    104      */
    105     public void destroy();
    106 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)