[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/upload/UploadAction.html.md)


    1   /*
    2    * $Id: UploadAction.java 471754 2006-11-06 14:55:09Z husted $
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
    24  
    25  import java.io.ByteArrayOutputStream;
    26  import java.io.FileNotFoundException;
    27  import java.io.FileOutputStream;
    28  import java.io.IOException;
    29  import java.io.InputStream;
    30  import java.io.OutputStream;
    31  
    32  import javax.servlet.http.HttpServletRequest;
    33  import javax.servlet.http.HttpServletResponse;
    34  
    35  import org.apache.struts.action.Action;
    36  import org.apache.struts.action.ActionForm;
    37  import org.apache.struts.action.ActionForward;
    38  import org.apache.struts.action.ActionMapping;
    39  import org.apache.struts.upload.FormFile;
    40  
    41  
    42  
    43  /**
    44   * This class takes the UploadForm and retrieves the text value
    45   * and file attributes and puts them in the request for the display.jsp
    46   * page to display them
    47   *
    48   * @author Mike Schachter
    49   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    50   */
    51  
    52  
    53  public class UploadAction extends Action
    54  {
    55      public ActionForward execute(ActionMapping mapping,
    56                                   ActionForm form,
    57                                   HttpServletRequest request,
    58                                   HttpServletResponse response)
    59          throws Exception {
    60  
    61          if (form instanceof UploadForm) {
    62  
    63              //this line is here for when the input page is upload-utf8.jsp,
    64              //it sets the correct character encoding for the response
    65              String encoding = request.getCharacterEncoding();
    66              if ((encoding != null) && (encoding.equalsIgnoreCase("utf-8")))
    67              {
    68                  response.setContentType("text.html.md; charset=utf-8");
    69              }
    70  
    71              UploadForm theForm = (UploadForm) form;
    72  
    73              //retrieve the text data
    74              String text = theForm.getTheText();
    75  
    76              //retrieve the query string value
    77              String queryValue = theForm.getQueryParam();
    78  
    79              //retrieve the file representation
    80              FormFile file = theForm.getTheFile();
    81  
    82              //retrieve the file name
    83              String fileName= file.getFileName();
    84  
    85              //retrieve the content type
    86              String contentType = file.getContentType();
    87  
    88              boolean writeFile = theForm.getWriteFile();
    89  
    90              //retrieve the file size
    91              String size = (file.getFileSize() + " bytes");
    92  
    93              String data = null;
    94  
    95              try {
    96                  //retrieve the file data
    97                  ByteArrayOutputStream baos = new ByteArrayOutputStream();
    98                  InputStream stream = file.getInputStream();
    99                  if (!writeFile) {
    100                     //only write files out that are less than 1MB
    101                     if (file.getFileSize() < (4*1024000)) {
    102 
    103                         byte[] buffer = new byte[8192];
    104                         int bytesRead = 0;
    105                         while ((bytesRead = stream.read(buffer, 0, 8192)) != -1) {
    106                             baos.write(buffer, 0, bytesRead);
    107                         }
    108                         data = new String(baos.toByteArray());
    109                     }
    110                     else {
    111                         data = new String("The file is greater than 4MB, " +
    112                                 " and has not been written to stream." +
    113                                 " File Size: " + file.getFileSize() + " bytes. This is a" +
    114                                 " limitation of this particular web application, hard-coded" +
    115                                 " in org.apache.struts.webapp.upload.UploadAction");
    116                     }
    117                 }
    118                 else {
    119                     //write the file to the file specified
    120                     OutputStream bos = new FileOutputStream(theForm.getFilePath());
    121                     int bytesRead = 0;
    122                     byte[] buffer = new byte[8192];
    123                     while ((bytesRead = stream.read(buffer, 0, 8192)) != -1) {
    124                         bos.write(buffer, 0, bytesRead);
    125                     }
    126                     bos.close();
    127                     data = "The file has been written to \"" + theForm.getFilePath() + "\"";
    128                 }
    129                 //close the stream
    130                 stream.close();
    131             }
    132             catch (FileNotFoundException fnfe) {
    133                 return null;
    134             }
    135             catch (IOException ioe) {
    136                 return null;
    137             }
    138 
    139             //place the data into the request for retrieval from display.jsp
    140             request.setAttribute("text", text);
    141             request.setAttribute("queryValue", queryValue);
    142             request.setAttribute("fileName", fileName);
    143             request.setAttribute("contentType", contentType);
    144             request.setAttribute("size", size);
    145             request.setAttribute("data", data);
    146 
    147             //destroy the temporary file created
    148             file.destroy();
    149 
    150             //return a forward to display.jsp
    151             return mapping.findForward("display");
    152         }
    153 
    154         //this shouldn't happen in this example
    155         return null;
    156     }
    157 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
