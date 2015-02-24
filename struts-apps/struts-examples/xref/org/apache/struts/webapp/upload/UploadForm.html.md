[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/upload/UploadForm.html.md)


    1   /*
    2    * $Id: UploadForm.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.webapp.upload;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  
    26  import org.apache.struts.action.ActionMapping;
    27  import org.apache.struts.action.ActionMessage;
    28  import org.apache.struts.action.ActionMessages;
    29  import org.apache.struts.action.ActionErrors;
    30  import org.apache.struts.validator.ValidatorForm;
    31  import org.apache.struts.upload.FormFile;
    32  import org.apache.struts.upload.MultipartRequestHandler;
    33  
    34  /**
    35   * This class is a placeholder for form values.  In a multipart request, files are represented by
    36   * set and get methods that use the class org.apache.struts.upload.FormFile, an interface with
    37   * basic methods to retrieve file information.  The actual structure of the FormFile is dependant
    38   * on the underlying impelementation of multipart request handling.  The default implementation
    39   * that struts uses is org.apache.struts.upload.CommonsMultipartRequestHandler.
    40   *
    41   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    42   */
    43  public class UploadForm extends ValidatorForm {
    44  
    45      /**
    46       * The value of the text the user has sent as form data
    47       */
    48      protected String theText;
    49  
    50      /**
    51       * The value of the embedded query string parameter
    52       */
    53      protected String queryParam;
    54  
    55      /**
    56       * Whether or not to write to a file
    57       */
    58      protected boolean writeFile;
    59  
    60      /**
    61       * The file that the user has uploaded
    62       */
    63      protected FormFile theFile;
    64  
    65      /**
    66       * The file path to write to
    67       */
    68      protected String filePath;
    69  
    70      /**
    71       * Retrieve the value of the text the user has sent as form data
    72       */
    73      public String getTheText() {
    74          return theText;
    75      }
    76  
    77      /**
    78       * Set the value of the form data text
    79       */
    80      public void setTheText(String theText) {
    81          this.theText = theText;
    82      }
    83  
    84      /**
    85       * Retrieve the value of the query string parameter
    86       */
    87      public String getQueryParam() {
    88          return queryParam;
    89      }
    90  
    91      /**
    92       * Set the value of the query string parameter
    93       */
    94      public void setQueryParam(String queryParam) {
    95          this.queryParam = queryParam;
    96      }
    97  
    98      /**
    99       * Retrieve a representation of the file the user has uploaded
    100      */
    101     public FormFile getTheFile() {
    102         return theFile;
    103     }
    104 
    105     /**
    106      * Set a representation of the file the user has uploaded
    107      */
    108     public void setTheFile(FormFile theFile) {
    109         this.theFile = theFile;
    110     }
    111 
    112     /**
    113      * Set whether or not to write to a file
    114      */
    115     public void setWriteFile(boolean writeFile) {
    116         this.writeFile = writeFile;
    117     }
    118 
    119     /**
    120      * Get whether or not to write to a file
    121      */
    122     public boolean getWriteFile() {
    123         return writeFile;
    124     }
    125 
    126     /**
    127      * Set the path to write a file to
    128      */
    129     public void setFilePath(String filePath) {
    130         this.filePath = filePath;
    131     }
    132 
    133     /**
    134      * Get the path to write a file to
    135      */
    136     public String getFilePath() {
    137         return filePath;
    138     }
    139 
    140     public void reset() {
    141         writeFile = false;
    142     }
    143 
    144     /**
    145      * Check to make sure the client hasn't exceeded the maximum allowed upload size inside of this
    146      * validate method.
    147      */
    148     public ActionErrors validate(
    149         ActionMapping mapping,
    150         HttpServletRequest request) {
    151 
    152         ActionErrors errors = super.validate(mapping, request);
    153 
    154         //has the maximum length been exceeded?
    155         Boolean maxLengthExceeded =
    156             (Boolean) request.getAttribute(
    157                 MultipartRequestHandler.ATTRIBUTE_MAX_LENGTH_EXCEEDED);
    158 
    159         if ((maxLengthExceeded != null) && (maxLengthExceeded.booleanValue())) {
    160             if (errors == null) {
    161                 errors = new ActionErrors();
    162             }
    163             errors.add(
    164                 ActionMessages.GLOBAL_MESSAGE ,
    165                 new ActionMessage("maxLengthExceeded"));
    166             errors.add(
    167                 ActionMessages.GLOBAL_MESSAGE ,
    168                 new ActionMessage("maxLengthExplanation"));
    169         }
    170         return errors;
    171 
    172     }
    173 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
