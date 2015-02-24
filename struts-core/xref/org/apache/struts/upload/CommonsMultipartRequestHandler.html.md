[View Javadoc](../../../../../apidocs/org/apache/struts/upload/CommonsMultipartRequestHandler.html.md)


    1   /*
    2    * $Id: CommonsMultipartRequestHandler.java 524895 2007-04-02 19:29:21Z germuska $
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
    23  import org.apache.commons.fileupload.DiskFileUpload;
    24  import org.apache.commons.fileupload.disk.DiskFileItem;
    25  import org.apache.commons.fileupload.FileItem;
    26  import org.apache.commons.fileupload.FileUploadException;
    27  import org.apache.commons.logging.Log;
    28  import org.apache.commons.logging.LogFactory;
    29  import org.apache.struts.Globals;
    30  import org.apache.struts.action.ActionMapping;
    31  import org.apache.struts.action.ActionServlet;
    32  import org.apache.struts.config.ModuleConfig;
    33  
    34  import javax.servlet.ServletContext;
    35  import javax.servlet.ServletException;
    36  import javax.servlet.http.HttpServletRequest;
    37  
    38  import java.io.File;
    39  import java.io.FileNotFoundException;
    40  import java.io.IOException;
    41  import java.io.InputStream;
    42  import java.io.Serializable;
    43  
    44  import java.util.ArrayList;
    45  import java.util.Hashtable;
    46  import java.util.Iterator;
    47  import java.util.List;
    48  
    49  /**
    50   * <p> This class implements the <code>MultipartRequestHandler</code>
    51   * interface by providing a wrapper around the Jakarta Commons FileUpload
    52   * library. </p>
    53   *
    54   * @version $Rev: 524895 $ $Date: 2007-04-02 14:29:21 -0500 (Mon, 02 Apr 2007) $
    55   * @since Struts 1.1
    56   */
    57  public class CommonsMultipartRequestHandler implements MultipartRequestHandler {
    58      // ----------------------------------------------------- Manifest Constants
    59  
    60      /**
    61       * <p> The default value for the maximum allowable size, in bytes, of an
    62       * uploaded file. The value is equivalent to 250MB. </p>
    63       */
    64      public static final long DEFAULT_SIZE_MAX = 250 * 1024 * 1024;
    65  
    66      /**
    67       * <p> The default value for the threshold which determines whether an
    68       * uploaded file will be written to disk or cached in memory. The value is
    69       * equivalent to 250KB. </p>
    70       */
    71      public static final int DEFAULT_SIZE_THRESHOLD = 256 * 1024;
    72  
    73      // ----------------------------------------------------- Instance Variables
    74  
    75      /**
    76       * <p> Commons Logging instance. </p>
    77       */
    78      protected static Log log =
    79          LogFactory.getLog(CommonsMultipartRequestHandler.class);
    80  
    81      /**
    82       * <p> The combined text and file request parameters. </p>
    83       */
    84      private Hashtable elementsAll;
    85  
    86      /**
    87       * <p> The file request parameters. </p>
    88       */
    89      private Hashtable elementsFile;
    90  
    91      /**
    92       * <p> The text request parameters. </p>
    93       */
    94      private Hashtable elementsText;
    95  
    96      /**
    97       * <p> The action mapping  with which this handler is associated. </p>
    98       */
    99      private ActionMapping mapping;
    100 
    101     /**
    102      * <p> The servlet with which this handler is associated. </p>
    103      */
    104     private ActionServlet servlet;
    105 
    106     // ---------------------------------------- MultipartRequestHandler Methods
    107 
    108     /**
    109      * <p> Retrieves the servlet with which this handler is associated. </p>
    110      *
    111      * @return The associated servlet.
    112      */
    113     public ActionServlet getServlet() {
    114         return this.servlet;
    115     }
    116 
    117     /**
    118      * <p> Sets the servlet with which this handler is associated. </p>
    119      *
    120      * @param servlet The associated servlet.
    121      */
    122     public void setServlet(ActionServlet servlet) {
    123         this.servlet = servlet;
    124     }
    125 
    126     /**
    127      * <p> Retrieves the action mapping with which this handler is associated.
    128      * </p>
    129      *
    130      * @return The associated action mapping.
    131      */
    132     public ActionMapping getMapping() {
    133         return this.mapping;
    134     }
    135 
    136     /**
    137      * <p> Sets the action mapping with which this handler is associated.
    138      * </p>
    139      *
    140      * @param mapping The associated action mapping.
    141      */
    142     public void setMapping(ActionMapping mapping) {
    143         this.mapping = mapping;
    144     }
    145 
    146     /**
    147      * <p> Parses the input stream and partitions the parsed items into a set
    148      * of form fields and a set of file items. In the process, the parsed
    149      * items are translated from Commons FileUpload <code>FileItem</code>
    150      * instances to Struts <code>FormFile</code> instances. </p>
    151      *
    152      * @param request The multipart request to be processed.
    153      * @throws ServletException if an unrecoverable error occurs.
    154      */
    155     public void handleRequest(HttpServletRequest request)
    156         throws ServletException {
    157         // Get the app config for the current request.
    158         ModuleConfig ac =
    159             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    160 
    161         // Create and configure a DIskFileUpload instance.
    162         DiskFileUpload upload = new DiskFileUpload();
    163 
    164         // The following line is to support an "EncodingFilter"
    165         // see http://issues.apache.org/bugzilla/show_bug.cgi?id=23255
    166         upload.setHeaderEncoding(request.getCharacterEncoding());
    167 
    168         // Set the maximum size before a FileUploadException will be thrown.
    169         upload.setSizeMax(getSizeMax(ac));
    170 
    171         // Set the maximum size that will be stored in memory.
    172         upload.setSizeThreshold((int) getSizeThreshold(ac));
    173 
    174         // Set the the location for saving data on disk.
    175         upload.setRepositoryPath(getRepositoryPath(ac));
    176 
    177         // Create the hash tables to be populated.
    178         elementsText = new Hashtable();
    179         elementsFile = new Hashtable();
    180         elementsAll = new Hashtable();
    181 
    182         // Parse the request into file items.
    183         List items = null;
    184 
    185         try {
    186             items = upload.parseRequest(request);
    187         } catch (DiskFileUpload.SizeLimitExceededException e) {
    188             // Special handling for uploads that are too big.
    189             request.setAttribute(MultipartRequestHandler.ATTRIBUTE_MAX_LENGTH_EXCEEDED,
    190                 Boolean.TRUE);
    191 
    192             return;
    193         } catch (FileUploadException e) {
    194             log.error("Failed to parse multipart request", e);
    195             throw new ServletException(e);
    196         }
    197 
    198         // Partition the items into form fields and files.
    199         Iterator iter = items.iterator();
    200 
    201         while (iter.hasNext()) {
    202             FileItem item = (FileItem) iter.next();
    203 
    204             if (item.isFormField()) {
    205                 addTextParameter(request, item);
    206             } else {
    207                 addFileParameter(item);
    208             }
    209         }
    210     }
    211 
    212     /**
    213      * <p> Returns a hash table containing the text (that is, non-file)
    214      * request parameters. </p>
    215      *
    216      * @return The text request parameters.
    217      */
    218     public Hashtable getTextElements() {
    219         return this.elementsText;
    220     }
    221 
    222     /**
    223      * <p> Returns a hash table containing the file (that is, non-text)
    224      * request parameters. </p>
    225      *
    226      * @return The file request parameters.
    227      */
    228     public Hashtable getFileElements() {
    229         return this.elementsFile;
    230     }
    231 
    232     /**
    233      * <p> Returns a hash table containing both text and file request
    234      * parameters. </p>
    235      *
    236      * @return The text and file request parameters.
    237      */
    238     public Hashtable getAllElements() {
    239         return this.elementsAll;
    240     }
    241 
    242     /**
    243      * <p> Cleans up when a problem occurs during request processing. </p>
    244      */
    245     public void rollback() {
    246         Iterator iter = elementsFile.values().iterator();
    247 
    248         Object o;
    249         while (iter.hasNext()) {
    250             o = iter.next();
    251             if (o instanceof List) {
    252                 for (Iterator i = ((List)o).iterator(); i.hasNext(); ) {
    253                     ((FormFile)i.next()).destroy();
    254                 }
    255             } else {
    256                 ((FormFile)o).destroy();
    257             }
    258         }
    259     }
    260 
    261     /**
    262      * <p> Cleans up at the end of a request. </p>
    263      */
    264     public void finish() {
    265         rollback();
    266     }
    267 
    268     // -------------------------------------------------------- Support Methods
    269 
    270     /**
    271      * <p> Returns the maximum allowable size, in bytes, of an uploaded file.
    272      * The value is obtained from the current module's controller
    273      * configuration. </p>
    274      *
    275      * @param mc The current module's configuration.
    276      * @return The maximum allowable file size, in bytes.
    277      */
    278     protected long getSizeMax(ModuleConfig mc) {
    279         return convertSizeToBytes(mc.getControllerConfig().getMaxFileSize(),
    280             DEFAULT_SIZE_MAX);
    281     }
    282 
    283     /**
    284      * <p> Returns the size threshold which determines whether an uploaded
    285      * file will be written to disk or cached in memory. </p>
    286      *
    287      * @param mc The current module's configuration.
    288      * @return The size threshold, in bytes.
    289      */
    290     protected long getSizeThreshold(ModuleConfig mc) {
    291         return convertSizeToBytes(mc.getControllerConfig().getMemFileSize(),
    292             DEFAULT_SIZE_THRESHOLD);
    293     }
    294 
    295     /**
    296      * <p> Converts a size value from a string representation to its numeric
    297      * value. The string must be of the form nnnm, where nnn is an arbitrary
    298      * decimal value, and m is a multiplier. The multiplier must be one of
    299      * 'K', 'M' and 'G', representing kilobytes, megabytes and gigabytes
    300      * respectively. </p><p> If the size value cannot be converted, for
    301      * example due to invalid syntax, the supplied default is returned
    302      * instead. </p>
    303      *
    304      * @param sizeString  The string representation of the size to be
    305      *                    converted.
    306      * @param defaultSize The value to be returned if the string is invalid.
    307      * @return The actual size in bytes.
    308      */
    309     protected long convertSizeToBytes(String sizeString, long defaultSize) {
    310         int multiplier = 1;
    311 
    312         if (sizeString.endsWith("K")) {
    313             multiplier = 1024;
    314         } else if (sizeString.endsWith("M")) {
    315             multiplier = 1024 * 1024;
    316         } else if (sizeString.endsWith("G")) {
    317             multiplier = 1024 * 1024 * 1024;
    318         }
    319 
    320         if (multiplier != 1) {
    321             sizeString = sizeString.substring(0, sizeString.length() - 1);
    322         }
    323 
    324         long size = 0;
    325 
    326         try {
    327             size = Long.parseLong(sizeString);
    328         } catch (NumberFormatException nfe) {
    329             log.warn("Invalid format for file size ('" + sizeString
    330                 + "'). Using default.");
    331             size = defaultSize;
    332             multiplier = 1;
    333         }
    334 
    335         return (size * multiplier);
    336     }
    337 
    338     /**
    339      * <p> Returns the path to the temporary directory to be used for uploaded
    340      * files which are written to disk. The directory used is determined from
    341      * the first of the following to be non-empty. <ol> <li>A temp dir
    342      * explicitly defined either using the <code>tempDir</code> servlet init
    343      * param, or the <code>tempDir</code> attribute of the &lt;controller&gt;
    344      * element in the Struts config file.</li> <li>The container-specified
    345      * temp dir, obtained from the <code>javax.servlet.context.tempdir</code>
    346      * servlet context attribute.</li> <li>The temp dir specified by the
    347      * <code>java.io.tmpdir</code> system property.</li> (/ol> </p>
    348      *
    349      * @param mc The module config instance for which the path should be
    350      *           determined.
    351      * @return The path to the directory to be used to store uploaded files.
    352      */
    353     protected String getRepositoryPath(ModuleConfig mc) {
    354         // First, look for an explicitly defined temp dir.
    355         String tempDir = mc.getControllerConfig().getTempDir();
    356 
    357         // If none, look for a container specified temp dir.
    358         if ((tempDir == null) || (tempDir.length() == 0)) {
    359             if (servlet != null) {
    360                 ServletContext context = servlet.getServletContext();
    361                 File tempDirFile =
    362                     (File) context.getAttribute("javax.servlet.context.tempdir");
    363 
    364                 tempDir = tempDirFile.getAbsolutePath();
    365             }
    366 
    367             // If none, pick up the system temp dir.
    368             if ((tempDir == null) || (tempDir.length() == 0)) {
    369                 tempDir = System.getProperty("java.io.tmpdir");
    370             }
    371         }
    372 
    373         if (log.isTraceEnabled()) {
    374             log.trace("File upload temp dir: " + tempDir);
    375         }
    376 
    377         return tempDir;
    378     }
    379 
    380     /**
    381      * <p> Adds a regular text parameter to the set of text parameters for
    382      * this request and also to the list of all parameters. Handles the case
    383      * of multiple values for the same parameter by using an array for the
    384      * parameter value. </p>
    385      *
    386      * @param request The request in which the parameter was specified.
    387      * @param item    The file item for the parameter to add.
    388      */
    389     protected void addTextParameter(HttpServletRequest request, FileItem item) {
    390         String name = item.getFieldName();
    391         String value = null;
    392         boolean haveValue = false;
    393         String encoding = null;
    394 
    395         if (item instanceof DiskFileItem) {
    396             encoding = ((DiskFileItem)item).getCharSet();
    397             if (log.isDebugEnabled()) {
    398                 log.debug("DiskFileItem.getCharSet=[" + encoding + "]");
    399             }
    400         }
    401 
    402         if (encoding == null) {
    403             encoding = request.getCharacterEncoding();
    404             if (log.isDebugEnabled()) {
    405                 log.debug("request.getCharacterEncoding=[" + encoding + "]");
    406             }
    407         }
    408 
    409         if (encoding != null) {
    410             try {
    411                 value = item.getString(encoding);
    412                 haveValue = true;
    413             } catch (Exception e) {
    414                 // Handled below, since haveValue is false.
    415             }
    416         }
    417 
    418         if (!haveValue) {
    419             try {
    420                 value = item.getString("ISO-8859-1");
    421             } catch (java.io.UnsupportedEncodingException uee) {
    422                 value = item.getString();
    423             }
    424 
    425             haveValue = true;
    426         }
    427 
    428         if (request instanceof MultipartRequestWrapper) {
    429             MultipartRequestWrapper wrapper = (MultipartRequestWrapper) request;
    430 
    431             wrapper.setParameter(name, value);
    432         }
    433 
    434         String[] oldArray = (String[]) elementsText.get(name);
    435         String[] newArray;
    436 
    437         if (oldArray != null) {
    438             newArray = new String[oldArray.length + 1];
    439             System.arraycopy(oldArray, 0, newArray, 0, oldArray.length);
    440             newArray[oldArray.length] = value;
    441         } else {
    442             newArray = new String[] { value };
    443         }
    444 
    445         elementsText.put(name, newArray);
    446         elementsAll.put(name, newArray);
    447     }
    448 
    449     /**
    450      * <p> Adds a file parameter to the set of file parameters for this
    451      * request and also to the list of all parameters. </p>
    452      *
    453      * @param item The file item for the parameter to add.
    454      */
    455     protected void addFileParameter(FileItem item) {
    456         FormFile formFile = new CommonsFormFile(item);
    457 
    458         String name = item.getFieldName();
    459         if (elementsFile.containsKey(name)) {
    460             Object o = elementsFile.get(name);
    461             if (o instanceof List) {
    462                 ((List)o).add(formFile);
    463             } else {
    464                 List list = new ArrayList();
    465                 list.add((FormFile)o);
    466                 list.add(formFile);
    467                 elementsFile.put(name, list);
    468                 elementsAll.put(name, list);
    469             }
    470         } else {
    471             elementsFile.put(name, formFile);
    472             elementsAll.put(name, formFile);
    473         }
    474     }
    475 
    476     // ---------------------------------------------------------- Inner Classes
    477 
    478     /**
    479      * <p> This class implements the Struts <code>FormFile</code> interface by
    480      * wrapping the Commons FileUpload <code>FileItem</code> interface. This
    481      * implementation is <i>read-only</i>; any attempt to modify an instance
    482      * of this class will result in an <code>UnsupportedOperationException</code>.
    483      * </p>
    484      */
    485     static class CommonsFormFile implements FormFile, Serializable {
    486         /**
    487          * <p> The <code>FileItem</code> instance wrapped by this object.
    488          * </p>
    489          */
    490         FileItem fileItem;
    491 
    492         /**
    493          * Constructs an instance of this class which wraps the supplied file
    494          * item. </p>
    495          *
    496          * @param fileItem The Commons file item to be wrapped.
    497          */
    498         public CommonsFormFile(FileItem fileItem) {
    499             this.fileItem = fileItem;
    500         }
    501 
    502         /**
    503          * <p> Returns the content type for this file. </p>
    504          *
    505          * @return A String representing content type.
    506          */
    507         public String getContentType() {
    508             return fileItem.getContentType();
    509         }
    510 
    511         /**
    512          * <p> Sets the content type for this file. <p> NOTE: This method is
    513          * not supported in this implementation. </p>
    514          *
    515          * @param contentType A string representing the content type.
    516          */
    517         public void setContentType(String contentType) {
    518             throw new UnsupportedOperationException(
    519                 "The setContentType() method is not supported.");
    520         }
    521 
    522         /**
    523          * <p> Returns the size, in bytes, of this file. </p>
    524          *
    525          * @return The size of the file, in bytes.
    526          */
    527         public int getFileSize() {
    528             return (int) fileItem.getSize();
    529         }
    530 
    531         /**
    532          * <p> Sets the size, in bytes, for this file. <p> NOTE: This method
    533          * is not supported in this implementation. </p>
    534          *
    535          * @param filesize The size of the file, in bytes.
    536          */
    537         public void setFileSize(int filesize) {
    538             throw new UnsupportedOperationException(
    539                 "The setFileSize() method is not supported.");
    540         }
    541 
    542         /**
    543          * <p> Returns the (client-side) file name for this file. </p>
    544          *
    545          * @return The client-size file name.
    546          */
    547         public String getFileName() {
    548             return getBaseFileName(fileItem.getName());
    549         }
    550 
    551         /**
    552          * <p> Sets the (client-side) file name for this file. <p> NOTE: This
    553          * method is not supported in this implementation. </p>
    554          *
    555          * @param fileName The client-side name for the file.
    556          */
    557         public void setFileName(String fileName) {
    558             throw new UnsupportedOperationException(
    559                 "The setFileName() method is not supported.");
    560         }
    561 
    562         /**
    563          * <p> Returns the data for this file as a byte array. Note that this
    564          * may result in excessive memory usage for large uploads. The use of
    565          * the {@link #getInputStream() getInputStream} method is encouraged
    566          * as an alternative. </p>
    567          *
    568          * @return An array of bytes representing the data contained in this
    569          *         form file.
    570          * @throws FileNotFoundException If some sort of file representation
    571          *                               cannot be found for the FormFile
    572          * @throws IOException           If there is some sort of IOException
    573          */
    574         public byte[] getFileData()
    575             throws FileNotFoundException, IOException {
    576             return fileItem.get();
    577         }
    578 
    579         /**
    580          * <p> Get an InputStream that represents this file.  This is the
    581          * preferred method of getting file data. </p>
    582          *
    583          * @throws FileNotFoundException If some sort of file representation
    584          *                               cannot be found for the FormFile
    585          * @throws IOException           If there is some sort of IOException
    586          */
    587         public InputStream getInputStream()
    588             throws FileNotFoundException, IOException {
    589             return fileItem.getInputStream();
    590         }
    591 
    592         /**
    593          * <p> Destroy all content for this form file. Implementations should
    594          * remove any temporary files or any temporary file data stored
    595          * somewhere </p>
    596          */
    597         public void destroy() {
    598             fileItem.delete();
    599         }
    600 
    601         /**
    602          * <p> Returns the base file name from the supplied file path. On the
    603          * surface, this would appear to be a trivial task. Apparently,
    604          * however, some Linux JDKs do not implement <code>File.getName()</code>
    605          * correctly for Windows paths, so we attempt to take care of that
    606          * here. </p>
    607          *
    608          * @param filePath The full path to the file.
    609          * @return The base file name, from the end of the path.
    610          */
    611         protected String getBaseFileName(String filePath) {
    612             // First, ask the JDK for the base file name.
    613             String fileName = new File(filePath).getName();
    614 
    615             // Now check for a Windows file name parsed incorrectly.
    616             int colonIndex = fileName.indexOf(":");
    617 
    618             if (colonIndex == -1) {
    619                 // Check for a Windows SMB file path.
    620                 colonIndex = fileName.indexOf("\\\\");
    621             }
    622 
    623             int backslashIndex = fileName.lastIndexOf("\\");
    624 
    625             if ((colonIndex > -1) && (backslashIndex > -1)) {
    626                 // Consider this filename to be a full Windows path, and parse it
    627                 // accordingly to retrieve just the base file name.
    628                 fileName = fileName.substring(backslashIndex + 1);
    629             }
    630 
    631             return fileName;
    632         }
    633 
    634         /**
    635          * <p> Returns the (client-side) file name for this file. </p>
    636          *
    637          * @return The client-size file name.
    638          */
    639         public String toString() {
    640             return getFileName();
    641         }
    642     }
    643 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
