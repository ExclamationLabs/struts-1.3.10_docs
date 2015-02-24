[View Javadoc](../../../../../apidocs/org/apache/struts/actions/DownloadAction.html.md)


    1   /*
    2    * $Id: $
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
    21  package org.apache.struts.actions;
    22  
    23  import org.apache.struts.action.ActionForm;
    24  import org.apache.struts.action.ActionForward;
    25  import org.apache.struts.action.ActionMapping;
    26  
    27  import javax.servlet.ServletContext;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  
    31  import java.io.BufferedInputStream;
    32  import java.io.File;
    33  import java.io.FileInputStream;
    34  import java.io.IOException;
    35  import java.io.InputStream;
    36  import java.io.OutputStream;
    37  
    38  /**
    39   * This is an abstract base class that minimizes the amount of special coding
    40   * that needs to be written to download a file. All that is required to use
    41   * this class is to extend it and implement the <code>getStreamInfo()</code>
    42   * method so that it returns the relevant information for the file (or other
    43   * stream) to be downloaded. Optionally, the <code>getBufferSize()</code>
    44   * method may be overridden to customize the size of the buffer used to
    45   * transfer the file.
    46   *
    47   * @since Struts 1.2.6
    48   */
    49  public abstract class DownloadAction extends BaseAction {
    50      /**
    51       * If the <code>getBufferSize()</code> method is not overridden, this is
    52       * the buffer size that will be used to transfer the data to the servlet
    53       * output stream.
    54       */
    55      protected static final int DEFAULT_BUFFER_SIZE = 4096;
    56  
    57      /**
    58       * Returns the information on the file, or other stream, to be downloaded
    59       * by this action. This method must be implemented by an extending class.
    60       *
    61       * @param mapping  The ActionMapping used to select this instance.
    62       * @param form     The optional ActionForm bean for this request (if
    63       *                 any).
    64       * @param request  The HTTP request we are processing.
    65       * @param response The HTTP response we are creating.
    66       * @return The information for the file to be downloaded.
    67       * @throws Exception if an exception occurs.
    68       */
    69      protected abstract StreamInfo getStreamInfo(ActionMapping mapping,
    70          ActionForm form, HttpServletRequest request,
    71          HttpServletResponse response)
    72          throws Exception;
    73  
    74      /**
    75       * Returns the size of the buffer to be used in transferring the data to
    76       * the servlet output stream. This method may be overridden by an
    77       * extending class in order to customize the buffer size.
    78       *
    79       * @return The size of the transfer buffer, in bytes.
    80       */
    81      protected int getBufferSize() {
    82          return DEFAULT_BUFFER_SIZE;
    83      }
    84  
    85      /**
    86       * Process the specified HTTP request, and create the corresponding HTTP
    87       * response (or forward to another web component that will create it).
    88       * Return an <code>ActionForward</code> instance describing where and how
    89       * control should be forwarded, or <code>null</code> if the response has
    90       * already been completed.
    91       *
    92       * @param mapping  The ActionMapping used to select this instance.
    93       * @param form     The optional ActionForm bean for this request (if
    94       *                 any).
    95       * @param request  The HTTP request we are processing.
    96       * @param response The HTTP response we are creating.
    97       * @return The forward to which control should be transferred, or
    98       *         <code>null</code> if the response has been completed.
    99       * @throws Exception if an exception occurs.
    100      */
    101     public ActionForward execute(ActionMapping mapping, ActionForm form,
    102         HttpServletRequest request, HttpServletResponse response)
    103         throws Exception {
    104         StreamInfo info = getStreamInfo(mapping, form, request, response);
    105         String contentType = info.getContentType();
    106         InputStream stream = info.getInputStream();
    107 
    108         try {
    109             response.setContentType(contentType);
    110             copy(stream, response.getOutputStream());
    111         } finally {
    112             if (stream != null) {
    113                 stream.close();
    114             }
    115         }
    116 
    117         // Tell Struts that we are done with the response.
    118         return null;
    119     }
    120 
    121     /**
    122      * Copy bytes from an <code>InputStream</code> to an
    123      * <code>OutputStream</code>.
    124      *
    125      * @param input  The <code>InputStream</code> to read from.
    126      * @param output The <code>OutputStream</code> to write to.
    127      * @return the number of bytes copied
    128      * @throws IOException In case of an I/O problem
    129      */
    130     public int copy(InputStream input, OutputStream output)
    131         throws IOException {
    132         byte[] buffer = new byte[getBufferSize()];
    133         int count = 0;
    134         int n = 0;
    135 
    136         while (-1 != (n = input.read(buffer))) {
    137             output.write(buffer, 0, n);
    138             count += n;
    139         }
    140 
    141         return count;
    142     }
    143 
    144     /**
    145      * The information on a file, or other stream, to be downloaded by the
    146      * <code>DownloadAction</code>.
    147      */
    148     public static interface StreamInfo {
    149         /**
    150          * Returns the content type of the stream to be downloaded.
    151          *
    152          * @return The content type of the stream.
    153          */
    154         String getContentType();
    155 
    156         /**
    157          * Returns an input stream on the content to be downloaded. This
    158          * stream will be closed by the <code>DownloadAction</code>.
    159          *
    160          * @return The input stream for the content to be downloaded.
    161          * @throws IOException if an error occurs
    162          */
    163         InputStream getInputStream()
    164             throws IOException;
    165     }
    166 
    167     /**
    168      * A concrete implementation of the <code>StreamInfo</code> interface
    169      * which simplifies the downloading of a file from the disk.
    170      */
    171     public static class FileStreamInfo implements StreamInfo {
    172         /**
    173          * The content type for this stream.
    174          */
    175         private String contentType;
    176 
    177         /**
    178          * The file to be downloaded.
    179          */
    180         private File file;
    181 
    182         /**
    183          * Constructs an instance of this class, based on the supplied
    184          * parameters.
    185          *
    186          * @param contentType The content type of the file.
    187          * @param file        The file to be downloaded.
    188          */
    189         public FileStreamInfo(String contentType, File file) {
    190             this.contentType = contentType;
    191             this.file = file;
    192         }
    193 
    194         /**
    195          * Returns the content type of the stream to be downloaded.
    196          *
    197          * @return The content type of the stream.
    198          */
    199         public String getContentType() {
    200             return this.contentType;
    201         }
    202 
    203         /**
    204          * Returns an input stream on the file to be downloaded. This stream
    205          * will be closed by the <code>DownloadAction</code>.
    206          *
    207          * @return The input stream for the file to be downloaded.
    208          * @throws IOException if an error occurs
    209          */
    210         public InputStream getInputStream()
    211             throws IOException {
    212             FileInputStream fis = new FileInputStream(file);
    213             BufferedInputStream bis = new BufferedInputStream(fis);
    214 
    215             return bis;
    216         }
    217     }
    218 
    219     /**
    220      * A concrete implementation of the <code>StreamInfo</code> interface
    221      * which simplifies the downloading of a web application resource.
    222      */
    223     public static class ResourceStreamInfo implements StreamInfo {
    224         /**
    225          * The content type for this stream.
    226          */
    227         private String contentType;
    228 
    229         /**
    230          * The servlet context for the resource to be downloaded.
    231          */
    232         private ServletContext context;
    233 
    234         /**
    235          * The path to the resource to be downloaded.
    236          */
    237         private String path;
    238 
    239         /**
    240          * Constructs an instance of this class, based on the supplied
    241          * parameters.
    242          *
    243          * @param contentType The content type of the file.
    244          * @param context     The servlet context for the resource.
    245          * @param path        The path to the resource to be downloaded.
    246          */
    247         public ResourceStreamInfo(String contentType, ServletContext context,
    248             String path) {
    249             this.contentType = contentType;
    250             this.context = context;
    251             this.path = path;
    252         }
    253 
    254         /**
    255          * Returns the content type of the stream to be downloaded.
    256          *
    257          * @return The content type of the stream.
    258          */
    259         public String getContentType() {
    260             return this.contentType;
    261         }
    262 
    263         /**
    264          * Returns an input stream on the resource to be downloaded. This
    265          * stream will be closed by the <code>DownloadAction</code>.
    266          *
    267          * @return The input stream for the resource to be downloaded.
    268          * @throws IOException if an error occurs
    269          */
    270         public InputStream getInputStream()
    271             throws IOException {
    272             return context.getResourceAsStream(path);
    273         }
    274     }
    275 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
